---
title: Añadir la gestión de errores
description: Cuando se producen errores durante la ejecución de un escenario, suele ser porque un servicio no está disponible debido a un fallo, un servicio responde con datos inesperados o falla la validación de los datos de entrada.
author: Becky
feature: Workfront Fusion
exl-id: 82ddaf73-ecf9-4fd6-8f8e-909351023c77
source-git-commit: d7072a2dca50bf47f20d1f25dba4d3fb819d3ddc
workflow-type: tm+mt
source-wordcount: '1152'
ht-degree: 21%

---

# Añadir la gestión de errores

Pueden producirse errores durante la ejecución de un escenario.

Por ejemplo, se puede producir un error debido a lo siguiente:

* Un servicio no está disponible debido a un error
* Un servicio responde con datos inesperados
* Error de validación de datos de entrada
* Otras razones

Si un módulo encuentra un error durante la ejecución del escenario y no hay ninguna ruta de control de errores asociada al módulo o a su ruta, se ejecuta la lógica de control de errores predeterminada.

Al agregar un controlador de error a un módulo o una ruta, puede reemplazar la lógica predeterminada de control de errores por la suya propia. Adobe Workfront Fusion ofrece cinco directivas diferentes que se pueden insertar al final de las rutas de gestión de errores.

Para obtener más información sobre la administración de errores predeterminada, consulte [Tipos de error](/help/workfront-fusion/references/errors/error-processing.md).

Para obtener más información acerca de las directivas de control de errores, consulte [Directivas de control de errores](/help/workfront-fusion/references/errors/directives-for-error-handling.md).

>[!NOTE]
>
>Workfront Fusion admite la gestión de errores en el nivel de ruta, lo que permite definir la lógica de gestión de errores una vez por ruta, en lugar de adjuntar controladores de error a cada módulo individual.
>Debido a que la gestión de errores en el nivel de ruta es una forma más escalable, coherente y arquitectónicamente limpia de administrar errores, especialmente en automatizaciones avanzadas de varias ramas, recomendamos utilizar la gestión de errores en el nivel de ruta como práctica recomendada.

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

## Ubicación y jerarquía del controlador de error

Puede agregar controladores de error a módulos individuales o a enrutadores.

Un controlador de error adjunto a un módulo déclencheur únicamente los errores encontrados al procesar ese módulo específico.

Un controlador de error adjunto a un enrutador déclencheur los errores encontrados por cualquier módulo en la ruta de ese enrutador. Esto incluye los errores encontrados en cualquier ruta secundaria que no tenga un controlador de errores en su propio enrutador.

Los errores se gestionan mediante la siguiente jerarquía:

1. Módulo
2. Enrutador
3. Enrutador principal
4. Gestión de errores predeterminada

>[!BEGINSHADEBOX]

### Ejemplo

Consideremos el siguiente escenario de ejemplo:

![Ejemplo de escenario que muestra rutas y controladores de errores](assets/error-handling-route-example-with-numbers.png)

1. Este módulo tiene un controlador de errores. Cualquier error en este módulo se gestiona mediante la directiva Commit.
1. Este módulo no tiene un controlador de errores. Si este módulo encuentra un error, el controlador del enrutador que creó la ruta del módulo lo controla. Cualquier error en este módulo se gestiona mediante la directiva Rollback.
1. Este módulo no tiene un controlador de errores, ni tampoco el enrutador que creó la ruta del módulo, pero hay un controlador de errores en el siguiente enrutador. Cualquier error en este módulo se gestiona mediante la directiva Break.

>[!NOTE]
>
>* Si un módulo no tiene un controlador de errores en el módulo, en su enrutador o en cualquier enrutador principal, los errores de ese módulo se gestionarán mediante el control de errores predeterminado.
>* Para crear un controlador de error global, cree un enrutador cerca del principio del escenario y adjúntele el control de errores a ese enrutador.


>[!ENDSHADEBOX]

## Añadir un controlador de error

Puede agregar un controlador de error a un módulo o a un enrutador.

* [Añadir un controlador de error a un módulo](#add-an-error-handler-to-a-module)
* [Añadir un controlador de error a un enrutador](#add-an-error-handler-to-a-router)

### Añadir un controlador de error a un módulo

Para agregar un controlador de error a un módulo:

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea agregar una ruta de control de errores.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haga clic con el botón derecho en el módulo después del cual desea agregar una ruta de controlador de error y seleccione **[!UICONTROL Agregar controlador de error]**:

   ![Ruta del controlador de error](assets/error-handler-route.png)

   Se agrega una ruta de controlador de error al módulo. Si el módulo es el último módulo de una ruta, el controlador de errores lo seguirá directamente. Si el módulo tiene más módulos después, se agrega una ruta de controlador de error independiente.

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

### Añadir un controlador de error a un enrutador

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea agregar una ruta de control de errores.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haga clic con el botón derecho en el enrutador donde desee agregar una ruta de controladores de error y seleccione **[!UICONTROL Agregar controlador de error]**:

   ![Ruta del controlador de error](assets/error-handler-on-router.png)

   Se agrega una ruta de controlador de error al enrutador.

   El módulo de gestión de errores muestra una lista de directivas, así como las aplicaciones que se utilizan en su escenario.

   ![Ruta de error](assets/error-handler-route-from-router.png)

1. Seleccione una de las directivas.

   O

   Añada uno o más módulos a la ruta del controlador de errores.

   Si agrega más módulos a la ruta, la directiva Ignore se aplica de forma predeterminada. Si hay un error, se procesan los módulos posteriores de esa ruta.

   Para obtener más información sobre directivas, consulte [Directivas de administración de errores](#error-handling-directives) en este artículo.

1. (Opcional) Añada un filtro a la ruta de gestión de errores. Para obtener instrucciones, vea [Agregar filtrado y anidamiento a rutas de control de errores](/help/workfront-fusion/create-scenarios/config-error-handling/advanced-error-handling.md).

## Directivas de la gestión de errores

Las directivas se explican brevemente a continuación. Para obtener más información, consulte [Directivas para la administración de errores](/help/workfront-fusion/references/errors/directives-for-error-handling.md).

Existen cinco directivas que se pueden agrupar en las siguientes categorías en función de si la ejecución de un escenario continúa después del error.

Las siguientes directivas garantizan que la ejecución de un escenario continúe:

* **[!UICONTROL Reanudar]**: permite especificar una salida de sustitución para el módulo con el error. El estado de ejecución del escenario se marca como correcto.
* **[!UICONTROL Ignorar]**: ignora el error. El estado de ejecución del escenario se marca como correcto.
* **[!UICONTROL Salto]**: almacena la entrada en la cola de ejecuciones incompletas. El estado de ejecución del escenario se marca como advertencia.

  Para obtener más información, vea [Ver y resolver ejecuciones incompletas](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md).

Si la ejecución de un escenario debe detenerse cuando se produce un error, utilice una de las siguientes directivas:

* **[!UICONTROL Reversión]**: detiene la ejecución del escenario inmediatamente y marca su estado como error.
* **[!UICONTROL Compromiso]**: detiene la ejecución del escenario inmediatamente y marca su estado como correcto.

## Recursos

Para obtener más información sobre la gestión de errores, consulte:

* [Directivas para la gestión de errores en Adobe Workfront Fusion](/help/workfront-fusion/references/errors/directives-for-error-handling.md)
* [Añadir filtrado y anidamiento a las rutas de gestión de errores](/help/workfront-fusion/create-scenarios/config-error-handling/advanced-error-handling.md)
