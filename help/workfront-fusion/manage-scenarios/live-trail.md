---
title: Usar Live Trail para revisar la ejecución de un escenario
description: La pista en directo muestra un escenario ejecutado mientras sucede, combinando solicitudes de módulo y ejecutando actividad en una lista. Puede abrir los detalles de la solicitud y la respuesta de cualquier operación.
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
source-git-commit: 94449f8511d7480f1a4fc0ac6e8db9b067977abd
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 17%
---

# Usar Live Trail para revisar la ejecución de un escenario

La pista en directo muestra un escenario ejecutado mientras sucede. Combina solicitudes de módulo y actividad de ejecución en una lista cronológica, para que pueda seguir una ejecución en el editor de escenarios y ver qué ha fallado sin salir del lienzo.

>[!NOTE]
>
>Esta funcionalidad solo está disponible en la nueva experiencia del editor de escenarios. Para obtener más información, consulte [Experiencias nuevas y clásicas](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md#new-and-classic-experiences) en el artículo Editor de escenarios.

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

## Abrir pista activa

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario que desea revisar.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Inicie una ejecución del escenario, por ejemplo, haciendo clic en **Ejecutar una vez**.



La pista activa se abre en el panel situado en el lado derecho del lienzo. Si cierra el panel durante una ejecución, una pequeña pestaña a la derecha de la pantalla le permite abrirlo de nuevo sin perder los eventos capturados.

## Revisar eventos en Live Trail

Live Trail enumera las solicitudes de módulo y ejecuta la actividad en el orden en que se producen. Puede:

* Busque en la lista.
* Filtrar la lista por estado.
* Siga el evento más reciente mientras continúa la ejecución.
* Despeja el rastro actual.

## Ver detalles de solicitud y respuesta

1. En Live Trail, haga clic en la solicitud cuyos detalles desee ver.

   El módulo que realizó la solicitud se muestra en el lienzo y los detalles de la solicitud y la respuesta se abren en el panel.

1. Revise los detalles. La vista de detalles incluye:

   * Navegación entre las operaciones del módulo
   * Encabezados y cuerpo de solicitud
   * Encabezados y cuerpo de respuesta

1. (Opcional) Copie los detalles para usarlos en cualquier otra parte haciendo clic en **Copiar raw** o **Copiar cURL**:

   * Copie un informe sin procesar de la solicitud y la respuesta.
   * Copie un comando cURL para la solicitud.

1. Para volver a la lista, haga clic en la flecha hacia atrás situada en la parte superior izquierda del panel.

## Asegúrese de que los detalles de la solicitud y la respuesta estén disponibles

Los detalles de solicitud y respuesta no se conservan para cada ejecución programada o desencadenada, ya que ocupan mucho espacio de almacenamiento.

* Ejecutar una vez siempre mantiene los detalles de solicitud y respuesta.
* Para las ejecuciones regulares de un escenario, active los registros de depuración temporales en la configuración del escenario antes de las ejecuciones que desee inspeccionar. Para obtener más información, vea [Registros de depuración temporales](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#temporary-debug-logs) en el artículo Configurar opciones de escenario.

Si abre una ejecución desde el historial de ejecución y el panel de solicitud y respuesta no tiene datos, el panel le dirige a la configuración Registros de depuración temporales.
