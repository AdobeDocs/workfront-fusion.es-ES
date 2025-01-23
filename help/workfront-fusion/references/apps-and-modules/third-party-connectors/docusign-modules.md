---
title: Módulos de DocuSign
description: Los módulos de  [!DNL Adobe Workfront Fusion DocuSign]  le permiten supervisar y recuperar el estado de los sobres, buscar y recuperar sobres o descargar y enviar un documento para iniciar sesión en su cuenta de  [!DNL DocuSign] .
author: Becky
draft: Probably
feature: Workfront Fusion, Digital Content and Documents
exl-id: 94a823a6-3c70-42a1-b6cf-298591dbca15
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '1631'
ht-degree: 85%

---

# Módulos de DocuSign

Los módulos [!DNL DocuSign] de [!DNL Adobe Workfront Fusion] le permiten supervisar y recuperar el estado de los sobres, buscar y recuperar sobres o descargar y enviar un documento para iniciar sesión en su cuenta de [!DNL DocuSign].

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

Para usar módulos [!DNL DocuSign], debe tener una cuenta de [!DNL DocuSign].

## Información de API de DocuSign

El conector de DocuSign utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>1.18.11</td> 
  </tr>
 </tbody> 
 </table>

## Conectar [!DNL DocuSign] a [!DNL Workfront Fusion] {#connect-docusign-to-workfront-fusion}

Para crear una conexión para los módulos de [!DNL DocuSign]:

1. Haga clic en **[!UICONTROL Add]** junto al cuadro [!UICONTROL Connection] cuando empiece a configurar el primer módulo de [!DNL DocuSign].
1. Introduzca lo siguiente:

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td>Escriba un nombre para la nueva conexión de [!DNL DocuSign]</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Account type]</td> 
      <td>Seleccione si la cuenta a la que desea conectarse es una cuenta de producción o una cuenta de demostración.</td> 
     </tr> 
    </tbody> 
   </table>

1. Continúe tal como se describe en [Crear una conexión a [!DNL Adobe Workfront Fusion] : instrucciones básicas](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md#connect).

## Módulos de [!DNL DocuSign] y sus campos

Al configurar módulos de [!DNL DocuSign], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL DocuSign] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Activadores](#triggers)
* [Acciones](#actions)

### Activadores

#### [!UICONTROL Watch envelopes]

Este módulo de activador inicia un escenario cuando se envía, entrega, firma, completa o rechaza un sobre.

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL DocuSign] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>Seleccione la cuenta que contiene los registros que desea ver.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event type]</td> 
   <td> <p> Seleccione el tipo de evento que desea ver.</p> 
    <ul> 
     <li>[!UICONTROL Document completed]</li> 
     <li>[!UICONTROL Document declined]</li> 
     <li>[!UICONTROL Document sent]</li> 
     <li>[!UICONTROL Document signed]</li> 
     <li>[!UICONTROL New document in Inbox]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Output fields]</p> </td> 
   <td> <p>Seleccione los campos que desea incluir en la salida del módulo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Introduzca o asigne el número máximo de registros con los que desea que trabaje el módulo durante cada ciclo de ejecución de escenario.</td> 
  </tr> 
 </tbody> 
</table>

### Acciones

* [[!UICONTROL Custom API Call]](#custom-api-call)
* [[!UICONTROL Download a document]](#download-a-document)
* [[!UICONTROL Read an envelope]](#read-an-envelope)
* [[!UICONTROL Upload a file to an envelope]](#upload-a-file-to-an-envelope)
* [[!UICONTROL Create a new envelope]](#create-a-new-envelope)
* [[!UICONTROL Add Recipient to Envelope]](#add-recipient-to-envelope)
* [[!UICONTROL Add custom field]](#add-custom-field)
* [[!UICONTROL Modify custom field]](#modify-custom-field)
* [[!UICONTROL Send envelope]](#send-envelope)

#### [!UICONTROL Custom API Call]

Este módulo de acción le permite realizar una llamada de API personalizada.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL DocuSign] a [!DNL Workfront Fusion], consulte <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Conectar [!DNL DocuSign] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Account]</td> 
   <td>Introduzca o asigne la cuenta que desea usar para acceder a la API de [!DNL DocuSign].</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL URL]</td> 
   <td> <p>Escriba la dirección del servidor web con el que desea que interactúe el módulo.</p> <p>Puede escribir una dirección URL relativa, lo que significa que no tiene que incluir el protocolo (como <code>http://</code>) al principio. Esto sugiere al servidor web que la interacción se está produciendo en el servidor.</p> <p>Por ejemplo: <code>[!DNL /api/conversations].create</code></p>  </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar. Determina el tipo de contenido de la petición.</p> <p>Por ejemplo:<code> {"Content-type":"application/json"}</code></p> <p>Nota: Si se producen errores y es difícil determinar su origen, considere la posibilidad de modificar los encabezados basándose en la documentación de [!DNL Workfront]. Si la llamada de API personalizada devuelve un error de petición HTTP 422, intente utilizar un encabezado “Content-Type”:“text/plain”.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query String]</td> 
   <td> <p>Añada la consulta para la llamada de API en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td>Introduzca o asigne el número máximo de resultados con los que se va a trabajar durante un ciclo de ejecución.</td> 
  </tr> 
 </tbody> 
</table>

>[!INFO]
>
>**Ejemplo:** enumerar sobres
>
>La siguiente llamada de la API devuelve sobres a partir de la fecha especificada en su cuenta de [!DNL DocuSign]:
>
>**URL**: `/v2.1/accounts/{accountId}/envelopes/`
>
>**Método**: `GET`
>
>**Cadena de consulta**:
>
>* **Clave**: `from_date`
>
>* **Valor**: `YYYY-MM-DD`
>
>Especifica cuándo comienza la solicitud a comprobar los cambios de estado de los sobres de la cuenta.
>
>![](/help/workfront-fusion/references/apps-and-modules/assets/example-docusign-setup-350x770.png)
>
>El resultado se puede encontrar en la salida del módulo en Paquete > Cuerpo > Sobres.
>
>En nuestro ejemplo, se devolvieron 6 sobres:
>
>![](/help/workfront-fusion/references/apps-and-modules/assets/docusign-example-output-350x677.png)

#### [!UICONTROL Download a document]

Este módulo de acción descarga un solo documento.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL DocuSign] a [!DNL Workfront Fusion], consulte <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Conectar [!DNL DocuSign] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>Seleccione la cuenta que contiene el documento que desea descargar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> Introduzca o asigne el ID del sobre que desea descargar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Document ID]</p> </td> 
   <td> <p>Introduzca o asigne el ID del documento que desea descargar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Certificate]</td> 
   <td>Seleccione <strong>[!UICONTROL Yes]</strong> si desea incluir el certificado de firma de sobre en la descarga.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Documents by User ID]</td> 
   <td>Seleccione <strong>[!UICONTROL Yes]</strong> si desea permitir que los destinatarios recuperen documentos por identificador de usuario. Por ejemplo, si un usuario se incluye en dos órdenes de enrutamiento diferentes con distintas visibilidades, al utilizar esta opción se devuelven todos los documentos de ambas rutas.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Encrypt]</td> 
   <td>Seleccione <strong>[!UICONTROL Yes]</strong> si desea que los bytes de PDF devueltos en la respuesta se cifren para todos los administradores de claves configurados en su cuenta de [!DNL DocuSign].</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Language]</td> 
   <td>Seleccione el idioma.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show Changes]</td> 
   <td>Cuando se establece en <strong>[!UICONTROL Yes]</strong>, los campos modificados para el PDF devuelto se resaltan en amarillo y las firmas o iniciales opcionales se resaltan en rojo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watermark]</td> 
   <td> <p>Seleccione <strong>[!UICONTROL No]</strong> para eliminar la marca de agua de los documentos del PDF.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Read an envelope]

Este módulo de acción lee información sobre un sobre en [!DNL DocuSign] mediante el identificador del sobre.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL DocuSign] a [!DNL Workfront Fusion], consulte <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Conectar [!DNL DocuSign] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>Seleccione la cuenta que contiene el documento del que desea leer información.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> Introduzca o asigne el ID que contiene el documento del que desea leer información.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Seleccione las propiedades que desea que aparezcan en la salida del módulo. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a file to an envelope]

Este módulo carga un archivo especificado en un sobre existente de DocuSign.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL DocuSign] a [!DNL Workfront Fusion], consulte <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Conectar [!DNL DocuSign] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>Seleccione la cuenta que contiene el sobre en el que desea cargar un archivo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> Introduzca o asigne el ID del sobre en el que desea cargar un archivo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>Seleccione un archivo de origen de un módulo anterior o introduzca el nombre y los datos del archivo de origen.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a new envelope]

Este módulo de acción crea un nuevo sobre a partir de una plantilla. Devuelve el ID del nuevo sobre, así como el estado del nuevo sobre.

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td>

<td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de DocuSign a Workfront Fusion, consulte los artículos en <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Account] </td>
   <td> <p>Seleccione la cuenta que contiene el sobre en el que desea cargar un archivo.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader" >[!UICONTROL Template]</td>
   <td> <p> Seleccione la plantilla a partir de la que desea crear el nuevo sobre. Las plantillas están disponibles según el(la) [!UICONTROL Account] que haya seleccionado.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL After creation]
   </td> 
   <td> <p>Seleccione si desea guardar el sobre como borrador o enviarlo para su firma.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader" >[!UICONTROL Template recipients]</td>
    <td>Seleccione el destinatario de este sobre</td>
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Add Recipient to Envelope]

Este módulo de acción añade uno o más destinatarios a un sobre existente. Si el sobre ya se ha enviado, se envía un correo electrónico al destinatario. Este módulo no es válido para sobres que ya se han completado.

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr data-mc-conditions=""> 
    <td>[!UICONTROL Connection] </td>
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de DocuSign a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr data-mc-conditions="">
    <td>[!UICONTROL Account] </td>
   <td> <p>Seleccione la cuenta que contiene el sobre en el que desea añadir destinatarios.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Envelope ID]</td>
    <td>Seleccione o asigne el ID del sobre en el que desea añadir el destinatario.</td>
  </tr> 
  <tr data-mc-conditions="">
    <td role="rowheader">[!UICONTROL Recipient type]</td>
   <td> <p> Seleccione el tipo de destinatario que desea añadir al sobre.</p> 
    <ul> 
     <li> <p>[!UICONTROL Agent]</p> </li> 
     <li> <p>[!UICONTROL Carbon copy]</p> </li> 
     <li> <p>[!UICONTROL Certified delivery]</p> </li> 
     <li> <p>[!UICONTROL In-person signer]</p> </li> 
     <li> <p>[!UICONTROL Intermediary]</p> </li> 
     <li> <p>[!UICONTROL Signer]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Email]</td>
   <td> <p>Introduzca o asigne la dirección de correo electrónico del destinatario que desea añadir al sobre.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Name]</td>
   <td>Introduzca o asigne el nombre del destinatario que desea añadir al sobre.</td> 
  </tr> 
  <tr>
    <td>[!UICONTROL Routing order]</td>
   <td> <p>Introduzca o asigne el número de enrutamiento del destinatario. El número de enrutamiento determina el orden en que los destinatarios reciben y firman los documentos.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Email body]</td>
   <td>Introduzca o asigne el cuerpo (contenido) del correo electrónico que se envía al destinatario.</td> 
  </tr> 
  <tr>
    <td role="rowheader">[!UICONTROL Email subject]</td>
   <td>Introduzca o asigne el asunto del correo electrónico que se envía al destinatario.</td> 
  </tr> 
    <td role="rowheader">[!UICONTROL Private message]</td>
   <td> <li> <p>Solo el destinatario seleccionado ve el mensaje privado, así como el mensaje general. El mensaje privado tiene un límite de 1000 caracteres.</p> </li> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Authentication]</td> 
   <td> <p>Seleccione el método de autenticación que desee utilizar para confirmar la identidad del destinatario.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL None]</strong> </p> </li> 
     <li> <p><strong>[!UICONTROL Access code]</strong> </p> <p>Introduzca o asigne el código de acceso.</p> </li> 
     <li> <p><strong>[!UICONTROL Phone]</strong> </p> <p>Introduzca o asigne el número de teléfono</p> </li> 
     <li> <p><strong>[!UICONTROL SMS]</strong> </p> <p>Introduzca o asigne el número de teléfono</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Add custom field]

Este módulo de acción añade un campo personalizado al documento

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL DocuSign] a [!DNL Workfront Fusion], consulte <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Conectar [!DNL DocuSign] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>Seleccione la cuenta que contiene el documento en el que desea añadir un campo personalizado.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> Introduzca o asigne el ID del sobre que contiene el documento en el que desea añadir un campo personalizado.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Field name]</td> 
   <td>Introduzca o asigne un nombre para el nuevo campo que desea añadir.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Required]</td> 
   <td>Habilite esta opción si desea que el campo añadido sea un campo obligatorio.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show field]</td> 
   <td>Habilite esta opción si desea que el campo sea visible.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Value]</td> 
   <td>Introduzca o asigne el valor (contenido) del campo añadido. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Modify custom field]

Este módulo de acción modifica un campo personalizado mediante el nombre del campo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL DocuSign] a [!DNL Workfront Fusion], consulte <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Conectar [!DNL DocuSign] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>Seleccione la cuenta que contiene el documento en el que desea modificar un campo personalizado.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> Introduzca o asigne el ID del sobre que contiene el documento en el que desea modificar un campo personalizado.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Field ID]</td> 
   <td>Introduzca o asigne el ID del campo que desea modificar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Field name]</td> 
   <td>Introduzca o asigne el nombre del campo que desea modificar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Required]</td> 
   <td>Habilite esta opción si desea que el campo modificado sea obligatorio.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show field]</td> 
   <td>Habilite esta opción si desea que el campo sea visible.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Value]</td> 
   <td>Introduzca o asigne el valor (contenido) del campo modificado. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Send envelope]

Este módulo de acción envía un sobre borrador a sus destinatarios.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL DocuSign] a [!DNL Workfront Fusion], consulte <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Conectar [!DNL DocuSign] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>Seleccione la cuenta que contiene el sobre borrador que desea enviar a sus destinatarios.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> Introduzca o asigne el ID del sobre borrador que desea enviar a sus destinatarios.</p> </td> 
  </tr> 
 </tbody> 
</table>
