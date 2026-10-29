---
title: Buscar y reemplazar variables, orígenes y conexiones en un escenario
description: Utilice Buscar y reemplazar para reemplazar una variable asignada, reasignar referencias de un módulo de origen a otro o copiar una conexión a otros módulos de su escenario.
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
source-git-commit: 94449f8511d7480f1a4fc0ac6e8db9b067977abd
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 15%
---

# Buscar y reemplazar variables, orígenes y conexiones en un escenario

>[!NOTE]
>
>Esta funcionalidad solo está disponible en la nueva experiencia del editor de escenarios. Para obtener más información, consulte [Experiencias nuevas y clásicas](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md#new-and-classic-experiences) en el artículo Editor de escenarios.

Buscar y reemplazar permite realizar el mismo cambio en varios módulos a la vez. Puede:

* Reemplace una variable asignada en todo el escenario o en un módulo.
* Reasignar referencias de un módulo de origen a otro.
* Copie una conexión a uno o todos los módulos compatibles de la misma aplicación.

Antes de realizar un cambio, Buscar y reemplazar muestra una vista previa de los módulos que se verán afectados.

En la experiencia clásica, puede utilizar las herramientas de conexión Swap variable, Remap source y Swap en DevTool para realizar estas tareas. Para obtener más información, vea [Depurar un escenario](/help/workfront-fusion/manage-scenarios/debug-a-scenario.md).

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

## Abrir Buscar y reemplazar

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea realizar los cambios.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haz clic en el icono **Buscar y reemplazar** ![Buscar y reemplazar](assets/find-replace-icon.png) en el área de Controles.

   Es posible que tenga que hacer clic en el icono de tres puntos del área Controles para ver el icono Buscar y reemplazar.

Busque y reemplace las aperturas en el panel situado en el lado derecho del lienzo.

## Reemplazar una variable

Utilice la ficha **Variable** para reemplazar una variable asignada.

1. Abra Buscar y reemplazar y, a continuación, haga clic en la ficha **Variable**.
1. En el campo Variable que buscar, pegue la variable que desee reemplazar.
1. En el campo Reemplazar con, pegue la variable que reemplazará a la variable anterior.
1. En el campo Módulo, elija el módulo al que se aplicará el cambio o seleccione **Todo el escenario** para aplicar el cambio a todos los módulos afectados en el escenario.
1. Haga clic en **Reemplazar**
1. Revise la vista previa de los módulos que se verán afectados. Para ir a un módulo en el lienzo, seleccione su fila en la vista previa.
1. Haga clic en **Aplicar**.

## Reasignación de un origen

Utilice la ficha **Source** para cambiar a qué módulo se refieren las asignaciones de otros módulos.

1. Abra Buscar y reemplazar y haga clic en la ficha **Source**.
1. En el campo Source module, seleccione el módulo de origen al que hacen referencia actualmente las asignaciones.
1. En los campos del módulo de Target, seleccione el módulo al que deben hacer referencia.
1. En el campo Módulo, elija el módulo al que se aplicará el cambio o seleccione **Todo el escenario** para aplicar el cambio a todos los módulos afectados en el escenario.
1. Haga clic en **Reemplazar**
1. Revise la vista previa de los módulos que se verán afectados. Para ir a un módulo en el lienzo, seleccione su fila en la vista previa.
1. Haga clic en **Aplicar**.

## Copia de una conexión a otros módulos

Use la ficha **Conexión** para usar la misma conexión en más de un módulo de la misma aplicación.

1. Abra Buscar y reemplazar y, a continuación, haga clic en la ficha **Conexión**.
1. En el campo Conexión desde, seleccione un módulo que tenga actualmente la conexión que desee utilizar para otros módulos.
1. En el campo Aplicar a, elija el módulo al que se aplicará el cambio o si se aplicará el cambio a todos los módulos compatibles del escenario.
1. Haga clic en **Aplicar**.
