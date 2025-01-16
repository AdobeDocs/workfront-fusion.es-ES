---
title: Resumen de organizaciones y equipos de Fusion
description: Las funciones de organización y equipos de Adobe Workfront Fusion permiten a las empresas controlar el acceso a escenarios y otras funciones dentro de Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 44e6de2a-b2d3-410d-abc3-10facd258495
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 2%

---

# Información general de [!DNL Adobe Workfront Fusion] organizaciones y equipos

Las características de organización y equipos de [!DNL Adobe Workfront Fusion] permiten a las empresas controlar el acceso a escenarios y otras características dentro de Fusion.

Una organización es la entidad más grande de Adobe Workfront Fusion. Por ejemplo, su organización de Fusion puede representar la cuenta de Fusion para toda la compañía.

Los equipos son grupos más pequeños dentro de la organización y comparten recursos de Fusion como escenarios, conexiones y plantillas.

## Organizaciones

[!DNL Workfront Fusion] usuarios pertenecen a una organización.

Los usuarios deben añadirse a una organización antes de que se añadan a un equipo.

### Funciones de organización

Un usuario tiene una de las siguientes funciones en una organización:

* **[!UICONTROL Owner]**: el propietario tiene todos los permisos disponibles en la organización.
* **[!UICONTROL Admin]**: los administradores pueden crear y administrar equipos y usuarios para la organización, así como aprobar plantillas.
* **[!UICONTROL Member]**: los miembros pueden usar [!DNL Workfront Fusion], pero no pueden realizar cambios organizativos.
* **[!UICONTROL Accountant]**: los contadores pueden ver la información de licencia en el panel de organización, pero no pueden realizar ninguna acción.
* **[!UICONTROL App Developer]**: la funcionalidad de este rol no está disponible actualmente y estará disponible en un futuro próximo. No se recomienda asignar usuarios a esta función en este momento.

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
>Como los equipos comparten recursos, a veces resulta útil que un equipo tenga solo un miembro. Por ejemplo, los usuarios en formación pueden crear conexiones con sus cuentas individuales de [!DNL Workfront]. Los integrantes del equipo también podrían conectarse a la cuenta individual de [!DNL Workfront]. En este caso, recomendamos que el usuario sea el único miembro de un equipo de formación.

Las organizaciones pueden tener tantos equipos como necesiten y los usuarios pueden pertenecer a uno o más equipos.

Los usuarios pueden seleccionar su equipo en la lista desplegable del panel de navegación izquierdo. Los usuarios solo ven los equipos de los que son miembros. Si se selecciona un equipo, el usuario podrá acceder a los recursos de dicho equipo.

### Funciones de equipo

Un usuario tiene una de las siguientes funciones en cada uno de sus equipos:

* **[!UICONTROL Team Admin]**: los administradores pueden agregar, quitar o cambiar la función de un miembro del equipo. También pueden realizar cualquier acción disponible para los demás roles de equipo.
* **[!UICONTROL Team Member]**: la función de miembro del equipo permite a los usuarios crear y ejecutar escenarios.
* **[!UICONTROL Team Monitoring]**: el rol [!UICONTROL monitoring] permite a los usuarios acceder a la información de ejecución de escenarios, pero no pueden diseñar escenarios ni cambiar su estado &quot;Activo&quot;.
* **[!UICONTROL Team Operator]**: el rol [!UICONTROL operator] permite a los usuarios ver datos de ejecución y cambiar el estado &quot;Activo&quot; de los escenarios.
* **[!UICONTROL Team Restricted Member]**: la funcionalidad de este rol no está disponible actualmente y estará disponible en un futuro próximo. No se recomienda asignar usuarios a esta función en este momento.

Para obtener información sobre las acciones específicas disponibles para los usuarios en cada rol de equipo, consulte [Funciones de organización y equipo](/help/workfront-fusion/references/licenses-and-roles/organization-roles.md).
