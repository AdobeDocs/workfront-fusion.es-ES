---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: Creación de un proyecto para la extensibilidad de IU
description: Creación de un proyecto para la extensibilidad de IU
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
source-wordcount: 1360
ht-degree: 0%

---

# Creación de un proyecto para la extensibilidad de IU

>[!NOTE]
>
>Este artículo asume cierta familiaridad con las herramientas de desarrollo de software.

Para crear una extensión de IU personalizada, debe crear un proyecto de App Builder para ella.

En esta página se describe cómo generar un proyecto de App Builder genérico con la línea de comandos `aio`. &quot;Genérico&quot; significa que el proyecto **no** se inicia a partir de una plantilla específica de producto. Comenzar con una aplicación genérica mantiene el proyecto sencillo y le permite conectarse con Workfront Fusion.

Puede resultar útil familiarizarse con los siguientes conceptos y terminología relativos a la creación de un proyecto para utilizarlo con la extensibilidad de Adobe Fusion AI.

* **Adobe Developer Console** (<https://developer.adobe.com/console>) es el tablero web donde se encuentra el proyecto.

* **Terminología**:

  | Término | Lo que significa |
  | ------ | --------------- |
  | **Organización** | La organización de Adobe de su empresa. La misma organización que utiliza en Fusion. |
  | **Proyecto** | Un contenedor para una aplicación o extensión. Creará un proyecto para la extensión. |
  | **Workspace** | Una copia de la configuración del proyecto para una fase de trabajo. Cada proyecto tiene un área de trabajo de **Producción**, y normalmente también se usa un área de trabajo de **Ensayo** para realizar pruebas. Piense en espacios de trabajo como &quot;entornos&quot;. |
  | **Credenciales / Servicios** | Permisos que la aplicación puede utilizar. Los valores predeterminados creados para usted son suficientes para comenzar. |

* Existen dos formas de crear un proyecto:

  * **Automático (recomendado):** El comando `aio app init` crea el proyecto y los espacios de trabajo al generar el código. Este artículo describe este proceso.
  * **Manual:** Primero cree usted mismo el proyecto en Developer Console y después apunte `aio` hacia él. Recomendamos hacerlo solo si su organización requiere que los proyectos se creen de forma centralizada.

* Al decidir qué área de trabajo usar, desarrolle e implemente primero en **Stage**. Fusion carga una compilación de fase solo cuando el usuario activa la prueba de fase en su perfil de Fusion (menú de avatar del usuario > Configuración del producto > Perfil de Fusion > Preferencias > Extensiones de fase); de lo contrario, solo aparecen las extensiones de producción publicadas. También puede obtener una vista previa local con `aio app run` y luego promocionarla a **Producción** más adelante.

  Para obtener más información sobre cómo promocionar a producción, consulte [Publicar su extensión](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-07-publish.md).


## Ejecutar `aio app init`

1. Abra un terminal.
1. En el terminal, desplácese a la carpeta donde guarda los proyectos.
1. Ejecutar:

   ```sh
   aio app init my-fusion-extension --standalone-app
   ```

   * `my-fusion-extension` es el nombre de la carpeta/aplicación. Puede seleccionar este nombre, pero puede usar letras minúsculas, guiones y sin espacios.
   * `--standalone-app` indica a la CLI que cree un **esqueleto de aplicación sin formato** en lugar de pedirle que elija una plantilla de producto. Esta es la clave para evitar la plantilla de AEM (o cualquier otra).

1. Cuando se le solicite, **seleccione su organización** (si pertenece a más de una).
1. Cuando se le solicite, seleccione **Crear nuevo proyecto** y acepte el nombre sugerido, o elija un proyecto vacío existente.

   El comando configura los espacios de trabajo **Stage** y **Production** automáticamente.

   El comando también genera archivos en la carpeta `my-fusion-extension` y ejecuta `npm install`.

1. Continuar a [Confirmar creación de proyecto](#confirm-project-creation).

>[!NOTE]
>
> **Si prefiere el menú interactivo:** ejecute `aio app init my-fusion-extension` > (sin `--standalone-app`). Cuando se pregunta a **&quot;¿Qué plantillas desea buscar?&quot;** o muestra una lista de comprobación de plantillas, no seleccione una plantilla de producto como AEM. Elija la opción para crear una **aplicación independiente** / **&quot;Todos los puntos de extensión → ninguno&quot;**.

## Compruebe la creación del proyecto

1. En el terminal, desplácese a la carpeta creada:

   ```sh
   cd my-fusion-extension
   ```

   Debería ver una estructura similar a esta (se omiten algunos archivos):

   ```
   my-fusion-extension/
   |--- app.config.yaml   // main configuration (you will edit this)
   |---  package.json   //dependencies and scripts
   |---  src/    // your source code
   |---  web-src/  or  src/.../web-src/  // front-end files (HTML/JS)
   ```

   Los dos archivos que más le importan son:

   * **`app.config.yaml`**: la configuración central. Más adelante en el proceso agregará aquí una sección `extensions:` que conecta su aplicación a un punto de extensión de Fusion.
   * **`package.json`**: enumera las bibliotecas que usa su aplicación. Aquí agregará la biblioteca de invitados de extensibilidad de la IU de Adobe.

1. Continuar a [Agregar bibliotecas requeridas](#add-required-libraries).

>[!TIP]
>
> No se preocupe si el diseño generado difiere ligeramente entre las versiones de CLI. Este procedimiento le indica exactamente qué archivos crear y qué colocar en ellos, de modo que puede coincidir con la estructura esperada independientemente del punto de inicio.

## Añadir bibliotecas requeridas

La extensión necesita dos bibliotecas:

* **`@adobe/uix-guest`**: permite que la aplicación hable con Fusion (el host).
* **`@adobe/react-spectrum`**: los componentes de la interfaz de usuario de React de Adobe, por lo que la pantalla coincide con la apariencia de Adobe. (Opcional, pero recomendada; puede utilizar HTML sin formato en su lugar).

Para instalar estas bibliotecas:

1. En el terminal, ejecute:

   ```sh
   npm install @adobe/uix-guest @adobe/react-spectrum
   ```

1. (Condicional) Si el proyecto generado no incluye ya React, instálelo también:

   ```sh
   npm install react react-dom react-router-dom
   ```

1. Continuar a [Confirmar las compilaciones del proyecto](#confirm-the-project-builds).

## Confirmar las versiones del proyecto

Antes de cambiar nada, asegúrese de que el proyecto vacío se compila

1. En el terminal, ejecute:

   ```sh
   aio app build
   ```

   Si esto termina sin errores, las herramientas y el proyecto se configuran correctamente. Está listo para conectar el proyecto a Fusion.

   >[!TIP]
   >
   > **Si la compilación falla,** la causa más común es una versión no compatible de Node.js. Ejecute `node --version` y asegúrese de que sea 18 o 20.
   >
   >* Para obtener información sobre la instalación de Node.js, consulte [Configurar las herramientas](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-02-set-up-tools-account.md).
   >* Para obtener información sobre otros posibles errores, consulte [Solución de problemas](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-08-troubleshooting.md).

1. Continúe con [Configurar el proyecto para Fusion](#configure-the-project-for-fusion).

## Configuración del proyecto para Fusion

El siguiente paso para configurar la extensión personalizada es conectar el proyecto genérico a Workfront Fusion.

Lo hará:

1. [Cree una carpeta para la extensión](#create-a-folder-for-your-extension)
1. Informe a App Builder sobre un **punto de extensión** de Fusion (en `app.config.yaml`).
1. Describa los fragmentos de su extensión (en `ext.config.yaml`).
1. **Registre** su widget para que Fusion sepa su título y dónde reside su interfaz de usuario.

Utilizamos `fusion/nav-organization/1` en todo. Para dirigirse a la sección Equipo, cambie `fusion/nav-team/1` en todas partes. Para admitir ambos, repita el patrón para cada uno.

## Cree una carpeta para la extensión

1. Cree los archivos para que el proyecto tenga este aspecto:

   ```
   my-fusion-extension/
   |-- app.config.yaml
   |-- src/
          |-- fusion-nav-organization-1/          // one folder per extension point
             |-- ext.config.yaml
             |-- web-src/
                |-- src/
                   |-- components/
                      |-- App.js
                      |-- ExtensionRegistration.js
                      |-- DashboardWidget.js
                      |-- Constants.js
   ```

   Se recomienda nombrar la carpeta después del punto de extensión (`fusion-nav-organization-1`). El nombre exacto depende de usted, pero debe coincidir con lo que hace referencia en `app.config.yaml`.

1. Continuar a [Declarar el punto de extensión en `app.config.yaml`](#declare-the-extension-point-in-appconfigyaml).

## Declarar el punto de extensión en `app.config.yaml`

1. Abra `app.config.yaml` y actualice su contenido a:

   ```yaml
   extensions:
     fusion/nav-organization/1:
       $include: src/fusion-nav-organization-1/ext.config.yaml
   ```

   Estos contenidos describen lo siguiente:

   * `extensions:`: esta aplicación implementa uno o más puntos de extensión.
   * `fusion/nav-organization/1`: la ranura Fusion en la que se está conectando. **El nombre debe coincidir exactamente con**, incluida la versión `1`.
   * `$include:`: esto apunta a un segundo archivo de configuración (creado en el siguiente paso) que describe el contenido de esta extensión. Si lo mantiene en un archivo independiente, `app.config.yaml` se mantendrá limpio y le permitirá agregar más puntos de extensión más adelante.

   >[!NOTE]
   >
   >Si va a segmentar ambas extensiones, enumere ambas, cada una con su propia carpeta:
   >
   > ```yaml
   > extensions:
   >     fusion/nav-organization/1:
   >         $include: src/fusion-nav-organization-1/ext.config.yaml
   >     fusion/nav-team/1:
   >         $include: src/fusion-nav-team-1/ext.config.yaml
   > ```

   1. Continuar a [Describir la extensión en `ext.config.yaml`](#describe-the-extension-in-extconfigyaml)

## Describir la extensión en `ext.config.yaml`

1. Crear `src/fusion-nav-organization-1/ext.config.yaml` con:

   ```yaml
   operations:
      view:
       - type: web
         impl: index.html
   web: web-src
   hooks:
     pre-app-build: node node_modules/@adobe/uix-guest/scripts/generate-metadata.js
      pre-app-run: node node_modules/@adobe/uix-guest/scripts/generate-metadata.js
   ```

   Estos contenidos describen lo siguiente:

   * **`operations.view`**: declara que su extensión proporciona una **vista** (una interfaz de usuario visible), ofrecida desde `index.html`. Esto es lo que hace que la extensión muestre una pantalla en lugar de ejecutarse solo en segundo plano.
   * **`web: web-src`**: la carpeta que contiene los archivos front-end. App Builder crea todo lo que hay debajo de aquí y lo aloja en la red de distribución de contenido (CDN) de Adobe.
   * **`hooks`**: comandos pequeños que se ejecutan automáticamente en tiempo de compilación/ejecución. El script `generate-metadata.js` se enviará con `@adobe/uix-guest` y producirá un archivo de `app-metadata.json` que su código de registro necesita (consulte el paso 4). No se escribe esta secuencia de comandos; simplemente se hace referencia a ella.

   >[!NOTE]
   >
   > Si también necesita lógica del lado del servidor, también puede agregar `actions` sin servidor (funciones backend pequeñas). Las acciones son opcionales y no son necesarias para procesar una interfaz de usuario, por lo que no se incluyen en esta guía. Si los agrega más adelante, declare una carpeta `actions:` aquí y un `runtimeManifest:` en `app.config.yaml`. El motivo más común para agregar uno es llamar a las API de Workfront/Fusion sin visitar el navegador CORS.
   > Para obtener información sobre cómo llamar a las API, consulte [Llamar a las API de Workfront y Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-10-calling-apis.md).
1. Continuar a [Establecer un Id. de extensión estable](#set-a-stable-extension-id).

## Establecimiento de un ID de extensión estable

La extensión requiere un ID único que compartan ambos marcos.

Para obtener información sobre los marcos en relación con las extensiones personalizadas, consulte [Marcos incluidos en una extensión de interfaz de usuario](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-01-overview.md#frames-included-in-a-ui-extension).

1. Crear `src/fusion-nav-organization-1/web-src/src/components/Constants.js`:

   ```js
   module.exports = {
     extensionId: 'my-fusion-extension'
   };
   ```

   Utilice el mismo valor en cualquier lugar donde el código haga referencia al ID de extensión.
1. Continuar a [Registrar tu widget](#register-your-widget).


## Registre el widget

&quot;Registro&quot; es la forma en que el marco de fondo oculto le dice a Fusion lo que ofrece su extensión. Usted declara un método `dashboard.getWidget()` que devuelve el título del widget y la dirección URL de su interfaz de usuario visible.

1. Crear `src/fusion-nav-organization-1/web-src/src/components/ExtensionRegistration.js`.
La parte importante es la llamada a `register(...)`:

   ```js
   import { register } from "@adobe/uix-guest";
   import metadata from "../../../../app-metadata.json";
   import { extensionId } from "./Constants";
   
   async function init() {
     await register({
       id: extensionId,
       metadata,
       methods: {
         dashboard: {
           getWidget() {
             return {
               id: extensionId,
               title: "My Fusion tool",        // shown on the Fusion nav button
               description: "What this tool does",
               url: "/index.html#/my-widget",  // route to your visible UI
               hideWidgetHeader: false          // false = Fusion shows the title
             };
           }
         }
       }
      });
   }
   
   init().catch(console.error);
   ```

   Puntos clave:

   * **`title`** es la etiqueta que Fusion pone en el botón de navegación. Si `hideWidgetHeader` es `false`, Fusion también muestra el título como un encabezado sobre la interfaz de usuario.
   * **`url`** es la ruta a la interfaz de usuario *visible* dentro de esta misma aplicación. Aquí hay una ruta hash (`#/my-widget`) que administra su enrutador front-end (configurada en la página siguiente). Debe resolverse en el componente que procesa la pantalla.
   * **`metadata`** proviene de `app-metadata.json`, que el vínculo `generate-metadata` crea para usted en el momento de la compilación. Importe como se muestra.
   * El nombre de método `dashboard.getWidget` son las llamadas de Fusion de contrato acordadas para descubrir su widget. Conservar el espacio de nombres `dashboard` y el nombre `getWidget`.

El back-end de la extensión ya está completo. El siguiente paso es crear la interfaz de usuario de la extensión.

Para obtener instrucciones sobre cómo crear la interfaz de usuario, consulte [Crear la interfaz de usuario de la extensión personalizada](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-05-build-ui-procedure.md).
