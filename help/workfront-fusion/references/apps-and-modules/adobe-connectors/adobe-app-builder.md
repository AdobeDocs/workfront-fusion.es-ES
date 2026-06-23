---
title: Módulo App Builder de Adobe
description: El conector App Builder de Adobe le permite utilizar funciones personalizadas en sus escenarios.
author: Becky
feature: Workfront Fusion
exl-id: 92661a0c-436b-4fbd-808a-a4fbe3cd2339
source-git-commit: 4392b9d13c49d3d64b2b694bf23cfc227ae36d02
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 26%

---

# Módulo App Builder de Adobe

Puede crear funciones personalizadas en el área Funciones de Fusion. A continuación, agregue estas funciones a sus escenarios en forma de módulo de Adobe App Builder.

Dado que las funciones personalizadas funcionan a través de Adobe App Builder, su organización debe tener una licencia de Adobe App Builder para utilizarlas.

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
   <p><ul><li>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li><li>Debe tener una licencia de Adobe App Builder para utilizar funciones personalizadas.</ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Módulos de Adobe App Builder

### Ejecutar un bloque de código personalizado

Este módulo le permite ejecutar un bloque de código. El bloque de código se configura al configurar el módulo y se ejecuta cuando el módulo se ejecuta durante la ejecución de un escenario.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Seleccione la conexión que contiene la función personalizada que desea ejecutar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bloque de código]</td> 
   <td>Escriba el bloque de código que desea que ejecute el módulo.<p>Para dar formato al código para facilitar la lectura, haga clic en el icono <b>Formato del código</b>.</td> 
  </tr> 
   </tbody> 
</table>

### Ejecutar una función personalizada

Este módulo le permite utilizar una función personalizada de JavaScript previamente configurada y almacenada en el área Funciones.

Para obtener instrucciones sobre cómo configurar una función personalizada, vea [Asignar datos mediante funciones personalizadas](/help/workfront-fusion/create-scenarios/map-data/map-using-custom-functions.md).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Seleccione la conexión que contiene la función personalizada que desea ejecutar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Action]</td> 
   <td>Seleccione la función personalizada que desea ejecutar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Parámetros] </td> 
   <td>Introduzca los valores de los parámetros de función. Los parámetros disponibles se basan en los parámetros configurados cuando se creó la función.<p>Si un parámetro tiene un valor predeterminado, no lo verá en el campo, pero puede anularlo introduciendo o asignando un valor en el campo.</p></td> 
  </tr> 
   </tbody> 
</table>
