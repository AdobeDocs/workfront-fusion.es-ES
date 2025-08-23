---
title: Módulos de DocuSign
description: Los módulos de  [!DNL Adobe Workfront Fusion DocuSign]  le permiten supervisar y recuperar el estado de los sobres, buscar y recuperar sobres o descargar y enviar un documento para iniciar sesión en su cuenta de  [!DNL DocuSign] .
author: Becky
draft: Probably
feature: Workfront Fusion, Digital Content and Documents
exl-id: 94a823a6-3c70-42a1-b6cf-298591dbca15
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '2244'
ht-degree: 65%

---

# Módulos de DocuSign

Los módulos de Adobe Workfront Fusion [!DNL DocuSign] le permiten supervisar y recuperar el estado de los sobres, buscar y recuperar sobres o descargar y enviar un documento para iniciar sesión en su cuenta de [!DNL DocuSign].

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
   <p>Actual: Su organización debe comprar Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

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

## Conexión de [!DNL DocuSign] a Workfront Fusion {#connect-docusign-to-workfront-fusion}

Para crear una conexión para los módulos de [!DNL DocuSign]:

1. Haga clic en **[!UICONTROL Añadir]** junto al cuadro [!UICONTROL Conexión] cuando empiece a configurar el primer módulo de [!DNL DocuSign].
1. Introduzca lo siguiente:

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td>Escriba un nombre para la nueva conexión [!DNL DocuSign].</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Environment]</p> </td> 
      <td>Seleccione si desea conectarse a un entorno de producción que no sea de producción.</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td>Seleccione si desea conectarse a una cuenta de servicio o a una personal.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Account type]</td> 
      <td>Seleccione si la cuenta a la que desea conectarse es una cuenta de producción o una cuenta de demostración.</td> 
     </tr> 
    </tbody> 
   </table>

1. Haga clic en **Continuar** para guardar la conexión y volver al módulo.

## Módulos de [!DNL DocuSign] y sus campos

Al configurar módulos de [!DNL DocuSign], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL DocuSign] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Activadores](#triggers)
* [Acciones](#actions)

### Activadores

#### [!UICONTROL Ver sobres]

Este módulo de activador inicia un escenario cuando se envía, entrega, firma, completa o rechaza un sobre.

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL DocuSign] a Workfront Fusion, consulte <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Conectar Docusign a Workfront Fusion</a> en este artículo.</p> </td> 
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
   <td role="rowheader"> <p>[!UICONTROL Outputs]</p> </td> 
   <td> <p>Seleccione los campos que desea incluir en la salida del módulo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Introduzca o asigne el número máximo de registros con los que desea que trabaje el módulo durante cada ciclo de ejecución de escenario.</td> 
  </tr> 
 </tbody> 
</table>

### Acciones

* [[!UICONTROL Agregar un campo personalizado]](#add-a-custom-field)
* [[!UICONTROL Añadir destinatario al sobre]](#add-recipient-to-envelope)
* [[!UICONTROL Crear un nuevo sobre]](#create-a-new-envelope)
* [[!UICONTROL Llamada de API personalizada]](#custom-api-call)
* [[!UICONTROL Descargar un documento]](#download-a-document)
* [[!UICONTROL Modificar campo personalizado]](#modify-custom-field)
* [[!UICONTROL Leer un sobre]](#read-an-envelope)
* [[!UICONTROL Enviar sobre]](#send-envelope)
* [[!UICONTROL Cargar un archivo en un sobre]](#upload-a-file-to-an-envelope)

#### [!UICONTROL Agregar un campo personalizado]

Este módulo de acción añade un campo personalizado al documento

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL DocuSign] a Workfront Fusion, consulte <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Conectar [!DNL DocuSign] a Workfront Fusion</a> en este artículo.</p> </td>
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

#### [!UICONTROL Añadir destinatario al sobre]

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
   <td>Introduzca o asigne el cuerpo (contenido) del correo electrónico enviado al destinatario.</td> 
  </tr> 
  <tr>
    <td role="rowheader">[!UICONTROL Email subject]</td>
   <td>Introduzca o asigne el asunto del correo electrónico que se envía al destinatario.</td> 
  </tr> 
    <td role="rowheader">[!UICONTROL Private message]</td>
   <td> Si desea enviar un mensaje privado al destinatario, escriba o asigne el texto del mensaje. <p>Solo el destinatario seleccionado ve el mensaje privado, así como el mensaje general. El mensaje privado tiene un límite de 1000 caracteres.</p>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Authentication]</td> 
   <td> <p>Seleccione el método de autenticación que desee utilizar para confirmar la identidad del destinatario.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL None]</strong> </p> </li> 
     <li> <p><strong>[!UICONTROL Access code]</strong> </p> <p>Introduzca o asigne el código de acceso.</p> </li> 
     <li> <p><strong>[!UICONTROL Phone]</strong> </p> <p>Escriba o asigne el número de teléfono.</p> </li> 
     <li> <p><strong>[!UICONTROL SMS]</strong> </p> <p>Escriba o asigne el número de teléfono.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Crear un nuevo sobre]

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
   <td> <p> Seleccione la plantilla a partir de la que desea crear el nuevo sobre. Las plantillas están disponibles según la [!UICONTROL Account] seleccionada.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL After creation]
   </td> 
   <td> <p>Seleccione si desea guardar el sobre como borrador o enviarlo para su firma.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader" >[!UICONTROL Template recipients]</td>
    <td>Para cada destinatario que desee agregar a este sobre, haga clic en <b>Agregar elemento</b> e introduzca los siguientes detalles:
    <ul>
    <li><b>Código de acceso</b><p>Introduzca o asigne el código que utiliza el destinatario para acceder al sobre.<p></li>
    <li><b>Correo electrónico</b><p>Introduzca o asigne la dirección de correo electrónico del destinatario.<p></li>
    <li><b>Nombre</b><p>Introduzca o asigne el nombre del destinatario.<p></li>
    <li><b>Nombre de la función</b><p>Introduzca o asigne el nombre de función del destinatario.<p></li>
    <li><b>Orden de enrutamiento</b><p>Introduzca o asigne el número de enrutamiento del destinatario. El número de enrutamiento determina el orden en que los destinatarios reciben y firman los documentos.<p></li>
    </ul>
    </td>
    </tr>
  <tr> 
   <td role="rowheader">
     [!UICONTROL Permitir impresión y firma]
   </td> 
   <td> <p>Active esta opción para permitir que el destinatario imprima el documento y firme el papel.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL Permitir reasignación]
   </td> 
   <td> <p>Active esta opción si desea que el destinatario pueda reasignar los documentos a otro usuario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL Permitir recursión de destinatario]
   </td> 
   <td> <p>Active esta opción para permitir la recursión del destinatario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL Copia autoritativa]
   </td> 
   <td> <p>Active esta opción para marcar los documentos de este sobre como copias autorizadas.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL Navegación automática]
   </td> 
   <td> <p>Active esta opción para definir la navegación automática para el destinatario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL ID de marca]
   </td> 
   <td> <p>Introduzca o asigne el ID de la marca.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL Marcado habilitado]
   </td> 
   <td> <p>Active esta opción para habilitar el marcado del documento.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL Caducidad habilitada]
   </td> 
   <td> <p>Active esta opción para establecer una caducidad para este sobre. Si activa esta opción, rellene los campos siguientes:<ul><li><b>Caduca después de</b><p>Introduzca o asigne el número de días después de los cuales caduca este sobre.</p></li><li><b>Advertencia de caducidad</b><p>Introduzca o asigne el número de días antes de la caducidad que se envía un correo electrónico recordatorio al destinatario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL Body]
   </td> 
   <td> <p>Escriba o asigne el cuerpo (contenido) del correo electrónico que acompaña a este sobre.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL Subject]
   </td> 
   <td> <p>Escriba o asigne el asunto del correo electrónico que acompaña a este sobre.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Llamada de API personalizada]

Este módulo de acción le permite realizar una llamada de API personalizada.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL DocuSign] a Workfront Fusion, consulte <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Conectar [!DNL DocuSign] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Account]</td> 
   <td>Introduzca o asigne la cuenta que desea usar para acceder a la API de [!DNL DocuSign].</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL URL]</td> 
   <td> <p>Introduzca o asigne una ruta relativa a <code>https://&lt;BASE_URI>/v2/accounts/&lt;ACCOUNT_ID>.</code></p>  </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar. Determina el tipo de contenido de la petición.</p> <p>Por ejemplo:<code> {"Content-type":"application/json"}</code></p> <p>Nota: Si se producen errores y es difícil determinar su origen, considere la posibilidad de modificar los encabezados según la documentación de Workfront. Si la llamada de API personalizada devuelve un error de petición HTTP 422, intente utilizar un encabezado “Content-Type”:“text/plain”.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query String]</td> 
   <td> <p>Añada la consulta para la llamada de API en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la instrucción condicional.</p> 
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

>[!BEGINSHADEBOX]

**Ejemplo:** enumerar sobres

La siguiente llamada de la API devuelve sobres a partir de la fecha especificada en su cuenta de [!DNL DocuSign]:

**URL**: `/v2.1/accounts/{accountId}/envelopes/`

**Método**: `GET`

**Cadena de consulta**:

* **Clave**: `from_date`

* **Valor**: `YYYY-MM-DD`

Especifica cuándo comienza la solicitud a comprobar los cambios de estado de los sobres de la cuenta.

![Ejemplo de configuración de Docusign](/help/workfront-fusion/references/apps-and-modules/assets/example-docusign-setup-350x770.png)

El resultado se puede encontrar en la salida del módulo en Paquete > Cuerpo > Sobres.

En nuestro ejemplo, se devolvieron 6 sobres:

![Ejemplo de salida de docusign](/help/workfront-fusion/references/apps-and-modules/assets/docusign-example-output-350x677.png)

>[!ENDSHADEBOX]

#### [!UICONTROL Descargar un documento]

Este módulo de acción descarga un solo documento.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL DocuSign] a Workfront Fusion, consulte <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Conectar [!DNL DocuSign] a Workfront Fusion</a> en este artículo.</p> </td>
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
   <td>Active esta opción para incluir el certificado de firma de sobre en la descarga.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Documents by User ID]</td> 
   <td>Active esta opción para permitir que los destinatarios recuperen documentos por ID de usuario. Por ejemplo, si un usuario se incluye en dos órdenes de enrutamiento diferentes con distintas visibilidades, al utilizar esta opción se devuelven todos los documentos de ambas rutas.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Encrypt]</td> 
   <td>Active esta opción si desea que los bytes de PDF devueltos en la respuesta se cifren para todos los administradores de claves configurados en su cuenta de [!DNL DocuSign].</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Language]</td> 
   <td>Seleccione el idioma.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show Changes]</td> 
   <td>Active esta opción para resaltar que los campos modificados para el PDF devuelto se resaltan en amarillo y esbozan firmas opcionales o iniciales en rojo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watermark]</td> 
   <td> <p>Active esta opción para activar la función de marca de agua. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Modificar campo personalizado]

Este módulo de acción modifica un campo personalizado mediante el nombre del campo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL DocuSign] a Workfront Fusion, consulte <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Conectar [!DNL DocuSign] a Workfront Fusion</a> en este artículo.</p> </td>
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

#### [!UICONTROL Leer un sobre]

Este módulo de acción lee información sobre un sobre en [!DNL DocuSign] mediante el identificador del sobre.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL DocuSign] a Workfront Fusion, consulte <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Conectar [!DNL DocuSign] a Workfront Fusion</a> en este artículo.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>Seleccione la cuenta que contiene el documento del que desea leer información.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> Escriba o asigne el Id. del sobre que contiene el documento del que desea leer información.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Seleccione las propiedades que desea que aparezcan en la salida del módulo. </td> 
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
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL DocuSign] a Workfront Fusion, consulte <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Conectar [!DNL DocuSign] a Workfront Fusion</a> en este artículo.</p> </td>
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

#### [!UICONTROL Cargar un archivo en un sobre]

Este módulo carga un archivo especificado en un sobre existente de DocuSign.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL DocuSign] a Workfront Fusion, consulte <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Conectar [!DNL DocuSign] a Workfront Fusion</a> en este artículo.</p> </td>
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
