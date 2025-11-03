---
title: Módulos de Allocadia
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan Allocadia, así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: 9a6fccd6-6eee-42dc-a678-c1f34280d139
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '1463'
ht-degree: 77%

---

# Módulos de [!DNL Allocadia]

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!DNL Allocadia], así como conectarlo a varias aplicaciones y servicios de terceros.

Para obtener instrucciones sobre cómo crear un escenario, vea los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront</td> 
   <td> <p>Cualquier paquete de flujo de trabajo de Adobe Workfront y cualquier paquete de integración y automatización de Adobe Workfront</p><p>Workfront Ultimate</p><p>Paquetes Workfront Prime y Select, con una compra adicional de Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencias de Adobe Workfront</td> 
   <td> <p>Estándar</p><p>Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion</td> 
   <td>
   <p>Basado en operaciones: no se requiere licencia de Workfront Fusion</p>
   <p>Basado en conectores (heredado): Workfront Fusion para la automatización e integración del trabajo </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete Select o Prime Workfront que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Para usar módulos de [!DNL Allocadia], debe disponer de una cuenta de [!DNL Allocadia].

## Información de la API [!DNL Allocadia]

El conector Allocadia utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> Versión 1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.7.6</td> 
  </tr>
 </tbody> 
</table>

## Conexión de [!DNL Allocadia] a Workfront Fusion

Puede crear una conexión con su cuenta de [!DNL Allocadia] directamente desde un módulo de [!DNL Allocadia].

1. En cualquier módulo de [!DNL Allocadia], haga clic en **[!UICONTROL Añadir]** junto al campo [!UICONTROL Conexión].
1. Seleccione si desea utilizar el servidor de Norteamérica o el de Europa.
1. Introduzca su nombre de usuario y contraseña.
1. Haga clic en **[!UICONTROL Continuar]** para crear la conexión y volver al módulo.

## Módulos de [!DNL Allocadia] y sus campos

Al configurar módulos de [!DNL Allocadia], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL Allocadia] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Activadores](#triggers)
* [Acciones](#actions)
* [Búsquedas](#searches)

### Activadores

#### [!UICONTROL Ver registro]

Este módulo de activación ejecuta un escenario cuando se añaden, actualizan o ambos objetos de un tipo específico. El módulo devuelve todos los campos estándar asociados con el registro o registros, junto con cualquier campo personalizado y valor al que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> <table style="table-layout:auto"> <col> 
 <col> 
 <tbody> 
  <tr> 
   td role="rowheader"&gt; <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Allocadia a Workfront Fusion, consulte <a href="#connect-allocadia-to-workfront-fusion" class="MCXref xref">[!UICONTROL Connect Allocadia] to Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Filtro</td> 
   <td> <p>Seleccione si desea que el escenario vea solo registros nuevos, [!UICONTROL Updated Records Only] o registros nuevos y actualizados.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de entidad</td> 
   <td>Seleccione el tipo de registro de Allocadia que desea que vea el módulo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Salidas</td> 
   <td> <p>Seleccione los campos que desea incluir en la salida del módulo. Los campos disponibles dependen del tipo de entidad seleccionado.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Límite</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo vea durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Acciones

* [Llamada de API personalizada](#custom-api-call)
* [Leer registro](#read-record)
* [Crear registro](#create-record)
* [Eliminar registro](#delete-record)
* [Actualizar registro](#update-record)

#### [!UICONTROL Llamada de API personalizada]

Este módulo de acción le permite realizar una llamada autenticada personalizada a la API [!DNL Allocadia]. De este modo, puede crear una automatización del flujo de datos que no puedan realizar los otros módulos de [!DNL Allocadia].

La acción se basa en el tipo de entidad (tipo de objeto de Allocadia) especificado.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Allocadia] a Workfront Fusion, consulte <a href="#connect-allocadia-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Allocadia] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Introduzca una ruta relativa a <code>https://api-na.allocadia.com/{version}</code> o <code>https://api-eu.allocadia.com/{version}</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion añade los encabezados de autorización para usted.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Añada la consulta para la llamada de API en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la instrucción condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Leer registro]

Este módulo de acción lee datos de un único registro en [!DNL Allocadia].

Especifique el identificador del registro.

El módulo devuelve cualquier campo estándar asociado con el registro, junto con los campos y valores personalizados a los que accede la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   td role="rowheader"&gt; <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Allocadia] a Workfront Fusion, consulte <a href="#connect-allocadia-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Allocadia] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>Seleccione el tipo de registro de [!DNL Allocadia] que desea que lea el módulo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Seleccione los campos que desea incluir en la salida del módulo. Los campos disponibles dependen del [!UICONTROL Entity Type] seleccionado.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Introduzca o asigne el identificador único de [!DNL Allocadia] del registro que desea que lea el módulo.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Crear registro]

Este módulo de acción crea un registro.

El módulo devuelve el identificador del registro y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   td role="rowheader"&gt; <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Allocadia] a Workfront Fusion, consulte <a href="#connect-allocadia-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Allocadia] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>Seleccione si desea crear un nuevo registro basado en el elemento de línea o en la opción de columna.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Budgets]</td> 
   <td> <p>Seleccione el presupuesto donde desea crear un registro.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Column choices]</td> 
   <td>Seleccione la columna que desea utilizar para crear un nuevo registro.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Label]</td> 
   <td>Introduzca o asigne una etiqueta para el nuevo registro</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Eliminación de registro]

Este módulo de acción elimina un registro en particular.

Especifique el identificador del registro.

El módulo devuelve el identificador del registro y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   td role="rowheader"&gt; <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Allocadia] a Workfront Fusion, consulte <a href="#connect-allocadia-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Allocadia] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td> <p>Seleccione el tipo de entidad que desea eliminar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Line item]</strong> </p> <p>Introduzca el ID de elemento de línea</p> </li> 
     <li> <p> <strong>[!UICONTROL Column Choice]</strong> </p> <p>Seleccione el presupuesto desde el que desea eliminar un registro y, a continuación, introduzca el identificador de columna y el identificador de opción.</p> </li> 
     <li> <p><strong>[!UICONTROL Forecast Tags]</strong> </p> <p>Seleccione el presupuesto desde el que desea eliminar un registro y, a continuación, introduzca el identificador de etiqueta.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Actualizar registro]

Este módulo de acción actualiza un registro, como un elemento de línea, un usuario o una opción de columna,.

Especifique el identificador del registro.

El módulo devuelve el identificador del registro y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Allocadia] a Workfront Fusion, consulte <a href="#connect-allocadia-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Allocadia] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>Seleccione el tipo de registro de [!DNL Allocadia] que desea que actualice el módulo. Aparecerán otros campos en función del tipo de entidad seleccionado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Budgets]</td> 
   <td> <p>Seleccione el presupuesto en el que desea actualizar un registro. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Búsquedas

#### [!UICONTROL Buscar registro]

Este módulo de búsqueda busca registros en un objeto de [!DNL Allocadia] que coincidan con la consulta de búsqueda especificada.

Puede asignar esta información en módulos subsiguientes en el escenario.

Se especifica el tipo de registros deseado.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   td role="rowheader"&gt; <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Allocadia] a Workfront Fusion, consulte <a href="#connect-allocadia-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Allocadia] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>Seleccione el tipo de registro [!DNL Allocadia] que desea que busque el módulo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Budgets]</td> 
   <td> <p>Seleccione el presupuesto que desea buscar. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Result set]</td> 
   <td>Seleccione si desea que el módulo devuelva todos los registros coincidentes o solo el primero.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximal count of records]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search criteria]</td> 
   <td>Seleccione el campo que desea buscar y luego la operación, e introduzca o asigne el valor que desea buscar. Puede añadir reglas [!DNL AND] o [!DNL OR] para filtrar aún más la búsqueda.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Seleccione los campos que desea incluir en la salida del módulo. Los campos disponibles dependen del tipo de entidad seleccionado.</p> </td> 
  </tr> 
 </tbody> 
</table>
