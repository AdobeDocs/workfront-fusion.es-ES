---
content-type: reference
title: Directivas para la gestión de errores
description: En este artículo se describen las directivas que puede utilizar para la gestión de errores en los casos de Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: d7b0141f-d99d-4ab7-a60f-ed552a76f05d
source-git-commit: a871a130a1ac023dcb4ce8da7241918da2431d3a
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 42%

---

# Directivas para la gestión de errores

Las directivas de gestión de errores permiten elegir lo que ocurre cuando un escenario encuentra un error.

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

## Directivas para la gestión de errores

Las siguientes directivas de gestión de errores están disponibles en Workfront Fusion.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>Reversión</p> <p> <img src="assets/rollback.png"> </p> </td> 
   <td> <ul><li><p>La ejecución del escenario se detiene inmediatamente.</li><li>Se inicia una fase de Rollback en todos los módulos, en un intento de revertirlos todos a su estado inicial. </li><li>Los módulos posteriores no se procesan.</p></li><li> <p>En la mayoría de los casos, el escenario se desactiva después del número de errores consecutivos especificados en Configuración del escenario. Para obtener más información, consulte <a href="/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#number-of-consecutive-errors" class="MCXref xref">Número de errores consecutivos</a>.</p> </li><li><p>El estado de ejecución del escenario se marca como "Error".</p></li></ul> <p><b>Nota</b>: Este es el comportamiento predeterminado si no hay ninguna ruta de controlador de error adjunta al módulo y la opción <a href="/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#allow-storing-incomplete-executions" class="MCXref xref">Permitir el almacenamiento de ejecuciones incompletas</a>Permitir el almacenamiento de ejecuciones incompletas en [!UICONTROL Configuración de escenario] no está activada.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Confirmar</p> <p> <img src="assets/commit.png"> </p> </td> 
   <td> <ul><li><p>La ejecución del escenario se detiene inmediatamente.</li><li>Se inicia una fase de confirmación en todos los módulos. </li><li>Los módulos posteriores no se procesan.</p></li><li> <p>Los paquetes sin procesar se ignoran.</p> </li><li><p>El estado de ejecución del escenario se marca como “éxito”. </p> </li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Reanudar</p> <p> <img src="assets/resume.png"> </p> </td> 
   <td> <ul><li><p>Se especifica una salida sustitutiva que se suministra al módulo que encuentra un error.</p> </li><li><p>Se procesan los módulos posteriores.</p></li><li> <p>El estado de ejecución del escenario se marca como “éxito”.</p></li></ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Ignorar</p> <p> <img src="assets/ignore.png"> </p> </td> 
   <td><ul><li> <p>Se ignora el error.</li><li> Los módulos posteriores no se procesan.</p> </li><li><p>Si hay paquetes sin procesar, la ejecución del escenario continúa con normalidad.</p> </li><li><p>El estado de ejecución del escenario se marca como “éxito”.</p> </li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Salto</p> <p> <img src="assets/break.png"> </p> </td> 
   <td><ul><li> <p>El estado de la ejecución del escenario se almacena en la cola de ejecuciones incompletas, donde el error se puede resolver manualmente. Para obtener más información, vea <a href="/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md" class="MCXref xref">Ver y resolver ejecuciones incompletas</a>.</p> <p>Sin embargo, hay algunas excepciones. Para obtener más información, vea <a href="/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#allow" class="MCXref xref">Permitir el almacenamiento de ejecuciones incompletas</a> en el artículo Configurar opciones de escenario</a>.</p></li><li> <p>Los módulos posteriores no se procesan.</p></li><li> <p>Si hay paquetes sin procesar, la ejecución del escenario continúa con normalidad.</p> </li><li><p>El estado de ejecución del escenario se marca como “advertencia” cuando la opción [!UICONTROL Automatically complete execution] está deshabilitada.</p></li></ul> <p>Para obtener más información, consulte la sección <a href="#break" class="MCXref xref">[!UICONTROL Break]</a> en este artículo</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Reintentar</p> <p> <img src="assets/retry.png"> </p> </td> 
   <td> <p>En algunos casos, puede resultar útil volver a ejecutar un módulo fallido cuando existe la posibilidad de que el motivo del error pueda pasar con el tiempo.</p> <p>Actualmente, Workfront Fusion no ofrece la directiva Reintentar, aunque se pueden emplear varias soluciones alternativas que imitan su funcionalidad. Para obtener más información, consulte <a href="/help/workfront-fusion/create-scenarios/config-error-handling/retry.md" class="MCXref xref">Reintentar la administración de errores</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>* Las directivas de control de errores no se pueden usar fuera de una ruta de control de errores.
>* Workfront Fusion actualmente no ofrece un módulo de lanzamiento que le permita generar fácilmente errores condicionalmente (lanzamiento), aunque se puede emplear una solución para imitar su funcionalidad.
>
>  Para obtener más información, consulte [Configurar la solución de error `throw`](/help/workfront-fusion/create-scenarios/config-error-handling/throw.md).

## Recursos

* Para obtener información sobre la reversión y la fase de reversión, consulte [Reversión](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md#rollback) en el artículo Ejecución de escenarios, ciclos y fases.
* Para obtener información sobre la fase de confirmación, consulte [confirmación](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md#commit) en el artículo Ejecución de escenarios, ciclos y fases.
