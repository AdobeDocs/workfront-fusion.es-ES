---
content-type: reference
title: Aprobar o desaprobar plantillas
description: Este artículo describe cómo aprobar o desaprobar plantillas de Fusion.
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: dafecd8b-96e5-46da-9ab6-15f0bc9b52a4
source-git-commit: 23e9f383b25c7b3789c413e557b94418e48a636b
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 22%

---

# Aprobar o desaprobar plantillas para la pestaña Public

Las plantillas de Adobe Workfront Fusion son escenarios creados previamente y diseñados para automatizar y optimizar varios flujos de trabajo. Estas plantillas pueden ayudar a los usuarios a configurar integraciones y automatizaciones rápidamente sin necesidad de crear todo desde cero.

Si es administrador, puede elegir si determinadas plantillas deben compartirse con toda la organización en la pestaña Plantillas públicas.

Los usuarios pueden enviar las plantillas que crean para su aprobación y compartirlas en la página Plantillas públicas. <!--do the have to be requested or can an admin just choose to approve?-->

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
  <col>
  <col>
  <tbody>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] plan</td>
      <td><p>Cualquiera</p></td>
    </tr>
    <tr data-mc-conditions="">
      <td role="rowheader">[!DNL Adobe Workfront] licencia</td>
      <td><p>Nuevo: [!UICONTROL Standard]</p><p>O</p><p>Actual: [!UICONTROL Work] o superior</p></td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront Fusion] licencia**</td>
      <td>
        <p>Actual: no se requiere licencia para [!DNL Workfront Fusion].</p>
        <p>O</p>
        <p>Heredado: cualquiera</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">Producto</td>
      <td>
        <p>Nuevo:</p>
        <ul>
          <li>[!UICONTROL Select] o plan [!UICONTROL Prime] [!DNL Workfront]: su organización debe comprar [!DNL Adobe Workfront Fusion].</li>
          <li>[!UICONTROL Ultimate] [!DNL Workfront] Plan: [!DNL Workfront Fusion] incluido.</li>
        </ul>
        <p>O</p>
        <p>Actual: su organización debe comprar [!DNL Adobe Workfront Fusion].</p>
      </td>
    </tr>
  </tbody>
</table>

<!--
For more detail about the information in this table, see [Access requirements in Workfront documentation](/help/quicksilver/administration-and-setup/add-users/access-levels-and-object-permissions/access-level-requirements-in-documentation.md). 

For information on [!DNL Adobe Workfront Fusion] licenses, see [[!DNL Adobe Workfront Fusion] licenses](../../workfront-fusion/get-started/license-automation-vs-integration.md).-->

+++

## Aprobar o desaprobar plantillas de [!DNL Workfront Fusion]

La aprobación de una plantilla la hace visible en la ficha [!UICONTROL Public templates] y está disponible para todos los usuarios.

Al desaprobar una plantilla, esta se eliminará de la ficha [!UICONTROL Public templates] y estará disponible solamente para el equipo que la creó.

1. Haga clic en **[!UICONTROL Administration]** en el panel de navegación izquierdo para abrir el área [!UICONTROL Administration].
1. Haga clic en **[!UICONTROL Templates]** en el panel de navegación izquierdo.
1. Si desea aprobar una plantilla, haga clic en **[!UICONTROL Approve]** a la derecha de la plantilla.
1. Si desea desaprobar una plantilla, haga clic en **[!UICONTROL Disapprove]** a la derecha de la plantilla.

>[!NOTE]
>
>Si está aprobando la plantilla que fue aprobada previamente y luego editada, su segunda aprobación sobrescribirá la plantilla original.


## Estados de plantilla

Puede comprobar el estado en la página de la plantilla bajo el nombre de la plantilla.

Están disponibles los siguientes estados:

* **[!UICONTROL Private]**: esta plantilla solo está visible para el autor de la plantilla y su equipo.
* **[!UICONTROL Published]**: esta plantilla solo está visible para el autor de la plantilla y su equipo. Una vez publicada, puede enviar la plantilla para su aprobación si lo desea. También puede copiar un vínculo compartible.
* **[!UICONTROL Approved]**: esta plantilla está visible para todos los usuarios de Workfront Fusion en la ficha [!UICONTROL Public templates]. También puede copiar un vínculo que se puede compartir haciendo clic en [!UICONTROL Options] en la esquina superior derecha de la pantalla.

También puede comprobar el estado desde la ficha [!UICONTROL Team templates]. Si se publica una plantilla, aparecerá un icono a la derecha del nombre de la plantilla.

* **Icono en forma de ojo**: la plantilla está publicada; solo es visible para el equipo; y no se envió una solicitud de aprobación.
* **Icono de marca de verificación amarilla**: la plantilla está publicada; solo es visible para el equipo; y está pendiente de aprobación para agregarse a la pestaña Plantillas públicas.
* **Icono de marca de verificación verde**: la plantilla está disponible en la pestaña Plantillas públicas y es visible para cualquier usuario de Workfront Fusion. También sigue visible en la ficha [!UICONTROL Team templates]. El autor de la plantilla o el miembro de su equipo aún pueden editarla.

Las plantillas sin iconos tienen el estado [!UICONTROL Private]. No se publican y solo son visibles para el equipo.


<!--

## Questions about how this works

Editing

1. If an admin edits a template, do they have to publish again? ... Do they have to approve again?
1. What does publishing actually do?
1. Does a user have to submit for approval to share on the Public tab or can admin go through and approve/reject which ones they want? 
1. What is the admin approving? Does a user have to submit it for approval? 



What does "Publishing" mean?
What does "Approving" mean?
If an admin edits a template, do they have to publish again? ... Do they have to approve again?
Does a user have to submit for approval to share on the Public tab or can admin go through and approve/reject which ones they want? 
What is the admin approving? Does a user have to submit it for approval?

-->
