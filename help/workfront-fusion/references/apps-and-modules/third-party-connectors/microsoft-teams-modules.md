---
title: Módulos de Microsoft Teams
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan Teams, así como conectarlos a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: d3a37c06-8f92-4065-bc00-c35f84b03f82
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '3648'
ht-degree: 12%

---

# Módulos de Microsoft Teams

<!-- ADD REDIRECTS -->

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan Microsoft Teams, así como conectarlos a varias aplicaciones y servicios de terceros.

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

Para utilizar módulos Microsoft Teams, debe tener una cuenta de Microsoft Teams capaz de realizar la acción en el módulo.

## Conexión del servicio de Microsoft Teams a Workfront Fusion

Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte [Crear una conexión a Adobe Workfront Fusion: instrucciones básicas](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

>[!NOTE]
>
>Algunas aplicaciones de Microsoft utilizan la misma conexión, que está vinculada a permisos de usuario individuales. Por lo tanto, al crear una conexión, la pantalla de consentimiento de permisos muestra los permisos que se otorgaron previamente a la conexión de este usuario, además de cualquier nuevo permiso que sea necesario para la aplicación actual.
>
>Por ejemplo, si a un usuario se le han otorgado permisos de &quot;Leer tabla&quot; a través del conector de Excel y luego crea una conexión en el conector de Outlook para leer correos electrónicos, la pantalla de consentimiento de permisos mostrará tanto el permiso de &quot;Leer tabla&quot; ya otorgado como el nuevo permiso requerido de &quot;Escribir correo electrónico&quot;.

## Módulos Microsoft Teams y sus campos

Al configurar los módulos de Microsoft Teams, Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden mostrarse campos de Microsoft Teams adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Equipo](#team)
* [Canal](#channel)
* [Mensaje](#message)
* [Miembro](#member)
* [Reunión en línea](#online-meeting)
* [Otro](#other)

### Equipo

* [Crear un equipo a partir de un grupo](#create-a-team-from-a-group)
* [Crear un grupo de Office 365](#create-an-office-365-group)
* [Eliminar un equipo o grupo](#delete-a-team-or-group)
* [Consigue un equipo](#get-a-team)
* [Mostrar todos los equipos y grupos](#list-all-teams-and-groups)
* [Lista de equipos unidos](#list-joined-teams)
* [Actualizar un equipo](#update-a-team)
* [Ver equipos](#watch-teams)

#### Crear un equipo a partir de un grupo

Este módulo de acción crea un equipo a partir de un grupo existente de Microsoft Office 365 y configura opciones para el nuevo equipo.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Identificador de grupo</td> 
   <td> <p>Seleccione el grupo desde el que desea crear un equipo.</p> 
   </tr> 
  <tr> 
   <td role="rowheader">Permitir que los miembros creen y actualicen canales</td> 
   <td>Seleccione si desea permitir que los miembros creen y actualicen canales.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Permitir que los miembros eliminen canales</td> 
   <td>Seleccione si desea permitir que los miembros eliminen canales.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Permitir que los miembros agreguen y eliminen aplicaciones</td> 
   <td>Seleccione si quiere permitir que los miembros agreguen y eliminen aplicaciones.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Permitir que los miembros creen, actualicen y eliminen fichas</td> 
   <td>Seleccione si desea permitir que los miembros creen, actualicen y eliminen fichas.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Permitir a los miembros crear y quitar conectores</td> 
   <td>Seleccione si desea permitir que los miembros creen y quiten conectores.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Permitir que los usuarios editen sus mensajes</td> 
   <td>Seleccione si desea permitir que los usuarios editen sus mensajes.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Permitir que los usuarios eliminen sus mensajes</td> 
   <td>Seleccione si desea permitir que los usuarios eliminen sus mensajes.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Permitir que los propietarios eliminen mensajes</td> 
   <td>Seleccione si desea permitir que los propietarios eliminen cualquier mensaje.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Permitir menciones @team</td> 
   <td>Seleccione si desea permitir las menciones @team.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Permitir menciones @channel</td> 
   <td>Seleccione si desea permitir las menciones @channel.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Permitir a Giphy</td> 
   <td>Seleccione si desea permitir el uso de Giphy para este equipo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Permitir pegatinas y memes</td> 
   <td>Seleccione si desea permitir que los usuarios incluyan pegatinas y memes.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Permitir memes personalizados</td> 
   <td>Seleccione si desea permitir que los usuarios incluyan memes personalizados.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Permitir que los invitados creen y actualicen canales</td> 
   <td>Seleccione si quiere permitir que los invitados creen y actualicen canales.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Permitir que los invitados eliminen canales</td> 
   <td>Seleccione si quiere permitir que los invitados eliminen canales.</td> 
  </tr> 
 </tbody> 
</table>

#### Crear un grupo de Office 365

Este módulo de acción crea un grupo en Microsoft Office 365.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre para mostrar</td> 
   <td> <p>Escriba o asigne el nombre que este grupo muestra en su libreta de direcciones.</p> 
   </tr> 
  <tr> 
   <td role="rowheader">Alias para grupo</td> 
   <td>Introduzca o asigne el alias de correo electrónico de este grupo. Puede incluir letras minúsculas, números y guiones bajos. Para el tipo de grupo de Office 365, este será el alias de correo electrónico del grupo ([Alias]@[Su dominio].onmicrosoft.com). Para el tipo Grupo de seguridad, el alias funciona como un sobrenombre.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de grupo</td> 
   <td>Seleccione si va a crear un grupo de Office 365 o un grupo de seguridad.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Descripción</td> 
   <td>Escriba o asigne una descripción para este grupo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Seguridad habilitada</td> 
   <td>Active esta opción si desea que el grupo tenga habilitada la seguridad.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Propietarios</td> 
   <td>Seleccione los propietarios de este grupo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Miembros</td> 
   <td>Seleccione los miembros de este grupo.</td> 
  </tr> 
 </tbody> 
</table>

#### Eliminar un equipo o grupo

Este módulo de acción elimina el equipo o grupo especificado.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Identificador de grupo</td> 
   <td> <p>Introduzca o asigne el ID del grupo que desea eliminar.</p> 
   </tr> 
 </tbody> 
</table>

#### Obtener un equipo

Este módulo recupera propiedades y relaciones para el equipo de Microsoft o el grupo de Office 365 especificado.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Identificador de grupo</td> 
   <td> <p>Introduzca o asigne el ID del grupo cuyos detalles desea recuperar.</p> 
   </tr> 
 </tbody> 
</table>

#### Mostrar todos los equipos y grupos

Este módulo enumera todos los equipos de los grupos de Microsoft Teams y Office 365 asociados a la organización. Puede filtrar para devolver solo los resultados que cumplan los criterios especificados.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Filtro</td> 
   <td> <p>Puede definir un filtro para que devuelva únicamente los equipos y grupos que cumplan los criterios seleccionados.</p> <p>Para cada filtro, introduzca el campo que desea que evalúe el filtro, el operador y el valor que desea que permita el filtro. Puede utilizar más de un filtro añadiendo reglas AND u OR.</p> </td> 
   </tr> 
  <tr> 
   <td>Número máximo de resultados devueltos</td> 
   <td>Establezca el número máximo de equipos o grupos que Workfront Fusion devolverá durante un ciclo de ejecución.</td> 
  </tr> 
 </tbody> 
</table>


#### Lista de equipos unidos

Este módulo de acción enumera los equipos a los que se ha unido el usuario asociado con la conexión utilizada en este módulo.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>Número máximo de resultados devueltos</td> 
   <td>Establezca el número máximo de equipos o grupos que Workfront Fusion devolverá durante un ciclo de ejecución.</td> 
  </tr> 
 </tbody> 
</table>

#### Actualizar un equipo

Este módulo de acción actualiza las propiedades de los equipos especificados en Microsoft Teams o en el grupo de Office 365.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre para mostrar</td> 
   <td> <p>Escriba o asigne el nombre que este grupo muestra en su libreta de direcciones.</p> 
   </tr> 
  <tr> 
   <td role="rowheader">Alias para grupo</td> 
   <td>Introduzca o asigne el alias de correo electrónico de este grupo. Puede incluir letras minúsculas, números y guiones bajos. Para el tipo de grupo de Office 365, este será el alias de correo electrónico del grupo ([Alias]@[Su dominio].onmicrosoft.com). Para el tipo de grupo de seguridad, el alias funciona como un sobrenombre.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Descripción</td> 
   <td>Escriba o asigne una descripción para este grupo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Seguridad habilitada</td> 
   <td>Active esta opción si desea que el grupo tenga habilitada la seguridad.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Visibilidad</td> 
   <td>Especifique la visibilidad del grupo de Office 365.</td> 
  </tr> 
 </tbody> 
</table>

#### Ver equipos

Este módulo de déclencheur inicia un escenario cuando se crea un equipo.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Filtro</td> 
   <td> <p>Puede establecer un filtro para inspeccionar solo los equipos y grupos que cumplan los criterios seleccionados.</p> <p>Para cada filtro, introduzca el campo que desea que evalúe el filtro, el operador y el valor que desea que permita el filtro. Puede utilizar más de un filtro añadiendo reglas AND u OR.</p> </td> 
   </tr> 
  <tr> 
   <td>Número máximo de resultados devueltos</td> 
   <td>Establezca el número máximo de equipos o grupos que Workfront Fusion devolverá durante un ciclo de ejecución.</td> 
  </tr> 
 </tbody> 
</table>

### Canal

* [Crear un canal](#create-a-channel)
* [Eliminación de un canal](#delete-a-channel)
* [Obtener un canal](#get-a-channel)
* [Enumerar canales](#list-channels)
* [Actualizar un canal](#update-a-channel)

#### Crear un canal

Este módulo de acción crea un nuevo canal para el equipo especificado.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de equipo</td> 
   <td> <p>Seleccione el equipo de Microsoft Teams para el que desea crear un canal.</p> </td> 
   </tr> 
  <tr> 
   <td>Nombre del canal</td> 
   <td>Introduzca o asigne un nombre para el nuevo canal.</td> 
  </tr> 
  <tr> 
   <td>Descripción</td> 
   <td>Escriba o asigne una descripción para el nuevo canal.</td> 
  </tr> 
 </tbody> 
</table>

#### Eliminación de un canal

Este módulo de acción elimina el canal especificado de un equipo de Microsoft.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de equipo</td> 
   <td> <p>Introduzca o asigne el ID del equipo de Microsoft Teams desde el que desea eliminar un canal.</p> </td> 
   </tr> 
  <tr> 
   <td>ID de canal</td> 
   <td>Introduzca o asigne el ID del canal que desea eliminar.</td> 
  </tr> 
  </tbody> 
</table>

#### Obtener un canal

Este módulo recupera las propiedades y relaciones de un canal.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de equipo</td> 
   <td> <p>Introduzca o asigne el ID del equipo de Microsoft Teams propietario del canal para el que desea recuperar los detalles.</p> </td> 
   </tr> 
  <tr> 
   <td>ID de canal</td> 
   <td>Introduzca o asigne el ID del canal para el que desea recuperar detalles.</td> 
  </tr> 
  </tbody> 
</table>

#### Enumerar canales

Estos módulos enumeran los canales propiedad del equipo especificado en Microsoft Teams.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de equipo</td> 
   <td> <p>Seleccione el equipo de Microsoft Teams para el que desee enumerar los canales.</p> </td> 
   </tr> 
  <tr> 
   <td>Número máximo de resultados devueltos</td> 
   <td>Establezca el número máximo de canales que Workfront Fusion devolverá durante un ciclo de ejecución.</td> 
  </tr> 
  </tbody> 
</table>

#### Actualizar un canal

Este módulo de acción actualiza la descripción del canal especificado.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de equipo</td> 
   <td> <p>Seleccione el equipo de Microsoft Teams que posee el canal que desea actualizar.</p> </td> 
   </tr> 
  <tr> 
   <td>Nombre del canal</td> 
   <td>Introduzca o asigne el nombre del canal que desea actualizar.</td> 
  </tr> 
  <tr> 
   <td>Descripción</td> 
   <td>Introduzca o asigne la nueva descripción del canal.</td> 
  </tr> 
 </tbody> 
</table>

### Mensaje

* [Responder a un mensaje de canal](#reply-to-a-channel-message)
* [Enviar un mensaje](#send-a-message)
* [Ver mensajes](#watch-messages)
* [Ver nuevas respuestas](#watch-new-replies)

#### Responder a un mensaje de canal

Este módulo de acción crea una respuesta a un mensaje en el canal especificado.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de equipo</td> 
   <td> <p>Seleccione el equipo de Microsoft Teams propietario del canal que contiene el mensaje al que desea responder.</p> </td> 
   </tr> 
  <tr> 
   <td>ID de canal</td> 
   <td>Seleccione el canal que contiene el mensaje al que desea responder.</td> 
  </tr> 
  <tr> 
   <td>ID de mensaje</td> 
   <td>Introduzca o asigne el ID del mensaje al que desea responder.</td> 
  </tr> 
  <tr> 
   <td>Tipo de contenido</td> 
   <td>Seleccione si desea enviar el mensaje en texto sin formato o en formato HTML.</td> 
  </tr> 
  <tr> 
   <td>Mensaje de respuesta</td> 
   <td>Introduzca o asigne el cuerpo del mensaje de respuesta que desea enviar.</td> 
  </tr> 
 </tbody> 
</table>

#### Enviar un mensaje

Este módulo de acción envía un mensaje al canal de un equipo o a un chat.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de mensaje/td&gt; 
   <td> <p>Seleccione si va a enviar un mensaje de canal o un mensaje de chat.</p> </td> 
   </tr> 
   <tr> 
   <td role="rowheader">ID de equipo</td> 
   <td> <p>Si está enviando un mensaje a un canal, introduzca o asigne el ID del equipo de Microsoft Teams propietario del canal al que desea enviar un mensaje.</p> </td> 
   </tr> 
  <tr> 
   <td>ID de canal</td> 
   <td>Si está enviando un mensaje a un canal, introduzca o asigne el ID del canal al que desea enviar un mensaje.</td> 
  </tr> 
  <tr> 
   <td>Crear un nuevo chat</td> 
   <td>Si está enviando un mensaje de chat, seleccione si desea crear un nuevo chat.
   <ul><li><b>Sí</b><p>Seleccione si desea un chat individual o un chat grupal, y seleccione el miembro que desea incluir en el chat. Debe seleccionar el usuario asociado con la conexión que utiliza este módulo, y un chat individual debe contener solo ese usuario y otro usuario.</p><p>Si está creando un grupo de chat, puede establecer un tema en el campo Tema.</p>
   <li><b>No</b><p>Introduzca o asigne el ID del equipo propietario del canal al que desea enviar un mensaje y, a continuación, introduzca o asigne el ID del canal.</td> 
  </tr> 
  <tr> 
   <td>Mensaje</td> 
   <td>Introduzca o asigne el cuerpo del mensaje que desea enviar.</td> 
  </tr> 
  <tr> 
   <td>Tipo de contenido</td> 
   <td>Seleccione si desea enviar el mensaje en texto sin formato o en formato HTML.</td> 
  </tr> 
 </tbody> 
</table>

#### Ver mensajes

Este módulo de déclencheur inicia un escenario cuando se envía un mensaje al canal de un equipo o a un chat.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de mensajes a observar</td> 
   <td> <p>Seleccione si desea ver mensajes de canal o mensajes de chat.</p> </td> 
   </tr> 
   <tr> 
   <td role="rowheader">ID de equipo</td> 
   <td> <p>Si está viendo mensajes del canal, seleccione el equipo de Microsoft Teams que posee el canal que está viendo los mensajes.</p> </td> 
   </tr> 
  <tr> 
   <td>ID de canal</td> 
   <td>Si está viendo mensajes del canal, seleccione el canal que desea ver en busca de mensajes.</td> 
  </tr> 
  <tr> 
   <td>ID de chat</td> 
   <td>Si está viendo mensajes de chat, seleccione el chat que desea ver en busca de mensajes.</td> 
  </tr> 
  <tr> 
   <td>Número máximo de mensajes devueltos</td> 
   <td>Establezca el número máximo de mensajes que Workfront Fusion devolverá durante un ciclo de ejecución.</td> 
  </tr> 
 </tbody> 
</table>

#### Ver nuevas respuestas

Este módulo de déclencheur inicia un escenario cuando el mensaje especificado recibe una nueva respuesta.

Este módulo no está disponible para cuentas personales.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">ID de equipo</td> 
   <td> <p>Seleccione el equipo de Microsoft Teams propietario del canal al que quiere ver las respuestas.</p> </td> 
   </tr> 
  <tr> 
   <td>ID de canal</td> 
   <td>Seleccione el canal que desee ver para ver las respuestas.</td> 
  </tr> 
  <tr> 
   <td>ID de mensaje</td> 
   <td>Seleccione el chat que desea ver para obtener respuestas.</td> 
  </tr> 
  <tr> 
   <td>Número máximo de respuestas devueltas</td> 
   <td>Defina el número máximo de respuestas que Workfront Fusion devolverá durante un ciclo de ejecución.</td> 
  </tr> 
 </tbody> 
</table>

### Miembro

* [Agregar un miembro](#add-a-member)
* [Agregar un miembro a un grupo](#add-a-member-to-a-group)

#### Agregar un miembro

Este módulo de acción agrega un miembro a Microsoft Teams.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Nombre de miembro</td> 
   <td> <p>Escriba o asigne el nombre del miembro que desea agregar a Microsoft Teams.</p> </td> 
   </tr> 
  <tr> 
   <td>Contraseña</td> 
   <td>Introduzca o asigne la contraseña del miembro.</td> 
  </tr> 
 </tbody> 
</table>

#### Agregar un miembro a un grupo

Este módulo de acción agrega un miembro a un grupo de Office 365.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Identificador de grupo</td> 
   <td> <p>Seleccione el grupo al que desea agregar un miembro.</p> </td> 
   </tr> 
  <tr> 
   <td>ID de miembro</td> 
   <td>Seleccione el miembro que desea agregar al grupo.</td> 
  </tr> 
 </tbody> 
</table>

### Reunión en línea

* [Crear una reunión en línea](#create-an-online-meeting)
* [Eliminar una reunión en línea](#delete-an-online-meeting)
* [Conseguir una reunión en línea](#get-an-online-meeting)
* [Actualizar una reunión en línea](#update-an-online-meeting)

#### Crear una reunión en línea

Este módulo de acción crea una reunión independiente que no está asociada a un evento en el calendario del usuario. Esta reunión no aparecerá en el calendario del usuario.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Asunto</td> 
   <td>Escriba o asigne un asunto para esta reunión.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Fecha y hora de inicio</td> 
   <td>Escriba o asigne la fecha y la hora en que desea que comience la reunión. Para obtener una lista de los formatos de fecha admitidos, vea <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos</a>.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Fecha y hora de finalización</td> 
   <td>Escriba o asigne la fecha y la hora en que desea que finalice la reunión. Para obtener una lista de los formatos de fecha admitidos, vea <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos</a>.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Presentadores permitidos</td> 
   <td>Seleccione el grupo que puede presentar en esta reunión.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Asistentes</td> 
   <td>Para cada asistente que desee agregar a la reunión, haga clic en <b>Agregar elemento</b> y seleccione el nombre y la función del asistente.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Permitir que los asistentes activen sus cámaras</td> 
   <td>Seleccione si desea permitir que los asistentes activen sus propias cámaras.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Permitir que los asistentes habiliten sus micrófonos</td> 
   <td>Seleccione si desea permitir que los asistentes habiliten sus propios micrófonos.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Permitir chat de reunión</td> 
   <td>Seleccione si desea que el chat de la reunión esté habilitado, deshabilitado o limitado a la duración de la llamada a la reunión</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Permitir reacciones de equipos</td> 
   <td>Seleccione si desea habilitar las reacciones de los equipos para esta reunión.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Identificador de hilo</td> 
   <td>Escriba o asigne el identificador de un subproceso asociado a esta reunión.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">ID de mensaje</td> 
   <td>Escriba o asigne el identificador de un mensaje asociado a esta reunión.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">ID del mensaje de cadena de respuesta</td> 
   <td>Escriba o asigne el identificador de la cadena de respuesta asociada a esta reunión.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Anunciar entrada y salida</td> 
   <td>Seleccione si desea que la reunión anuncie cuándo entran o salen los asistentes.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Ámbito</td> 
   <td>Seleccione el grupo de asistentes que pueden evitar la espera en el vestíbulo. Estos asistentes se unirán directamente a la reunión.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Permitir a los usuarios de acceso telefónico omitir el vestíbulo</td> 
   <td>Seleccione si desea permitir que los usuarios de acceso telefónico omitan el punto de encuentro.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Grabar automáticamente</td> 
   <td>Seleccione si desea grabar la reunión automáticamente.</td> 
   </tr> 
   </tbody> 
</table>

#### Eliminar una reunión en línea

Este módulo de acción elimina la reunión en línea con el ID especificado.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Identificador de reunión</td> 
   <td> <p>Escriba o asigne el identificador de la reunión que desea eliminar.</p> </td> 
   </tr> 
 </tbody> 
</table>

#### Conseguir una reunión en línea

Este módulo de acción recupera los detalles de la reunión en línea con el ID especificado.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Identificador de reunión</td> 
   <td> <p>Escriba o asigne el identificador de la reunión cuyos detalles desea recuperar.</p> </td> 
   </tr> 
 </tbody> 
</table>

#### Actualizar una reunión en línea

Este módulo de acción actualiza la reunión en línea con el identificador especificado.



<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Identificador de reunión</td> 
   <td>Escriba o asigne el identificador de la reunión que desea actualizar.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Asunto</td> 
   <td>Escriba o asigne un asunto para esta reunión.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Fecha y hora de inicio</td> 
   <td>Escriba o asigne la fecha y la hora en que desea que comience la reunión. Para obtener una lista de los formatos de fecha admitidos, vea <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos</a>.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Fecha y hora de finalización</td> 
   <td>Escriba o asigne la fecha y la hora en que desea que finalice la reunión. Para obtener una lista de los formatos de fecha admitidos, vea <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos</a>.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Presentadores permitidos</td> 
   <td>Seleccione el grupo que puede presentar en esta reunión.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Asistentes</td> 
   <td>Para cada asistente que desee agregar a la reunión, haga clic en <b>Agregar elemento</b> y seleccione el nombre y la función del asistente.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Permitir que los asistentes activen sus cámaras</td> 
   <td>Seleccione si desea permitir que los asistentes activen sus propias cámaras.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Permitir que los asistentes habiliten sus micrófonos</td> 
   <td>Seleccione si desea permitir que los asistentes habiliten sus propios micrófonos.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Permitir chat de reunión</td> 
   <td>Seleccione si desea que el chat de la reunión esté habilitado, deshabilitado o limitado a la duración de la llamada a la reunión</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Permitir reacciones de equipos</td> 
   <td>Seleccione si desea habilitar las reacciones de los equipos para esta reunión.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Identificador de hilo</td> 
   <td>Escriba o asigne el identificador de un subproceso asociado a esta reunión.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">ID de mensaje</td> 
   <td>Escriba o asigne el identificador de un mensaje asociado a esta reunión.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">ID del mensaje de cadena de respuesta</td> 
   <td>Escriba o asigne el identificador de la cadena de respuesta asociada a esta reunión.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Anunciar entrada y salida</td> 
   <td>Seleccione si desea que la reunión anuncie cuándo entran o salen los asistentes.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Ámbito</td> 
   <td>Seleccione el grupo de asistentes que pueden evitar la espera en el vestíbulo. Estos asistentes se unirán directamente a la reunión.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Permitir a los usuarios de acceso telefónico omitir el vestíbulo</td> 
   <td>Seleccione si desea permitir que los usuarios de acceso telefónico omitan el punto de encuentro.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Grabar automáticamente</td> 
   <td>Seleccione si desea grabar la reunión automáticamente.</td> 
   </tr> 
   </tbody> 
</table>

### Otro

* [Comprobar la presencia de usuarios](#check-presence-of-users)
* [Realizar una llamada de API personalizada](#make-a-custom-api-call)
* [Buscar usuarios](#search-users)

#### Comprobar la presencia de usuarios

Estos módulos de acción comprueban si los usuarios seleccionados están presentes en Microsoft Teams.

Este módulo no admite cuentas personales.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">ID de usuario</td> 
   <td> <p>Seleccione los usuarios para los que desea comprobar la presencia.</p> </td> 
   </tr> 
 </tbody> 
</table>

#### Realizar una llamada de API personalizada

Este módulo de acción realiza una solicitud personalizada a la API de Microsoft Teams.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Introduzca una ruta relativa a <code>https://graph.microsoft.com</code>. Ejemplo:<code> /v1.0/groups</code></td> 
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

#### Buscar usuarios

Este módulo busca usuarios según los criterios especificados.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft Teams a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Filtro</td> 
   <td> <p>Puede definir un filtro para que devuelva únicamente los usuarios que cumplan los criterios seleccionados.</p> <p>Para cada filtro, introduzca el campo que desea que evalúe el filtro, el operador y el valor que desea que permita el filtro. Puede utilizar más de un filtro añadiendo reglas AND u OR.</p> </td> 
   </tr> 
  <tr> 
   <td>Número máximo de resultados devueltos</td> 
   <td>Establezca el número máximo de equipos o grupos que Workfront Fusion devolverá durante un ciclo de ejecución.</td> 
  </tr> 
 </tbody> 
</table>
