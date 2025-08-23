---
title: Módulos de cadena
description: Con estos módulos, puede encadenar escenarios juntos, realizando una llamada a la otra.
author: Becky
feature: Workfront Fusion
hide: true
hidefromtoc: true
exl-id: 21429f94-fe4c-4ccc-a8c0-d7573657fecc
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 7%

---

# Encadenar módulos

Con los módulos Cadena, puede conectar un escenario a otro.

<!--This article will be about the specific module configuration-->

Para obtener instrucciones sobre cómo planear escenarios encadenados, vea [Encadenar varios escenarios](/help/workfront-fusion/create-scenarios/plan-a-scenario/chain-scenarios.md).


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
   <td> <p>Nuevo: estándar</p><p>O</p><p>Actual: Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion**</td> 
   <td>
   <p>No se requiere licencia de Workfront Fusion</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Seleccione o paquete de Prime Workfront: su organización debe adquirir Adobe Workfront Fusion.</li><li>Paquete de Ultimate Workfront: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe comprar Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Módulos de cadena y sus campos

### Activadores

#### Recibir datos del elemento principal

Este módulo es el módulo de déclencheur en el escenario secundario y se activa mediante el módulo Invocar a un escenario secundario en el escenario principal. Recibe datos del escenario principal, que se pueden procesar en el escenario secundario.

Para configurar el módulo principal Recibir datos de:

1. Para utilizar una estructura de datos existente, en el campo Data structure, seleccione la estructura de datos que se utilizará para los datos de entrada del escenario.

   O

   Para crear una nueva estructura de datos para usarla como datos de entrada del escenario, haga clic en **Agregar** junto al campo Estructura de datos y cree la estructura de datos.

   Para obtener instrucciones sobre cómo crear una estructura de datos, vea [Estructuras de datos](/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md).

1. Haga clic en **Aceptar** para guardar el módulo.

### Acciones

#### Llamar a un escenario secundario

Este módulo se encuentra en el escenario principal. Los campos reflejan la estructura de datos establecida en el módulo Recibir datos del principal en el escenario secundario.

>[!NOTE]
>
>* Puede seleccionar un escenario secundario existente o crear uno nuevo mediante este módulo.
>* Puede crear la estructura de datos al crear un escenario secundario.

Para configurar el módulo Llamar a un escenario secundario

1. Agregue el módulo Llamar a un escenario secundario a su escenario.
1. Para utilizar un escenario secundario existente, en el campo Cadena, seleccione el escenario secundario al que desee llamar.

   O

   Para crear un nuevo escenario secundario, haga clic en Agregar junto al campo Cadena. El escenario secundario aparece en una ventana independiente, con los módulos principal Recibir datos del principal y Devolver respuesta del principal.

   Los campos configurados en el módulo déclencheur del escenario secundario aparecen en el módulo Llamar a un escenario secundario.

1. Escriba o asigne la información que se va a pasar al escenario secundario en el módulo Llamar a un escenario secundario.
1. (Condicional) Si desea que el escenario principal continúe su ejecución sin esperar una respuesta del escenario secundario, habilite la opción **Fire and Olvidar**.
1. Haga clic en **Aceptar** para guardar el módulo.

>[!NOTE]
>
>Si crea un nuevo escenario secundario para este módulo, el escenario secundario se abre en una ventana independiente del explorador, lo que permite ver y configurar los escenarios principal y secundario al mismo tiempo.

#### Devolver respuesta al elemento principal

Se encuentra en el escenario secundario y envía los datos de la estructura seleccionada al escenario principal. Puede asignar estos datos en módulos posteriores en el escenario principal.

Si el escenario secundario tiene varias rutas, se recomienda agregar este módulo a una ruta que siempre se ejecute después de cualquier otra ruta.

Para configurar el módulo Agregar Respondedor:

1. Para utilizar una estructura de datos existente, en el campo Estructura de datos, seleccione la estructura de datos que se utilizará para los datos que el escenario secundario devuelve al escenario principal.

   O

   Para crear una nueva estructura de datos para los datos, haga clic en **Agregar** junto al campo Estructura de datos y cree la estructura de datos.

   Para obtener instrucciones sobre cómo crear una estructura de datos, vea [Estructuras de datos](/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md).

1. Haga clic en **Aceptar** para guardar el módulo.
