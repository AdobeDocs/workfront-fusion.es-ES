---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: Usar una función para actualizar un proyecto en un escenario básico
description: Obtenga información sobre cómo añadir una función para actualizar un elemento de trabajo en Workfront.
author: Becky
feature: Workfront Fusion
exl-id: aa082ac8-48e8-4569-880e-024dd77feaa1
source-git-commit: 88147d0305595e1d0d388f510ed43fc5beaa4b64
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 77%

---

# Usar una función para actualizar un proyecto en un escenario básico

La actualización de un elemento de trabajo de Workfront es un caso de uso común para Workfront Fusion. En este ejemplo, utilizará una función para cambiar el nombre de un proyecto para que esté en mayúsculas.

Fusion incluye muchos tipos de funciones que le permiten transformar y realizar lógica condicional en sus datos. Para obtener más información acerca del uso de funciones, vea [Descripción general de funciones](/help/workfront-fusion/get-started-with-fusion/understand-fusion/function-overview.md).

Este ejemplo modifica el escenario creado en [Crear un escenario básico](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md).

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

Para obtener más información sobre el contenido de esta tabla, consulte los [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Requisitos previos

Debe crear el escenario descrito en [Crear un escenario básico](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md) antes de seguir este procedimiento.

## Utilizar una función para actualizar un proyecto

### Añada el módulo Actualizar registro a su escenario

1. Abra el escenario en el editor de escenarios.
1. Pase el ratón sobre el círculo parcial a la derecha del del segundo módulo y luego haga clic en **[!UICONTROL Agregar otro módulo]**.
1. Seleccione Adobe Workfront de la lista de aplicaciones y, a continuación, elija el módulo **[!UICONTROL Actualizar registro]**.
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
1. En Workfront Fusion, haga clic en **[!UICONTROL Guardar]** cerca de la esquina inferior izquierda para guardar su progreso en el escenario.

   >[!IMPORTANT]
   >
   >Guarde con frecuencia mientras perfecciona y prueba un escenario. Es posible que tenga que crear un nuevo problema en su cuenta de Workfront para almacenar en déclencheur el escenario.

## Recursos

* [Asignación de elementos mediante funciones integradas](/help//workfront-fusion/create-scenarios/map-data/map-using-functions.md)
