---
title: Módulos de Box
description: En un escenario de [!DNL Adobe Workfront Fusion] puede automatizar los flujos de trabajo que usan Box, así como conectarlo a varias aplicaciones y servicios de terceros. monitoriza una carpeta especificada para comprobar si hay cambios en el archivo, modificar o eliminar archivos existentes, o cargar nuevos archivos en una carpeta.
author: Becky
feature: Workfront Fusion
exl-id: 9e741dce-05a6-4e13-8d58-fbe3b4900d7e
source-git-commit: 0ed33cbed2b8ed4ab2c89c86b7e8f37b2683ec75
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 33%

---

# Módulos de Box

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!DNL Box], así como conectarlo a varias aplicaciones y servicios de terceros. monitoriza una carpeta especificada para comprobar si hay cambios en el archivo, modificar o eliminar archivos existentes, o cargar nuevos archivos en una carpeta.

Para obtener instrucciones sobre cómo crear un escenario, vea los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md). Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

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
   <p>Vigente: No hay requisito de licencia de Workfront Fusion</p>
   <p>O</p>
   <p>Legado: Workfront Fusion para la automatización e integración del trabajo </p>
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

Para usar módulos [!DNL Box], debe tener una cuenta de [!DNL Box].

## Información de API de Box

El conector Box utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL básica</td> 
   <td> https://api.box.com/2.0
    </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> Versión 2.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 3.0.3</td> 
  </tr>
 </tbody> 
 </table>

## Módulos de [!DNL Box] y sus campos

Al configurar módulos de [!DNL Box], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Box] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, consulte [Información de mapa de una módulo a otra](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Activadores](#triggers)
* [Acciones](#actions)
* [Búsquedas](#searches)

### Activadores

* [[!UICONTROL Nuevo evento de archivo]](#new-file-event)
* [Nuevo evento de carpeta](#new-folder-event)
* [[!UICONTROL Ver archivos]](#watch-files)

#### [!UICONTROL Nuevo evento Archivo]

Este módulo de déclencheur instantáneo inicia un escenario cuando la acción seleccionada se produce en un archivo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>Seleccione el webhook que desee utilizar para ver los mensajes salientes o agregue un webhook. </p><p>Para añadir un webhook, haga clic en <strong>[! UICONTROL añadir]</strong> e introduzca el nombre y la conexión del webhook, el archivo que desea ver y los desencadenadores que desea ver.</p> <p> Para obtener instrucciones sobre cómo conectar su [! UICONTROL Box] cuenta a [! UICONTROL Workfront Fusion], consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Conectarse a un servicio: instrucciones básicas</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Nuevo Carpeta evento

Esta módulo de activación instantánea inicia un escenario cuando la acción de selección ocurre en la carpeta.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>Seleccione el webhook que desea usar para ver los mensajes salientes o agregue un webhook. </p><p>Para agregar un webhook, haga clic en <strong>[!UICONTROL Agregar]</strong> e introduzca el nombre y la conexión del webhook, la carpeta que desea ver y los déclencheur que desea ver.</p> <p> Para obtener instrucciones acerca de cómo conectar su cuenta de [!UICONTROL Box] a [!UICONTROL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Conectarse a un servicio: instrucciones básicas</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Ver archivos]

Este módulo de activación se inicia cuando se añade un archivo nuevo o se actualiza un archivo existente en una carpeta que se está viendo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Box] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  <tr> 
   <td role="rowheader">Ver en carpeta</td> 
   <td> <p>Seleccione la carpeta que desee ver. Un escenario puede ver una sola carpeta.</p> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Ver</td> 
   <td> <p>Seleccione el tipo de archivos que desee ver. </p> 
    <ul> 
     <li> <p><strong>Solo archivos nuevos</strong> </p> <p>El escenario se iniciará cuando se añada un nuevo archivo.</p> </li> 
     <li> <p><strong>Nuevos archivos y todos los cambios</strong> </p> <p>El escenario se inicia cuando se añade un archivo o cuando se modifica el contenido o un atributo de archivo (como el nombre).</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Número máximo de archivos descargados</p> </td> 
   <td> <p>Introduzca el número máximo de archivos que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Acciones

<!--* [[!UICONTROL Delete a file]](#delete-a-file)
* [[!UICONTROL Get a file]](#get-a-file)
* [[!UICONTROL Update a file]](#update-a-file)
* [[!UICONTROL Upload] a file](#upload-a-file)-->
* [Crear una carpeta](#create-a-folder)
* [Obtenga una Carpeta](#get-a-folder)
* [Obtener metadatos de Carpeta](#get-folder-metadata)
* [Realizar una llamada de API](#make-an-api-call)
* [Actualizar metadatos de carpeta](#update-folder-metadata)

<!--#### [!UICONTROL Delete a file] 

This action module deletes a file.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your [!DNL Box] account to [!DNL Workfront Fusion], see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to [!DNL Adobe Workfront Fusion] - Basic instructions</a>.</p> </td> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>Enter or map the unique ID of the file that you want the module to delete.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a file]

This action module downloads a file.

You specify the ID of the file.

>[!NOTE]
>
>This module is useful for providing files to subsequent modules.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your [!DNL Box] account to [!DNL Workfront Fusion], see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to [!DNL Adobe Workfront Fusion] - Basic instructions</a>.</p> </td> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>Enter or map the unique ID of the file that you want the module to retrieve.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a file] 

This action module updates a file.

You specify the ID of the file.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your [!DNL Box] account to [!DNL Workfront Fusion], see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to [!DNL Adobe Workfront Fusion] - Basic instructions</a>.</p> </td> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>Enter or map the unique ID of the file that you want the module to update.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Select a source file from a previous module, or map the source file's name and data.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a file] 

This action module uploads a file.

You specify the file. You can also provide a new filename for the file.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your [!DNL Box] account to [!DNL Workfront Fusion], see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to [!DNL Adobe Workfront Fusion] - Basic instructions</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td> <p>Select the folder where you want to upload the file.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Select a source file from a previous module, or map the source file's name and data.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>If this module is not successful, consider the following:
>
>* The size of the file might exceed the maximum file size limit for your [!DNL Box] plan, or you may have used all of your [!DNL Box] account's storage quota. To get more storage space, delete existing files from [!DNL Box] or upgrade your [!DNL Box] account.
>* [!DNL Box] does not upload more than one files with the same name to a single folder. If the destination folder contains a file with the same name as the file being uploaded, the scenario run terminates with an error. To avoid this, rename the file. If you want to update the file, use the **[!UICONTROL Update a file]** module.-->

#### Crear una carpeta

Este módulo de acción crea una nueva carpeta vacía dentro de la carpeta principal especificada.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Box] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td> <p>Introduzca o asigne un nombre para la nueva carpeta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Carpeta principal]</td> 
   <td> <p>Seleccione la carpeta donde desea crear la nueva carpeta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Acceso de correo electrónico de carga de carpeta]</td> 
   <td> <p>Cuando se ha establecido este parámetro, los usuarios pueden enviar archivos por correo electrónico a la dirección de correo electrónico que se ha creado automáticamente para esta carpeta. Las opciones de colaboradores permiten solo correos electrónicos registrados para colaboradores.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[! Estado de sincronización UICONTROL]</td> 
   <td> <p>Especifica si una carpeta se debe sincronizar o no con el dispositivo de un usuario. Esto se usa en Box Sync (interrumpido) y no en Box Drive.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Obtener una carpeta

Este módulo de acción recupera los detalles de una carpeta, incluidas las primeras 100 entradas de la carpeta.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Box] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td> <p>Seleccione la carpeta cuyos detalles desea recuperar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Obtener metadatos de carpeta

Este módulo de acción recupera los metadatos de la carpeta por ID de carpeta.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Box] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scope]</td> 
   <td> <p>Seleccione el ámbito que desea utilizar para esta recuperación de metadatos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td> <p>Seleccione la carpeta para la que desea recuperar los metadatos.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Realizar una llamada de API

Esta acción módulo realiza una llamada personalizada a la API de Box.



<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Bynder] a [!DNL Workfront Fusion], consulte <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Bynder] a [!DNL Workfront Fusion] </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>Escriba una ruta relativa a <code>https://api.box.com</code>. <p>Ejemplo: <code>/2.0/users/me</code></p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, consulte <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">petición HTTP métodos</a>.</p> </td> 
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
 </tbody> 
</table>

#### Actualizar metadatos de carpeta

Esta acción módulo crea o actualiza el metadatos de una carpeta.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Box] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scope]</td> 
   <td> <p>Seleccione el ámbito que desea utilizar para esta actualización de metadatos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td> <p>Seleccione la carpeta para la que desee actualizar los metadatos.</p> </td> 
  </tr> 
 </tbody> 
</table>


### Búsquedas

#### Search para el contenido

Este búsqueda módulo busca los elementos que están disponibles para el usuario o para la empresa emtire.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Box] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td> <p>Introduzca o asigne la cadena que desea buscar. Esta consulta se compara con nombres de elementos, descripciones, contenido de texto de archivos y varios otros campos de los diferentes tipos de elementos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scope]</td> 
   <td> <p>Seleccione si está buscando contenido asociado con el usuario cuyas credenciales se utilizan para la conexión utilizada en este módulo o buscando contenido asociado con toda la empresa.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td> <p>Seleccione si desea buscar archivos, carpetas o vínculos web.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort]</td> 
   <td> <p>Seleccione si desea ordenar por relevancia o por fecha de modificación.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Contenido de papelera]</td> 
   <td> <p>Seleccione si desea buscar contenido enviado a la papelera o contenido que no se haya enviado a la papelera.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Id. de carpeta principal]</td> 
   <td> <p>Para búsqueda en una carpeta específica, para cada carpeta que desee búsqueda, haga clic en <b>añadir elemento</b> e introduzca el ID de la carpeta. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[! UICONTROL Creado desde]</td> 
   <td> <p>Para búsqueda los activos creados en un intervalo de fecha determinado, introduzca la fecha más temprana del intervalo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[! UICONTROL Creado para]</td> 
   <td> <p>Para búsqueda para activos creado en un intervalo de fecha determinado, introduzca la última fecha del intervalo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Actualizado Desde]</td> 
   <td> <p>Para buscar recursos actualizados en un intervalo de fechas determinado, escriba la fecha más temprana en el intervalo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL actualizado a]</td> 
   <td> <p>Para buscar recursos actualizados en un intervalo de fechas determinado, introduzca la fecha más reciente en el intervalo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td> <p>Para cada atributo que desee devolver en la respuesta del módulo, haga clic en <b>Agregar elemento</b> e introduzca el campo.</p><p>Esto se puede utilizar para solicitar campos que normalmente no se devuelven en una respuesta estándar. Tenga en cuenta que especificar este parámetro tendrá el efecto de que no se devuelve ninguno de los campos estándar en la respuesta a menos que se especifique explícitamente. </p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Extensiones de archivo]</td> 
   <td> <p>Para limitar la búsqueda a extensiones de archivo específicas, introduzca una lista de extensiones de archivo separados por coma.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tamaño Desde]</td> 
   <td> <p>Para búsqueda para activos en un rango de tamaño específico, introduzca el extremo pequeño del intervalo, en bytes.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tamaño A]</td> 
   <td> <p>Para buscar recursos en un intervalo de tamaño específico, introduzca el extremo grande del intervalo, en bytes.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Propietario ID de usuario]</td> 
   <td> <p>Para buscar recursos propiedad de usuarios específicos, introduzca una lista de ID de propietario separados por comas.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de resultados que desea que la módulo devuelva en cada ciclo de ejecución.</p> </td> 
  </tr> 
 </tbody> 
</table>


