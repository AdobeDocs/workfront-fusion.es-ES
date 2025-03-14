---
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: errors
title: Configurar la solución del error de lanzamiento
description: En algunos casos, es posible que desee detener forzosamente la ejecución del escenario seguida de la fase Revertir o Confirmar, o bien detener el procesamiento de una ruta, almacenarla opcionalmente en la cola de Ver y resolver las ejecuciones incompletas en Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 4bf2a6c7-16b2-4545-9adf-be3947a7017d
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 38%

---

# Solución alternativa al error `throw`

En algunos casos, es posible que desee detener a la fuerza la ejecución del escenario seguida de la fase Rollback o Commit, o detener el procesamiento de una ruta y, opcionalmente, almacenarla en la cola de ejecuciones incompletas.

En la actualidad, las directivas de gestión de errores no se pueden utilizar fuera del ámbito de una ruta de gestión de errores y Adobe Workfront Fusion no ofrece un módulo que le permita generar (arrojar) errores de forma fácil y condicional.

Puede utilizar la siguiente solución para imitar la funcionalidad de error `throw`.

Para obtener información sobre las ejecuciones incompletas, consulte [Ver y resolver ejecuciones incompletas en Adobe Workfront Fusion](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md).

Para obtener información sobre las directivas de control de errores, consulte [Directivas para el control de errores en  [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/references/errors/directives-for-error-handling.md).

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront 
   <td> <p>Cualquiera</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencia de Adobe Workfront</td> 
   <td> <p>Nuevo: estándar</p><p>O</p><p>Actual: Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion**</td> 
   <td>
   <p>Actual: No se requiere licencia de Workfront Fusion</p>
   <p>O</p>
   <p>Heredado: cualquiera </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Plan Select or Prime Workfront: su organización debe adquirir Adobe Workfront Fusion.</li><li>Plan Ultimate Workfront: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe adquirir Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Solución alternativa para `throw`

Para generar un error de forma condicional, puede configurar un módulo para que falle a propósito durante su funcionamiento. Una posibilidad es emplear el módulo [!UICONTROL JSON] > [!UICONTROL Analizar JSON], configurado para generar opcionalmente un error (`BundleValidationError` en este caso):

![Error JSON](assets/json-parse-json.png)

A continuación, puede adjuntar una de las directivas de gestión de errores a la ruta de gestión de errores:

* **Reversión**: Fuerza la ejecución del escenario para que se detenga y realice la fase de reversión.
* **Compromiso**: Fuerza la ejecución del escenario para que se detenga y realice la fase de confirmación.
* **Ignorar**: detiene el procesamiento de una ruta.
* **Descanso**: detiene el procesamiento de una ruta y la almacena en la cola de la carpeta de ejecuciones incompletas.

El ejemplo siguiente muestra el uso de la directiva [!DNL Rollback]:

![Directiva de reversión](assets/rollback-directive.png)
