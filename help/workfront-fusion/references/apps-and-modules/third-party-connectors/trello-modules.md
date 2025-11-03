---
title: Módulos Trello
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan Trello, así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: 5df5cd2b-ad4c-4a02-9d0c-7cee35232f93
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '5386'
ht-degree: 69%

---

# Módulos de [!UICONTROL Trello]

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!UICONTROL Trello], así como conectarlo a varias aplicaciones y servicios de terceros.

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

Para usar módulos [!DNL Trello], debe tener una cuenta de [!UICONTROL Trello].

## Información de API de Trello

El conector Trello utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Dirección URL base</td> 
   <td> https://api.trello.com/1</td>
  </tr> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> Versión 1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>v4.12.37</td> 
  </tr>
 </tbody> 
 </table>

## Conectar [!UICONTROL Trello] a Workfront Fusion

Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte [Crear una conexión a Adobe Workfront Fusion: instrucciones básicas](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

## Módulos [!UICONTROL Trello] y sus campos

Al configurar los módulos [!UICONTROL Trello], Workfront Fusion muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse campos [!UICONTROL Trello] adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Tableros](#boards)
* [Listas](#lists)
* [Tarjetas](#cards)
* [Miembros](#members)
* [Listas de verificación](#checklists)
* [Etiquetas](#labels)
* [Comentarios](#comments)

### Tableros

+++ **[!UICONTROL Archivar o desarchivar un tablero]**

Este módulo de acción cierra (archiva) o vuelve a abrir (desarchiva) un tablero que haya especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Board ID]</td> 
   <td> <p> Introduzca o asigne el ID del tablero que desea cerrar o volver a abrir.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Archive or unarchive]</td> 
   <td> <p> Seleccione si desea cerrar (archivar) o volver a abrir (desarchivar) el tablero.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Asignar un miembro a un tablero]**

Este módulo de acción asigna un miembro al tablero que especifique. 

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Board ID]</td> 
   <td> <p> Seleccione el tablero en el que desea añadir un miembro.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Email address]</td> 
   <td> <p> Escriba o asigne la dirección de correo electrónico del miembro que desea añadir al tablero.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Member type]</p> </td> 
   <td> <p>Seleccione el tipo de miembro que desea que sea el nuevo miembro.</p> 
    <ul> 
     <li><strong>[!UICONTROL Admin]</strong>: un administrador del tablero puede realizar cualquier acción en el tablero.</li> 
     <li><strong>[!UICONTROL Normal]</strong>: un miembro normal es simplemente un miembro del tablero.</li> 
     <li><strong>[!UICONTROL Observer]</strong>: un observador es un miembro con acceso de solo lectura al tablero. <br>Los observadores solo están disponibles para los equipos con [!UICONTROL Trello Business Class].</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Full name]</td> 
   <td> <p> Introduzca o asigne el nombre completo del usuario que desea agregar al tablero.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Create a Board]**

Este módulo de acción crea un tablero nuevo con la configuración seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>Introduzca o asigne un nombre para el nuevo tablero.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td> <p>Introduzca o asigne la descripción del tablero si es necesario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Organization ID]</p> </td> 
   <td> <p>Introduzca o asigne el ID de la organización. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Permission level]</p> </td> 
   <td> <p>Los tableros tienen diferentes reglas de votación y comentarios para cada nivel de permiso. Por ejemplo, si el tablero es [!UICONTROL Private] y establece las reglas de votación y comentarios como [!UICONTROL All], recibirá un error. </p> <p>Votar y comentar está limitado a los siguientes grupos para cada nivel de permiso:</p> 
    <ul> 
     <li><strong>[!UICONTROL Privado]</strong>: 
      Miembros, miembros y observadores</li> 
     <li><strong>[!UICONTROL Para la organización]</strong>: 
      Miembros, Miembros y Observadores, Miembros de la Organización</li> 
     <li><strong>[!UICONTROL Público]</strong>: 
      Miembros, Miembros y Observadores, Miembros de la Organización, Todos</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Voting]</p> </td> 
   <td> <p>Seleccione una opción para especificar quién puede votar en este tablero. Consulte el campo [!UICONTROL Permission level] para ver las limitaciones de voto en los niveles de permiso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Comments]</p> </td> 
   <td> <p>Seleccione una opción para especificar quién puede realizar comentarios en las tarjetas de este tablero. Consulte el campo [!UICONTROL Permission level] para comentar las limitaciones de los niveles de permiso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Invitations]</p> </td> 
   <td> <p>Seleccione quién puede invitar a otras personas a este tablero.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Self-join]</p> </td> 
   <td> <p>Seleccione si los integrantes del equipo pueden unirse al tablero ellos mismos o si tienen que ser invitados.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Default labels]</p> </td> 
   <td> <p>Seleccione si desea utilizar el conjunto predeterminado de etiquetas para el nuevo tablero.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Default lists]</p> </td> 
   <td> <p>Seleccione si desea añadir el conjunto predeterminado de listas al tablero ([!UICONTROL To Do], [!UICONTROL Doing], [!UICONTROL Done]).</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Board source ID]</p> </td> 
   <td> <p>Seleccione o asigne el ID del tablero que desea copiar en el nuevo tablero.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Card Covers]</p> </td> 
   <td> <p>Seleccione <strong>[!UICONTROL Yes]</strong> si desea habilitar las cubiertas de tarjeta para el tablero.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Background]</p> </td> 
   <td> <p>Seleccione el color del fondo o el fondo personalizado.</p> <p>Nota: los fondos personalizados solo están disponibles para suscriptores de [!UICONTROL Trello Gold and Business Class].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Background ID]</td> 
   <td> <p> Si ha seleccionado utilizar un fondo personalizado en el campo [!UICONTROL Fondo], introduzca o asigne el ID del fondo que desea utilizar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Card aging]</p> </td> 
   <td> <p>Seleccione entre dos modos de caducidad de la tarjeta. </p> 
    <ul> 
     <li><strong>[!UICONTROL modo pirata]</strong>: Las cartas se rasgarán, se pondrán amarillas y se agrietarán como un viejo mapa pirata a medida que envejezcan.</li> 
     <li><strong>[!UICONTROL Modo normal ]</strong>: Las tarjetas se vuelven cada vez más transparentes a medida que envejecen. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Editar un tablero]**

Este módulo de acción edita la configuración de un tablero existente.

>[!SUCCESS]
>
><table style="table-layout:auto">
<col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Board ID]</p> </td> 
   <td> <p>Introduzca o asigne el ID [!UICONTROL Trello] único del tablero que desea que cree el módulo. Puede recuperar el ID de tablero con otro módulo, como el módulo Tableros de observación</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/watch-boards.png"> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New name]</td> 
   <td> <p> Introduzca o asigne un nombre nuevo para el tablero.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New description]</td> 
   <td> <p> Introduzca o asigne una nueva descripción de tablero.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Organization ID]</p> </td> 
   <td> <p>Introduzca o asigne el ID [!UICONTROL Trello] único del tablero que desea que edite el módulo.  </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subscribe] </td> 
   <td> <p>Seleccione una opción para especificar si el usuario propietario de la conexión utilizada por este módulo está suscrito al tablero.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Permission level]</p> </td> 
   <td> <p>Los tableros tienen diferentes reglas de votación y comentarios para cada nivel de permiso. Por ejemplo: si el tablero es [!UICONTROL Private] y establece las reglas de votación y comentarios como [!UICONTROL All], recibirá un error. </p> <p>Votar y comentar está limitado a los siguientes grupos para cada nivel de permiso:</p> 
    <ul> 
     <li><strong>[!UICONTROL Privado]</strong>: 
      Miembros, miembros y observadores</li> 
     <li><strong>[!UICONTROL Para la organización]</strong>: 
      Miembros, Miembros y Observadores, Miembros de la Organización</li> 
     <li><strong>[!UICONTROL Público]</strong>: 
      Miembros, Miembros y Observadores, Miembros de la Organización, Todos</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Voting]</p> </td> 
   <td> <p>Seleccione una opción para especificar quién puede votar en este tablero. Consulte el campo [!UICONTROL Permission level] para ver las limitaciones de voto en los niveles de permiso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Comments]</p> </td> 
   <td> <p>Seleccione una opción para especificar quién puede realizar comentarios en las tarjetas de este tablero. Consulte el campo [!UICONTROL Permission level] para comentar las limitaciones de los niveles de permiso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Invitations] </td> 
   <td> <p>Seleccione quién puede invitar a personas a este tablero.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Self-join]</td> 
   <td> <p> Seleccione si los integrantes del equipo pueden unirse al tablero ellos mismos o si tienen que ser invitados.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Card covers]</td> 
   <td> <p> Seleccione si las cubiertas de tarjeta deben mostrarse en este tablero.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Background] </td> 
   <td> <p>Seleccione el color del fondo o el fondo personalizado.</p> <p>Nota: los fondos personalizados solo están disponibles para suscriptores de [!UICONTROL Trello Gold and Business Class].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Background ID]</td> 
   <td> <p> Si ha seleccionado utilizar un fondo personalizado en el campo [!UICONTROL Fondo], introduzca o asigne el ID del fondo que desea utilizar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Card aging]</p> </td> 
   <td> <p>Seleccione entre dos modos de caducidad de la tarjeta. </p> 
    <ul> 
     <li><strong>[!UICONTROL modo pirata]</strong>: Las cartas se rasgarán, se pondrán amarillas y se agrietarán como un viejo mapa pirata a medida que envejezcan.</li> 
     <li><strong>[!UICONTROL Modo normal]</strong>: Las tarjetas se vuelven cada vez más transparentes a medida que envejecen. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar feed enabled]</td> 
   <td> <p> Seleccione si la fuente del calendario está habilitada o no.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL &lt;Color&gt; label name]</td> 
   <td> <p> Asigne un nombre a la etiqueta de color que desee.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Archive] </td> 
   <td> <p>Seleccione una opción para indicar si desea archivar (cerrar) el tablero. </p> </td> 
  </tr> 
 </tbody> 
</table>


+++

+++ **[!UICONTROL Get a Board]**

Este módulo de acción recupera los detalles de un tablero.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Board ID]</p> </td> 
   <td> <p>Introduzca o asigne el ID del tablero sobre el que desea recuperar información.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!DNL Search for Boards]**

Este módulo de búsqueda recupera información sobre un tablero que usted especifique.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query] </td> 
   <td> <p>Introduzca o asigne el nombre (o una parte del nombre) del tablero sobre el que desea obtener información.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned boards]</td> 
   <td> <p> Introduzca el número máximo de tableros que Workfront Fusion devolverá durante un ciclo de ejecución. Este valor debe ser menor o igual a 1000.</p>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Partial] </p> </td> 
   <td> <p>De forma predeterminada, este módulo busca coincidencias exactas de cada palabra de la consulta en el contenido de los abonados. Cuando se ha habilitado [!UICONTROL Partial], el módulo busca contenido que comience con cualquier palabra de la consulta.</p> <p> Por ejemplo, si está utilizando la palabra “desarrollo” para buscar un tablero llamado “Mi informe de estado de desarrollo”, de forma predeterminada debería realizar una búsqueda de palabra completa. Si ha habilitado [!UICONTROL Partial], podrá buscar “des” pero no “desarrollo”.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Boards] </td> 
   <td> <p>Escriba “mío” o asigne una lista de ID de tablero separados por comas.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Anular la asignación de un miembro del tablero]**

Este módulo de acción elimina un miembro de un tablero.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Board ID]</td> 
   <td> <p> Introduzca (asigne o seleccione) el ID del tablero desde el que desea eliminar al usuario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Member] </td> 
   <td> <p>Seleccione el miembro que desea eliminar del tablero.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Watch Boards]**

Este módulo de activador inicia un escenario cuando se añade un nuevo tablero.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Introduzca o asigne el número máximo de tableros que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### Listas

+++ **[!UICONTROL Create a List]**

Este módulo de acción crea una lista en un tablero que se especifique. 

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Board ID]</td> 
   <td> <p> Introduzca o asigne el ID del tablero en el que desea crear una lista.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>Introduzca o asigne un nombre para la nueva lista.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Position] </td> 
   <td> <p>Seleccione si desea añadir la lista al principio o anexarla al final de la tarjeta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy list]</td> 
   <td> <p> Si está copiando una lista, seleccione cómo desea introducir el ID de la lista que desea copiar.</p> 
    <ul> 
     <li> <p><strong>Enter manually</strong> </p> <p>En el campo <strong>[!UICONTROL List ID]</strong>, escriba o asigne el ID de la lista que desea copiar.<br></p> </li> 
     <li> <p><strong>Select</strong> </p> <p>Seleccione el tablero que contiene la lista que desea copiar y, a continuación, seleccione la lista.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Edit a List]**

Este módulo de acción edita una lista existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List ID]</td> 
   <td> <p> Introduzca o asigne el ID de la lista que desea actualizar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>Introduzca o asigne un nuevo nombre para la lista.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Board ID]</td> 
   <td> <p> Asigne o seleccione el tablero al que desea mover la lista.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Position] </td> 
   <td> <p>Seleccione si desea añadir la lista al principio o anexarla al final de la tarjeta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subscribed]</td> 
   <td> <p>Habilite esta opción si desea suscribir al miembro activo a la lista.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Get a List]**

Este módulo de acción recupera detalles sobre una lista específica.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL List ID]</p> </td> 
   <td> <p>Introduzca o asigne el ID de la lista sobre la que desea recuperar información.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Ver tarjetas trasladadas a una lista]**

Este módulo del activador se activa cuando se mueve una tarjeta a una lista específica.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Board]</td> 
   <td>Seleccione el tablero que contiene la lista que desea ver para las tarjetas.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List]</td> 
   <td>Seleccione la lista que desea ver para las tarjetas.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### Tarjetas

+++ **[!UICONTROL Add an Attachment]**

Este módulo de acción añade un archivo adjunto a la tarjeta seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter card ID]</td> 
   <td> <p> Seleccione cómo desea introducir el ID de la tarjeta a la que desea agregar un archivo adjunto.</p> 
    <ul> 
     <li> <p><strong>Enter manually</strong> </p> <p>En el campo <strong>[!UICONTROL ID de tarjeta]</strong>, escriba o asigne el ID de la tarjeta a la que desea agregar un archivo adjunto.<br></p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>Seleccione el tablero que contiene la tarjeta a la que desea agregar un archivo adjunto, seleccione la lista que contiene la tarjeta y, a continuación, seleccione la tarjeta.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachment type]</p> </td> 
   <td> <p>Seleccione si desea cargar el archivo directamente o proporcionar una dirección URL para el archivo.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL File]</strong> </p> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </li> 
     <li> <p><strong>[!UICONTROL URL]</strong> </p> <p>Introduzca la dirección URL del archivo y proporcione un nombre para el archivo adjunto.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Archive or Unarchive a Card]**

Este módulo de acción archiva o devuelve una tarjeta al tablero.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Card ID]</td> 
   <td> <p> Introduzca o asigne el ID de la tarjeta que desea archivar o devolver al tablero.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Archive or unarchive]</td> 
   <td> <p> Seleccione si desea cerrar la tarjeta (archivar) o enviarla de vuelta al tablero (desarchivar).</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Create a card]**

Este módulo de acción crea una tarjeta en una lista seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a list ID]</td> 
   <td> <p> Seleccione cómo desea introducir el ID de la lista en la que desea añadir una tarjeta.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>En el campo <strong>[!UICONTROL List ID]</strong>, escriba o asigne el ID de la lista a la que desea añadir una tarjeta.<br></p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>Seleccione el tablero que contiene la lista donde desea agregar una tarjeta y, a continuación, seleccione la lista.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Labels] </td> 
   <td> <p>Para cada etiqueta que desee agregar a la tarjeta, haga clic en <b>Agregar elemento</b> e introduzca el identificador de la etiqueta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Members]</td> 
   <td>Para cada miembro que desee agregar a la tarjeta, haga clic en <b>Agregar elemento</b> e introduzca el identificador del miembro. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>Introduzca un nombre para la nueva tarjeta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Description]</p> </td> 
   <td> <p>Escriba una descripción para la tarjeta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Position] </td> 
   <td> <p>Seleccione si desea agregar la tarjeta al principio o anexarla al final de la lista.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Due date]</td> 
   <td> <p> Escriba una fecha de límite para la tarjeta. Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Due complete]</td> 
   <td> <p> Active esta opción para marcar la tarjeta como completada en la fecha de vencimiento.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File URL]</td> 
   <td> <p>Introduzca o asigne la dirección URL del archivo que desee añadir como datos adjuntos a la tarjeta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Source file]</p> </td> 
   <td> <p>Escriba o asigne información para un archivo que desee agregar como datos adjuntos a la tarjeta. Seleccione un archivo de un módulo anterior o asigne el nombre y los datos del archivo</p> 
     <p>Nota: Hay un límite de carga de archivos de 10 MB por archivo adjunto. Sin embargo, los miembros de [!UICONTROL Business Class] y [!UICONTROL Trello Gold] tienen un límite de carga de archivos de 250 MB por archivo adjunto.</p> 
     </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy card]</td> 
   <td> <p> Si está creando una tarjeta nueva como copia de una tarjeta existente, seleccione cómo desea introducir el ID de la tarjeta que desea copiar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>En el campo <strong>[!UICONTROL Card ID]</strong>, escriba o asigne el ID de la tarjeta que desea copiar.<br></p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>Seleccione el tablero que contiene la tarjeta que desea copiar y, a continuación, seleccione la lista que contiene la tarjeta. A continuación, seleccione la tarjeta.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Edit a Card]**

Este módulo de acción edita una tarjeta existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Card ID]</td> 
   <td> <p> Seleccione cómo desea introducir el ID de la tarjeta que desea editar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>En el campo <strong>[!UICONTROL Card ID]</strong>, escriba o asigne el ID de la tarjeta que desea editar.<br></p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>Seleccione el tablero que contiene la tarjeta que desea editar, luego seleccione la lista que contiene la tarjeta y, a continuación, seleccione la tarjeta.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New name]</td> 
   <td> <p>Escriba o asigne un nombre nuevo para la tarjeta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL New description]</p> </td> 
   <td> <p>Escriba o asigne una nueva descripción para la tarjeta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Move a card]</p> </td> 
   <td> <p>Seleccione el tablero o el tablero y la lista dónde desea mover la tarjeta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Labels] </td> 
   <td> <p>Para cada etiqueta que desee agregar a la tarjeta, haga clic en <b>Agregar elemento</b> e introduzca el identificador de la etiqueta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Position] </td> 
   <td> <p>Seleccione si desea añadir la tarjeta al principio o [!UICONTROL append] la tarjeta al final de la lista.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Due date]</td> 
   <td> <p> Escriba una fecha de límite para la tarjeta. Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Due complete]</td> 
   <td> <p> Active esta opción para marcar la tarjeta como completada en la fecha de vencimiento.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Members] </td> 
   <td> <p>Para cada miembro que desee agregar a la tarjeta, haga clic en <b>Agregar elemento</b> y escriba o asigne el identificador del miembro.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachment cover ID]</p> </td> 
   <td> <p>Introduzca o asigne el ID del archivo adjunto de imagen que desea que la tarjeta use como portada.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subscribe] </td> 
   <td> <p>Seleccione si el miembro debe suscribirse a la tarjeta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Archive] </td> 
   <td> <p>Seleccione una opción para indicar si desea archivar (cerrar) la tarjeta. </p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Get a Card]**

Este módulo de acción recupera los detalles de una tarjeta seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Board ID]</td> 
   <td> <p>Introduzca el ID del tablero que contiene la tarjeta sobre la que desea recuperar los detalles. Esto le permite ver los nombres de los campos personalizados del tablero.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter card ID]</td> 
   <td> <p> Seleccione cómo desea introducir el ID de la tarjeta cuyos detalles desea recuperar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>En el campo <strong>[!UICONTROL Card ID]</strong>, escriba o asigne el ID de la tarjeta cuyos detalles desee recuperar.<br></p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>Seleccione el tablero que contiene la tarjeta sobre la que desea recuperar los detalles, luego seleccione la lista que contiene la tarjeta y, a continuación, seleccione la tarjeta.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Search for Cards]**

Este módulo de acción devuelve tarjetas que coinciden con la consulta de búsqueda.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Board] </td> 
   <td> <p>Seleccione los tableros en los que quiera buscar. Si no se ha seleccionado ningún tablero, se buscarán todos los tableros.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Query]</p> </td> 
   <td> <p>Introduzca la consulta de búsqueda. Puede restringir la búsqueda mediante los siguientes operadores de búsqueda:</p> 
    <ul> 
     <li><code><strong>-operator</strong></code> <p>Puede añadir "-" a cualquier operador para realizar una búsqueda negativa, como <code>[!UICONTROL -has:members]</code> para buscar tarjetas sin ningún miembro asignado.</p> </li> 
     <li><code><strong>@name</strong></code> <p>Devuelve las tarjetas asignadas a un miembro. También puede usar <code>member:</code>. Use <code>@me</code> para incluir solamente sus tarjetas.</p> </li> 
     <li><code><strong>#label</strong></code> <p>Devuelve tarjetas etiquetadas. También puede usar <code>label:</code>. Por ejemplo, <code>label:"FIX IT"</code> devolverá tarjetas con la etiqueta "FIX IT".</p> </li> 
     <li><code><strong>board:id</strong></code> <p>Devuelve tarjetas dentro de un tablero específico. Por ejemplo, <code>board:Trello</code> devolverá tarjetas en tableros con [!UICONTROL Trello] en el nombre del tablero.</p> </li> 
     <li><code><strong>list:name</strong></code> <p>Devuelve tarjetas dentro de la lista llamada “nombre”.</p> </li> 
     <li><code><strong>has:attachments</strong></code> <p>Devuelve tarjetas con archivos adjuntos. El operador <code>has</code> también se puede usar con otros atributos, como <code>has:description</code>, <code>has:cover</code>, <code>has:members</code> o <code>has:stickers</code>.</p> </li> 
     <li><code><strong>due:day</strong></code> <p>Devuelve tarjetas con un vencimiento de 24 horas. El operador <code>due:</code> también se puede usar con otros períodos de tiempo, como <code>due:week</code>, <code>due:month</code> o <code>due:overdue</code>. También puede buscar por un intervalo de días específico. Por ejemplo, si se añada <code>due:14</code> a la búsqueda, se incluirán las tarjetas que vencen en los próximos 14 días.</p> </li> 
     <li><code><strong>created:day</strong></code> <p>Devuelve las tarjetas creadas en las últimas 24 horas. El operador <code> created:</code> también se puede usar con otros marcos de tiempo como <code>created:week</code> o <code>created:month</code>. También puede buscar por un intervalo de días específico. Por ejemplo, al añadir <code>created:14</code> a la búsqueda se incluyen las tarjetas creadas en los últimos 14 días.</p> </li> 
     <li><code><strong>edited:day</strong></code> <p>Devuelve las tarjetas editadas en las últimas 24 horas. El operador <code>edited:</code> también se puede usar con otros periodos de tiempo, como <code>edited:week</code> o <code>edited:month</code>. También puede buscar por un intervalo de días específico. Por ejemplo, añadir <code>edited:21</code> a la búsqueda incluye tarjetas editadas en los últimos 21 días.</p> </li> 
     <li><code><strong>description:</strong>, <strong>checklist:</strong>, <strong>comment:</strong>, and <strong>name:</strong></code> <p>Devuelve tarjetas que coinciden con el texto de las descripciones, listas de comprobación, comentarios o nombres de las tarjetas. Por ejemplo, <code>comment:"FIX IT"</code> devolverá tarjetas con "CORREGIRLO" en un comentario.</p> </li> 
     <li><code><strong>is:open</strong> and <strong>is:archived</strong></code> <p>Devuelve las tarjetas abiertas o archivadas. Si no se especifica ninguno, [!UICONTROL Trello] devuelve ambos tipos.</p> </li> 
     <li><code><strong>is:starred</strong> </code> <p>Solo incluye tarjetas en tableros con estrellas.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned cards]</td> 
   <td> <p> Introduzca o asigne el número máximo de tarjetas que desea que Workfront Fusion devuelva durante un ciclo de ejecución. Este valor debe ser menor o igual a 1000.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Partial] </td> 
   <td> <p>De forma predeterminada, este módulo busca coincidencias exactas de cada palabra de la consulta en el contenido de los abonados. Cuando se ha habilitado [!UICONTROL Partial], el módulo busca contenido que comience con cualquier palabra de la consulta.</p> <p> Por ejemplo, si está utilizando la palabra “desarrollo” para buscar un tablero llamado “Mi informe de estado de desarrollo”, de forma predeterminada debería realizar una búsqueda de palabra completa. Si ha habilitado [!UICONTROL Partial], podrá buscar “des” pero no “desarrollo”.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Cards] </td> 
   <td> <p>Para buscar tarjetas específicas, haga clic en <b>Agregar elemento</b> y agregue el identificador de la tarjeta.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Watch cards]**

Este módulo de déclencheur inicia un escenario cuando se agrega una tarjeta nueva.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watched object]</td> 
   <td> <p>Seleccione la ubicación que desea ver para las tarjetas.</p> 
    <ul> 
     <li><strong>[!UICONTROL All cards]</strong> </li> 
     <li> <p><strong>Cards on specific board</strong> </p> <p>Seleccione el tablero que desea ver para las tarjetas</p> </li> 
     <li> <p><strong>[!UICONTROL Cards on specific list]</strong> </p> <p>Seleccione el tablero que contiene la lista que desea buscar tarjetas y, a continuación, seleccione la lista.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### Miembros

+++ **[!UICONTROL Añadir un abonado a una tarjeta]**

Este módulo de acción añade al abonado especificado a la tarjeta especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Enter card ID and member ID]</p> </td> 
   <td> <p>Elija cómo desea introducir el ID de tarjeta y el ID de abonado.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Introduzca o asigne el <strong>[!UICONTROL Card ID]</strong> y el <strong>[!UICONTROL Member ID]</strong>.</p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>Seleccione el tablero que contiene la tarjeta a la que desea añadir un abonado y, a continuación, seleccione la lista que contiene la tarjeta, la propia tarjeta y el abonado que desea añadir a la tarjeta.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Asignar un abonado a un tablero]**

Consulte “[!UICONTROL Asignar un abonado a un tablero]” en [Tableros](#boards).

+++

+++ **[!UICONTROL Buscar abonados]**

Este módulo de acción recupera información sobre los abonados de [!UICONTROL Trello].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query] </td> 
   <td> <p>Introduzca el nombre o el nombre de usuario del usuario que desea buscar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Partial] </td> 
   <td> <p>De forma predeterminada, este módulo busca coincidencias exactas de cada palabra de la consulta en el contenido de los abonados. Cuando se ha habilitado [!UICONTROL Partial], el módulo busca contenido que comience con cualquier palabra de la consulta.</p> <p> Por ejemplo, si está utilizando la palabra “desarrollo” para buscar un tablero llamado “Mi informe de estado de desarrollo”, de forma predeterminada debería realizar una búsqueda de palabra completa. Si ha habilitado [!UICONTROL Partial], podrá buscar “des” pero no “desarrollo”.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned members]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Anular la asignación de un abonado del tablero]**

Consulte “[!UICONTROL Anular la asignación de un abonado del tablero]” en [Tableros](#boards).

+++

### Listas de verificación

+++ **[!UICONTROL Create a Checklist]**

Este módulo de acción crea una lista de comprobación en la tarjeta seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a card ID]</td> 
   <td> <p> Seleccione cómo desea introducir el ID de la tarjeta en la que desea añadir una lista de comprobación.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>En el campo <strong>[!UICONTROL Card ID]</strong>, introduzca o asigne el ID de la tarjeta en la que desea añadir una lista de verificación.<br></p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>Seleccione el tablero que contiene la tarjeta en la que desea añadir una lista de verificación, luego la lista que contiene la tarjeta y, a continuación, la tarjeta.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>Introduzca o asigne un nombre para la lista de verificación.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Position] </td> 
   <td> <p>Seleccione si desea agregar la lista de comprobación a la parte superior o anexar la lista de comprobación a la parte inferior de la tarjeta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Enter checklist ID]</p> </td> 
   <td> <p>Si está creando la lista de comprobación copiando una lista de comprobación existente, introduzca o asigne el ID de una lista de comprobación de origen que desee copiar en la nueva.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Create a Checklist Item]**

Este módulo de acción añade un elemento a una lista de verificación específica.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter checklist ID]</td> 
   <td> <p> Si va a crear una nueva lista de comprobación copiando una lista existente, seleccione cómo desea introducir el ID de la lista de comprobación en la que desea agregar un elemento.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>En el campo <strong>[!UICONTROL Checklist ID]</strong>, introduzca o asigne el ID de la tarjeta en la que desea añadir una lista de verificación.<br></p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>Seleccione el tablero que contiene la tarjeta en la que desea añadir una lista de verificación, luego la lista que contiene la tarjeta, luego la tarjeta y, a continuación, la lista de verificación.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Item name]</p> </td> 
   <td> <p>Introduzca o asigne un nombre para el nuevo elemento.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Position]</p> </td> 
   <td> <p>Seleccione si el elemento lo desea añadir al principio o [!UICONTROL append] al final de la lista de verificación.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Checked]</p> </td> 
   <td> <p>Habilite esta opción si desea añadir el elemento como ya marcado.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Edit a Checklist Item]**

Este módulo de acción edita una lista de verificación existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a Card ID and Checklist Item ID]</td> 
   <td> <p> Seleccione cómo desea introducir el ID de la tarjeta y la lista de verificación en la que desea editar un elemento.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>En el campo <strong>[!UICONTROL Checklist ID]</strong>, introduzca o asigne el ID de la tarjeta en la que desea añadir una lista de verificación.</p> <p>En el campo <strong>[!UICONTROL Checklist Item ID]</strong>, introduzca o asigne el ID de la lista de verificación.</p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>Seleccione el tablero que contiene la tarjeta en la que desea añadir una lista de verificación, luego la lista que contiene la tarjeta, luego la tarjeta y, a continuación, la lista de verificación.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Checklist ID]</td> 
   <td>Seleccione o asigne la lista de verificación a la que desea mover el elemento de la lista de verificación.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Item name]</p> </td> 
   <td> <p>Introduzca o asigne un nombre para el nuevo elemento.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Position]</p> </td> 
   <td> <p>Seleccione si el elemento lo desea añadir al principio o anexar al final de la lista de verificación.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL State]</p> </td> 
   <td> <p>Seleccione si el elemento de la lista de verificación está completado o incompleto.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### Etiquetas

+++ **[!UICONTROL Add a Label to a Card]**

Este módulo de acción añade una etiqueta a la tarjeta seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter card ID]</td> 
   <td> <p> Seleccione cómo desea introducir el ID de la tarjeta en la que desea añadir una lista de comprobación.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>En el campo <strong>[!UICONTROL Card ID]</strong>, escriba o asigne el ID de la tarjeta donde quiera añadir una lista de comprobación. En el campo <strong>[!UICONTROL Label ID]</strong>, introduzca o asigne el ID de la etiqueta que quiera añadir.<br></p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>Seleccione el tablero que contiene la tarjeta en la que desea añadir una lista de verificación, luego la lista que contiene la tarjeta y, a continuación, la tarjeta. </p> <p>Seleccione la etiqueta que quiera mover a la carpeta raíz.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

### Comentarios

+++ **[!UICONTROL Crear un comentario en una tarjeta]**

Este módulo de acción añade un comentario a una tarjeta seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a card ID]</td> 
   <td> <p> Seleccione cómo introducir el ID de la tarjeta en la que desea añadir un comentario.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>En el campo <strong>[!UICONTROL Card ID]</strong>, introduzca o asigne el ID de la tarjeta donde quiera añadir un comentario.<br></p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>Seleccione el tablero que contenga la tarjeta en la que quiera añadir un comentario, seleccione la lista que contenga la tarjeta y, a continuación, seleccione la tarjeta.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment] </td> 
   <td> <p>Escriba o asigne el comentario que desea agregar a la tarjeta seleccionada.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Enumerar comentarios en una tarjeta]**

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a card ID]</td> 
   <td> <p> Seleccione cómo introducir el ID de la tarjeta en la que desea añadir un comentario.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>En el campo <strong>[!UICONTROL Card ID]</strong>, introduzca o asigne el ID de la tarjeta donde quiera añadir un comentario.<br></p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>Seleccione el tablero que contenga la tarjeta en la que quiera añadir un comentario, seleccione la lista que contenga la tarjeta y, a continuación, seleccione la tarjeta.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned comments]</td> 
   <td> <p> Introduzca el número máximo de comentarios que Workfront Fusion devolverá durante un ciclo de ejecución.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Since] </td> 
   <td> <p>Establezca la fecha de inicio del periodo en el que se creó el comentario. Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Before] </td> 
   <td> <p>Establezca la fecha de finalización del periodo en el que se creó el comentario. Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Ver comentarios]**

Este módulo de déclencheur inicia un escenario cuando se agrega un comentario.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!UICONTROL Trello] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watched object]</td> 
   <td> <p>Seleccione la ubicación en la que quiera ver comentarios.</p> 
    <ul> 
     <li><strong>[!UICONTROL All cards] en todas partes</strong> </li> 
     <li> <p><strong>[!UICONTROL Board]</strong> </p> <p>Seleccione el tablero que quiera para ver comentarios</p> </li> 
     <li> <p><strong>[!UICONTROL List]</strong> </p> <p>Seleccione el tablero que contenga la lista que quiera para ver comentarios y, a continuación, seleccione la lista.</p> </li> 
     <li><strong>[!UICONTROL Card]</strong> </li> 
     <li>Seleccione el tablero que contenga la tarjeta en la que quiera ver comentarios, seleccione la lista que contenga la tarjeta y, por último, seleccione la tarjeta.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Introduzca o asigne el número máximo de comentarios que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

## ID de objeto [!UICONTROL Trello]

* [Encontrar el ID o el vínculo abreviado de una tarjeta en  [!DNL Trello]](#how-to-find-the-id-or-the-shortlink-of-a-card-in-trello)
* [Buscar los ID de otros objetos en  [!DNL Trello]](#how-to-find-ids-of-other-objects-in-trello)

### Encontrar el ID o el vínculo abreviado de una tarjeta en [!DNL Trello]

Si desea editar una tarjeta o crear un nuevo comentario, debe conocer el ID de la tarjeta o su vínculo abreviado. Puede obtener esta información en la salida del activador [!UICONTROL New Card]. El vínculo abreviado de una tarjeta también se puede obtener abriéndola y haciendo clic en el botón [!UICONTROL Share]. El vínculo abreviado se encuentra en el cuadro [!UICONTROL Link to this card], al final de la dirección URL después de `https://trello.com/c/`.

![Compartir y más](/help/workfront-fusion/references/apps-and-modules/assets/share-and-more-350x575.png)

### Buscar los ID de otros objetos en [!DNL Trello]

Los ID de tablero, lista y comentario solo se pueden obtener mediante activadores. El sitio web [!DNL `trello.com`] no muestra estos ID.
