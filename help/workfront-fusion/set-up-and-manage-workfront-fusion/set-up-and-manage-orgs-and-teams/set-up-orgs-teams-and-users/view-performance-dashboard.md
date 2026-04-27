---
title: Ver el panel de control de rendimiento de una organización
description: Fusion administrators can view a dashboard that shows execution metrics for an organization.
author: Becky
feature: Workfront Fusion
exl-id: 8f80f86a-69e5-48a1-9812-87322a4959a6
source-git-commit: 6762806f17a0fc55531b647a84901b8ca572a997
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 9%

---

# Ver el panel de control de rendimiento de una organización

The Fusion Performance Dashboard allows you to quickly see which scenarios are running the most, where delays are occurring, and how effectively your worker pools are operating. This provides real-time visibility into execution volumes, queue depth, pool utilization, and scenario-level performance.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Paquete de Adobe Workfront</td> 
   <td> <p>Adobe Workfront Workflow Ultimate and Adobe Workfront Automation and Integration Ultimate</p><p>Workfront Ultimate</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencias de Adobe Workfront</td> 
   <td> <p>Estándar</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Configuraciones de nivel de acceso</td> 
   <td> 
     <p>Debe ser administrador de Workfront Fusion para su organización.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte los [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Performance dashboard components

>[!NOTE]
>
>Metrics are shown by worker pool. To view a different worker pool, click the Pool field near the upper-left corner of the dashboard, then select the pool you want to view metrics for.

<!--

>[!NOTE]
>
>Organizations can request provisioning for one additional worker pool (for a total of 2).

-->

In the Fusion performance dashboard, you can see the following metrics.

* **Executions waiting to be processed**
This chart shows the number of executions waiting to be processed (also known as the execution backlog) at a given point in time.

  A high number of executions waiting to be processed may affect performance in your Fusion instance. You will receive a notification if your execution backlog reaches 5000 executions. We recommend identifying responsible scenarios and modifying or disabling them. If the high execution backlog persists, the Fusion team will protect the performance of your Fusion instance by disabling the responsible scenarios.
* **Pool Utilization**
This chart shows worker pool utilization over time. If this chart routinely shows worker pool utilization, you may want to assign some scenarios to another pool.

  If a pool is nearing 100% utilization, other resources that use the same pool may be delayed or disrupted. If this occurs, we recommend reassigning a high-usage scenario to another worker pool, or modifying existing scenarios to be less resource intensive.
* **Executions per scenario**
This chart displays executions per scenario. Different colors represent different scenarios. When you hover over the chart, a window appears that shows which color is which scenario.

  You can use this chart to identify which scenarios may be causing an execution backlog or high worker pool utilization.
* **Duration of executions**
This chart displays executions per scenario. Different colors represent different scenarios. When you hover over the chart, a window appears that shows which color is which scenario.

  You can use this chart to identify scenarios that are taking longer than usual, including those affected by issues with a connected app or service.

## View the Fusion Performance Dashboard

1. In Fusion, click **Performance** in the left navigation.

   The Dashboard opens.

1. To view data for a specific point in time, hover over a dashboard and adjust your cursor to be over the point in time you want to view.

   A line appears over that point in time on all the graphs, and a window showing data for that time appears on each graph.
1. To view data for a specific scenario in the Executions per scenario chart or the Duration of executions chart, click on a bar of the color for the scenario you want to view data for. To return to the view showing all scenarios, click on the graph again.
1. To go to a specific scenario shown in the Executions per scenario chart or the Duration of executions chart, right click on a bar of the color for the scenario, and select **Open scenario in new tab**.
1. To expand a chart, click the **Expand** icon ![Expand icon](assets/expand-icon.png) at the upper-right corner of that chart.
1. To change the time range of the dashboard, the Time Range field in the upper-right corner of the dashboard, then select a new time frame. The longest available time frame is 24 hours, and the shortest is 15 minutes.
1. To refresh the charts, click the Refresh icon near the upper-right corner of the dashboard.
1. To view a different worker pool, click the Pool field near the upper-left corner of the dashboard, then select the pool you want to view.
