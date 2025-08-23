---
title: Operaciones
description: Una operación en Adobe Workfront Fusion es una tarea realizada por un módulo. Para fines de seguimiento, cualquier acción correcta realizada por un módulo es una operación.
author: Becky
feature: Workfront Fusion
exl-id: c14e2bb2-1cce-48ff-8bea-acc9829d3cf2
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 74%

---

# Operaciones

Una operación en Adobe Workfront Fusion es una tarea realizada por un módulo. Para fines de seguimiento, cualquier acción correcta realizada por un módulo es una operación.

## Consideraciones al contar el número de operaciones

* En general, cualquier ejecución correcta de la etapa de acción se considera una operación.
* El primer módulo de un escenario se ejecuta solo una vez y siempre se cuenta como una operación, aunque no devuelva un paquete.
* El número de veces que se ejecuta el resto de los módulos depende del número de paquetes que deben procesar.  Una ejecución de un módulo para un paquete es una operación. Una excepción es el módulo del agregador, que se cuenta como una operación por cada conjunto de paquetes que se procesa.
* Las operaciones se cuentan en la fase [!UICONTROL Finalización] de la ejecución de un escenario.
* Los siguientes **no** se cuentan como operaciones:
   * Cualquier paso del filtro.
   * Cualquier acción que falle o se detenga.
   * Cualquier ruta que no se ejecute porque no se cumplen las reglas de la ruta, como las rutas de reserva o deshabilitadas.
   * Cualquier acción que no se ejecute, ya sea porque un filtro no ha permitido el paso de datos o porque el escenario se ha detenido debido a un error.

## Límites de operación

Es posible que su organización tenga un límite mensual de operaciones. Esto se basa en el plan de Workfront adquirido por su organización. El plan [!UICONTROL Ultimate] Workfront ofrece operaciones ilimitadas.

Si su organización tiene un límite mensual, se le notificará cuando su organización esté cerca del límite. Si su organización sobrepasa el límite, Workfront se pondrá en contacto con ella para asegurarse de que su plan satisface sus necesidades.

Workfront Fusion envía una notificación cuando su organización alcanza los siguientes porcentajes del límite mensual de la organización:

* 50 %
* 75 %
* 90 %
* 100 %

## Visualización del número de operaciones realizadas en los últimos 30 días

Se pueden ver gráficos que muestran el número de operaciones realizadas. Estos gráficos están disponibles en las siguientes ubicaciones:

* **Panel de organización**: operaciones utilizadas por toda la organización
* **Panel del equipo**: operaciones utilizadas por escenarios propiedad de este equipo
* **Página de detalles del escenario**: operaciones utilizadas por este escenario
