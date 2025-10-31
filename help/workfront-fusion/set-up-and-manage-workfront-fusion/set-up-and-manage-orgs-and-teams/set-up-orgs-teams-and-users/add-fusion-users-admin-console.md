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
source-git-commit: f7c1d5b1de74cc0c59e3a00938bed14b489500db
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 45%

---

# Añadir usuarios a Adobe Workfront Fusion mediante Adobe Admin Console

Puede agregar un usuario a [!DNL Adobe Admin Console] y asignarlo a Adobe Workfront Fusion, o asignar un usuario existente en [!DNL Adobe Admin Console] a Workfront Fusion.

Para ver un vídeo que describe Workfront Fusion en [!DNL Adobe Admin Console], incluyendo cómo agregar usuarios, consulte [[!DNL Fusion] en Adobe IMS](https://video.tv.adobe.com/v/3412464/){target=_blank}.

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
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete Select o Prime Workfront que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">Configuraciones de nivel de acceso</td> 
   <td> 
     <p>Debe ser administrador de Workfront Fusion para su organización.</p>
     <p>Debe ser administrador de Workfront Fusion para su equipo.</p>
   </td> 
  </tr> 
  </tr>
   <tr> 
   <td role="rowheader">Configuraciones de nivel de acceso</td> 
   <td>Debe ser administrador de configuración de productos de Adobe para su organización.</td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++



## Requisitos previos

Antes de usar [!DNL Admin Console] para Workfront, debería recibir un mensaje de correo electrónico que le invite a la consola.

1. Si es nuevo en [!DNL Adobe] y ha recibido un mensaje de correo electrónico que le informa de que ahora tiene derechos de administración para administrar el software y los servicios de [!DNL Adobe] para su organización, haga clic en el botón del mensaje de correo electrónico para crear una cuenta de [!DNL Adobe] y abrir [!DNL Admin Console].

   O

   Si ya tiene una cuenta de Adobe, vaya a la página de [[!DNL Adobe Admin Console] &#x200B;](https://adminconsole.adobe.com).


## Agregar un nuevo usuario a [!DNL Adobe Admin Console] y a Workfront Fusion

1. En la [[!DNL Adobe Admin Console] página](https://adminconsole.adobe.com/), seleccione la ficha **[!UICONTROL Productos]** en la barra de navegación superior y, a continuación, seleccione el mosaico del producto **Workfront Fusion**.

   ![Fusion en Admin Console](assets/fusion-product-admin-console.png)

1. En la lista que se muestra, seleccione la organización en la que desea añadir un usuario.

   ![Instancia de Fusion en Admin Console](assets/fusion-instances-admin-console.png)

1. En la lista que aparece, con la ficha **[!UICONTROL Perfiles de producto]** seleccionada, haga clic en el nombre del vínculo [!UICONTROL Perfil de producto] de Workfront Fusion.

   >[!IMPORTANT]
   >
   > No realice ningún cambio en el propio [!UICONTROL Perfil del producto].

1. Con la pestaña **[!UICONTROL Usuarios]** seleccionada encima de la lista, haga clic en **[!UICONTROL Añadir usuario]**.

1. En el cuadro **[!UICONTROL Añadir usuarios a este perfil de producto]**, introduzca la dirección de correo electrónico o el nombre del usuario que desea añadir y, a continuación, seleccione el usuario en la lista que aparece.

1. Haga clic en **[!UICONTROL Guardar]**.

   El usuario se crea en Workfront Fusion.

1. (Opcional) Continúe con [Cambiar el nivel de acceso de un usuario en Workfront Fusion](#change-a-users-access-level-in-workfront-fusion)

## Cambio del nivel de acceso de un usuario en Workfront Fusion

* [Cambie la función de un usuario a Admin](#change-a-users-role-to-admin)
* [Cambiar la función de un usuario a Miembro, Contable o Desarrollador de aplicaciones](#change-a-users-role-to-member-accountant-or-app-developer)

### Cambie la función de un usuario a Admin

Otorgar al usuario una función de administrador debe hacerse en [!DNL Adobe Admin Console].

1. En la página de Workfront Fusion [!UICONTROL Perfil de producto] donde agregó al usuario, seleccione la pestaña **[!UICONTROL Administradores]**.

1. Haga clic en **[!UICONTROL Add Admin]**.

1. En el cuadro **[!UICONTROL Agregar administradores de perfil de producto]**, escriba la dirección de correo electrónico o el nombre del usuario que desea que sea administrador y, a continuación, seleccione el usuario en la lista que aparece.

1. Haga clic en **[!UICONTROL Guardar]**.

   El usuario es ahora administrador en Workfront Fusion.

### Cambiar la función de un usuario a Miembro, Contable o Desarrollador de aplicaciones

Las funciones de miembro, contador y desarrollador de aplicaciones se gestionan dentro de Workfront Fusion.

Para obtener instrucciones, vea [Ver o editar los roles de usuario](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/manage-users-and-teams/view-or-edit-user-roles.md).

## Asignar un usuario existente en [!DNL Adobe Admin Console] a Workfront Fusion

Puede añadir un usuario existente a un equipo en Fusion. Esto se gestiona dentro de Fusion.

Para obtener instrucciones, consulte [Agregar un usuario a un equipo](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/add-a-user-to-a-team.md).
