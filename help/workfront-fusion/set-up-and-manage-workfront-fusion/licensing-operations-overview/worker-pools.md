---
title: Grupos de trabajo
description: Un grupo de trabajo es una cantidad de recursos de procesamiento de Workfront Fusion dedicados a una o más organizaciones específicas. Todas las operaciones y el procesamiento de Fusion se realizan en el contexto del grupo de trabajadores asignado de una organización.
author: Becky
feature: Workfront Fusion
exl-id: 8bf508a8-d1f9-455f-af89-62f688289137
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: 01689332f97c15b317e686d11a27cb4dc7e2e8bd
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%
---
# Grupos de trabajo

Un grupo de trabajo es una cantidad de recursos de procesamiento de Workfront Fusion dedicados a una organización específica. Todas las operaciones y el procesamiento de Fusion se realizan en el contexto del grupo de trabajadores asignado de una organización.

Los grupos de trabajo permiten que sus escenarios se ejecuten de manera más eficiente y eliminan las posibilidades de competir con otras organizaciones por la capacidad de procesamiento de Fusion.

## Resumen del grupo de trabajo

Un grupo de trabajo es una forma de procesar ejecuciones de escenarios en paralelo. Cada grupo de trabajadores está asociado con:

* Un número de trabajadores.
* Una cola de ejecución.

Cuando se ejecuta un escenario, pasa a la cola de ejecución del grupo de trabajo. Los trabajadores del grupo extraen continuamente tareas del grupo de ejecución y las procesan en paralelo.

Si la profundidad de la cola de ejecución aumenta y se utilizan todos los trabajadores existentes, Workfront Fusion escala automáticamente el grupo añadiendo más trabajadores. Esta escala es dinámica y está impulsada por eventos, lo que significa que la capacidad precisa o se contrae en función de la carga en tiempo real sin que su organización ni usted realicen ninguna acción.

El equipo de Workfront Fusion supervisa continuamente el uso y el comportamiento de escalado de los grupos y puede revisar los umbrales o patrones para garantizar un rendimiento coherente a medida que aumenta el uso.
