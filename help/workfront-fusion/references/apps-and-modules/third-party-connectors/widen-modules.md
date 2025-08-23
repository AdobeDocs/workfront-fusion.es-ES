---
title: Módulos de Widen
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!UICONTROL Widen], así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
draft: Probably
feature: Workfront Fusion
exl-id: 11376e58-a44b-4766-85dc-e2421b0112de
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1657'
ht-degree: 70%

---

# Módulos de [!DNL Widen]

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!UICONTROL Widen], así como conectarlo a varias aplicaciones y servicios de terceros.

Para obtener instrucciones sobre cómo crear un escenario, vea los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

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
   <td> <p>Nuevo: estándar</p><p>O</p><p>Actual: Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion**</td> 
   <td>
   <p>Actual: No se requiere licencia de Workfront Fusion</p>
   <p>O</p>
   <p>Heredado: Workfront Fusion para la automatización e integración del trabajo </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Seleccione o paquete de Prime Workfront: su organización debe adquirir Adobe Workfront Fusion.</li><li>Paquete de Ultimate Workfront: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe comprar Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

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

## Conexión de [!DNL Widen] a Workfront Fusion  {#connect-widen-to-workfront-fusion}

Puede crear una conexión con su cuenta de [!DNL Widen] directamente desde un módulo de [!DNL Widen].

1. En cualquier módulo de [!DNL Widen], haga clic en **[!UICONTROL Añadir]** junto al campo [!UICONTROL Conexión].
1. Seleccione el entorno y el tipo de cuenta a la que se está conectando. Esto es solo para obtener información y aparece en el área Conexiones de Fusion.
1. Seleccione el dominio [!DNL Widen] al que desea conectarse.
1. Introduzca el token para su cuenta de [!DNL Widen]. Para obtener instrucciones sobre cómo localizar este token, consulte [[!DNL Widen] Preguntas frecuentes sobre API](https://community.widen.com/collective/s/article/API-FAQs).
1. Haga clic en **[!UICONTROL Continuar]** para crear la conexión y volver al módulo.

## Módulos de [!DNL Widen] y sus campos

Al configurar módulos de [!DNL Widen], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL Widen] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Módulos de activador](#trigger-modules)
* [Módulos de acción](#action-modules)
* [Módulos de búsqueda](#search-modules)

### Módulos de activador

#### [!UICONTROL Ver recursos]

Este módulo activador inicia un escenario cuando se crea o actualiza un recurso.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Widen] a Workfront Fusion, consulte <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Widen] a Workfront Fusion </a> en este artículo.</p> </td> 
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

* [[!UICONTROL Añadir recursos a colecciones]](#add-assets-to-collections)
* [[!UICONTROL Llamada de API personalizada]](#custom-api-call)
* [[!UICONTROL Descargar archivo]](#download-file)
* [[!UICONTROL Leer información de recurso]](#read-asset-info)
* [[!UICONTROL Quitar recursos de la colección]](#remove-assets-from-collection)
* [[!UICONTROL Actualizar metadatos de recursos]](#update-asset-metadata)
* [[!UICONTROL Cargar un archivo]](#upload-a-file)

#### [!UICONTROL Añadir recursos a colecciones]

Este módulo de acción añade uno o más recursos a las colecciones.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Widen] a Workfront Fusion, consulte <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Widen] a Workfront Fusion </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collections ID]</td> 
   <td>Para cada colección a la que desee agregar los recursos, haga clic en <strong>[ID de colección]</strong> e introduzca o asigne el [!UICONTROL ID de colección].</li> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assets ID]</td> 
   <td> Para cada recurso que desee agregar a una colección, haga clic en <strong>[!UICONTROL Assets ID]</strong> e introduzca o asigne el ID del recurso.</p> </li> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de recursos con los que desea que trabaje el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Llamada de API personalizada]

Este módulo de acción le permite realizar una llamada autenticada personalizada a la API [!DNL Widen]. De este modo, puede crear una automatización del flujo de datos imposibles de realizar por los otros [!DNL Widen] módulos.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Widen] a Workfront Fusion, consulte <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Widen] a Workfront Fusion </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL API Version]</td> 
   <td>Seleccione si desea utilizar la última versión de la API [!DNL Widen] o la versión 1.0</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Introduzca o asigne la URL de su llamada de API.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Métodos de solicitud HTTP</a>.</p> </td> 
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

#### [!UICONTROL Descargar archivo]

Este módulo de acción descarga un recurso de su cuenta de [!DNL Widen].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Widen] a Workfront Fusion, consulte <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Widen] a Workfront Fusion </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td> <p>Introduzca o asigne el ID del recurso que desea descargar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Leer información de recurso]

Este módulo de acción recupera un recurso individual por su ID único.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Widen] a Workfront Fusion, consulte <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Widen] a Workfront Fusion </a> en este artículo.</p> </td> 
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

#### [!UICONTROL Quitar recursos de la colección]

Este módulo de acción elimina uno o varios recursos de las colecciones.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Widen] a Workfront Fusion, consulte <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Widen] a Workfront Fusion </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collections ID]</td> 
   <td>Para cada colección de la que desee quitar recursos, haga clic en <strong>[ID de colección]</strong> e introduzca o asigne el [!UICONTROL ID de colección].</li> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assets ID]</td> 
   <td> Para cada recurso que desee eliminar de una colección, haga clic en <strong>[!UICONTROL Assets ID]</strong> e introduzca o asigne el ID del recurso.</p> </li> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de recursos con los que desea que trabaje el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Actualizar metadatos de recurso]

Este módulo de acción actualiza los campos de metadatos de un recurso.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Widen] a Workfront Fusion, consulte <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Widen] a Workfront Fusion </a> en este artículo.</p> </td> 
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

#### [!UICONTROL Subir un archivo]

Este módulo de acción carga un archivo a su cuenta de [!DNL Widen].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Widen] a Workfront Fusion, consulte <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Widen] a Workfront Fusion </a> en este artículo.</p> </td> 
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
   <td>Seleccione los campos de metadatos que desee incluir en la carga del archivo. Para cada campo, introduzca el [!UICONTROL value] para el campo.</td> 
  </tr> 
 </tbody> 
</table>

### Módulos de búsqueda

* [[!UICONTROL Leer recursos de colección]](#read-collection-assets)
* [[!UICONTROL Buscar recursos]](#search-assets)

#### [!UICONTROL Leer recursos de colección]

Este módulo de acción recupera una lista de recursos dentro de una colección.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Widen] a Workfront Fusion, consulte <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Widen] a Workfront Fusion </a> en este artículo.</p> </td> 
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

#### [!UICONTROL Buscar recursos]

Este módulo de búsqueda recupera una lista de recursos que coinciden con los criterios de búsqueda específicos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Widen] a Workfront Fusion, consulte <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Widen] a Workfront Fusion </a> en este artículo.</p> </td> 
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
   <td>Active esta opción para incluir el texto del documento en la búsqueda o establezca en falso para incluir solo los recursos cuyo título coincida con los criterios de búsqueda.</td> 
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
