---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: fusion
navigation-topic: workfront-fusion-navigation-topic
title: Llamada a las API de Workfront y Fusion desde la extensión
description: Llamada a las API de Workfront y Fusion desde la extensión
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: 925a8ee910434c474d527c2914897d7c42e4a3d1
workflow-type: tm+mt
source-wordcount: 1083
ht-degree: 0%

---


# Llamada a las API de Workfront y Fusion desde la extensión

>[!NOTE]
>
>Este artículo asume cierta familiaridad con las herramientas de desarrollo de software.

La referencia de contexto de Fusion le proporciona el token IMS del usuario que ha iniciado sesión, por lo que un paso siguiente natural es llamar a las API de Workfront o Fusion y mostrar datos reales. Esto no es posible debido a CORS. Este artículo muestra cómo superar esa limitación mediante una acción de tiempo de ejecución de App Builder como proxy del lado del servidor e incluye un ejemplo (el panel de suscripciones de evento).

## Por qué falla una llamada directa del explorador (CORS)

La interfaz de usuario visible se ejecuta en un `<iframe>` servido desde la CDN de Adobe (`https://<your-app>.adobeio-static.net`). Cuando esa página realiza `fetch(...)` en una API de Workfront o Fusion con un origen **diferente**, el explorador exige el Intercambio de recursos de origen cruzado (CORS). A menos que la API devuelva explícitamente `Access-Control-Allow-Origin` para el origen de CDN, el explorador bloqueará la respuesta. Estas API no lista de permitidos orígenes de extensión arbitrarios, por lo que las llamadas directas del invitado fallan.

Para obtener información sobre CORS, consulte [CORS](https://developer.mozilla.org/docs/Web/HTTP/CORS).

## Llame a su propia acción de tiempo de ejecución sin CORS

La solución para esto es llamar a su propia acción de tiempo de ejecución sin CORS.

Las aplicaciones de App Builder pueden incluir acciones de tiempo de ejecución, que son pequeñas funciones sin servidor que se ejecutan en Adobe I/O Runtime del lado del servidor. Las llamadas de servidor a servidor no están sujetas al CORS del explorador. Y como la acción forma parte de la aplicación, el invitado puede llamarla con una dirección URL relativa, que es del mismo origen y, por lo tanto, no está bloqueada.

```
  Guest UI (browser, adobeio-static.net)
     │  fetch('/api/v1/web/<app>/wf-proxy?...')   ← relative = same-origin, no CORS
     ▼
  Your runtime action  (Adobe I/O Runtime, server-side)
     │  fetch('https://fusion.adobe.com/api/v3/...')  ← server-to-server, no CORS
     ▼
  Workfront / Fusion API
```

La acción recibe el token IMS del usuario del invitado y lo reenvía al flujo ascendente, por lo que las llamadas se siguen realizando en nombre del usuario con sus permisos.

## Paso 1: Declarar la acción

Las acciones en tiempo de ejecución se declaran en `app.config.yaml` en `runtimeManifest` de la extensión. Agregar una acción `wf-proxy` junto a la extensión:

```yaml
extensions:
  fusion/nav-organization/1:
    $include: src/fusion-nav-organization-1/ext.config.yaml
    runtimeManifest:
      packages:
        fusion-uix-guest:                # ← your package name; part of the action URL
          license: Apache-2.0
          actions:
            wf-proxy:
              function: src/fusion-nav-organization-1/actions/wf-proxy/index.js
              web: 'yes'                  # exposes it at /api/v1/web/<package>/wf-proxy
              runtime: nodejs:22
              inputs:
                LOG_LEVEL: debug
              annotations:
                require-adobe-auth: false # see note below
                final: true
```

La acción se vuelve accesible en:

```
/api/v1/web/<package>/<action>     e.g.  /api/v1/web/fusion-uix-guest/wf-proxy
```

### `require-adobe-auth`: verdadero frente a falso

Esta anotación controla si la puerta de enlace de Adobe valida un token de IMS antes de que se ejecute la acción.

* **`true`:** El valor predeterminado seguro.  La puerta de enlace rechaza las llamadas no autenticadas. Sin embargo, el validador es estricto sobre los encabezados que espera y puede rechazar solicitudes o soltar encabezados personalizados que necesite la llamada ascendente. Si esto sucede, se mostrará como `401` aunque el token sea válido.
* **`false`:** omite la comprobación de puerta de enlace. La acción se puede invocar públicamente, por lo que **debe** aplicar la autorización usted mismo. Requiera un portador de `Authorization` en la acción y rechace si falta, a continuación, y reenvíelo en sentido ascendente, donde Workfront y Fusion lo validan. Combinada con una lista de permitidos de destino estricta, descrita en el paso 2, esta es la ruta fiable para un proxy que necesita pasar encabezados personalizados.

>[!TIP]
>
> Pruebe `true` primero. Si ve un(a) `401` que no puede explicar porque el token es válido y funciona en otra parte, cambie a `false` **y** para mantener la comprobación de portador y la lista de permitidos en su acción de modo que la seguridad se siga aplicando en sentido ascendente.

## Paso 2: escribir la acción para un proxy incluido en la lista de permitidos

Crear `src/fusion-nav-organization-1/actions/wf-proxy/index.js`. Hay dos reglas que lo mantienen seguro: una lista de permitidos de destinos ascendentes para que la acción no se pueda usar como retransmisión abierta y un token de portador requerido que se reenvía en sentido ascendente.

```js
const fetch = require('node-fetch')
const { Core } = require('@adobe/aio-sdk')
const { errorResponse, getBearerToken, checkMissingRequestInputs } = require('../utils')

// Page-through query params (see "Paginate list results" below).
const pageQuery = (p) => {
  const q = new URLSearchParams()
  if (p.start != null) q.set('start', p.start)
  if (p.limit != null) q.set('limit', p.limit)
  return q
}

// Only these upstreams may be reached. Never build the URL from arbitrary input.
const TARGETS = {
  subscriptions: {
    method: 'GET',
    url: () => 'https://<your-wf-host>/attask/eventsubscription/api/v1/subscriptions',
  },
  hooks: {
    method: 'GET',
    // Fusion hooks are team-scoped: teamId is a REQUIRED query param (see below).
    url: (p) => {
      const q = pageQuery(p)
      if (p.teamId) q.set('teamId', p.teamId)
      return `https://fusion.adobe.com/api/v3/hooks?${q.toString()}`
    },
  },
  scenarios: {
    method: 'GET',
    url: (p) => {
      const q = pageQuery(p)
      if (p.fusionOrgId) q.set('organizationId', p.fusionOrgId)
      return `https://fusion.adobe.com/api/v3/scenarios?${q.toString()}`
    },
  },
}

async function main (params) {
  const logger = Core.Logger('main', { level: params.LOG_LEVEL || 'info' })
  try {
    const missing = checkMissingRequestInputs(params, ['target'], ['Authorization'])
    if (missing) return errorResponse(400, missing, logger)

    const target = TARGETS[params.target]
    if (!target) return errorResponse(400, `unknown target '${params.target}'`, logger)

    const token = getBearerToken(params)              // reads params.__ow_headers.authorization
    const headers = { authorization: `Bearer ${token}`, 'content-type': 'application/json' }
    if (params.orgId) headers['x-gw-ims-org-id'] = params.orgId        // Adobe IMS org id
    if (params.fusionOrgId) headers['x-organization-id'] = params.fusionOrgId  // Fusion tenant id
    if (params.teamId) headers['x-team-id'] = params.teamId            // Fusion team id

    const res = await fetch(target.url(params), { method: target.method, headers })
    const text = await res.text()
    let body
    try { body = JSON.parse(text) } catch (e) { body = text }

    if (!res.ok) {
      return { statusCode: res.status, body: { error: `upstream ${res.status}`, target: params.target, details: body } }
    }
    return { statusCode: 200, body }
  } catch (error) {
    logger.error(error)
    return errorResponse(500, 'server error: ' + error.message, logger)
  }
}

exports.main = main
```

`getBearerToken`, `errorResponse` y `checkMissingRequestInputs` provienen de la `actions/utils.js` generada, donde la plantilla los andamia. `getBearerToken` lee `params.__ow_headers.authorization`, que es donde la puerta de enlace coloca el encabezado `Authorization` entrante.

## Paso 3: Invoca la acción desde el invitado

Desde la interfaz de usuario, `fetch` la acción con una dirección URL relativa (del mismo origen) y envía el token de IMS como portador. Pase los ID de organización y equipo que necesita el flujo ascendente como parámetros de consulta.

```js
const PROXY_URL = "/api/v1/web/fusion-uix-guest/wf-proxy";

async function callProxy(target, token, { imsOrgId, fusionOrgId, teamId, start, limit } = {}) {
  const params = new URLSearchParams({ target });
  if (imsOrgId) params.set("orgId", imsOrgId);          // → x-gw-ims-org-id
  if (fusionOrgId) params.set("fusionOrgId", fusionOrgId); // → x-organization-id
  if (teamId) params.set("teamId", teamId);             // → x-team-id
  if (start != null) params.set("start", start);        // pagination offset
  if (limit != null) params.set("limit", limit);        // pagination page size
  const res = await fetch(`${PROXY_URL}?${params.toString()}`, {
    headers: { authorization: `Bearer ${token}` },
  });
  if (!res.ok) throw new Error(`${target} request failed: ${res.status}`);
  return res.json();
}
```

Obtener `token`, `imsOrgId`, `fusionOrgId` y `teamId` del contexto:

```js
const token       = connection.sharedContext.get("imsToken");
const imsOrgId    = connection.sharedContext.get("imsOrgId");
const fusionOrgId = connection.sharedContext.get("organization")?.id; // Fusion tenant id
const teamId      = connection.sharedContext.get("team")?.id;
```

Para obtener información sobre el contexto, consulte [La referencia de contexto de Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md).

## Detalles de la API de Fusion v3

Lo que funcionó para el tablero en `https://fusion.adobe.com/api/v3`:

| Encabezado/parámetro | Valor | Notas |
| ---------------- | ------- | ------- |
| `Authorization` | `Bearer <imsToken>` | El token IMS del usuario del contexto. |
| `x-organization-id` | `organization.id` | El ID del inquilino de Fusion, no el ID de la organización de IMS. Fusion identifica al inquilino con esto. |
| `x-team-id` | `team.id` | Enviar cuando la llamada tenga alcance de equipo. |
| `x-gw-ims-org-id` | `imsOrgId` | ID de organización de IMS de Adobe, para la puerta de enlace. |

Tenga en cuenta las siguientes advertencias:

* **`GET /api/v3/hooks`tiene ámbito de equipo:** `teamId` es un **parámetro de consulta necesario** (`/api/v3/hooks?teamId=...`). Sin él, obtendrá un `400`. Esto significa que los vínculos vuelven para el *equipo activo solamente*; para cubrir una organización, crear bucles en los equipos y combinar.
* **`GET /api/v3/scenarios`** funciona con `organizationId` (`/api/v3/scenarios?organizationId=...`).

>[!NOTE]
>
> La referencia oficial es [Workfront Fusion API](https://developer.adobe.com/workfront-fusion-apis/) de Adobe. Los requisitos de encabezado/autenticación varían según la puerta de enlace. Esta tabla refleja lo que realmente necesitaba la demostración. Si una llamada devuelve `401`/`400`, vuelva a comprobar primero estos encabezados.

## Paginar resultados de lista

Los extremos de lista de Fusion v3 (enlaces, escenarios) devuelven una **página** a la vez, no todo el conjunto. Una respuesta tiene este aspecto:

```json
{
  "items": [ /* ...this page of records... */ ],
  "_page": { "start": 0, "limit": 100, "total": 342 }
}
```

Los registros están bajo **`items`** y los metadatos de paginación están bajo **`_page`**. La página tiene los parámetros de consulta **`start`** (desplazamiento) y **`limit`** (tamaño de página). El proxy de arriba pasa por ambos, por lo que pagina al invitado haciendo un bucle hasta que hayas recopilado todo:

```js
const PAGE_LIMIT = 100;

async function fetchAllPages(target, token, opts = {}) {
  const all = [];
  let start = 0;
  // Stop when a page returns fewer than PAGE_LIMIT items, or when _page.total is reached.
  for (;;) {
    const res = await callProxy(target, token, { ...opts, start, limit: PAGE_LIMIT });
    const items = res.items ?? [];
    all.push(...items);

    const total = res._page?.total;
    const done = items.length < PAGE_LIMIT || (total != null && all.length >= total);
    if (done) break;
    start += PAGE_LIMIT;
  }
  return all;
}
```

Si prefiere mantener la paginación fuera del explorador, realice el mismo bucle dentro de la acción de tiempo de ejecución y devuelva la matriz `items` combinada en una respuesta. En cualquier caso, no suponga que la primera página es todo el conjunto de resultados. De lo contrario, un equipo con más de una página de vínculos tendría el aspecto de que le faltan escenarios.

## Lista de comprobación de seguridad

* **flujos ascendentes de Lista de permitidos.** Nunca construya la dirección URL de destino a partir de la entrada del cliente sin procesar. Asigne una clave corta `target` a una dirección URL fija, como en el paso 2. Esto evita que la acción se convierta en una retransmisión abierta.
* **Requiere el token de portador** en la acción y reenvíalo en sentido ascendente. Permita que Workfront y Fusion apliquen los permisos del usuario.
* **Nunca registre el token.** `imsToken` es una credencial. Tenga en cuenta `LOG_LEVEL` lo que `stringParameters` imprime.
* **Reenviar solo a través de HTTPS** a hosts de Adobe y Workfront de confianza.

## Ejemplo trabajado: el panel de suscripciones de evento

El tablero de demostración une tres fuentes para mostrar, por cada suscripción de evento de Workfront, si un escenario de Fusion coincidente está en buen estado:

1. `fetchSubscriptions()` → suscripciones a eventos de Workfront (con contadores recibidos/pasados).
1. `fetchHooks(teamId)` → enlaces de Fusion para el equipo activo (paginado con `fetchAllPages`).
1. `fetchScenarios(fusionOrgId)` → escenarios de Fusion para la organización (paginado con `fetchAllPages`).

**join** los encadena, pero hay un problema al que vale la pena llamar: una suscripción a Workfront y el vínculo Fusion al que apunta en **hosts diferentes**, por lo que sus campos de URL no son iguales byte a byte. Lo que es estable es el **token al final de la URL del gancho web** (el último segmento de ruta). Coincidencia en ese token final, no en la dirección URL completa. El enlace `scenarioId` entonces coincide con el `id` de un escenario:

```
subscription.targetUrl  ──(trailing token)──▶  hook.url
                                                hook.scenarioId  ──▶  scenario.id
```

```js
// Reduce a webhook URL to its trailing token so hosts/bases can differ.
function hookKey(url) {
  if (!url) return "";
  const path = String(url).trim().toLowerCase().split(/[?#]/)[0].replace(/\/+$/, "");
  const i = path.lastIndexOf("/");
  return i >= 0 ? path.slice(i + 1) : path;
}

// Index hooks by token, then look each subscription up by the same token.
const hooksByToken = new Map(hooks.map((h) => [hookKey(pick(h, ["url", "address", "targetUrl"], "")), h]));
const hook = hooksByToken.get(hookKey(pick(sub, ["url", "endpointUrl", "targetUrl", "target.url", "callbackUrl"], "")));
```

El estado se deriva de la unión:

* **Roto**: no hay ningún vínculo coincidente o el vínculo es `gone`.
* **Filtrado**: coincidió, pero `passed < received` (los eventos llegan pero se filtran antes de que se ejecute el escenario).
* **Correcto**: coincidió y pasó.

Dado que las formas de carga útil reales varían, el cliente asigna los campos de forma defensiva, intentando varias claves candidatas por campo, de modo que una diferencia menor de la API no interrumpe la tabla:

```js
function pick(obj, keys, fallback) {
  for (const key of keys) {
    const value = key.split(".").reduce((acc, part) => (acc == null ? acc : acc[part]), obj);
    if (value != null) return value;
  }
  return fallback;
}
```

Este es solo un ejemplo. El mismo patrón de proxy funciona para cualquier API de Workfront o Fusion que necesite.
