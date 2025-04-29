---
title: Módulos de Box
description: En un escenario de [!DNL Adobe Workfront Fusion] puede automatizar los flujos de trabajo que usan Box, así como conectarlo a varias aplicaciones y servicios de terceros. monitoriza una carpeta especificada para comprobar si hay cambios en el archivo, modificar o eliminar archivos existentes, o cargar nuevos archivos en una carpeta.
author: Becky
feature: Workfront Fusion
exl-id: 9e741dce-05a6-4e13-8d58-fbe3b4900d7e
source-git-commit: f02c4df01c7fad6bb9cdf4911512eef97e71c82b
workflow-type: tm+mt
source-wordcount: '918'
ht-degree: 72%

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

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Activadores](#triggers)
* [Acciones](#actions)

### Activadores

* [[!UICONTROL Nuevo evento]](#new-event)
* [[!UICONTROL Ver archivos]](#watch-files)

#### [!UICONTROL Nuevo evento]

Este módulo de activación instantáneo inicia un escenario cuando se añade, mueve, copia, elimina, bloquea o desbloquea un archivo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>Seleccione el webhook que desee utilizar para observar los mensajes salientes. Para añadir un webhook, haga clic en <strong>[!UICONTROL Add]</strong> e introduzca el nombre y la conexión del webhook.</p> <p> Para obtener instrucciones acerca de cómo conectar su cuenta de [!UICONTROL Box] a [!UICONTROL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Conectarse a un servicio: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Maximum number of returned events]</p> </td> 
   <td> <p>Introduzca el número máximo de eventos que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
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
   <td role="rowheader">Carpeta</td> 
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

* [[!UICONTROL Eliminar un archivo]](#delete-a-file)
* [[!UICONTROL Obtener un archivo]](#get-a-file)
* [[!UICONTROL Actualizar un archivo]](#update-a-file)
* [[!UICONTROL Subir] un archivo](#upload-a-file)

#### [!UICONTROL Eliminar un archivo]

Este módulo de acción elimina un archivo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Box] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>Introduzca o asigne el ID único del archivo que desea que elimine el módulo.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Obtener un archivo]

Este módulo de acción descarga un archivo.

Especifique el ID del archivo.

>[!NOTE]
>
>Este módulo es útil para proporcionar archivos a los módulos posteriores.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Box] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>Introduzca o asigne el ID único del archivo que desea que recupere el módulo.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Actualizar un archivo]

Este módulo de acción actualiza un archivo.

Especifique el ID del archivo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Box] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>Introduzca o asigne el identificador único del archivo que desea que el módulo actualice.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Cargar un archivo]

Este módulo de acción carga un archivo.

Usted especifica el archivo. También puede proporcionar un nuevo nombre para el archivo.

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
   <td> <p>Seleccione la carpeta en la que desea cargar el archivo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Si este módulo no se ejecuta correctamente, tenga en cuenta lo siguiente:
>
>* Es posible que el tamaño del archivo supere el tamaño máximo de archivo para el plan de [!DNL Box] o que haya utilizado toda la cuota de almacenamiento de su cuenta de [!DNL Box]. Para obtener más espacio de almacenamiento, elimine los archivos existentes de [!DNL Box] o actualice la cuenta de [!DNL Box].
>* [!DNL Box] no carga más de un archivo con el mismo nombre en una sola carpeta. Si la carpeta de destino contiene un archivo con el mismo nombre que el archivo que se está cargando, la ejecución del escenario finalizará con un error. Para evitarlo, cambie el nombre del archivo. Si desea actualizar el archivo, utilice el módulo **[!UICONTROL Actualizar un archivo]**.
