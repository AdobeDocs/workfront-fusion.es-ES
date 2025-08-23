---
title: Módulos de Box
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan Box y conectarlo a varias aplicaciones y servicios de terceros. monitoriza una carpeta especificada para comprobar si hay cambios en el archivo, modificar o eliminar archivos existentes, o cargar nuevos archivos en una carpeta.
author: Becky
feature: Workfront Fusion
exl-id: 9e741dce-05a6-4e13-8d58-fbe3b4900d7e
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1542'
ht-degree: 29%

---

# Módulos de Box

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!DNL Box], así como conectarlo a varias aplicaciones y servicios de terceros. monitoriza una carpeta especificada para comprobar si hay cambios en el archivo, modificar o eliminar archivos existentes, o cargar nuevos archivos en una carpeta.

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

Para usar módulos [!DNL Box], debe tener una cuenta de [!DNL Box].

## Información de API de Box

El conector Box utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Dirección URL base</td> 
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

Al configurar módulos de [!DNL Box], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL Box] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Activadores](#triggers)
* [Acciones](#actions)
* [Búsquedas](#searches)

### Activadores

* [[!UICONTROL Nuevo evento de archivo]](#new-file-event)
* [Nuevo evento de carpeta](#new-folder-event)
* [[!UICONTROL Ver archivos]](#watch-files)

#### [!UICONTROL Nuevo evento de archivo]

Este módulo de déclencheur instantáneo inicia un escenario cuando la acción seleccionada se produce en un archivo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>Seleccione el webhook que desee utilizar para ver los mensajes salientes o agregue un webhook. </p><p>Para agregar un webhook, haga clic en <strong>[!UICONTROL Agregar]</strong> e introduzca el nombre y la conexión del webhook, el archivo que desea ver y los déclencheur que desea ver.</p> <p> Para obtener instrucciones acerca de cómo conectar su cuenta de [!UICONTROL Box] a [!UICONTROL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Conectarse a un servicio: instrucciones básicas</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Nuevo evento de carpeta

Este módulo de déclencheur instantáneo inicia un escenario cuando la acción de selección se produce en la carpeta.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>Seleccione el webhook que desee utilizar para ver los mensajes salientes o agregue un webhook. </p><p>Para agregar un webhook, haga clic en <strong>[!UICONTROL Agregar]</strong> e introduzca el nombre y la conexión del webhook, la carpeta que desea ver y los déclencheur que desea ver.</p> <p> Para obtener instrucciones acerca de cómo conectar su cuenta de [!UICONTROL Box] a [!UICONTROL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Conectarse a un servicio: instrucciones básicas</a>.</p> </td> 
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
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Box] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
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
* [Obtener una carpeta](#get-a-folder)
* [Obtener metadatos de carpeta](#get-folder-metadata)
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
   <td> <p>For instructions about connecting your [!DNL Box] account to Workfront Fusion, see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to Adobe Workfront Fusion - Basic instructions</a>.</p> </td> 
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
   <td> <p>For instructions about connecting your [!DNL Box] account to Workfront Fusion, see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to Adobe Workfront Fusion - Basic instructions</a>.</p> </td> 
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
   <td> <p>For instructions about connecting your [!DNL Box] account to Workfront Fusion, see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to Adobe Workfront Fusion - Basic instructions</a>.</p> </td> 
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
   <td> <p>For instructions about connecting your [!DNL Box] account to Workfront Fusion, see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to Adobe Workfront Fusion - Basic instructions</a>.</p> </td> 
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
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Box] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
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
   <td role="rowheader">[!UICONTROL Estado de sincronización]</td> 
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
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Box] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
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
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Box] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
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

Este módulo de acción realiza una llamada personalizada a la API Box.



<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Bynder] a Workfront Fusion, consulte <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Bynder] a Workfront Fusion </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>Escriba una ruta relativa a <code>https://api.box.com</code>. <p>Ejemplo: <code>/2.0/users/me</code></p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td> 
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

Este módulo de acción crea o actualiza los metadatos de una carpeta.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Box] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
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

#### Buscar contenido

Este módulo de búsqueda busca los elementos disponibles para el usuario o para toda la empresa.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Box] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
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
   <td> <p>Para buscar en una carpeta específica, para cada carpeta que desee buscar, haga clic en <b>Agregar elemento</b> e introduzca el identificador de la carpeta. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Creado Desde]</td> 
   <td> <p>Para buscar recursos creados en un intervalo de fechas determinado, introduzca la fecha más antigua del intervalo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Creado en]</td> 
   <td> <p>Para buscar recursos creados en un intervalo de fechas determinado, introduzca la fecha más reciente en el intervalo.</p> </td> 
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
   <td> <p>Para buscar recursos en un intervalo de tamaño específico, escriba el extremo pequeño del intervalo, en bytes.</p> </td> 
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
   <td> <p>Introduzca o asigne el número máximo de resultados que desea que devuelva el módulo en cada ciclo de ejecución.</p> </td> 
  </tr> 
 </tbody> 
</table>


