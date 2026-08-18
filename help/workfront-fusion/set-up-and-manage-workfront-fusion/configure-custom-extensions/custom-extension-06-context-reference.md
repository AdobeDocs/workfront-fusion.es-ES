---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: La referencia de contexto de Fusion
description: La referencia de contexto de Fusion
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: a9dd86f7dc4070ad98c7c4a526a6a38939097940
workflow-type: tm+mt
source-wordcount: 757
ht-degree: 8%

---

# La referencia de contexto de Fusion

>[!NOTE]
>
>Este artículo asume cierta familiaridad con las herramientas de desarrollo de software.

Cuando la interfaz de usuario llama a `attach(...)`, Fusion comparte un objeto **context** que describe la sesión actual. Esta página enumera todos los campos, qué significa y cómo se relacionan los identificadores IMS de Fusion y Adobe.

## Cómo leer el contexto

* **Valores iniciales:** `connection.sharedContext.get("<key>")`
* **Actualizaciones:** Escuche el evento `contextchange`. El objeto más reciente llega el `event.detail.context`.

Para ver el patrón de código completo, consulte [Generar la interfaz de usuario de la extensión personalizada](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-05-build-ui-procedure.md).

```js
const organization = connection.sharedContext.get("organization");
const fusionOrgId  = organization?.id;        // Fusion's organization id
const imsOrgId     = connection.sharedContext.get("imsOrgId"); // Adobe IMS org id
```

## Claves de nivel superior

| Clave | Tipo | Descripción |
| ----- | ------ | ------------- |
| `imsToken` | cadena | El token de acceso de Adobe **IMS del usuario que inició sesión**. Use esto como un token de `Bearer` para llamar a las API de Adobe o Fusion en nombre del usuario. **Debido a que es confidencial, nunca lo registre ni lo muestre.** |
| `imsOrgId` | cadena | El identificador de organización de Adobe **IMS**, con el formato `XXXXXXXXXXXX@AdobeOrg`. |
| `imsUserId` | cadena | El Adobe **ID de usuario de IMS** del usuario que inició sesión. |
| `organization` | objeto | La **organización activa de Fusion completa**. Para obtener más información, vea [`organization` campos](#organization-fields) en este artículo. |
| `team` | objeto \| indefinido | El **equipo de Fusion activo completo**, cuando hay uno activo (siempre relevante para `fusion/nav-team/1`). Para obtener más información, vea [`team` campos](#team-fields) en este artículo. |
| `user` | objeto | **usuario de Fusion con sesión completa**. Para obtener más información, vea [`user` campos](#user-fields) en este artículo. |

### ID de Fusion e ID de IMS

Cada entidad tiene un **Fusion ID** (utilizado por las propias API de Fusion) y, si existe, un **Adobe IMS ID** (utilizado por las API de Adobe Platform):

| Entidad | ID de Fusion | ID de Adobe IMS |
| -------- | ----------- | -------------- |
| Organización | `organization.id` | `imsOrgId` (también expuesto como `organization.externalOrgId`) |
| Equipo | `team.id` | *(los equipos son solo de Fusion; sin ID de IMS)* |
| Usuario | `user.id` | `imsUserId` |

## `organization` campos

Estos campos se encuentran en el registro de organización activo. La mayoría de las extensiones solo requieren `id`, `name` y los identificadores.

| Campo | Tipo | Descripción |
| ------- | ------ | ------------- |
| `id` | cadena | ID de organización de Fusion. |
| `name` | cadena | Nombre para mostrar de organización |
| `externalOrgId` | cadena | ID de organización de IMS de Adobe (mismo valor que `imsOrgId`). |
| `externalId` | cadena | Identificador externo utilizado por las integraciones de Fusion |
| `countryId` | cadena | ID de configuración de país. |
| `timezoneId` | cadena | ID de configuración de zona horaria |
| `serviceName` | cadena | Identificador de servicio/plan |
| `teamIds` | cadena[] | ID de equipos de esta organización |
| `license` | objeto | Límites y derechos del plan, como operaciones, transferencia de datos, puestos de usuario y indicadores de funcionalidades |
| `scenariosCount` | number | Escenarios totales en la organización |
| `activeScenarios` | number | Escenarios activos actualmente |
| `activeApps` | number | Número de aplicaciones o conexiones activas |
| `operations`, `operationsExt` | number | Contadores de uso de operaciones |
| `transfer`, `transferExt` | number | Contadores de uso de transferencia de datos |
| `isPaused` | booleano | Si la organización está en pausa |
| `isDeleted` | booleano | Si la organización está marcada como eliminada |
| `imsEnabled` | booleano | Si la organización está vinculada a Adobe IMS |
| `usersCount` | number | Número de usuarios en la organización |
| `nextReset` | cadena (fecha) | Cuando se restablezcan los contadores de uso. Ver [Fechas](#dates) |

## `team` campos

Estos campos están presentes cuando un equipo está activo. Debe proporcionar una reserva en caso de que el equipo sea `undefined` (por ejemplo, en una pantalla de nivel de organización sin ningún equipo seleccionado).

| Campo | Tipo | Descripción |
| ------- | ------ | ------------- |
| `id` | cadena | ID del equipo de Fusion. |
| `name` | cadena | Nombre para mostrar del equipo. |
| `organizationId` | cadena | ID de Fusion de la organización a la que pertenece este equipo. |
| `country` | cadena | Configuración del país del equipo. |
| `timezone` | cadena | Zona horaria del equipo. |
| `license` | objeto | Límites y derechos a nivel de equipo. |
| `activeScenarios` | number | Escenarios activos en el equipo. |
| `activeApps` | number | Aplicaciones o conexiones activas en el equipo de. |
| `scenarioDrafts` | booleano | Indica si los borradores de escenarios están habilitados. |
| `isDeleted` | booleano | Si el equipo se marca como eliminado. |
| `created` | cadena (fecha) | Cuando se creó el equipo. Ver [Fechas](#dates). |

## `user` campos

Estos campos se aplican al usuario de Fusion que ha iniciado sesión.

| Campo | Tipo | Descripción |
| ------- | ------ | ------------- |
| `id` | cadena | ID de usuario de Fusion. |
| `name` | cadena | Nombre completo. |
| `email` | cadena | Correo electrónico. |
| `avatar` | cadena | URL de imagen de avatar. |
| `locale` | cadena | Configuración regional del usuario, como `en`. |
| `language` | cadena | Idioma preferido, cuando se establece. |
| `timezone` | cadena | Nombre de zona horaria. |
| `timezoneId` | cadena | ID de ajuste de zona horaria. |
| `countryId` | cadena | ID de configuración de país. |
| `localeId` | cadena | ID de configuración regional. |
| `features` | objeto | Indicadores de características por usuario (p. ej. `allow_apps`, `public_templates`). |
| `usersAdminsRoleId` | cadena | El ID de rol de administrador del usuario, cuando corresponda. |

>[!NOTE]
>
> El objeto `user` puede incluir campos internos adicionales. Solo debe confiar en los campos documentados aquí. Otros campos pueden cambiar sin previo aviso y algunos campos relacionados con la autenticación nunca deben registrarse ni mostrarse.

## Fechas

El contexto se serializa antes de que llegue a su extensión, por lo que los **campos de fecha se presentan como cadenas** (ISO 8601, como `"2026-06-24T00:00:00.000Z"`), no como objetos de JavaScript `Date`. Puede convertirlos si es necesario:

```js
const resetDate = new Date(context.organization.nextReset);
```

## Actualizaciones de contexto

Fusion vuelve a enviar todo el contexto (a través de `contextchange`) cuando:

* el usuario **cambia la organización**,
* el usuario **cambia de equipo**, o
* cambia la información **del usuario que inició sesión**.

Vuelva a leer siempre todas las claves que utilice dentro del controlador `contextchange` en lugar de suponer que sólo ha cambiado un valor.

## Prácticas recomendadas de seguridad

* **Nunca registrar, mostrar ni mantener `imsToken`.** Trátelo como una contraseña.
* Envíe el token solo a puntos finales de Adobe/Fusion de confianza, a través de HTTPS, como un token `Bearer`.
* No almacene datos personales del contexto más allá de lo que necesita su función.

## Utilice el token para llamar a las API de

Para convertir `imsToken` (más `organization.id` / `team.id`) en Workfront real o
Los datos de Fusion no permiten llamar a estas API directamente desde el explorador, ya que CORS bloquea
it. En su lugar, enrute la llamada a través de una pequeña acción de tiempo de ejecución de App Builder. Consulte
[Llamando a las API de Workfront y Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-10-calling-apis.md).


Para continuar el proceso de creación de una extensión personalizada, consulta [Publicar tu extensión](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-07-publish.md).
