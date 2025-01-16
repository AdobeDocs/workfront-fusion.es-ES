---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: Usar una función para actualizar un proyecto en un escenario básico
description: Obtenga información sobre cómo añadir una función para actualizar un elemento de trabajo en Workfront.
author: Becky
feature: Workfront Fusion
exl-id: aa082ac8-48e8-4569-880e-024dd77feaa1
source-git-commit: 8884aef2237ad358c774110b81ac17b9efb386d4
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 73%

---

# Usar una función para actualizar un proyecto en un escenario básico

La actualización de un elemento de trabajo de Workfront es un caso de uso común para Workfront Fusion. En este ejemplo, utilizará una función para cambiar el nombre de un proyecto para que esté en mayúsculas.

Fusion incluye muchos tipos de funciones que le permiten transformar y realizar lógica condicional en sus datos. Para obtener más información acerca del uso de funciones, vea [Descripción general de funciones](/help/workfront-fusion/get-started-with-fusion/understand-fusion/function-overview.md).

Este ejemplo modifica el escenario creado en [Crear un escenario básico](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md).

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] paquete</td> 
   <td> <p>Cualquiera</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licencia</td> 
   <td> <p>Nuevo: [!UICONTROL Standard]</p><p>O</p><p>Actual: [!UICONTROL Work] o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licencia**</td> 
   <td>
   <p>Actual: no se requiere licencia para [!DNL Workfront Fusion].</p>
   <p>O</p>
   <p>Heredado: cualquiera </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>[!UICONTROL Select] o plan [!UICONTROL Prime] [!DNL Workfront]: su organización debe comprar [!DNL Adobe Workfront Fusion].</li><li>[!UICONTROL Ultimate] [!DNL Workfront] plan: [!DNL Workfront Fusion] está incluido.</li></ul>
   <p>O</p>
   <p>Actual: su organización debe comprar [!DNL Adobe Workfront Fusion].</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Debe crear el escenario descrito en [Crear un escenario básico](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md) antes de seguir este procedimiento.

## Utilizar una función para actualizar un proyecto

### Añada el módulo Actualizar registro a su escenario

1. Abra el escenario en el editor de escenarios.
1. Pase el ratón sobre el círculo parcial a la derecha del del segundo módulo y luego haga clic en **[!UICONTROL Add another module]**.
1. Seleccione [!DNL Adobe Workfront] de la lista de aplicaciones y luego elija el módulo **[!UICONTROL Update Record]**.
1. En el campo ID, seleccione el bloque de ID que se encuentra en el módulo Convertir objeto. Este es el ID del proyecto que ese módulo generó.

   ![ID de Convertir objeto](assets/id-convert-object.png)

1. En el campo Tipo de registro, seleccione Proyecto, ya que el objeto que se va a actualizar es un proyecto.
1. En el área Seleccionar campos para asignar, seleccione Nombre.

   Se abrirá un campo Nombre.
1. Continúe con [Asignar la función para la actualización de nombre](#map-the-function-for-the-name-update).

### Asignación de la función para la actualización del nombre

Cuando este escenario convierte una solicitud en un proyecto, el nombre del proyecto es el mismo que la solicitud. La función toma ese nombre y pone en mayúsculas todas las letras que contiene.

1. Haga clic en el campo **Nombre**.

   Se abrirá el panel de asignación.
1. En el panel de asignación, haga clic en el icono **Funciones binarias y de texto**. ![Icono de funciones de texto](assets/toolbar-icon-text&binary-functions.png)
1. Seleccione la función **superior**.

   La función aparece en el campo Nombre, incluido el formato de la entrada que espera.

   La entrada para este ejemplo es el nombre del problema desde el que se convirtió el proyecto.

1. Mueva el cursor entre los paréntesis, ya que aquí es donde irá la entrada.
1. En el panel de asignación, haga clic en el icono **Salida de módulo**. ![Icono de salida del módulo](assets/toolbar-icon-functions-you-map-from-other-modules.png)
1. Seleccione el bloque de nombres que generó el primer módulo.

   El bloque de nombres aparece en la función.

   ![Bloque de nombres en la función](assets/map-name.png)

1. Haga clic en **Aceptar** para guardar la configuración del módulo.

### Prueba y activación

1. Pruebe el escenario haciendo clic en **Ejecutar una vez** en la esquina inferior izquierda de la pantalla.
1. Examine el resultado para asegurarse de que el escenario se ejecutó según lo esperado.
1. Cuando esté seguro de que el escenario funciona según lo esperado, haga clic en el conmutador **Programando** en la parte inferior izquierda de la pantalla para **activarlo**.

   Esto activará el escenario. Los escenarios activos se ejecutan según la programación establecida en el módulo del activador.
1. En [!DNL Workfront Fusion], haga clic en **[!UICONTROL Save]** cerca de la esquina inferior izquierda para guardar su progreso en el escenario.

   >[!IMPORTANT]
   >
   >Se recomienda guardar con frecuencia mientras se perfeccionan y prueban escenarios.

## Recursos

* [Asignación de elementos mediante funciones](/help//workfront-fusion/create-scenarios/map-data/map-using-functions.md)
