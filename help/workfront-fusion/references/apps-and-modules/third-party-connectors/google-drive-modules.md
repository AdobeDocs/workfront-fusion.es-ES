---
title: Módulos de Google Drive
description: Los módulos  [!DNL Adobe Workfront Fusion Google Drive] le permiten supervisar, buscar, crear, actualizar, eliminar y administrar sus archivos, carpetas o unidades compartidas en su [!DNL Google Drive].
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 788f4e1b-d774-45ad-a8be-b16922c1d5dc
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '2102'
ht-degree: 20%

---

# Módulos de [!DNL Google Drive]

Los módulos de Adobe Workfront Fusion [!DNL Google Drive] le permiten supervisar, buscar, crear, actualizar, eliminar y administrar sus archivos, carpetas o unidades compartidas en su [!DNL Google Drive].

En un escenario de Adobe Workfront Fusion, puede conectar su cuenta de [!DNL Google Drive] a varias aplicaciones y servicios de terceros.

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

## Información de API de Google Drive

El conector de Google Drive utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Dirección URL base</td> 
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



## Conectando [!DNL Google Drive] a Workfront Fusion

Si usa [!DNL @gmail.com] o [!DNL @googlemail.com] usuario, debe crear un cliente de OAuth en [!DNL Google Cloud Platform] para obtener su [!UICONTROL ID de cliente] y [!UICONTROL Secreto de cliente].

Para obtener instrucciones paso a paso sobre cómo crear el cliente OAuth (y obtener [!UICONTROL ID de cliente] y [!UICONTROL Secreto de cliente]), consulte [Conectar Adobe Workfront Fusion a [!DNL Google Services] usando un cliente OAuth personalizado](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md).

Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Drive] a [!UICONTROL Workfront Fusion], consulte [Crear una conexión a [!UICONTROL Adobe Workfront Fusion]: instrucciones básicas](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

## Módulos de [!DNL Google Drive] y sus campos

Al configurar módulos de [!DNL Google Drive], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL Google Drive] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)



* [Activadores](#triggers)
* [Acciones](#actions)

### Activadores

* [[!UICONTROL Ver todos los archivos]](#watch-all-files)
* [[!UICONTROL Ver comentarios]](#watch-comments)
* [[!UICONTROL Observar archivos en la carpeta]](#watch-files-in-folder)
* [[!UICONTROL Ver archivos compartidos]](#watch-shared-files)

#### [!UICONTROL Ver todos los archivos]

Este módulo de déclencheur inicia un escenario cuando se agrega o modifica un archivo de su [!DNL Google Drive].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Drive] a Workfront Fusion, consulte <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
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
    <td >[!UICONTROL Convert [!DNL Google Documents] files to format]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Documents].</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Spreadsheets] files to format]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Spreadsheets].</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Slides] files to format]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Slides].</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Drawings] files to format]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Drawings].</td>
  </tr>  
  <tr> 
   <td>[!UICONTROL Watch]</td> 
   <td>Seleccione si desea inspeccionar los nuevos archivos y todos los cambios, o sólo los nuevos.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of downloaded files]</td> 
   <td>Defina el número máximo de resultados que Workfront Fusion descargará durante un ciclo (el número de repeticiones por ejecución de escenario).</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Ver comentarios]

Este módulo de déclencheur inicia un escenario cuando se agrega o modifica un comentario en el archivo seleccionado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Drive] a Workfront Fusion, consulte <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
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
   <td>Establezca el número máximo de comentarios que Workfront Fusion devolverá durante un ciclo (el número de repeticiones por ejecución de escenario).</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Observar archivos en la carpeta]

Este módulo de déclencheur inicia un escenario cuando se agrega o modifica un archivo en la carpeta especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection] </td>
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Drive] a Workfront Fusion, consulte <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr>
    <td>[!UICONTROL Seleccione la carpeta que desea ver]</td>
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
    <td >[!UICONTROL Convert [!DNL Google Documents] files to format]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Documents].</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Spreadsheets] files to format]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Spreadsheets].</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Slides] files to format]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Slides].</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Drawings] files to format]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Drawings].</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Watch]</td>
    <td>Seleccione si desea inspeccionar los nuevos archivos y todos los cambios, o sólo los nuevos.</td>
  </tr> 
  <tr> 
    <td>[!UICONTROL Maximum number of downloaded files]</td>
    <td>Defina el número máximo de resultados que Workfront Fusion descargará durante un ciclo (el número de repeticiones por ejecución de escenario).</td>
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Ver archivos compartidos]

Déclencheur cuando se comparte un nuevo archivo con usted o cuando se actualiza un archivo compartido existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Drive] a Workfront Fusion, consulte <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Seleccione la carpeta que desea ver]</td> 
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
    <td >[!UICONTROL Convert [!DNL Google Documents] files to format]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Documents].</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Spreadsheets] files to format]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Spreadsheets].</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Slides] files to format]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Slides].</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Drawings] files to format]</td>
    <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Drawings].</td>
  </tr> 
  <tr> 
   <td>[!UICONTROL Watch]</td> 
   <td>Seleccione si desea inspeccionar los nuevos archivos y todos los cambios, o sólo los nuevos.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of downloaded files]</td> 
   <td>Defina el número máximo de resultados que Workfront Fusion descargará durante un ciclo (el número de repeticiones por ejecución de escenario).</td> 
  </tr> 
 </tbody> 
</table>

### Acciones

* [[!UICONTROL Copiar un archivo]](#copy-a-file)
* [[!UICONTROL Crear una carpeta]](#create-a-folder)
* [[!UICONTROL Eliminar un archivo]](#delete-a-file)
* [[!UICONTROL Obtener un archivo]](#get-a-file)
* [[!UICONTROL Obtener un vínculo compartido]](#get-a-share-link)
* [[!UICONTROL Mover un archivo a la papelera]](#move-a-filefolder-to-trash)
* [[!UICONTROL Buscar archivos/carpetas]](#search-for-filesfolders)
* [[!UICONTROL Actualizar un archivo]](#update-a-file)
* [[!UICONTROL Subir un archivo]](#upload-a-file)

#### [!UICONTROL Copiar un archivo]

Este módulo de acción copia un archivo en la nueva ubicación.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Drive] a Workfront Fusion, consulte <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination]</td> 
   <td> <p>Seleccione el destino en el que desea copiar un archivo.</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL compartido conmigo]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Carpeta de destino]</td> 
   <td>Seleccione la carpeta que contiene el archivo que desea copiar.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>Asigne el ID del archivo que desea copiar.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL El nombre de la copia]</td> 
   <td>Escriba un título para el nuevo archivo. Deje este campo en blanco si no desea cambiar el nombre del archivo original.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Crear una carpeta]

Este módulo de acción crea una carpeta en la ubicación especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Drive] a Workfront Fusion, consulte <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination]</td> 
   <td> <p>Seleccione el destino en el que desea crear una carpeta.</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL compartido conmigo]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Nueva ubicación de carpeta]</td> 
   <td>Vaya a la ubicación en la que desea crear una carpeta nueva.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL The name of the new folder]</td> 
   <td>Escriba un nombre para la carpeta que está creando.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Compartir carpeta]</td> 
   <td>Seleccione esta opción si desea compartir la carpeta con alguien que tenga el vínculo [!UICONTROL Compartir]. De lo contrario, el vínculo compartido solo es para el propietario.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Eliminar un archivo]

Este módulo de acción elimina permanentemente un archivo o una carpeta.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Drive] a Workfront Fusion, consulte <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>Asigne el ID del archivo que desea eliminar.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Obtener un archivo]

Este módulo de acción recupera el archivo con el ID especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Drive] a Workfront Fusion, consulte <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Documents] files to format]</td> 
   <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Documents].</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Spreadsheets] files to format]</td> 
   <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Spreadsheets].</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Slides] files to format]</td> 
   <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Slides].</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Drawings] files to format]</td> 
   <td>Seleccione el formato de archivo al que desea convertir [!DNL Google Drawings].</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>Asigne el ID del archivo que desea recuperar.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Obtener un vínculo compartido]

Este módulo de acción recupera el vínculo compartido de un archivo en Google Drive.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Drive] a Workfront Fusion, consulte <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>Asigne el ID del archivo para el que desea obtener el vínculo compartido.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Mover un archivo a la papelera]

Este módulo de acción mueve un archivo o una carpeta a la papelera.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Drive] a Workfront Fusion, consulte <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>Asigne el ID del archivo que desea mover a la papelera.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Buscar archivos/carpetas]

Este módulo de búsqueda busca archivos o carpetas según los criterios de búsqueda.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Drive] a Workfront Fusion, consulte <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination]</td> 
   <td> <p>Seleccione la unidad de destino que desea buscar.</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL compartido conmigo]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Mostrar una carpeta]</td> 
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
     <li> <p><strong>[!UICONTROL Buscar en nombres de archivo/carpeta]</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Query]</strong> </p> <p>Introduzca una parte del nombre de archivo o el nombre completo del archivo (incluido el sufijo) que desee buscar.</p> </li> 
       <li> <p><strong>[!UICONTROL Opciones de búsqueda]</strong> </p> <p>Seleccione si desea buscar el término exacto o si desea buscar nombres que contengan el término de búsqueda.</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL Texto completo] buscar</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Query]</strong> </p> <p>Escriba cualquier término de búsqueda que quiera buscar en su [!DNL Google Drive].</p> </li> 
      </ul> </li> 
     <li> <p><strong>Introducir consulta de búsqueda personalizada</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Query]</strong> </p> <p>Introduzca la consulta de búsqueda personalizada. Para obtener más información, consulte la sección [!UICONTROL Buscar archivos] de este artículo.</p> </li> 
       <li> <p><strong>Agregar la carpeta seleccionada arriba a la consulta</strong> </p> <p>Busca la carpeta en la colección primaria. Esto encuentra todos los archivos y carpetas ubicados directamente en la carpeta seleccionada anteriormente.</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned results]</td> 
   <td>Establezca el número máximo de archivos o carpetas que Workfront Fusion devolverá durante un ciclo de ejecución.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Continue the execution of the route even if the module returns no results]</td> 
   <td>Active esta opción para asegurarse de que el escenario no se detiene si el módulo no devuelve resultados.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Actualizar un archivo]

Este módulo de acción actualiza los metadatos o el contenido de un archivo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Drive] a Workfront Fusion, consulte <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination]</td> 
   <td> <p>Seleccione el destino que contiene el archivo que desea actualizar.</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL compartido conmigo]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Mover a una carpeta]</td> 
   <td>Si desea mover el archivo a una carpeta específica, seleccione la carpeta en la que desea mover el archivo.</td> 
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
   <td>[!UICONTROL Cambiar el contenido de un archivo]</td> 
   <td>Seleccione si desea reemplazar el contenido del archivo.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td>Si va a reemplazar el contenido, seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convertir un archivo]</td> 
   <td>Active esta opción para convertir el archivo al formato de archivo Google correspondiente.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Subir un archivo]

Sube un archivo a su [!DNL Google Drive].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Drive] a Workfront Fusion, consulte <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL Google Drive] a [!UICONTROL Workfront Fusion]</a></p> </td> 
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
   <td>[!UICONTROL Carpeta de destino]</td> 
   <td>Seleccione la carpeta en la que desea cargar un archivo. </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Title]</td> 
   <td>Escriba un título para el nuevo archivo.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convertir un archivo]</td> 
   <td>Al habilitar esta opción, el módulo podrá convertir archivos al formato [!DNL Google] correspondiente.</td> 
  </tr> 
 </tbody> 
</table>

## Resolución de problemas

### No se puede cargar o actualizar un archivo

Existen varias razones por las que no se puede cargar o actualizar un archivo:

* El archivo cargado es demasiado grande y supera el límite máximo de tamaño de archivo permitido para el plan [!DNL Google Drive], o bien ya ha superado el límite de almacenamiento de [!DNL Google Drive]. Puede actualizar su plan de almacenamiento o eliminar los archivos existentes del servicio [!DNL Google Drive].
* La carpeta seleccionada en la que se iba a cargar el archivo ya no existe. En este caso, el escenario se detiene y debe seleccionar una carpeta de destino diferente en el módulo.

<!-- Not present February 2025

## Search for files

In the module List files in a folder you can use your own query which consists of these parts:

* **[!UICONTROL Field]** - Attribute of the file that is being searched, for example, the attribute `name` of the file.

* **[!UICONTROL Operator]** - Test that is performed on the data to provide a match, for example, `contains`.

* **[!UICONTROL Value]** - The content of the attribute that is tested, for example, the name of the file `My cool document`.

Combine clauses with the conjunctions `and` or `or`, and negate the query with `not`.

* [Fields](#fields)
* [Value types](#value-types)
* [Operators](#operators)
* [Examples](#examples)

### Fields 

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Field </th> 
   <th>Value Type </th> 
   <th>Operators</th> 
   <th> <p> Description</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td><code>[!UICONTROL title]</code></td> 
   <td>string</td> 
   <td><code>contains</code><sup>1</sup>, <code>=</code>, <code>!=</code></td> 
   <td> <p> Name of the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL fullText]</code> </td> 
   <td>string </td> 
   <td><code>contains</code><sup>2, 3</sup> </td> 
   <td> <p> Full text of the file including name, description, content, and indexable text.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL mimeType]</code> </td> 
   <td> string</td> 
   <td><code>contains</code>, <code>=</code>, <code>!=</code></td> 
   <td> <p> MIME type of the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL modifiedDate]</code> </td> 
   <td> date<sup>4</sup></td> 
   <td><code> &lt;=</code>, <code>&lt;</code>, <code>=</code>, <code>!=</code>, <code>></code>, <code>>=</code></td> 
   <td> <p> Date of the last modification to the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL lastViewedByMeDate]</code> </td> 
   <td> date<sup>4</sup></td> 
   <td><code>&lt;=</code>, <code>&lt;</code>, <code>=</code>, <code>!=</code>, <code>></code>, <code>>=</code></td> 
   <td> <p> Date that the user last viewed a file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL trashed]</code></td> 
   <td>boolean </td> 
   <td><code>=</code>, <code>!=</code></td> 
   <td> <p> Whether the file is in the trash or not.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL starred]</code></td> 
   <td>boolean </td> 
   <td><code>=</code>, <code>!=</code></td> 
   <td> <p>Whether the file is starred or not.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL parents]</code></td> 
   <td>collection </td> 
   <td><code>in </code> </td> 
   <td> <p>Whether the [!UICONTROL parents] collection contains the specified ID.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL owners]</code></td> 
   <td>collection </td> 
   <td><code>in </code> </td> 
   <td> <p>Users who own the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL writers]</code></td> 
   <td>collection </td> 
   <td><code>in </code> </td> 
   <td> <p>Users who have permission to modify the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL readers] </code> </td> 
   <td>collection </td> 
   <td><code>in </code> </td> 
   <td> <p>Users who have permission to read the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL sharedWithMe]</code> </td> 
   <td>boolean </td> 
   <td><code>=</code>, <code>!=</code></td> 
   <td> <p> Files that are in the user's "Shared with me" collection.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL properties] </code> </td> 
   <td>collection</td> 
   <td><code>has </code> </td> 
   <td> <p> Public custom file properties.</p> </td> 
  </tr> 
 </tbody> 
</table>

Consider the following about operators in these fields:

* The `contains` operator only performs prefix matching for a `title`.

   For example, the title "HelloWorld" matches for `title contains 'Hello'` but not for `title contains 'World'`.

* The `contains` operator only performs matching on entire string tokens for `fullText`.

   For example, if the full text of a doc contains the string "HelloWorld" only the query `fullText contains 'HelloWorld'` returns a result. Queries such as `fullText contains 'Hello'` would not return results in this scenario.

* The `contains` operator matches on an exact alphanumeric phrase if it is surrounded by double quotes.

   For example, if the `fullText` of a doc contains the string "Hello there world", then the query `fullText contains '"Hello there"'` returns a result, but the query `fullText contains '"Hello world"'` does not.

   Furthermore, because the search is alphanumeric, if the `fullText` of a doc contains the string "Hello_world", then the query `fullText contains '"Hello world"'` returns a result.

* Fields of `type` date are currently not comparable to each other, only to constant dates.

### Value types

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Value Type</th> 
   <th> <p> Notes</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>String </td> 
   <td> <p>Surround with single quotes '. Escape single quotes in queries with <code>\'</code>, e.g.,<code> 'Valentine\'s Day'</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>Boolean </td> 
   <td> <p><code>true </code>or <code>false</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>Date </td> 
   <td> <p>RFC 3339 format, default timezone is UTC, e.g., <code>2012-06-04T12:00:00-08:00</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Operators

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Operator </th> 
   <th> <p>Notes</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td><code>contains</code></td> 
   <td> <p>The content of one string is present in the other.</p> </td> 
  </tr> 
  <tr> 
   <td><code>=</code> </td> 
   <td> <p> The content of a string or boolean is equal to the other.</p> </td> 
  </tr> 
  <tr> 
   <td><code>!=</code> </td> 
   <td> <p> The content of a string or boolean is not equal to the other.</p> </td> 
  </tr> 
  <tr> 
   <td><code>&lt;</code> </td> 
   <td> <p> A date is earlier than another.</p> </td> 
  </tr> 
  <tr> 
   <td><code>&lt;=</code> </td> 
   <td> <p> A date is earlier than or equal to another.</p> </td> 
  </tr> 
  <tr> 
   <td><code>></code> </td> 
   <td> <p> A date is later than another.</p> </td> 
  </tr> 
  <tr> 
   <td><code>>=</code> </td> 
   <td> <p> A date is later than or equal to another.</p> </td> 
  </tr> 
  <tr> 
   <td><code>in </code> </td> 
   <td> <p>An element is contained within a collection.</p> </td> 
  </tr> 
  <tr> 
   <td><code>and </code> </td> 
   <td> <p>Return files that match both clauses.</p> </td> 
  </tr> 
  <tr> 
   <td><code>or </code> </td> 
   <td> <p>Return files that match either clause.</p> </td> 
  </tr> 
  <tr> 
   <td><code>not </code> </td> 
   <td> <p>Negates a search clause.</p> </td> 
  </tr> 
  <tr> 
   <td><code>has </code> </td> 
   <td> <p>A collection contains an element matching the parameters.</p> </td> 
  </tr> 
 </tbody> 
</table>

For compound clauses, you can use parentheses to group clauses together. For example:
`modifiedDate > '2012-06-04T12:00:00' and (mimeType contains 'image/' or mimeType contains 'video/')` This search returns all files with an image or video MIME type that their last modification was after June 4, 2012. Because `and` and `or` operators are evaluated from left to right, without parentheses, the above example would return only images modified after June 4, 2012, but would return all videos, even those before June 4, 2012.

### Examples 

All examples on this page show the unencoded `<q>q</q>` parameter, where `title = 'hello'` is encoded as `title+%3d+%27hello%27`. Client libraries handle this encoding automatically.

* Search for files with the name "hello"
   <pre>title = 'hello'</pre>
* Search for folders using the folder-specific MIME type
   <pre>mimeType = 'application/vnd.google-apps.folder'</pre>
* Search for files that are not folders
   <pre>mimeType != 'application/vnd.google-apps.folder'</pre>
* Search for files with a name containing the words "hello" and "goodbye"
   <pre>title contains 'hello' and [!UICONTROL name] contains 'goodbye'</pre>
* Search for files with a name that does not contain the word "hello"
   <pre>not title contains 'hello'</pre>
* Search for files containing the word "hello" in the content
   <pre>fullText contains 'hello'</pre>
* Search for files not containing the word "hello" in the content
   <pre>not fullText contains 'hello'</pre>
* Search for files containing the exact phrase "hello world" in the content
   <pre>fullText contains '"hello world"'fullText contains '"hello_world"'</pre>
* Search for files with a query containing the "\" character (e.g., "\authors")
   <pre>fullText contains '\\authors'</pre>
* Search for files writeable by the user `test@example.org`
   <pre>'test@example.org' in [!DNL writers]</pre>
* Search for the ID `1234567` in the `parents` collection. This finds all files and folders located directly in the folder whose ID is `1234567`.
   <pre>'1234567' in [!UICONTROL parents]</pre>
* Search for the alias ID `appDataFolder` in the `parents` collection. This finds all files and folders located directly under the [Application Data folder](https://developers.google.com/drive/api/v2/appdata).
   <pre>'appDataFolder' in parents</pre>
* Search for files writeable by the users `test@example.org` and `test2@example.org`
   <pre>'test@example.org' in writers and 'test2@example.org' in writers</pre>
* Search for files containing the text "important" which are in the trash
   <pre>fullText contains 'important' and trashed = true</pre>
* Search for files modified after June 4th 2012
   <pre>modifiedDate > '2012-06-04T12:00:00' // default time zone is UTC</pre><pre>modifiedDate > '2012-06-04T12:00:00-08:00'</pre>
* Search for files shared with the authorized user with "hello" in the name
   <pre>sharedWithMe and title contains 'hello'</pre>
* Search for files with a [custom file property](https://developers.google.com/drive/api/v2/properties) named `additionalID` with the value `8e8aceg2af2ge72e78`.
   <pre>properties has { key='additionalID' and value='8e8aceg2af2ge72e78' and visibility='PRIVATE' }</pre>

Source of this guide is [[!DNL Google Drive] documentation](https://developers.google.com/drive/api/v2/search-shareddrives).

-->
