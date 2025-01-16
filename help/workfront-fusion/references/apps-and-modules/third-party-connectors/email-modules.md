---
title: Módulos de correo electrónico
description: En un escenario de  [!DNL Adobe Workfront Fusion] , puede conectar su cuenta de correo electrónico a varias aplicaciones y servicios de terceros. Esto le permite descargar correos electrónicos a través de IMAP, enviar correos electrónicos a través de SMTP, crear nuevos borradores, mover y copiar correos electrónicos de una carpeta a otra, marcar correos electrónicos como leídos o no leídos y eliminar correos electrónicos.
author: Becky
feature: Workfront Fusion
exl-id: 28a04bad-d3ef-4f3a-be93-8b04761a75e4
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '2103'
ht-degree: 71%

---

# Módulos de correo electrónico

En un escenario de [!DNL Adobe Workfront Fusion], puede conectar su cuenta de correo electrónico a varias aplicaciones y servicios de terceros. Esto le permite descargar correos electrónicos a través de IMAP, enviar correos electrónicos a través de SMTP, crear nuevos borradores, mover y copiar correos electrónicos de una carpeta a otra, marcar correos electrónicos como leídos o no leídos y eliminar correos electrónicos.

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

## Conectar su correo electrónico a Workfront Fusion {#connect-your-email-to-workfront-fusion}

* [Conectarse a Google](#connect-to-google)
* [Conectarse a otros servicios de correo electrónico (SMAP)](#connect-to-other-email-services-smap)

### Conectarse a [!DNL Google]

Utilice esta opción para crear escenarios con módulos de correo electrónico que requieran una conexión con su cuenta de [!DNL Google]. Esta es una cuenta con ámbitos restringidos.

Puede crear una conexión a su cuenta de [!DNL Google] directamente desde un módulo de correo electrónico.

1. En cualquier módulo de correo electrónico, haga clic en **[!UICONTROL Add]** junto al campo [!UICONTROL Connection].
1. Seleccione **[!DNL Google]** como el tipo de conexión.
1. Introduzca un nombre para la conexión. 
1. (Opcional) Escriba [!UICONTROL [!DNL Google] Client ID] y [!UICONTROL Client Secret].
1. Haga clic en **[!UICONTROL Continue]** para crear la conexión y volver al módulo.

### Conectarse a otros servicios de correo electrónico (SMAP)

La conexión SMAP le permite acceder al buzón de forma remota y leer o manipular los mensajes del buzón. La mayoría de los módulos de correo electrónico utilizan la conexión SMAP.

1. En cualquier módulo de correo electrónico, haga clic en **[!UICONTROL Add]** junto al campo [!UICONTROL Connection].
1. Seleccione **[!UICONTROL Others (SMTP)]** como el tipo de conexión.
1. Escriba un **[!UICONTROL Name]** para la conexión.
1. Seleccione su **[!UICONTROL Email provider]** de la lista. Si su proveedor de correo electrónico no está en la lista, seleccione Otro.
1. Escriba **[!UICONTROL Email address]**, **[!UICONTROL Your full name]**, **[!UICONTROL User name]** y **[!UICONTROL Password]**.
1. (Condicional) Si su proveedor no está en la lista, escriba sus **[!UICONTROL SMTP server]** y **[!UICONTROL Port]** y especifique si desea **[!UICONTROL Use a secure connection (TLS)]**. Para encontrar esta información, consulte la sección [!UICONTROL Help] del buzón. Si no dispone de esta información, póngase en contacto con su proveedor de servicios de correo electrónico.
1. Haga clic en **[!UICONTROL Continue]** para crear la conexión y volver al módulo.

## Módulos de [!UICONTROL Email] y sus campos

Al configurar módulos de [!UICONTROL Email], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Además, es posible que aparezcan otros campos en función de factores como el nivel de acceso a la aplicación o al servicio. El título en negrita en un módulo indica un campo obligatorio.

Es posible que algunos de los campos de correo electrónico ya contengan datos porque se usaron en otro módulo del escenario. Consulte la documentación de ayuda sobre el correo electrónico si necesita más información al respecto.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

>[!NOTE]
>
>El identificador único de correo electrónico conocido como &#39;[!UICONTROL Email ID (UID)]&#39; es el identificador del correo electrónico. El ID de correo electrónico es específico para cada carpeta del correo electrónico.

* [Activadores](#triggers)
* [Acciones](#actions)
* [Iteradores](#iterators)

### Activadores

#### [!UICONTROL Watch Emails]

Se activa cuando se recibe un nuevo correo electrónico para su procesamiento según criterios especificados.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de correo electrónico a [!UICONTROL Workfront Fusion], vea <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Conectar su correo electrónico a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder] </td> 
   <td> <p>Seleccione la carpeta que contenga los correos electrónicos que quiera ver.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Criteria]</p> </td> 
   <td> <p>Seleccione los criterios según los cuales se mostrarán los correos electrónicos:</p> 
    <ul> 
     <li>[!UICONTROL All Emails]</li> 
     <li>[!UICONTROL Only Read Emails]</li> 
     <li>[!UICONTROL Only Unread Emails]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sender Email Address] </td> 
   <td> <p>Introduzca la dirección de correo electrónico del remitente cuyos correos electrónicos desea ver.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Recipient Email Address]</td> 
   <td> <p> Introduzca la dirección de correo electrónico del destinatario cuyos correos electrónicos desea ver.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject] </td> 
   <td> <p>Introduzca el asunto del correo electrónico que quiera ver.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Phrase] </td> 
   <td> <p>Introduzca cualquier palabra clave para ver solo aquellos correos electrónicos que contengan frases específicas.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mark message(s) as read when fetched]</td> 
   <td> <p>Habilite esta opción para marcar correos electrónicos no leídos como leídos después de recuperar los detalles.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of results]</td> 
   <td> <p> Número máximo de correos electrónicos que [!DNL Workfront Fusion] debería devolver durante un ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Acciones

* [[!UICONTROL Send an Email]](#send-an-email)
* [[!UICONTROL Create a Draft]](#create-a-draft)
* [[!UICONTROL Mark an Email as Read]](#mark-an-email-as-read)
* [[!UICONTROL Mark an Email as Unread]](#mark-an-email-as-unread)
* [[!UICONTROL Move an Email]](#move-an-email)
* [[!UICONTROL Copy an Email]](#copy-an-email)
* [[!UICONTROL Delete an Email]](#delete-an-email)
* [[!UICONTROL Get Emails]](#get-emails)

#### [!UICONTROL Send an Email]

Envía un nuevo correo electrónico.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de correo electrónico a [!DNL Workfront Fusion], vea <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Conectar su correo electrónico a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Save Message after Sending]</td> 
   <td>Una vez enviado el mensaje de correo electrónico, se guardará en el buzón. Habilite esta opción si desea guardar los mensajes de correo electrónico enviados mediante [!DNL Workfront Fusion] a la carpeta <i>[!UICONTROL Sent mail]</i> u otra carpeta del buzón. Algunos servicios de correo electrónico, como [!DNL Gmail], guardan automáticamente los mensajes enviados.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL To] </td> 
   <td> <p>Añada las direcciones de correo electrónico a las que desee enviar el correo electrónico.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject] </td> 
   <td> <p>Introduzca o asigne la línea de asunto del correo electrónico.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Content Type]</p> </td> 
   <td> <p>Seleccione el tipo [!UICONTROL content] para el correo electrónico:</p> 
    <ul> 
     <li>HTML</li> 
     <li>[!UICONTROL Plaintext]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content] </td> 
   <td> <p>Introduzca o asigne el contenido del correo electrónico en formato de HTML mediante etiquetas de HTML o en texto sin formato, según lo que elija en el campo [!UICONTROL Content Type].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>Añada un archivo adjunto:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL File name]</strong> </p> <p>Introduzca el nombre de archivo. Por ejemplo, sample.doc.</p> </li> 
     <li> <p><strong>[!UICONTROL Data]</strong> </p> <p>Introduzca la ruta a la carpeta para cargar el archivo adjunto.</p> </li> 
     <li> <p><strong>[!UICONTROL Content-ID]</strong> </p> <p>Escriba [!UICONTROL content ID] para insertar el archivo adjunto (imagen) en el contenido.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy Recipient] </td> 
   <td> <p>Introduzca o asigne una o más direcciones de correo electrónico a las que desee enviar una copia de este correo electrónico. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Blind Copy Recipient]</td> 
   <td> <p> Introduzca o asigne una o varias direcciones de correo electrónico a las que desee enviar una copia de este correo electrónico sin que aparezcan en él.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL From] </td> 
   <td> <p>Escriba o asigne la dirección de correo electrónico (y el nombre, si es necesario) que aparece en el campo [!UICONTROL From] del mensaje. </p> <p>Importante: Utilice la sintaxis correcta, <code>name@email.com</code> o <code>"Name" name@email.com</code>.</p> <p>Nota: Normalmente, [!DNL Workfront Fusion] usa la dirección de correo electrónico que usted especificó al crear la conexión como dirección del remitente. Si introduce cualquier otra dirección de correo electrónico, puede producirse un error al enviar un mensaje, ya que es posible que su cuenta no tenga permiso para enviar correos electrónicos desde una dirección diferente a la suya. Por ejemplo: <code>test@mail.com</code> o "<code>John Bush" test@email.com</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Sender]</p> </td> 
   <td> <p>Escriba o asigne la dirección de correo electrónico que aparece en el campo [!UICONTROL Sender] del correo electrónico.</p> <p>Sugerencia: Si no está seguro de si desea utilizar este campo o el campo De, le recomendamos que elija el campo De.</p> <p>Importante: Utilice la sintaxis correcta, <code>name@email.com</code> o <code>"Name" name@email.com</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reply-To]</td> 
   <td> <p> Si desea que las respuestas a este correo electrónico se envíen a una dirección diferente a la dirección “de”, introduzca la dirección de correo electrónico a la que desea que se envíen las respuestas a este correo electrónico.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL In-Reply-To]</td> 
   <td> <p> Si responde a un correo electrónico específico, introduzca o asigne el ID del correo electrónico al que está respondiendo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL References] </td> 
   <td> <p>Introduzca los ID de mensaje de todas las respuestas del hilo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Priority]</p> </td> 
   <td> <p>Seleccione la prioridad del correo electrónico:</p> 
    <ul> 
     <li>[!UICONTROL High]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL Low]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Headers]</p> </td> 
   <td> <p>Añada los encabezados:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Key]</strong> </p> <p>Añada la clave. Por ejemplo, [!UICONTROL Sender], [!UICONTROL Date], [!UICONTROL To], etc.</p> </li> 
     <li> <p><strong>[!UICONTROL Value]</strong> </p> <p>Introduzca el valor de la clave.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Draft]

Crea y añade un nuevo borrador a la carpeta seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de correo electrónico a [!UICONTROL Workfront Fusion], vea <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Conectar su correo electrónico a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>Seleccione la carpeta en la que desea crear el borrador del correo electrónico.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL To] </td> 
   <td> <p>Introduzca o asigne la dirección de correo electrónico a la que desea enviar el correo electrónico.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject] </td> 
   <td> <p>Introduzca o asigne la línea de asunto del correo electrónico.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Content Type]</p> </td> 
   <td> <p>Seleccione el tipo de contenido del correo electrónico:</p> 
    <ul> 
     <li>HTML</li> 
     <li>[!UICONTROL Plain Text]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content] </td> 
   <td> <p>Introduzca o asigne el contenido del correo electrónico en formato de HTML mediante etiquetas de HTML o en texto sin formato, según lo que elija en el campo [!UICONTROL Content Type].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>Añada un archivo adjunto:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL File name]</strong> </p> <p>Introduzca el nombre de archivo. Por ejemplo, sample.doc.</p> </li> 
     <li> <p><strong>[!UICONTROL Data]</strong> </p> <p>Introduzca la ruta a la carpeta para cargar el archivo adjunto.</p> </li> 
     <li> <p><strong>[!UICONTROL Content-ID]</strong> </p> <p>Introduzca el ID de contenido para insertar el archivo adjunto (imagen) en el contenido.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy Recipient] </td> 
   <td> <p>Introduzca o asigne una o más direcciones de correo electrónico a las que desee enviar una copia de este correo electrónico. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Blind Copy Recipient]</td> 
   <td> <p> Introduzca o asigne una o varias direcciones de correo electrónico a las que desee enviar una copia de este correo electrónico sin que aparezcan en él.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL From] </td> 
   <td> <p>Escriba o asigne la dirección de correo electrónico (y el nombre, si es necesario) que aparece en el campo [!UICONTROL From] del mensaje. </p> <p>Importante: Utilice la sintaxis correcta, <code>name@email.com</code> o <code>"Name" name@email.com</code>.</p> <p>Nota: Normalmente, [!DNL Workfront Fusion] usa la dirección de correo electrónico que usted especificó al crear la conexión como dirección del remitente. Si introduce cualquier otra dirección de correo electrónico, puede producirse un error al enviar un mensaje, ya que es posible que su cuenta no tenga permiso para enviar correos electrónicos desde una dirección diferente a la suya. Por ejemplo: <code>test@mail.com</code> o "<code>John Bush" test@email.com</code>.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Sender]</p> </td> 
   <td> <p>Escriba o asigne la dirección de correo electrónico que aparece en el campo [!UICONTROL Sender] del correo electrónico.</p> <p>Sugerencia: Si no está seguro de si desea utilizar este campo o el campo De, le recomendamos que elija el campo De.</p> <p>Importante: Utilice la sintaxis correcta, <code>name@email.com</code> o <code>"Name" name@email.com</code></p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Reply-To]</td> 
   <td> <p> Si desea que las respuestas a este correo electrónico se envíen a una dirección diferente a la dirección "[!UICONTROL from]", escriba la dirección de correo electrónico a la que desea enviar las respuestas a este correo electrónico.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL In-Reply-To]</td> 
   <td> <p> Si responde a un correo electrónico específico, introduzca o asigne el ID del correo electrónico al que está respondiendo.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL References] </td> 
   <td> <p>Introduzca los ID de mensaje de todas las respuestas del hilo.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Priority]</p> </td> 
   <td> <p>Seleccione la prioridad del correo electrónico:</p> 
    <ul> 
     <li>[!UICONTROL High]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL Low]</li> 
    </ul> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Headers]</p> </td> 
   <td> <p>Añada los encabezados:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Key]</strong> </p> <p>Añada la clave. Por ejemplo, Remitente, Fecha, Para, etc.</p> </li> 
     <li> <p><strong>[!UICONTROL Value]</strong> </p> <p>Introduzca el valor de la clave.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Mark an Email as Read]

Marca un correo electrónico o un borrador de una carpeta seleccionada como leído al establecer el indicador [!UICONTROL Read].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de correo electrónico a [!UICONTROL Workfront Fusion], vea <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Conectar su correo electrónico a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>Seleccione la carpeta del correo electrónico que desea marcar como leído. Ejemplo: Principal.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>Introduzca el UID de correo electrónico del correo electrónico que desea marcar como leído.</p> <p>Puede obtener el UID del correo electrónico utilizando el módulo [!UICONTROL Email] &gt;[!UICONTROL Watch Email] o el módulo [!UICONTROL Search Email].</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Mark an Email as Unread]

Marca un correo electrónico o un borrador de una carpeta seleccionada como no leído al establecer el indicador No leído.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de correo electrónico a [!UICONTROL Workfront Fusion], vea <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Conectar su correo electrónico a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>Seleccione la carpeta del correo electrónico que desea marcar como no leído. Ejemplo: Principal.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>Introduzca el UID de correo electrónico del correo electrónico que desea marcar como no leído.</p> <p>Puede obtener el UID del correo electrónico utilizando el módulo [!UICONTROL Email] &gt;[!UICONTROL Watch Email] o el módulo [!UICONTROL Search Email].</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move an Email]

Mueve un correo electrónico o borrador seleccionado a una carpeta seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de correo electrónico a [!UICONTROL Workfront Fusion], vea <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Conectar su correo electrónico a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Folder]</td> 
   <td>Seleccione la carpeta que contiene el correo electrónico desde el que desea mover el correo electrónico. Ejemplo: Principal.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination Folder]</td> 
   <td> <p> Seleccione la carpeta a la que desea añadir el correo electrónico. Ejemplo: Trabajo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>Introduzca el UID de correo electrónico del correo electrónico que desea mover a la carpeta de destino.</p> <p>Puede obtener el UID del correo electrónico utilizando el módulo [!UICONTROL Email] &gt;[!UICONTROL Watch Email] o el módulo [!UICONTROL Search Email].</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Copy an Email]

Copia un correo electrónico o un borrador en una carpeta seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de correo electrónico a [!UICONTROL Workfront Fusion], vea <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Conectar su correo electrónico a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Folder]</td> 
   <td>Seleccione la carpeta desde la que desea copiar el correo electrónico. Ejemplo: Principal.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination Folder]</td> 
   <td> <p> Seleccione la carpeta en la que desea copiar el correo electrónico. Ejemplo: Trabajo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>Introduzca el UID de correo electrónico del correo electrónico que desea copiar en la carpeta de destino.</p> <p>Puede obtener el UID del correo electrónico utilizando el módulo [!UICONTROL Email] &gt;[!UICONTROL Watch Email] o el módulo [!UICONTROL Search Email].</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete an Email]

Quita un correo electrónico o un borrador de la carpeta seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de correo electrónico a [!UICONTROL Workfront Fusion], vea <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Conectar su correo electrónico a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>Seleccione la carpeta del correo electrónico que desea eliminar. Ejemplo: Principal.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>Introduzca el UID de correo electrónico del correo electrónico que desea eliminar.</p> <p>Puede obtener el UID del correo electrónico utilizando el módulo [!UICONTROL Email] &gt;[!UICONTROL Watch Email] o el módulo [!UICONTROL Search Email].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expunge]</td> 
   <td> <p>Habilite esta opción para permitir que el módulo quite permanentemente todos los mensajes marcados como [!UICONTROL Deleted] en el buzón abierto actualmente.</p> <p>Nota: en [!DNL Gmail], este comportamiento se basa en la configuración de la sección [!UICONTROL Settings] &gt;[!UICONTROL Forwarding POP/IMAP in IMAP access].</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Emails]

Muestra los correos electrónicos que coinciden con los criterios especificados.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de correo electrónico a [!UICONTROL Workfront Fusion], vea <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Conectar su correo electrónico a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder] </td> 
   <td> <p>Seleccione la carpeta que contiene los correos electrónicos que desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mark message(s) as read when fetched] </td> 
   <td> <p>Habilite esta opción si desea marcar el correo electrónico no leído como leído después de recuperar los detalles.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Criteria]</p> </td> 
   <td> <p>Seleccione los criterios de los correos electrónicos que desea recuperar:</p> 
    <ul> 
     <li>[!UICONTROL All Emails]</li> 
     <li>[!UICONTROL Only Read Emails]</li> 
     <li>[!UICONTROL Only Unread Emails]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sender Email Address] </td> 
   <td> <p>Introduzca o asigne la dirección de correo electrónico del remitente cuyos correos electrónicos desea recuperar.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Recipient Email Address]</td> 
   <td> <p> Introduzca o asigne la dirección de correo electrónico del destinatario cuyos correos electrónicos desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From date] </td> 
   <td> <p>Introduzca o asigne la fecha para recuperar los correos electrónicos que se procesaron en la fecha especificada o después de ella.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Before date]</td> 
   <td> <p> Introduzca o asigne la fecha para recuperar los correos electrónicos que se procesaron en la fecha especificada o antes de ella.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject] </td> 
   <td> <p>Introduzca o asigne el asunto del correo electrónico que desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Phrase] </td> 
   <td> <p>Introduzca o asigne cualquier palabra clave para recuperar solo los correos electrónicos que contengan frases específicas.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Email ID (UID)]</td> 
   <td> <p> Introduzca el ID de correo electrónico (UID) del correo electrónico cuyos detalles desea recuperar.</p> <p>Puede obtener el UID del correo electrónico utilizando el módulo [!UICONTROL  Watch Email] o el módulo [!UICONTROL Search Email] de [!DNL Workfront Fusion].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of results]</td> 
   <td> <p> Número máximo de correos electrónicos que [!DNL Workfront Fusion] debería devolver durante un ciclo de ejecución de escenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Continue the execution of the route even if the module returns no results]</td> 
   <td> <p> Seleccione si desea continuar ejecutando el módulo aunque no se devuelvan resultados.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Iteradores

#### [!UICONTROL Iterate Attachments]

Itera los archivos adjuntos recibidos uno a uno.

El módulo del iterador de correo electrónico permite administrar los archivos adjuntos de los correos electrónicos por separado. Por ejemplo, puede configurar los ajustes para ver correos electrónicos para iterar los correos con archivos adjuntos y recibir alertas.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source module]</td> 
   <td> <p>Seleccione el módulo que genera el correo electrónico con los archivos adjuntos que desea iterar.</p> </td> 
  </tr> 
 </tbody> 
</table>

Para obtener más información acerca de los iteradores, vea [Módulo Iterator](/help/workfront-fusion/references/modules/iterator-module.md).
