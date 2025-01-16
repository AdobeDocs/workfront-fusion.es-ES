---
title: Publish y uso compartido de plantillas
description: Al crear una plantilla, esta plantilla estará disponible para todos los integrantes del equipo. Si desea compartir la plantilla con alguien que no pertenezca a su equipo, primero debe publicarla.
author: Becky
feature: Workfront Fusion
exl-id: 99a1227d-bff9-479f-b8b9-efcf7cea3708
source-git-commit: 7acc27ab2ce80b964b7f9fbb302816aa75964ab5
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 38%

---

# Publish y uso compartido de plantillas

Al crear una plantilla, esta plantilla estará disponible para todos los integrantes del equipo. Si desea compartir la plantilla con alguien que no pertenezca a su equipo, primero debe publicarla.

Para obtener información sobre cómo crear una plantilla, vea [Crear una plantilla nueva](/help/workfront-fusion/create-and-manage-templates/create-new-fusion-templates.md).

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
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Se debe crear una plantilla para poder publicarla o compartirla.

## Publish una plantilla

1. En el panel de navegación izquierdo, haga clic en **[!UICONTROL Templates]**.
1. Haga clic en la ficha **[!UICONTROL Team templates]**.
1. Haga clic en **Publish** en la línea de la plantilla que desee publicar.

   O


   Haga clic en el nombre de la plantilla que desee publicar y luego haga clic en el botón **[!UICONTROL Publish]** en la esquina superior derecha de la pantalla.

## Compartir una plantilla de [!DNL Workfront Fusion]

Después de publicar una plantilla, puede compartirla.

1. En el panel de navegación izquierdo, haga clic en **[!UICONTROL Templates]**.
1. Haga clic en la ficha **[!UICONTROL Team templates]**.
1. Haga clic en el nombre de la plantilla que desee compartir para abrirla.
1. Haga clic en la ficha **Publicado** para abrir esa versión de la plantilla.
1. (Condicional) Si desea un vínculo que se pueda compartir, haga clic en **[!UICONTROL Share public link]**.

   >[!NOTE]
   >
   >Aunque puede compartir este vínculo, la plantilla en sí permanece en la ficha [!UICONTROL Team templates] y no es pública.

1. (Condicional) Si desea que la plantilla se haga pública, envíela al administrador para que la apruebe haciendo clic en **[!UICONTROL Request Approval]**.

   >[!NOTE]
   >
   >* Una vez aprobada la plantilla, se vuelve pública. [!UICONTROL Public templates] están visibles en la ficha [!UICONTROL Public templates] para todos los usuarios de [!DNL Workfront Fusion], independientemente de la organización o del equipo.
   >* No se notifica al administrador acerca de la recepción de la plantilla para que la revise por correo electrónico.  Si la aprobación es urgente, póngase en contacto directamente con el administrador.


## Estados de plantilla

Fusion guarda las distintas versiones (privada, publicada y aprobada) en diferentes pestañas de la página de la plantilla.

Están disponibles los siguientes estados:

* **[!UICONTROL Private]**: esta plantilla solo está visible para el autor de la plantilla y su equipo.
* **[!UICONTROL Published]**: esta plantilla solo está visible para el autor de la plantilla y su equipo. Puede enviar plantillas publicadas para su aprobación y copiar un vínculo para compartir.
* **[!UICONTROL Approved]**: esta plantilla está visible para todos los usuarios de Workfront Fusion en la ficha [!UICONTROL Public templates]. Para copiar un vínculo que se puede compartir, haga clic en [!UICONTROL Options], en la esquina superior derecha de la pantalla.

<!--You can also check the status from the [!UICONTROL Team templates] tab. If a template is published, it will have an icon to the right of the template name.

* **Eye icon**: The template is published, it is visible only for the team, and the approval request was not sent.
* **Yellow checkmark icon**: The template is published, it is visible only for the team, and the approval request was sent.
* **Green checkmark icon**: The template is published and public. It is visible for any Workfront Fusion user in the [!UICONTROL Public templates] tab. It is also still visible in the [!UICONTROL Team templates] tab, and the template author or their team member can still edit it.

Templates without icons have [!UICONTROL Private] status. They are not published and are visible only to the team.
-->
