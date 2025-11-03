---
title: Módulos de Google Calendar
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan Google Calendar, así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: 6e514204-cd8e-4f30-bbbb-b8fbe48fc670
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '2696'
ht-degree: 67%

---

# Módulos de [!DNL Google Calendar]

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!UICONTROL Google Calendar], así como conectarlo a varias aplicaciones y servicios de terceros.

Para obtener instrucciones sobre cómo crear un escenario, vea los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

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

Para usar módulos [!DNL Google Calendar], debe tener una cuenta de [!DNL Google].

## Información de API de Google Calendar

El conector Google Calendar utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Dirección URL base</td> 
   <td> https://www.googleapis.com/calendar/v3</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> v3 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 5.4.5</td> 
  </tr>
 </tbody> 
 </table>

## Módulos de [!DNL Google Calendar] y sus campos

Al configurar módulos de [!DNL Google Calendar], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL Google Calendar] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)


* [Activadores](#triggers)
* [Acciones](#actions)
* [Iteradores](#iterators)

### Activadores

* [Ver eventos](#watch-events)
* [Ver eventos (instantáneos)](#watch-events-instant)

#### Ver eventos

Este módulo de activador ejecuta un escenario cuando se añade, actualiza, elimina, inicia o finaliza un nuevo evento en el calendario que especifique. El módulo devuelve todos los campos estándar asociados con el registro o registros, junto con cualquier campo personalizado y valor al que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Google Calendar] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar] </td> 
   <td> <p>Seleccione el calendario con el que desea que funcione el módulo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Watch]</td> 
   <td> <p>Elija si desea ver solo los nuevos eventos o los nuevos eventos y todos los cambios.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Show deleted events]</td> 
   <td> <p>Habilite esta opción para incluir eventos que se hayan eliminado.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query] </td> 
   <td> <p>Escriba el texto para el que desea obtener resultados.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Número máximo de eventos]</td> 
   <td> <p> Establezca el número máximo de eventos con los que Workfront Fusion trabaja durante un ciclo (el número de repeticiones por ejecución de escenario). Si el valor se establece demasiado alto, la conexión se puede interrumpir en el lado del servicio de terceros proporcionado (tiempo de espera). Workfront Fusion no influye en esto. Le recomendamos que establezca un valor menor y defina un valor mayor para el número máximo de ciclos o que ejecute el escenario con más frecuencia.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Ver eventos (instantáneos)

Este módulo de déclencheur utiliza un gancho de correo para crear una dirección de correo electrónico que puede utilizar como invitado a eventos. El módulo inicia un escenario basado en eventos a los que se invita a la dirección de correo electrónico.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Mailhook] </td> 
   <td> <p>Seleccione el mailhook que desee utilizar para este módulo. Para crear un nuevo mailhook, haz clic en <b>Agregar</b> e ingresa la conexión que deseas usar para el mailhook.</p><p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Google Calendar] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Número máximo de eventos]</td> 
   <td> <p> Establezca el número máximo de eventos con los que Workfront Fusion trabaja durante un ciclo (el número de repeticiones por ejecución de escenario). Si el valor se establece demasiado alto, la conexión se puede interrumpir en el lado del servicio de terceros proporcionado (tiempo de espera). Workfront Fusion no influye en esto. Le recomendamos que establezca un valor menor y defina un valor mayor para el número máximo de ciclos o que ejecute el escenario con más frecuencia.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Acciones

* [Creación de un calendario](#create-a-calendar)
* [Creación de un evento](#create-an-event)
* [Eliminación de un evento](#delete-an-event)
* [Obtener eventos](#get-events)
* [Actualización de un evento](#update-an-event)

#### Creación de un calendario

Este módulo de acción crea un calendario asociado a la cuenta.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Google Calendar] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Color] </td> 
   <td> <p>Seleccione el color que desea asociar al calendario.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar name] </td> 
   <td> <p>Escriba o asigne un nombre para el nuevo calendario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Crear un evento]

Este módulo de acción crea un evento.

Especifique el calendario y los parámetros del evento.

El módulo devuelve el ID del evento y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Google Calendar] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar]</td> 
   <td> <p>Seleccione el calendario donde desea que aparezca el evento.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Color]</td> 
   <td>Seleccione el color que el evento muestra en el calendario.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Event name]</td> 
   <td> <p> Introduzca o asigne un nombre para el evento. </p> <p>Nota: Si ha seleccionado [!UICONTROL Quick add] en el campo [!UICONTROL Crear un evento], puede incluir la fecha y la hora del evento, y Workfront Fusion crea el evento para esa fecha y hora. Ejemplo: <code>Appointment at Capitol Hill on June 3rd 10am-10:25am</code>. Si seleccionó [!UICONTROL Quick add] pero no incluye una fecha y hora en el nombre del evento, el evento se creará a partir de la hora actual y durará una hora.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL All day event]</td> 
   <td>Habilite esta opción si el evento dura todo el día (no requiere horas de inicio y finalización).</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Start date]</td> 
   <td> <p>Introduzca o asigne la fecha y hora de inicio del evento. </p> <p>Para obtener una lista de los formatos de fecha admitidos, vea <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL End date]</td> 
   <td> <p> Introduzca o asigne la fecha y hora de finalización del evento. </p> <p>Para obtener una lista de los formatos de fecha admitidos, vea <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Description]</td> 
   <td>Introduzca o asigne una descripción para el evento. Este campo admite HTML.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Location]</td> 
   <td>Introduzca una ubicación para el evento en forma de texto.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Use the default reminder settings for this event]</td> 
   <td>Habilite esta opción para utilizar la configuración de recordatorio predeterminada. Si establece un aviso personalizado en el campo [!UICONTROL Reminder], este valor se establece en No.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Reminder] </td> 
   <td> <p>Añada un recordatorio para el evento. Para cada recordatorio que desee agregar, haga clic en <b>Agregar elemento</b>, luego seleccione el método con el que desea que se le recuerde y defina cuánto tiempo (en minutos) antes del evento desea que se le recuerde.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Attendees]</td> 
   <td>Añada los asistentes al evento. Para cada asistente, haga clic en <b>Agregar un asistente</b> y escriba o asigne su nombre y dirección de correo electrónico.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Show me as]</td> 
   <td>Seleccione si desea que las personas que ven el calendario lo vean como Ocupado o Disponible durante este evento.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Visibility] </td> 
   <td> <p>Seleccione la visibilidad de este evento. </p> 
    <ul> 
     <li> <p><b>[!UICONTROL Default]</b></p> <p>El evento tiene la visibilidad que ha establecido en la configuración del calendario.</p> </li> 
     <li> <p><b>[!UICONTROL Public]</b></p> <p>Cualquier persona con la que se comparta el calendario puede ver este evento.</p> </li> 
     <li> <p><b>[!UICONTROL Private]</b></p> <p>Solo los asistentes pueden ver este evento.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Send notification about the event creation]</td> 
   <td> <p>Seleccione si desea enviar notificaciones sobre la creación de un nuevo evento a todos los invitados, a invitados que no sean de [!DNL Google Calendar] o a nadie.</p> <p>Sugerencia: Recomendamos utilizar la opción [!UICONTROL None] solo en los casos de uso de migración.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Guests can modify the event]</td> 
   <td> <p>Habilite esta opción si desea que los invitados puedan modificar este evento.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Recurrence]</td> 
   <td>Añada las reglas de periodicidad que desee aplicar a este evento. Cada regla requiere una lista de líneas [!UICONTROL RRULE], [!UICONTROL EXRULE], [!UICONTROL RDATE] y [!UICONTROL EXDATE] para un evento recurrente. Tenga en cuenta que las líneas [!UICONTROL DTSTART] y [!UICONTROL DTEND] no están permitidas en este campo; las horas de inicio y finalización de los eventos se especifican en los campos de inicio y finalización. Este campo se omite para eventos únicos o instancias de eventos recurrentes. Para obtener más información, consulte <a href="https://tools.ietf.org/html/rfc5545#section-3.8.5">RFC5545</a>.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Eliminar un evento]

Este módulo de acción elimina un evento.

Especifique el calendario y el ID de evento.

El módulo devuelve el ID del evento y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Google Calendar] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar]</td> 
   <td> <p>Seleccione el calendario que contiene el evento que desea eliminar.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Event ID]</td> 
   <td> <p> Introduzca el ID de evento de un evento de [!DNL Google Calendar] creado anteriormente que desee eliminar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Obtener eventos]

Este módulo recupera información sobre los eventos del calendario seleccionado en función de los criterios especificados.

Especifique el calendario y los parámetros de la búsqueda.

El módulo devuelve el ID de los eventos y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Google Calendar] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar]</td> 
   <td> <p>Seleccione el calendario para el que desea recuperar eventos.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Start date]</td> 
   <td> <p> Introduzca o asigne la fecha en la que se inicia el evento. Este módulo también recupera eventos que comienzan antes de esta fecha y que aún se producen en la fecha de inicio introducida. </p> <p>Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL End date]</td> 
   <td> <p> Introduzca o asigne la fecha en la que termina el evento. </p> <p> Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Single events]</td> 
   <td> <p> Habilite esta opción para tratar los eventos recurrentes como instancias únicas. Por ejemplo, si tiene una reunión semanal y esta opción está habilitada, el módulo devolverá la reunión de cada semana como un evento independiente.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query]</td> 
   <td> <p>Introduzca o asigne el término de búsqueda por el que desea buscar. </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Order by]</td> 
   <td> <p>Seleccione el orden de los eventos devueltos en el resultado.</p> 
    <ul> 
     <li><strong>[!UICONTROL Start Time]</strong>: ordene por fecha y hora de inicio (orden ascendente). Esto solo está disponible cuando se consultan eventos únicos.</li> 
     <li><strong>[!UICONTROL Updated Time]</strong>: ordene por hora de última modificación (orden ascendente).</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Número máximo de eventos devueltos]</td> 
   <td> <p>Establezca el número máximo de eventos que Workfront Fusion devuelve durante un ciclo de ejecución.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Actualizar un evento]

Este módulo de acción cambia un evento existente.

Especifique el calendario y el ID de evento.

El módulo devuelve el ID del evento y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Google Calendar] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar] </td> 
   <td> <p>Seleccione el calendario con el que desea trabajar.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Event ID] </td> 
   <td> <p>Introduzca el ID de evento del evento de [!DNL Google Calendar] creado anteriormente que desee actualizar.</p> </td> 
  </tr>   <tr> 
   <td>[!UICONTROL Event name]</td> 
   <td> <p> Introduzca o asigne un nombre para el evento. </p> <p>Nota: Si ha seleccionado [!UICONTROL Quick add] en el campo [!UICONTROL Crear un evento], puede incluir la fecha y la hora del evento, y Workfront Fusion crea el evento para esa fecha y hora. Ejemplo: <code>Appointment at Capitol Hill on June 3rd 10am-10:25am</code>. Si seleccionó [!UICONTROL Quick add] pero no incluye una fecha y hora en el nombre del evento, el evento se creará a partir de la hora actual y durará una hora.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL All day event]</td> 
   <td>Habilite esta opción si el evento dura todo el día (no requiere horas de inicio y finalización).</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Start date]</td> 
   <td> <p>Introduzca o asigne la fecha y hora de inicio del evento. </p> <p>Para obtener una lista de los formatos de fecha admitidos, vea <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL End date]</td> 
   <td> <p> Introduzca o asigne la fecha y hora de finalización del evento. </p> <p>Para obtener una lista de los formatos de fecha admitidos, vea <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Description]</td> 
   <td>Introduzca o asigne una descripción para el evento. Este campo admite HTML.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Location]</td> 
   <td>Introduzca una ubicación para el evento en forma de texto.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Use the default reminder settings for this event]</td> 
   <td>Habilite esta opción para utilizar la configuración de recordatorio predeterminada. Si establece un aviso personalizado en el campo [!UICONTROL Reminder], este valor se establece en No.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Reminder] </td> 
   <td> <p>Añada un recordatorio para el evento. Para cada recordatorio que desee agregar, haga clic en <b>Agregar elemento</b>, luego seleccione el método con el que desea que se le recuerde y defina cuánto tiempo (en minutos) antes del evento desea que se le recuerde.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Attendees]</td> 
   <td>Añada los asistentes al evento. Para cada asistente, haga clic en <b>Agregar un asistente</b> y escriba o asigne su nombre y dirección de correo electrónico.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Show me as]</td> 
   <td>Seleccione si desea que las personas que ven el calendario lo vean como Ocupado o Disponible durante este evento.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Visibility] </td> 
   <td> <p>Seleccione la visibilidad de este evento. </p> 
    <ul> 
     <li> <p><b>[!UICONTROL Default]</b></p> <p>El evento tiene la visibilidad que ha establecido en la configuración del calendario.</p> </li> 
     <li> <p><b>[!UICONTROL Public]</b></p> <p>Cualquier persona con la que se comparta el calendario puede ver este evento.</p> </li> 
     <li> <p><b>[!UICONTROL Private]</b></p> <p>Solo los asistentes pueden ver este evento.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Send notification about the event creation]</td> 
   <td> <p>Seleccione si desea enviar notificaciones sobre la creación de un nuevo evento a todos los invitados, a invitados que no sean de [!DNL Google Calendar] o a nadie.</p> <p>Sugerencia: Recomendamos utilizar la opción [!UICONTROL None] solo en los casos de uso de migración.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Guests can modify the event]</td> 
   <td> <p>Habilite esta opción si desea que los invitados puedan modificar este evento.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Recurrence]</td> 
   <td>Añada las reglas de periodicidad que desee aplicar a este evento. Cada regla requiere una lista de líneas [!UICONTROL RRULE], [!UICONTROL EXRULE], [!UICONTROL RDATE] y [!UICONTROL EXDATE] para un evento recurrente. Tenga en cuenta que las líneas [!UICONTROL DTSTART] y [!UICONTROL DTEND] no están permitidas en este campo; las horas de inicio y finalización de los eventos se especifican en los campos de inicio y finalización. Este campo se omite para eventos únicos o instancias de eventos recurrentes. Para obtener más información, consulte <a href="https://tools.ietf.org/html/rfc5545#section-3.8.5">RFC5545</a>.</td> 
  </tr>

</tbody> 
</table>

### Iteradores

#### Repetir archivos adjuntos

Estos módulos de acción iteran a través de los archivos adjuntos en un evento y generan cada archivo adjunto en un paquete independiente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Source module] </td> 
   <td> Seleccione el módulo en este escenario que genera el evento que contiene los archivos adjuntos que desea repetir. </td> 
  </tr> 
 </tbody> 
</table>

#### Iterar asistentes

Estos módulos de acción recorren en iteración los asistentes de un evento y generan cada asistente en un paquete independiente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Source module] </td> 
   <td> Seleccione el módulo en este escenario que genera el evento que contiene los asistentes que desea repetir. </td> 
  </tr> 
 </tbody> 
</table>





## Activador de un escenario antes de un evento

Puede activar un escenario en un tiempo especificado antes de un evento con la ayuda de [!DNL Google Calendar] recordatorios de correo electrónico estándar y el módulo [!UICONTROL Webhooks] >[!UICONTROL mailhook personalizado].

1. Use el módulo [!UICONTROL Calendario de Google] >[!UICONTROL Actualizar un evento] para añadir un recordatorio por correo electrónico al evento:

   ![Escenario de Déclencheur antes del evento](/help/workfront-fusion/references/apps-and-modules/assets/trigger-scen-before-event-350x209.png)

1. Cree un nuevo escenario a partir del módulo [!UICONTROL Webhooks] >[!UICONTROL mailhook personalizado].

   1. Copie la dirección de correo electrónico del mailhook.
   1. Guarde el escenario y ejecútelo.

1. En [!DNL Gmail], redirija los recordatorios de correo electrónico de [!DNL Google Calendar] a la dirección de correo electrónico del mailhook:

   1. Abra la configuración de **[!UICONTROL [!DNL Gmail]]**.
   1. Abra la pestaña **[!UICONTROL Reenvío y POP/IMAP]**.
   1. Haga clic en **[!UICONTROL Añadir una dirección de reenvío].**
   1. Pegue la dirección de correo electrónico de los mailhooks copiados, haga clic en&#x200B;**[!UICONTROL Siguiente]**, confirme pulsando **[!UICONTROL Continuar]** en la ventana emergente y, a continuación, haga clic en **[!UICONTROL Aceptar]**.

   1. En Workfront Fusion, cambie al nuevo escenario que debería finalizar su ejecución al recibir el correo electrónico de confirmación.
   1. Haga clic en la burbuja situada encima del módulo para inspeccionar su salida.
   1. Expanda el elemento `Text` y copie el código de confirmación:

      ![Código de confirmación](/help/workfront-fusion/references/apps-and-modules/assets/confirmation-code-350x252.png)

   1. En Gmail, pegue el código de confirmación en el cuadro de edición y haga clic en&#x200B;**[!UICONTROL Verificar]**:

      ![Pegar código](/help/workfront-fusion/references/apps-and-modules/assets/paste-code-350x46.png)

   1. Abra la pestaña **[!UICONTROL Filtros y direcciones bloqueadas]**.
   1. Haga clic en **[!UICONTROL Crear un nuevo filtro]**.
   1. Configure un filtro para todos los correos electrónicos que provengan de `     calendar-notification@google.com` y haga clic en&#x200B;**[!UICONTROL Crear un filtro]**:
   1. Seleccione **[!UICONTROL Reenviarlo a]** y elija la dirección de correo electrónico de los mailhooks de la lista.
   1. Haga clic en **[!UICONTROL Crear filtro]** para crear el filtro.

1. (Opcional) En Workfront Fusion, agregue el módulo [!UICONTROL Analizador de texto] > [!UICONTROL Patrón de coincidencia] después del módulo [!UICONTROL Webhooks] >[!UICONTROL Gancho de correo personalizado] para analizar el código HTML del correo electrónico y obtener la información que necesite.

   Por ejemplo, puede configurar el módulo de la siguiente manera para obtener el ID del evento:

   *Patrón*: `<meta itemprop="eventId/googleCalendar" content="(?<evenitID>.*?)"/>`

   *Texto*: el elemento `HTML content` se ha extraído del módulo [!UICONTROL Webhooks] >[!UICONTROL Mailhook personalizado].
