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
source-git-commit: b800142d824927e5765eed50a831731e6b5d9925
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 19%
---
# Grupos de trabajo

Un grupo de trabajo es una cantidad de recursos de procesamiento de Workfront Fusion dedicados a una organización específica. Todas las operaciones y el procesamiento de Fusion se realizan en el contexto del grupo de trabajadores asignado de una organización.

Los grupos de trabajo permiten que sus escenarios se ejecuten de manera más eficiente y eliminan las posibilidades de competir con otras organizaciones por la capacidad de procesamiento de Fusion.

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

## Resumen del grupo de trabajo

Un grupo de trabajo es una forma de procesar ejecuciones de escenarios en paralelo. Cada grupo de trabajadores está asociado con:

* Un número de trabajadores.
* Una cola de ejecución.

Cuando se ejecuta un escenario, pasa a la cola de ejecución del grupo de trabajo. Los trabajadores del grupo extraen continuamente tareas del grupo de ejecución y las procesan en paralelo.

Si la profundidad de la cola de ejecución aumenta y se utilizan todos los trabajadores existentes, Workfront Fusion escala automáticamente el grupo añadiendo más trabajadores. Esta escala es dinámica y está impulsada por eventos, lo que significa que la capacidad precisa o se contrae en función de la carga en tiempo real sin que su organización ni usted realicen ninguna acción.

El equipo de Workfront Fusion supervisa continuamente el uso y el comportamiento de escalado de los grupos y puede revisar los umbrales o patrones para garantizar un rendimiento coherente a medida que aumenta el uso.

## Cambiar nombre de grupo de trabajo

Los propietarios y administradores de la organización pueden cambiar el nombre de los grupos de trabajo asignados a su organización. Cada grupo muestra un nombre generado por el sistema de forma predeterminada. Puede asignar a un grupo de servidores un nombre personalizado, como `Marketing EU` o `High-volume integrations`, y cambiarlo siempre que lo necesite.

Al cambiar el nombre de un grupo solo cambia su etiqueta. Los escenarios, las ejecuciones y la capacidad del grupo no se ven afectados. El nuevo nombre aparece siempre que se muestra el grupo, como cuando asigna escenarios a un grupo.

>[!NOTE]
>
>La ficha **[!UICONTROL Grupos de trabajo]** solo aparece cuando hay más de un grupo de trabajo asignado a su organización. Si su organización tiene un solo grupo de trabajo o utiliza el grupo compartido, no verá la pestaña.

Para cambiar el nombre de un grupo de trabajo:

1. En el panel de navegación de la izquierda, haga clic en **Resumen de organización**
1. Haga clic en la ficha **[!UICONTROL Grupos de trabajo]**, cerca de la parte superior de la página.

   La pestaña enumera cada grupo y muestra cuántos escenarios se le asignan.

1. Haga clic en **[!UICONTROL Cambiar nombre]** junto al grupo al que desee cambiar el nombre.
1. En el panel que se abre, introduzca el nuevo nombre.
1. Haga clic en **Guardar**.
