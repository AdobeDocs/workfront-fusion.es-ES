---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: Solución de problemas de extensiones personalizadas
description: Solución de problemas de extensiones personalizadas
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: a9dd86f7dc4070ad98c7c4a526a6a38939097940
workflow-type: tm+mt
source-wordcount: 1136
ht-degree: 0%

---


# Solución de problemas de extensiones personalizadas

>[!NOTE]
>
>Este artículo asume cierta familiaridad con las herramientas de desarrollo de software.

Este artículo presenta algunas soluciones a los problemas que es más probable que encuentre al crear extensiones personalizadas, aproximadamente en el orden en que se producen durante el desarrollo.

## Lista de comprobación rápida

Si algo no funciona, compruebe primero lo siguiente:

* Node.js es la versión 18 o 20 (`node --version`).
* Ha iniciado sesión (`aio login`) y se encuentra en la organización, el proyecto o el espacio de trabajo correcto (`aio console where`).
* El nombre del punto de extensión coincide exactamente, incluida la versión: `fusion/nav-organization/1`.
* El `url` de `getWidget()` coincide con una ruta de su aplicación.
* Su interfaz de usuario visible llama a `attach({ id })`.
* Está viendo el conjunto correcto de extensiones en Fusion:
  * Para ver una compilación de fase, implemente en Fase y active el conmutador Extensiones de fase en su perfil de Fusion (Configuración del producto > Perfil de Fusion > Preferencias).
  * Para ver una extensión publicada, implemente en Producción y haga que se apruebe.

## Error 1060: &quot;El punto de extensión no existe&quot;

**Mensaje completo:** `CoreConsoleAPISDK ... 1060: Extension point 'fusion/nav-organization/1' does not exist` durante `aio app deploy`.

**Significado:** El punto de extensión de Fusion aún no está habilitado (&quot;incorporado&quot;) para su organización de Adobe. Adobe valida, en el momento de la implementación, que el punto de extensión existe en el catálogo de la organización. Esto **no es** un problema con tu código o tu YAML.

**Corrección:** Pida al equipo de Fusion que incorpore los puntos de extensión (`fusion/nav-organization/1` o `fusion/nav-team/1`) para su organización IMS. Cuando solicite la incorporación, incluya:

* su **id. de organización de IMS** (`XXXX@AdobeOrg`),
* los **puntos de extensión** que necesita,
* sus nombres de **Developer Console project and workspace**.

Una vez confirmada la incorporación, vuelva a ejecutar `aio app deploy`.


## &quot;Esperando el mensaje inicial del iframe de destino&quot; / el panel gira para siempre

**Significado:** Fusion abrió su interfaz de usuario visible pero no completó el protocolo de enlace, así que se agotó el tiempo de espera de Fusion.

**Causas comunes:**

* `attach` solo está en el componente de registro, no en el widget visible.
* El `url` de `getWidget()` señala a una ruta que representa el componente **registro** (o una página en blanco) en lugar de su widget.
* El(la) `id` pasado(a) a `attach` difiere del(la) `id` utilizado(a) en `register`. Deben ser idénticos, así que mantenga ambos en `Constants.js`.

**Corrección:** Asegúrese de que el componente **visible** llama a `attach({ id })`:

```jsx
useEffect(() => {
  attach({ id: extensionId }).catch(console.error);
}, []);
```

Para obtener más información, consulte [Generar la interfaz de usuario de la extensión personalizada](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-05-build-ui-procedure.md).



## El botón de navegación no aparece en Fusion

Si el botón de navegación de la extensión personalizada no aparece en Fusion, compruebe estos elementos en orden:

1. **¿Está viendo el conjunto correcto de extensiones?** De forma predeterminada, Fusion solo muestra las extensiones publicadas, que se han implementado en Producción y se han aprobado. Si está probando una compilación de fase, active el conmutador Extensiones de fase en su perfil de Fusion (Configuración del producto > Perfil de Fusion > Preferencias) y vuelva a cargar. Los elementos de fase están etiquetados como **(fase)**.
Para obtener más información, consulte [Publicar su extensión personalizada](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-07-publish.md).
1. **¿Se revocó o se retrajo?** Una extensión revocada o retirada deja de aparecer en Fusion sin errores. Si desaparece un botón que funcionaba anteriormente, confirme que sigue activo en Adobe Exchange antes de buscar un problema de código.
1. **¿Se ha implementado en el espacio de trabajo correcto?** Implemente en el espacio de trabajo que realmente está cargando, el espacio de trabajo de ensayo cuando utilice el conmutador de prueba de ensayo.
1. **¿Se ha implementado en la organización correcta?** Inicie sesión en Fusion con una cuenta en la **misma** organización de IMS que implementó en.
1. **¿Se encuentra en la sección correcta?** `fusion/nav-organization/1` muestra bajo **Organización**; `fusion/nav-team/1` muestra bajo **Equipo** (primero debe seleccionar un equipo).
1. **¿Hay un error tipográfico en el nombre del punto de extensión?** Debe leer exactamente `fusion/nav-organization/1` tanto en `app.config.yaml` como en la ruta de inclusión de la carpeta `ext.config.yaml`.


## Aparece el botón pero el panel está en blanco

Si aparece el botón pero el panel está en blanco, compruebe lo siguiente:

* **Discordancia de ruta:** `url` de `getWidget()` (como `/index.html#/my-widget`) debe coincidir con `<Route>` en `App.js`. Una discrepancia carga una página sin componente.
* **Error de JavaScript:** abra la ficha Herramientas para desarrolladores del explorador (F12) > **Consola** y busque los errores procedentes del iframe. Corregir el error notificado y volver a implementar.
* **Falta/duplica el encabezado:** `hideWidgetHeader` en `getWidget()` controla si Fusion muestra el título sobre la interfaz de usuario. Configúrelo en `true` si procesa su propio encabezado.

## El iframe está bloqueado (política de seguridad de contenido/rechazo de la incriminación)

Fusion solo permite extensiones alojadas en la CDN de App Builder de Adobe (`*.adobeio-static.net`), que es donde `aio app deploy` coloca los archivos de forma predeterminada. Si aloja la interfaz de usuario en otro lugar, como un dominio personalizado, Fusion se niega a cargarla. Implemente a través de App Builder como se ha documentado, o pregunte al equipo de Fusion si su dominio puede estar incluido en la lista de permitidos.

## El contexto está vacío o obsoleto

* **Vacío justo después de la carga:** Lea el contexto **después de que** `attach` se resuelva, no antes. Hasta entonces, muestre el estado &quot;Conectando...&quot;.
* **No se actualiza cuando el usuario cambia de organización o equipo:** Suscríbase al evento `contextchange` y vuelva a leer las claves que contiene el controlador. Para obtener más información, consulte [Leer el contexto de los recursos compartidos de Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-05-build-ui-procedure.md#read-the-context-fusion-shares) en el artículo Generar la interfaz de usuario de la extensión personalizada.
* **Las fechas tienen un aspecto incorrecto:** Los campos de fecha llegan con formato ISO **strings**, no con objetos `Date`. Agrupar entre ellos `new Date(...)`. Consulte [Fechas](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md#dates) en el artículo La referencia de contexto de Fusion.

## La llamada a una API falla con un error CORS

**Síntoma:** La consola del explorador muestra *&quot;Sin encabezado &#39;Access-Control-Allow-Origin&#39;&quot;* (o la solicitud está bloqueada) cuando la interfaz de usuario llama directamente a una API de Workfront/Fusion.

**Corrección:** No llame a esas API desde el explorador. Enrute la llamada a través de su propia **acción de tiempo de ejecución** de App Builder (del lado del servidor, sin CORS) y haga que el invitado llame a la acción con una URL relativa del mismo origen. Para obtener más información, consulte [Llamar a las API de Workfront y Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-10-calling-apis.md).


## La acción de proxy devuelve 401 incluso con un token válido

**Significado:** Con `require-adobe-auth: true`, la puerta de enlace de Adobe valida la llamada antes de que se ejecute la acción y puede rechazarla o soltar encabezados personalizados que el flujo ascendente necesite, mostrándolos como `401`.

**Corrección:** Establezca `require-adobe-auth: false` en la acción **y** aplique la autorización usted mismo. Requiera un portador `Authorization` en la acción, reenvíela en sentido ascendente y mantenga una lista de permitidos de destino estricta. Consulte [require-adobe-auth: true vs. false](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-10-calling-apis.md#require-adobe-auth-true-vs-false).

## Fusion `GET /api/v3/hooks` devuelve 400

**Significado:** El extremo de los vínculos es **de ámbito de equipo**, por lo que `teamId` es un parámetro de consulta obligatorio.

**Corrección:** Llamada `/api/v3/hooks?teamId=<team.id>`. Los enlaces vuelven únicamente para el equipo activo. Para cubrir una organización, realice un bucle en sus equipos y fusiónelos. Los escenarios, por el contrario, aceptan `organizationId`. Consulte [Detalles de la API de Fusion v3](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-10-calling-apis.md#fusion-v3-api-specifics).


## `aio` errores

* **`aio: command not found`:** La CLI no está instalada o no se encuentra en su RUTA. Vuelva a ejecutar `npm install -g @adobe/aio-cli` y, a continuación, abra un nuevo terminal.
* **Error de compilación/implementación en una versión de nodo completamente nueva:** Use el nodo **18 o 20 LTS**. Las versiones muy nuevas que no son de LTS a veces rompen la cadena de herramientas.
* **&quot;No es un desarrollador&quot; / no puede ver su organización:** El administrador de su organización de Adobe debe otorgarle la función **Desarrollador** y el acceso a App Builder. Para obtener más información, consulte [Configurar las herramientas de extensión de la interfaz de usuario y la cuenta](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-02-set-up-tools-account.md).
* **401 / token no válido durante la implementación o la detección:** Su sesión expiró o está mezclando entornos. Ejecute `aio logout`, luego `aio login`, confirme `aio console where` e implemente en el área de trabajo que está cargando.

## Recopilación de información para la asistencia

Recopile esta información para hacer el diagnóstico mucho más rápido:

* El comando exacto que ejecutó y el resultado de error **full**.
* Su **ID de organización de IMS**, **proyecto** y **espacio de trabajo**.
* El **punto de extensión** al que se está dirigiendo.
* Si `aio app deploy` se realizó correctamente y si la extensión es **publicada** (o, para una prueba de fase, si el conmutador de extensiones de fase está activado).
* Errores en el explorador **Consola** (F12) al abrir el panel en Fusion.
