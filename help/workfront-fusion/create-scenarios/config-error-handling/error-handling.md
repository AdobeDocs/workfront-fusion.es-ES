---
title: Añadir gestión de errores
description: Cuando se producen errores durante la ejecución de un escenario, suele ser porque un servicio no está disponible debido a un fallo, un servicio responde con datos inesperados o falla la validación de los datos de entrada.
author: Becky
feature: Workfront Fusion
exl-id: 82ddaf73-ecf9-4fd6-8f8e-909351023c77
source-git-commit: 0668441df8405610488e3e33658635e4cc7db270
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 30%

---

# Añadir gestión de errores

Pueden producirse errores durante la ejecución de un escenario.

Por ejemplo, se puede producir un error debido a lo siguiente:

* Un servicio no está disponible debido a un error
* Un servicio responde con datos inesperados
* Error de validación de datos de entrada
* Otras razones

Si un módulo encuentra un error durante la ejecución del escenario y no hay ninguna ruta de control de errores asociada al módulo, se ejecuta la lógica de control de errores predeterminada.

Al añadir una ruta de controlador de errores a un módulo, puede reemplazar la lógica de control de errores predeterminada por la suya propia. Adobe Workfront Fusion ofrece cinco directivas diferentes que se pueden insertar al final de las rutas de gestión de errores.

Para obtener más información sobre la administración de errores predeterminada, consulte [Tipos de error](/help/workfront-fusion/references/errors/error-processing.md).

Para obtener más información acerca de las directivas de control de errores, consulte [Directivas de control de errores](/help/workfront-fusion/references/errors/directives-for-error-handling.md).

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
   <p>Actual: no se requiere licencia de Workfront Fusion.</p>
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

## Añadir un controlador de error

Para agregar un controlador de error a un módulo:

1. Haga clic en la ficha **[!UICONTROL Scenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea agregar una ruta de control de errores.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haga clic con el botón secundario en el módulo después del cual desea agregar una ruta de controlador de error y seleccione **[!UICONTROL Add error handler]**:

   ![](assets/error-handler-route.png)

   Se agrega una ruta de controlador de error al módulo. Si el módulo es el último módulo de una ruta, el controlador de errores le seguirá directamente. Si el módulo tiene más módulos después, se agrega una ruta de controlador de error independiente.

   El módulo de gestión de errores muestra una lista de directivas, así como las aplicaciones que se utilizan en su escenario.

   ![Ruta de error](assets/error-route.png)

1. Seleccione una de las directivas.

   O

   Añada uno o más módulos a la ruta del controlador de errores.

   Si agrega más módulos a la ruta, la directiva Ignore se aplica de forma predeterminada. Si hay un error, se procesan los módulos posteriores de esa ruta.

   Para obtener más información sobre directivas, consulte [Directivas de administración de errores](#error-handling-directives) en este artículo.

1. (Opcional) Añada un filtro a la ruta de gestión de errores. Para obtener instrucciones, vea [Agregar filtrado y anidamiento a rutas de control de errores](/help/workfront-fusion/create-scenarios/config-error-handling/advanced-error-handling.md).

>[!NOTE]
>
>Tenga en cuenta que una ruta del controlador de errores está compuesta por círculos transparentes, mientras que una ruta normal está compuesta por círculos sólidos.

## Directivas de la gestión de errores

Las directivas se explican brevemente a continuación. Para obtener más información, consulte [Directivas para la administración de errores](/help/workfront-fusion/references/errors/directives-for-error-handling.md).

Existen cinco directivas que se pueden agrupar en las siguientes categorías en función de si la ejecución de un escenario continúa después del error.

Las siguientes directivas garantizan que la ejecución de un escenario continúe:

* **[!UICONTROL Resume]**: permite especificar una salida de sustitución para el módulo con el error. El estado de ejecución del escenario se marca como correcto.
* **[!UICONTROL Ignore]**: omite el error. El estado de ejecución del escenario se marca como correcto.
* **[!UICONTROL Break]**: almacena la entrada en la cola de ejecuciones incompletas. El estado de ejecución del escenario se marca como advertencia.

  Para obtener más información, vea [Ver y resolver ejecuciones incompletas](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md).

Si la ejecución de un escenario debe detenerse cuando se produce un error, utilice una de las siguientes directivas:

* **[!UICONTROL Rollback]**: detiene la ejecución del escenario inmediatamente y marca su estado como error.
* **[!UICONTROL Commit]**: detiene la ejecución del escenario inmediatamente y marca su estado como correcto.

## Recursos

Para obtener más información sobre la gestión de errores, consulte:

* [Directivas para la gestión de errores en Adobe Workfront Fusion](/help/workfront-fusion/references/errors/directives-for-error-handling.md)
* [Añadir filtrado y anidamiento a las rutas de gestión de errores](/help/workfront-fusion/create-scenarios/config-error-handling/advanced-error-handling.md)
