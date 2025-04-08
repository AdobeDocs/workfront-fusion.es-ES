---
title: Módulos Slack
description: En un escenario de  [!DNL Adobe Workfront Fusion] , es posible automatizar los flujos de trabajo que utilizan Slack, así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: c9c68a4c-f592-42d1-b15f-a525b9aa3944
source-git-commit: eb0518ba0d1a0c758cb547e362c722f4be3674c7
workflow-type: tm+mt
source-wordcount: '1954'
ht-degree: 67%

---

# Módulos de [!DNL Slack]

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!DNL Slack], así como conectarlo a varias aplicaciones y servicios de terceros.

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

Para usar módulos [!DNL Slack], debe tener una cuenta de [!DNL Slack].

## Información de API de Slack

El conector de Slack utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL básica</td> 
   <td>{{ifempty(parameters.domain, 'https://slack.com/api/')}}</td> 
  </tr>
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 4.0.15</td> 
  </tr>
 </tbody> 
 </table>

## Módulos de [!DNL Slack] y sus campos

Al configurar módulos de [!DNL Slack], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Slack] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Mensajes](#messages)
* [Conversaciones](#channels)
* [Otro](#other)

### Mensajes

* [Crear un mensaje](#create-a-message)
* [Eliminar un mensaje](#delete-a-message)
* [Obtener un mensaje de canal privado](#get-a-private-channel-message)
* [Obtener un mensaje de canal público](#get-a-public-channel-message)
* [Actualizar un mensaje](#update-a-message)
* [Ver mensajes de canal privado](#watch-private-channel-messages)
* [Ver mensajes de canal público](#watch-public-channel-messages)

### [!UICONTROL Crear un mensaje]

Este módulo de acción crea un nuevo mensaje.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Enter a channel ID or name]</p> </td> 
   <td> <p>Elija cómo desea seleccionar el canal en el que desea crear un mensaje.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>En el campo <strong>[!UICONTROL Channel ID or name]</strong>, escriba o asigne el ID de canal o el nombre del canal en el que desea publicar el mensaje.</p> <p>Nota: el ID del canal se puede recuperar mediante el módulo [!UICONTROL List Channels].</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el tipo de canal y, a continuación, seleccione el canal.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Text]</p> </td> 
   <td> <p>Introduzca el contenido de texto del mensaje que desea crear.</p> <p>Nota: Para obtener información detallada sobre el formato de texto, consulte <a href="https://api.slack.com/reference/surfaces/formatting">Formato de texto para superficies de aplicación</a> en la documentación de [!DNL Slack].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Como usuario]</td> 
   <td>Active esta opción para publicar el mensaje como el usuario propietario de las credenciales utilizadas por la conexión para este módulo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Thread message ID (time stamp)]</td> 
   <td>Si el nuevo mensaje es una respuesta, escriba la marca de tiempo del mensaje al que desea responder. No introduzca la marca de tiempo de un mensaje que ya sea una respuesta.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reply broadcast]</td> 
   <td> <p>Seleccione <strong>[!UICONTROL Yes]</strong> si se aplican las dos condiciones siguientes:</p> 
    <ul> 
     <li> <p>El nuevo mensaje es una respuesta a otro mensaje</p> </li> 
     <li> <p>Desea que el nuevo mensaje sea visible para todos los miembros del canal</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Attachments]</td> 
   <td>Para cada elemento que desee adjuntar al mensaje, haga clic en <b>Agregar elemento</b> y rellene los detalles del elemento.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Icono emoji]</td> 
   <td>Escriba o asigne el emoji que se usará como icono para este mensaje, con el formato <code>:icon-name:</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Icono URL]</td> 
   <td>Introduzca o asigne la dirección URL de la imagen que se utilizará como icono para este mensaje. </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Link names]</p> </td> 
   <td> <p>Habilite esta opción para permitir que los nombres y canales utilicen el formato <code>@username</code> o <code>#channel</code>. </p> <p>Para obtener más información, consulte <a href="https://api.slack.com/docs/formatting">Formato de texto para superficies de aplicación</a> en la documentación de [!DNL Slack].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Parse message text]</p> </td> 
   <td> <p>Active esta opción para permitir el análisis automático. </p> <p>Para obtener más información, consulte <a href="https://api.slack.com/docs/formatting">Formato de texto para superficies de aplicación</a> en la documentación de [!DNL Slack].</p> <p>Nota: si ha utilizado las opciones [!UICONTROL Link names] o [!UICONTROL Parse message text] en el mensaje original, debe especificarlas también al ejecutar el módulo [!UICONTROL Update a Message].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Use markdown]</p> </td> 
   <td> <p>Habilite esta opción para permitir que [!DNL Slack] utilice Markdown en el texto.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Unfurl primarily text-based content]</p> </td> 
   <td> <p>Active esta opción para permitir el despliegue de contenido principalmente basado en texto. </p> <p>Para obtener más información acerca de cómo desplegar en [!DNL Slack], consulte <a href="https://api.slack.com/reference/messaging/link-unfurling">Desplegar vínculos en mensajes</a> en la documentación de [!DNL Slack].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Unfurl media content]</p> </td> 
   <td> <p>Active esta opción para permitir el despliegue de contenido multimedia. </p> <p>Para obtener más información acerca de cómo desplegar en [!DNL Slack], consulte <a href="https://api.slack.com/reference/messaging/link-unfurling">Desplegar vínculos en mensajes</a> en la documentación de [!DNL Slack].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL User name]</td> 
   <td>Especifique el nombre de usuario utilizado para publicar el mensaje. Si no se especifica ningún nombre de usuario, se utiliza el nombre "Bot".</td> 
  </tr> 
 </tbody> 
</table>


#### [!UICONTROL Eliminar un mensaje]

Este módulo de acción elimina un mensaje especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>Introduzca o asigne el ID de canal.</p> <p>Nota: el ID del canal se puede recuperar mediante el módulo [!UICONTROL List Channels].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> Introduzca o asigne la marca de tiempo del mensaje que desea eliminar.</p> <p>Nota: La marca de tiempo se puede recuperar mediante otro módulo, como el módulo Ver mensajes de canal privado.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Como usuario]</td> 
   <td> <p> Active esta opción para eliminar el mensaje como el usuario con las credenciales utilizadas en la conexión.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Obtener un mensaje de canal privado]

Este módulo de acción recupera los detalles de un mensaje desde un canal seleccionado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>Introduzca (asigne) el ID de canal.</p> <p>Nota: el ID del canal se puede recuperar mediante el módulo [!UICONTROL List Channels].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Message ID (Time stamp)]</p> </td> 
   <td> <p> Introduzca o asigne la marca de tiempo del mensaje del que desea recuperar información.</p> <p>Nota: La marca de tiempo se puede recuperar mediante otro módulo, como el módulo [!UICONTROL Watch Private Channel Messages].</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Obtener un mensaje del canal público]**

Este módulo de acción devuelve un mensaje con una ID determinada de un canal público especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>Introduzca o asigne el ID de canal.</p> <p>Nota: el ID del canal se puede recuperar mediante el módulo [!UICONTROL List Channels].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID (Time stamp)]</td> 
   <td> <p> Introduzca o asigne la marca de tiempo del mensaje del que desea recuperar información.</p> <p>Nota: La marca de tiempo se puede recuperar mediante otro módulo, como el módulo [!UICONTROL Watch Public Channel Messages].</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Actualizar un mensaje]

Este módulo de acción le permite editar un mensaje existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
<!--  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Enter a channel ID or name]</p> </td> 
   <td> <p>Choose how you want to select the message you want to .</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>In the <strong>[!UICONTROL Channel ID or name]</strong> field, enter or map the Channel ID or of the channel that contains the message, then enter the <strong>[!UICONTROL Time Stamp (Message ID)]</strong> of the message.</p> <p>Note: The Channel ID can be retrieved using the [!UICONTROL List Channels] module.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Select the type of channel, then select the channel, then select the message.</p> </li> 
    </ul> </td> 
  </tr> -->
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>Introduzca o asigne el ID del canal que contiene el mensaje que desea actualizar.</p> <p>Nota: el ID del canal se puede recuperar mediante el módulo [!UICONTROL List Channels].</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Message ID (Time stamp)]</p> </td> 
   <td> <p> Introduzca o asigne la marca de tiempo del mensaje del que desea recuperar información.</p> <p>Nota: La marca de tiempo se puede recuperar mediante otro módulo, como el módulo [!UICONTROL Watch Public Channel Messages].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Text]</p> </td> 
   <td> <p>Introduzca el nuevo contenido de texto del mensaje que desea actualizar.</p> <p>Para obtener más información, consulte <a href="https://api.slack.com/docs/formatting">Formato de texto para superficies de aplicación</a> en la documentación de [!DNL Slack].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Como usuario]</td> 
   <td>Active esta opción para actualizar el mensaje como el usuario propietario de las credenciales utilizadas por la conexión para este módulo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Attachments]</td> 
   <td>Para cada elemento que desee adjuntar al mensaje, haga clic en <b>Agregar elemento</b> y rellene los detalles del elemento.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Link names]</p> </td> 
   <td> <p>Habilite esta opción para permitir que los nombres y canales utilicen el formato <code>@username</code> o <code>#channel</code>. </p> <p>Para obtener más información, consulte <a href="https://api.slack.com/docs/formatting">Formato de texto para superficies de aplicación</a> en la documentación de [!DNL Slack].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Parse message text]</p> </td> 
   <td> <p>Active esta opción para permitir el análisis automático. </p> <p> Para obtener más información, consulte <a href="https://api.slack.com/docs/formatting">Formato de texto para superficies de aplicaciones</a> en la documentación de [!DNL Slack].</p> <p>Nota: si ha utilizado las opciones [!UICONTROL Link names] o [!UICONTROL Parse message text] en el mensaje original, debe especificarlas también al ejecutar el módulo Actualizar un mensaje.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Ver mensajes de canal privado]

Este módulo de activador inicia el escenario cuando se añade un nuevo mensaje a un canal privado (grupo).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel] </td> 
   <td> <p>Seleccione el canal privado en el que desea ver los mensajes nuevos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Establezca el número máximo de mensajes que [!DNL Workfront Fusion] devolverá durante un ciclo de ejecución.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Ver mensajes del canal público]

Este módulo de activador inicia el escenario cuando se añade un nuevo mensaje a un canal público.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel] </td> 
   <td> <p>Seleccione el canal público en el que desea recibir nuevos mensajes.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Establezca el número máximo de mensajes que [!DNL Workfront Fusion] devolverá durante un ciclo de ejecución.</p> </td> 
  </tr> 
 </tbody> 
</table>



### Conversaciones

* [Obtener un canal](#get-a-channel)
* [Enumerar canales](#list-channels)
* [Enumerar miembros en el canal](#list-members-in-channel)

#### [!UICONTROL Obtener un canal]

Este módulo de acción devuelve información sobre un canal de Workspace.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>Introduzca o asigne el ID del canal del que desea obtener información.</p> <p>Nota: el ID del canal se puede recuperar mediante el módulo [!UICONTROL List Channels].</p> </td> 
  </tr> 
 </tbody>

#### [!UICONTROL Enumerar canales]

Este módulo de búsqueda devuelve una lista de todos los canales de un espacio de trabajo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Exclude archived]</p> </td> 
   <td> <p>Seleccione [!UICONTROL Yes] para excluir los canales archivados en los resultados.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type] </td> 
   <td> <p>Seleccione los tipos de canales que desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Establezca el número máximo de canales que [!DNL Workfront Fusion] devolverá durante un ciclo de ejecución.</p> </td> 
  </tr> 
 </tbody> 
</table>
</table>

#### [!UICONTROL Enumerar miembros en el canal]

Este módulo de búsqueda devuelve una lista de usuarios en el canal seleccionado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
<tr> 
   <td role="rowheader"> <p>[!UICONTROL Enter a channel ID or name]</p> </td> 
   <td> <p>Elija cómo desea seleccionar el mensaje que desea enviar</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>En el campo <strong>[!UICONTROL ID o nombre de canal]</strong>, escriba o asigne el ID de canal o del canal desde el que desee enumerar a los usuarios.</p> <p>Nota: el ID del canal se puede recuperar mediante el módulo [!UICONTROL List Channels].</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el tipo de canal y, a continuación, seleccione el canal.</p> </li> 
    </ul> </td> 
  </tr>
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Establezca el número máximo de miembros que [!DNL Workfront Fusion] devolverá durante un ciclo de ejecución.</p> </td> 
  </tr> 
 </tbody> 
</table>


### Otro

#### [!UICONTROL Realizar una llamada de API]

Este módulo de acción le permite realizar una llamada autenticada personalizada a la API de [!DNL Slack]. De este modo, puede crear una automatización del flujo de datos que no puedan realizar los otros módulos de [!DNL Slack].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Escriba una ruta relativa a <code>https://slack.com/api/</code>. Ejemplo: <code>/users/identity</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   td&gt; <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>[!UICONTROL Workfront Fusion] añade los encabezados de autorización automáticamente.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Añada la consulta para la llamada de API en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la instrucción condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Base URL]</td> 
   <td>Seleccione la dirección URL de base que desee utilizar para la llamada de API.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enviar token de acceso]</td> 
   <td>Seleccione si desea enviar el token de acceso como encabezado o como parámetro de consulta.</td> 
  </tr> 
 </tbody> 
</table>

## Terminología

La siguiente terminología puede resultar útil al configurar los módulos de [!DNL Slack]:

* **MD**: [!UICONTROL Mensaje directo]
* **MI**: [!UICONTROL Mensaje instantáneo]
* **Canal privado**: anteriormente, [!UICONTROL Grupo]
* **Mensaje directo**: anteriormente, [!UICONTROL MI]
* **Canal**: [!UICONTROL Conversación] en la documentación de la API, [!UICONTROL canal] en la aplicación [!DNL Slack].
