---
title: Módulos de Google Team Drive
description: Los módulos de  [!DNL Adobe Workfront Fusion Google Team Drive]  le permiten supervisar, cargar, actualizar, copiar, eliminar o recuperar archivos y crear carpetas en su Drive de  [!DNL Google Shared] .
author: Becky
feature: Workfront Fusion
exl-id: 95dd9d23-1df9-40da-8fd0-646cc697bfc8
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1397'
ht-degree: 67%

---

# Módulos de [!DNL Google Team Drive]

Los módulos de Adobe Workfront Fusion [!DNL Google Team Drive] le permiten supervisar, cargar, actualizar, copiar, eliminar o recuperar archivos y crear carpetas en su [!DNL Google Shared Drive].

Para usar [!DNL Google Team Drive] con Adobe Workfront Fusion, es necesario tener una cuenta de [!DNL Google Workspace]. Si no dispone de una, puede crear una cuenta de [!DNL Google Workspace] en el sitio de registro de [[!DNL Google Workspace] ](https://workspace.google.com/business/signup/welcome).

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!DNL Google Team Drive], así como conectarlo a varias aplicaciones y servicios de terceros.

Para obtener instrucciones sobre cómo crear un escenario, vea los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

## Requisitos de acceso

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Plan de Adobe Workfront*</td>
  <td> <p>[!UICONTROL Pro] o superior</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencia de Adobe Workfront*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion**</td> 
   <td>
   <p>Requisito de licencia actual: no se requiere licencia de Workfront Fusion.</p>
   <p>O</p>
   <p>Requisito de licencia heredado: [!UICONTROL Workfront Fusion para automatización e integración de trabajo] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Requisito actual del producto: si tiene el plan de Adobe Workfront de [!UICONTROL Select] o [!UICONTROL Prime], su organización debe adquirir Adobe Workfront Fusion y Adobe Workfront para utilizar la funcionalidad que se describe en este artículo. Workfront Fusion está incluido en el plan de Workfront de [!UICONTROL Ultimate].</p>
   <p>O</p>
   <p>Requisito de productos heredados: su organización debe adquirir Adobe Workfront Fusion así como Adobe Workfront para utilizar la funcionalidad descrita en este artículo.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Para saber qué plan, tipo de licencia o acceso tiene, póngase en contacto con el administrador de Workfront.

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## Requisitos previos

Para usar los módulos de [!DNL Google Team Drive], debe disponer de [!DNL Google Team Drive].

## Módulos de [!DNL Google Team Drive] y sus campos

Al configurar módulos de [!DNL Google Team Drive], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL Google Team Drive] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Los campos del cuadro de diálogo del módulo que se muestran en **bold** (en el escenario de Workfront Fusion, **not** en este artículo de documentación) son obligatorios.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Activadores

#### [!UICONTROL Ver archivos]

Devuelve detalles del archivo cuando se añade o modifica un nuevo archivo en la carpeta especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Team Drive] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Team Drive]</td> 
   <td> <p> Seleccione la unidad compartida que desee ver.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Seleccione la carpeta dentro de la unidad compartida.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL What files to watch]</td> 
   <td> <p> Seleccione el tipo de archivos que desee ver. </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Documents] files to format] </td> 
   <td> <p>Seleccione el formato al que desea convertir los archivos de [!DNL Google Documents] que ha visto.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Sheets] files to format] </td> 
   <td> <p>Seleccione el formato al que desea convertir los archivos de [!DNL Google Sheets] que ha visto.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Slides] files to format] </td> 
   <td> <p>Seleccione el formato al que desea convertir los archivos de [!DNL Google Slides] que ha visto.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Drawings] files to format] </td> 
   <td> <p>Seleccione el formato al que desea convertir los archivos de [!DNL Google Drawings] detectados.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Watch]</td> 
   <td> <p> Seleccione si desea supervisar la carpeta en busca de archivos nuevos y modificados o solo en busca de archivos nuevos.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of downloaded files]</td> 
   <td> <p> Establezca el número máximo de archivos que Workfront Fusion devolverá durante un ciclo de ejecución.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Acciones

* [[!UICONTROL Cargar un archivo]](#upload-a-file)
* [[!UICONTROL Actualizar un archivo]](#update-a-file)
* [[!UICONTROL Copiar un archivo]](#copy-a-file)
* [[!UICONTROL Eliminar un archivo]](#delete-a-file)
* [[!UICONTROL Mover un archivo a la papelera]](#move-a-file-to-trash)
* [[!UICONTROL Obtener un archivo]](#get-a-file)
* [[!UICONTROL Obtener una lista de archivos]](#get-a-file-list)
* [[!UICONTROL Crear una carpeta]](#create-a-folder)

#### [!UICONTROL Cargar un archivo]

Carga un archivo en la unidad compartida especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Team Drive] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Team Drive] </td> 
   <td> <p>Seleccione la unidad compartida en la que desea cargar un archivo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Seleccione la carpeta dentro de la unidad compartida.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Source File]</p> </td> 
   <td> <p>Especifique el archivo que desea cargar en la unidad compartida.</p> <p>Asigne el archivo que desee cargar desde el módulo anterior (por ejemplo, [!UICONTROL HTTP] &gt; [!UICONTROL Obtener un archivo] o [!UICONTROL Dropbox] &gt;[!UICONTROL Obtener un archivo)], o bien introduzca manualmente el nombre y los datos del archivo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Title]</td> 
   <td> <p> Escriba el título del archivo que se mostrará en la carpeta compartida.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert a File]</td> 
   <td> <p> Active esta opción para convertir el archivo al formato de Google correspondiente en la carpeta compartida.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Actualizar un archivo]

Le permite cambiar el nombre de archivo o el contenido del archivo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Team Drive] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Team Drive]</td> 
   <td> <p> Seleccione la unidad compartida que contiene el archivo que desea actualizar.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Seleccione la carpeta dentro de la unidad compartida.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td> <p> Introduzca (asigne) el ID del archivo que desea actualizar.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Source File]</p> </td> 
   <td>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Title] </td> 
   <td> <p>Introduzca el nuevo título del archivo actualizado.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert a File]</td> 
   <td> <p> Habilite esta opción para convertir el archivo al formato de [!DNL Google] correspondiente en la carpeta compartida.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Copiar un archivo]

Copia un archivo especificado en la carpeta seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Team Drive] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Team Drive]</td> 
   <td> <p> Seleccione la unidad compartida que contiene el archivo que desea copiar.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Seleccione la carpeta de destino a la que desea copiar el archivo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td> <p> Introduzca (asigne) el ID del archivo que desea copiar.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL The name of the copy file]</p> </td> 
   <td> <p>Introduzca el nuevo nombre de archivo si desea que se cambie en la ubicación de destino.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Eliminar un archivo]

Elimina un archivo especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Team Drive] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td> <p> Introduzca o asigne el ID del archivo que desea eliminar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Mover un archivo a la papelera]

Mueve un archivo especificado a la papelera.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Team Drive] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td> <p> Introduzca o asigne el ID del archivo que desea mover a la papelera.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Obtener un archivo]

Recupera detalles acerca del archivo especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Team Drive] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Documents] files to format] </td> 
   <td> <p>Seleccione el formato al que desea convertir los archivos de [!DNL Google Documents].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Sheets] files to format] </td> 
   <td> <p>Seleccione el formato al que desea convertir los archivos de [!DNL Google Sheets].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Slides] files to format] </td> 
   <td> <p>Seleccione el formato al que desea convertir los archivos de [!DNL Google Slides].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Drawings] files to format] </td> 
   <td> <p>Seleccione el formato al que desea convertir los archivos de [!DNL Google Drawings].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td> <p> Introduzca o asigne el ID del archivo que desea recuperar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Obtener una lista de archivos]

Recupera detalles de archivos o carpetas en función del término de búsqueda.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Team Drive] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Team Drive]</td> 
   <td> <p> Seleccione la unidad compartida desde la que desee enumerar los archivos.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Seleccione la carpeta desde la que desee enumerar los archivos.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search] </td> 
   <td> <p>Seleccione el tipo de búsqueda que desea realizar (consulte a continuación).</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Query]</p> </td> 
   <td> 
    <ul> 
     <li style="font-weight: bold;"> <p>[!UICONTROL Search within file names]</p> <p style="font-weight: normal;">Introduzca el nombre del archivo (incluida la extensión de archivo) cuando la opción [!UICONTROL Search for exact term Search] esté seleccionada o introduzca la parte del nombre cuando la opción [!UICONTROL Search for names containing the searched term] esté seleccionada.</p> </li> 
     <li> <p style="font-weight: bold;">[!UICONTROL Fulltext search]</p> <p>Introduzca el término de búsqueda para buscar entre los nombres de archivo, las descripciones y el contenido.</p> </li> 
     <li> <p style="font-weight: bold;">[!UICONTROL Custom search query]</p> <p>Escriba el término de la consulta de búsqueda de [!DNL Google]. Para obtener más información, consulte <a href="https://developers.google.com/drive/api/v2/ref-search-terms">Documentación de la consulta de búsqueda</a> de [!DNL Google]. Ejemplo: <code>fullText contains '"Hello world"'</code></p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Retrieve]</td> 
   <td>Seleccione si desea recuperar archivos, carpetas o ambos.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned results]</td> 
   <td> <p> Establezca el número máximo de archivos o carpetas que Workfront Fusion devolverá durante un ciclo de ejecución.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Crear una carpeta]

Crea una nueva carpeta.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Team Drive] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Team Drive]</td> 
   <td> <p> Seleccione la unidad compartida donde desea crear una carpeta.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Seleccione la carpeta en la que desea crear una carpeta.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL The name of the new folder]</td> 
   <td> <p> Introduzca el nombre de la nueva carpeta.</p> </td> 
  </tr> 
 </tbody> 
</table>
