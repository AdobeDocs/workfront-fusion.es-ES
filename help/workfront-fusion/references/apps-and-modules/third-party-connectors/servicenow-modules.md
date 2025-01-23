---
title: Módulos de ServiceNow
description: En un escenario de  [!DNL Adobe Workfront Fusion] , puede automatizar los flujos de trabajo que utilizan [!DNL ServiceNow], así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: 7b236869-bd83-4db5-a363-d6570f6e4aff
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '1354'
ht-degree: 79%

---

# Módulos de [!DNL ServiceNow]

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!DNL ServiceNow], así como conectarlo a varias aplicaciones y servicios de terceros.

Para obtener instrucciones sobre cómo crear un escenario, vea los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

## Requisitos de acceso

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] plan*</td>
  <td> <p>[!UICONTROL Pro] o superior</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licencia*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licencia**</td> 
   <td>
   <p>Requisito de licencia actual: no se requiere ninguna licencia de [!DNL Workfront Fusion].</p>
   <p>O</p>
   <p>Requisito de licencia heredado: [!UICONTROL [!DNL Workfront Fusion] para automatización e integración de trabajo </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Requisito de producto actual: si tiene el plan [!UICONTROL Select] o [!UICONTROL Prime] [!DNL Adobe Workfront], su organización debe adquirir [!DNL Adobe Workfront Fusion] así como [!DNL Adobe Workfront] para utilizar la funcionalidad descrita en este artículo. [!DNL Workfront Fusion] está incluido en el plan [!UICONTROL Ultimate] [!DNL Workfront].</p>
   <p>O</p>
   <p>Requisito de productos heredados: su organización debe comprar [!DNL Adobe Workfront Fusion] y [!DNL Adobe Workfront] para utilizar la funcionalidad descrita en este artículo.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Para saber qué plan, tipo de licencia o acceso tiene, póngase en contacto con el administrador de [!DNL Workfront].

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## Requisitos previos

Para usar módulos [!DNL ServiceNow], debe tener una cuenta de [!DNL ServiceNow].

## Información de API de ServiceNow

El conector ServiceNow utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL básica</td> 
   <td>https://{{connection.instance}}/api</td> 
  </tr>
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.5.13</td> 
  </tr>
 </tbody> 
 </table>

## Conectar [!DNL ServiceNow] a [!DNL Workfront Fusion]

Para crear una conexión para los módulos de [!DNL ServiceNow]:

1. Haga clic en **[!UICONTROL Add]** junto al cuadro [!UICONTROL Connection] cuando empiece a configurar el primer módulo de [!DNL ServiceNow].
1. Introduzca lo siguiente:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td>Escriba un nombre para la nueva conexión de [!DNL ServiceNow]</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Username]</p> </td> 
      <td>Escriba su nombre de usuario de [!DNL ServiceNow]</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Password]</p> </td> 
      <td>Introduzca su contraseña de ServiceNow.</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Instance]</p> </td> 
      <td> <p>Escriba la dirección de su cuenta de [!DNL ServiceNow] sin <code>https://</code> (normalmente, <code>&lt;company>.service-now.com</code>).</p> </td> 
     </tr> 
    </tbody> 
   </table>

   <!--Markdown placeholder-->

## Módulos de [!UICONTROL ServiceNow] y sus campos

Al configurar módulos de [!DNL ServiceNow], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL ServiceNow] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

>[!NOTE]
>
>Si se selecciona un registro personalizado en un campo &quot;[!UICONTROL Record type]&quot;, puede llevar algún tiempo cargar los campos personalizados.
>
>Si no hay registros personalizados, la lista desplegable estará vacía.

* [[!UICONTROL Watch records]](#watch-records)
* [[!UICONTROL Custom API Call]](#custom-api-call)
* [[!UICONTROL Read a record]](#read-a-record)
* [[!UICONTROL Deactivate a User]](#deactivate-a-user)
* [[!UICONTROL Download an attachment]](#download-an-attachment)
* [[!UICONTROL Upload an attachment]](#upload-an-attachment)
* [[!UICONTROL Create a record]](#create-a-record)
* [[!UICONTROL Update a record]](#update-a-record)
* [[!UICONTROL Delete a record]](#delete-a-record)
* [[!UICONTROL Search for records]](#search-for-records)

### [!UICONTROL Watch records]

Este módulo activador activa un escenario cuando se crea o actualiza un registro.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de ServiceNow a [!DNL Workfront Fusion], vea <a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">Conectar [!DNL ServiceNow] a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Table type]</td> 
   <td>Seleccione si la tabla que desea ver es una tabla personalizada o una tabla estándar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>Seleccione el tipo de registro que desea ver.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Display]</td> 
   <td>Seleccione el tipo de valores que desea mostrar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Seleccione los campos que desea que emita el módulo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td>Seleccione si desea ver registros nuevos o actualizados.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Custom API Call]

Este módulo de acción le permite realizar una llamada autenticada personalizada a la API [!DNL ServiceNow]. De este modo, puede crear una automatización del flujo de datos imposibles de realizar por los otros [!DNL ServiceNow] módulos.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de ServiceNow a [!DNL Workfront Fusion], vea <a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">Conectar [!DNL ServiceNow] a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Relative URL]</td> 
   <td> <p>Escriba la dirección del servidor web con el que desea que interactúe el módulo.</p> <p>Puede escribir una dirección URL relativa, lo que significa que no tiene que incluir el protocolo (como <code>http://</code>) al principio. Esto sugiere al servidor web que la interacción se está produciendo en el servidor.</p> <p>Por ejemplo: <code>[!DNL /api/conversations].create</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   td&gt; <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Añada la consulta para la llamada de API en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Read a record]

Este módulo de acción lee un registro de [!DNL ServiceNow] mediante el identificador del sistema.

El módulo devuelve cualquier campo estándar asociado con el registro, junto con los campos y valores personalizados a los que accede la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de ServiceNow a [!DNL Workfront Fusion], vea <a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">Conectar [!DNL ServiceNow] a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record System ID]</td> 
   <td>Escriba o asigne el identificador único [!DNL ServiceNow] del registro que desea que lea el módulo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Table type]</td> 
   <td>Seleccione si el registro que desea leer está en una tabla personalizada o en una tabla estándar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td>Seleccione el tipo de registro de [!DNL ServiceNow] que desea que lea el módulo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Display]</td> 
   <td>Seleccione el tipo de valores que desea mostrar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Seleccione los campos que desea que emita el módulo.</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Deactivate a User]

Este módulo de acción desactiva un usuario en [!DNL ServiceNow] mediante el identificador del sistema.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de ServiceNow a [!DNL Workfront Fusion], vea <a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">Conectar [!DNL ServiceNow] a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL User System ID]</td> 
   <td> Escriba o asigne el identificador único de [!DNL ServiceNow] del usuario que desea que el módulo desactive.</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Download an attachment]

Este módulo de acción descarga un archivo adjunto en un registro de [!DNL ServiceNow].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de ServiceNow a [!DNL Workfront Fusion], vea <a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">Conectar [!DNL ServiceNow] a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Attachment System ID]</td> 
   <td> Escriba o asigne el identificador único de [!DNL ServiceNow] del archivo adjunto que desea que descargue el módulo.</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Upload an attachment]

Este módulo de acción carga un archivo adjunto en un registro de [!DNL ServiceNow].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de ServiceNow a [!DNL Workfront Fusion], vea <a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">Conectar [!DNL ServiceNow] a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Table name]</td> 
   <td>Introduzca o asigne el nombre de la tabla en la que desea cargar el archivo adjunto.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL System ID]</td> 
   <td>Escriba o asigne el identificador único de [!DNL ServiceNow] del sistema donde desea cargar el archivo adjunto.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File name]</td> 
   <td>Escriba o asigne un nombre para el archivo adjunto</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File content]</td> 
   <td>Escriba o asigne el archivo que desea cargar a [!DNL ServiceNow].</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Create a record]

Este módulo de acción crea un nuevo registro de [!DNL ServiceNow].

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de ServiceNow a [!DNL Workfront Fusion], vea <a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">Conectar [!DNL ServiceNow] a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Table type]</td> 
   <td>Seleccione si desea crear un registro en una tabla personalizada o en una tabla estándar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td>Seleccione el tipo de registro de [!DNL ServiceNow] que desea que cree el módulo. A continuación, puede rellenar los campos disponibles para este tipo de registro.</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Update a record]

Este módulo de acción crea un nuevo registro de [!DNL ServiceNow].

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de ServiceNow a [!DNL Workfront Fusion], vea <a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">Conectar [!DNL ServiceNow] a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record System ID]</td> 
   <td>Escriba o asigne el identificador único de [!DNL ServiceNow] del registro que desea que actualice el módulo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Table type]</td> 
   <td>Seleccione si el registro que desea actualizar se encuentra en una tabla personalizada o estándar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td>Seleccione el tipo de registro de [!DNL ServiceNow] que desea que actualice el módulo. A continuación, puede rellenar los campos disponibles para este tipo de registro.</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Delete a record]

Este módulo de acción elimina un incidente o un usuario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de ServiceNow a [!DNL Workfront Fusion], vea <a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">Conectar [!DNL ServiceNow] a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td>Seleccione si desea eliminar un incidente o un usuario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL System ID]</td> 
   <td>Escriba o asigne el identificador único de [!DNL ServiceNow] del registro que desea que elimine el módulo.</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Search for records]

Este módulo busca registros utilizando los criterios seleccionados.

El módulo devuelve cualquier campo estándar asociado con el registro, junto con los campos y valores personalizados a los que accede la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de ServiceNow a [!DNL Workfront Fusion], vea <a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">Conectar [!DNL ServiceNow] a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Table type]</td> 
   <td>Seleccione si la tabla que desea buscar es una tabla personalizada o una tabla estándar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>Seleccione el tipo de registro que desea buscar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Result set]</td> 
   <td>Seleccione si desea que el módulo devuelva todos los registros que coincidan con los criterios o solo el primer registro que coincida. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximal count of records]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search type]</td> 
   <td> <p>Seleccione el tipo de búsqueda que desea que ejecute el módulo</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Advanced query]</strong> </p> 
      <ul> 
       <li> <p>[!UICONTROL Search Query]</p> <p>Introduzca la consulta de búsqueda personalizada. Para obtener información sobre consultas de búsqueda personalizada de [!DNL ServiceNow], consulte la <a href="https://docs.servicenow.com/bundle/orlando-platform-user-interface/page/use/common-ui-elements/reference/r_OpAvailableFiltersQueries.html">documentación de consultas de ServiceNow</a>.</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL Simple]</strong> </p> 
      <ul> 
       <li> <p>[!UICONTROL Search Criteria]</p> <p>Introduzca los criterios según los cuales desea que busque el módulo. <!--For more information on setting up search filters, see <a href="." class="MCXref xref">Add a filter to a scenario in Adobe Workfront Fusion</a>.</p>--> </li> 
       <li> <p>[!UICONTROL Sort by]</p> <p>Indique por qué campo desea que el módulo ordene los resultados y si deben ordenarse de forma ascendente o descendente.</p> </li> 
      </ul> </li> 
    </ul> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Display]</td> 
   <td>Seleccione el tipo de valores que desea mostrar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Seleccione los campos que desea que emita el módulo.</td> 
  </tr> 
 </tbody> 
</table>
