---
title: Módulos Slack
description: En un escenario de  [!DNL Adobe Workfront Fusion] , es posible automatizar los flujos de trabajo que utilizan Slack, así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
source-git-commit: 0dbe23c5eb7a0d890b7b543f2f310b163baa3793
workflow-type: tm+mt
source-wordcount: '4580'
ht-degree: 37%

---

# Módulos de [!DNL Slack]

>[!IMPORTANT]
>
>Este artículo describe los módulos disponibles en el nuevo conector de Slack, publicado el 17 de noviembre de 2025.
>
>Para obtener información sobre el conector Slack heredado, consulte [[!DNL Slack] módulos (heredados)](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/slack-modules.md).

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!DNL Slack], así como conectarlo a varias aplicaciones y servicios de terceros.

Para obtener instrucciones sobre cómo crear un escenario, vea los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Paquete de Adobe Workfront</td> 
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
   <p>Basado en conector (heredado): Workfront Fusion for Work Automation and Integration </p>
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

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

* Para usar módulos [!DNL Slack], debe tener una cuenta de [!DNL Slack].
* Si está creando conexiones de OAuth@, debe añadir las siguientes direcciones URL a la lista de permitidos de su organización:
   * token de bot: `https://oauth.app.workfrontfusion.com/oauth/cb/slack3`
   * token de usuario:` https://oauth.app.workfrontfusion.com/oauth/cb/slack2`

## Información de API de Slack

El conector de Slack utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Dirección URL base</td> 
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

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, consulte [Asignar información de un módulo a otro en](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Mensajes](#messages)
* [Archivos](#files)
* [Canales](#channels)
* [Reacciones](#reactions)
* [Estrellas](#stars)
* [Elementos guardados](#saved-items)
* [Fijadores](#pins)
* [Usuarios](#users)
* [Recordatorios](#reminders)
* [Eventos](#events)
* [Perfil](#profile)
* [Otro](#other)

### Mensajes

+++ **[!UICONTROL Crear un mensaje]**

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
   <td role="rowheader">[!UICONTROL Blocks]</td> 
   <td>Los bloques son componentes reutilizables que puede utilizar para personalizar y organizar los mensajes. Para obtener más información sobre bloques, consulte <a href="https://api.slack.com/block-kit">Kit de bloques</a> en la documentación de [!DNL Slack].</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Id. de mensaje de subproceso (marca de tiempo)]</td> 
   <td>Si el nuevo mensaje es una respuesta, introduzca la marca de tiempo del mensaje al que desea responder. No introduzca la marca de tiempo de un mensaje que ya sea una respuesta.</td> 
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
 </tbody> 
</table>

+++

+++ **[!UICONTROL Eliminar un mensaje]**

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
   <td role="rowheader">[!UICONTROL ID de mensaje (marca de tiempo)]</td> 
   <td> <p> Introduzca o asigne la marca de tiempo del mensaje que desea eliminar.</p> <p>Nota: La marca de tiempo se puede recuperar mediante otro módulo, como el módulo Ver canal privado.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Obtener un mensaje de canal privado]**

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
   <td role="rowheader"> <p>[!UICONTROL Channel]</p> </td> 
   <td> <p>Seleccione el canal que contiene el mensaje.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Message ID (Time stamp)]</p> </td> 
   <td> <p> Introduzca o asigne la marca de tiempo del mensaje del que desea recuperar información.</p> <p>Nota: La marca de tiempo se puede recuperar mediante otro módulo, como el módulo [!UICONTROL Watch Public Channel].</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Obtener un mensaje de canal público]**

Este módulo de acción devuelve un mensaje con un ID determinado de un canal público especificado.

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
   <td> <p>Seleccione el canal que contiene el mensaje.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID (Time stamp)]</td> 
   <td> <p> Introduzca o asigne la marca de tiempo del mensaje del que desea recuperar información.</p> <p>Nota: La marca de tiempo se puede recuperar mediante otro módulo, como el módulo [!UICONTROL Watch Public Channel].</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Respuestas de lista]**

Este módulo de acción recupera un hilo de mensajes publicados en una conversación.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>Seleccione el tipo de canal que contiene el mensaje para el que desea recuperar las respuestas y, a continuación, seleccione el canal.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Id. de mensaje principal (marca de tiempo)]</td> 
   <td> <p> Introduzca o asigne la marca de tiempo del mensaje para el que desea recuperar las respuestas.</p> <p>Nota: La marca de tiempo se puede recuperar mediante otro módulo, como el módulo [!UICONTROL Watch Public Channel].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de respuestas que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Buscar mensaje]**

Este módulo de búsqueda devuelve mensajes que coinciden con una consulta de búsqueda.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td> <p>Introduzca la consulta con la que desea buscar. </p> <p>Para obtener información sobre cómo crear fórmulas desde el panel de asignación, vea <a href="/help/workfront-fusion/create-scenarios/map-data/map-using-functions.md" class="MCXref xref">Asignar elementos usando funciones en [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Introduzca el número máximo de registros que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort by] </td> 
   <td> <p>Seleccione si desea ordenar los mensajes devueltos por su puntuación o por su marca de tiempo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Seleccione si desea ordenar los mensajes en sentido ascendente o descendente.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Actualizar un mensaje]**

Este módulo de acción le permite editar un mensaje existente.

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
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>En el campo <strong>[!UICONTROL Channel ID or name]</strong>, escriba o asigne el ID de canal o del canal que contiene el mensaje y, a continuación, escriba la <strong>[!UICONTROL Time Stamp (Message ID)]</strong> del mensaje.</p> <p>Nota: el ID del canal se puede recuperar mediante el módulo [!UICONTROL List Channels].</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el tipo de canal, seleccione el canal y, a continuación, seleccione el mensaje.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Text]</p> </td> 
   <td> <p>Introduzca el nuevo contenido de texto del mensaje que desea actualizar.</p> <p>Para obtener más información, consulte <a href="https://api.slack.com/docs/formatting">Formato de texto para superficies de aplicación</a> en la documentación de [!DNL Slack].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Blocks]</td> 
   <td>Los bloques son componentes reutilizables que puede utilizar para personalizar y organizar los mensajes. Para obtener más información sobre bloques, consulte <a href="https://api.slack.com/block-kit">Kit de bloques</a> en la documentación de [!DNL Slack].</td> 
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

+++

+++ **[!UICONTROL Ver mensajes directos]**

Este módulo de déclencheur inicia el escenario cuando se agrega un nuevo mensaje a un mensaje directo.

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
   <td> <p>Seleccione la conversación de mensaje directo que desee ver para ver si hay nuevos mensajes.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Introduzca el número máximo de mensajes que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Ver mensajes directos de varios participantes]**

Este módulo de déclencheur inicia el escenario cuando se agrega un nuevo mensaje a un canal de mensajes directos de varios participantes.

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
   <td> <p>Seleccione la conversación de mensaje directo que desee ver para ver si hay nuevos mensajes.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Introduzca el número máximo de mensajes que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**[!UICONTROL Ver mensajes de canal privado]**

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
   <td> <p>Introduzca el número máximo de mensajes que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**[!UICONTROL Ver mensajes del canal público]**

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
   <td> <p>Introduzca el número máximo de mensajes que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### Archivos

+++ **[!UICONTROL Eliminar un archivo]**

Este módulo de acción devuelve y elimina el archivo especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td> <p>Introduzca o asigne el ID del archivo que desea eliminar. </p> <p>Nota: El id. de archivo se puede recuperar mediante otro módulo, como el módulo [!DNL Watch Files].</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Obtener un archivo]**

Este módulo de acción devuelve detalles sobre el archivo especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td> <p>Introduzca o asigne el ID del archivo que desea recuperar. </p> <p>Nota: El id. de archivo se puede recuperar mediante otro módulo, como el módulo [!DNL Watch Files].</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Listar archivos]**

Este módulo de acción devuelve una lista de archivos basados en el filtro especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type] </td> 
   <td> <p>Seleccione los tipos de archivos que desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel type]</p> </td> 
   <td> <p>Seleccione el tipo de canal que representa el canal desde el que desea enumerar los archivos y, a continuación, seleccione el canal.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Creado por]</td> 
   <td> <p>Seleccione un usuario para devolver solo los archivos creados por el usuario especificado.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fecha desde]</td> 
   <td>Introduzca la fecha más temprana desde la que desea devolver los archivos. Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">Coerción de tipos en [!DNL Adobe Workfront Fusion]</a>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fecha a]</td> 
   <td>Introduzca la última fecha desde la que desea devolver los archivos. Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">Coerción de tipos en [!DNL Adobe Workfront Fusion]</a>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Introduzca o asigne el número máximo de archivos que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</td> 
  </tr> 
 </tbody> 
</table>

+++

<!--

+++ **[!UICONTROL Download a File]**

This action module downloads a file from a URL. It must follow the [!UICONTROL Slack] >[!UICONTROL Get a File] module in a scenario.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>For instructions about connecting your [!DNL Slack] account to [!DNL Workfront Fusion], see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to [!DNL Adobe Workfront Fusion] - Basic instructions</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL private download]</td> 
   <td> <p>Map the <b>[!UICONTROL URL Private download]</b> value from the [!DNL Slack] >[!UICONTROL Get a File] module.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

-->

+++ **[!UICONTROL Subir un archivo]**

Este módulo de acción crea o carga un archivo en [!DNL Slack]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channels]</td> 
   <td> <p>Para cada canal en el que desee cargar el archivo, haga clic en <b>[!UICONTROL Agregar elemento]</b> y, a continuación, seleccione el tipo de canal y el canal.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Title]</td> 
   <td>Escriba un título para el archivo que desea cargar</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Id. de subproceso (marca de tiempo)]</td> 
   <td> <p>Si carga el archivo como respuesta, escriba o asigne la marca de tiempo del mensaje al que desee responder.</p> <p>Nota: La marca de tiempo se puede recuperar mediante otro módulo, como el módulo [!UICONTROL Watch Private Channel].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comentario inicial]</td> 
   <td> <p>Introduzca o asigne el texto del mensaje que introduce el archivo.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Ver archivos]**

Este módulo de déclencheur inicia un escenario cuando se agrega un nuevo archivo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>Seleccione el tipo de archivo que desea que el módulo inspeccione.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td> <p>Seleccione el tipo de canal que desea inspeccionar para buscar archivos y, a continuación, seleccione el canal.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Creado por]</td> 
   <td> <p>Seleccione un usuario para devolver solo los archivos creados por el usuario especificado.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Introduzca o asigne el número máximo de archivos que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### Canales

+++ **[!UICONTROL Archivar un canal]**

Este módulo de acción archiva un canal.

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
   <td> <p>Introduzca o asigne el ID del canal que desea archivar.</p> <p>Nota: el ID del canal se puede recuperar mediante el módulo [!UICONTROL List Channels].</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Crear un canal]**

Este módulo de acción crea un nuevo canal.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Name]</p> </td> 
   <td> <p>Introduzca o asigne un nombre para el nuevo canal.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Es privado]</td> 
   <td>Active esta opción para establecer el nuevo canal como privado.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Obtener un canal]**

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
</table>

+++

+++ **[!UICONTROL Unirse a un canal]**

Este módulo de acción une al usuario a un canal.

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
   <td> <p>Introduzca o asigne el ID del canal al que desea unirse.</p> <p>Nota: el ID del canal se puede recuperar mediante el módulo [!UICONTROL List Channels].</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Dejar un canal]**

Este módulo de acción elimina al usuario de un canal.

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
   <td> <p>Introduzca o asigne el ID del canal que desea dejar.</p> <p>Nota: el ID del canal se puede recuperar mediante el módulo [!UICONTROL List Channels].</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Enumerar canales]**

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
   <td> <p>Defina el número máximo de canales que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Enumerar miembros en el canal]**

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
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>Seleccione el tipo de canal que contiene los miembros que desea enumerar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private Channel]</td> 
   <td>Seleccione el canal del que desea enumerar a los miembros.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Establezca el número máximo de miembros que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Establecer el propósito de un canal]**

Este módulo de acción cambia el propósito de un canal

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>Seleccione el tipo de canal para el que desea cambiar el propósito.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private] / Usuario / [!UICONTROL Multiple IM Channel]</td> 
   <td>Seleccione el canal o el usuario para el que desea cambiar el propósito.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Propósito]</td> 
   <td>Introduzca o asigne el nuevo propósito del canal. Este campo no admite formato ni vínculos.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Establecer el tema de un canal]**

Este módulo de acción cambia el tema de un canal

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>Seleccione el tipo de canal para el que desea cambiar el tema.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private] / [!UICONTROL User] / [!UICONTROL Multiple IM Channel]</td> 
   <td>Seleccione el canal o usuario para el que desee cambiar el tema.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tema]</td> 
   <td>Introduzca o asigne el nuevo tema del canal. Este campo no admite formato ni vínculos.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Desarchivar un canal]**

Este módulo de acción desarchiva un canal.

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
   <td> <p>Introduzca o asigne el ID del canal que desea desarchivar.</p> <p>Nota: el ID del canal se puede recuperar mediante el módulo [!UICONTROL List Channels].</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### Reacciones

+++ **[!UICONTROL Agregar una reacción]**

Este módulo de acción añade una reacción a un elemento.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>Seleccione el tipo de canal al que desea añadir una reacción.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private] / [!UICONTROL User] / [!UICONTROL Multiple IM channel]</td> 
   <td>Seleccione el canal o el usuario al que desee añadir una reacción.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de mensaje (marca de tiempo)]</td> 
   <td> <p> Introduzca o asigne la marca de tiempo del mensaje al que desee agregar una reacción.</p> <p>Nota: La marca de tiempo se puede recuperar mediante otro módulo, como el módulo [!UICONTROL Watch Private Channel].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reaction (nombre del emoji)]</td> 
   <td>Escriba o asigne el nombre del emoji que desea utilizar para una reacción. Ejemplo: <code>thumbsup</code>. </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Enumerar reacciones]**

Este módulo de acción devuelve las reacciones que ha realizado un usuario.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL User]</p> </td> 
   <td> <p>Seleccione al usuario que realizó las reacciones que desea enumerar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de reacciones que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Quitar una reacción]**

Este módulo de acción elimina una reacción de un elemento.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>Seleccione el tipo de canal del que desea quitar una reacción.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private] / [!UICONTROL User] / [!UICONTROL Multiple IM channel]</td> 
   <td>Seleccione el canal o el usuario del que desea quitar una reacción.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> Introduzca o asigne la marca de tiempo del mensaje del que desea quitar una reacción.</p> <p>Nota: La marca de tiempo se puede recuperar mediante otro módulo, como el módulo [!UICONTROL Watch Private Channel].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reaction (nombre del emoji)]</td> 
   <td>Escriba o asigne el nombre del emoji que desea quitar del mensaje. Ejemplo: <code>thumbsup</code>. </td> 
  </tr> 
 </tbody> 
</table>

+++

### Estrellas

+++ **[!UICONTROL Agregar una estrella]**

Este módulo de acción convierte un canal en un canal con estrella.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>Seleccione el tipo de canal al que desea agregar una estrella.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private] / [!UICONTROL User] / [!UICONTROL Multiple IM channel]</td> 
   <td>Seleccione el canal o el usuario al que desee agregar una estrella.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Quitar una estrella]**

Este módulo de acción elimina la estrella de un canal con estrella.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>Seleccione el tipo de canal al que desea agregar una estrella.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private] / [!UICONTROL User] / [!UICONTROL Multiple IM channel]</td> 
   <td>Seleccione el canal o el usuario al que desee agregar una estrella.</td> 
  </tr> 
 </tbody> 
</table>

+++

### Elementos guardados

+++ **[!UICONTROL Quitar elemento guardado]**

Este módulo de acción quita un elemento de los elementos guardados.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID (Time stamp)]</td> 
   <td> <p> Introduzca o asigne la marca de tiempo del mensaje que desea eliminar de los elementos guardados.</p> <p>Nota: La marca de tiempo se puede recuperar mediante otro módulo, como el módulo [!UICONTROL Watch Private Channel].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td> <p>Escriba o asigne el archivo que desea quitar de los elementos guardados.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Guardar un elemento]**

Este módulo de acción agrega un elemento a los elementos guardados.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID (Time stamp)]</td> 
   <td> <p> Introduzca o asigne la marca de tiempo del mensaje que desea guardar.</p> <p>Nota: La marca de tiempo se puede recuperar mediante otro módulo, como el módulo [!UICONTROL Watch Private Channel].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td> <p>Introduzca o asigne el archivo que desea guardar.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### Fijadores

+++ **[!UICONTROL Anclar un elemento]**

Este módulo de acción fija un elemento a un canal.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>Seleccione el tipo de canal al que desea fijar un elemento.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private] / [!UICONTROL Multiple IM channel] / [!UICONTROL User]</td> 
   <td>Seleccione el canal o el usuario al que desee anclar un elemento.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> Introduzca o asigne la marca de tiempo del mensaje que desea anclar.</p> <p>Nota: La marca de tiempo se puede recuperar mediante otro módulo, como el módulo [!UICONTROL Watch Private Channel].</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Desanclar un elemento]**

Este módulo de acción libera un elemento de un canal.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>Seleccione el tipo de canal desde el que desea desanclar un elemento.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private] / [!UICONTROL Multiple IM channel] / [!UICONTROL User]</td> 
   <td>Seleccione el canal o el usuario desde el que desea desanclar un elemento.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> Introduzca o asigne la marca de tiempo del mensaje que desea desanclar.</p> <p>Nota: La marca de tiempo se puede recuperar mediante otro módulo, como el módulo [!UICONTROL Watch Private Channel].</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### Usuarios

+++ **[!UICONTROL Obtener un usuario]**

Este módulo de acción recupera detalles sobre un miembro de un espacio de trabajo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL User ID]</p> </td> 
   <td> <p>Introduzca o asigne el ID de usuario para el que desea recuperar los detalles.</p> <p>Nota: El identificador de usuario se puede recuperar mediante otro módulo, como el módulo [!DNL List Users].</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Invitar usuarios]**

Este módulo de acción invita a entre 1 y 30 usuarios a un canal público o privado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>Seleccione el tipo de canal al que desea invitar a los usuarios.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private channel]</td> 
   <td>Seleccione el canal al que desee invitar a los usuarios.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Users]</td> 
   <td> <p>Seleccione los usuarios que desee añadir al canal.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Patear a un usuario]**

Este módulo de acción elimina un usuario de un canal.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>Seleccione el tipo de canal del que desea quitar un usuario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private channel]</td> 
   <td>Seleccione el canal del que desea quitar un usuario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Users]</td> 
   <td> <p>Seleccione el usuario que desea eliminar del canal.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Enumerar usuarios]**

Este módulo de acción devuelve una lista de todos los usuarios de un espacio de trabajo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Limit]</p> </td> 
   <td> <p>Introduzca o asigne el número máximo de usuarios que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Buscar usuario]**

Este módulo de acción recupera detalles sobre un solo usuario mediante el uso de su dirección de correo electrónico.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email] </p> </td> 
   <td> <p>Introduzca o asigne la dirección de correo electrónico del usuario cuyos detalles desea recuperar.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Usuarios en observación]**

Este módulo de déclencheur inicia el escenario cuando se agrega un nuevo usuario al área de trabajo [!DNL Slack].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Establezca el número máximo de usuarios que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### Recordatorios

<!--

+++ **[!UICONTROL List Reminders]**

This action module returns a list of all reminders created by or given to the currently authenticated user.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>For instructions about connecting your [!DNL Slack] account to [!DNL Workfront Fusion], see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to [!DNL Adobe Workfront Fusion] - Basic instructions</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Limit]</p> </td> 
   <td> <p>Enter or map the maximum number of reminders you want the module to return during each scenario execution cycle.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Get a Reminder]**

This action module retrieves details about a specific reminder.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>For instructions about connecting your [!DNL Slack] account to [!DNL Workfront Fusion], see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to [!DNL Adobe Workfront Fusion] - Basic instructions</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Reminder ID]</p> </td> 
   <td> <p>Enter or map the Reminder ID of the reminder you want to retrieve details for.</p> <p>Note: The Reminder ID can be retrieved using another module, such as the [!UICONTROL List Reminders] module.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

-->

+++ **[!UICONTROL Crear un recordatorio]**

Este módulo de acción crea un recordatorio.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text]</td> 
   <td>Introduzca o asigne el contenido del recordatorio</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Hora]</td> 
   <td> <p>Introduzca o asigne la fecha y la hora en que debe producirse este recordatorio. Introduzca una de las siguientes opciones: </p> 
    <ul> 
     <li> <p>La marca de tiempo Unix (hasta cinco años a partir de ahora)</p> </li> 
     <li> <p>El número de segundos hasta el recordatorio (si es en 24 horas) </p> </li> 
     <li> <p>Una descripción en lenguaje natural (por ejemplo: "en 15 minutos" o "todos los jueves")</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL User] </p> </td> 
   <td> <p>Seleccione el usuario que recibe el recordatorio.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

<!--

+++ **[!UICONTROL Complete a Reminder]**

This action module completes a specific reminder.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>For instructions about connecting your [!DNL Slack] account to [!DNL Workfront Fusion], see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to [!DNL Adobe Workfront Fusion] - Basic instructions</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Reminder ID]</p> </td> 
   <td> <p>Enter or map the Reminder ID of the reminder you want to complete.</p> <p>Note: The Reminder ID can be retrieved using another module, such as the [!UICONTROL List Reminders] module.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Delete a Reminder]**

This action module deletes a specific reminder.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>For instructions about connecting your [!DNL Slack] account to [!DNL Workfront Fusion], see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to [!DNL Adobe Workfront Fusion] - Basic instructions</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Reminder ID]</p> </td> 
   <td> <p>Enter or map the Reminder ID of the reminder you want to delete.</p> <p>Note: The Reminder ID can be retrieved using another module, such as the [!UICONTROL List Reminders] module.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

-->

### Eventos

+++ **[!UICONTROL Nuevo evento]**

Este déclencheur instantáneo inicia un escenario cuando se crea un nuevo mensaje u otro evento.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Webhook]</p> </td> 
   <td> <p>Seleccione el webhook que desee utilizar.</p> <p>O</p> <p>Cree un nuevo webhook.</p> 
    <ol> 
     <li value="1"> <p>Haga clic en <b>[!UICONTROL Add]</b>.</p> </li> 
     <li value="2"> <p>Seleccione el tipo de evento.</p> </li> 
     <li value="3"> <p>Seleccione o agregue una conexión. Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Slack] a [!UICONTROL Workfront Fusion], consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a [!UICONTROL Adobe Workfront Fusion]: instrucciones básicas</a></p> </li> 
     <li value="4"> <p>Si se le solicita, seleccione el canal que desee ver.</p> </li> 
     <li value="5"> <p>Haga clic en <b>[!UICONTROL Save]</b> para guardar el webhook y volver al módulo.</p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

+++

### Perfil

+++ **[!UICONTROL Establecer un estado]**

Este módulo de acción actualiza el estado actual de un usuario.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Slack] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Estado texto]</p> </td> 
   <td> <p>Introduzca o asigne el texto de estado. Tenga en cuenta lo siguiente:</p> 
    <ul> 
     <li> <p>Puede introducir hasta 100 caracteres.</p> </li> 
     <li> <p>Puede utilizar marcado u otro formato, como las menciones de usuario.</p> </li> 
     <li> <p>Puede incluir emojis en el texto de estado utilizando el formato <code>:emojiname:</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Estado emoji]</td> 
   <td> <p>Escriba o asigne el emoji que desea utilizar para representar su estado. Use el formato <code>:emojiname:</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expiración de estado]</td> 
   <td>Introduzca o asigne la fecha y la hora en que desea que caduque el estado. Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">Coerción de tipos</a>.</td> 
  </tr> 
 </tbody> 
</table>

+++

### Otro

+++ **[!UICONTROL Realizar una llamada de API]**

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
   td&gt; <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, consulte <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de petición HTTP</a>.</p> </td> 
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
 </tbody> 
</table>

+++

## Terminología

La siguiente terminología puede resultar útil al configurar los módulos de [!DNL Slack]:

* **MD**: [!UICONTROL Mensaje directo]
* **MI**: [!UICONTROL Mensaje instantáneo]
* **Canal privado**: anteriormente, [!UICONTROL Grupo]
* **Mensaje directo**: anteriormente, [!UICONTROL MI]
* **Canal**: [!UICONTROL Conversación] en la documentación de la API, [!UICONTROL canal] en la aplicación [!DNL Slack].

