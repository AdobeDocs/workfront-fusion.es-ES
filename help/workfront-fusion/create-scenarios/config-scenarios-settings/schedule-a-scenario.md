---
content-type: reference
title: Programar un escenario
description: De forma predeterminada, un escenario se ejecuta cada 15 minutos. Puede cambiar esto definiendo cuándo y con qué frecuencia se ejecuta un escenario activado. Los escenarios de fusión pueden programarse para que se ejecuten incluso cada 5 minutos.
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 9b74af0d-e7ff-4bf5-974e-0651d0d51f71
TQID: https://experienceleague.adobe.com/jWWR3vbD-ShhjTws5p3Gx24C2YfL-qYKHXyssnR-dFM
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 575
ht-degree: 34%

---

# Programar un escenario

De forma predeterminada, un escenario se ejecuta cada 15 minutos. Puede cambiar esto definiendo cuándo y con qué frecuencia se ejecuta un escenario activado. Los escenarios de fusión pueden programarse para que se ejecuten incluso cada 5 minutos.

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
        <li> <p><strong>[!UICONTROL Una Vez]</strong> </p> <p>Escriba la fecha y la hora en que desea que se ejecute el escenario. Use el formato <code>MM/DD/YYYY h:mm A</code>. Ejemplo: <code>06/25/2019 11:00 PM</code>.</p> </li> 
        <li> <p><strong>[!UICONTROL Todos los días]</strong> </p> <p>Introduzca la hora a la que desea que se ejecute el escenario. Use el formato <code>h:mm A</code>. Ejemplo: <code>11:00 PM</code>.</p> </li> 
        <li> <p><strong>[!UICONTROL Días de la semana]</strong> </p> <p>Días: seleccione los días de la semana en los que desea que se ejecute el escenario. Puede seleccionar uno o más días.</p> <p>Hora: introduzca la hora a la que desea que se ejecute el escenario en los días seleccionados. Use el formato <code>h:mm A</code>. Ejemplo: <code>11:00 PM</code></p> </li> 
        <li> <p><strong>[!UICONTROL Días del mes]</strong> </p> <p>Días: seleccione los días del mes en que desea que se ejecute el escenario. Puede seleccionar uno o más días.</p> <p>Hora: introduzca la hora a la que desea que se ejecute el escenario en los días seleccionados. Use el formato <code>h:mm A</code>. Ejemplo: <code>11:00 PM</code></p> </li> 
        <li> <p><strong>[!UICONTROL Fechas especificadas]</strong> </p> <p>Meses: seleccione los meses en los que desea ejecutar el escenario. Puede seleccionar uno o más meses.</p> <p>Días: seleccione los días del mes en que desea que se ejecute el escenario. Puede seleccionar uno o más días.</p> <p>Hora: introduzca la hora a la que desea que se ejecute el escenario en los días seleccionados. Use el formato <code>h:mm A</code>. Ejemplo: <code>11:00 PM</code></p> </li> 
       </ul> <p>Nota: Debe existir una fecha para que un escenario se ejecute en esa fecha. Por ejemplo, un escenario programado solo para el 31 del mes no se ejecutará en febrero, abril, junio, septiembre o noviembre, porque esos meses no tienen un día 31.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Programación avanzada]</td> 
      <td>Puede definir intervalos de tiempo específicos durante los cuales se ejecutará el escenario. Puede especificar intervalos de hora del día, días laborables o meses. Para cada intervalo, haga clic en <strong>[!UICONTROL Agregar]</strong> y rellene los campos como se describe en el campo [!UICONTROL Ejecutar escenario].</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Start]</td> 
      <td>Escriba la fecha y la hora después de las cuales desea que se ejecute el escenario. Use el formato <code>MM/DD/YYYY h:mm A</code>. Ejemplo: <code>06/25/2019 11:00 PM</code>.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Fin]</td> 
      <td>Escriba la fecha y la hora antes de las cuales desea que se ejecute el escenario. Use el formato <code>MM/DD/YYYY h:mm A</code>. Ejemplo: <code>06/25/2019 11:00 PM</code>.</td> 
     </tr> 
    </tbody> 
   </table>

1. Haga clic en **[!UICONTROL Aceptar]** para guardar la configuración de programación y volver al escenario.
