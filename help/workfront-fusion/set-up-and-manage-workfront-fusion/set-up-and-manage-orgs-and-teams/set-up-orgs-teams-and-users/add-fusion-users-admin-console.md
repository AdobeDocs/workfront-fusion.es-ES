---
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: Añadir usuarios a Adobe Workfront Fusion mediante Adobe Admin Console
description: Puede añadir un usuario a Adobe Admin Console y asignarlo a Adobe Workfront Fusion o asignar un usuario existente de Adobe Admin Console a Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 7cb1c1a7-3c7a-459a-818f-d9cefcb9988b
source-git-commit: 6762806f17a0fc55531b647a84901b8ca572a997
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 56%

---

# Añadir usuarios a Adobe Workfront Fusion mediante Adobe Admin Console

You can add a user to the [!DNL Adobe Admin Console] and assign them to Adobe Workfront Fusion, or assign an existing user in the [!DNL Adobe Admin Console] to Workfront Fusion.

For a video describing Workfront Fusion in the [!DNL Adobe Admin Console], including how to add users, see [[!DNL Fusion] on Adobe IMS](https://video.tv.adobe.com/v/3412464/){target=_blank}.

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
     <p>You must be a Workfront Fusion administrator for your team.</p>
   </td> 
  </tr> 
  </tr>
   <tr> 
   <td role="rowheader">Configuraciones de nivel de acceso</td> 
   <td>You must be a Product Configuration Administrator of Adobe products for your organization.</td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte los [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++



## Requisitos previos

Before using the [!DNL Admin Console] for Workfront, you should receive a receive an email inviting you to the console.

* Si es nuevo en [!DNL Adobe] y ha recibido un mensaje de correo electrónico que le informa de que ahora tiene derechos de administración para administrar el software y los servicios de [!DNL Adobe] para su organización, haga clic en el botón del mensaje de correo electrónico para crear una cuenta de [!DNL Adobe] y abrir [!DNL Admin Console].

  O

  Si ya tiene una cuenta de Adobe, vaya a la página de [[!DNL Adobe Admin Console] &#x200B;](https://adminconsole.adobe.com).


## Add a new user to the [!DNL Adobe Admin Console] and Workfront Fusion

1. From the [[!DNL Adobe Admin Console] page](https://adminconsole.adobe.com/), select the **[!UICONTROL Products]** tab in the top navigation bar, and then select the **Workfront Fusion** product tile.

   ![Fusion en Admin Console](assets/fusion-product-admin-console.png)

1. En la lista que se muestra, seleccione la organización en la que desea añadir un usuario.

   ![Instancia de Fusion en Admin Console](assets/fusion-instances-admin-console.png)

1. In the list that displays, with the **[!UICONTROL Product Profiles]** tab selected, click the name of the Workfront Fusion [!UICONTROL Product Profile] link.

   >[!IMPORTANT]
   >
   > No realice ningún cambio en el propio [!UICONTROL Perfil del producto].

1. Con la pestaña **[!UICONTROL Usuarios]** seleccionada encima de la lista, haga clic en **[!UICONTROL Añadir usuario]**.

1. En el cuadro **[!UICONTROL Añadir usuarios a este perfil de producto]**, introduzca la dirección de correo electrónico o el nombre del usuario que desea añadir y, a continuación, seleccione el usuario en la lista que aparece.

1. Haga clic en **[!UICONTROL Guardar]**.

   The user is created in Workfront Fusion.

1. (Optional) Continue to [Change a user&#39;s access level in Workfront Fusion](#change-a-users-access-level-in-workfront-fusion).

## Cambio del nivel de acceso de un usuario en Workfront Fusion

* [Cambie la función de un usuario a Admin](#change-a-users-role-to-admin)
* [Change a user&#39;s role to Member, Accountant, or App Developer](#change-a-users-role-to-member-accountant-or-app-developer)

### Cambie la función de un usuario a Admin

Otorgar al usuario una función de administrador debe hacerse en [!DNL Adobe Admin Console].

1. On the Workfront Fusion [!UICONTROL Product Profile] page where you added the user, select the **[!UICONTROL Admins]** tab.

1. Haga clic en **[!UICONTROL Add Admin]**.

1. In the **[!UICONTROL Add product profile administrators]** box, enter the email address or name of the user you want to become an admin, then select the user in the list that appears.

1. Haga clic en **[!UICONTROL Guardar]**.

   The user is now an Administrator in Workfront Fusion.

### Change a user&#39;s role to Member, Accountant, or App Developer

Member, Accountant, and App Developer roles are handled inside Workfront Fusion.

For instructions, see [View or edit user roles](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/manage-users-and-teams/view-or-edit-user-roles.md).

## Assign an existing user in the [!DNL Adobe Admin Console] to Workfront Fusion

Puede añadir un usuario existente a un equipo en Fusion. Esto se gestiona dentro de Fusion.

For instructions, see [Add a user to a team](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/add-a-user-to-a-team.md).
