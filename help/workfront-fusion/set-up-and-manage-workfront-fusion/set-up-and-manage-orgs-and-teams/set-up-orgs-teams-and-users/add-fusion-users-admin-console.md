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
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 61%

---

# Añadir usuarios a Adobe Workfront Fusion mediante Adobe Admin Console

Puede añadir un usuario a [!DNL Adobe Admin Console] y asignarlo a [!DNL Adobe Workfront Fusion], o asignar un usuario existente en [!DNL Adobe Admin Console] a [!DNL Workfront Fusion].

Para ver un vídeo que describe [!DNL Workfront Fusion] en [!DNL Adobe Admin Console], incluido cómo añadir usuarios, consulte [[!DNL Fusion]  en Adobe IMS](https://video.tv.adobe.com/v/3412464/){target=_blank}.



Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] plan*</td> 
   <td> <p>[!UICONTROL Pro] o superior</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licencia*</td> 
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licencia**</td> 
   <td>
   <p>Requisito de licencia actual: no se requiere ninguna licencia de [!DNL Workfront Fusion].</p>
   <p>O</p>
   <p>Requisito de licencia heredado: [!UICONTROL [!DNL Workfront Fusion] para automatización e integración de trabajo </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Requisito de producto actual: si tiene el plan [!UICONTROL Select] o [!UICONTROL Prime] [!DNL Adobe Workfront], su organización debe adquirir [!DNL Adobe Workfront Fusion] así como [!DNL Adobe Workfront] para utilizar la funcionalidad descrita en este artículo. [!DNL Workfront Fusion] está incluido en el plan [!UICONTROL Ultimate] [!DNL Workfront].</p>
   <p>O</p>
   <p>Requisito de producto heredado: su organización debe adquirir [!DNL Adobe Workfront Fusion] y [!DNL Adobe Workfront] para utilizar la funcionalidad descrita en este artículo.</p>
   </td> 
  </tr>
   <tr> 
   <td role="rowheader">[!DNL Adobe] derechos de administrador</td> 
   <td>Debe ser un [!UICONTROL Product Configuration Administrator] de [!DNL Adobe] productos para su organización.</td> 
  </tr>
  </tbody> 
</table>

&#42;Para saber qué plan, tipo de licencia o acceso tiene, póngase en contacto con el administrador de [!DNL Workfront].

&#42;&#42;Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).



## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] paquete</td> 
   <td> <p>Cualquiera</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licencia</td> 
   <td> <p>Nuevo: [!UICONTROL Standard]</p><p>O</p><p>Actual: [!UICONTROL Work] o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licencia**</td> 
   <td>
   <p>Actual: no se requiere licencia para [!DNL Workfront Fusion].</p>
   <p>O</p>
   <p>Heredado: cualquiera </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>[!UICONTROL Select] o plan [!UICONTROL Prime] [!DNL Workfront]: su organización debe comprar [!DNL Adobe Workfront Fusion].</li><li>[!UICONTROL Ultimate] [!DNL Workfront] plan: [!DNL Workfront Fusion] está incluido.</li></ul>
   <p>O</p>
   <p>Actual: su organización debe comprar [!DNL Adobe Workfront Fusion].</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">Configuraciones de nivel de acceso*</td> 
   <td> 
     <p>Debe ser administrador de [!DNL Workfront Fusion] de su organización.</p>
     <p>Debe ser administrador de [!DNL Workfront Fusion] de su equipo.</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++


## Requisitos previos

Antes de usar [!DNL Admin Console] para [!DNL Workfront], debería recibir un mensaje de correo electrónico que le invite a la consola.

1. Si es nuevo en [!DNL Adobe] y ha recibido un mensaje de correo electrónico que le informa de que ahora tiene derechos de administración para administrar el software y los servicios de [!DNL Adobe] para su organización, haga clic en el botón del mensaje de correo electrónico para crear una cuenta de [!DNL Adobe] y abrir [!DNL Admin Console].

   O

   Si ya tiene una cuenta de Adobe, vaya a la página de [[!DNL Adobe Admin Console] ](https://adminconsole.adobe.com).


## Añadir un nuevo usuario a [!DNL Adobe Admin Console] y a [!DNL Workfront Fusion]

1. En la [[!DNL Adobe Admin Console] página](https://adminconsole.adobe.com/), seleccione la ficha **[!UICONTROL Products]** en la barra de navegación superior y, a continuación, seleccione el mosaico de producto **[!DNL Workfront Fusion]**.

   ![Fusion en Admin Console](assets/fusion-product-admin-console.png)

1. En la lista que se muestra, seleccione la organización en la que desea añadir un usuario.

   ![Instancia de Fusion en Admin Console](assets/fusion-instances-admin-console.png)

1. En la lista que aparece, con la ficha **[!UICONTROL Product Profiles]** seleccionada, haga clic en el nombre del vínculo [!DNL Workfront Fusion] [!UICONTROL Product Profile].

   >[!IMPORTANT]
   >
   > No realice ningún cambio en [!UICONTROL Product Profile].

1. Con la ficha **[!UICONTROL Users]** seleccionada encima de la lista, haga clic en **[!UICONTROL Add User]**.

1. En el cuadro **[!UICONTROL Add users to this product profile]**, escriba la dirección de correo electrónico o el nombre del usuario que desea agregar y, a continuación, seleccione el usuario en la lista que aparece.

1. Haga clic en **[!UICONTROL Save]**.

   Se crea el usuario en [!DNL Workfront Fusion].

1. (Opcional) Continúe con [Cambio del nivel de acceso de un usuario en  [!DNL Workfront Fusion]](#change-a-users-access-level-in-workfront-fusion)

## Cambio del nivel de acceso de un usuario en Workfront Fusion

* [Cambie la función de un usuario a Admin](#change-a-users-role-to-admin)
* [Cambiar la función de un usuario a Miembro, Contable o Desarrollador de aplicaciones](#change-a-users-role-to-member-accountant-or-app-developer)

### Cambie la función de un usuario a Admin

Otorgar al usuario una función de administrador debe hacerse en [!DNL Adobe Admin Console].

1. En la página [!DNL Workfront Fusion] [!UICONTROL Product Profile] donde agregó el usuario, seleccione la ficha **[!UICONTROL Admins]**.

1. Haga clic en **[!UICONTROL Add Admin]**.

1. En el cuadro **[!UICONTROL Add product profile administrators]**, escriba la dirección de correo electrónico o el nombre del usuario que desea que sea administrador y, a continuación, seleccione el usuario en la lista que aparece.

1. Haga clic en **[!UICONTROL Save]**.

   El usuario es ahora administrador en [!DNL Workfront Fusion].

### Cambiar la función de un usuario a Miembro, Contable o Desarrollador de aplicaciones

Las funciones de miembro, contador y desarrollador de aplicaciones se gestionan dentro de Workfront Fusion.

Para obtener instrucciones, vea [Ver o editar los roles de usuario](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/manage-users-and-teams/view-or-edit-user-roles.md).

## Asignar un usuario existente en [!DNL Adobe Admin Console] a [!DNL Workfront Fusion]

Puede añadir un usuario existente a un equipo en Fusion. Esto se gestiona dentro de Fusion.

Para obtener instrucciones, consulte [Agregar un usuario a un equipo](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/add-a-user-to-a-team.md).
