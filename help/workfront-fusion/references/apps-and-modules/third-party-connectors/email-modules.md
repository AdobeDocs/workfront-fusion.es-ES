---
title: Módulos de correo electrónico
description: En un escenario de Adobe Workfront Fusion, puede conectar su cuenta de correo electrónico a varias aplicaciones y servicios de terceros. Esto le permite descargar correos electrónicos a través de IMAP, enviar correos electrónicos a través de SMTP, crear nuevos borradores, mover y copiar correos electrónicos de una carpeta a otra, marcar correos electrónicos como leídos o no leídos y eliminar correos electrónicos.
author: Becky
feature: Workfront Fusion
exl-id: 28a04bad-d3ef-4f3a-be93-8b04761a75e4
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '2491'
ht-degree: 61%

---

# Módulos de correo electrónico

En un escenario de Adobe Workfront Fusion, puede conectar su cuenta de correo electrónico a varias aplicaciones y servicios de terceros. Esto le permite descargar correos electrónicos a través de IMAP, enviar correos electrónicos a través de SMTP, crear nuevos borradores, mover y copiar correos electrónicos de una carpeta a otra, marcar correos electrónicos como leídos o no leídos y eliminar correos electrónicos.

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

## Conectar su correo electrónico a Workfront Fusion {#connect-your-email-to-workfront-fusion}

* [Conectarse a Google](#connect-to-google)
* [Conectar con otros servicios de correo electrónico (IMAP)](#connect-to-other-email-services-smap)

### Conectarse a [!DNL Google]

Utilice esta opción para crear escenarios con módulos de correo electrónico que requieran una conexión con su cuenta de [!DNL Google]. Esta es una cuenta con ámbitos restringidos.

Puede crear una conexión a su cuenta de [!DNL Google] directamente desde un módulo de correo electrónico.

1. En cualquier módulo de correo electrónico, haga clic en **[!UICONTROL Add]** junto al campo [!UICONTROL Connection].
1. Seleccione **[!DNL Google]** como el tipo de conexión.
1. Introduzca un nombre para la conexión. 
1. (Opcional) Escriba su [!UICONTROL [!DNL Google] Client ID] y [!UICONTROL Client Secret].
1. Haga clic en **[!UICONTROL Continue]** para crear la conexión y volver al módulo.

### Conectar con otros servicios de correo electrónico (IMAP)

La conexión IMAP permite tener acceso al buzón de forma remota y leer o manipular los mensajes del buzón. La mayoría de los módulos de correo electrónico utilizan la conexión IMAP.

1. En cualquier módulo de correo electrónico, haga clic en **[!UICONTROL Add]** junto al campo [!UICONTROL Connection].
1. Seleccione **[!UICONTROL Otros (SMTP)]** como el tipo de conexión.
1. Introduzca un **[!UICONTROL Nombre]** para la conexión.
1. Seleccione su **[!UICONTROL Email provider]** de la lista. Si su proveedor de correo electrónico no está en la lista, seleccione Otro.
1. Escriba **[!UICONTROL nombre de usuario]** y **[!UICONTROL contraseña]** para la cuenta de correo electrónico.
1. (Condicional) Si su proveedor no está en la lista, escriba su **[!UICONTROL SMTP server]** y **[!UICONTROL Port]**, y especifique si desea **[!UICONTROL Use a secure connection (TLS)]**. Para encontrar esta información, consulta la sección [!UICONTROL Help] de su buzón. Si no dispone de esta información, póngase en contacto con su proveedor de servicios de correo electrónico.
1. Para usar un certificado autofirmado, habilite la opción **Rechazar certificados no autorizados** y cargue el certificado autofirmado. Para obtener instrucciones, vea [Cargar un certificado firmado automáticamente](#upload-a-self-signed-certificate)
1. Haga clic en **[!UICONTROL Continuar]** para crear la conexión y volver al módulo.

#### Cargar un certificado firmado automáticamente

Para agregar un certificado autofirmado:

1. Haga clic en **Extraer**.
1. Seleccione el tipo de archivo que va a extraer.
1. Seleccione el archivo que contiene el certificado o.
1. Introduzca la contraseña del archivo.
1. Haga clic en **Guardar** para extraer el archivo y volver a la configuración del módulo.

## Módulos de [!UICONTROL Email] y sus campos

Al configurar los módulos [!UICONTROL Correo electrónico], Workfront Fusion muestra los campos que se indican a continuación. Además, es posible que aparezcan otros campos en función de factores como el nivel de acceso a la aplicación o al servicio. El título en negrita en un módulo indica un campo obligatorio.

Es posible que algunos de los campos de correo electrónico ya contengan datos porque se usaron en otro módulo del escenario. Consulte la documentación de ayuda sobre el correo electrónico si necesita más información al respecto.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

>[!NOTE]
>
>El ID único de correo electrónico conocido como “[!UICONTROL ID de correo electrónico (UID)]” es el identificador del correo electrónico. El ID de correo electrónico es específico para cada carpeta del correo electrónico.

* [Activadores](#triggers)
* [Acciones](#actions)
* [Iteradores](#iterators)

### Activadores

#### [!UICONTROL Ver correos electrónicos]

Este módulo de déclencheur inicia un escenario en el que se recibe un nuevo correo electrónico para su procesamiento según criterios especificados.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la cuenta de correo electrónico a [!UICONTROL Workfront Fusion], consulte <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Conectar el correo electrónico a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
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
  <tr> 
   <td role="rowheader">[!UICONTROL Subject] </td> 
   <td> <p>Introduzca el asunto del correo electrónico que quiera ver.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Phrase] </td> 
   <td> <p>Introduzca cualquier palabra clave para ver solo los correos electrónicos que contienen las palabras clave.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mark message(s) as read when fetched]</td> 
   <td> <p>Habilite esta opción para marcar correos electrónicos no leídos como leídos después de recuperar los detalles.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of results]</td> 
   <td> <p> Introduzca o asigne el número máximo de correos electrónicos que Workfront Fusion debe devolver durante un ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Acciones

* [[!UICONTROL Copiar un correo electrónico]](#copy-an-email)
* [[!UICONTROL Crear un borrador]](#create-a-draft)
* [[!UICONTROL Eliminar un correo electrónico]](#delete-an-email)
* [[!UICONTROL Obtener correos electrónicos]](#get-emails)
* [[!UICONTROL Marcar un correo electrónico como leído]](#mark-an-email-as-read)
* [[!UICONTROL Marcar un correo electrónico como no leído]](#mark-an-email-as-unread)
* [[!UICONTROL Mover un correo electrónico]](#move-an-email)
* [[!UICONTROL Enviar un correo electrónico]](#send-an-email)

#### [!UICONTROL Copiar un correo electrónico]

Este módulo de acción copia un correo electrónico o un borrador en una carpeta seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de correo electrónico a [!UICONTROL Workfront Fusion], consulte <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Conectar su correo electrónico a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td>
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
   <td> <p>Introduzca el UID de correo electrónico del correo electrónico que desea copiar en la carpeta de destino.</p> <p>Puede obtener el UID del correo electrónico mediante el módulo [!UICONTROL Email] &gt; [!UICONTROL Watch Email] o el módulo [!UICONTROL Search Email].</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Crear un borrador]

Este módulo de acción crea y agrega un nuevo borrador a una carpeta seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la cuenta de correo electrónico a [!UICONTROL Workfront Fusion], consulte <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Conectar el correo electrónico a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td>
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
  <tr> 
   <td role="rowheader">[!UICONTROL Content] </td> 
   <td> <p>Introduzca o asigne el contenido del correo electrónico en formato HTML mediante etiquetas de HTML o en texto sin formato.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>Para cada archivo adjunto que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca lo siguiente:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL File name]</strong> </p> <p>Introduzca el nombre del archivo, incluida la extensión. </p> </li> 
     <li> <p><strong>[!UICONTROL Data]</strong> </p> <p>Introduzca la ruta a la carpeta en la que desea cargar el archivo adjunto.</p> </li> 
     <li> <p><strong>[!UICONTROL Content-ID]</strong> </p> <p>Introduzca el ID de contenido para insertar el archivo adjunto (imagen) en el contenido.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy Recipient] </td> 
   <td> <p>Para cada dirección de correo electrónico a la que desee enviar una copia de este correo electrónico, haga clic en <b>Agregar elemento</b> e introduzca la dirección de correo electrónico. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Blind Copy Recipient]</td> 
   <td> <p> Para cada dirección de correo electrónico a la que desee enviar una copia de este correo electrónico sin que aparezca en el mismo, haga clic en <b>Agregar elemento</b> e introduzca la dirección de correo electrónico.</p> </td> 
  </tr> 
  <!--<tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL From] </td> 
   <td> <p>Enter or map the email address (and name, if needed) that appears in the [!UICONTROL From] field in the email. </p> <p>Important: Use the correct syntax: <code>name@email.com</code> or <code>"Name" name@email.com</code>.</p> <p>Note:  Normally, Workfront Fusion uses the email address that you entered when creating the connection as the sender address. If you enter any other email address, an error may occur when sending a message because your account may not have permission to send emails from a different address than your own. E.g. <code>test@mail.com</code> or "<code>John Bush" test@email.com</code>.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Sender]</p> </td> 
   <td> <p>Enter or map the email address that appears in the [!UICONTROL Sender] field in the email.</p> <p>Tip:  If you are unsure whether to use this field or the From field, we recommend choosing the From field.</p> <p>Important: Use the correct syntax: <code>name@email.com</code> or <code>"Name" name@email.com</code></p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Reply-To]</td> 
   <td> <p> If you want replies to this email sent to a different address than the "[!UICONTROL from]" address, enter the email address where you want replies to this email sent.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL In-Reply-To]</td> 
   <td> <p> If you are replying to a specific email, enter or map the ID of the email you are replying to.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL References] </td> 
   <td> <p>Enter the message IDs of all the replies in the thread.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Priority]</p> </td> 
   <td> <p>Select the priority of the email:</p> 
    <ul> 
     <li>[!UICONTROL High]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL Low]</li> 
    </ul> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Headers]</p> </td> 
   <td> <p>Add the headers:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Key]</strong> </p> <p>Add the key. For example, Sender, Date, To, and so on.</p> </li> 
     <li> <p><strong>[!UICONTROL Value]</strong> </p> <p>Enter the value for the key.</p> </li> 
    </ul> </td> 
  </tr> -->
 </tbody> 
</table>

#### [!UICONTROL Eliminar un correo electrónico]

Este módulo de acción elimina un correo electrónico o un borrador de la carpeta seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la cuenta de correo electrónico a [!UICONTROL Workfront Fusion], consulte <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Conectar el correo electrónico a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>Seleccione la carpeta que contiene el correo electrónico que desea eliminar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>Introduzca el UID de correo electrónico del correo electrónico que desea eliminar.</p> <p>Puede obtener el UID del correo electrónico mediante el módulo Correo electrónico &gt; Ver correo electrónico o [!UICONTROL Buscar correo electrónico].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expunge]</td> 
   <td> <p>Active esta opción para quitar permanentemente todos los mensajes marcados como [!UICONTROL Eliminado] en el buzón abierto actualmente.</p> <p>Nota: en [!DNL Gmail], este comportamiento se basa en la configuración de la sección [!UICONTROL Settings] &gt;[!UICONTROL Forwarding POP/IMAP in IMAP access].</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Obtener correos electrónicos]

Este módulo devuelve correos electrónicos que coinciden con los criterios especificados.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la cuenta de correo electrónico a [!UICONTROL Workfront Fusion], consulte <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Conectar el correo electrónico a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td>
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
   <td role="rowheader">[!UICONTROL Correo electrónico del destinatario]</td> 
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
   <td> <p>Introduzca o asigne cualquier palabra clave para recuperar solo los correos electrónicos que contengan esas palabras clave.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Email ID (UID)]</td> 
   <td> <p> Introduzca el ID de correo electrónico (UID) del correo electrónico cuyos detalles desea recuperar.</p> <p>Puede obtener el UID del correo electrónico mediante el módulo [!UICONTROL Watch Email] de Workfront Fusion o el módulo [!UICONTROL Search Email].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of results]</td> 
   <td> <p> Número máximo de correos electrónicos que Workfront Fusion debe devolver durante un ciclo de ejecución de escenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Continue the execution of the route even if the module returns no results]</td> 
   <td> <p> Seleccione si desea continuar ejecutando el módulo aunque no se devuelvan resultados.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Marcar un correo electrónico como leído]

Este módulo de acción marca un correo electrónico o borrador en una carpeta seleccionada como leído, al establecer el indicador [!UICONTROL Read].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la cuenta de correo electrónico a [!UICONTROL Workfront Fusion], consulte <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Conectar el correo electrónico a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>Seleccione la carpeta que contiene el correo electrónico que desea marcar como leído.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>Introduzca el UID de correo electrónico del correo electrónico que desea marcar como leído.</p> <p>Puede obtener el UID del correo electrónico mediante el módulo Correo electrónico &gt; Ver correo electrónico o [!UICONTROL Buscar correo electrónico].</p> </td> 
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
   <td> <p>Para obtener instrucciones sobre cómo conectar la cuenta de correo electrónico a [!UICONTROL Workfront Fusion], consulte <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Conectar el correo electrónico a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>Seleccione la carpeta que contiene el correo electrónico que desea marcar como no leído. Ejemplo: Principal.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>Introduzca el UID de correo electrónico del correo electrónico que desea marcar como no leído.</p> <p>Puede obtener el UID del correo electrónico mediante el módulo Correo electrónico &gt; Ver correo electrónico o [!UICONTROL Buscar correo electrónico].</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Mover un correo electrónico]

Mueve un correo electrónico o borrador seleccionado a una carpeta seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de correo electrónico a [!UICONTROL Workfront Fusion], consulte <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Conectar su correo electrónico a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Folder]</td> 
   <td>Seleccione la carpeta que contiene el correo electrónico que desea mover. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination Folder]</td> 
   <td> <p> Seleccione la carpeta a la que desea añadir el correo electrónico.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>Introduzca el UID de correo electrónico del correo electrónico que desea mover a la carpeta de destino.</p> <p>Puede obtener el UID del correo electrónico mediante el módulo Correo electrónico &gt; Ver correo electrónico o [!UICONTROL Buscar correo electrónico].</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Enviar un correo electrónico]

Envía un nuevo correo electrónico.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de correo electrónico a Workfront Fusion, consulte <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Conecte su correo electrónico a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Save Message after Sending]</td> 
   <td>Una vez enviado el mensaje de correo electrónico, se guardará en el buzón. Active esta opción si desea guardar los mensajes de correo electrónico enviados mediante Workfront Fusion en la carpeta <i>[!UICONTROL Correo enviado]</i> u otra carpeta del buzón. Algunos servicios de correo electrónico, como [!DNL Gmail], guardan automáticamente los mensajes enviados.</td> 
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
   <td> <p>Seleccione el tipo de [!UICONTROL content] para el correo electrónico:</p> 
    <ul> 
     <li>HTML</li> 
     <li>[!UICONTROL Plaintext]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content] </td> 
   <td> <p>Introduzca o asigne el contenido del correo electrónico en formato HTML mediante etiquetas HTML o en texto sin formato, según lo que eligió en el campo [!UICONTROL Content Type].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>Para cada archivo adjunto que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca lo siguiente:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL File name]</strong> </p> <p>Introduzca el nombre del archivo, incluida la extensión. </p> </li> 
     <li> <p><strong>[!UICONTROL Data]</strong> </p> <p>Introduzca la ruta a la carpeta en la que desea cargar el archivo adjunto.</p> </li> 
     <li> <p><strong>[!UICONTROL Content-ID]</strong> </p> <p>Introduzca el ID de contenido para insertar el archivo adjunto (imagen) en el contenido.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy Recipient] </td> 
   <td> <p>Para cada dirección de correo electrónico a la que desee enviar una copia de este correo electrónico, haga clic en <b>Agregar elemento</b> e introduzca la dirección de correo electrónico. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Blind Copy Recipient]</td> 
   <td> <p> Para cada dirección de correo electrónico a la que desee enviar una copia de este correo electrónico sin que aparezca en el mismo, haga clic en <b>Agregar elemento</b> e introduzca la dirección de correo electrónico.</p> </td> 
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
<tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL From] </td> 
   <td> <p>Introduzca o asigne la dirección de correo electrónico (y el nombre si es necesario) que aparece en el campo [!UICONTROL From] del correo electrónico. </p> <p>Importante: Utilice la sintaxis correcta, <code>name@email.com</code> o <code>"Name" name@email.com</code>.</p> <p>Nota: Normalmente, Workfront Fusion utiliza la dirección de correo electrónico introducida al crear la conexión como dirección del remitente. Si introduce cualquier otra dirección de correo electrónico, puede producirse un error al enviar un mensaje, ya que es posible que su cuenta no tenga permiso para enviar correos electrónicos desde una dirección diferente a la suya. Por ejemplo: <code>test@mail.com</code> o "<code>John Bush" test@email.com</code>.</p> </td> 
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
