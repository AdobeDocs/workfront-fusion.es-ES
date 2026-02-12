---
title: Grupos de trabajo
description: Un grupo de trabajo es una cantidad de recursos de procesamiento de Workfront Fusion dedicados a una o más organizaciones específicas. Todas las operaciones y el procesamiento de Fusion se realizan en el contexto del grupo de trabajadores asignado de una organización.
author: Becky
feature: Workfront Fusion
source-git-commit: bb94083eb9f58dc3ae9f94a59288da43317b567b
workflow-type: tm+mt
source-wordcount: '217'
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
