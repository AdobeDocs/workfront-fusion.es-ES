---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: Tutorial de demostración de una extensión personalizada
description: Tutorial de demostración de una extensión personalizada
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: a9dd86f7dc4070ad98c7c4a526a6a38939097940
workflow-type: tm+mt
source-wordcount: 964
ht-degree: 0%

---


# Tutorial de demostración sobre la creación de una extensión personalizada en Fusion

>[!NOTE]
>
>Este artículo asume cierta familiaridad con las herramientas de desarrollo de software.

Esta demostración le guiará por la creación de una extensión personalizada, su implementación y su ejecución en Fusion.

Incluye:

* Andamiaje de una aplicación de App Builder desde la plantilla genérica de Experience Cloud Shell.
* Reasigne la aplicación a un punto de extensión de Fusion.
* Implemente la aplicación en el espacio de trabajo de fase.
* Active las pruebas de fase en Fusion y muestre la aplicación en ejecución.

Comenzar desde la plantilla en lugar de un `--standalone-app` vacío significa que se genera el bootstrap de la SPA para usted: `index.js`, `exc-runtime.js`, `App.js` con el enrutamiento y `ErrorBoundary`, y una muestra `ExtensionRegistration`. Los pasos activos de la demostración son redireccionar la configuración y editar dos archivos, que es exactamente como se creó el `fusion-uix-guest` real.

>[!NOTE]
>
> **Tiempo:** La demostración en vivo toma alrededor de 10 minutos después de que se hayan configurado las herramientas. Debe realizar la configuración única (Nodo 18/20, `aio` CLI, `aio login`) **antes** de la demostración. Para obtener instrucciones, consulte [Configurar las herramientas de extensión de la interfaz de usuario y la cuenta](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-02-set-up-tools-account.md).


## Antes de comenzar

Esto solo debe hacerse una vez, y puede hacerse fuera de la cámara antes de la demostración.

```sh
node --version          # must be 18 or 20
aio --version           # @adobe/aio-cli installed
aio login               # signs you into your Adobe org
aio console org select  # pick the org you'll demo in (same org as Fusion)
```

Dos cosas deben ser ciertas en la organización de demostración:

* El punto de extensión `fusion/nav-organization/1` está incorporado para la organización. Si no se incorpora, la implementación falla con el error 1060. Para obtener más información, consulte [Solución de problemas de extensiones personalizadas](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-08-troubleshooting.md).
* La función de extensiones personalizadas está habilitada en el host de Fusion. (Esta función está activada de forma predeterminada). Dado que demostrará una compilación de ensayo en lugar de una publicada, también activará el conmutador **Extensiones de ensayo** en su perfil de Fusion. (Este interruptor se muestra en el paso 7). Fusion solo muestra las extensiones publicadas hasta que lo haga.

## Paso 1: Generar la aplicación a partir de la plantilla genérica

```sh
aio app init my-fusion-extension --template @adobe/generator-app-excshell
cd my-fusion-extension
```

* Seleccione **Crear nuevo proyecto** cuando se le solicite y acepte el nombre sugerido.
* `@adobe/generator-app-excshell` es la plantilla genérica de extensión de interfaz de usuario **Experience Cloud Shell** y no es específica del producto. Andamiaje un SPA completo y en funcionamiento bajo `src/dx-excshell-1/`.

>[!NOTE]
>
>Si prefiere el menú, ejecute `aio app init my-fusion-extension`, elija **Agregar extensiones o aplicación independiente** > **Plantillas** y seleccione **&quot;Extensión UIX de App Builder para el shell de Experience Cloud&quot;**.

Obtendrá un conjunto de archivos, incluidos los siguientes:

```
my-fusion-extension/
|-- app.config.yaml
|-- src/dx-excshell-1/
    |-- ext.config.yaml
    |-- web-src/src/
        |-- index.js          // SPA bootstrap (exc-app Runtime + React render)
        |-- exc-runtime.js    // Experience Cloud Shell runtime glue
        |-- components/
            |-- App.js                    // Router + ErrorBoundary (generated)
            |-- ExtensionRegistration.js  // sample registration (generated)
```

## Paso 2: Añadir la biblioteca de invitados de Fusion

La plantilla ya incluye React, React Spectrum y exc-app. Añada la biblioteca que hable con el host de Fusion:

```sh
npm install @adobe/uix-guest
```

## Paso 3: Reasigne la configuración a Fusion

Abra **`app.config.yaml`** y cambie **solo la clave de punto de extensión** del punto de shell de Experience Cloud al de Fusion (deje la ruta de acceso `$include` tal cual):

```yaml
extensions:
  fusion/nav-organization/1:                 # was: dx/excshell/1
    $include: src/dx-excshell-1/ext.config.yaml
```

No es necesario cambiar nada más en la configuración. El nombre de carpeta `dx-excshell-1` es interno y no afecta a Fusion, por lo que puede dejarlo. Cambiar el nombre también significaría actualizar cualquier ruta de acción. Omita eso para la demostración.

>[!NOTE]
>
>Si está dirigiendo la sección **Equipo**, use `fusion/nav-team/1` en su lugar. Para enviar **tanto la organización como el equipo de** en producción, use **dos proyectos independientes**. Un paquete de punto de extensión por nombre de registro evita un conflicto de aplicación compartida.

## Paso 4: Editar los archivos de registro y widget

Todas las rutas son de menos de `src/dx-excshell-1/web-src/src/components/`.

### **`ExtensionRegistration.js`**

El archivo generado registra una muestra de Experience Cloud Shell. Reemplace su `methods` por el contrato de Fusion **`dashboard.getWidget`** para que Fusion sepa su título y dónde se encuentra la interfaz de usuario:

```js
import { Text } from "@adobe/react-spectrum";
import { register } from "@adobe/uix-guest";
import metadata from "../../../../app-metadata.json";
import { extensionId } from "./Constants";

function ExtensionRegistration() {
  const init = async () => {
    await register({
      id: extensionId,
      metadata,
      methods: {
        dashboard: {
          getWidget() {
            return {
              id: extensionId,
              title: "My Fusion tool",          // label on the Fusion nav button
              description: "Hello from App Builder",
              url: "/index.html#/widget",       // route to the visible UI (4b)
              widgetSize: { defaultWidth: 6, defaultHeight: 6 },
              hideWidgetHeader: false,
            };
          },
        },
      },
    });
  };
  init().catch(console.error);

  return <Text>Registering with Fusion...</Text>;
}

export default ExtensionRegistration;
```

Si `Constants.js` no existe al lado, créelo:

```js
module.exports = { extensionId: "my-fusion-extension" };
```

### `DashboardWidget.js`

Cree este archivo. Completa el protocolo de enlace y muestra el contexto de Fusion activo:

```js
import { useEffect, useState } from "react";
import { Flex, Heading, Text, View } from "@adobe/react-spectrum";
import { attach } from "@adobe/uix-guest";
import { extensionId } from "./Constants";

const KEYS = ["imsOrgId", "imsUserId", "organization", "team", "user"];

export default function DashboardWidget() {
  const [ctx, setCtx] = useState(null);

  useEffect(() => {
    attach({ id: extensionId })
      .then((guest) => {
        const read = () =>
          KEYS.reduce((acc, k) => ({ ...acc, [k]: guest.sharedContext.get(k) }), {});
        setCtx(read());
        guest.addEventListener("contextchange", () => setCtx(read()));
      })
      .catch((e) => console.error("attach failed", e));
  }, []);

  return (
    <View padding="size-300">
      <Heading level={2}>Hello from App Builder</Heading>
      {!ctx ? (
        <Text>Connecting to Fusion...</Text>
      ) : (
        <Flex direction="column" gap="size-100" marginTop="size-200">
          <Text>User: {ctx.user?.name ?? ctx.imsUserId}</Text>
          <Text>Organization: {ctx.organization?.name} (id {ctx.organization?.id})</Text>
          <Text>Team: {ctx.team?.name ?? "-"}</Text>
        </Flex>
      )}
    </View>
  );
}
```

### `App.js`

El enrutador generado ya envía `index` / `index.html` a `ExtensionRegistration`. Añada una ruta para el widget e impórtelo:

```js
import DashboardWidget from "./DashboardWidget";
// ...inside <Routes>, alongside the existing ExtensionRegistration routes:
<Route exact path="widget" element={<DashboardWidget />} />
```

> La ruta de acceso de ruta (`widget`) debe coincidir con el hash de `getWidget().url` (`/index.html#/widget`). Mantenga el `index.js` / `exc-runtime.js` generado y el resto de `App.js` exactamente como se encuentra en el andamiaje, ya que ese es el bootstrap que desea que proporcione la plantilla.

## Paso 5: Generación

```sh
aio app build
```

Esto compila el front-end y ejecuta el vínculo de metadatos que genera `app-metadata.json`. Corrija los errores antes de continuar.

## Paso 6: Implementación en fase

```sh
aio console workspace select     # choose Stage
aio app deploy
```

`deploy` aloja su interfaz de usuario en la red de distribución de contenido (CDN) de Adobe y registra el extremo de la extensión en el espacio de trabajo de ensayo, que es lo que permite que Fusion lo descubra. La CLI imprime la dirección URL del extremo, como `https://<project>-stage.adobeio-static.net`.

## Paso 7: Activar las pruebas de fase y mostrar la extensión en Fusion

1. Abra Fusion en Experience Cloud, haya iniciado sesión en la misma organización en la que ha implementado.
1. Abra el menú de avatar del usuario y vaya a **Configuración del producto** > **Perfil Fusion** > **Preferencias**.
1. Encienda el conmutador **Extensiones de ensayo** y confirme la recarga.

   Fusion ahora carga extensiones desde el espacio de trabajo de fase y las marca **(fase)**.
1. Vaya al área de **Organización** en el panel de navegación izquierdo.

   Aparece el botón **&quot;Herramienta My Fusion (Stage)&quot;**.
1. Haga clic en el botón **&quot;Herramienta My Fusion (Stage)&quot;**.
La interfaz de usuario se carga en el panel principal y muestra el usuario, la organización y el equipo activos.
1. **Cambiar la organización o el equipo activo** en Fusion.

   El panel se actualiza, lo que muestra el contexto activo (`contextchange`).

>[!TIP]
>
>Si no aparece el botón, vuelva a cargarlo una vez, ya que la detección se almacena en caché por sesión. A continuación, vea [Solución de problemas de extensiones personalizadas](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-08-troubleshooting.md).


## Iteración durante la demostración

Realice un cambio y, a continuación, vuelva a compilar y a implementar.  Los usuarios verán la extensión actualizada la próxima vez que la abran.

```sh
aio app build && aio app deploy
```

## Vaya a Producción después de la demostración

El escenario es suficiente para la demostración. Para realizar el lanzamiento en toda la organización, cambie al espacio de trabajo de producción e implemente y envíe la solicitud de aprobación. La solicitud debe enviarse con una función de administrador del sistema. Para ver el proceso completo, consulte [Versión para producción](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-07-publish.md#release-on-production).

## Seguimiento de demostración (opcional)

Durante la demostración en directo, puede que desee añadir los siguientes puntos:

* **&quot;Empecé desde la plantilla genérica de Experience Cloud Shell.&quot;** Se andamia todo el shell de SPA, así que solo redireccioné el punto de extensión y edité dos archivos.
* **&quot;Fusion es el host, mi aplicación es el invitado.&quot;** Se ejecutan en marcos independientes y hablan sobre la SDK de extensibilidad de la interfaz de usuario de Adobe, sin redes personalizadas.
* **&quot;Registro frente a vista.&quot;** El marco oculto *registra* lo que ofrezco (`dashboard.getWidget`) y el marco visible *adjunta* y lee el contexto.
* **&quot;La prueba de fase es un cambio por usuario.&quot;** Fusion muestra solo las extensiones publicadas de forma predeterminada. He cambiado las extensiones de fase en mi perfil de Fusion para cargar mi compilación de fase, sin una versión de producción.
* **&quot;Contexto en vivo.&quot;** Al cambiar de organización o de equipo, el contexto se vuelve a enviar y el invitado se vuelve a procesar.
