---
title: Depuración de un escenario
description: Adobe Workfront Fusion Devtool le permite entender y solucionar problemas de escenarios. Devtool añade un panel adicional a las herramientas para desarrolladores de Chrome. Con este panel del depurador, puede comprobar todas las ejecuciones manuales de su escenario, revisar todas las operaciones realizadas y ver los detalles de cada llamada de API realizada. Puede ver qué módulo, operación o respuesta única causó el error y utilizar ese conocimiento para perfeccionar el escenario.
author: Becky
feature: Workfront Fusion
exl-id: 34215370-27e3-4c28-8bd1-a16268900b86
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1483'
ht-degree: 74%

---

# Depuración de un escenario

Adobe Workfront Fusion DevTool le ayuda a comprender y solucionar problemas de escenarios. Con la herramienta de desarrollo, puede comprobar todas las ejecuciones manuales de su escenario, revisar todas las operaciones realizadas y ver los detalles de cada llamada de API realizada. Puede ver qué módulo, operación o respuesta única causó el error y utilizar ese conocimiento para perfeccionar el escenario.

>[!NOTE]
>
>El inicio de sesión en el panel del depurador estará limitado o no estará disponible en escenarios confidenciales, ejecuciones automáticas y operaciones satisfactorias.

Para ver un vídeo introductorio y un tutorial de Fusion Devtool, consulte

* [Herramienta de desarrollo de Fusion](https://video.tv.adobe.com/v/3427031/){target=_blank}
* [Tutorial de Devtool](https://experienceleague.adobe.com/docs/workfront-learn/tutorials-workfront/fusion/troubleshooting-and-error-handling/dev-tool-walkthrough.html?lang=es)

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront</td> 
   <td> <p>Cualquiera</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencia de Adobe Workfront</td> 
   <td> <p>Nuevo: estándar</p><p>O</p><p>Actual: [!UICONTROL Work] o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion**</td> 
   <td>
   <p>Actual: no se requiere licencia de Workfront Fusion.</p>
   <p>O</p>
   <p>Heredado: cualquiera </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Plan de Workfront de [!UICONTROL Select] o [!UICONTROL Prime]: su organización debe adquirir Adobe Workfront Fusion.</li><li>Plan de Workfront de [!UICONTROL Ultimate]: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe comprar Adobe Workfront Fusion.</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">Configuraciones de nivel de acceso*</td> 
   <td> 
     <p>Debe ser administrador de Workfront Fusion para su organización.</p>
     <p>Debe ser administrador de Workfront Fusion para su equipo.</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Acceso a Devtool

Si utiliza Fusion en el Unified Shell de Adobe o ha actualizado a la nueva experiencia de Fusion, puede acceder a Devtool desde el editor de escenarios.

1. Haga clic en el icono **Helper tools** ![Helper tools](assets/debugger-icon.png) cerca de la parte inferior de la pantalla.

O

1. Vaya al editor de escenarios correspondiente al escenario que desea depurar.

   Para localizar el editor de escenarios, consulte [El editor de escenarios](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md).

1. Haga clic con el botón derecho en un área vacía de la página (no en un módulo).
1. Seleccione **abrir Devtool**.

## Uso de Workfront Fusion Devtool

La herramienta Devtool de Workfront Fusion se divide en tres secciones principales. Puede encontrarlas en el panel izquierdo de la ventana de Devtool.

* [Live Stream](#live-stream)
* [Depurador de escenario](#scenario-debugger)
* [Herramientas](#tools)

### Live Stream

Live Stream muestra lo que está sucediendo en segundo plano cuando hace clic en Ejecutar una vez en su escenario.

1. Haga clic en el icono **[!UICONTROL Transmisión en vivo]** ![Icono de transmisión en vivo](assets/live-stream-icon.png) para abrir la sección Transmisión en vivo.
1. Realice una de las siguientes acciones:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <thead> 
     <tr> 
      <th>Acción</th> 
      <th>Instrucciones</th> 
     </tr> 
    </thead> 
    <tbody> 
     <tr> 
      <td role="rowheader">Ver información de solicitud</td> 
      <td> <p>Puede ver la siguiente información para cada módulo de su escenario</p> 
       <ul> 
        <li> <p>Encabezados de solicitud (URL de extremo de API, método HTTP, hora y fecha en que se llamó a la solicitud, encabezados de solicitud y cadena de consulta)</p> </li> 
        <li> <p>Cuerpo de solicitud</p> </li> 
        <li> <p>Encabezados de respuesta</p> </li> 
        <li> <p>Cuerpo de respuesta</p> </li> 
       </ul> <p>Para ver esta información, haga clic en la pestaña correspondiente del panel derecho de Workfront Fusion DevTool.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>Buscar eventos por contenido</p> </td> 
      <td> <p>Introduzca el término de búsqueda en el campo de búsqueda del panel izquierdo de la herramienta Workfront Fusion para mostrar solo las solicitudes que contienen el término de búsqueda.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>Borrar lista de solicitudes </p> </td> 
      <td> <p>Haga clic en el icono de la papelera situado en la esquina superior derecha del panel izquierdo de Devtool para borrar la lista de solicitudes registradas por Devtool de Workfront Fusion. </p> </td> 
     </tr> 
     <!--<tr> 
      <td role="rowheader"> <p>Enable Console Logging</p> </td> 
      <td> <p>Click the computer icon <img src="assets/console-computer-icon.png"> in the top-right corner of the Devtool's left panel.</p> <p>Logging in the console is enabled when the computer icon is green.</p> </td> 
     </tr>-->
     <tr> 
      <td role="rowheader"> <p>Recuperar la solicitud en formato Raw JSON o cURL</p> </td> 
      <td> 
       <ul> 
        <li> <p><strong>Raw JSON</strong> </p> <p>Haga clic en <strong>[!UICONTROL Copy RAW]</strong> en la esquina superior derecha del panel derecho de Devtool.</p> </li> 
        <li> <p><strong>cURL</strong> </p> <p>Haga clic en <strong>[!UICONTROL Copy cURL]</strong> en la esquina superior derecha del panel derecho de Devtool.</p> </li> 
       </ul> </td> 
     </tr> 
    </tbody> 
   </table>

### Depurador de escenario

El depurador de escenario resulta útil para escenarios más complejos. Muestra el historial de ejecuciones de escenarios y le permite buscar módulos por su nombre o ID.

1. Haga clic en el icono **[!UICONTROL Depurador de escenarios]** ![Icono de depurador](assets/scenario-debugger-icon.png) para abrir el Depurador de escenarios.
1. (Opcional) Introduzca el término de búsqueda (nombre o ID de módulo) en el campo de búsqueda.
1. Haga clic en el nombre del módulo.
1. Haga clic en la operación para ver los detalles de la solicitud.

### Herramientas

Workfront Fusion DevTool incluye herramientas que facilitan la configuración de su escenario.

1. Haga clic en el icono **[!UICONTROL Herramientas]** ![Icono de herramientas de consola](assets/console-tools-icon.png) para abrir las herramientas.
1. Seleccione la herramienta que desee utilizar.
1. Configure los campos como se indica a continuación.
1. Haga clic en **[!UICONTROL Ejecutar]**.

Herramientas y sus campos:

* [Enfoque en un módulo](#focus-a-module)
* [Buscar módulos por asignación](#find-modules-by-mapping)
* [Obtener metadatos de la aplicación](#get-app-metadata)
* [Copiar asignación](#copy-mapping)
* [Copiar filtro](#copy-filter)
* [Copiar nombre de módulo](#copy-module-name)
* [Intercambiar conexión](#swap-connection)
* [Intercambiar variable](#swap-variable)
* [Base 64](#base-64)
* [Reasignar origen](#remap-source)

#### [!UICONTROL Enfoque en un módulo]

Abre la configuración del módulo especificado por identificador.

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Module ID]</td>
        <td>Introduzca el ID del módulo para abrir su configuración.</td>
    </tr>
</table>

#### [!UICONTROL Buscar módulos por asignación]

Permite buscar los valores de los módulos para el término especificado. La salida contiene los ID de los módulos que contienen el término que se ha buscado.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Keyword]</td> 
   <td> <p> Introduzca el término que desea buscar. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Use Only Values]</p> </td> 
   <td> <p>Active esta opción para buscar únicamente en los valores de los campos del módulo.</p> <p>Deshabilite esta opción para buscar también en los nombres de los campos del módulo.</p> <p>La búsqueda se realiza mediante los parámetros de nombre y etiqueta.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Obtener metadatos de la aplicación]

Recupera los metadatos de la aplicación por el nombre o ID del módulo de la aplicación. Esto resulta útil, por ejemplo, cuando necesita saber la versión de la aplicación utilizada en su escenario.

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Source Module]</td>
        <td>Seleccione el módulo cuyos metadatos desea recuperar.</td>
    </tr>
</table>

#### [!UICONTROL Copiar asignación]

Copia los valores del módulo de origen en el módulo de destino.

>[!CAUTION]
>
>Asegúrese de establecer los módulos de origen y de destino correctos. Si selecciona un tipo de módulo diferente, se eliminarán los valores del módulo de destino.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Module]</td> 
   <td> <p> Seleccione el módulo o introduzca el ID del módulo cuyos valores de campo desea copiar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Target Module]</p> </td> 
   <td> <p>Seleccione el módulo o introduzca el ID del módulo en el que desea insertar los valores del módulo de origen.</p> <p>Importante: los valores del módulo de destino se sobrescribirán.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Copiar filtro]

Copia la configuración del filtro del módulo de origen al módulo de destino.

>[!NOTE]
>
>La acción de copiar se realiza en el filtro colocado en el lado izquierdo del módulo seleccionado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Module]</td> 
   <td> <p> Seleccione el módulo o introduzca el ID del módulo del que desea copiar los valores de filtro.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Target Module]</p> </td> 
   <td> <p>Seleccione el módulo o introduzca el ID del módulo en el que desea insertar los valores de filtro desde el módulo de origen.</p> <p>Importante: los valores del módulo de destino se sobrescribirán.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Preserve Fallback Route setting]</p> </td> 
   <td> <p>El filtro de origen se establece como ruta de reserva. Active esta opción para establecer también que el filtro de destino se establezca como ruta de reserva.</p> </td> 
  </tr> 
 </tbody> 
</table>


#### [!UICONTROL Copiar nombre de módulo]

Copia el nombre del módulo seleccionado en el portapapeles.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Module] </td> 
   <td> <p>Seleccione el módulo del que desea copiar el nombre. </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Intercambiar conexión]

Duplica una conexión desde el módulo de origen a cada uno de los módulos en el escenario de la misma aplicación.

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Source Module]</td>
        <td>Seleccione el módulo o introduzca el ID del módulo del que desea duplicar la conexión.</td>
    </tr>
</table>

#### [!UICONTROL Intercambiar variable]

Busca las variables especificadas en el escenario y las reemplaza por una variable nueva.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Variable to Find]</td> 
   <td> <p> Busque la píldora de variables que desee reemplazar desde el módulo de variables en su escenario y cópiela en este campo ([!UICONTROL Variable to Find]). En el campo, aparece entre corchetes dobles. Ejemplo: <code>&#123;&#123;5.value&#125;&#125;</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Replace With]</p> </td> 
   <td> <p>Busque la píldora de variables con la que desea reemplazar la variable desde el módulo de variables en su escenario y cópiela en este campo ([!UICONTROL Variable to Find]). En el campo, aparece entre corchetes dobles. Ejemplo: <code>&#123;&#123;5.value&#125;&#125;</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Module]</p> </td> 
   <td> <p>Seleccione el módulo de variables en el que desea reemplazar la variable. Si no se selecciona ningún módulo, la variable se reemplazará en todo el escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Base 64]

Le permite codificar los datos introducidos en Base64 o descodificar Base64. Algunas solicitudes se codifican en Base64. Esta herramienta puede resultar útil cuando desea buscar datos concretos en la solicitud codificada.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Operation] </td> 
   <td> <p>Seleccione si desea codificar los datos del campo [!UICONTROL Raw Data] a Base64 o descodificar Base64 a Raw Data.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Raw Data]</p> </td> 
   <td> <p> Introduzca los datos que desea codificar a Base64 o Base64 si desea descodificarlos a datos sin procesar, según la opción seleccionada en el campo [!UICONTROL Operation] anterior.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Reasignar origen]

Le permite cambiar el origen de la asignación de un módulo a otro.

Primero debe añadir el módulo para utilizarlo como módulo de origen para la ruta en un escenario.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Module] </td> 
   <td> <p> Seleccione el módulo que desea reemplazar como origen de asignación para otros módulos de su escenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Target Module]</p> </td> 
   <td> <p>Seleccione el módulo que desee utilizar como nuevo origen de asignación.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Module to Edit]</p> </td> 
   <td> <p>Seleccione el módulo para el que desea cambiar la asignación si no desea cambiar la asignación en todo el escenario. </p> </td> 
  </tr> 
 </tbody> 
</table>
