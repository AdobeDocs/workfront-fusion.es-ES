---
title: Visualización del historial de ejecución de un escenario
description: Puede mostrar información sobre los eventos o las ejecuciones de un escenario, o puede buscar datos específicos en todas las ejecuciones del escenario.
author: Becky
feature: Workfront Fusion
exl-id: 974b32b4-d86a-48cd-a8d4-1ae2cf309b9b
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 60%

---

# Visualización del historial de ejecución de un escenario

Puede mostrar información sobre los eventos o las ejecuciones de un escenario, o puede buscar datos específicos en todas las ejecuciones del escenario.

La ejecución de un escenario representa una única ejecución del escenario.

Un evento de escenario es una modificación del escenario, como editarlo, activarlo o desactivarlo.

>[!NOTE]
>
>El historial de un escenario muestra todos los eventos y ejecuciones de un escenario durante los últimos 30 días.

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
  <tr data-mc-conditions=""> 
   <td role="rowheader">Configuraciones de nivel de acceso*</td> 
   <td> 
     <p>Debe ser administrador de Workfront Fusion para su organización.</p>
     <p>Debe ser administrador de Workfront Fusion para su equipo.</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Ver historial de escenarios


### Ver el historial de escenarios en la pestaña Historial

La ficha [!UICONTROL Historial] muestra más detalles de los que están disponibles en la página [!UICONTROL Detalles del escenario]. También puede filtrar y ordenar las ejecuciones en la ficha [!UICONTROL Historial].

1. Haga clic en la ficha **[!UICONTROL Escenario]** en el panel izquierdo y, a continuación, haga clic en el escenario.

   O

   Si está trabajando en el escenario en el Editor de escenarios, haga clic en la flecha izquierda ![Salir de la flecha de edición](assets/exit-editing-arrow.png) cerca de la esquina superior izquierda de la ventana.

1. Haga clic en **Historial** cerca del nombre del escenario.
   ![ficha de historial](assets/history-tab.png)

   Se enumeran los siguientes detalles para cada ejecución del escenario:

   * Fecha en la que se **[!UICONTROL inició]** la ejecución
   * ID de ejecución
   * **[!UICONTROL Estado]** (correcto o fallido)
   * **[!UICONTROL Duración]** de la ejecución
   * Número de **[!UICONTROL operaciones]**
   * Tamaño de la **[!UICONTROL transferencia de datos]**

   >[!NOTE]
   >
   >El historial de escenarios muestra un distintivo **En procesamiento** junto a los escenarios que se han ejecutado recientemente, mientras que los detalles de la ejecución se escriben en el almacenamiento. El procesamiento se produce inmediatamente después de que se ejecute el escenario. y no debe durar más de unos minutos. Es posible que los detalles de la ejecución del escenario no estén visibles mientras se procesa la ejecución.

1. Para ver los detalles de una ejecución de escenario específico, haga clic en **Detalles** en el extremo derecho. El vínculo [!UICONTROL detalles] solo es visible si la ejecución tiene detalles disponibles.

   Para obtener más información sobre cómo ver los detalles de ejecución de un escenario, vea [Ver una ejecución de escenario específica](/help/workfront-fusion/manage-scenarios/view-a-specific-scenario-execution.md).
1. Para ver los eventos, activa o desactiva **Mostrar eventos**.


### Ver el historial de escenarios en la página Detalles del escenario


1. Haga clic en la ficha **[!UICONTROL Escenario]** en el panel izquierdo y, a continuación, haga clic en el escenario.

   O

   Si está trabajando en el escenario en el Editor de escenarios, haga clic en la flecha izquierda ![Salir de la flecha de edición](assets/exit-editing-arrow.png) cerca de la esquina superior izquierda de la ventana.

1. Haga clic en la ficha **[!UICONTROL Historial]** en el panel derecho.
1. (Opcional) Para obtener información detallada sobre la ejecución de un escenario seleccionado, haga clic en la ejecución en el panel derecho.

   Para obtener más información sobre el procesamiento de paquetes, consulte [Flujo de ejecución de escenario](/help/workfront-fusion/references/scenarios/scenario-execution-flow.md)

   >[!NOTE]
   >
   >* El historial de escenarios muestra un distintivo **Historial de procesamiento** junto a los escenarios que se han ejecutado recientemente, mientras que los detalles de la ejecución se escriben en el almacenamiento. El procesamiento se produce inmediatamente después de que se ejecute el escenario. y no debe durar más de unos minutos. Es posible que los detalles de la ejecución del escenario no estén visibles mientras se procesa la ejecución.

1. Para ver los eventos, haga clic en la ficha **Eventos**.

## Filtrado del historial de ejecuciones del escenario

Puede filtrar el historial de ejecuciones para ver solo las ejecuciones con los valores especificados.

1. Abra el historial de página completa de un escenario como se describe en [Ver el historial de ejecuciones de un escenario en la ficha [!UICONTROL Historial]](#view-scenario-history-on-the-history-tab) de este artículo.
1. Haga clic en el icono [!UICONTROL filter] ![Icono de filtro de escenario](assets/fusion-scenario-filter-icon.png) en el encabezado de la columna por la que desee filtrar.
1. En el cuadro de diálogo [!UICONTROL filtrar], escriba los valores por los que desea filtrar.
1. Haga clic en **[!UICONTROL Guardar]**.

El icono de filtro es de color naranja en las columnas con un filtro activo.

<!-- don't see how to do this
## Sort the scenario execution history

You can sort the scenario execution history.

1. Open the full-page history for a scenario as described in [View scenario execution history on the [!UICONTROL History] tab](#view-scenario-execution-history-on-the-history-tab) in this article.
1. Click the [!UICONTROL Sort] icon in the header of the column you want to filter by.
1. Optional: To reverse the order of the sort, click the [!UICONTROL Sort] icon again.
-->

## Buscar todas las ejecuciones de un escenario

1. Abra el historial de página completa de un escenario como se describe en [Ver el historial de ejecuciones de un escenario en la ficha [!UICONTROL Historial]](#view-scenario-history-on-the-history-tab) de este artículo.
1. Haga clic en **[!UICONTROL Búsqueda de texto completo]** en la parte superior de la lista de ejecuciones.

   O

   Escriba **Ctrl+Mayús+F** (Windows) o **Cmd+Mayús+F** (Mac)
Se abre la ventana [!UICONTROL Buscar en el historial].

1. (Opcional) Para buscar ejecuciones que contengan texto específico, escriba el texto en la barra de búsqueda de la ventana **[!UICONTROL Buscar en el historial]**.

   Para buscar texto exacto, escriba el texto entre comillas dobles (&quot;ejemplo&quot;).

   >[!INFO]
   >
   >**Ejemplo:** si desea encontrar la ejecución que creó un proyecto específico, escriba el identificador de proyecto en la barra [!UICONTROL Búsqueda de texto completo].
   >
   >&quot;625ef2ef0006036bd1794b6e52d737c5&quot;

1. (Opcional) Para limitar la búsqueda por intervalo de fechas, seleccione las fechas de inicio y finalización de la búsqueda deseada en el área [!UICONTROL Por intervalo de fechas].

   >[!NOTE]
   >
   >* Las ejecuciones solo están disponibles durante los 30 días anteriores.
   >
   >* Workfront Fusion almacena las cargas útiles de los ganchos web durante 30 días. Al acceder a una carga útil de webhook más de 30 días después de su creación se produce el error &quot;[!UICONTROL No se pudo leer el archivo desde el almacenamiento]&quot;.


1. (Opcional) Para limitar la búsqueda por estado, seleccione el estado que desee en la lista desplegable **[!UICONTROL Por estado]**.


   Los estados disponibles son:

   * [!UICONTROL Todo]

   * [!UICONTROL Error]

   * [!UICONTROL Advertencia]

   * [!UICONTROL Correcto]

1. (Opcional) Cambie el orden en que se muestran los resultados en la lista desplegable **[!UICONTROL Ordenar por fechas]**.

1. (Opcional) Para copiar un ID de ejecución de escenario, haga clic en el icono **[!UICONTROL Copiar ID de ejecución]** <img src="assets/copy-fusion-execution-id-icon.png"> en la fila de la ejecución deseada.

1. (Opcional) Haga clic en un resultado de la [!UICONTROL búsqueda de texto completo] para examinar el paquete de salida del módulo de escenario que contiene la información.
