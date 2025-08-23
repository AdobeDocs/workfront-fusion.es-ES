---
title: Asignación de información de un módulo a otro
description: La asignación es el proceso de asignar los resultados de un módulo, estructurados en elementos, a los campos de entrada de otro módulo.
author: Becky
feature: Workfront Fusion
exl-id: 1e3f7729-f48e-451e-a90b-d680c9e3bcbc
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 42%

---

# Asignación de información de un módulo a otro

La asignación es el proceso de asignar los resultados de un módulo a los campos de entrada de otro módulo.

El panel Asignación se muestra al hacer clic en un campo en el que puede insertar un valor generado desde un módulo anterior en un escenario.

También puede crear una fórmula utilizando cualquier combinación de funciones y elementos asignados del panel Asignación con texto estático que escriba. Estos elementos se pueden anidar entre sí.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront</td> 
   <td> <p>Cualquiera</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencia de Adobe Workfront</td> 
   <td> <p>Nuevo: estándar</p><p>O</p><p>Actual: [!UICONTROL Work] o superior</p> </td> 
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
   <p>Nuevo:</p> <ul><li>Plan de Workfront de [!UICONTROL Select] o [!UICONTROL Prime]: su organización debe adquirir Adobe Workfront Fusion.</li><li>Plan de Workfront de [!UICONTROL Ultimate]: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe comprar Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Asignar un elemento

Después de crear una secuencia de módulos vinculando dos o más de ellos, cada módulo puede procesar los valores de los elementos que generan los módulos que le preceden.

Para asignar elementos de salida a los campos de entrada de un módulo:

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea asignar datos.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haga clic en el módulo que debe procesar la salida del módulo o módulos anteriores.
1. En el panel Configuración del módulo que aparece, haga clic en un campo en el que desee utilizar el valor de un elemento generado desde un módulo anterior.

   Se abrirá el panel de asignación.

1. (Opcional) Para buscar un campo determinado en el panel de asignación, haga clic en la barra de búsqueda del panel de asignación y escriba el término que desea buscar. Haga clic en el nombre cuando aparezca en la lista.

   Los resultados de la búsqueda contienen el término de búsqueda y no distinguen entre mayúsculas y minúsculas.
1. Para seleccionar un valor que es un elemento de una colección, haga clic en la flecha situada junto a esa colección y, a continuación, seleccione el elemento cuando aparezca.

   ![Elemento de colección](assets/collection-dropdown.png)

1. Haga clic en un elemento del panel de asignación para insertarlo en el campo.

Para obtener más información, consulte [Configurar un módulo](/help/workfront-fusion/create-scenarios/add-modules/configure-a-modules-settings.md).


## Resolución de problemas

### Problema: Faltan elementos en el panel de asignación

El panel de asignación muestra los elementos de salida de módulos anteriores. En ocasiones, es posible que falten algunos elementos en este panel. Puede ejecutar el módulo al que le falta salida en el editor de escenarios y, a continuación, el panel de asignación puede incluir esos elementos en módulos posteriores. El procedimiento exacto difiere según el tipo de módulo

* [Activador instantáneo](#instant-trigger)
* [Activador de sondeo](#polling-trigger)
* [Otros módulos](#other-modules)

#### Activador instantáneo

1. Haga clic con el botón secundario en el módulo y, a continuación, haga clic en **[!UICONTROL Run this module only]** en el menú que se muestra.

   Como se trata de un déclencheur instantáneo, comienza a observar eventos.

1. Cree el evento que está viendo el módulo.

   Por ejemplo, si el módulo es un módulo de Workfront > Ver eventos que está inspeccionando asignaciones de tareas, inicie sesión en Workfront (como usuario que no es el que utiliza la conexión de Fusion) y asigne una tarea.

1. Cuando el módulo termine de ejecutarse, haga clic en la burbuja situada encima del módulo para explorar su salida completa.

   El panel de asignación para módulos posteriores ahora contiene todos los elementos en la salida del módulo.

#### Activador de sondeo

1. Haga clic con el botón secundario en el módulo y, a continuación, haga clic en **[!UICONTROL Run this module only]** en el menú que se muestra.
1. Si no hay salida, haga clic en **[!UICONTROL Choose where to start]** y ajuste la configuración.
1. (Condicional) Si no hay ningún evento que procesar, cree el evento que el módulo inspecciona y repita el paso 2.

   Por ejemplo, si el módulo es un módulo de Workfront > Registros de inspección que está inspeccionando asignaciones de tareas, inicie sesión en Workfront (como usuario que no es el que utiliza la conexión de Fusion), asigne una tarea y, a continuación, ejecute el módulo de nuevo.

1. Cuando el módulo termine de ejecutarse, haga clic en la burbuja situada encima del módulo para explorar su salida completa.

   El panel de asignación para módulos posteriores ahora contiene todos los elementos en la salida del módulo.

#### Otros módulos

Puede elegir ejecutar:

* Todo el escenario (o solo la parte que contiene el módulo)
* El módulo único

Para ejecutar el módulo único:

1. Haga clic con el botón secundario en el módulo y, a continuación, haga clic en **[!UICONTROL Run this module only]** en el menú que se muestra.
1. Proporcione valores de muestra para los elementos de entrada y haga clic en **[!UICONTROL Aceptar]** .
1. Cuando el módulo termine de ejecutarse, haga clic en la burbuja situada encima del módulo para explorar su salida completa.

   El panel de asignación para módulos posteriores ahora contiene todos los elementos en la salida del módulo.
