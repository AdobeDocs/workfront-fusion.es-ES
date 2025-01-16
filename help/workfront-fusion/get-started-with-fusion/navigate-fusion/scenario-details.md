---
title: Información general sobre escenarios
description: Detalles del escenario en  [!DNL Adobe Workfront Fusion]
author: Becky
feature: Workfront Fusion
exl-id: a6d07ed9-aa55-4993-9f78-7e691aa61049
source-git-commit: 190bfe5992fb21b789a7246c4ae732a5dc7672fa
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 20%

---

# Información general sobre escenarios

La página de detalles del escenario es la página principal de un escenario específico. Proporciona acceso a información específica para el escenario representado en la página.

También le proporciona acceso al editor de escenarios, donde puede editar el escenario.

Para obtener información sobre el editor de escenarios, consulte [El editor de escenarios](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md)

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

## Abrir la página [!UICONTROL Scenario detail]:

1. Haga clic en la ficha **[!UICONTROL Scenario]** en el panel izquierdo y, a continuación, haga clic en un escenario sobre el que desee obtener detalles.

   O

   Si está trabajando en el escenario en el editor de escenarios, haga clic en la flecha izquierda ![](assets/exit-editing-arrow.png) cerca de la esquina superior izquierda de la ventana.

1. En la página que se muestra, puede revisar los elementos que se enumeran en la siguiente tabla:

   ![](assets/scenario-detail-350x207.png)

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Modules diagram] </td> 
      <td>Esta pestaña muestra la representación visual del escenario. El diagrama es el mismo que verá en el editor de escenarios.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Reports] pestaña </td> 
      <td> <p>Abra esta pestaña para ver un gráfico del número de operaciones realizadas por este escenario durante los últimos 30 días.</p>  </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL History] pestaña </td> 
      <td> <p>Abra esta pestaña para ver el historial del escenario, incluidas las ediciones realizadas en él. </p> <p>La pestaña [!UICONTROL History] también proporciona el historial de ejecución de escenario de cada ejecución, que incluye lo siguiente:</p> 
       <ul> 
        <li>Estado de cada ejecución (éxito o error)</li> 
        <li>Duración de ejecución</li> 
        <li>Número de operaciones</li> 
        <li>Tamaño de la transferencia de datos</li> 
        <li>Vínculo a información detallada</li> 
       </ul> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Incomplete executions]</td> 
      <td> <p>Esta pestaña proporciona información sobre cualquier ejecución incompleta del escenario. Incluye la siguiente información para cada ejecución incompleta:</p> 
       <ul> 
        <li>Fecha de creación</li> 
        <li>Tamaño de la transferencia de datos</li> 
        <li>Reintentar</li> 
        <li>Resuelto</li> 
        <li>Número de intentos</li> 
       </ul> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Activate scenario] (Botón de activación/desactivación)</td> 
      <td>Una vez creado un escenario, debe activarse para que se ejecute según su programación. Al hacer clic en el botón Activado/Desactivado cerca de la esquina superior derecha, puede activar o desactivar el escenario. Una vez activado, el escenario se ejecuta según su programación.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Edit]</td> 
      <td>Haga clic en el diagrama de escenario para abrir el editor de escenarios y realizar cambios en el escenario.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Options]</td> 
      <td> <p>Este menú le proporciona opciones adicionales sin tener que abrir el editor de escenarios. Estos incluyen:</p> 
       <ul> 
        <li>[!UICONTROL Scheduling]</li> 
        <li>[!UICONTROL Rename]</li> 
        <li>[!UICONTROL Clone]</li> 
        <li>[!UICONTROL Delete]</li> 
       </ul> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Currently running]</td> 
      <td>Esta área muestra información relacionada con la ejecución que se está ejecutando.</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL History] panel</p> <p> </p> </td> 
      <td> <p>Esta área muestra información relacionada con las últimas ejecuciones del escenario. Para cada ejecución, se muestra:</p> 
       <ul> 
        <li>Fecha de ejecución</li> 
        <li>Estado (correcto o fallido)</li> 
        <li>Duración de ejecución</li> 
        <li>Tamaño de la transferencia de datos</li> 
        <li>Vínculo a información detallada</li> 
       </ul> </td> 
     </tr> 
         <tr> 
      <td role="rowheader"> <p>[!UICONTROL Events] panel</p>  </td> 
      <td>Esta área muestra información sobre los eventos relacionados con el escenario.  </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Processing banner]</p>  </td>

   <td>Si el escenario se ha ejecutado recientemente, puede ver un titular que dice:<p><code>Data is still being processed. Only partial scenario history will show until processing is complete.</code></p>Esto aparece mientras los detalles de ejecución se escriben en el almacenamiento. El procesamiento se produce inmediatamente después de que se ejecute el escenario. y no debe durar más de unos minutos. Es posible que los detalles de la ejecución del escenario no estén visibles mientras se procesa la ejecución.</td> 
     </tr> 
    </tbody> 
   </table>
