---
title: Módulos de Google Drive
description: Los módulos  [!DNL Adobe Workfront Fusion Google Drive] le permiten supervisar, buscar, crear, actualizar, eliminar y administrar sus archivos, carpetas o unidades compartidas en su [!DNL Google Drive].
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 788f4e1b-d774-45ad-a8be-b16922c1d5dc
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '2489'
ht-degree: 9%

---

# Módulos de [!DNL Google Drive]

Los módulos [!DNL Adobe Workfront Fusion] [!DNL Google Drive] le permiten supervisar, buscar, crear, actualizar, eliminar y administrar sus archivos, carpetas o unidades compartidas en su [!DNL Google Drive].

En un escenario de [!DNL Adobe Workfront Fusion], puede conectar su cuenta de [!DNL Google Drive] a varias aplicaciones y servicios de terceros.

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

## Información de API de Google Drive

El conector de Google Drive utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL básica</td> 
   <td> https://www.googleapis.com/drive/v3</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> v3 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>v4.1.22</td> 
  </tr>
 </tbody> 
 </table>



## Conectar [!DNL Google Drive] a [!DNL Workfront Fusion]

Si es un usuario de [!DNL @gmail.com] o [!DNL @googlemail.com], debe crear un cliente de OAuth en [the [!DNL Google Cloud Platform]](https://console.developers.google.com/projectselector2/apis/dashboard?supportedpurview=project) para obtener [!UICONTROL Client ID] y [!UICONTROL Client Secret].

Para obtener instrucciones paso a paso sobre cómo crear el cliente OAuth (y obtener [!UICONTROL Client ID] y [!UICONTROL Client Secret]), consulte [Conectarse [!DNL Adobe Workfront Fusion] a [!DNL Google Services] mediante un cliente OAuth personalizado](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md).

Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Drive] a [!UICONTROL Workfront Fusion], consulte [Crear una conexión con [!UICONTROL Adobe Workfront Fusion]: instrucciones básicas](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

## Módulos de [!DNL Google Drive] y sus campos

Al configurar módulos de [!DNL Google Drive], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Google Drive] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)



* [Activadores](#triggers)
* [Acciones](#actions)

### Activadores

* [[!UICONTROL Watch Files In Folder]](#watch-files-in-folder)
* [[!UICONTROL Watch All Files]](#watch-all-files)
* [[!UICONTROL Watch shared files]](#watch-shared-files)
* [[!UICONTROL Watch Comments]](#watch-comments)

#### [!UICONTROL Watch Files In Folder]

Recupera detalles del archivo cuando se agrega o modifica un archivo en la carpeta especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection] </td>
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Drive] a [!DNL Workfront Fusion], vea <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr>
    <td>[!UICONTROL Select the folder to be watched]</td>
    <td >Seleccione la carpeta de la unidad en la que desea inspeccionar los archivos.</td>
  </tr> 
  <tr> 
    <td>[!UICONTROL What files to watch]</td>
   <td> <p>Seleccione el tipo de archivos que desea inspeccionar.</p> 
    <ul> 
     <li>[!UICONTROL All]</li> 
     <li>[!DNL Google Documents]</li> 
     <li>[!DNL Google Spreadsheets]</li> 
     <li>[!DNL Google Slides]</li> 
     <li>[!DNL Google Drawings]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
    <td >[!UICONTROL Convert [!DNL Google Documents] archivos para formatear]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Documents].</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Spreadsheets] archivos para formatear]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Spreadsheets].</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Slides] archivos para formatear]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Slides].</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Drawings] archivos para formatear]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Drawings].</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Watch]</td>
    <td>Seleccione si desea inspeccionar los nuevos archivos y todos los cambios, o sólo los nuevos.</td>
  </tr> 
  <tr> 
    <td>[!UICONTROL Maximum number of downloaded files]</td>
    <td>Establezca el número máximo de resultados que [!DNL Workfront Fusion] descargará durante un ciclo (el número de repeticiones por ejecución de escenario).</td>
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch All Files]

Recupera detalles del archivo cuando se agrega o modifica un archivo de su [!DNL Google Drive].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Drive] a [!DNL Workfront Fusion], vea <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL What files to watch]</td> 
   <td> <p>Seleccione el tipo de archivos que desea inspeccionar.</p> 
    <ul> 
     <li>[!UICONTROL All]</li> 
     <li>[!DNL Google Documents]</li> 
     <li>[!DNL Google Spreadsheets]</li> 
     <li>[!DNL Google Slides]</li> 
     <li>[!DNL Google Drawings]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
    <td >[!UICONTROL Convert [!DNL Google Documents] archivos para formatear]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Documents].</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Spreadsheets] archivos para formatear]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Spreadsheets].</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Slides] archivos para formatear]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Slides].</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Drawings] archivos para formatear]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Drawings].</td>
  </tr>  
  <tr> 
   <td>[!UICONTROL Watch]</td> 
   <td>Seleccione si desea inspeccionar los nuevos archivos y todos los cambios, o sólo los nuevos.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of downloaded files]</td> 
   <td>Establezca el número máximo de resultados que [!DNL Workfront Fusion] descargará durante un ciclo (el número de repeticiones por ejecución de escenario).</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch shared files]

Déclencheur cuando se comparte un nuevo archivo con usted o cuando se actualiza un archivo compartido existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Drive] a [!DNL Workfront Fusion], vea <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Select the folder to be watched]</td> 
   <td>Seleccione la carpeta compartida en la que desea inspeccionar los archivos.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL What files to watch]</td> 
   <td> <p>Seleccione el tipo de archivos que desea inspeccionar.</p> 
    <ul> 
     <li>[!UICONTROL All]</li> 
     <li>[!DNL Google Documents]</li> 
     <li>[!DNL Google Spreadsheets]</li> 
     <li>[!DNL Google Slides]</li> 
     <li>[!DNL Google Drawings]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
    <td >[!UICONTROL Convert [!DNL Google Documents] archivos para formatear]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Documents].</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Spreadsheets] archivos para formatear]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Spreadsheets].</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Slides] archivos para formatear]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Slides].</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Drawings] archivos para formatear]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Drawings].</td>
  </tr> 
  <tr> 
   <td>[!UICONTROL Watch]</td> 
   <td>Seleccione si desea inspeccionar los nuevos archivos y todos los cambios, o sólo los nuevos.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of downloaded files]</td> 
   <td>Establezca el número máximo de resultados que [!DNL Workfront Fusion] descargará durante un ciclo (el número de repeticiones por ejecución de escenario).</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Comments]

Déclencheur cuando se agrega o modifica un comentario en el archivo seleccionado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Drive] a [!DNL Workfront Fusion], vea <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File]</td> 
   <td>Seleccione el archivo que desea inspeccionar en busca de comentarios.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Watch]</td> 
   <td>Seleccione si desea inspeccionar todos los cambios o sólo los comentarios nuevos</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned comments]</td> 
   <td>Establezca el número máximo de comentarios que [!DNL Workfront Fusion] devolverá durante un ciclo (el número de repeticiones por ejecución de escenario).</td> 
  </tr> 
 </tbody> 
</table>

### Acciones

* [[!UICONTROL Upload a File]](#upload-a-file)
* [[!UICONTROL Update a File]](#update-a-file)
* [[!UICONTROL Copy a File]](#copy-a-file)
* [[!UICONTROL Delete a File]](#delete-a-file)
* [[!UICONTROL Move a File/Folder to Trash]](#move-a-filefolder-to-trash)
* [[!UICONTROL Get a file]](#get-a-file)
* [[!UICONTROL Search for Files/Folders]](#search-for-filesfolders)
* [[!UICONTROL Create a Folder]](#create-a-folder)
* [[!UICONTROL Get a share link]](#get-a-share-link)

#### [!UICONTROL Upload a File]

Sube un archivo a su [!DNL Google Drive].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Drive] a [!DNL Workfront Fusion], vea <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!DNL Destination]</td> 
   <td> <p>Seleccione el destino en el que desea cargar un archivo.</p> 
    <ul> 
     <li>[!DNL My Drive]</li> 
     <li>[!DNL Shared with Me]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Target folder]</td> 
   <td>Seleccione la carpeta en la que desea cargar un archivo. </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td>Seleccione si desea utilizar un archivo transferido desde un módulo anterior o si desea asignar el archivo manualmente.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File name]</td> 
   <td>Seleccione el nombre del archivo. Esta opción está disponible si selecciona "[!UICONTROL Map]" en el campo [!UICONTROL source file].</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Data]</td> 
   <td>Seleccione el archivo de datos que desea cargar. Esta opción está disponible si selecciona "[!UICONTROL Map]" en el campo [!UICONTROL source file].</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Title]</td> 
   <td>Escriba un título para el nuevo archivo.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert a file]</td> 
   <td>Al habilitar esta opción, el módulo podrá convertir archivos al formato [!DNL Google] correspondiente.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a File]

Actualiza los metadatos o el contenido de un archivo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Drive] a [!DNL Workfront Fusion], vea <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination]</td> 
   <td> <p>Seleccione el destino en el que desea cargar un archivo.</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared with Me]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Move to a folder]</td> 
   <td>Si desea mover el archivo a una carpeta diferente, seleccione la carpeta en la que desea mover el archivo.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>Asigne el ID del archivo que desea actualizar.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Title]</td> 
   <td>Escriba un título para el archivo actualizado.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Change a file content]</td> 
   <td>Seleccione si desea reemplazar el contenido del archivo.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td>Seleccione si desea utilizar un archivo transferido desde un módulo anterior o si desea asignar el archivo manualmente. Este campo está disponible si ha seleccionado cambiar el contenido del archivo en el campo anterior.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File name]</td> 
   <td>Seleccione el nombre del archivo. Esta opción está disponible si selecciona "[!UICONTROL Map]" en el campo [!UICONTROL source file].</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Data]</td> 
   <td>Seleccione el archivo de datos que desea cargar. Esta opción está disponible si selecciona "[!UICONTROL Map]" en el campo [!UICONTROL source file].</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Copy a File]

Copia un archivo en la nueva ubicación.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Drive] a [!DNL Workfront Fusion], vea <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination]</td> 
   <td> <p>Seleccione el destino en el que desea cargar un archivo.</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared with Me]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Target folder]</td> 
   <td>Seleccione la carpeta donde se encuentra el archivo que desea copiar/</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>Asigne el ID del archivo que desea actualizar.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL The name of the copy]</td> 
   <td>Escriba un título para el nuevo archivo. Deje este campo en blanco si no desea cambiar el nombre del archivo original.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a File]

Elimina permanentemente un archivo o carpeta.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Drive] a [!DNL Workfront Fusion], vea <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>Asigne el ID del archivo que desea eliminar.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move a File/Folder to Trash]

Mueve un archivo o una carpeta a la papelera.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Drive] a [!DNL Workfront Fusion], vea <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>Asigne el ID del archivo que desea mover a la papelera.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a file]

Recupera el archivo con el ID especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Drive] a [!DNL Workfront Fusion], vea <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Documents] archivos para formatear]</td> 
   <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Documents].</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Spreadsheets] archivos para formatear]</td> 
   <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Spreadsheets].</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Slides] archivos para formatear]</td> 
   <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Slides].</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Drawings] archivos para formatear]</td> 
   <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Drawings].</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>Asigne el ID del archivo que desea recuperar.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search for Files/Folders]

Busca archivos o carpetas según los criterios de búsqueda.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Drive] a [!DNL Workfront Fusion], vea <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination]</td> 
   <td> <p>Seleccione el destino en el que desea buscar.</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared with Me]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL List a folder]</td> 
   <td>Desplácese hasta la carpeta en la que desee buscar los archivos o carpetas.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Retrieve]</td> 
   <td> <p> Seleccione si desea buscar archivos, carpetas o ambos.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Search]</p> </td> 
   <td> <p>Seleccione el tipo de búsqueda que desea realizar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Search within file/folder names]</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Query]</strong> </p> <p>Introduzca una parte del nombre de archivo o el nombre completo del archivo (incluido el sufijo) que desee buscar.</p> </li> 
       <li> <p><strong>[!UICONTROL Search Options]</strong> </p> <p>Seleccione si desea buscar el término exacto o si desea buscar nombres que contengan el término de búsqueda.</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL Fulltext] búsqueda</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Query]</strong> </p> <p>Escriba cualquier término de búsqueda que quiera buscar en su [!DNL Google Drive].</p> </li> 
      </ul> </li> 
     <li> <p><strong>Introducir consulta de búsqueda personalizada</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Query]</strong> </p> <p>Introduzca la consulta de búsqueda personalizada. Para obtener más información, consulte la sección [!UICONTROL Search for Files] de este artículo.</p> </li> 
       <li> <p><strong>Agregar la carpeta seleccionada arriba a la consulta</strong> </p> <p>Busca la carpeta en la colección primaria. Esto encuentra todos los archivos y carpetas ubicados directamente en la carpeta seleccionada anteriormente.</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned results]</td> 
   <td>Establezca el número máximo de archivos o carpetas que [!DNL Workfront Fusion] devolverá durante un ciclo de ejecución.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Continue the execution of the route even if the module returns no results]</td> 
   <td>Active esta opción para asegurarse de que el escenario no se detiene si el módulo no devuelve resultados.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Folder]

Crea una carpeta en la ubicación especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Drive] a [!DNL Workfront Fusion], vea <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination]</td> 
   <td> <p>Seleccione el destino en el que desea cargar un archivo.</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared with Me]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL New folder location]</td> 
   <td>Vaya a la ubicación en la que desea crear una carpeta nueva.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL The name of the new folder]</td> 
   <td>Escriba un nombre para la carpeta que está creando.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Share folder]</td> 
   <td>Seleccione esta opción si desea compartir la carpeta con alguien que tenga el vínculo [!UICONTROL Share]. De lo contrario, el vínculo compartido solo es para el propietario.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a share link]

Recupera el vínculo compartido de un archivo en Google Drive.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Drive] a [!DNL Workfront Fusion], vea <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>Asigne el ID del archivo para el que desea obtener el vínculo compartido.</td> 
  </tr> 
 </tbody> 
</table>

## Resolución de problemas

### No se puede cargar o actualizar un archivo

Cuando falla la carga o actualización de un archivo, se dan varias situaciones:

* El archivo cargado es demasiado grande y supera el límite máximo de tamaño de archivo permitido para el plan [!DNL Google Drive] o ha excedido el límite de almacenamiento de [!DNL Google Drive]. Puede actualizar su plan de almacenamiento o eliminar los archivos existentes del servicio [!DNL Google Drive].
* La carpeta seleccionada en la que se iba a cargar el archivo ya no existe. El escenario se detiene y es necesario volver a seleccionar una carpeta de destino.

## Buscar archivos

En el módulo Mostrar archivos en una carpeta puede utilizar su propia consulta, que consta de estas partes:

* **[!UICONTROL Field]**: atributo del archivo que se está buscando, por ejemplo, el atributo `name` del archivo.

* **[!UICONTROL Operator]**: prueba que se realiza en los datos para proporcionar una coincidencia, por ejemplo, `contains`.

* **[!UICONTROL Value]**: el contenido del atributo que se prueba, por ejemplo, el nombre del archivo `My cool document`.

Combine cláusulas con las conjunciones `and` o `or` y anule la consulta con `not`.

* [Campos](#fields)
* [Tipos de valor](#value-types)
* [Operadores](#operators)
* [Ejemplos](#examples)

### Campos

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Campo </th> 
   <th>Tipo de valor </th> 
   <th>Operadores</th> 
   <th> <p> Descripción</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td><code>[!UICONTROL title]</code></td> 
   <td>cadena</td> 
   <td><code>contains</code><sup>1</sup>, <code>=</code>, <code>!=</code></td> 
   <td> <p> Nombre del archivo.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL fullText]</code> </td> 
   <td>cadena </td> 
   <td><code>contains</code><sup>2, 3</sup> </td> 
   <td> <p> Texto completo del archivo, incluido el nombre, la descripción, el contenido y el texto indexable.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL mimeType]</code> </td> 
   <td> cadena</td> 
   <td><code>contains</code>, <code>=</code>, <code>!=</code></td> 
   <td> <p> Tipo MIME del archivo.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL modifiedDate]</code> </td> 
   <td> fecha<sup>4</sup></td> 
   <td><code> &lt;=</code>, <code>&lt;</code>, <code>=</code>, <code>!=</code>, <code>></code>, <code>>=</code></td> 
   <td> <p> Fecha de la última modificación del archivo.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL lastViewedByMeDate]</code> </td> 
   <td> fecha<sup>4</sup></td> 
   <td><code>&lt;=</code>, <code>&lt;</code>, <code>=</code>, <code>!=</code>, <code>></code>, <code>>=</code></td> 
   <td> <p> Fecha en la que el usuario vio un archivo por última vez.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL trashed]</code></td> 
   <td>booleano </td> 
   <td><code>=</code>, <code>!=</code></td> 
   <td> <p> Si el archivo está en la papelera o no.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL starred]</code></td> 
   <td>booleano </td> 
   <td><code>=</code>, <code>!=</code></td> 
   <td> <p>Si el archivo está marcado con estrellas o no.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL parents]</code></td> 
   <td>colección </td> 
   <td><code>in </code> </td> 
   <td> <p>Si la colección [!UICONTROL parents] contiene el identificador especificado.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL owners]</code></td> 
   <td>colección </td> 
   <td><code>in </code> </td> 
   <td> <p>Usuarios que son propietarios del archivo.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL writers]</code></td> 
   <td>colección </td> 
   <td><code>in </code> </td> 
   <td> <p>Usuarios que tienen permiso para modificar el archivo.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL readers] </code> </td> 
   <td>colección </td> 
   <td><code>in </code> </td> 
   <td> <p>Usuarios que tienen permiso para leer el archivo.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL sharedWithMe]</code> </td> 
   <td>booleano </td> 
   <td><code>=</code>, <code>!=</code></td> 
   <td> <p> Archivos que se encuentran en la colección "Compartido conmigo" del usuario.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL properties] </code> </td> 
   <td>colección</td> 
   <td><code>has </code> </td> 
   <td> <p> Propiedades públicas del archivo personalizado.</p> </td> 
  </tr> 
 </tbody> 
</table>

Tenga en cuenta lo siguiente sobre los operadores en estos campos:

* El operador `contains` solo realiza la coincidencia de prefijos para `title`.

  Por ejemplo, el título &quot;HelloWorld&quot; coincide con `title contains 'Hello'` pero no con `title contains 'World'`.

* El operador `contains` solo realiza coincidencias en tokens de cadena completos para `fullText`.

  Por ejemplo, si el texto completo de un documento contiene la cadena &quot;HelloWorld&quot;, solo la consulta `fullText contains 'HelloWorld'` devuelve un resultado. Consultas como `fullText contains 'Hello'` no arrojarían resultados en este escenario.

* El operador `contains` coincide con una frase alfanumérica exacta si está entre comillas dobles.

  Por ejemplo, si el `fullText` de un documento contiene la cadena &quot;Hello there world&quot;, la consulta `fullText contains '"Hello there"'` devuelve un resultado, pero la consulta `fullText contains '"Hello world"'` no.

  Además, como la búsqueda es alfanumérica, si el `fullText` de un documento contiene la cadena &quot;Hello_world&quot;, la consulta `fullText contains '"Hello world"'` devuelve un resultado.

* Actualmente, los campos de fecha `type` no son comparables entre sí, solo con fechas constantes.

### Tipos de valor

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Tipo de valor</th> 
   <th> <p> Notas</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>Cadena </td> 
   <td> <p>Rodear con comillas simples '. Omitir comillas simples en consultas con <code>\'</code>, p. ej.,<code> 'Valentine\'s Day'</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>Booleano </td> 
   <td> <p><code>true </code>o <code>false</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>Fecha </td> 
   <td> <p>formato RFC 3339, la zona horaria predeterminada es UTC; p. ej., <code>2012-06-04T12:00:00-08:00</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Operadores

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Operador </th> 
   <th> <p>Notas</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td><code>contains</code></td> 
   <td> <p>El contenido de una cadena está presente en la otra.</p> </td> 
  </tr> 
  <tr> 
   <td><code>=</code> </td> 
   <td> <p> El contenido de una cadena o booleano es igual al otro.</p> </td> 
  </tr> 
  <tr> 
   <td><code>!=</code> </td> 
   <td> <p> El contenido de una cadena o booleano no es igual al otro.</p> </td> 
  </tr> 
  <tr> 
   <td><code>&lt;</code> </td> 
   <td> <p> Una fecha es anterior a otra.</p> </td> 
  </tr> 
  <tr> 
   <td><code>&lt;=</code> </td> 
   <td> <p> Una fecha es anterior o igual a otra.</p> </td> 
  </tr> 
  <tr> 
   <td><code>></code> </td> 
   <td> <p> Una fecha es posterior a otra.</p> </td> 
  </tr> 
  <tr> 
   <td><code>>=</code> </td> 
   <td> <p> Una fecha es posterior o igual a otra.</p> </td> 
  </tr> 
  <tr> 
   <td><code>in </code> </td> 
   <td> <p>Un elemento está contenido dentro de una colección.</p> </td> 
  </tr> 
  <tr> 
   <td><code>and </code> </td> 
   <td> <p>Devuelve archivos que coinciden con ambas cláusulas.</p> </td> 
  </tr> 
  <tr> 
   <td><code>or </code> </td> 
   <td> <p>Devolver archivos que coincidan con cualquiera de las cláusulas.</p> </td> 
  </tr> 
  <tr> 
   <td><code>not </code> </td> 
   <td> <p>Anula una cláusula de búsqueda.</p> </td> 
  </tr> 
  <tr> 
   <td><code>has </code> </td> 
   <td> <p>Una colección contiene un elemento que coincide con los parámetros.</p> </td> 
  </tr> 
 </tbody> 
</table>

En el caso de las cláusulas compuestas, puede utilizar paréntesis para agrupar cláusulas. Por ejemplo:
`modifiedDate > '2012-06-04T12:00:00' and (mimeType contains 'image/' or mimeType contains 'video/')` Esta búsqueda devuelve todos los archivos con un tipo MIME de imagen o vídeo cuya última modificación fue después del 4 de junio de 2012. Dado que los operadores `and` y `or` se evalúan de izquierda a derecha, sin paréntesis, el ejemplo anterior devuelve solamente las imágenes modificadas después del 4 de junio de 2012, pero devuelve todos los vídeos, incluso los anteriores al 4 de junio de 2012.

### Ejemplos

Todos los ejemplos de esta página muestran el parámetro sin codificar `<q>q</q>`, donde `title = 'hello'` está codificado como `title+%3d+%27hello%27`. Las bibliotecas de cliente gestionan esta codificación automáticamente.

* Buscar archivos con el nombre &quot;hello&quot;
  <pre>title = 'hello'</pre>
* Buscar carpetas utilizando el tipo MIME específico de la carpeta
  <pre>mimeType = 'application/vnd.google-apps.folder'</pre>
* Buscar archivos que no sean carpetas
  <pre>mimeType!= 'application/vnd.google-apps.folder'</pre>
* Busque archivos con un nombre que contenga las palabras &quot;hello&quot; y &quot;bye&quot;
  <pre>el título contiene 'hello' y [!UICONTROL name] 'bye'</pre>
* Busque archivos con un nombre que no contenga la palabra &quot;hello&quot;
  <pre>no el título contiene 'hello'</pre>
* Busque archivos que contengan la palabra &quot;hello&quot; en el contenido
  <pre>fullText contiene 'hello'</pre>
* Busque archivos que no contengan la palabra &quot;hello&quot; en el contenido
  <pre>no fullText contiene 'hello'</pre>
* Busque archivos que contengan la frase exacta &quot;hello world&quot; en el contenido
  <pre>fullText contiene 'hello world''fullText contiene 'hello_world'</pre>
* Busque archivos con una consulta que contenga el carácter &quot;\&quot; (por ejemplo, &quot;\authors&quot;)
  <pre>fullText contiene '\\authors'</pre>
* Buscar archivos que pueda escribir el usuario `test@example.org`
  <pre>'test@example.org' en [!DNL writers]</pre>
* Busque el identificador `1234567` en la colección `parents`. Esto encuentra todos los archivos y carpetas ubicados directamente en la carpeta cuyo identificador es `1234567`.
  <pre>'1234567' en [!UICONTROL parents]</pre>
* Busque el ID de alias `appDataFolder` en la colección `parents`. Esto encuentra todos los archivos y carpetas ubicados directamente bajo la [carpeta de datos de la aplicación](https://developers.google.com/drive/api/v2/appdata).
  <pre>'appDataFolder' en elementos primarios</pre>
* Busque archivos que puedan escribir los usuarios `test@example.org` y `test2@example.org`
  <pre>'test@example.org' en escritores y 'test2@example.org' en escritores</pre>
* Busque archivos que contengan el texto &quot;importante&quot; y que se encuentren en la papelera
  <pre>fullText contiene 'important' y trashed = true</pre>
* Buscar archivos modificados después del 4 de junio de 2012
  <pre>modifiedDate &gt; '2012-06-04T12:00:00' // La zona horaria predeterminada es UTC</pre><pre>modifiedDate &gt; '2012-06-04T12:00:00-08:00'</pre>
* Busque archivos compartidos con el usuario autorizado con &quot;hello&quot; en el nombre
  <pre>sharedWithMe y el título contiene 'hello'</pre>
* Busque archivos con una [propiedad de archivo personalizada](https://developers.google.com/drive/api/v2/properties) denominada `additionalID` con el valor `8e8aceg2af2ge72e78`.
  <pre>properties tiene { key='additionalID' and value='8e8aceg2af2ge72e78' and visibility='PRIVATE' }</pre>

El Source de esta guía es [[!DNL Google Drive] documentation](https://developers.google.com/drive/api/v2/search-shareddrives).
