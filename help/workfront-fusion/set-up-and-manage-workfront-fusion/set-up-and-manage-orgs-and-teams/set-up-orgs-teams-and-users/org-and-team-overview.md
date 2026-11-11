---
title: Resumen de organizaciones y equipos de Fusion
description: Las funciones de organización y equipos de Adobe Workfront Fusion permiten a las empresas controlar el acceso a escenarios y otras funciones dentro de Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 44e6de2a-b2d3-410d-abc3-10facd258495
TQID: 'https://experienceleague.adobe.com/rWg9TitUlX092UIFTY1LUZsR7UlmWwE5dItl6wnlBMA'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: f9cdbcf936fc6b022f6513f47b9b377424731419
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 2%
---
# Información general sobre organizaciones y equipos de Adobe Workfront Fusion

Las funciones de organización y equipos de Adobe Workfront Fusion permiten a las empresas controlar el acceso a escenarios y otras funciones dentro de Fusion.

Una organización es la entidad más grande de Adobe Workfront Fusion. Por ejemplo, su organización de Fusion puede representar la cuenta de Fusion para toda la compañía.

Los equipos son grupos más pequeños dentro de la organización y comparten recursos de Fusion como escenarios, conexiones y plantillas.

Para obtener instrucciones sobre cómo crear un equipo, consulte [Crear un equipo](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/create-a-team.md).

## Organizaciones

Los usuarios de Workfront Fusion pertenecen a una organización.

Los usuarios deben añadirse a una organización antes de que se añadan a un equipo.

### Recursos de organización

Los siguientes recursos afectan a toda la organización de Fusion y, por lo tanto, son propiedad y se gestionan a nivel de organización:

* **Grupos de trabajo:**: un grupo de trabajo es una cantidad de recursos de procesamiento de Workfront Fusion dedicados a una organización específica.

  Para obtener más información, vea [Grupos de trabajo](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/worker-pools.md).

* **Operaciones**: Una operación en Adobe Workfront Fusion es una tarea realizada por un módulo.

  Para obtener más información, consulte [Operaciones](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/operations-in-workfront-fusion.md).

### Funciones de organización

Un usuario tiene una de las siguientes funciones en una organización:

* **[!UICONTROL Propietario]**: el propietario tiene todos los permisos disponibles en la organización.
* **[!UICONTROL Administrador]**: los administradores pueden administrar usuarios en Adobe Admin Console si la organización está habilitada para Adobe Identity Management System (IMS) o pueden invitar a nuevos usuarios a organizaciones que no están en IMS. También pueden aprobar plantillas.
* **[!UICONTROL Miembro]**: Los miembros pueden usar Workfront Fusion pero no pueden realizar cambios organizativos.
* **[!UICONTROL Contador]**: los contables pueden ver información de licencia en el panel de organización, pero no pueden realizar ninguna acción.
* **[!UICONTROL Desarrollador de aplicaciones]**: la funcionalidad de esta función no está disponible actualmente y estará disponible en un futuro próximo. No se recomienda asignar usuarios a esta función en este momento.

Para obtener información sobre las acciones específicas disponibles para los usuarios en cada función de organización, consulte [Funciones de organización y equipo](/help/workfront-fusion/references/licenses-and-roles/organization-roles.md).

## Equipos

Los equipos son grupos de usuarios que comparten el acceso a recursos específicos. Estos recursos pueden incluir:

* Escenarios
* Conexiones
* Webhooks
* Claves
* Almacenes de datos
* Estructuras de datos
* Configuración de notificaciones por correo electrónico

>[!NOTE]
>
>Como los equipos comparten recursos, a veces resulta útil que un equipo tenga solo un miembro. Por ejemplo, los usuarios en formación pueden crear conexiones con sus cuentas de Workfront individuales. Los integrantes del equipo también podrían conectarse a la cuenta de Workfront individual. En este caso, recomendamos que el usuario sea el único miembro de un equipo de formación.

Las organizaciones pueden tener tantos equipos como necesiten y los usuarios pueden pertenecer a uno o más equipos.

Los usuarios pueden seleccionar su equipo en la lista desplegable del panel de navegación izquierdo. Los usuarios solo ven los equipos de los que son miembros. Si se selecciona un equipo, el usuario podrá acceder a los recursos de dicho equipo.

### Funciones de equipo

Un usuario tiene una de las siguientes funciones en cada uno de sus equipos:

* **[!UICONTROL Administrador de equipo]**: los administradores pueden agregar, quitar o cambiar el rol de un miembro del equipo. También pueden realizar cualquier acción disponible para los demás roles de equipo.
* **[!UICONTROL Miembro del equipo]**: La función de miembro del equipo permite a los usuarios crear y ejecutar escenarios.
* **[!UICONTROL Supervisión del equipo]**: La función [!UICONTROL Supervisión] permite a los usuarios acceder a la información de ejecución de los escenarios, pero no pueden diseñarlos ni cambiar su estado &quot;Activo&quot;.
* **[!UICONTROL Operador de equipo]**: El rol [!UICONTROL operator] permite a los usuarios ver los datos de ejecución y cambiar el estado &quot;Activo&quot; de los escenarios.
* **[!UICONTROL Miembro restringido del equipo]**: la funcionalidad de este rol no está disponible actualmente y estará disponible en un futuro próximo. No se recomienda asignar usuarios a esta función en este momento.

Para obtener información sobre las acciones específicas disponibles para los usuarios en cada rol de equipo, consulte [Funciones de organización y equipo](/help/workfront-fusion/references/licenses-and-roles/organization-roles.md).

### Funciones de equipo personalizadas

<!-- BECKY CHECK ME: The source material (the Slack announcement) says flexible permissions are live in QA and for internal customers, with a limited pilot with paid customers next, then general availability. Confirm availability at the 2026-11-12 release before publishing, and whether this section should say that the feature is available only to some organizations. -->

Además de los roles de equipo predefinidos, cada equipo tiene una ficha **[!UICONTROL Roles]** en la que puede crear sus propios roles. Puede crear, actualizar y eliminar funciones, y elegir exactamente los permisos que incluye cada función. Ya no está limitado a un conjunto fijo de funciones.

Para obtener instrucciones, consulte [Ver y administrar los roles del equipo](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/manage-users-and-teams/view-and-manage-team-roles.md).

Con las funciones personalizadas, puede:

* Proporcione a cada persona solo el acceso que necesita su trabajo, lo que reduce el riesgo de cambios accidentales en situaciones críticas.
* Configure el acceso para que coincida con el funcionamiento de su organización, en lugar de ajustar sus equipos a las funciones predefinidas.
* Administre el acceso usted mismo, sin ponerse en contacto con el soporte técnico.

Cualquier persona con el permiso **[!UICONTROL Administrar miembros]** en un equipo puede crear, actualizar, eliminar y asignar usuarios a roles de ese equipo. En las funciones predefinidas, este permiso se incluye en las funciones Administrador de equipos y Propietario de la organización.

* Los propietarios de organización pueden crear y administrar roles en todos los equipos.
* Los administradores de organización solo pueden administrar roles en los equipos de los que son miembros y en los que tienen el permiso **[!UICONTROL Administrar miembros]**.
* Los administradores de equipos pueden administrar los roles de sus equipos.

<!-- BECKY CHECK ME: The source does not describe the steps in the Roles tab, the list of permissions that you can choose from, or whether you can edit or delete the predefined roles. Add the steps and permissions list once confirmed. Also confirm that Team Admins can manage roles (the source says the Manage members permission was previously given to Team Admin and Org Owner roles, and that team and org admins can create roles only in the teams where they are admins). -->
