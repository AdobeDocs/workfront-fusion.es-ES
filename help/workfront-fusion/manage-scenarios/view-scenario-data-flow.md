---
title: Ver el flujo de datos en un escenario
description: Puede ver un escenario en ejecución para ver cómo fluyen los datos a través de él.
author: Becky
feature: Workfront Fusion
exl-id: 24eeb1d3-b5a7-4486-8d0b-0a43eb154e8e
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 21%

---

# Ver el flujo de datos en un escenario en ejecución

Puede ver un escenario en ejecución para ver cómo fluyen los datos a través de él.

Mientras se ejecuta un escenario, el módulo activo se marca con un anillo de crecimiento alrededor del módulo. El anillo solo muestra que el módulo se está ejecutando, no su progreso. Los módulos que se ejecutan rápidamente pueden mostrar solo una pequeña parte del anillo.

![Anillo alrededor del módulo](assets/ring-around-module.png)

Una vez ejecutado el módulo, aparecerá un indicador de salida.

![Indicador de salida](assets/data-flow-output.png)

Si el módulo procesa más de un paquete, el anillo aparece para cada paquete procesado y el indicador de salida cuenta para cada paquete que genera.

Para obtener más información sobre el flujo de datos del escenario, consulte [Flujo de ejecución del escenario](/help/workfront-fusion/references/scenarios/scenario-execution-flow.md).

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

## Ver el flujo de datos en un escenario en ejecución

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea ver el flujo de datos.
1. Si el escenario no se está ejecutando, actívelo o haga clic en **Ejecutar una vez** para iniciarlo.
1. Seleccione la ejecución que desea ver en la sección Actualmente en ejecución del panel Historial de ejecuciones.

![En ejecución](assets/currently-running.png)
