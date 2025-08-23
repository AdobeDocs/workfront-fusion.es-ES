---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: Agregar un webhook a un escenario básico
description: Los webhooks, también conocidos como déclencheur instantáneos, son un tipo específico de módulo de déclencheur que puede iniciar un escenario cada vez que se realice un cambio, en lugar de hacerlo en una programación determinada.
author: Becky
feature: Workfront Fusion
exl-id: 28ecca1f-a9c3-4b3d-95f5-73cb9a5dc4b9
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 36%

---

# Agregar un webhook a un escenario básico

Los webhooks, también conocidos como déclencheur instantáneos, son un tipo específico de módulo de déclencheur que puede iniciar un escenario cada vez que se realice un cambio, en lugar de hacerlo en una programación determinada.

En este ejemplo, agregará un webhook para iniciar un escenario en cuanto se haya enviado una solicitud a una cola de solicitudes específica. A continuación, el escenario convertirá esas solicitudes en un proyecto.

En este ejemplo se modifica el escenario que se creó en [Crear un escenario básico](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md).

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront</td> 
   <td> <p>Cualquier paquete que incluya automatización e integración de Workfront</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion</td> 
   <td>
   <p>No se requiere licencia de Workfront Fusion.</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Debe tener una cuenta para cualquier aplicación o servicio al que se conecte con Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Debe crear el escenario descrito en [Crear un escenario básico](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md) antes de seguir este procedimiento.

## Agregar y configurar el webhook


### Añadir el módulo webhook

1. Abra el escenario en el editor de escenarios.
1. Haga clic con el botón derecho en el primer módulo y seleccione **Eliminar módulo**.

   El módulo se eliminará y quedará un marcador de posición en blanco.

1. Haga clic en el módulo en blanco y seleccione **Adobe Workfront** de la lista de aplicaciones.
1. Seleccione **Ver eventos**.
1. Haga clic en **Agregar** junto al campo Webhook.
1. en el campo Tipo de registro, seleccione **Problema**, de modo que el módulo se almacenará en déclencheur para los cambios en los problemas.
1. En el campo Estado, seleccione **Nuevo estado**. Este es un campo obligatorio que se utiliza para el filtro, que este ejemplo no cubre.
1. En el campo Origen de registro, seleccione **Solo nuevo registro**. Esto permite que el escenario entre en déclencheur cuando se agrega un problema, no cuando se actualiza o elimina uno.
1. Haga clic en **Guardar** para guardar la configuración del módulo.

## Actualización del segundo módulo

1. Abra el escenario.
1. Haga clic en el módulo **Convertir objeto** para abrirlo.
1. En el campo ID del problema, elimine el bloque de ID negro. El bloque es negro porque el módulo desde el que se asignó ya no está disponible.
1. Seleccione el bloque de ID bajo el primer módulo (Ver eventos) para asignarlo al segundo módulo.
1. Haga clic en **Aceptar**.



### Prueba y activación

1. Haga clic en **[!UICONTROL Ejecutar una vez]** en la esquina inferior izquierda del editor de escenarios.

   El escenario debe estar en ejecución para poder ver la nueva solicitud.
1. Vaya al entorno de Workfront al que se conecte Fusion y añada un problema.

   El escenario debería ejecutarse.
1. Examine el resultado para asegurarse de que el escenario se ejecutó según lo esperado.
1. Cuando esté seguro de que el escenario funciona según lo esperado, haga clic en el conmutador **Programando** de la parte inferior izquierda de la pantalla para **Activar**.

   Esto activará el escenario.
1. En Workfront Fusion, haga clic en **[!UICONTROL Guardar]** cerca de la esquina inferior izquierda para guardar su progreso en el escenario.
