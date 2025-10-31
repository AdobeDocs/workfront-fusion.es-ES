---
title: Ejecutar el experto en puntuación de escenarios
description: El experto en puntuación de escenarios puede ayudarle a garantizar que su escenario se configura de una manera que siga las prácticas recomendadas. Comprueba el escenario y ofrece recomendaciones para su estructura y organización.
author: Becky
feature: Workfront Fusion
exl-id: b668e7f6-dac5-4ac9-b3f3-109f70eaa2c4
source-git-commit: 42be02d6a59a5d7b8faccdcfe40e8b967153c6eb
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 6%

---

# Ejecutar el experto en puntuación de escenarios

>[!IMPORTANT]
>
>El experto en puntuación de escenarios se ha desactivado temporalmente.

El experto en puntuación de escenarios puede ayudarle a garantizar que su escenario se configura de una manera que siga las prácticas recomendadas. Comprueba el escenario y ofrece recomendaciones para su estructura y organización.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront</td> 
   <td> <p>Cualquier paquete de flujo de trabajo de Adobe Workfront y cualquier paquete de integración y automatización de Adobe Workfront</p><p>Workfront Ultimate</p><p>Paquetes Workfront Prime y Select, con una compra adicional de Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencias de Adobe Workfront</td> 
   <td> <p>Estándar</p><p>Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete Select o Prime Workfront que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Ejecutar el experto en puntuación de escenarios

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que quiere ejecutar el Experto en puntuación de escenarios.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haga clic en el icono de Scenario Scoring Expert ![Experto en puntuación de escenario](assets/scoring-expert-icon.png) cerca de la parte inferior de la pantalla.

   Se abrirá el panel Experto en puntuación de escenarios.
1. Haga clic en **Evaluar**.

El experto en puntuación de escenarios devuelve una puntuación de 10 y muestra qué comprobaciones han pasado o fallado. Si una comprobación ha fallado, el experto en puntuación de escenarios ofrece recomendaciones para asegurarse de que el escenario cumpla estas comprobaciones.

![Puntuación de escenario](assets/scenario-score.png)

## Comprobaciones de puntuación de escenario

El experto en puntuación de escenarios utiliza las siguientes comprobaciones:

* El escenario debe llamarse.
* Todos los módulos deben estar etiquetados.
* El escenario debe ejecutarse en una programación establecida.

  Para obtener instrucciones, consulte [Programar un escenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md).
* El tamaño del modelo de escenario debe ser inferior a 5 MB.

  Para obtener más información, consulte [Protecciones de rendimiento de Fusion](/help/workfront-fusion/references/scenarios/fusion-performance-guardrails.md#scenarios).
* Si se utiliza un módulo de déclencheur instantáneo de Workfront, debe filtrarse.

  Para obtener instrucciones, consulte [Filtros de suscripción de eventos en el módulo Workfront > [!UICONTROL Ver eventos]](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#event-subscription-filters-in-the-workfront--watch-events-modules).
