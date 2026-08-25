---
title: Movimiento de módulos a una cadena
description: Puede seleccionar un grupo de módulos en un escenario y moverlos a un nuevo escenario encadenado, sin volver a crear manualmente asignaciones o estructuras de datos.
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: f1a80f64edc410ae76bfbba1280df7232e2d09c5
workflow-type: tm+mt
source-wordcount: 513
ht-degree: 17%

---

# Movimiento de módulos a una cadena

>[!IMPORTANT]
>
>Esta función se encuentra en Beta y no se recomienda para flujos de trabajo de producción esenciales. Como función de Beta, el comportamiento puede cambiar y es posible que los casos extremos no se gestionen completamente.

Puede seleccionar un grupo de módulos en un escenario y moverlos a un nuevo escenario encadenado, sin volver a crear manualmente asignaciones o estructuras de datos. Esto proporciona una manera fácil de modular los escenarios grandes.

Cuando mueve un grupo de módulos a una cadena, Workfront Fusion:

* Mueve los módulos seleccionados a un escenario recién creado.
* Abre el nuevo escenario en una ventana independiente del explorador.
* Reemplaza los módulos seleccionados en el escenario original con un módulo Chain > Call a child scenario.
* Crea automáticamente las estructuras de datos de entrada y salida necesarias para el nuevo escenario secundario.
* Conserva el comportamiento del escenario existente, de modo que el escenario sigue ejecutándose del mismo modo que antes de que se movieran los módulos.
* Actualiza automáticamente las asignaciones:
  * Los módulos trasladados al escenario secundario reciben datos a través de la cadena > Recibir datos de las entradas del módulo principal.
  * Las salidas del escenario secundario se exponen automáticamente de nuevo al escenario principal.
  * Las asignaciones existentes en el modelo se ajustan para coincidir con la nueva estructura.

Para obtener información sobre cómo planificar escenarios encadenados, vea [Encadenar varios escenarios](/help/workfront-fusion/create-scenarios/plan-a-scenario/chain-scenarios.md).

Para obtener instrucciones sobre la configuración de módulos de cadena, consulte [Módulos de cadena](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/chain-modules.md).

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

## Requisitos previos

Los módulos que desea mover a una cadena ya deben existir en un escenario y debe seleccionar más de un módulo.

## Limitaciones

No se puede mover una selección de módulos a una cadena en las situaciones siguientes:

* Los módulos seleccionados no forman parte de un solo flujo ininterrumpido. Por ejemplo, no puede seleccionar módulos de dos rutas diferentes sin conexión al mismo tiempo.
* La selección incluye un módulo webhook.
* La selección incluye otro módulo Chain.
* La selección incluye un módulo Enrutador y no ha seleccionado todas las rutas de ese enrutador.
* Un módulo seleccionado tiene una ruta de gestión de errores y no ha seleccionado también esa ruta.

## Mover módulos a una cadena

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario que contiene los módulos que desea mover.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Seleccione los módulos que desea mover a una cadena manteniendo presionada la tecla [!UICONTROL Mayús] y haciendo clic en los módulos que desea mover.
1. Haga clic con el botón derecho en uno de los módulos seleccionados.
1. Seleccione **[!UICONTROL Mover a cadena]**.
