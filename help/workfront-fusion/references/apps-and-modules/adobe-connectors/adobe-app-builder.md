---
title: Módulo App Builder de Adobe
description: El conector App Builder de Adobe le permite utilizar funciones personalizadas en sus escenarios.
author: Becky
feature: Workfront Fusion
source-git-commit: 8250d4fdad8ed7ffe63cd003f6e0cb325cbbfa8d
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 31%

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

## Módulo App Builder de Adobe

El único módulo de Adobe App Builder disponible actualmente es Ejecutar una acción, que le permite utilizar una función de JavaScript personalizada previamente configurada.

Para obtener instrucciones sobre cómo configurar una función personalizada, vea [Asignar datos mediante funciones personalizadas](/help/workfront-fusion/create-scenarios/map-data/map-using-custom-functions.md).

### Ejecutar una acción

Este módulo ejecuta una función personalizada previamente configurada.

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


