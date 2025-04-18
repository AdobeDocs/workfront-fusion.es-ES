---
title: Módulos de Dropbox
description: En un escenario de  [!DNL Adobe Workfront Fusion] , puede automatizar los flujos de trabajo que utilizan Dropbox, así como conectarlo a varias aplicaciones y servicios de terceros. Esto le permite automatizar actividades como la monitorización, la búsqueda, la recuperación, la enumeración, y la creación y edición de archivos y carpetas en el Dropbox.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 29ce5940-4d71-4719-ab5e-f03c44b28c8c
source-git-commit: 8a4e54a4c1783e4bc679778c6fcf21dcb4d3d537
workflow-type: tm+mt
source-wordcount: '3203'
ht-degree: 83%

---

# Módulos de [!DNL Dropbox]

En un escenario de [!DNL Adobe Workfront Fusion], puede automatizar los flujos de trabajo que utilizan [!UICONTROL Dropbox] o [!DNL Dropbox Business], así como conectarlo a varias aplicaciones y servicios de terceros. Esto le permite automatizar actividades como la monitorización, la búsqueda, la recuperación, la enumeración, y la creación y edición de archivos y carpetas en el.[!UICONTROL Dropbox].

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
   <p>Actual: Su organización debe adquirir Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

* Para usar módulos de [!DNL Dropbox], debe tener una cuenta de [!DNL Dropbox].

>[!IMPORTANT]
>
>Dropbox debe aprobar las aplicaciones con más de 50 usuarios.
>
>Para obtener más información, busque “Aprobación de producción” en la guía para desarrolladores de Dropbox.

## Información de API de Dropbox

El conector de Dropbox utiliza lo siguiente:

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

1. En cualquier módulo, haga clic en **[!UICONTROL Agregar]** junto al cuadro Conexión.

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
        <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Introduza su [!UICONTROL Client ID] de [!UICONTROL Dropbox]. </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Introduzca su [!DNL Dropbox] [!UICONTROL Client Secret]. </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Account Type]</td>
        <td>Seleccione si desea conectarse a una cuenta personal o a una cuenta de empresa de Dropbox (Dropbox Business).</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Excluir encabezado dropbox-api-path-root]</td>
        <td>Active esta opción para excluir el encabezado dropbox-api-path-root en las aplicaciones de Dropbox con acceso a la carpeta de la aplicación.</td>
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

#### [!UICONTROL Ver archivos]

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

* [[!UICONTROL Descargar un archivo]](#download-a-file)
* [[!UICONTROL Obtener metadatos de una carpeta]](#get-a-folder-metadata)
* [[!UICONTROL Listar todos los archivos/subcarpetas de una carpeta]](#list-all-filessubfolders-in-a-folder)
* [[!UICONTROL Revisiones de archivos de lista]](#list-file-revisions)
* [[!UICONTROL Buscar archivos/carpetas]](#search-filesfolders)

#### [!UICONTROL Descargar un archivo]

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

#### [!UICONTROL Obtener metadatos de carpeta]

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

#### [!UICONTROL Enumerar todos los archivos/subcarpetas de una carpeta]

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

#### [!UICONTROL Enumerar revisiones de archivos]

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
   <td> <p><b>Ruta de archivo</b></p> <p>Introduzca o asigne la ruta de destino al archivo.</p> <p><b>Archivo</b></p> <p>Seleccione el archivo en el menú.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Límite</p> </td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo enumere durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Buscar archivos/carpetas]

Este módulo de búsqueda busca registros en un objeto en [!DNL Dropbox] que coincidan con la consulta de búsqueda especificada.

Puede asignar esta información en módulos subsiguientes en el escenario.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Dropbox] a [!DNL Workfront Fusion], consulte <a href="#create-a-connection-to-dropbox" class="MCXref xref">Crear una conexión con [!DNL Dropbox]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search] </td> 
   <td> <p>Introduzca el término de búsqueda.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Seleccione la carpeta en la que desea buscar. Este módulo busca en toda la cuenta de [!DNL Dropbox] si no selecciona ninguna carpeta.</p> </td> 
  </tr> 
  <tr> 
   <td>Estado del archivo</td> 
   <td> <p> Seleccione el estado del archivo que desea incluir en la búsqueda.</p> </td> 
  </tr> 
  <tr> 
   <td>Categorías de archivo</td> 
   <td> <p> Seleccione las categorías de archivos que desee incluir en la búsqueda.</p> </td> 
  </tr> 
  <tr> 
   <td>Extensiones de archivo</td> 
   <td> <p>Para cada extensión de archivo que desee incluir en la búsqueda, haga clic en <b>Agregar elemento</b> y escriba o asigne la extensión de archivo.</p> </td> 
  </tr> 
  <tr> 
   <td>Límite </td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Módulos para crear y editar archivos y carpetas de [!DNL Dropbox]

* [[!UICONTROL Crear una carpeta]](#create-a-folder)
* [[!UICONTROL Crear o sobrescribir un archivo de texto]](#createoverwrite-a-text-file)
* [[!UICONTROL Crear/actualizar un vínculo compartido]](#createupdate-a-share-link)
* [[!UICONTROL Eliminar archivo/carpeta]](#delete-a-filefolder)
* [[!UICONTROL Mover un archivo/carpeta]](#move-a-filefolder)
* [[!UICONTROL Cambiar el nombre de un archivo o carpeta]](#rename-a-filefolder)
* [[!UICONTROL Restaurar un archivo]](#restore-a-file)
* [[!UICONTROL Cargar] un archivo](#upload-a-file)

#### [!UICONTROL Crear una carpeta]

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
   <td> <p>Introduzca o asigne la ruta donde desea crear una nueva carpeta.</p> <p>Nota:   <p>Si usa una cuenta de [!DNL Dropbox Business] (con espacios de equipo), debe quitar la barra <code>/</code> o no hacer clic en <strong>Haga clic aquí para elegir la carpeta</strong> para crear una carpeta de equipo en la raíz.</p> <p>Si no se quita la barra oblicua, se devuelve un error <code>[409] path/malformed_path/..</code>.</p> </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Auto rename]</td> 
   <td> <p> Active esta opción para cambiar el nombre de la nueva carpeta, si ya existe una carpeta con el mismo nombre en la ubicación de destino.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Crear o sobrescribir un archivo de texto]

Este módulo de acción crea un archivo DOC o sobrescribe el contenido de uno existente.

Especifique el archivo de origen y la carpeta.

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
   <td> <p> Seleccione si desea crear o sobrescribir un archivo DOC.</p><ul><li><b>Crear</b></p>Seleccione la carpeta en la que desea crear un archivo.</li><li><b>Sobrescribir</b><p>Seleccione cómo desea elegir el archivo que desea sobrescribir y, a continuación, asigne la ruta del archivo o seleccione el archivo. </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Source File]</p> </td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el contenido del archivo de origen. </p> <p>Si está creando un archivo, seleccione <b>Vacío</b>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Crear/actualizar un vínculo compartido]

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
   <td> <p style="font-weight: bold;">[!UICONTROL File Path]</p> <p>Introduzca o asigne la ruta al archivo de destino.</p> <p style="font-weight: bold;">[!UICONTROL File]</p> <p>Seleccione el archivo de destino.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Requested Visibility]</p> </td> 
   <td> <p>Seleccione si el vínculo es público, de equipo o si está restringido con contraseña.</p> <p><b>Nota:</b></p><p> [!UICONTROL Solo equipo] solo está disponible para cuentas de Dropbox Business. [!UICONTROL Acceso con contraseña] solo está disponible para [!DNL Dropbox Pro] o cuentas de Dropbox Business.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Link's Expiration Date]</td> 
   <td> <p> Introduzca la fecha y la hora en que caducará el vínculo y dejará de ser accesible. Si este campo se deja vacío, el vínculo no caducará. Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">Coerción de tipos</a>.</p>  </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Link's Access Level]</p> </td> 
   <td> <p>Establezca el permiso para el destinatario del vínculo.</p> <ul><li><strong>[!UICONTROL Visor]</strong> <p>Los usuarios que utilizan el vínculo pueden ver el contenido y realizar comentarios sobre él.</p> </li><li><strong>[!UICONTROL Editor]</strong><p> Los usuarios que utilizan el vínculo pueden editar, ver y comentar el contenido. Este nivel de acceso solo está disponible para documentos basados en la nube.</p> </li><li><strong>[!UICONTROL Máximo]</strong> <p>Los usuarios que utilicen el vínculo reciben el nivel de acceso máximo al que puede establecer el vínculo.</p></li><ul> </td> 
  </tr> 
 </tbody> 
</table>


#### [!UICONTROL Eliminar un archivo o carpeta]

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
   <td> <p>[!UICONTROL Ruta de archivo o carpeta] / [!UICONTROL Archivo o carpeta]</p> </td> 
   <td> <p style="font-weight: bold;">[!UICONTROL File/Folder Path]</p> <p>Introduzca o asigne la ruta de destino al archivo o carpeta.</p> <p style="font-weight: bold;">[!UICONTROL File/Folder]</p> <p>Seleccione el archivo o la carpeta en el menú.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Mover un archivo/carpeta]

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
   <td>[!UICONTROL Forma de seleccionar archivos / carpetas] </td> 
   <td> <p>Seleccione si desea asignar o introducir la ruta del archivo o la carpeta, o bien seleccione el archivo o la carpeta manualmente.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Archivo / Ruta de carpeta] /</p> </td> 
   <td> <p style="font-weight: bold;">[!UICONTROL File/Folder Path]</p> <p>Introduzca o asigne la ruta de destino al archivo o carpeta.</p> <p style="font-weight: bold;">[!UICONTROL File/Folder]</p> <p>Seleccione si va a mover un archivo o una carpeta y, a continuación, el archivo o la carpeta.</p> </td> 
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
   <td> <p>Habilite esta opción para asegurarse de que si existe un archivo o una carpeta con el mismo nombre, el módulo cambie el nombre del nuevo archivo o carpeta añadiendo ([!UICONTROL NUMBER]) después del nombre del archivo o carpeta. De lo contrario, se sobrescribirá el archivo o la carpeta de la ubicación de destino.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Allow ownership transfer]</p> </td> 
   <td> <p>Habilite esta opción para permitir los movimientos por propietario, incluso si se produce una transferencia de propiedad del contenido que se está moviendo.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Cambiar el nombre de un archivo o carpeta]

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
   <td> <p style="font-weight: bold;">Ruta de archivo/carpeta</p> <p>Introduzca o asigne la ruta de destino al archivo o carpeta.</p> <p style="font-weight: bold;">Archivo/Carpeta</p> <p>Seleccione si va a mover un archivo o una carpeta y, a continuación, el archivo o la carpeta.</p> </td> 
  </tr> 
  <tr> 
   <td>Cambiar nombre </td> 
   <td> <p>Introduzca el nuevo nombre del archivo, incluida su extensión.</p> </td> 
  </tr> 
 </tbody> 
</table>


#### [!UICONTROL Restaurar un archivo]

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

#### [!UICONTROL Cargar un archivo]

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
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> <p><b>Nota:</b></p><p> El tamaño máximo del archivo cargado es de 150 MB.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Overwrite an existing file]</td> 
   <td> <p> Active esta opción para reemplazar el archivo existente con el nuevo archivo. Si esta opción se deja deshabilitada, se cambiará el nombre del archivo cargado.</p> </td> 
  </tr> 
 </tbody> 
</table>


### Otros módulos

#### [!UICONTROL Realizar una llamada de API]

Este módulo de acción le permite realizar una llamada autenticada personalizada a la API de [!DNL Dropbox]. De este modo, puede crear una automatización del flujo de datos imposibles de realizar por los otros [!DNL Dropbox] módulos.

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
   <td> <p>Escriba una ruta relativa a Escriba una ruta relativa a <code>https://api.dropboxapi.com</code>. Por ejemplo: <code>/2/files/list_folder</code></p>  </td> 
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

>[!BEGINSHADEBOX]

**Ejemplo:**

La siguiente llamada de API devuelve los primeros 10 archivos de la carpeta [!DNL /Text files] de su cuenta de [!DNL Dropbox]:

URL: `/2/files/list_folder`

Cuerpo:

```
{
"path": "/Text files",
"limit": 10,
"recursive": false,
"include_deleted": false
}
```

Las coincidencias de la búsqueda se pueden encontrar en la salida del módulo en [!UICONTROL Paquete] > [!UICONTROL Cuerpo] > entradas.

En nuestro ejemplo, se devolvieron 10 tickets.

>[!ENDSHADEBOX]

## Problemas comunes

* [No se puede cargar o actualizar un archivo](#unable-to-upload-or-update-a-file)
* [La imagen a la que se hace referencia mediante un vínculo compartido no se representa](#image-referenced-via-a-shared-link-does-not-render)

### No se puede cargar o actualizar un archivo

Los siguientes pueden ser motivos por los que falla la carga o actualización de un archivo:

* El archivo cargado es demasiado grande y supera el tamaño máximo de archivo permitido para el plan de [!DNL Dropbox], o bien se ha utilizado toda la cuota de almacenamiento de la cuenta de [!DNL Dropbox]. Debe eliminar los archivos existentes de su cuenta de [!DNL Dropbox] o actualizar su plan.
* La carpeta seleccionada anteriormente, a la que se está cargando el archivo, ya no existe. El escenario se detiene y debe volver a seleccionar la carpeta de destino.

### La imagen a la que se hace referencia mediante un vínculo compartido no se representa

La dirección URL devuelta por el [!UICONTROL Dropbox] >[!UICONTROL Crear un vínculo compartido] no vincula directamente a una imagen, sino a una página de [!DNL Dropbox]. Para forzar la descarga de la imagen, sustituya el `?dl=0` final por `?dl=1`. Para forzar el procesamiento de la imagen (por ejemplo, en un explorador Web o en Facebook Messenger), añada `&raw=1` a la dirección URL.

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
