---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: scenarios
title: Administrar escenarios bloqueados
description: Administración de escenarios bloqueados en Adobe Workfront Fusion
author: Becky
feature: Workfront Fusion
exl-id: b5e92bdc-cc1d-4b22-8c5f-42cc279d5590
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 62%

---

# Administrar escenarios bloqueados

En algunos casos, un escenario podría estar bloqueado temporalmente en Workfront Fusion. Los escenarios bloqueados se desbloquearán automáticamente en un plazo de 2 a 4 horas. Puede desbloquear escenarios manualmente, pero generalmente no se recomienda.

Los escenarios pueden bloquearse por varios motivos:

* Workfront Fusion no admite el procesamiento paralelo de escenarios programados. Estos escenarios se bloquean al principio de la ejecución del escenario y se desbloquean cuando se completa. Si se interrumpe la ejecución, es posible que el escenario no se desbloquee. Esto puede ocurrir cuando un usuario detiene manualmente el escenario o cuando se produce un problema en el sistema.

* El equipo de ingeniería de Workfront Fusion puede bloquear un escenario porque está causando problemas de rendimiento u otros problemas.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront</td> 
   <td> <p>Cualquiera</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencia de Adobe Workfront</td> 
   <td> <p>Nuevo: estándar</p><p>O</p><p>Actual: [!UICONTROL Work] o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion**</td> 
   <td>
   <p>Actual: no se requiere licencia de Workfront Fusion.</p>
   <p>O</p>
   <p>Heredado: cualquiera </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Plan de Workfront de [!UICONTROL Select] o [!UICONTROL Prime]: su organización debe adquirir Adobe Workfront Fusion.</li><li>Plan de Workfront de [!UICONTROL Ultimate]: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe comprar Adobe Workfront Fusion.</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">Configuraciones de nivel de acceso*</td> 
   <td> 
     <p>Debe ser administrador de Workfront Fusion para su organización.</p>
     <p>Debe ser administrador de Workfront Fusion para su equipo.</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

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
