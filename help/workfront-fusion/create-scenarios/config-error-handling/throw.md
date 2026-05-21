---
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: errors
title: Configurar la solución de emisión de error
description: En algunos casos, es posible que desee detener forzosamente la ejecución del escenario seguida de la fase Revertir o Confirmar, o bien detener el procesamiento de una ruta, almacenarla opcionalmente en la cola de Ver y resolver las ejecuciones incompletas en Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 4bf2a6c7-16b2-4545-9adf-be3947a7017d
TQID: https://experienceleague.adobe.com/zdEDHRJhIt8dc4Ql835IDypV-CM3YRT5w41mjGDVpSE
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 367
ht-degree: 43%

---

# Solución alternativa al error `throw`

En algunos casos, es posible que desee detener a la fuerza la ejecución del escenario seguida de la fase Rollback o Commit, o detener el procesamiento de una ruta y, opcionalmente, almacenarla en la cola de ejecuciones incompletas.

En la actualidad, las directivas de gestión de errores no se pueden utilizar fuera del ámbito de una ruta de gestión de errores y Adobe Workfront Fusion no ofrece un módulo que le permita generar (arrojar) errores de forma fácil y condicional.

Puede utilizar la siguiente solución para imitar la funcionalidad de error `throw`.

Para obtener información sobre las ejecuciones incompletas, consulte [Ver y resolver ejecuciones incompletas en Adobe Workfront Fusion](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md).

Para obtener información sobre las directivas de gestión de errores, consulte [Directivas para la gestión de errores en Adobe Workfront Fusion](/help/workfront-fusion/references/errors/directives-for-error-handling.md).

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
