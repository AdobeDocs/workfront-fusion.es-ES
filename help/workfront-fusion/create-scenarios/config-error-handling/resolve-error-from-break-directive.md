---
title: Resolver errores gestionados por la directiva Break
description: A veces, resulta útil volver a ejecutar un módulo que falla si existe la posibilidad de que el motivo del error se resuelva rápidamente.
author: Becky
feature: Workfront Fusion
exl-id: d568942c-2cd5-430c-bdbf-e1496da25b50
source-git-commit: b2ca63ca5af26ee79758798118817b55113b3bd0
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 51%

---

# Resolver errores gestionados por la directiva Break

Cuando la directiva Break gestiona un error, se crea un registro en la carpeta de ejecuciones incompletas. Este registro almacena el estado de la ejecución del escenario, junto con los datos de los módulos anteriores. El registro hace referencia al módulo en el que se originó el error y contiene información sobre los datos recibidos por el módulo como entrada. Para cada paquete de datos que causa el error, se crea un registro independiente.

Para obtener más información, vea [Ver y resolver ejecuciones incompletas](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md).

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

## Resolver errores resultantes de la directiva Salto

Puede resolver el error manualmente actualizando el escenario (si es necesario) y ejecutándolo una vez.

También puede configurar el escenario para que procese automáticamente una ejecución incompleta haciendo que se vuelva a ejecutar el escenario. Para configurar el módulo de forma que procese las ejecuciones incompletas:

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea agregar la solución.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haga clic en el icono **Control de flujo** ![Control de flujo](assets/flow-control-icon.png) y seleccione **Salto**.
1. Dentro del módulo Salto, habilite la opción [!UICONTROL **Finalizar ejecución automáticamente**].
1. En el campo **Número de intentos**, indique o asigne el número máximo de intentos que desea que el módulo reintente la ejecución

   Este número debe estar entre 1 y 100.
1. En el campo **Intervalo entre intentos**, escriba o asigne el número de minutos que debe transcurrir entre cada reintento.

Con esta opción habilitada, cuando se produce un error, la ejecución incompleta se recupera (después del tiempo especificado en el campo [!UICONTROL Intervalo entre intentos]) y se ejecuta con los datos de entrada originales. Esto se repetirá hasta que la ejecución del módulo se complete sin ningún error o hasta que se alcance el Número de intentos especificado.

>[!NOTE]
>
>Si falla el intento de reintento inicial, el intervalo entre reintentos aumenta exponencialmente con cada intento.


Cuando la opción de ejecución Completar automáticamente está activada, la ejecución del escenario se marca como &quot;Correcta&quot; porque el reintento automático del controlador de error de interrupción gestiona el problema automáticamente. En este caso, los usuarios no reciben un correo electrónico sobre la ejecución fallida.

Cuando la opción Automatically complete execution está desactivada, la ejecución se marca como &quot;Warning&quot;.

Hay algunas excepciones al almacenamiento de las ejecuciones en Ejecuciones incompletas y, con algunos tipos de error, no es posible reintentar automáticamente la ejecución de un escenario.

## Recursos

Para obtener más información, consulte [Permitir el almacenamiento de ejecuciones incompletas](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#allow-storing-incomplete-executions) en el artículo Configurar opciones de escenario.
