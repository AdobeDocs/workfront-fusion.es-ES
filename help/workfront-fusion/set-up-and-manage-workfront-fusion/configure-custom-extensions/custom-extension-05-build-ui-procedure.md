---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: Creación de la IU de extensión personalizada
description: Creación de la IU de extensión personalizada
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: a9dd86f7dc4070ad98c7c4a526a6a38939097940
workflow-type: tm+mt
source-wordcount: 440
ht-degree: 0%

---


# Creación de la IU de extensión personalizada

>[!NOTE]
>
>Este artículo asume cierta familiaridad con las herramientas de desarrollo de software.

Este procedimiento describe cómo crear la pantalla que los usuarios ven realmente y cómo completar la **conexión (&quot;protocolo de enlace&quot;)** con Fusion.

Durante este proceso, es importante recordar que la extensión se ejecuta en dos fotogramas: el fotograma **registro** oculto y el fotograma **IU** visible.

Para obtener información sobre los marcos en relación con las extensiones personalizadas, consulte [Marcos incluidos en una extensión de interfaz de usuario](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-01-overview.md#frames-included-in-a-ui-extension).

Para obtener instrucciones sobre cómo crear el marco de registro, consulte [Crear un proyecto para la extensibilidad de la interfaz de usuario](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-03-04-create-project-configure-fusion.md).

## Ruta entre los dos fotogramas

Ambos fotogramas cargan el mismo `index.html`; un pequeño enrutador front-end decide qué componente se mostrará en función de la dirección URL.

1. Configurar las rutas en `web-src/src/components/App.js`. La parte esencial es:

   ```jsx
   import { HashRouter as Router, Routes, Route } from "react-router-dom";
   import ExtensionRegistration from "./ExtensionRegistration";
   import DashboardWidget from "./DashboardWidget";
   
   export default function App() {
     return (
       <Router>
         <Routes>
           {/* Background frame: registers the extension with Fusion */}
           <Route index element={<ExtensionRegistration />} />
           <Route path="index.html" element={<ExtensionRegistration />} />
   
           {/* Visible frame: the URL you returned from getWidget() */}
           <Route path="my-widget" element={<DashboardWidget />} />
         </Routes>
       </Router>
     );
   }
   ```

   Estas rutas se asignan a la configuración anterior de la siguiente manera:

   * La ruta predeterminada (`index`) procesa **`ExtensionRegistration`**, el marco oculto que llama a `register(...)`.
   * La ruta `my-widget` procesa **`DashboardWidget`**, su interfaz de usuario visible. Esto coincide con el `url: "/index.html#/my-widget"` que devolvió de `getWidget()` en [la página anterior](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-03-04-create-project-configure-fusion.md).

   >[!NOTE]
   >
   > **Las rutas y la dirección URL `getWidget` deben estar de acuerdo.** Si cambia el nombre de la ruta, cambie el `url` a o Fusion cargará una página en blanco.

1. Continuar a [Completar el protocolo de enlace con `attach`](#complete-the-handshake-with-attach).

## Completar el protocolo de enlace con `attach`

Esta es la línea más importante de la IU visible. Cuando Fusion abre el marco de la interfaz de usuario, espera a que ese marco &quot;se registre&quot;. Su código se registra llamando a `attach({ id })`.

**Si se omite, Fusion agotará el tiempo de espera** con un error como *&quot;esperando el mensaje inicial del iframe de destino.&quot;*

1. Agregar lo siguiente a `web-src/src/components/DashboardWidget.js`:

   ```jsx
   import { useEffect, useState } from "react";
   import { attach } from "@adobe/uix-guest";
   import { extensionId } from "./Constants";
   
   export default function DashboardWidget() {
     const [connection, setConnection] = useState(null);
   
     useEffect(() => {
       // Tell Fusion this UI frame is ready. Required.
       attach({ id: extensionId })
         .then(setConnection)
         .catch((e) => console.error("attach failed", e));
     }, []);
   
     if (!connection) {
       return <p>Connecting to Fusion...</p>;
     }
   
     return <h2>Hello from my Fusion extension!</h2>;
   }
   ```

   Este código hace lo siguiente:

   * `attach({ id })` devuelve un **objeto de conexión** una vez que Fusion responde. Se recomienda guardarlo, ya que lo utilizará en el siguiente paso para leer el contexto que Fusion envía.
   * Hasta que se resuelva la conexión, un breve &quot;Conectando...&quot; se muestra el mensaje.
   * Utiliza **el mismo`extensionId`** que configuró en `Constants.js`.

   En este punto tiene una extensión en funcionamiento: registra, adjunta y muestra un mensaje. Después de esto, todo gira en torno al uso de los datos que Fusion le ofrece.

1. Continúe en [Leer el contexto de los recursos compartidos de Fusion](#read-the-context-fusion-shares).

## Leer el contexto que comparte Fusion

Una vez que se adjunta, la conexión expone un **contexto compartido** con información sobre el usuario, la organización y el equipo actuales. Puede leer valores individuales con `connection.sharedContext.get("<key>")`:

```jsx
const orgId = connection.sharedContext.get("imsOrgId");
const organization = connection.sharedContext.get("organization"); // full Fusion org
const user = connection.sharedContext.get("user");                 // full Fusion user
```

Este ejemplo muestra un ejemplo completo y reactivo que también se actualiza cuando el usuario cambia de organización o equipo:

```jsx
import { useEffect, useState } from "react";
import { attach } from "@adobe/uix-guest";
import { extensionId } from "./Constants";

const KEYS = ["imsOrgId", "imsUserId", "organization", "team", "user"];

function readContext(source) {
  // sharedContext behaves like a Map (.get); the change event gives a plain object.
  const get =
    typeof source.get === "function" ? (k) => source.get(k) : (k) => source[k];
  return Object.fromEntries(KEYS.map((k) => [k, get(k)]));
}

export default function DashboardWidget() {
  const [context, setContext] = useState(null);

  useEffect(() => {
    let cleanup = () => {};
    attach({ id: extensionId })
      .then((connection) => {
        // 1) initial values
        setContext(readContext(connection.sharedContext));

        // 2) react to org/team/user changes pushed by Fusion
        const onChange = (event) =>
          setContext(readContext(event?.detail?.context ?? connection.sharedContext));
        connection.addEventListener("contextchange", onChange);
        cleanup = () => connection.removeEventListener?.("contextchange", onChange);
      })
      .catch((e) => console.error("attach failed", e));
    return () => cleanup();
  }, []);

  if (!context) return <p>Connecting to Fusion...</p>;

  return (
    <div>
      <h2>{context.organization?.name ?? "No organization"}</h2>
      <p>Signed in as {context.user?.name} ({context.user?.email})</p>
      <p>IMS org: {context.imsOrgId}</p>
    </div>
  );
}
```

Recuerde lo siguiente:

* **Leer los valores iniciales** de `connection.sharedContext.get(key)` justo después de `attach`.
* **Suscribirse a`contextchange`** para permanecer sincronizado. Fusion activa este evento cada vez que cambia la organización, el equipo o el usuario activos. Los nuevos valores llegan el `event.detail.context`.

Para obtener la lista completa de claves y lo que contiene cada una, consulte [La referencia de contexto de Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md).

Para continuar con el proceso de configuración de tu extensión personalizada, ve a [The Fusion context reference](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md).
