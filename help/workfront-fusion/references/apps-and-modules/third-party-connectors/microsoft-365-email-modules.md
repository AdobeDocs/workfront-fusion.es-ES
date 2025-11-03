---
title: Correo electrónico de Microsoft Office 365
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan el correo electrónico de Microsoft Office 365, así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: 5d4072ba-c598-4347-a42f-c59c7add0a1b
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '2921'
ht-degree: 62%

---

# Módulos de [!DNL Microsoft Office 365 Email]

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!UICONTROL el correo electrónico de Microsoft Office 365], así como conectarlo a varias aplicaciones y servicios de terceros.

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

## Requisitos previos

Para usar módulos [!DNL Microsoft Office 365 Email], debe tener una cuenta de [!DNL Microsoft Office 365 Email].

## Información de API de correo electrónico de Microsoft Office 365

El conector de correo electrónico de Microsoft Office 365 utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Dirección URL base</td> 
   <td> https://graph.microsoft.com/v1.0</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> Versión 1.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 2.6.5</td> 
  </tr>
 </tbody> 
 </table>

## Conectando el servicio [!DNL Office 365 Email] a Workfront Fusion

Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365 Email] a [!UICONTROL Workfront Fusion], consulte [Crear una conexión a [!UICONTROL Adobe Workfront Fusion]: instrucciones básicas](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

>[!NOTE]
>
>Algunas aplicaciones de Microsoft utilizan la misma conexión, que está vinculada a permisos de usuario individuales. Por lo tanto, al crear una conexión, la pantalla de consentimiento de permisos muestra los permisos que se otorgaron previamente a la conexión de este usuario, además de cualquier nuevo permiso que sea necesario para la aplicación actual.
>
>Por ejemplo, si a un usuario se le han otorgado permisos de &quot;Leer tabla&quot; a través del conector de Excel y luego crea una conexión en el conector de Outlook para leer correos electrónicos, la pantalla de consentimiento de permisos mostrará tanto el permiso de &quot;Leer tabla&quot; ya otorgado como el nuevo permiso requerido de &quot;Escribir correo electrónico&quot;.

## Módulos de [!DNL Microsoft Office 365 Email] y sus campos

Al configurar módulos de [!DNL Microsoft Office 365 Email], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL Microsoft Office 365 Email] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Mensaje](#message)
* [Borrador de mensaje](#draft-message)
* [Archivos adjuntos](#attachment)
* [Otro](#other)

### Mensaje

* [[!UICONTROL Crear y enviar un mensaje (heredado)]](#create-and-send-a-message)
* [[!UICONTROL Eliminar un mensaje]](#delete-a-message)
* [[!UICONTROL Obtener un mensaje]](#get-a-message)
* [[!UICONTROL Mover un mensaje]](#move-a-message)
* [[!UICONTROL Buscar mensajes]](#search-messages)
* [[!UICONTROL Ver mensajes]](#watch-messages)



#### [!UICONTROL Crear y enviar un mensaje (heredado)]

Este módulo de acción crea y envía un mensaje de correo electrónico.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject]</td> 
   <td> <p>Introduzca o asigne la línea de asunto del mensaje.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body content]</td> 
   <td> <p>Introduzca o asigne el texto del cuerpo del mensaje del correo electrónico.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Importance]</td> 
   <td> <p>Seleccione la importancia del correo electrónico</p> 
    <ul> 
     <li>[!UICONTROL Low]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL High]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p> [!UICONTROL To Recipients]</p> </td> 
   <td> <p>Para cada destinatario al que desee enviar el correo electrónico, haga clic en <b>Agregar elemento</b> e introduzca lo siguiente:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Introduzca la dirección de correo electrónico del contacto.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Introduzca el nombre del contacto.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL CC Recipients]</p> </td> 
   <td> <p><p>Para cada destinatario al que desee enviar una copia del correo electrónico, haga clic en <b>Agregar elemento</b> e introduzca lo siguiente:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Introduzca la dirección de correo electrónico del contacto.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Introduzca el nombre del contacto.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Bcc Recipients]</p> </td> 
   <td> <p>Para cada destinatario al que desee enviar una copia del correo electrónico, sin permitir que otros destinatarios vean sus nombres o direcciones de correo electrónico, haga clic en <b>Agregar elemento</b> e introduzca lo siguiente:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Introduzca la dirección de correo electrónico del contacto.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Introduzca el nombre del contacto.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>Para cada archivo adjunto que desee agregar al correo electrónico, haga clic en <b>Agregar elemento</b> e introduzca lo siguiente:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL archivo Source]</strong> </p> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Internet Message Headers]</td> 
   <td> <p>Para cada encabezado que desee agregar al correo electrónico, haga clic en <b>Agregar elemento</b> e introduzca lo siguiente:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Introduzca el nombre del encabezado</p> </li> 
     <li> <p><strong>[!UICONTROL Value]</strong> </p> <p>Introduzca un valor para el encabezado.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Eliminar un mensaje]

Este módulo de acción elimina un mensaje de correo electrónico existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From email address]</td> 
   <td> <p> Para utilizar una dirección de correo electrónico compartida, introduzca la dirección aquí. El usuario cuyas credenciales se utilizan en la conexión utilizada para este módulo debe tener acceso a la carpeta compartida.<p>Deje este campo en blanco para utilizar la dirección de correo electrónico propia del propietario de la conexión.</p></p> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> Seleccione o asigne el ID del mensaje que desea eliminar.</p> </td> 
  </tr> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a message]

Este módulo de acción obtiene los metadatos de un mensaje específico

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From email address]</td> 
   <td> <p> Para utilizar una dirección de correo electrónico compartida, introduzca la dirección aquí. El usuario cuyas credenciales se utilizan en la conexión utilizada para este módulo debe tener acceso a la carpeta compartida.<p>Deje este campo en blanco para utilizar la dirección de correo electrónico propia del propietario de la conexión.</p></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> Seleccione o asigne el ID del mensaje para el que desea recuperar los metadatos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get MIME contents]</td> 
   <td>Habilite esta opción para recuperar datos sobre el contenido MIME del mensaje. El contenido de [!UICONTROL MIME] puede incluir imágenes, audio, vídeo u otros tipos de archivos.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move a Message]

Este módulo de acción mueve un mensaje de correo electrónico a una carpeta seleccionada del buzón.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> Seleccione o asigne el ID del mensaje que desea mover a una carpeta diferente.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mail Folder] </td> 
   <td> <p>Seleccione o asigne el ID de la carpeta a la que desea mover el mensaje.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search messages]

Este módulo de búsqueda busca mensajes en función de criterios específicos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL From email address]</td> 
   <td> <p> Para utilizar una dirección de correo electrónico compartida, introduzca la dirección aquí. El usuario cuyas credenciales se utilizan en la conexión utilizada para este módulo debe tener acceso a la carpeta compartida.<p>Deje este campo en blanco para utilizar la dirección de correo electrónico propia del propietario de la conexión.</p></p> </td> 
  </tr> 
<tr> 
   <td role="rowheader">[!UICONTROL Mail Folder]</td> 
   <td> <p>Seleccione la carpeta que contiene los mensajes que desea buscar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search]</td> 
   <td>Introduzca la consulta de búsqueda. Para obtener información sobre cómo escribir una consulta de búsqueda, consulte el artículo de soporte técnico de [!DNL Microsoft] <a href="https://support.microsoft.com/en-us/office/search-mail-and-people-in-outlook-com-88108edf-028e-4306-b87e-7400bbb40aa7?ui=en-us&rs=en-us&ad=us">Buscar correo y personas en [!DNL Outlook.com]</a>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order by]</td> 
   <td> <p>Seleccione cómo desea ordenar los resultados:</p> 
    <ul> 
     <li>[!UICONTROL Subject (Ascending or descending)]</li> 
     <li>[!UICONTROL Created Date Time (Ascending or descending)]</li> 
     <li>[!UICONTROL Last Modified Date Time (Ascending or descending)]</li> 
     <li>[!UICONTROL Received Date Time (Ascending or descending)]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca el número máximo de mensajes que Workfront Fusion debe devolver durante un ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Ver mensajes]

Este módulo de déclencheur inicia un escenario cuando se envía o recibe un nuevo mensaje de correo electrónico.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Watch Messages]</p> </td> 
   <td> <p>Seleccione los mensajes que desee ver:</p> 
    <ul> 
     <li>[!UICONTROL Only Unread]</li> 
     <li>[!UICONTROL Only read]</li> 
     <li>[!UICONTROL All]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mail Folder]</td> 
   <td> <p>Seleccione la carpeta que contiene los mensajes que desea ver.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search]</td> 
   <td>Introduzca la consulta de búsqueda. El módulo devuelve mensajes que coinciden con esta consulta. Para obtener información sobre cómo redactar una consulta de búsqueda, consulte el artículo de asistencia técnica [!DNL Microsoft] <a href="https://support.microsoft.com/en-us/office/search-mail-and-people-in-outlook-com-88108edf-028e-4306-b87e-7400bbb40aa7?ui=en-us&rs=en-us&ad=us">Buscar correo y personas en [!DNL Outlook.com]</a>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Introduzca el número máximo de mensajes que Workfront Fusion debe devolver durante un ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Borrador de mensaje

* [Crear un borrador de mensaje](#create-a-draft-message)
* [Enviar un borrador de mensaje](#send-a-draft-message)
* [Actualizar un mensaje](#update-a-message)

#### [!UICONTROL Crear un borrador de mensaje]

Este módulo de acción crea un nuevo mensaje de correo electrónico como borrador.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject]</td> 
   <td> <p>Introduzca la línea de asunto del mensaje.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body Content Type]</td> 
   <td>Seleccione si el contenido del cuerpo del mensaje es HTML o texto.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body content]</td> 
   <td> <p>Introduzca o asigne el texto del cuerpo del mensaje del correo electrónico.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Importance]</td> 
   <td> <p>Seleccione la importancia del correo electrónico</p> 
    <ul> 
     <li>[!UICONTROL Low]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL High]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p> [!UICONTROL To Recipients]</p> </td> 
   <td> <p>Para cada destinatario al que desee enviar el correo electrónico, haga clic en <b>Agregar elemento</b> e introduzca lo siguiente:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Introduzca la dirección de correo electrónico del contacto.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Introduzca el nombre del contacto.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL CC Recipients]</p> </td> 
   <td> <p><p>Para cada destinatario al que desee enviar una copia del correo electrónico, haga clic en <b>Agregar elemento</b> e introduzca lo siguiente:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Introduzca la dirección de correo electrónico del contacto.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Introduzca el nombre del contacto.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Bcc Recipients]</p> </td> 
   <td> <p>Para cada destinatario al que desee enviar una copia del correo electrónico, sin permitir que otros destinatarios vean sus nombres o direcciones de correo electrónico, haga clic en <b>Agregar elemento</b> e introduzca lo siguiente:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Introduzca la dirección de correo electrónico del contacto.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Introduzca el nombre del contacto.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>Para cada archivo adjunto que desee agregar al correo electrónico, haga clic en <b>Agregar elemento</b> e introduzca lo siguiente:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL archivo Source]</strong> </p> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From email address]</td> 
   <td> <p> Para utilizar una dirección de correo electrónico compartida, introduzca la dirección aquí. El usuario cuyas credenciales se utilizan en la conexión utilizada para este módulo debe tener acceso a la carpeta compartida.<p>Deje este campo en blanco para utilizar la dirección de correo electrónico propia del propietario de la conexión.</p></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Enviar un mensaje de borrador]

Este módulo de acción envía un mensaje de correo electrónico que está actualmente en borrador.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From email address]</td> 
   <td> <p> Para utilizar una dirección de correo electrónico compartida, introduzca la dirección aquí. El usuario cuyas credenciales se utilizan en la conexión utilizada para este módulo debe tener acceso a la carpeta compartida.<p>Deje este campo en blanco para utilizar la dirección de correo electrónico propia del propietario de la conexión.</p></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Draft Message ID]</td> 
   <td> <p> Seleccione o asigne el ID de mensaje del borrador que desea enviar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Actualizar un mensaje]

Este módulo de acción actualiza un mensaje existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From email address]</td> 
   <td> <p> Para utilizar una dirección de correo electrónico compartida, introduzca la dirección aquí. El usuario cuyas credenciales se utilizan en la conexión utilizada para este módulo debe tener acceso a la carpeta compartida.<p>Deje este campo en blanco para utilizar la dirección de correo electrónico propia del propietario de la conexión.</p></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a message ID]</td> 
   <td> <p>Seleccione cómo desea identificar el mensaje que se va a actualizar:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter Manually]</strong> </p> <p>Introduzca o asigne el ID del mensaje.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione la carpeta que contiene el mensaje que desea actualizar y, a continuación, seleccione el mensaje</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject]</td> 
   <td> <p>Introduzca la línea de asunto del mensaje.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body content]</td> 
   <td> <p>Introduzca el texto del cuerpo del mensaje del correo electrónico.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Importance]</td> 
   <td> <p>Seleccione la importancia del correo electrónico</p> 
    <ul> 
     <li>[!UICONTROL Low]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL High]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p> [!UICONTROL To Recipients]</p> </td> 
   <td> <p>Para cada destinatario al que desee enviar el correo electrónico, haga clic en <b>Agregar elemento</b> e introduzca lo siguiente:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Introduzca la dirección de correo electrónico del contacto.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Introduzca el nombre del contacto.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL CC Recipients]</p> </td> 
   <td> <p><p>Para cada destinatario al que desee enviar una copia del correo electrónico, haga clic en <b>Agregar elemento</b> e introduzca lo siguiente:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Introduzca la dirección de correo electrónico del contacto.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Introduzca el nombre del contacto.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Bcc Recipients]</p> </td> 
   <td> <p>Para cada destinatario al que desee enviar una copia del correo electrónico, sin permitir que otros destinatarios vean sus nombres o direcciones de correo electrónico, haga clic en <b>Agregar elemento</b> e introduzca lo siguiente:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Introduzca la dirección de correo electrónico del contacto.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Introduzca el nombre del contacto.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>Para cada archivo adjunto que desee agregar al correo electrónico, haga clic en <b>Agregar elemento</b> e introduzca lo siguiente:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL archivo Source]</strong> </p> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mark it as Read]</td> 
   <td>Habilite esta opción para marcar el mensaje actualizado como leído.</td> 
  </tr> 
 </tbody> 
</table>

### Archivos adjuntos

* [[!UICONTROL Descargar un archivo adjunto]](#download-an-attachment)
* [[!UICONTROL List Attachments]](#list-attachments)

#### [!UICONTROL Download an Attachment]

Este módulo descarga el archivo adjunto especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From email address]</td> 
   <td> <p> Para utilizar una dirección de correo electrónico compartida, introduzca la dirección aquí. El usuario cuyas credenciales se utilizan en la conexión utilizada para este módulo debe tener acceso a la carpeta compartida.<p>Deje este campo en blanco para utilizar la dirección de correo electrónico propia del propietario de la conexión.</p></p> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> Seleccione o asigne el ID del mensaje que contiene el archivo adjunto que desea descargar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Attachment ID]</td> 
   <td> <p>Introduzca o asigne el ID del archivo adjunto que desea descargar. Puede localizar esta idea mediante el módulo List Attachments.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Attachments]

Este módulo recupera una lista de archivos adjuntos que pertenecen al mensaje especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From email address]</td> 
   <td> <p> Para utilizar una dirección de correo electrónico compartida, introduzca la dirección aquí. El usuario cuyas credenciales se utilizan en la conexión utilizada para este módulo debe tener acceso a la carpeta compartida.<p>Deje este campo en blanco para utilizar la dirección de correo electrónico propia del propietario de la conexión.</p></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> Seleccione o asigne el ID del mensaje del que desea recuperar los archivos adjuntos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de archivos adjuntos que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Otro

* [[!UICONTROL Add an Attachment]](#add-an-attachment)
* [Creación y envío de un mensaje](#create-and-send-a-message)
* [[!UICONTROL Make an API Call]](#make-an-api-call)

#### [!UICONTROL Add an Attachment]

Este módulo añade un archivo adjunto grande a un mensaje.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From email address]</td> 
   <td> <p> Para utilizar una dirección de correo electrónico compartida, introduzca la dirección aquí. El usuario cuyas credenciales se utilizan en la conexión utilizada para este módulo debe tener acceso a la carpeta compartida.<p>Deje este campo en blanco para utilizar la dirección de correo electrónico propia del propietario de la conexión.</p></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> Seleccione o asigne el ID del mensaje al que desea añadir un archivo adjunto.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Crear y enviar un mensaje]

Este módulo de acción crea y envía un mensaje de correo electrónico.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject]</td> 
   <td> <p>Introduzca o asigne la línea de asunto del mensaje.</p> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL Body content]</td> 
   <td> <p>Introduzca o asigne el texto del cuerpo del mensaje del correo electrónico.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Importance]</td> 
   <td> <p>Seleccione la importancia del correo electrónico</p> 
    <ul> 
     <li>[!UICONTROL Low]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL High]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p> [!UICONTROL To Recipients]</p> </td> 
   <td> <p>Para cada destinatario al que desee enviar el correo electrónico, haga clic en <b>Agregar elemento</b> e introduzca lo siguiente:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Introduzca la dirección de correo electrónico del contacto.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Introduzca el nombre del contacto.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL CC Recipients]</p> </td> 
   <td> <p><p>Para cada destinatario al que desee enviar una copia del correo electrónico, haga clic en <b>Agregar elemento</b> e introduzca lo siguiente:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Introduzca la dirección de correo electrónico del contacto.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Introduzca el nombre del contacto.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Bcc Recipients]</p> </td> 
   <td> <p>Para cada destinatario al que desee enviar una copia del correo electrónico, sin permitir que otros destinatarios vean sus nombres o direcciones de correo electrónico, haga clic en <b>Agregar elemento</b> e introduzca lo siguiente:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Introduzca la dirección de correo electrónico del contacto.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Introduzca el nombre del contacto.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>Para cada archivo adjunto que desee agregar al correo electrónico, haga clic en <b>Agregar elemento</b> e introduzca lo siguiente:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL archivo Source]</strong> </p> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Internet Message Headers]</td> 
   <td> <p>Añada los encabezados de los mensajes del correo electrónico.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Introduzca el nombre del encabezado</p> </li> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Introduzca un valor para el encabezado.</p> </li> 
    </ul> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL From email address]</td> 
   <td> <p> Para utilizar una dirección de correo electrónico compartida, introduzca la dirección aquí. El usuario cuyas credenciales se utilizan en la conexión utilizada para este módulo debe tener acceso a la carpeta compartida.<p>Deje este campo en blanco para utilizar la dirección de correo electrónico propia del propietario de la conexión.</p></p> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Realizar una llamada de API]

Este módulo le permite realizar una llamada de API personalizada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>Introduzca una ruta relativa a <code>https://graph.microsoft.com</code>. Ejemplo:<code> /v1.0/me/messages</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   td&gt; <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar. Por ejemplo, <code>{"Content-type":"application/json"}</code>. Workfront Fusion añade los encabezados de autorización para usted.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> Añada la consulta para la llamada de API en forma de objeto JSON estándar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la instrucción condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>
