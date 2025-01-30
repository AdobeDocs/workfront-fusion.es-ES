---
title: Módulos de documentos de Google
description: Los módulos  [!DNL Google Docs]  de Adobe Workfront Fusion le permiten supervisar, crear, editar y recuperar documentos en sus  [!DNL Google Docs]  y  [!DNL Google Docs] (para los usuarios de  [!DNL Google Workspace] ).
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: cd44250d-c2cd-46b2-8773-15b30472a8d8
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '3221'
ht-degree: 66%

---

# Módulos de [!DNL Google Docs]

Los módulos de [!DNL Adobe Workfront Fusion] [!DNL Google Docs] le permiten supervisar, crear, editar y recuperar documentos en sus [!DNL Google Docs] y [!DNL Google Docs] (para los usuarios de [!DNL Google Workspace].

Para poder utilizar [!DNL Google Docs] con [!DNL Adobe Workfront Fusion], es necesario tener una cuenta de [!DNL Google]. Si todavía no tiene una cuenta de [!DNL Google], puede crearla en la página de ayuda de la cuenta [!DNL Google].

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

Para utilizar módulos de [!DNL Google Docs], debe tener una cuenta de Google.

## Información de API de Google Docs

El conector de Google Docs utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL básica</td> 
   <td> https://docs.googleapis.com/v1</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> Versión 1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.4.13</td> 
  </tr>
 </tbody> 
 </table>

## Módulos de [!DNL Google Docs] y sus campos

Al configurar módulos de [!DNL Google Docs], [!UICONTROL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Google Docs] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Documento

* [[!UICONTROL Watch Documents]](#watch-documents)
* [[!UICONTROL List Documents]](#list-documents)
* [[!UICONTROL Get Content of a Document]](#get-content-of-a-document)
* [[!UICONTROL Create a Document]](#create-a-document)
* [[!UICONTROL Create a Document From a Template]](#create-a-document-from-a-template)
* [[!UICONTROL Insert a Paragraph to a Document]](#insert-a-paragraph-to-a-document)
* [[!UICONTROL Insert an Image to a Document]](#insert-an-image-to-a-document)
* [[!UICONTROL Replace an Image with a New Image]](#replace-an-image-with-a-new-image)
* [[!UICONTROL Replace Text in a Document]](#replace-text-in-a-document)
* [[!UICONTROL Download a Document]](#download-a-document)
* [[!UICONTROL Delete a Document]](#delete-a-document)

#### [!UICONTROL Watch Documents]

Este módulo de activador devuelve los detalles del documento cuando se crea o modifica un nuevo documento en la carpeta seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch Documents]</td> 
   <td> <p style="color: #000000;">Seleccione si desea ver documentos creados ([!UICONTROL By Created Date]) o modificados ([!UICONTROL By Modified Date]).</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Seleccione el tipo de unidad que desea monitorizar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Seleccione la carpeta en la que desea inspeccionar documentos creados o modificados.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Seleccione la carpeta en la que desea inspeccionar documentos creados o modificados.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] </strong> (disponible solo para usuarios de [!DNL Google Workspace])</p> <p>Seleccione si desea [!UICONTROL Use Domain Admin Access]. Al seleccionar [!UICONTROL Yes], se emite la solicitud como administrador de dominio y se devuelven todas las unidades compartidas en las que el solicitante es administrador.</p> <p>Seleccione la unidad compartida que desee ver.</p> <p>Nota: Si ha seleccionado la opción [!DNL Google Shared Drive] en este campo y no es un usuario de [!DNL Google Workspace], se devuelve el error <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Establezca el número máximo de documentos que Workfront Fusion devuelve en un ciclo de ejecución.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Documents]

Este módulo de acción recupera una lista de documentos de la carpeta seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Seleccione el tipo de unidad desde la que desea enumerar los documentos.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Seleccione la carpeta desde la que desea enumerar los documentos.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Seleccione la carpeta desde la que desea enumerar los documentos.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] </strong> (disponible solo para usuarios de [!DNL Google Workspace])</p> <p>Seleccione si desea [!UICONTROL Use Domain Admin Access]. Al seleccionar [!UICONTROL Yes], se emite la solicitud como administrador de dominio y se devuelven todas las unidades compartidas en las que el solicitante es administrador.</p> <p>Seleccione la unidad compartida desde la que desee enumerar los documentos.</p> <p>Nota: Si ha seleccionado la opción [!DNL Google Docs] en este campo y no es un usuario de [!DNL Google Workspace], se devuelve el error <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Establezca el número máximo de documentos que [!DNL Workfront Fusion] devuelve en un ciclo de ejecución.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Content of a Document]

Este módulo de acción recupera un documento especificado.

Es posible que tenga que ampliar los permisos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get Content of a Document]</td> 
   <td> <p>Seleccione si desea asignar el ID del documento o seleccione de forma manual el documento en el menú desplegable.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Seleccione el tipo de unidad que contiene el documento que desea recuperar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Seleccione la carpeta que contiene el documento que desea recuperar.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Seleccione la carpeta que contiene el documento que desea recuperar.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] </strong> (disponible solo para usuarios de [!DNL Google Workspace])</p> <p>Seleccione si desea [!UICONTROL Use Domain Admin Access]. Al seleccionar [!UICONTROL Yes], se emite la solicitud como administrador de dominio y se devuelven todas las unidades compartidas en las que el solicitante es administrador.</p> <p>Seleccione la unidad compartida que contiene el documento que desea recuperar.</p> <p>Nota: Si ha seleccionado la opción [!DNL Google Docs] en este campo y no es un usuario de [!DNL Google Workspace], se devuelve el error <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Filter]</p> </td> 
   <td> <p>Seleccione el objeto que desea que se devuelva en la salida del módulo.</p> 
    <ul> 
     <li>[!UICONTROL Image] (predeterminado)</li> 
     <li>[!UICONTROL Drawing]</li> 
     <li>[!UICONTROL Chart]</li> 
    </ul> <p>Nota:  <p>Para obtener más información sobre la asignación de estos objetos, utilice el valor [!UICONTROL Inline Objects Array] en la salida de este módulo (en lugar de [!UICONTROL inlineObjects]).</p> <p>Los objetos [!UICONTROL Inline Objects Array] se ordenan en el mismo orden en que aparecen en el documento. Esto facilitará cualquier procesamiento posterior.</p> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Document]

Este módulo de acción le permite crear un nuevo documento en la carpeta seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>Introduzca el nombre del documento.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content]</td> 
   <td> <p>Introduzca el contenido del documento.  Se admite el HTML.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Seleccione el tipo de unidad donde desea crear un documento.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Seleccione la carpeta donde desea crear un documento.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Seleccione la carpeta donde desea crear un documento.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] </strong> (disponible solo para usuarios de [!DNL Google Workspace])</p> <p>Seleccione si desea [!UICONTROL Use Domain Admin Access]. Al seleccionar [!UICONTROL Yes], se emite la solicitud como administrador de dominio y se devuelven todas las unidades compartidas en las que el solicitante es administrador.</p> <p>Seleccione la unidad compartida en la que desea crear un documento.</p> <p>Nota: Si ha seleccionado la opción [!DNL Google Docs] en este campo y no es un usuario de [!DNL Google Workspace], se devuelve el error <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Insert a Header]</td> 
   <td> <p> Active esta opción para insertar el encabezado en el documento y, a continuación, introduzca o asigne el texto del encabezado.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Insert a Footer] </td> 
   <td> <p>Active esta opción para insertar el pie de página en el documento y, a continuación, introduzca o asigne el texto del encabezado.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Document From a Template]

Este módulo de acción crea una copia de un documento de plantilla existente y reemplaza las etiquetas. Este módulo también permite a los usuarios reemplazar imágenes con nuevas imágenes por URL.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Create a Document from a Template]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>Seleccione esta opción para asignar la plantilla de documento.</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br>Seleccione esta opción para elegir la plantilla de documento en el menú desplegable.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Seleccione el tipo de unidad en la que se encuentra la plantilla. Esta opción está disponible si seleccionó [!UICONTROL By Dropdown] en el campo anterior.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Seleccione la carpeta donde se encuentra la plantilla.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Seleccione la carpeta donde se encuentra la plantilla.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] </strong> (disponible solo para usuarios de [!DNL Google Workspace])</p> <p>Seleccione si desea [!UICONTROL Use Domain Admin Access]. Al seleccionar [!UICONTROL Yes], se emite la solicitud como administrador de dominio y se devuelven todas las unidades compartidas en las que el solicitante es administrador.</p> <p>Seleccione la unidad compartida en la que se encuentra la plantilla.</p> <p>Nota: Si ha seleccionado la opción [!DNL Google Docs] en este campo y no es un usuario de [!DNL Google Workspace], se devuelve el error <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Values]</p> </td> 
   <td> <p>Escriba los valores que se introducirán en lugar de las variables en el nuevo documento.</p> 
    <ul> 
     <li><strong>[!UICONTROL Tags]</strong> <br>Introduzca las etiquetas que contiene la plantilla de documento. No use <code>&#123;&#123;&#125;&#125;</code>. Ejemplo: use <code>name</code> en lugar de <code>&#123;&#123;name&#125;&#125;</code>.</li> 
     <li><strong>[!UICONTROL Replaced Value]</strong><br>Introduzca el valor de la etiqueta.</li> 
    </ul> <p>Por ejemplo, la variable <code> &#123;&#123;name&#125;&#125;</code> del documento de origen se mostrará como el campo de nombre aquí, donde se puede insertar el valor, como <code>John</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Images Replacement]</p> </td> 
   <td> <p>Escriba el vínculo a [!UICONTROL Image Object ID] y [!UICONTROL Image URL] que reemplazarán la imagen actual.</p> <p>Nota: Puede recuperar los ID de imagen mediante el módulo [!UICONTROL Get a Document], donde los ID están contenidos en la matriz [!UICONTROL Inline Object Array].</p> <p>Le recomendamos que añada texto alternativo a las imágenes de su documento de [!DNL Google]. </p> <p>Para añadir un texto alternativo a la imagen de [!DNL Google Docs], siga estos pasos:</p> 
    <ol> 
     <li value="1">Haga clic con el botón derecho en la imagen.</li> 
     <li value="2">Seleccione la opción [!UICONTROL ALT text].</li> 
     <li value="3">Escriba [!UICONTROL ALT text] en el campo [!UICONTROL Title] y haga clic en [!UICONTROL OK].</li> 
    </ol> <p>Una vez añadido el texto alternativo a la imagen, se muestra entre paréntesis en el nombre del campo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Title] </td> 
   <td> <p>Introduzca el nombre del nuevo documento.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Seleccione el tipo de unidad en la que se encuentra la plantilla. Esta opción está disponible si seleccionó [!UICONTROL By Dropdown] en el campo anterior.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Seleccione la carpeta donde desea crear el documento.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Seleccione la carpeta donde desea crear el documento.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] </strong> (disponible solo para usuarios de [!DNL Google Workspace])</p> <p>Seleccione si desea [!UICONTROL Use Domain Admin Access]. Al seleccionar [!UICONTROL Yes], se emite la solicitud como administrador de dominio y se devuelven todas las unidades compartidas en las que el solicitante es administrador.</p> <p>Seleccione la unidad compartida en la que desea crear el documento.</p> <p>Nota: Si ha seleccionado la opción [!DNL Google Docs] en este campo y no es un usuario de [!DNL Google Workspace], se devuelve el error <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Insert a Paragraph to a Document]

Este módulo de acción anexa o inserta un párrafo nuevo en un documento existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Select a Document]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>Seleccione esta opción para asignar el documento.</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br> Seleccione esta opción para elegir el documento en el menú desplegable.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Seleccione el tipo de unidad en la que se encuentra el documento al que desea añadir un párrafo. Esta opción está disponible si seleccionó [!UICONTROL By Dropdown] en el campo anterior.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Seleccione la carpeta donde se encuentra el documento al que desea añadir un párrafo y, a continuación, seleccione el documento.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Seleccione la carpeta donde se encuentra el documento al que desea añadir un párrafo y, a continuación, seleccione el documento.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] </strong> (disponible solo para usuarios de [!DNL Google Workspace])</p> <p>Seleccione si desea [!UICONTROL Use Domain Admin Access]. Al seleccionar [!UICONTROL Yes], se emite la solicitud como administrador de dominio y se devuelven todas las unidades compartidas en las que el solicitante es administrador.</p> <p>Seleccione la unidad compartida donde se encuentra el documento al que desea añadir un párrafo y, a continuación, seleccione el documento.</p> <p>Nota: Si ha seleccionado la opción [!DNL Google Docs] en este campo y no es un usuario de [!DNL Google Workspace], se devuelve el error <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Insert a Paragraph]</p> </td> 
   <td> <p>Seleccione cómo desea que se inserte el nuevo texto en el documento.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL By specification of location]</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL By index]</strong> </p> 
        <ul> 
         <li> <p><strong>[!UICONTROL Index]</strong> </p> <p>Introduzca el número de índice donde desea insertar el texto. Puede usar el módulo [!UICONTROL Get a Document] para recuperar el número de índice.</p> <p>Para mostrar todos los caracteres (incluidos los ocultos) del documento, puede utilizar el complemento [!UICONTROL Show]. Puede encontrar el complemento en [!UICONTROL Add-ons] &gt; [!UICONTROL Get add-ons]. Busque [!UICONTROL Show] e instale el complemento [!UICONTROL Show].</p> </li> 
         <li> <p><strong>[!UICONTROL Inserted text]</strong> </p> <p>Escriba el texto que desee insertar en el documento.</p> </li> 
        </ul> </li> 
       <li> <p><strong>[!UICONTROL By segment ID]</strong> </p> <p>Seleccione el encabezado y el pie de página en los que desea insertar el contenido del texto e introduzca el texto que quiere escribir en los campos correspondientes.</p> <p>Si el encabezado o pie de página ya contiene texto, el nuevo texto se añadirá antes del texto existente.</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL By appending to the body of the document]</strong> </p> <p>Añada el texto introducido al final del contenido del cuerpo del documento.</p> <p>El estilo del nuevo párrafo se copiará del párrafo en el índice de inserción actual, incluidas las listas y viñetas.</p> </li> 
    </ul> 
    <ul> 
     <li> <p><strong>[!UICONTROL By appending to the end of segment (Header and Footer)]</strong> </p> <p>Seleccione el encabezado y el pie de página en los que desea insertar el contenido del texto e introduzca el texto que quiere escribir en los campos correspondientes.</p> <p>Si el encabezado o pie de página ya contiene texto, el nuevo texto se añadirá después del existente.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Appended Text]</td> 
   <td>Escritura o asignación del texto que desea anexar al documento</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Insert an Image to a Document]

Este módulo de acción inserta una imagen desde la dirección URL al documento.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Select a Document]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>Seleccione esta opción para asignar la plantilla de documento.</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br> Seleccione esta opción para elegir el documento en el menú desplegable.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Seleccione el tipo de unidad donde se encuentra el documento al que desea añadir una imagen. Esta opción está disponible si seleccionó [!UICONTROL By Dropdown] en el campo anterior.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Seleccione la carpeta donde se encuentra el documento al que desea añadir una imagen y, a continuación, seleccione el documento.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Seleccione la carpeta donde se encuentra el documento al que desea añadir una imagen y, a continuación, seleccione el documento.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] </strong> (disponible solo para usuarios de [!DNL Google Workspace])</p> <p>Seleccione si desea [!UICONTROL Use Domain Admin Access]. Al seleccionar [!UICONTROL Yes], se emite la solicitud como administrador de dominio y se devuelven todas las unidades compartidas en las que el solicitante es administrador.</p> <p>Seleccione la unidad compartida donde se encuentra el documento al que desea añadir una imagen y, a continuación, seleccione el documento.</p> <p>Nota: Si ha seleccionado la opción [!DNL Google Docs] en este campo y no es un usuario de [!DNL Google Workspace], se devuelve el error <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Insert an Image]</p> </td> 
   <td> <p>Seleccione cómo desea insertar la nueva imagen en el documento.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL By specification of location]</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL By index]</strong> </p> 
        <ul> 
         <li> <p><strong>[!UICONTROL Index]</strong> </p> <p>Introduzca el número del índice donde quiera insertar la imagen. Puede usar el módulo [!UICONTROL Get a Document] para recuperar [!UICONTROL Index number].</p> <p>Para mostrar todos los caracteres (incluidos los ocultos) del documento, puede utilizar el complemento [!UICONTROL Show]. Puede encontrar el complemento en [!UICONTROL Add-ons] &gt; [!UICONTROL Get add-ons]. Busque [!UICONTROL Show] e instale el complemento [!UICONTROL Show].</p> </li> 
         <li> <p><strong>[!UICONTROL Image URL]</strong> </p> <p>Introduzca la dirección URL de la imagen que quiera insertar en el documento.</p> <p>El tamaño máximo de la imagen es de 50 MB. No se pueden superar los 25 megapíxeles. Solo se admiten los formatos PNG, JPEG o GIF.</p> </li> 
        </ul> </li> 
       <li> <p><strong>[!UICONTROL By segment ID]</strong> </p> <p>Seleccione el encabezado y pie de página en los que quiera insertar la imagen e introduzca la URL de la misma en los campos correspondientes.</p> <p>El tamaño máximo de la imagen es de 50 MB. La imagen no debe superar los 25 megapíxeles. Solo se admiten los formatos PNG, JPEG o GIF.</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL By appending to the body of the document]</strong> </p> <p>Adjunta una imagen específica al final del contenido del cuerpo del documento.</p> </li> 
    </ul> 
    <ul> 
     <li> <p><strong>[!UICONTROL By appending to the end of segment (Header and Footer)]</strong> </p> <p>Seleccione el encabezado y el pie de página en los que quiera insertar una imagen e introduzca la URL de la imagen que quiera insertar en los campos correspondientes.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Height Magnitude in Points/Width Magnitude in Points]</p> </td> 
   <td> <p>Defina el tamaño de la imagen insertada. Se mantendrá la relación de aspecto.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Replace an Image with a New Image]

Este módulo de acción reemplazará una imagen existente. Se mantendrá la relación de aspecto de la imagen original.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Select a Document]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>Seleccione esta opción para asignar la plantilla de documento.</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br> Seleccione esta opción para elegir el documento en el menú desplegable.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Seleccione el tipo de unidad donde se encuentra el documento del que desea reemplazar una imagen. Esta opción está disponible si seleccionó [!UICONTROL By Dropdown] en el campo anterior.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Seleccione la carpeta en la que se encuentra el documento del que desea reemplazar una imagen y, a continuación, seleccione el documento.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Seleccione la carpeta en la que se encuentra el documento del que desea reemplazar una imagen y, a continuación, seleccione el documento.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] </strong> (disponible solo para usuarios de [!DNL Google Workspace])</p> <p>Seleccione si desea [!UICONTROL Use Domain Admin Access]. Al seleccionar [!UICONTROL Yes], se emite la solicitud como administrador de dominio y se devuelven todas las unidades compartidas en las que el solicitante es administrador.</p> <p>Seleccione la unidad compartida en la que se encuentra el documento del que desea reemplazar una imagen y, a continuación, selecciónelo.</p> <p>Nota: Si seleccionó la opción [!DNL Google Docs] en este campo y no se trata de un usuario de [!DNL Google Workspace], se devolverá el error <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Image URL]</p> </td> 
   <td> <p>Introduzca o asigne la dirección URL de la nueva imagen que reemplazará a la imagen existente.</p> <p>Las imágenes se muestran en el orden en que aparecen en el documento. Por ejemplo: <code>Body: Image No. 1</code> es la primera imagen del documento.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Replace Text in a Document]

Este módulo de acción reemplaza el texto de un documento.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Select a Document]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>Seleccione esta opción para asignar la plantilla de documento.</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br> Seleccione esta opción para elegir el documento en el menú desplegable.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Seleccione el tipo de unidad en la que se encuentra el documento al que desea añadir texto. Esta opción está disponible si seleccionó [!UICONTROL By Dropdown] en el campo anterior.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Seleccione la carpeta donde se encuentra el documento al que desea añadir texto y, a continuación, seleccione el documento.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Seleccione la carpeta donde se encuentra el documento al que desea añadir texto y, a continuación, seleccione el documento.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] </strong> (disponible solo para usuarios de [!DNL Google Workspace])</p> <p>Seleccione si desea [!UICONTROL Use Domain Admin Access]. Al seleccionar [!UICONTROL Yes], se emite la solicitud como administrador de dominio y se devuelven todas las unidades compartidas en las que el solicitante es administrador.</p> <p>Seleccione la unidad compartida en la que se encuentra el documento al que desea añadir texto y, a continuación, seleccione el documento.</p> <p>Nota: Si ha seleccionado la opción [!DNL Google Docs] en este campo y no es un usuario de [!DNL Google Workspace], se devuelve el error <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Replace a Text]</p> </td> 
   <td> <p>Añada cada texto que desee reemplazar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Old text to be replaced]</strong> </p> <p>Escriba el texto que desee reemplazar.</p> </li> 
     <li> <p><strong>[!UICONTROL New text to be inserted]</strong> </p> <p>Introduzca el nuevo texto.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download a Document]

Este módulo de acción convierte y descarga el documento seleccionado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Seleccione el tipo de unidad en la que se encuentra el documento que desea descargar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Seleccione la carpeta en la que se encuentra el documento que desea descargar y, a continuación, seleccione el documento.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Seleccione la carpeta en la que se encuentra el documento que desea descargar y, a continuación, seleccione el documento.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] </strong> (disponible solo para usuarios de [!DNL Google Workspace])</p> <p>Seleccione si desea [!UICONTROL Use Domain Admin Access]. Al seleccionar [!UICONTROL Yes], se emite la solicitud como administrador de dominio y se devuelven todas las unidades compartidas en las que el solicitante es administrador.</p> <p>Seleccione la unidad compartida en la que se encuentra el documento que desea descargar y, a continuación, seleccione el documento.</p> <p>Nota: Si ha seleccionado la opción [!DNL Google Docs] en este campo y no es un usuario de [!DNL Google Workspace], se devuelve el error <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Type] </p> </td> 
   <td> <p>Seleccione el formato de archivo de destino del documento descargado.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Document]

Este módulo de acción elimina un documento.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Seleccione el tipo de unidad en la que se encuentra el documento que desea eliminar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Seleccione la carpeta en la que se encuentra el documento que desea eliminar y, a continuación, seleccione el documento.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Seleccione la carpeta en la que se encuentra el documento que desea eliminar y, a continuación, seleccione el documento.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] </strong> (disponible solo para usuarios de [!DNL Google Workspace])</p> <p>Seleccione si desea [!UICONTROL Use Domain Admin Access]. Al seleccionar [!UICONTROL Yes], se emite la solicitud como administrador de dominio y se devuelven todas las unidades compartidas en las que el solicitante es administrador.</p> <p>Seleccione la unidad compartida en la que se encuentra el documento que desea eliminar y, a continuación, seleccione el documento.</p> <p>Nota: Si ha seleccionado la opción [!DNL Google Docs] en este campo y no es un usuario de [!DNL Google Workspace], se devuelve el error <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Shared Drive]</td> 
   <td> <p>Seleccione la unidad que contiene el documento que desea descargar y, a continuación, seleccione un documento. Esta opción está disponible si ha seleccionado [!DNL Google Docs] en el campo [!UICONTROL Choose a Drive].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Document ID]</td> 
   <td> <p> Seleccione o asigne el documento en el que desea reemplazar una o varias imágenes.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Otro

* [[!UICONTROL Make an API Call]](#make-an-api-call)
* [[!UICONTROL Make All Links in a Document Clickable]](#make-all-links-in-a-document-clickable)

#### [!UICONTROL Make an API Call]

Este módulo de acción le permite realizar una llamada de API personalizada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> <p>Escriba una ruta relativa a <code>https://docs.googleapis.com/</code>. Ejemplo: <code>/v1/documents/{presentationID}</code>. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Métodos de solicitud HTTP</a>.</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar. Por ejemplo, <code>{"Content-type":"application/json"}</code>. [!DNL Workfront Fusion] añade los encabezados de autorización en su lugar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> Introduzca la cadena de consulta de la solicitud.</p> </td> 
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

**Ejemplo:** la siguiente llamada de API recupera los detalles del documento especificado en los documentos de Google:

**URL:**

/v1/documents/1ujkf-GDgB0TQSYPrxbCSK4Uso54tHVMqHZEVZZxB6aY

**Método:**

[!UICONTROL GET]

![Ejemplo de llamada API](/help/workfront-fusion/references/apps-and-modules/assets/api-call-example.png)

Los detalles del documento recuperado se pueden encontrar en la salida del módulo en [!UICONTROL Bundle] > [!UICONTROL Body].

![Salida de llamada API](/help/workfront-fusion/references/apps-and-modules/assets/api-output.png)

#### [!UICONTROL Make All Links in a Document Clickable]

Este módulo de acción busca todos los vínculos del documento y los hace clicables.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Make All Links in a Document]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>Seleccione esta opción para asignar la plantilla de documento.</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br> Seleccione esta opción para elegir el documento en el menú desplegable.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Seleccione el tipo de unidad en la que se encuentra el documento en el que desea que se pueda hacer clic en los vínculos. Esta opción está disponible si seleccionó [!UICONTROL By Dropdown] en el campo anterior.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Seleccione la carpeta en la que se encuentra el documento en el que desea que se pueda hacer clic en los vínculos y, a continuación, seleccione el documento.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Seleccione la carpeta en la que se encuentra el documento en el que desea que se pueda hacer clic en los vínculos y, a continuación, seleccione el documento.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] </strong> (disponible solo para usuarios de [!DNL Google Workspace])</p> <p>Seleccione si desea [!UICONTROL Use Domain Admin Access]. Al seleccionar [!UICONTROL Yes], se emite la solicitud como administrador de dominio y se devuelven todas las unidades compartidas en las que el solicitante es administrador.</p> <p>Seleccione la unidad compartida en la que se encuentra el documento en el que desea que se pueda hacer clic en los vínculos y, a continuación, seleccione el documento.</p> <p>Nota: si ha seleccionado la opción [!DNL Google Docs] en este campo y no es un usuario de [!DNL Google Workspace], se devuelve el error <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Shared Drive]</td> 
   <td> <p>Seleccione la unidad que contiene el documento en el que desea actualizar los vínculos y, a continuación, seleccione un documento. Esta opción está disponible si ha seleccionado [!DNL Google Docs] en [!UICONTROL Choose a Drive field].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Document ID]</td> 
   <td> <p> Seleccione o asigne el documento en el que desea actualizar los vínculos.</p> </td> 
  </tr> 
 </tbody> 
</table>
