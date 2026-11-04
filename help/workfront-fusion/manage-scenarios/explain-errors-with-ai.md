---
title: Explicar un error de escenario con IA
description: Cuando se produce un error en la ejecución de un escenario, puede hacer clic en Explicar junto al error para obtener una descripción breve y en lenguaje sencillo de lo que ha fallado y cómo solucionarlo.
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: e2420c8a25fd9e38c4b0300b00560fe1837a5e43
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 15%
---
# Explicar un error de escenario con IA

Cuando falla la ejecución de un escenario, IA puede proporcionarle una descripción breve y en lenguaje sencillo de qué ha fallado y cómo solucionarlo. La explicación aparece junto al error original, por lo que pueden leerse ambos juntos.

Puede explicar los errores en las siguientes áreas de Workfront Fusion:

* Los detalles del error del módulo en el diseñador de escenarios
* Los detalles de ejecución en el historial de ejecución de un escenario
* La tabla [!UICONTROL Registros de ejecuciones con errores] de la página de información

>[!NOTE]
>
>El botón **[!UICONTROL Explicar]** solo está disponible en el nuevo diseñador de escenarios. No está disponible en el diseñador de escenarios heredado.

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
   <p>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Explicar un error en los detalles de salida del módulo

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea explicar un error.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Ejecute el escenario, según lo programado o haciendo clic en **Ejecutar una vez**.
1. Cuando falle un módulo, abra los detalles del error del módulo.
1. Haga clic en **[!UICONTROL Explicar]**.

   El botón se encuentra debajo del error.

   ![Explicar error en la salida del módulo](assets/explain-in-module-output.png)

La explicación aparece debajo del error.

>[!NOTE]
>
> * Mientras que AI genera la explicación, aparece un estado de carga.
> * Si no se genera la explicación, haga clic en **[!UICONTROL Inténtelo de nuevo]**.
> * Si su organización alcanza el límite de uso de IA, aparece un mensaje de límite de uso en lugar de una explicación.

## Explicar un error en el historial de ejecución de un escenario

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo y, a continuación, haga clic en el escenario.
1. Haga clic en **[!UICONTROL Historial]** cerca del nombre del escenario.
1. Haga clic en la ejecución fallida que desee ver.

   Cada error en los detalles de la ejecución tiene un botón **[!UICONTROL Explicar]** debajo.

1. Haga clic en **[!UICONTROL Explicar]** debajo del error que desea explicar.

   Si varios módulos fallan en la ejecución, puede explicar cada error por su cuenta.

   ![Explicar en el historial de ejecución](assets/explain-in-execution-details.png)

Para obtener más información acerca de cómo ver una ejecución, vea [Ver el historial de ejecución de un escenario](/help/workfront-fusion/manage-scenarios/view-scenario-execution-history.md) y [Ver la ejecución de un escenario específico](/help/workfront-fusion/manage-scenarios/view-a-specific-scenario-execution.md).

>[!NOTE]
>
> * Mientras que AI genera la explicación, aparece un estado de carga.
> * Si no se genera la explicación, haga clic en **[!UICONTROL Inténtelo de nuevo]**.
> * Si su organización alcanza el límite de uso de IA, aparece un mensaje de límite de uso en lugar de una explicación.

## Explicar un error en la página de perspectivas

1. En Fusion, haga clic en **[!UICONTROL Información]** en el panel de navegación izquierdo.
1. En la tabla [!UICONTROL ejecuciones con errores], pase el ratón sobre la fila con errores que desee ver.

   Aparece un botón **[!UICONTROL Explicar]**.

1. Haga clic en **[!UICONTROL Explicar]**.

   ![Explicar en la página de perspectivas](assets/explain-failed-execution-log.png)

   Se abre una ventana emergente que muestra el error y la explicación de la IA.

Para obtener más información acerca de la página de perspectivas, vea [Ver el panel de perspectivas de una organización](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/view-insights-dashboard.md).

>[!NOTE]
>
> * Mientras que AI genera la explicación, aparece un estado de carga.
> * Si no se genera la explicación, haga clic en **[!UICONTROL Inténtelo de nuevo]**.
> * Si su organización alcanza el límite de uso de IA, aparece un mensaje de límite de uso en lugar de una explicación.
