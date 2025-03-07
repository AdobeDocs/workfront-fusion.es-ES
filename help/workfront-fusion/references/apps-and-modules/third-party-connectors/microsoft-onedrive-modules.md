---
title: Módulos de Microsoft OneDrive
description: En un escenario de  [!DNL Adobe Workfront Fusion] , puede automatizar los flujos de trabajo que utilizan OneDrive, así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: d21eafad-9c67-4f42-b718-0aa4223846e6
source-git-commit: 632128bdcb6f8b8361f5a28e4a5fb527eb274d54
workflow-type: tm+mt
source-wordcount: '4087'
ht-degree: 96%

---

# Módulos de [!DNL Microsoft OneDrive]

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!DNL OneDrive], así como conectarlo a varias aplicaciones y servicios de terceros.

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
   <p>Actual: no se requiere licencia de Workfront Fusion.</p>
   <p>O</p>
   <p>Heredado: Workfront Fusion para la automatización e integración del trabajo </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Seleccione o paquete de Prime Workfront: su organización debe adquirir Adobe Workfront Fusion.</li><li>Paquete de Ultimate Workfront: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe adquirir Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Para usar módulos [!DNL OneDrive], debe tener una cuenta de [!DNL Microsoft OneDrive].



## Información de API de OneDrive

El conector OneDrive utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL básica</td> 
   <td> https://graph.microsoft.com/v1.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> Versión 1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 2.0.10</td> 
  </tr>
 </tbody> 
 </table>


## Conexión del servicio de [!DNL OneDrive] a [!DNL Workfront Fusion]

Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL OneDrive] a [!UICONTROL Workfront Fusion], consulte [Crear una conexión a [!UICONTROL Adobe Workfront Fusion]: instrucciones básicas](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

>[!NOTE]
>
>Algunas aplicaciones de Microsoft utilizan la misma conexión, que está vinculada a permisos de usuario individuales. Por lo tanto, al crear una conexión, la pantalla de consentimiento de permisos muestra los permisos que se otorgaron previamente a la conexión de este usuario, además de cualquier nuevo permiso que sea necesario para la aplicación actual.
>
>Por ejemplo, si a un usuario se le han otorgado permisos de &quot;Leer tabla&quot; a través del conector de Excel y luego crea una conexión en el conector de Outlook para leer correos electrónicos, la pantalla de consentimiento de permisos mostrará tanto el permiso de &quot;Leer tabla&quot; ya otorgado como el nuevo permiso requerido de &quot;Escribir correo electrónico&quot;.

## Módulos de [!DNL Microsoft OneDrive] y sus campos

Al configurar módulos de [!DNL OneDrive], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL OneDrive] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Archivo/Carpeta](#filefolder)
* [Otro](#other)

### Archivo/Carpeta

* [[!UICONTROL Copiar un archivo]](#copy-a-file)
* [[!UICONTROL Crear una carpeta]](#create-a-folder)
* [[!UICONTROL Eliminar archivo/carpeta]](#delete-a-filefolder)
* [[!UICONTROL Descargar un archivo]](#download-a-file)
* [[!UICONTROL Obtener un archivo]](#get-a-file)
* [[!UICONTROL Obtener un vínculo para compartir]](#get-a-share-link)
* [[!UICONTROL Mover un archivo/carpeta]](#move-a-filefolder)
* [[!UICONTROL Buscar archivos/carpetas]](#search-filesfolders)
* [[!UICONTROL Cargar un archivo]](#upload-a-file)
* [[!UICONTROL Ver archivos/carpetas]](#watch-filesfolders)

#### [!UICONTROL Copiar un archivo]

Este módulo de acción copia un archivo en la ubicación de la nueva carpeta

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL OneDrive] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a [!DNL Adobe Workfront Fusion]: instrucciones básicas</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter (File ID &amp; File Path)]</td> 
   <td>Seleccione si desea identificar el archivo por ID de archivo o por ruta de archivo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a File ID] / [!UICONTROL File Path]</td> 
   <td> <p>Seleccione cómo desea introducir el ID de archivo o la ruta de archivo:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>Seleccione esta opción si desea introducir el ID o la ruta directamente o bien asignarlos desde un módulo anterior.</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>Seleccione esta opción si desea hacer una selección desde una lista de archivos o rutas disponibles. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] location]</td> 
   <td> <p>Seleccione la ubicación que contiene el archivo que desea copiar:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>Seleccione esta opción si desea permitir que el módulo introduzca un ID de unidad.</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>Escriba el identificador de la unidad que contiene el archivo o la carpeta que desea copiar.</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>Seleccione el sitio de SharePoint que contiene el archivo que desea mover. Los sitios disponibles son sitios seguidos por el usuario que ha iniciado sesión.</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>Seleccione el grupo cuya unidad contiene el archivo que desea copiar.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> [!UICONTROL Drive ID]</td> 
   <td> <p>Seleccione o asigne la unidad que contiene el archivo que desea copiar. Este campo no está disponible si seleccionó [!UICONTROL No] en el campo [!UICONTROL Enable to Enter a Drive ID].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p role="rowheader">[!UICONTROL File] / [!UICONTROL File ID] / [!UICONTROL File Path]</p> </td> 
   <td> <p>Si seleccionó [!UICONTROL Enter Manually], escriba o asigne el ID o la ruta de acceso del archivo que desea copiar.</p> <p>Si ha seleccionado Seleccionar de la lista, seleccione el archivo que desea copiar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a New Folder Location]</td> 
   <td> <p>Seleccione cómo desea introducir la ubicación en la que desea copiar el archivo:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>Seleccione esta opción si desea introducir el ID o la ruta directamente o bien asignarlos desde un módulo anterior.</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>Seleccione esta opción si desea seleccionar de una lista de carpetas disponibles. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New OneDrive location]</td> 
   <td> <p>Seleccione la ubicación donde desea copiar el filtro. Esta opción está disponible si elige seleccionar la nueva ubicación de la carpeta en una lista.</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>Seleccione esta opción si desea permitir que el módulo introduzca un ID de unidad.</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>Escriba el identificador de la unidad donde desea copiar el archivo.</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>Seleccione el sitio [!DNL SharePoint] en el que desea copiar el archivo. Los sitios disponibles son sitios seguidos por el usuario que ha iniciado sesión.</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>Seleccione el grupo en cuya unidad desee copiar el archivo.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> [!UICONTROL Drive ID]</td> 
   <td> <p>Seleccione o asigne la unidad que contiene la carpeta en la que desea copiar el archivo. Este campo no está disponible si seleccionó [!UICONTROL No] en el campo [!UICONTROL Enable to Enter a Drive ID].</p> <p>Si deja esto en blanco, el archivo o la carpeta solo se podrán copiar dentro de la misma [!UICONTROL OneDrive].</p> <p>Puede copiar archivos y carpetas de [!UICONTROL My Drive] a una [!UICONTROL Site's Drive] o una [!UICONTROL Group's Drive]. </p> <p>Solo puede copiar archivos de una unidad de [!UICONTROL Site's Drive] en la misma unidad del mismo sitio.</p> <p>Puede copiar archivos de una unidad de [!UICONTROL Group's Drive] solo en la misma unidad del mismo grupo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>Introduzca o asigne la carpeta a la que desea mover la copia o carpeta.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New Copied File Name]</td> 
   <td> <p>Introduzca o asigne un nombre para la nueva copia del archivo. Puede dejarlo en blanco si no desea cambiar el nombre del archivo original.</p> <p>El nombre debe incluir la extensión de archivo. Ejemplo: <code>file.txt</code></p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- Start audit here-->

#### [!UICONTROL Create a Folder]

Este módulo de acción crea una nueva carpeta en la unidad especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL OneDrive] a [!DNL Workfront Fusion], consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] location]</td> 
   <td> <p>Seleccione la ubicación donde desea crear una carpeta:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>Seleccione esta opción si desea permitir que el módulo introduzca un ID de unidad.</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>Seleccione la unidad donde desea crear una carpeta.</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>Seleccione el sitio [!DNL SharePoint] en el que desea crear una carpeta. Los sitios disponibles son sitios seguidos por el usuario que ha iniciado sesión.</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>Seleccione el grupo propietario de la unidad donde desea crear una carpeta.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> [!UICONTROL Drive ID]</td> 
   <td> <p>Seleccione la unidad en la que desea crear una carpeta. Este campo no está disponible si seleccionó [!UICONTROL No] en el campo [!UICONTROL Enable to Enter a Drive ID].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>Si desea que la nueva carpeta sea una subcarpeta, vaya a la carpeta en la que desea que sea una subcarpeta.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New Folder Name]</td> 
   <td> <p>Introduzca o asigne un nombre para la nueva carpeta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL If the Folder with the Same Name Exists]</td> 
   <td>Seleccione cómo continuar si ya existe un archivo con el mismo nombre.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a File/Folder]

Este módulo de acción elimina el archivo seleccionado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL OneDrive] a [!DNL Workfront Fusion], consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter (File/Folder ID &amp; Path)]</td> 
   <td>Seleccione si desea identificar el archivo por ID de archivo o por ruta de archivo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a File/Folder ID /Enter a File/Folder Path]</td> 
   <td> <p>Seleccione cómo desea introducir el ID de archivo o la ruta de archivo:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>Seleccione esta opción si desea introducir el ID o la ruta directamente o bien asignarlos desde un módulo anterior.</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>Seleccione esta opción si desea hacer una selección desde una lista de archivos o rutas disponibles. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] location]</td> 
   <td> <p>Seleccione la ubicación en la que desea buscar:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>Seleccione esta opción si desea permitir que el módulo introduzca un ID de unidad.</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>Introduzca el ID de la unidad que contiene el archivo o la carpeta que desea eliminar.</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>Seleccione el sitio de [!DNL SharePoint] que contiene el archivo o la carpeta que desea eliminar. Los sitios disponibles son sitios seguidos por el usuario que ha iniciado sesión.</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>Seleccione el grupo cuya unidad contiene el archivo o la carpeta que desea eliminar.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> [!UICONTROL Drive ID]</td> 
   <td> <p>Seleccione o asigne la unidad que contiene el archivo o la carpeta que desea eliminar. Este campo no está disponible si seleccionó [!UICONTROL No] en el campo [!UICONTROL Enable to Enter a Drive ID].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Seleccionar [!UICONTROL File/Folder]</td> 
   <td>Seleccione si desea eliminar un archivo o una carpeta.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File] / [!UICONTROL File ID] / [!UICONTROL File Path]</td>
   <td> <p>Si ha seleccionado [!UICONTROL Enter Manually], introduzca o asigne el ID o la ruta del archivo que desea eliminar.</p> <p>Si ha seleccionado [!UICONTROL Select] en la lista, seleccione el archivo que desea eliminar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Descargar un archivo]

Este módulo de acción descarga el archivo especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL OneDrive] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a [!DNL Adobe Workfront Fusion]: instrucciones básicas</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter (File ID &amp; File Path)]</td> 
   <td>Seleccione si desea identificar el archivo por ID de archivo o por ruta de archivo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Introduzca un ID de archivo / ruta de archivo</td> 
   <td> <p>Seleccione cómo desea introducir el ID de archivo o la ruta de archivo:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>Seleccione esta opción si desea introducir el ID o la ruta directamente o bien asignarlos desde un módulo anterior.</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>Seleccione esta opción si desea hacer una selección desde una lista de archivos o rutas disponibles. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] location]</td> 
   <td> <p>Seleccione la ubicación que desea que contenga el archivo que va a descargar:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>Seleccione esta opción si desea permitir que el módulo introduzca un ID de unidad.</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>Escriba el identificador de la unidad que contiene el archivo que desea descargar.</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>Seleccione el sitio de SharePoint que contiene el archivo que desea descargar. Los sitios disponibles son sitios seguidos por el usuario que ha iniciado sesión.</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>Seleccione el grupo cuya unidad contiene el archivo que desea descargar.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> [!UICONTROL Drive ID]</td> 
   <td> <p>Seleccione o asigne la unidad que contiene el archivo que desea descargar. Este campo no está disponible si seleccionó [!UICONTROL No] en el campo [!UICONTROL Enable to Enter a Drive ID].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File] / [!UICONTROL File ID] / [!UICONTROL File Path]</td>
   <td> <p>Si seleccionó [!UICONTROL Enter Manually], escriba o asigne el ID o la ruta de acceso del archivo que desea descargar.</p> <p>Si seleccionó [!UICONTROL Select from the list], seleccione el archivo que desea descargar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Convert to PDF]</td> 
   <td> <p>Active esta opción para convertir el archivo en un archivo PDF. Puede convertir desde los siguientes tipos de archivo:</p> 
    <table style="table-layout:auto"> 
     <col> 
     <col> 
     <col> 
     <tbody> 
      <tr> 
       <td> 
        <ul> 
         <li> <p> <p>CSV</p> </p> </li> 
         <li> <p> <p>DOC</p> </p> </li> 
         <li> <p> <p>DOCX</p> </p> </li> 
         <li> <p> <p>ODP</p> </p> </li> 
         <li> <p> <p>ODS</p> </p> </li> 
         <li> <p> <p>ODT</p> </p> </li> 
        </ul> </td> 
       <td> 
        <ul> 
         <li> <p> <p>POT</p> </p> </li> 
         <li> <p> <p>POTM</p> </p> </li> 
         <li> <p> <p>POTX</p> </p> </li> 
         <li> <p> <p>PPS</p> </p> </li> 
         <li> <p> <p>PPSX</p> </p> </li> 
         <li> <p> <p>PPSXM</p> </p> </li> 
        </ul> </td> 
       <td> 
        <ul> 
         <li> <p>PPT</p> </li> 
         <li> <p>PPTM</p> </li> 
         <li> <p>PPTX</p> </li> 
         <li> <p>RTF</p> </li> 
         <li> <p>XLS</p> </li> 
         <li> <p>XLSX</p> </li> 
        </ul> </td> 
      </tr> 
     </tbody> 
    </table> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Obtener un archivo]

Este módulo de acción obtiene los metadatos de un archivo especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL OneDrive] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a [!DNL Adobe Workfront Fusion]: instrucciones básicas</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter (File ID &amp; File Path)]</td> 
   <td>Seleccione si desea identificar el archivo por ID de archivo o por ruta de archivo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a File ID] / [!UICONTROL File Path]</td> 
   <td> <p>Seleccione cómo desea introducir el ID de archivo o la ruta de archivo:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>Seleccione esta opción si desea introducir el ID o la ruta directamente o bien asignarlos desde un módulo anterior.</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>Seleccione esta opción si desea hacer una selección desde una lista de archivos o rutas disponibles. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] location]</td> 
   <td> <p>Seleccione la ubicación en la que desea buscar:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>Seleccione esta opción si desea permitir que el módulo introduzca un ID de unidad.</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>Escriba el ID de la unidad que contiene el archivo que desea obtener.</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>Seleccione el sitio de SharePoint que contiene el archivo que desea obtener. Los sitios disponibles son sitios seguidos por el usuario que ha iniciado sesión.</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>Seleccione el grupo cuya unidad contiene el archivo que desea obtener.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> [!UICONTROL Drive ID]</td> 
   <td> <p>Seleccione o asigne la unidad que contiene el archivo que desea obtener. Este campo no está disponible si seleccionó [!UICONTROL No] en el campo [!UICONTROL Enable to Enter a Drive ID].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File] / [!UICONTROL File ID] / [!UICONTROL File Path]</td> 
   <td> <p>Si seleccionó [!UICONTROL Enter Manually], escriba o asigne el ID o la ruta de acceso del archivo que desea obtener.</p> <p>Si seleccionó [!UICONTROL Select from the list], seleccione el archivo que desea obtener.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Share Link]

Este módulo de acción devuelve un vínculo compartido para el archivo especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL OneDrive] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a [!DNL Adobe Workfront Fusion]: instrucciones básicas</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter (File ID &amp; File Path)]</td> 
   <td>Seleccione si desea identificar el archivo por ID de archivo o por ruta de archivo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a File ID] / [!UICONTROL File Path]</td> 
   <td> <p>Seleccione cómo desea introducir el ID de archivo o la ruta de archivo:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>Seleccione esta opción si desea introducir el ID o la ruta directamente o bien asignarlos desde un módulo anterior.</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>Seleccione esta opción si desea hacer una selección desde una lista de archivos o rutas disponibles. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] location]</td> 
   <td> <p>Seleccione la ubicación para la que desea recuperar un vínculo compartido:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>Seleccione esta opción si desea permitir que el módulo introduzca un ID de unidad.</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>Introduzca el identificador de la unidad que contiene el archivo para el que desea recuperar un vínculo compartido.</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>Seleccione el sitio de SharePoint que contiene el archivo para el que desea recuperar un vínculo compartido. Los sitios disponibles son sitios seguidos por el usuario que ha iniciado sesión.</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>Seleccione el grupo cuya unidad contiene el archivo para el que desea recuperar un vínculo compartido.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> [!UICONTROL Drive ID]</td> 
   <td> <p>Seleccione o asigne la unidad que contiene el archivo para el que desea recuperar un vínculo compartido. Este campo no está disponible si seleccionó [!UICONTROL No] en el campo [!UICONTROL Enable to Enter a Drive ID].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File] / [!UICONTROL File ID] / [!UICONTROL File Path]</td> 
   <td> <p>Si seleccionó [!UICONTROL Enter Manually], introduzca o asigne el identificador de archivo o la ruta del archivo para el que desea recuperar un vínculo compartido.</p> <p>Si seleccionó [!UICONTROL Select] de la lista, seleccione el archivo para el que desea recuperar un vínculo compartido.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Permission Type]</td> 
   <td> <p>Seleccione si desea que las personas con el vínculo puedan leer y escribir en el archivo o sólo leer.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scope]</td> 
   <td>Seleccione si desea que el archivo esté disponible para cualquier persona que tenga el vínculo o solo para los miembros de su organización que lo tengan.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Mover un archivo/carpeta]

Este módulo de acción mueve un archivo o carpeta a una nueva ubicación de carpeta

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL OneDrive] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a [!DNL Adobe Workfront Fusion]: instrucciones básicas</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter (File ID &amp; File Path)]</td> 
   <td>Seleccione si desea identificar el archivo por ID de archivo o por ruta de archivo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a File ID / File Path]</td> 
   <td> <p>Seleccione cómo desea introducir el ID de archivo o la ruta de archivo:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>Seleccione esta opción si desea introducir el ID o la ruta directamente o bien asignarlos desde un módulo anterior.</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>Seleccione esta opción si desea hacer una selección desde una lista de archivos o rutas disponibles. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] location]</td> 
   <td> <p>Seleccione la ubicación que contiene el archivo o la carpeta que desea mover:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>Seleccione esta opción si desea permitir que el módulo introduzca un ID de unidad.</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>Escriba el identificador de la unidad que contiene el archivo o la carpeta que desea mover.</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>Seleccione el sitio [!DNL SharePoint] que contiene el archivo o la carpeta que desea mover. Los sitios disponibles son sitios seguidos por el usuario que ha iniciado sesión.</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>Seleccione el grupo cuya unidad contiene el archivo o la carpeta que desea mover.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> [!UICONTROL Drive ID]</td> 
   <td> <p>Seleccione o asigne la unidad que contiene el archivo o la carpeta que desea mover. Este campo no está disponible si seleccionó [!UICONTROL No] en el campo [!UICONTROL Enable to Enter a Drive ID].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Seleccionar [!UICONTROL File/Folder]</td> 
   <td>Seleccione si desea mover un archivo o una carpeta.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p role="rowheader">[!UICONTROL File] / [!UICONTROL File ID] / [!UICONTROL File Path]</p> <p role="rowheader">[!UICONTROL Folder] / [!UICONTROL Folder ID] / [!UICONTROL Folder Path]</p> </td> 
   <td> <p>Si seleccionó [!UICONTROL Enter Manually], escriba o asigne el ID o la ruta del archivo o carpeta que desea mover.</p> <p>Si seleccionó [!UICONTROL Select] de la lista, seleccione el archivo o carpeta que desea mover.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a New Folder Location]</td> 
   <td> <p>Seleccione cómo desea introducir la ubicación a la que desea mover el archivo o carpeta:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>Seleccione esta opción si desea introducir el ID o la ruta directamente o bien asignarlos desde un módulo anterior.</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>Seleccione esta opción si desea hacer una selección desde una lista de archivos o rutas disponibles. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] location]</td> 
   <td> <p>Seleccione la ubicación a la que desea mover el archivo o carpeta:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>Seleccione esta opción si desea permitir que el módulo introduzca un ID de unidad.</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>Escriba el ID de la unidad donde desea mover el archivo o carpeta.</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>Seleccione el sitio [!DNL SharePoint] al que desea mover el archivo o carpeta. Los sitios disponibles son sitios seguidos por el usuario que ha iniciado sesión.</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>Seleccione el grupo a cuya unidad desea mover el archivo o carpeta.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> [!UICONTROL Drive ID]</td> 
   <td> <p>Seleccione o asigne la unidad que contiene la carpeta a la que desea mover el archivo o carpeta. Este campo no está disponible si seleccionó [!UICONTROL No] en el campo [!UICONTROL Enable to Enter a Drive ID].</p> <p>Si deja este campo en blanco, el archivo o carpeta solamente se podrán mover dentro del mismo [!DNL OneDrive].</p> <p>Pueden moverse archivos y carpetas de [!UICONTROL My Drive] a [!UICONTROL Site's Drive] o a [!UICONTROL Group's Drive]. </p> <p>Solo pueden moverse archivos de [!UICONTROL Site's Drive] a la misma unidad del mismo sitio.</p> <p>Solo se pueden mover archivos de [!UICONTROL Group's Drive] a la misma unidad del mismo grupo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>Escriba o asigne la carpeta donde desea mover el archivo o carpeta.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Buscar archivos/carpetas]

Este módulo de búsqueda devuelve archivos y carpetas en función de los criterios definidos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL OneDrive] a [!DNL Workfront Fusion], consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] location]</td> 
   <td> <p>Seleccione la ubicación en la que desea buscar:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>Seleccione esta opción si desea permitir que el módulo introduzca un ID de unidad.</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>Escriba el identificador de la unidad que desea que busque el módulo.</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> <p>Vaya a la carpeta en la que desee buscar el módulo. También puede introducir una consulta para filtrar los resultados devueltos.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Shared With Me]</b> </p> <p>El módulo busca los archivos que se han compartido con el propietario de la unidad.</p> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>Seleccione el sitio de [!DNL SharePoint] en el que desea que busque el módulo. Los sitios disponibles son sitios seguidos por el usuario que ha iniciado sesión.</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>Seleccione el grupo en cuya unidad desea que busque el módulo.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose an Item Type]</td> 
   <td> <p>Seleccione si desea buscar archivos, carpetas o ambos.</p> <p>Nota: No se pueden buscar carpetas en una unidad de [!UICONTROL Shared With Me].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a file]

Este módulo de acción carga un archivo en la carpeta especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL OneDrive] a [!DNL Workfront Fusion], consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">Introducir (ID y ruta de ubicación de la carpeta)</td> 
   <td>Seleccione si desea identificar la carpeta de destino por ID o por ruta.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] location]</td> 
   <td> <p>Seleccione la ubicación donde desea cargar el archivo:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>Seleccione esta opción si desea permitir que el módulo introduzca un ID de unidad.</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>Seleccione la unidad que contiene el archivo que desea obtener.</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>Seleccione el sitio [!DNL SharePoint] que contiene la carpeta donde desea cargar un archivo. Los sitios disponibles son sitios seguidos por el usuario que ha iniciado sesión.</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>Seleccione el grupo cuya unidad contiene la carpeta donde desea cargar un archivo.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> [!UICONTROL Drive ID]</td> 
   <td> <p>Seleccione la unidad que contiene la carpeta donde desea cargar un archivo. Este campo no está disponible si seleccionó [!UICONTROL No] en el campo [!UICONTROL Enable to Enter a Drive ID].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL If the File with the Same Name Exists]</td> 
   <td>Seleccione cómo continuar si ya existe un archivo con el mismo nombre.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Añada una descripción al archivo cargado.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Ver archivos/carpetas]

Este módulo de activación inicia un escenario cuando se crea o actualiza un archivo o carpeta.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL OneDrive] a [!DNL Workfront Fusion], consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch Files/Folders]</td> 
   <td> <p>Seleccione cómo desea ver archivos o carpetas:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL By Created Time]</b> </p> <p>Ver nuevos archivos o carpetas.</p> </li> 
     <li> <p><b>[!UICONTROL By Updated Time]</b> </p> <p>Ver archivos o carpetas existentes actualizados.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] location]</td> 
   <td> <p>Seleccione la ubicación que desee ver:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>Seleccione esta opción si desea permitir que el módulo introduzca un ID de unidad.</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>Escriba el identificador de la unidad que desea que visualice el módulo.</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> <p>Vaya a la carpeta que desee que visualice el módulo. También puede introducir una consulta para filtrar los resultados devueltos.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Shared With Me]</b> </p> <p>El módulo visualiza los archivos que se han compartido con el propietario de la unidad.</p> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>Seleccione el sitio de SharePoint que desea que visualice el módulo. Los sitios disponibles son sitios seguidos por el usuario que ha iniciado sesión.</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>Seleccione el grupo cuya unidad desea que visualice el módulo.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose an Item Type]</td> 
   <td> <p>Seleccione si desea ver archivos, carpetas o ambos.</p> <p>Nota: No puede ver carpetas en una unidad de [!UICONTROL Shared With Me].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>



### Otro

#### [!UICONTROL Make an API Call]

Este módulo realiza una llamada de API personalizada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL OneDrive] a [!DNL Workfront Fusion], consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a [!DNL Adobe Workfront Fusion]: instrucciones básicas</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Introduzca una ruta relativa a <code>https://graph.microsoft.com</code>. Ejemplo:<code> /v1.0/me/drive/root/children</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   td&gt; <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td> 
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
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>



## Si no puede cargar o actualizar un archivo

Existen varios posibles problemas cuando falla la carga o actualización de un archivo:

* El archivo cargado es demasiado grande y supera el límite máximo de tamaño de archivo para el plan [!DNL OneDrive] o ha utilizado toda la cuota de almacenamiento de la cuenta [!DNL OneDrive]. Para obtener más espacio de almacenamiento, elimine los archivos existentes de [!DNL OneDrive] o actualice la cuenta de [!DNL OneDrive].
* OneDrive no permite cargar dos archivos con el mismo nombre en una sola carpeta. Si la carpeta de destino contiene un archivo con el mismo nombre que el archivo que se está cargando, la ejecución del escenario finaliza con un error. La solución consiste simplemente en cambiar el nombre del archivo que se está cargando. Si su objetivo es actualizar un archivo, use la acción [!UICONTROL Actualizar un archivo].
* La carpeta seleccionada anteriormente, en la que se está cargando el archivo, ya no existe. El escenario se detiene y tendrá que volver a seleccionar la carpeta de destino.
