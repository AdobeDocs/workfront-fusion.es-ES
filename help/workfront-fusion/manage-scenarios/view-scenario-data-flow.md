---
title: Ver flujo de datos en un escenario
description: Puede ver un escenario en ejecución para ver cómo fluyen los datos a través de él.
author: Becky
feature: Workfront Fusion
source-git-commit: 43f4dd92f7b15e32d956c889f7dccb1527f81d2d
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 25%

---

# Ver flujo de datos en un escenario en ejecución

Puede ver un escenario en ejecución para ver cómo fluyen los datos a través de él.

Mientras se ejecuta un escenario, el módulo activo está marcado por un anillo creciente alrededor del módulo. El anillo solo muestra que la módulo se está ejecutando, no su progreso. Los módulos que se ejecutan rápidamente pueden mostrar solo una pequeña parte del anillo.

![Anillo alrededor de módulo](assets/ring-around-module.png)

Una vez ejecutada la módulo, aparece un indicador de salida.

![Output indicador](assets/data-flow-output.png)

Si el módulo procesa más de un bumdle, el anillo aparece para cada paquete procesado y el indicador de salida cuenta para cada paquete que produce.

Para obtener más información sobre el flujo de datos de escenarios, consulte [Flujo](/help/workfront-fusion/references/scenarios/scenario-execution-flow.md) de ejecución de escenarios.

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
   <p>Nuevo:</p> <ul><li>[! UICONTROL Seleccionar] o [! UICONTROL Prime] plan: [!DNL Workfront] Su organización debe comprar [!DNL Adobe Workfront Fusion].</li><li>[! UICONTROL Ultimate] [!DNL Workfront] plan: [!DNL Workfront Fusion] está incluido.</li></ul>
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

Para obtener más información sobre la información de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Ver flujo de datos en un escenario en ejecución

1. Haga clic en el **[!UICONTROL pestaña Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desee vista flujo de datos.
1. Si el escenario no se está ejecutando, actívelo o haga clic en **Ejecutar una vez** para inicio la ejecución del escenario.
1. Seleccione la ejecución que desea vista en la sección En ejecución del panel del historial de ejecución.

![En ejecución](assets/currently-running.png)


