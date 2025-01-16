---
title: Módulos Split.io
description: En un escenario de  [!DNL Adobe Workfront Fusion] , puede automatizar los flujos de trabajo que usan [!DNL Split.io], así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: 7d738a96-5424-4c30-831f-82e1d4c6f9d2
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1493'
ht-degree: 87%

---

# Módulos de [!DNL Split.io]

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!DNL Split.io], así como conectarlo a varias aplicaciones y servicios de terceros.

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

Para usar módulos [!DNL Split.io], debe tener una cuenta de [!DNL Split.io].

## Información de la API Split.io

El conector Split.io utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL básica</td> 
   <td> https://api.split.io/internal/api</td>
   </tr> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> Versión 2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.34.1</td> 
  </tr>
 </tbody> 
 </table>

## Conectar [!DNL Split.io] a [!DNL Workfront Fusion] {#connect-split-io-to-workfront-fusion}

Puede crear una conexión con su cuenta de [!DNL Split.io] directamente desde un módulo de [!DNL Split.io].

1. En cualquier módulo de [!DNL Split.io], haga clic en **[!UICONTROL Add]** junto al campo [!UICONTROL Connection].
1. Introduzca un nombre para la conexión. 
1. Escriba su clave de API de [!DNL Split.io].

   Para obtener más información sobre las claves de API de [!DNL Split.io], consulte [claves de API](https://help.split.io/hc/en-us/articles/360019916211-API-keys) en la documentación de [!DNL Split.io].

1. Haga clic en **[!UICONTROL Continue]** para crear la conexión y volver al módulo.

## Módulos de [!DNL Split.io] y sus campos

Al configurar módulos de [!DNL split.io], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL split.io] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Acciones](#actions)
* [Búsquedas](#searches)

### Acciones

* [[!UICONTROL Custom API Call]](#custom-api-call)
* [[!UICONTROL Get Split]](#get-split)
* [[!UICONTROL Get Split Definition in Environment]](#get-split-definition-in-environment)
* [[!UICONTROL Create Split]](#create-split)
* [[!UICONTROL Delete Split]](#delete-split)
* [[!UICONTROL Create Split Definition in Environment]](#create-split-definition-in-environment)
* [[!UICONTROL Remove Split Definition from Environment]](#remove-split-definition-from-environment)
* [[!UICONTROL Partial Update Split Definition in Environment]](#partial-update-split-definition-in-environment)
* [[!UICONTROL Associate Tags]](#associate-tags)

#### [!UICONTROL Custom API Call]

Este módulo de acción le permite realizar una llamada autenticada personalizada a la API [!DNL split.io]. De este modo, puede crear una automatización del flujo de datos que no puedan realizar los otros [!DNL split.io] módulos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Split.io] a [!DNL Workfront Fusion], consulte <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Split.io] a [!UICONTROL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Escriba una ruta relativa a <code>https://api.split.io/internal/api/v2/</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Métodos de petición HTTP en [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
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
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Introduzca o asigne el número máximo de registros con los que desea que trabaje el módulo durante cada ciclo de ejecución de escenario.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Split]

Este módulo de acción recupera la división.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Split.io] a [!DNL Workfront Fusion], consulte <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Split.io] a [!UICONTROL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Seleccione o asigne el espacio de trabajo que contiene la división que desea recuperar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>Introduzca o asigne el nombre de la división que desea recuperar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Split Definition in Environment]

Este módulo de acción recupera una definición de división específica del entorno designado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Split.io] a [!DNL Workfront Fusion], consulte <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Split.io] a [!UICONTROL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Seleccione o asigne el espacio de trabajo que contiene la definición de división que desea recuperar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Environment Name or ID]</td> 
   <td>Seleccione o asigne el entorno que contiene la definición de división que desea recuperar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>Introduzca o asigne el nombre de la división para la que desea recuperar la definición de división.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create Split]

Este módulo de acción crea una nueva división en su organización, dado un tipo de tráfico.

>[!NOTE]
>
>La API no configura la división en ningún entorno.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Split.io] a [!DNL Workfront Fusion], consulte <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Split.io] a [!UICONTROL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Seleccione o asigne el espacio de trabajo en el que desea crear la división.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Traffic Type ID or Name]</td> 
   <td>Seleccione o asigne el tipo de tráfico que desea utilizar para crear la división.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>Introduzca o asigne un nombre para la división que desea crear.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Description]</td> 
   <td>Escriba o asigne una descripción de [!UICONTROL split] para la división que desee crear.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete Split]

Este módulo de acción elimina una división de su organización, lo que desconfigura automáticamente la definición de división de todos los entornos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Split.io] a [!DNL Workfront Fusion], consulte <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Split.io] a [!UICONTROL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Seleccione o asigne el espacio de trabajo en el que desea eliminar la división.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>Introduzca o asigne el nombre de la división que desea eliminar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create Split Definition in Environment]

Este módulo de acción configura una definición de división para un entorno específico.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Split.io] a [!DNL Workfront Fusion], consulte <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Split.io] a [!UICONTROL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Seleccione o asigne el espacio de trabajo en el que desea crear una definición de división.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Environment Name or ID]</td> 
   <td>Seleccione o asigne el entorno en el que desea crear una definición de división.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>Introduzca o asigne el nombre de la división para la que desea crear una definición.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comments]</td> 
   <td>Introduzca o asigne cualquier comentario que desee añadir a la definición de división.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Rules]</td> 
   <td> <p>Para cada regla de segmentación que desee agregar a la definición, haga clic en <b>[!UICONTROL Add item]</b> y después introduzca o asigne la regla.</p> <p>Para obtener más información sobre las reglas de segmentación, consulte <a href="https://docs.split.io/reference#create-split-definition-in-environment">Crear una definición de división en un entorno</a> en la documentación de [!DNL Split.io].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Default rule]</td> 
   <td> <p>Introduzca o asigne la regla que desea que la división utilice para el tráfico que no cumple las especificaciones de las demás reglas.</p> <p>Para obtener más información sobre las reglas de segmentación, consulte <a href="https://docs.split.io/reference#create-split-definition-in-environment">Crear una definición de división en un entorno</a> en la documentación de [!DNL Split.io].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Default treatment]</td> 
   <td> <p>Introduzca o asigne el tratamiento que desea que utilice la división si esta se anula o si el cliente no se incluye en la asignación de tráfico.</p> <p>Para obtener más información sobre los tratamientos, consulte <a href="https://docs.split.io/reference#create-split-definition-in-environment">Crear una definición de división en un entorno</a> en la documentación de [!DNL Split.io].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Treatments]</td> 
   <td> <p>Para cada tratamiento que desee agregar a la definición, haga clic en <b>[!UICONTROL Add item]</b> y, a continuación, especifique o asigne el tratamiento.</p> <p>Para obtener más información sobre los tratamientos, consulte <a href="https://docs.split.io/reference#create-split-definition-in-environment">Crear una definición de división en un entorno</a> en la documentación de [!DNL Split.io].</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Remove Split Definition from Environment]

Este módulo de acción desconfigura una definición de división para un entorno específico.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Split.io] a [!DNL Workfront Fusion], consulte <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Split.io] a [!UICONTROL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Seleccione o asigne el espacio de trabajo en el que desea quitar una definición de división.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Environment Name or ID]</td> 
   <td>Seleccione o asigne el entorno en el que desea quitar una definición de división.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>Introduzca o asigne el nombre de la división para la que desea eliminar una definición.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comments]</td> 
   <td>Introduzca o asigne cualquier comentario que desee añadir a la definición de división.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Partial Update Split Definition in Environment]

Este módulo de acción actualiza una definición dividida para un entorno específico.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Split.io] a [!DNL Workfront Fusion], consulte <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Split.io] a [!UICONTROL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Seleccione o asigne el espacio de trabajo en el que desea actualizar una definición de división.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Environment Name or ID]</td> 
   <td>Seleccione o asigne el entorno en el que desea actualizar una definición de división.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>Introduzca o asigne el nombre de la división para la que desea actualizar una definición.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Update content]</td> 
   <td> <p>Para cada atributo de la división que desee actualizar, haga clic en <b>[!UICONTROL Add item]</b> e introduzca o asigne los cambios deseados.</p> <p>Para obtener más información, consulte <a href="https://docs.split.io/reference#partial-update-split-definition-in-environment">Definición de división de actualización parcial en el entorno</a> en la documentación de [!DNL Split.io].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comments]</td> 
   <td>Introduzca o asigne cualquier comentario que desee añadir a la definición de división.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Associate Tags]

Este módulo de acción añade etiquetas al objeto especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Split.io] a [!DNL Workfront Fusion], consulte <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Split.io] a [!UICONTROL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Seleccione o asigne el espacio de trabajo donde desea añadir una etiqueta.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object Name]</td> 
   <td>Introduzca o asigne el nombre del objeto al que desea añadir etiquetas.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object Type]</td> 
   <td> <p>Introduzca o asigne el tipo de objeto al que desea añadir etiquetas.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tags]</td> 
   <td> <p>Para cada etiqueta que desee agregar, haga clic en <b>[!UICONTROL Add item]</b> y escriba o asigne la etiqueta.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Búsquedas

* [[!UICONTROL Get Workspaces]](#get-workspaces)
* [[!UICONTROL Get Environments]](#get-environments)
* [[!UICONTROL Get Splits]](#get-splits)
* [[!UICONTROL List Split Definitions in an Environment]](#list-split-definitions-in-an-environment)
* [[!UICONTROL Get Traffic Types]](#get-traffic-types)

#### [!UICONTROL Get Workspaces]

Este módulo de búsqueda recupera los espacios de trabajo de una organización.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Split.io] a [!DNL Workfront Fusion], consulte <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Split.io] a [!UICONTROL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Introduzca o asigne el número máximo de espacios de trabajo que desea que el módulo recupere durante cada ciclo de ejecución de escenario.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Environments]

Este módulo de búsqueda recupera una lista de entornos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Split.io] a [!DNL Workfront Fusion], consulte <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Split.io] a [!UICONTROL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Seleccione o asigne el espacio de trabajo que contiene los entornos que desea enumerar.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Splits]

Este módulo de búsqueda recupera una lista de divisiones.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Split.io] a [!DNL Workfront Fusion], consulte <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Split.io] a [!UICONTROL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Seleccione o asigne el espacio de trabajo que contiene las divisiones que desea enumerar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Introduzca o asigne el número máximo de divisiones que desea que el módulo recupere durante cada ciclo de ejecución de escenario.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Split Definitions in an Environment]

Este módulo de búsqueda recupera una lista de definiciones divididas en un entorno determinado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Split.io] a [!DNL Workfront Fusion], consulte <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Split.io] a [!UICONTROL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Seleccione o asigne el espacio de trabajo que contiene las definiciones de división que desea enumerar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Environment Name or ID]</td> 
   <td>Seleccione o asigne el entorno que contiene las definiciones de división que desea enumerar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Introduzca o asigne el número máximo de definiciones de división que desea que el módulo recupere durante cada ciclo de ejecución de escenario.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Traffic Types]

Este módulo de búsqueda recupera una lista de tipos de tráfico.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Split.io] a [!DNL Workfront Fusion], consulte <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Split.io] a [!UICONTROL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Seleccione o asigne el espacio de trabajo que contiene los tipos de tráfico que desea enumerar.</td> 
  </tr> 
 </tbody> 
</table>
