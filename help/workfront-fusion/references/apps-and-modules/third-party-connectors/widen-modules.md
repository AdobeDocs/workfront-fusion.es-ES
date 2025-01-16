---
title: Módulos de Widen
description: En un  [!DNL Adobe Workfront Fusion] escenario, puede automatizar los flujos de trabajo que utilizan [!UICONTROL Widen], así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
draft: Probably
feature: Workfront Fusion
exl-id: 11376e58-a44b-4766-85dc-e2421b0112de
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1363'
ht-degree: 89%

---

# Módulos de [!DNL Widen]

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!UICONTROL Widen], así como conectarlo a varias aplicaciones y servicios de terceros.

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

Para usar módulos [!UICONTROL Widen], debe tener una cuenta de [!UICONTROL Widen].

## Ampliar información de API

El conector Widen utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> Versión 2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.10.11</td> 
  </tr>
 </tbody> 
 </table>

## Conectar [!DNL Widen] a [!DNL Workfront Fusion] {#connect-widen-to-workfront-fusion}

Puede crear una conexión con su cuenta de [!DNL Widen] directamente desde un módulo de [!DNL Widen].

1. En cualquier módulo de [!DNL Widen], haga clic en **[!UICONTROL Add]** junto al campo [!UICONTROL Connection].
1. Seleccione el dominio [!DNL Widen] al que desea conectarse.
1. Introduzca el token para su cuenta de [!DNL Widen]. Para obtener instrucciones sobre cómo localizar este token, consulte [[!DNL Widen] Preguntas frecuentes sobre API](https://community.widen.com/collective/s/article/API-FAQs).
1. Haga clic en **[!UICONTROL Continue]** para crear la conexión y volver al módulo.

## Módulos de [!DNL Widen] y sus campos

Al configurar módulos de [!DNL Widen], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Widen] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Módulos de activador](#trigger-modules)
* [Módulos de acción](#action-modules)
* [Módulos de búsqueda](#search-modules)

### Módulos de activador

#### [!UICONTROL Watch assets]

Este módulo activador inicia un escenario cuando se crea o actualiza un recurso.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Widen] a [!DNL Workfront Fusion], consulte <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Widen] a [!DNL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event type]</td> 
   <td> <p>Seleccione si desea ver recursos nuevos o actualizados.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expand]</td> 
   <td> <p>Seleccione las propiedades que desee incluir en la salida del módulo además de los campos de recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Seleccione los campos que desea incluir en la salida del módulo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de recursos con los que desea que trabaje el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Módulos de acción

* [[!UICONTROL Custom API Call]](#custom-api-call)
* [[!UICONTROL Read asset info]](#read-asset-info)
* [[!UICONTROL Add assets to collections]](#add-assets-to-collections)
* [[!UICONTROL Remove assets from collection]](#remove-assets-from-collection)
* [[!UICONTROL Update asset metadata]](#update-asset-metadata)
* [[!UICONTROL Download File]](#download-file)
* [[!UICONTROL Upload] un archivo](#upload-a-file)

#### [!UICONTROL Custom API Call]

Este módulo de acción le permite realizar una llamada autenticada personalizada a la API [!DNL Widen]. De este modo, puede crear una automatización del flujo de datos imposibles de realizar por los otros [!DNL Widen] módulos.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Widen] a [!DNL Workfront Fusion], consulte <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Widen] a [!DNL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL API Version]</td> 
   <td>Seleccione si desea utilizar la última versión de la API [!DNL Widen] o la versión 1.0</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Introduzca o asigne la URL de su llamada de API.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Métodos de petición HTTP en [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>[!UICONTROL Workfront Fusion] añade los encabezados de autorización automáticamente.</p> </td> 
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

#### [!UICONTROL Read asset info]

Este módulo de acción recupera un recurso individual por su ID único.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Widen] a [!DNL Workfront Fusion], consulte <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Widen] a [!DNL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td> <p>Introduzca o asigne el ID del recurso del que desea leer información.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expand]</td> 
   <td> <p>Seleccione las propiedades que desee incluir en la salida del módulo además de los campos de recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Seleccione los campos que desea incluir en la salida del módulo.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Add assets to collections]

Este módulo de acción añade uno o más recursos a las colecciones.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Widen] a [!DNL Workfront Fusion], consulte <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Widen] a [!DNL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collections ID]</td> 
   <td> <p>Para cada colección a la que desee añadir los recursos:</p> 
    <ol> 
     <li value="1"> <p> Haga clic en <strong>[!UICONTROL Add]</strong>.</p> </li> 
     <li value="2"> <p>Escriba o asigne [!UICONTROL Collection ID].</p> </li> 
     <li value="3"> <p>Haga clic en <strong>[!UICONTROL Add item]</strong>.</p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assets ID]</td> 
   <td> <p>Para cada recurso que desee añadir a una colección:</p> 
    <ol> 
     <li value="1"> <p> Haga clic en <strong>[!UICONTROL Add]</strong>.</p> </li> 
     <li value="2"> <p>Introduzca o asigne el ID de recurso.</p> </li> 
     <li value="3"> <p>Haga clic en <strong>[!UICONTROL Add item]</strong>.</p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de recursos con los que desea que trabaje el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Remove assets from collection]

Este módulo de acción elimina uno o varios recursos de las colecciones.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Widen] a [!DNL Workfront Fusion], consulte <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Widen] a [!DNL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collections ID]</td> 
   <td> <p>Para cada colección de la que desee quitar los recursos:</p> 
    <ol> 
     <li value="1"> <p> Haga clic en <strong>[!UICONTROL Add]</strong>.</p> </li> 
     <li value="2"> <p>Introduzca o asigne el ID de colección.</p> </li> 
     <li value="3"> <p>Haga clic en <strong>[!UICONTROL Add item]</strong>.</p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de recursos</td> 
   <td> <p>Para cada recurso que desee quitar de una colección:</p> 
    <ol> 
     <li value="1"> <p> Haga clic en <strong>[!UICONTROL Add]</strong>.</p> </li> 
     <li value="2"> <p>Introduzca o asigne el ID de recurso.</p> </li> 
     <li value="3"> <p>Haga clic en <strong>[!UICONTROL Add item]</strong>.</p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de recursos con los que desea que trabaje el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update asset metadata]

Este módulo de acción actualiza los campos de metadatos de un recurso.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Widen] a [!DNL Workfront Fusion], consulte <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Widen] a [!DNL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td> <p>Introduzca o asigne el ID del recurso donde desea actualizar los metadatos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata type]</td> 
   <td> <p>Seleccione el tipo de metadatos para los metadatos que desea actualizar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata]</td> 
   <td>Seleccione los campos de metadatos que desea actualizar. Para cada campo, introduzca el nuevo valor para el campo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de recursos con los que desea que trabaje el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download File]

Este módulo de acción descarga un recurso de su cuenta de [!DNL Widen].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Widen] a [!DNL Workfront Fusion], consulte <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Widen] a [!DNL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td> <p>Introduzca o asigne el ID del recurso que desea descargar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a file]

Este módulo de acción carga un archivo a su cuenta de [!DNL Widen].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Widen] a [!DNL Workfront Fusion], consulte <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Widen] a [!DNL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Upload Profile]</td> 
   <td> <p>Seleccione el perfil de carga que desea que utilice el módulo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Upload Method]</td> 
   <td> <p>Seleccione cómo desea cargar el archivo.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL From File]</strong> </p> <p>Seleccione o asigne el archivo de origen de un módulo anterior.</p> </li> 
     <li> <p><strong>[!UICONTROL By URL]</strong> </p> <p>Introduzca o asigne la URL del archivo que desea cargar.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File name]</td> 
   <td>Introduzca o asigne un nombre para el archivo cargado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata Type]</td> 
   <td>Seleccione el tipo de metadatos del archivo que desea cargar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata]</td> 
   <td>Seleccione los campos de metadatos que desee incluir en la carga del archivo. Para cada campo, ingrese [!UICONTROL value] para el campo.</td> 
  </tr> 
 </tbody> 
</table>

### Módulos de búsqueda

* [[!UICONTROL Read collection assets]](#read-collection-assets)
* [[!UICONTROL Search assets]](#search-assets)

#### [!UICONTROL Read collection assets]

Este módulo de acción recupera una lista de recursos dentro de una colección.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Widen] a [!DNL Workfront Fusion], consulte <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Widen] a [!DNL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collection ID]</td> 
   <td> <p>Introduzca o asigne el ID de la colección que contiene los recursos que desea leer.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start]</td> 
   <td>Introduzca o asigne el número del primer elemento que desee enumerar. Esta es una forma de paginar los registros.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Max]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort By]</td> 
   <td> <p>Seleccione la propiedad según la cual desea ordenar los recursos. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order]</td> 
   <td>Seleccione si desea ordenar los recursos de forma ascendente o descendente.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Seleccione los campos que desea incluir en la salida del módulo.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search assets]

Este módulo de búsqueda recupera una lista de recursos que coinciden con los criterios de búsqueda específicos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Widen] a [!DNL Workfront Fusion], consulte <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Widen] a [!DNL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search query]</td> 
   <td> <p>Introduzca los criterios según los cuales quiere buscar recursos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort By]</td> 
   <td> <p>Seleccione cómo desea ordenar los recursos. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order]</td> 
   <td>Seleccione si desea ordenar los recursos de forma ascendente o descendente.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include deleted]</td> 
   <td>Active esta opción para incluir los recursos eliminados en la búsqueda.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Include archived]</p> </td> 
   <td> <p>Active esta opción para incluir recursos archivados en la búsqueda.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search document text]</td> 
   <td>Active esta opción para incluir el texto del documento en la búsqueda o active la opción Falso para incluir solo los recursos cuyo título coincida con los criterios de búsqueda.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Offset]</td> 
   <td>Introduzca o asigne el número del primer elemento para el que desea recuperar detalles. Esta es una forma de paginar los registros.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scroll]</td> 
   <td>Active esta opción para permitir el desplazamiento.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expand]</td> 
   <td> <p>Seleccione las propiedades que desee incluir en la salida del módulo además de los campos de recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Seleccione los campos que desea incluir en la salida del módulo.</td> 
  </tr> 
 </tbody> 
</table>
