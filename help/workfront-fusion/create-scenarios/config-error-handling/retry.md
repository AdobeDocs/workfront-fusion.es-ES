---
title: Configurar la solución de reintento de administración de errores
description: A veces, resulta útil volver a ejecutar un módulo que falla si existe la posibilidad de que el motivo del error se resuelva rápidamente.
author: Becky
feature: Workfront Fusion
exl-id: 08e19a1a-7ca9-4c79-a165-f200048a5cda
source-git-commit: b2ca63ca5af26ee79758798118817b55113b3bd0
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 3%

---

# Configurar solución de gestión de errores `retry`

A veces, resulta útil volver a ejecutar un módulo que falla si existe la posibilidad de que el motivo del error se resuelva rápidamente.

Adobe Workfront Fusion no ofrece actualmente la directiva de gestión de errores `retry`, pero hay dos soluciones disponibles para imitar la funcionalidad `retry`.

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

## Soluciones a la directiva de gestión de errores [!UICONTROL Retry]

Workfront Fusion no ofrece actualmente la directiva de gestión de errores `retry`. Utilice una de las siguientes soluciones para imitar la funcionalidad de reintentos.

Para obtener instrucciones, consulte [Directivas para la administración de errores](/help/workfront-fusion/references/errors/directives-for-error-handling.md).

* [Usar la directiva Break](#use-the-break-directive)
* [Uso del módulo Repetidor](#use-the-repeater-module)

### Usar la directiva Break

Cuando se ejecuta la directiva Break, el estado de la ejecución del escenario se almacena en la cola de ejecuciones incompletas. Si esto sucede, puede resolver la ejecución incompleta manualmente.

Para obtener instrucciones, consulte [Resolver errores administrados por la directiva Break](/help/workfront-fusion/create-scenarios/config-error-handling/resolve-error-from-break-directive.md)

Para obtener instrucciones sobre cómo resolver ejecuciones incompletas, vea [Ver y resolver ejecuciones incompletas](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md).

#### Inconvenientes

* El intervalo mínimo de reintento es de un minuto.
* Si el módulo procesa varios paquetes y falla el procesamiento de un paquete, la ejecución parcial (solo el paquete que provocó el error) se mueve a la carpeta de ejecuciones incompletas y se programa para reintentos según la configuración de la directiva [!UICONTROL Break]. Sin embargo, la ejecución actual continúa y el módulo continúa procesando los paquetes posteriores.

  Para evitar que el escenario se vuelva a ejecutar hasta que la ejecución almacenada en la carpeta de ejecuciones incompletas se haya resuelto correctamente, habilite la opción &quot;[!UICONTROL Procesamiento secuencial]&quot; en [!UICONTROL Configuración del escenario].

Para obtener más información sobre las ejecuciones incompletas, vea [Ver y resolver ejecuciones incompletas](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md).

### Uso del módulo Repetidor

La solución del módulo Repetidor es más compleja, pero más personalizable.

#### Configuración de la ruta del controlador de error

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea agregar la solución.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haga clic en el icono **Control de flujo** ![Control de flujo](assets/flow-control-icon.png) y seleccione **Repetidor**.
1. En el módulo Repetidor, establezca el campo **[!UICONTROL Repeticiones]** al número máximo de veces que desea que el escenario se reintente.
1. Adjunte el módulo que podría fallar después del módulo **[!UICONTROL Repeater]**.
1. Adjunte una ruta de controlador de error al módulo que podría fallar.

   Para obtener instrucciones, consulte [Agregar administración de errores](/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md).
1. Agregue el módulo **[!UICONTROL Tools] > [!UICONTROL Sleep]** a la ruta del controlador de errores y establezca su campo **[!UICONTROL Delay]** en el número de segundos entre reintentos.

1. Agregue la directiva **[!UICONTROL Ignore]** después del módulo **[!UICONTROL Tools] > [!UICONTROL Sleep]**.
1. Continúe con [Configurar la ruta predeterminada](#configure-the-default-route).

#### Configuración de la ruta predeterminada

1. Agregue el módulo **[!UICONTROL Tools] > [!UICONTROL Set variable]** en una ruta independiente (que no sea de controlador de error) después del módulo que podría dar error y configúrelo para almacenar el resultado del módulo en una variable denominada, como `Result`.

1. Agregue el módulo **[!UICONTROL Array aggregator]** después del módulo **[!UICONTROL Tools] > [!UICONTROL Set variable]** y seleccione el módulo **[!DNL Repeater]** en el campo Source Module.

1. Agregue el módulo **[!UICONTROL Tools] > [!UICONTROL Get variable]** después del módulo **[!UICONTROL Array aggregator]** y asígnele el valor de la variable `Result`.

1. Inserte el módulo **[!UICONTROL Tools] > [!UICONTROL Get variable]** entre el módulo **[!UICONTROL Repeater]** y el módulo que podría fallar, y asígnele el valor de la variable `Result`.

1. Inserte un filtro entre este módulo **[!UICONTROL Tools] > [!UICONTROL Get variable]** y el módulo que podría dar error para continuar solo si la variable `Result` no existe.

>[!BEGINSHADEBOX]

**Ejemplo:**

En este escenario de ejemplo, el módulo [!UICONTROL HTTP] > [!UICONTROL Realizar una solicitud] representa el módulo que podría fallar:

![HTTP realiza una solicitud](assets/http-make-request.png)

>[!ENDSHADEBOX]

Si el resultado del módulo que puede dar error es demasiado complejo para almacenarlo en una variable simple, puede utilizar un almacén de datos para almacenar y recuperar el resultado. El almacén de datos contendría un solo registro. La clave del registro puede ser, por ejemplo, `Result`.

Para obtener más información sobre los almacenes de datos, consulte [Almacenes de datos](/help/workfront-fusion/create-scenarios/map-data/data-stores.md).

#### Inconvenientes

* Esta solución es más compleja.
* Esta solución utiliza más operaciones.

## Recursos

* Para obtener más información sobre los módulos del repetidor y las directivas de interrupción, consulte [Control de flujo](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/flow-control.md).
* Para obtener más información sobre los módulos Obtener variable, consulte [Herramientas](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/tools-modules.md).
