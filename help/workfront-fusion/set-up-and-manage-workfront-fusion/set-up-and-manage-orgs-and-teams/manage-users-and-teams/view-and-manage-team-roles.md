---
title: Ver y administrar roles de equipo
description: Cada equipo tiene una ficha Funciones en la que puede ver las funciones del equipo, crear sus propias funciones, elegir los permisos que cada función incluye y actualizar o eliminar funciones.
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: a3a6922afd713cd002cdf472c7ef62c1855b80d9
workflow-type: tm+mt
source-wordcount: '1032'
ht-degree: 10%
---
# Ver y administrar roles de equipo

Puede ver las funciones disponibles en un equipo, crear sus propias funciones y elegir los permisos que incluye cada función. También puede actualizar y eliminar funciones.

Las funciones personalizadas ofrecen las siguientes ventajas:

* Cada miembro del equipo solo tiene el acceso que necesita su trabajo, lo que reduce el riesgo de cambios accidentales en situaciones críticas.
* Las funciones personalizadas pueden coincidir mejor con el funcionamiento de su organización, en lugar de ajustar sus equipos a las funciones predefinidas.
* Puede administrar el acceso usted mismo, sin ponerse en contacto con el servicio de asistencia.

Para obtener una descripción general de las organizaciones, los equipos y los roles de equipo predefinidos, consulte [Descripción general de la organización y el equipo](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/org-and-team-overview.md). Para obtener los permisos incluidos en las funciones predefinidas, vea [Funciones de organización y equipo](/help/workfront-fusion/references/licenses-and-roles/organization-roles.md).

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Paquete de Adobe Workfront</td> 
   <td> <p>Cualquier paquete del flujo de trabajo de Adobe Workfront y cualquier paquete de integración y automatización de Adobe Workfront</p><p>Workfront Ultimate</p><p>Paquetes Workfront Prime y Select, con una compra adicional de Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencias de Adobe Workfront</td> 
   <td> <p>Estándar</p><p>Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">Configuraciones de nivel de acceso</td> 
   <td> 
     <p>Debe tener el permiso <b>[!UICONTROL Manage members]</b> en el equipo. En las funciones predefinidas, este permiso se incluye en las funciones Administrador de equipos y Propietario de la organización.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Quién puede administrar los roles de equipo

Cualquier persona con el permiso **[!UICONTROL Administrar miembros]** en un equipo puede crear, actualizar, eliminar y asignar usuarios a roles de ese equipo.

* Los propietarios de organización pueden crear y administrar roles en todos los equipos.
* Los administradores de organización solo pueden administrar roles en los equipos de los que son miembros y en los que tienen el permiso **[!UICONTROL Administrar miembros]**.
* Los administradores de equipos pueden administrar los roles de sus equipos.

## Crear o editar un rol

1. En Fusion, en el panel de navegación izquierdo, haga clic en **Resumen del equipo**.
1. (Condicional) Si no se encuentra en la página del equipo para el que desea ver los roles, haga clic en el menú desplegable **Equipo** situado cerca de la parte superior de la página y seleccione el equipo correcto.
1. Abra la ficha **[!UICONTROL Roles]**.

   La pestaña enumera las funciones disponibles en el equipo, incluidas las funciones predefinidas. Para cada función, la lista muestra el nombre de la función y un resumen de sus permisos, como &quot;Sin permisos&quot;, &quot;Miembro&quot; o &quot;Personalizado · 19 permisos&quot;.

1. Para crear una función, haga clic en **[!UICONTROL Crear función]**.

   O

   Para editar un rol, haga clic en **[!UICONTROL Editar]** en la fila del rol que desea editar.

   <!-- BECKY CHECK ME: The Edit button is available for the predefined roles as well as custom roles. Confirm the title of the edit page, whether you can rename the predefined roles, and what happens to users who already have the role. -->

1. Escriba un nombre para la función en el campo **[!UICONTROL Nombre de función]**.
1. En el menú desplegable **[!UICONTROL Plantilla de rol]**, seleccione la plantilla desde la que desee comenzar.

   La plantilla establece los permisos iniciales para la función. La plantilla predeterminada es **[!UICONTROL Visor]**.

1. En el área **[!UICONTROL Permisos de ámbito]**, seleccione los permisos que desea que incluya la función.

   Los permisos se agrupan por áreas, como **[!UICONTROL Automaciones]**, **[!UICONTROL Conexiones]** y **[!UICONTROL Equipo]**. Para cada área, puede realizar cualquiera de las siguientes acciones:

   * Para establecer todos los permisos en un área a la vez, haga clic en **[!UICONTROL Sin acceso]**, **[!UICONTROL Solo vista]** o **[!UICONTROL Acceso completo]** junto al nombre del área.
   * Para elegir permisos específicos, active o desactive la casilla de verificación de cada permiso.

   Para obtener una lista de los permisos, consulte [Permisos que puede incluir en una función](#permissions-that-you-can-include-in-a-role) en este artículo.

   <!-- BECKY CHECK ME: Confirm the options in the Role template dropdown and what each one selects. Confirm exactly what No access, View only, and Full access select in each area (in the screenshot, View only selects the view permissions). Confirm whether there is a Description field, and whether there are areas below Team on the page (the screenshots end at Team). -->

1. Haga clic en **[!UICONTROL Guardar]**. Para cerrar la página sin guardar, haga clic en **[!UICONTROL Cancelar]**.
1. (Opcional) Para eliminar un rol, haga clic en **[!UICONTROL Eliminar]** en la fila del rol en la ficha **[!UICONTROL Roles]**.

   <!-- BECKY CHECK ME: Confirm why the Delete button is unavailable (dimmed) for some roles, such as Team Operator, Team Member, and Team Admin in the screenshot, whether there is a confirmation prompt, and what happens to users who have the role. Update this step and add a note, if needed. -->

Una función que cree estará disponible en el equipo. Puede asignarlo a los integrantes del equipo.

### Permisos que puede incluir en un rol

<table style="table-layout:auto">
 <col>
 <col>
 <thead>
  <tr>
   <th>Área</th>
   <th>Permisos</th>
  </tr>
 </thead>
 <tbody>
 <tr>
   <td role="rowheader">[!UICONTROL Automations]</td>
   <td>Ver lista, Ver detalles, Ver historial de ejecución, Administrar notificaciones, Restablecer estadísticas, Ejecutar una vez, Editar programación, Activar, Desactivar, Crear, Editar, Publicar, Eliminar</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL Ejecuciones incompletas]</td>
   <td>Ver, Administrar</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL Webhooks]</td>
   <td>Ver, Ver cola, Crear, Editar, Administrar cola, Cambiar prioridad, Eliminar</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL Connections]</td>
   <td>Ver, crear, editar, eliminar</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL Teclas]</td>
   <td>Ver, crear, editar, eliminar</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL Almacenes de datos]</td>
   <td>Ver lista, Examinar registros, Crear, Editar, Eliminar</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL Estructuras de datos]</td>
   <td>Ver, crear, editar, eliminar</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL Templates]</td>
   <td>Ver lista, Ver detalles, Crear, Editar, Eliminar</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL Team]</td>
   <td>Ver equipo, Editar configuración de equipo, Administrar miembros, Eliminar equipo</td>
  </tr>
 </tbody>
</table>

<!-- BECKY CHECK ME: Confirm that this list is complete, and add a description of what each permission allows, if needed. The list is taken from the Create role page, which may have more areas below Team. -->

## Clonar roles a otro equipo

Puede copiar los roles de un equipo a otro, de modo que no tenga que volver a crear los mismos roles en cada equipo.

1. Abra la ficha **[!UICONTROL Roles]** del equipo, tal como se describe en [Crear o editar un rol](#create-or-edit-a-role) en este artículo.
1. Haga clic en **[!UICONTROL Clonar al equipo]**.

   Se abre la página **[!UICONTROL Clonar roles a otro equipo]**.

1. En el menú desplegable **[!UICONTROL Equipo de destino]**, seleccione el equipo en el que desee clonar los roles.

   Aparece una tabla que enumera las funciones del equipo actual.

1. Para cada función de la tabla, revise y configure lo siguiente:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Función de Source]</td> 
      <td> <p>La función en el equipo actual, con un resumen de sus permisos.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Action]</td> 
      <td> <p>Qué hacer con el rol. Por ejemplo, <b>[!UICONTROL Copiar en la función existente]</b> copia los permisos de la función de origen en una función que ya existe en el equipo de destino.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Target]</td> 
      <td> <p>La función en el equipo de destino en la que se copia la función de origen.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Cambios]</td> 
      <td> <p>Si la función de destino difiere de la función de origen. Por ejemplo, <b>[!UICONTROL Ya está sincronizado]</b> significa que la función de destino ya tiene los mismos permisos que la función de origen.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Users]</td> 
      <td> <p>Información sobre los usuarios que tienen la función. Por ejemplo, <b>[!UICONTROL No hay usuarios que coincidan]</b> significa que no hay usuarios que incluir.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Status]</td> 
      <td> <p>El resultado de la función después de clonar.</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. Haga clic en **[!UICONTROL Clonar]**. Para cerrar la página sin clonarla, haga clic en **[!UICONTROL Cancelar]**.

<!-- BECKY CHECK ME: The screenshot shows the Clone roles to another team page after a target team is selected. Confirm the options in the Action dropdown (for example, whether you can create a new role in the target team), the options in the Target dropdown, what the checkbox in the Users column does (for example, whether it also assigns the role to matching users in the target team) and what "matching users" means, what the Changes column shows when the roles differ, and what the Status column shows before and after you clone. -->

<!-- BECKY CHECK ME: Confirm whether the Target team dropdown lists all teams or only the teams that you can manage, and whether the Clone to team button is visible to everyone who can manage roles. -->

## Asignar una función a un usuario

Puede asignar una función personalizada de la misma manera que asigna una función predefinida. Para obtener instrucciones, consulte [Agregar un usuario a un equipo](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/add-a-user-to-a-team.md) y [Ver o editar los roles de usuario](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/manage-users-and-teams/view-or-edit-user-roles.md#view-or-edit-user-roles-for-a-team).

<!-- BECKY CHECK ME: Confirm that custom roles appear in the role dropdowns in both of these procedures. -->

## Consideraciones

* Permisos de organización en cascada. Para que alguien tenga acceso para realizar una acción en todos los equipos, asigne una función de organización en lugar de crear una función de equipo. Para obtener más información, consulte [Funciones de organización y equipo](/help/workfront-fusion/references/licenses-and-roles/organization-roles.md).
* Las funciones que cree pertenecen a un equipo.

<!-- BECKY CHECK ME: The Slack thread says that defining a role that is available in all teams was out of scope for the initial release. Confirm that a role belongs to a single team, and that you clone it to use it in another team. -->
