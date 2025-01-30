---
title: Módulos de Dropbox
description: En un escenario de  [!DNL Adobe Workfront Fusion] , puede automatizar los flujos de trabajo que utilizan Dropbox, así como conectarlo a varias aplicaciones y servicios de terceros. Esto le permite automatizar actividades como la monitorización, la búsqueda, la recuperación, la enumeración, y la creación y edición de archivos y carpetas en el Dropbox.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 29ce5940-4d71-4719-ab5e-f03c44b28c8c
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '2876'
ht-degree: 88%

---

# Módulos de [!DNL Dropbox]

En un escenario de [!DNL Adobe Workfront Fusion], puede automatizar los flujos de trabajo que usan [!UICONTROL Dropbox] o [!DNL Dropbox Business], así como conectarlo a varias aplicaciones y servicios de terceros. Esto le permite automatizar actividades como la supervisión, la búsqueda, la recuperación, la inclusión, la creación y edición de archivos y carpetas en su [!UICONTROL Dropbox].

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

* Para usar módulos de [!DNL Dropbox], debe tener una cuenta de [!DNL Dropbox].

>[!IMPORTANT]
>
>Dropbox debe aprobar las aplicaciones con más de 50 usuarios.
>
>Para obtener más información, busque “Aprobación de producción” en la guía para desarrolladores de Dropbox.

## Información de API del Dropbox

El conector del Dropbox utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL básica</td> 
   <td> https://api.dropboxapi.com/2    </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> 2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td><ul><li><p>Dropbox</p><p>Versión 5.3.9</p></li><li><p>Dropbox Business</p><p>Versión 1.0.12</p></li></ul></td> 
  </tr>
 </tbody> 
 </table>


## Crear una conexión a [!DNL Dropbox]

Para crear una conexión para los módulos de [!DNL Dropbox]:

1. Haga clic en **[!UICONTROL Add]** junto al cuadro Conexión.

1. Rellene los campos siguientes:

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>Introduzca un nombre para esta conexión.</p>
        </td>
        <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>Seleccione si esta conexión es para un entorno de producción o de no producción.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>Seleccione si desea conectarse a una cuenta de servicio o a una personal.</td>
        </tr>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Escriba su [!UICONTROL Dropbox] [!UICONTROL Client ID]. </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Escriba su [!DNL Dropbox] [!UICONTROL Client Secret]. </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Account Type]</td>
        <td>Seleccione si desea conectarse a una cuenta personal o a una cuenta de empresa de Dropbox (Dropbox Business).</td>
        </tr>
      </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continue]** para guardar la conexión y volver al módulo.Módulos de ## [!DNL Dropbox] y sus campos

## Módulos de [!DNL Dropbox] y sus campos

Al configurar módulos de [!DNL Dropbox], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Dropbox] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Módulos de activador](#trigger-modules)
* [Módulos para obtener archivos y carpetas de  [!DNL Dropbox] ](#modules-for-getting-dropbox-files-and-folders)
* [Módulos para crear y editar archivos y carpetas de  [!DNL Dropbox] ](#modules-for-creating-and-editing-dropbox-files-and-folders)
* [Otros módulos](#other-modules)

### Módulos de activador

#### [!UICONTROL Watch Files]

Este módulo de tipo Activador devuelve los detalles del archivo cuando se modifica el archivo de una carpeta especificada.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Dropbox] a [!DNL Workfront Fusion], consulte <a href="#create-a-connection-to-dropbox" class="MCXref xref">Crear una conexión con [!DNL Dropbox]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Seleccione la carpeta en la que desea ver los cambios.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Watch also subfolders]</td> 
   <td> <p> Habilite esta opción para supervisar también las subcarpetas de la carpeta seleccionada en busca de archivos modificados.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit] </td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Módulos para obtener archivos y carpetas de [!DNL Dropbox]

* [[!UICONTROL Search Files/Folders]](#search-filesfolders)
* [[!UICONTROL Download a File]](#download-a-file)
* [[!UICONTROL Get a Folder Metadata]](#get-a-folder-metadata)
* [[!UICONTROL List All Files/Subfolders in a Folder]](#list-all-filessubfolders-in-a-folder)
* [[!UICONTROL List File Revisions]](#list-file-revisions)

#### [!UICONTROL Search Files/Folders]

Este módulo de búsqueda busca registros en un objeto de [!DNL Dropbox] que coincidan con la consulta de búsqueda especificada.

Puede asignar esta información en módulos subsiguientes en el escenario.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Dropbox] a [!DNL Workfront Fusion], consulte <a href="#create-a-connection-to-dropbox" class="MCXref xref">Crear una conexión con [!DNL Dropbox]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search] </td> 
   <td> <p>Introduzca el término de búsqueda.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Seleccione la carpeta en la que desea buscar. Este módulo busca en todo [!DNL Dropbox] si no selecciona ninguna carpeta.</p> </td> 
  </tr> 
  <tr> 
   <td>Estado del archivo</td> 
   <td> <p> Seleccione el estado del archivo para restringir la búsqueda al estado del archivo seleccionado.</p> </td> 
  </tr> 
  <tr> 
   <td>Categorías de archivo</td> 
   <td> <p> Seleccione las categorías de archivo para restringir la búsqueda a las categorías seleccionadas.</p> </td> 
  </tr> 
  <tr> 
   <td>Extensiones de archivo</td> 
   <td> <p> Elija las extensiones de archivo que desea buscar.</p> </td> 
  </tr> 
  <tr> 
   <td>Límite </td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download a File]

Este módulo de acción descarga un archivo de una carpeta.

Especifique el archivo y su ubicación.

El módulo devuelve el ID del archivo y cualquier campo asociado, junto con cualquier campo personalizado y valor al que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

>[!NOTE]
>
>Este módulo es útil para proporcionar archivos a los módulos posteriores.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Dropbox] a [!DNL Workfront Fusion], consulte <a href="#create-a-connection-to-dropbox" class="MCXref xref">Crear una conexión con [!DNL Dropbox]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>Forma de seleccionar archivos</td> 
   <td> <p> Seleccione si desea asignar la ruta de acceso del archivo o seleccione el archivo manualmente.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Ruta de archivo / Archivo</p> </td> 
   <td> <p style="font-weight: bold;">Ruta de archivo</p> <p>Introduzca o asigne la ruta de destino al archivo.</p> <p style="font-weight: bold;">Archivo</p> <p>Seleccione el archivo en el menú.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Folder Metadata]

Este módulo de acción recupera los detalles de la carpeta compartida.

Especifique el ID de la carpeta.

El módulo devuelve el ID de la carpeta y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Dropbox] a [!DNL Workfront Fusion], consulte <a href="#create-a-connection-to-dropbox" class="MCXref xref">Crear una conexión con [!DNL Dropbox]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>Identificador de carpeta compartida</td> 
   <td> <p> Introduzca o asigne el ID de la carpeta sobre la que desea recuperar los detalles.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List All Files/Subfolders in a Folder]

Este módulo de acción enumera los archivos o carpetas de una carpeta concreta.

Especifique el ID de la carpeta.

El módulo devuelve los ID de los archivos o carpetas y cualquier campo asociado, junto con cualquier campo personalizado y valor al que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Dropbox] a [!DNL Workfront Fusion], consulte <a href="#create-a-connection-to-dropbox" class="MCXref xref">Crear una conexión con [!DNL Dropbox]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>Lista </td> 
   <td> <p>Seleccione si desea recuperar archivos o carpetas.</p> </td> 
  </tr> 
  <tr> 
   <td>Mostrar solo los archivos descargables</td> 
   <td> <p> Active esta opción para devolver solo los archivos descargables. Algunos tipos de archivos, como los documentos de Google, no se pueden descargar.</p> </td> 
  </tr> 
  <tr> 
   <td>Carpeta </td> 
   <td> <p>Introduzca o asigne la carpeta de la que desea recuperar archivos o carpetas.</p> </td> 
  </tr> 
  <tr> 
   <td>Límite </td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo enumere durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List File Revisions]

Este módulo de acción recupera todas las revisiones de archivo (un historial de versiones) de un archivo concreto.\
Especifique el ID del archivo.

El módulo devuelve cualquier campo estándar asociado con el registro, junto con los campos y valores personalizados a los que accede la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Dropbox] a [!DNL Workfront Fusion], consulte <a href="#create-a-connection-to-dropbox" class="MCXref xref">Crear una conexión con [!DNL Dropbox]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>Forma de seleccionar archivos</td> 
   <td> <p> Seleccione si desea asignar la ruta de acceso del archivo o seleccione el archivo manualmente.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Ruta de archivo / Archivo</p> </td> 
   <td> <p style="font-weight: bold;">Ruta de archivo</p> <p>Introduzca o asigne la ruta de destino al archivo.</p> <p style="font-weight: bold;">Archivo</p> <p>Seleccione el archivo en el menú.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Límite</p> </td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo enumere durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Módulos para crear y editar archivos y carpetas de [!DNL Dropbox]

* [[!UICONTROL Upload] un archivo](#upload-a-file)
* [[!UICONTROL Create a Folder]](#create-a-folder)
* [[!UICONTROL Create/Overwrite a Text File]](#createoverwrite-a-text-file)
* [[!UICONTROL Create/Update a Share Link]](#createupdate-a-share-link)
* [[!UICONTROL Restore a File]](#restore-a-file)
* [[!UICONTROL Move a File/Folder]](#move-a-filefolder)
* [[!UICONTROL Rename a File/Folder]](#rename-a-filefolder)
* [[!UICONTROL Delete a File/Folder]](#delete-a-filefolder)

#### [!UICONTROL Upload a File]

Este módulo de acción carga un archivo en una carpeta.

Especifique información como la ubicación del archivo, el archivo que desea cargar y un nuevo nombre opcional para el archivo.

El módulo devuelve el identificador del archivo y cualquier campo asociado, junto con cualquier otro campo personalizado y valor al que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Dropbox] a [!DNL Workfront Fusion], consulte <a href="#create-a-connection-to-dropbox" class="MCXref xref">Crear una conexión con [!DNL Dropbox]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder]</td> 
   <td> <p> Seleccione la carpeta de su [!DNL Dropbox] en la que desee cargar el archivo.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Source File]</p> </td> 
   <td> <p>Escriba o asigne el archivo que desea añadir a la carpeta de [!DNL Dropbox] seleccionada anteriormente.</p> <p style="font-weight: bold;">[!UICONTROL File name]</p> <p>Introduzca o asigne el nombre del archivo, incluida su extensión.</p> <p style="font-weight: bold;">[!UICONTROL File data]</p> <p>Escriba o asigne los datos del archivo (del módulo anterior, como [!UICONTROL Google Drive] &gt;[!UICONTROL Get a File)]).</p> <p>Nota: el tamaño máximo del archivo cargado es de 150 MB.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Overwrite an existing file]</td> 
   <td> <p> Active esta opción para reemplazar el archivo existente con el nuevo archivo. Si esta opción se deja deshabilitada, se cambiará el nombre del archivo cargado.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Folder]

Este módulo de acción crea una nueva carpeta.

Especifique la ruta y el nombre de la carpeta.

El módulo devuelve el ID de la carpeta y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Dropbox] a [!DNL Workfront Fusion], consulte <a href="#create-a-connection-to-dropbox" class="MCXref xref">Crear una conexión con [!DNL Dropbox]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder Name] </td> 
   <td> <p>Introduzca el nombre de la nueva carpeta.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Folder]</p> </td> 
   <td> <p>Introduzca o asigne la ruta donde desea crear una nueva carpeta.</p> <p>Nota:   <p>Si usa una cuenta de [!DNL Dropbox Business] (con espacios de equipo), debe quitar la barra diagonal <code>/</code> o no hacer clic en <strong>[!UICONTROL Click here] para elegir la carpeta </strong> y crear una carpeta de equipo en la raíz.</p> <p>Si no se quita la barra oblicua, se devuelve un error <code>[409] path/malformed_path/..</code>.</p> </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Auto rename]</td> 
   <td> <p> Active esta opción para cambiar el nombre de la nueva carpeta, si ya existe una carpeta con el mismo nombre en la ubicación de destino.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create/Overwrite a Text File]

Este módulo de acción crea un archivo DOC o sobrescribe el contenido de uno existente.

Especifique el archivo de origen y la carpeta.

El módulo devuelve el ID de la carpeta y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Dropbox] a [!DNL Workfront Fusion], consulte <a href="#create-a-connection-to-dropbox" class="MCXref xref">Crear una conexión con [!DNL Dropbox]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Select to]</td> 
   <td> <p> Seleccione si desea crear o sobrescribir un archivo DOC.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Seleccione la ubicación de destino en la que desea crear un archivo.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Source File]</p> </td> 
   <td> <p>Escriba o asigne el archivo que desea añadir a la carpeta de [!DNL Dropbox].</p> <p style="font-weight: bold;">Nombre del archivo</p> <p>Introduzca el nombre del nuevo archivo DOC (sin extensión).</p> <p style="font-weight: bold;">Contenido de archivo</p> <p>Introduzca el contenido de texto del archivo DOC.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create/Update a Share Link]

Este módulo de acción crea un vínculo público a un archivo.

Especifique el archivo y la información sobre el vínculo.

El módulo devuelve el ID del vínculo y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Dropbox] a [!DNL Workfront Fusion], consulte <a href="#create-a-connection-to-dropbox" class="MCXref xref">Crear una conexión con [!DNL Dropbox]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Way of selecting files]</td> 
   <td> <p> Seleccione si desea asignar o introducir la ruta del archivo, o seleccione el archivo manualmente.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL File Path / File]</p> </td> 
   <td> <p style="font-weight: bold;">[!UICONTROL File Path]</p> <p>Introduzca o asigne la ruta de destino al archivo.</p> <p style="font-weight: bold;">[!UICONTROL File]</p> <p>Seleccione el archivo en el menú.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Requested Visibility]</p> </td> 
   <td> <p>Seleccione si el vínculo es público, de equipo o si está restringido con contraseña.</p> <p>Nota: las opciones [!UICONTROL Team only] y [!UICONTROL Access with password] solo están disponibles para los usuarios que tengan [!DNL Dropbox Pro] o una versión superior.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Link's Expiration Date]</td> 
   <td> <p> Introduzca la fecha y la hora en que caducará el vínculo y dejará de ser accesible. Si este campo se deja vacío, el vínculo no caducará. Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">Coerción de tipos en [!DNL Adobe Workfront Fusion]</a>.</p> <p>Nota: las opciones [!UICONTROL Team only] y [!UICONTROL Access with password] solo están disponibles para los usuarios que tienen [!UICONTROL Dropbox Pro] o versiones posteriores.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Link's Access Level]</p> </td> 
   <td> <p>Establezca el permiso para el destinatario del vínculo.</p> <p><strong>[!UICONTROL Viewer]</strong> Los usuarios que utilizan el vínculo pueden ver el contenido y realizar comentarios sobre él.</p> <p><strong>[!UICONTROL Editor]</strong> Los usuarios que utilizan el vínculo pueden editar, ver y comentar el contenido.</p> <p><strong>[!UICONTROL Max]</strong> Los usuarios que utilicen el vínculo reciben el nivel de acceso máximo al que puede establecer el vínculo.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Restore a File]

Este módulo de acción restaura una versión anterior de un archivo.

Especifique el archivo y el número de revisión que desee.

El módulo devuelve el ID de la versión y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Dropbox] a [!DNL Workfront Fusion], consulte <a href="#create-a-connection-to-dropbox" class="MCXref xref">Crear una conexión con [!DNL Dropbox]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Way of selecting files]</td> 
   <td> <p> Seleccione si desea asignar o introducir la ruta del archivo, o seleccione el archivo manualmente.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL File Path] / [!UICONTROL File]</p> </td> 
   <td> <p><strong>[!UICONTROL File Path]</strong> </p> <p>Introduzca o asigne la ruta de destino al archivo.</p> <p><strong>[!UICONTROL File]</strong> </p> <p>Seleccione el archivo en el menú.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Revision]</p> </td> 
   <td> <p>Introduzca o asigne el número de revisión de la revisión que desea restaurar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move a File/Folder]

Este módulo de acción mueve un archivo o carpeta a una ubicación diferente.

El usuario especifica el archivo o carpeta y cómo y dónde desea moverlo.

El módulo devuelve el ID del archivo o la carpeta y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Dropbox] a [!DNL Workfront Fusion], consulte <a href="#create-a-connection-to-dropbox" class="MCXref xref">Crear una conexión con [!DNL Dropbox]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Way of selecting files] </td> 
   <td> <p>Seleccione si desea asignar o introducir la ruta del archivo, o seleccione el archivo manualmente.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL File/Folder Path] / [!UICONTROL File/Folder]</p> </td> 
   <td> <p style="font-weight: bold;">[!UICONTROL File/Folder Path]</p> <p>Introduzca o asigne la ruta de destino al archivo o carpeta.</p> <p style="font-weight: bold;">[!UICONTROL File/Folder]</p> <p>Seleccione el archivo o la carpeta en el menú.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL To Folder]</p> </td> 
   <td> <p>Introduzca o asigne la ubicación de destino del archivo o carpeta.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL New Name]</p> </td> 
   <td> <p>Introduzca el nuevo nombre del archivo o la carpeta en la nueva ubicación.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Auto Rename]</p> </td> 
   <td> <p>Habilite esta opción para asegurarse de que si existe un archivo o una carpeta con el mismo nombre, el módulo cambie el nombre del nuevo archivo o carpeta agregando ([!UICONTROL NUMBER]) después del nombre del archivo o carpeta. De lo contrario, se sobrescribirá el archivo o la carpeta de la ubicación de destino.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Allow ownership transfer]</p> </td> 
   <td> <p>Habilite esta opción para permitir los movimientos por propietario, incluso si se produce una transferencia de propiedad del contenido que se está moviendo.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Rename a File/Folder]

Este módulo de acción cambia el nombre de un archivo o carpeta.

Especifique el archivo o la carpeta y el nuevo nombre.

El módulo devuelve el ID del archivo o la carpeta y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Dropbox] a [!DNL Workfront Fusion], consulte <a href="#create-a-connection-to-dropbox" class="MCXref xref">Crear una conexión con [!DNL Dropbox]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>Forma de seleccionar archivos</td> 
   <td> <p> Seleccione si desea asignar o introducir la ruta del archivo, o seleccione el archivo manualmente.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Ruta de archivo/carpeta / Archivo/carpeta</p> </td> 
   <td> <p style="font-weight: bold;">Ruta de archivo/carpeta</p> <p>Introduzca o asigne la ruta de destino al archivo o carpeta.</p> <p style="font-weight: bold;">Archivo/Carpeta</p> <p>Seleccione el archivo o la carpeta en el menú.</p> </td> 
  </tr> 
  <tr> 
   <td>Cambiar nombre </td> 
   <td> <p>Escriba [!UICONTROL target name] para el archivo, incluida la extensión de archivo.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a File/Folder]

Este módulo de acción elimina un archivo o una carpeta.

Especifique el archivo o la carpeta.

El módulo devuelve el identificador del registro y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Dropbox] a [!DNL Workfront Fusion], consulte <a href="#create-a-connection-to-dropbox" class="MCXref xref">Crear una conexión con [!DNL Dropbox]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Way of selecting files]</td> 
   <td> <p> Seleccione si desea asignar o introducir la ruta del archivo, o seleccione el archivo manualmente.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL File Path] / [!UICONTROL File]</p> </td> 
   <td> <p style="font-weight: bold;">[!UICONTROL File Path]</p> <p>Introduzca o asigne la ruta de destino al archivo.</p> <p style="font-weight: bold;">[!UICONTROL File]</p> <p>Seleccione el archivo en el menú.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Otros módulos

#### [!UICONTROL Make an API Call]

Este módulo de acción le permite realizar una llamada autenticada personalizada a la API [!DNL Dropbox]. De este modo, puede crear una automatización del flujo de datos imposibles de realizar por los otros [!DNL Dropbox] módulos.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Dropbox] a [!DNL Workfront Fusion], consulte <a href="#create-a-connection-to-dropbox" class="MCXref xref">Crear una conexión con [!DNL Dropbox]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>Escriba una ruta relativa a Escriba una ruta relativa a <code>https://api.dropboxapi.com</code>. Por ejemplo: <code>/2/files/list_folder</code></p> <p>Nota: para obtener la lista de puntos finales disponibles, consulte la <a href="https://www.dropbox.com/developers/documentation/http/documentation">Documentación de la API de Dropbox versión 2</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Headers] </td> 
   <td> <p>Introduzca los encabezados de solicitud deseados. [!DNL Workfront Fusion] añade encabezados de autorización automáticamente.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query String]</td> 
   <td> <p> Introduzca la cadena de consulta de la solicitud.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Body] </td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:   <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>">  
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!INFO]
>
>**Ejemplo:** la siguiente llamada de API devuelve los primeros 10 archivos de la carpeta [!DNL /Text files] de su cuenta de [!DNL Dropbox]:
>
>URL: `/2/files/list_folder`
>
>Cuerpo:
> 
>`{`
>
>`"path": "/Text files",`
>
>`"limit": 10,`
>
>`"recursive": false,`
>
>`"include_deleted": false`
>
>`}`
>
>Las coincidencias de la búsqueda se pueden encontrar en la sección Salida del módulo en [!UICONTROL Bundle] > [!UICONTROL Body] > entradas.
>
>En nuestro ejemplo, se devolvieron 10 tickets:

## Problemas comunes

* [No se puede cargar o actualizar un archivo](#unable-to-upload-or-update-a-file)
* [La imagen a la que se hace referencia mediante un vínculo compartido no se representa](#image-referenced-via-a-shared-link-does-not-render)

### No se puede cargar o actualizar un archivo

Cuando falla la carga o actualización de un archivo, se dan varias situaciones:

* El archivo cargado es demasiado grande y supera el tamaño máximo de archivo permitido para el plan de [!DNL Dropbox], o bien se ha utilizado toda la cuota de almacenamiento de la cuenta de [!DNL Dropbox]. Debe eliminar los archivos existentes de su cuenta de [!DNL Dropbox] o actualizar su plan.
* La carpeta seleccionada anteriormente, a la que se está cargando el archivo, ya no existe. El escenario se detiene y debe volver a seleccionar la carpeta de destino.

### La imagen a la que se hace referencia mediante un vínculo compartido no se representa

La dirección URL devuelta por [!UICONTROL Dropbox] >[!UICONTROL Create a shared link] no se vincula directamente a una imagen, sino a una página [!DNL Dropbox]. Para forzar la descarga de la imagen, sustituya el `?dl=0` final por `?dl=1`. Para forzar el procesamiento de la imagen (por ejemplo, en un explorador Web o en Facebook Messenger), añada `&raw=1` a la dirección URL.

Si necesita obtener el vínculo directo o sin procesar de la imagen para su sitio web o para otros módulos de [!DNL Workfront Fusion], debe modificar la dirección URL compartida inicial de la siguiente manera:

URL original:

`https://www.dropbox.com/s/ia8qtvs20f3a5ux/Screen%20Shot%202018-10-15%20at%204.21.11%20PM.png?dl=0`

1. Reemplazar `www` por `dl`.
1. Eliminar `?dl=0`.

URL final:

`https://dl.dropbox.com/s/ia8qtvs20f3a5ux/Screen%20Shot%202018-10-15%20at%204.21.11%20PM.png`

Para modificar automáticamente la dirección URL, puede usar la función `replace()` dos veces:

* Reemplazar www por dl

  ![Reemplazar www por dl](/help/workfront-fusion/references/apps-and-modules/assets/www-to-dl-350x32.png)

* Y para quitar ?dl=0

  ![Quitar DL](/help/workfront-fusion/references/apps-and-modules/assets/remove-dl0-350x33.png)

Para hacerlo en un solo paso, combine estas funciones:

![Reemplazar ambos](/help/workfront-fusion/references/apps-and-modules/assets/replace-both-350x47.png)

También puede copiarlo y pegarlo en el campo. Reemplazar `1.url` por la URL.

```
{{replace(replace(1.url; "?dl=0"; ""); "www"; "dl")}}
```
