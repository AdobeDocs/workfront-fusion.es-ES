---
content-type: reference
title: Programar un escenario
description: De forma predeterminada, un escenario se ejecuta cada 15 minutos. Puede cambiar esto definiendo cuándo y con qué frecuencia se ejecuta un escenario activado. Los escenarios de fusión pueden programarse para que se ejecuten incluso cada 5 minutos.
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 9b74af0d-e7ff-4bf5-974e-0651d0d51f71
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 24%

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

## Programar un escenario

1. Haga clic en la ficha **Escenario** en el panel izquierdo.
1. Seleccione el escenario que desee programar.
1. En la esquina superior derecha de la página de detalles del escenario, haga clic en **[!UICONTROL Opciones]** > **[!UICONTROL Programación]**

   O

   Haga clic en el icono **[!UICONTROL Programación]** (reloj) en el módulo de déclencheur del escenario.

1. Introduzca información en los campos siguientes:

   <table style="table-layout:auto">   
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Ejecutar escenario]</td> 
      <td> <p>Seleccione la frecuencia con la que desea ejecutar el escenario y, a continuación, seleccione el intervalo.</p> 
       <ul> 
        <li> <p><strong>[!UICONTROL A intervalos regulares]</strong> </p> <p>Introduzca el número de minutos entre ejecuciones. El valor predeterminado es 15 minutos.</p> </li> 
        <li> <p><strong>[!UICONTROL Una Vez]</strong> </p> <p>Escriba la fecha y la hora en que desea que se ejecute el escenario. Usar el formato <code>MM/DD/YYYY h:mm A</code>. Ejemplo: <code>06/25/2019 11:00 PM</code>.</p> </li> 
        <li> <p><strong>[!UICONTROL Todos los días]</strong> </p> <p>Introduzca la hora a la que desea que se ejecute el escenario. Usar el formato <code>h:mm A</code>. Ejemplo: <code>11:00 PM</code>.</p> </li> 
        <li> <p><strong>[!UICONTROL Días de la semana]</strong> </p> <p>Días: seleccione los días de la semana en los que desea que se ejecute el escenario. Puede seleccionar uno o más días.</p> <p>Hora: introduzca la hora a la que desea que se ejecute el escenario en los días seleccionados. Usar el formato <code>h:mm A</code>. Ejemplo: <code>11:00 PM</code></p> </li> 
        <li> <p><strong>[!UICONTROL Días del mes]</strong> </p> <p>Días: seleccione los días del mes en que desea que se ejecute el escenario. Puede seleccionar uno o más días.</p> <p>Hora: introduzca la hora a la que desea que se ejecute el escenario en los días seleccionados. Usar el formato <code>h:mm A</code>. Ejemplo: <code>11:00 PM</code></p> </li> 
        <li> <p><strong>[!UICONTROL Fechas especificadas]</strong> </p> <p>Meses: seleccione los meses en los que desea ejecutar el escenario. Puede seleccionar uno o más meses.</p> <p>Días: seleccione los días del mes en que desea que se ejecute el escenario. Puede seleccionar uno o más días.</p> <p>Hora: introduzca la hora a la que desea que se ejecute el escenario en los días seleccionados. Usar el formato <code>h:mm A</code>. Ejemplo: <code>11:00 PM</code></p> </li> 
       </ul> <p>Nota: Debe existir una fecha para que un escenario se ejecute en esa fecha. Por ejemplo, un escenario programado solo para el 31 del mes no se ejecutará en febrero, abril, junio, septiembre o noviembre, porque esos meses no tienen un día 31.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Programación avanzada]</td> 
      <td>Puede definir intervalos de tiempo específicos durante los cuales se ejecutará el escenario. Puede especificar intervalos de hora del día, días laborables o meses. Para cada intervalo, haga clic en <strong>[!UICONTROL Agregar]</strong> y rellene los campos como se describe en el campo [!UICONTROL Ejecutar escenario].</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Start]</td> 
      <td>Escriba la fecha y la hora después de las cuales desea que se ejecute el escenario. Usar el formato <code>MM/DD/YYYY h:mm A</code>. Ejemplo: <code>06/25/2019 11:00 PM</code>.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Fin]</td> 
      <td>Escriba la fecha y la hora antes de las cuales desea que se ejecute el escenario. Usar el formato <code>MM/DD/YYYY h:mm A</code>. Ejemplo: <code>06/25/2019 11:00 PM</code>.</td> 
     </tr> 
    </tbody> 
   </table>

1. Haga clic en **[!UICONTROL Aceptar]** para guardar la configuración de programación y volver al escenario.
