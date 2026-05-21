---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: scenarios
title: Administrar escenarios bloqueados
description: Administración de escenarios bloqueados en Adobe Workfront Fusion
author: Becky
feature: Workfront Fusion
exl-id: b5e92bdc-cc1d-4b22-8c5f-42cc279d5590
TQID: https://experienceleague.adobe.com/1eVGWr4SwutYzNmCKB62CCWbQ6ExdXtpjC5BORh-kxo
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 327
ht-degree: 77%

---

# Administrar escenarios bloqueados

En algunos casos, un escenario podría estar bloqueado temporalmente en Workfront Fusion. Los escenarios bloqueados se desbloquearán automáticamente en un plazo de 2 a 4 horas. Puede desbloquear escenarios manualmente, pero generalmente no se recomienda.

Los escenarios pueden bloquearse por varios motivos:

* Workfront Fusion no admite el procesamiento paralelo de escenarios programados. Estos escenarios se bloquean al principio de la ejecución del escenario y se desbloquean cuando se completa. Si se interrumpe la ejecución, es posible que el escenario no se desbloquee. Esto puede ocurrir cuando un usuario detiene manualmente el escenario o cuando se produce un problema en el sistema.

* El equipo de ingeniería de Workfront Fusion puede bloquear un escenario porque está causando problemas de rendimiento u otros problemas.

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
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Desbloquear un escenario bloqueado

Los escenarios bloqueados se desbloquearán transcurridas de dos a cuatro horas desde el momento en que se bloquearon. Puede desbloquear un escenario manualmente antes de programarlo para que se desbloquee automáticamente.

>[!WARNING]
>
>Desbloquear manualmente un escenario puede provocar errores en las ejecuciones de un escenario. Se recomienda desbloquear escenarios manualmente solo cuando un escenario esté bloqueado debido a la ejecución y detención de ejecuciones como parte del diseño del mismo. En otras circunstancias, se recomienda esperar a que el escenario se desbloquee automáticamente.


Para desbloquear manualmente un escenario bloqueado:

1. Vaya a la página de detalles del escenario bloqueado.
1. Haga clic en **[!UICONTROL Opciones]** en la esquina superior derecha de la pantalla.
1. Seleccione **[!UICONTROL Desbloquear ejecución]**.
1. Haga clic en **[!UICONTROL Desbloquear]**.
   ![Desbloquear escenario](assets/unlock-scenario.png)
