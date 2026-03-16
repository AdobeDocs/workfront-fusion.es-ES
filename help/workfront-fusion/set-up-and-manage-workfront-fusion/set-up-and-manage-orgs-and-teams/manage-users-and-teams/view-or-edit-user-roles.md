---
title: Gestionar los usuarios de Adobe Workfront Fusion de su organización
description: Gestionar los usuarios de Adobe Workfront Fusion de su organización
author: Becky
feature: Workfront Fusion
exl-id: 32c221fa-856b-4921-9fa6-5e60f2aa08cd
source-git-commit: 3f9390d8947ef2666336c1a4cc6eab8d174849d5
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 25%

---

# Visualización o edición de las funciones de usuario

Los administradores de Adobe Workfront Fusion pueden administrar las funciones de usuario dentro de Workfront Fusion.


>[!NOTE]
>
>Si su organización se encuentra actualmente en el proceso de pasar a Adobe Admin Console, no puede administrar usuarios en Workfront (añadiendo o eliminando usuarios). Puede realizar estas acciones en Adobe Admin Console una vez completada la migración.

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
   <p>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">Configuraciones de nivel de acceso</td> 
   <td> 
     <p>Debe ser administrador de Workfront Fusion para su organización.</p>
     <p>Debe ser administrador de Workfront Fusion para su equipo.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte los [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Ver o editar los roles de usuario de una organización

Los administradores de Adobe Workfront Fusion pueden ver y actualizar las funciones de usuario de una organización.

1. Cuando haya iniciado sesión como administrador de Workfront Fusion, seleccione **[!UICONTROL Todos los usuarios]** en el panel de navegación izquierdo.
1. Haga clic en **[!UICONTROL Detalles]** en la fila del usuario que desee ver.
1. (Opcional) Para actualizar la función del usuario en una organización, haga clic en el menú desplegable de la columna **[!DNL Role]** en la fila de la organización donde desea cambiar la función del usuario y, a continuación, seleccione la nueva función.

### Consideraciones al añadir o cambiar propietarios de la organización

Su organización puede tener más de un propietario.

Al asignar un usuario a o desde una función Propietario, tenga en cuenta lo siguiente.

* Solamente un propietario puede asignar el rol Propietario o asignar otro rol a un propietario actual.
* Solo los administradores pueden actualizarse a propietario.
* Si solo hay un propietario, la función Propietario no se puede cambiar ni eliminar.
* Si solo hay un Propietario, este no se puede eliminar si hay otros usuarios en la organización.
* Cuando se asigna a un administrador una función de propietario, se convierte automáticamente en administrador en todos los equipos de la organización.
* Cuando se asigna un Propietario a otra función, ese usuario se convierte automáticamente en un Miembro del equipo en todos los equipos.
* Cuando se crea un nuevo equipo, todos los propietarios se asignan automáticamente como administradores de equipo.

## Ver o editar los roles de usuario de un equipo

Los administradores de Adobe Workfront Fusion y los administradores de equipos pueden ver y actualizar las funciones de usuario.

1. Cuando haya iniciado sesión como administrador de Workfront Fusion, seleccione **[!UICONTROL Todos los usuarios]** en el panel de navegación izquierdo.
1. Haga clic en **[!UICONTROL Detalles]** en la fila del usuario que desee ver.
1. Haga clic en el icono Equipos en la columna **[!DNL Role]** de la fila de la organización que contiene el equipo donde desea ver o editar el rol del usuario.
1. (Opcional) Para actualizar la función del usuario en un equipo, haga clic en el menú desplegable de la columna **[!DNL Role]** en la fila del equipo donde desea cambiar la función del usuario y, a continuación, seleccione la nueva función.
