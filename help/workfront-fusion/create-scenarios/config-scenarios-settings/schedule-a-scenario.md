---
content-type: reference
title: Programar un escenario
description: De forma predeterminada, un escenario se ejecuta cada 15 minutos. Puede cambiar esto definiendo cuándo y con qué frecuencia se ejecuta un escenario activado. Los escenarios de fusión pueden programarse para que se ejecuten incluso cada 5 minutos.
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 9b74af0d-e7ff-4bf5-974e-0651d0d51f71
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 27%

---

# Programar un escenario

De forma predeterminada, un escenario se ejecuta cada 15 minutos. Puede cambiar esto definiendo cuándo y con qué frecuencia se ejecuta un escenario activado. Los escenarios de fusión pueden programarse para que se ejecuten incluso cada 5 minutos.

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
   <p>Nuevo:</p> <ul><li>[!UICONTROL Select] o plan [!UICONTROL Prime] [!DNL Workfront]: su organización debe comprar [!DNL Adobe Workfront Fusion].</li><li>[!UICONTROL Ultimate] [!DNL Workfront] Plan: [!DNL Workfront Fusion] incluido.</li></ul>
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

## Programar un escenario

1. Haga clic en la ficha **Escenario** en el panel izquierdo.
1. Seleccione el escenario que desee programar.
1. En la esquina superior derecha de la página de detalles del escenario, haga clic en **[!UICONTROL Options]** > **[!UICONTROL Scheduling]**

   O

   Haga clic en el icono **[!UICONTROL Scheduling]** (reloj) en el módulo de déclencheur del escenario.

1. Introduzca información en los campos siguientes:

   <table style="table-layout:auto">   
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Run scenario]</td> 
      <td> <p>Seleccione la frecuencia con la que desea ejecutar el escenario y, a continuación, seleccione el intervalo.</p> 
       <ul> 
        <li> <p><strong>[!UICONTROL At regular intervals]</strong> </p> <p>Introduzca el número de minutos entre ejecuciones. El valor predeterminado es 15 minutos.</p> </li> 
        <li> <p><strong>[!UICONTROL Once]</strong> </p> <p>Escriba la fecha y la hora en que desea que se ejecute el escenario. Usar el formato <code>MM/DD/YYYY h:mm A</code>. Ejemplo: <code>06/25/2019 11:00 PM</code>.</p> </li> 
        <li> <p><strong>[!UICONTROL Every day]</strong> </p> <p>Introduzca la hora a la que desea que se ejecute el escenario. Usar el formato <code>h:mm A</code>. Ejemplo: <code>11:00 PM</code>.</p> </li> 
        <li> <p><strong>[!UICONTROL Days of the week]</strong> </p> <p>Días: seleccione los días de la semana en los que desea que se ejecute el escenario. Puede seleccionar uno o más días.</p> <p>Hora: introduzca la hora a la que desea que se ejecute el escenario en los días seleccionados. Usar el formato <code>h:mm A</code>. Ejemplo: <code>11:00 PM</code></p> </li> 
        <li> <p><strong>[!UICONTROL Days of the month]</strong> </p> <p>Días: seleccione los días del mes en que desea que se ejecute el escenario. Puede seleccionar uno o más días.</p> <p>Hora: introduzca la hora a la que desea que se ejecute el escenario en los días seleccionados. Usar el formato <code>h:mm A</code>. Ejemplo: <code>11:00 PM</code></p> </li> 
        <li> <p><strong>[!UICONTROL Specified dates]</strong> </p> <p>Meses: seleccione los meses en los que desea ejecutar el escenario. Puede seleccionar uno o más meses.</p> <p>Días: seleccione los días del mes en que desea que se ejecute el escenario. Puede seleccionar uno o más días.</p> <p>Hora: introduzca la hora a la que desea que se ejecute el escenario en los días seleccionados. Usar el formato <code>h:mm A</code>. Ejemplo: <code>11:00 PM</code></p> </li> 
       </ul> <p>Nota: Debe existir una fecha para que un escenario se ejecute en esa fecha. Por ejemplo, un escenario programado solo para el 31 del mes no se ejecutará en febrero, abril, junio, septiembre o noviembre, porque esos meses no tienen un día 31.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Advanced scheduling]</td> 
      <td>Puede definir intervalos de tiempo específicos durante los cuales se ejecutará el escenario. Puede especificar intervalos de hora del día, días laborables o meses. Para cada intervalo, haga clic en <strong>[!UICONTROL Add]</strong> y rellene los campos como se describe en el campo [!UICONTROL Run scenario].</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Start]</td> 
      <td>Escriba la fecha y la hora después de las cuales desea que se ejecute el escenario. Usar el formato <code>MM/DD/YYYY h:mm A</code>. Ejemplo: <code>06/25/2019 11:00 PM</code>.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL End]</td> 
      <td>Escriba la fecha y la hora antes de las cuales desea que se ejecute el escenario. Usar el formato <code>MM/DD/YYYY h:mm A</code>. Ejemplo: <code>06/25/2019 11:00 PM</code>.</td> 
     </tr> 
    </tbody> 
   </table>

1. Haga clic en **[!UICONTROL OK]** para guardar la configuración de programación y volver al escenario.
