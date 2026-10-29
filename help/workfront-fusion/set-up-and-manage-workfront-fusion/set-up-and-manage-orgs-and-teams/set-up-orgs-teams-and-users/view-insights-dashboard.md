---
title: Ver el panel de información de una organización
description: Los administradores de Fusion pueden ver un tablero que muestra las métricas de ejecución de una organización.
author: Becky
feature: Workfront Fusion
exl-id: 8f80f86a-69e5-48a1-9812-87322a4959a6
TQID: 'https://experienceleague.adobe.com/tBZCbpImQxY42gOE8e04aQwCJC8EKgrDTIAt6Sw1KaU'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: 45c755a2f6152b6e230864e4c840d0334705bd22
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 5%
---
# Ver el panel de información de una organización

El panel de datos de Fusion Insights le permite ver rápidamente qué escenarios se están ejecutando más, dónde se están produciendo los retrasos y con qué eficacia están funcionando los grupos de trabajo. Esto proporciona visibilidad en tiempo real de los volúmenes de ejecución, la profundidad de la cola, el uso del grupo y el rendimiento en el nivel de escenario.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Paquete de Adobe Workfront</td> 
   <td> <p>Flujo de trabajo de Adobe Workfront Ultimate y automatización e integración de Adobe Workfront Ultimate</p><p>Workfront Ultimate</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencias de Adobe Workfront</td> 
   <td> <p>Estándar</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Configuraciones de nivel de acceso</td> 
   <td> 
     <p>Debe ser administrador de Workfront Fusion para su organización.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte los [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Componentes del panel de perspectivas

>[!NOTE]
>
>Las métricas se muestran por grupo de trabajo. Para ver un grupo de trabajo diferente, haga clic en el campo Grupo situado cerca de la esquina superior izquierda del panel y, a continuación, seleccione el grupo para el que desea ver las métricas.

<!--

>[!NOTE]
>
>Organizations can request provisioning for one additional worker pool (for a total of 2).

-->

En el panel de Fusion Insights, puede ver las siguientes métricas.

* **Registros de ejecuciones con errores**
Esta tabla enumera todas las ejecuciones de escenarios de advertencia o fallidas de su organización, para que pueda encontrar y solucionar problemas de ejecuciones sin salir del panel.
* **Operaciones de organización**
Este gráfico le permite ver el número de operaciones utilizadas en su organización. Puede seleccionar equipos o escenarios específicos y ver las operaciones de la última semana, mes o año.
* **Escenarios principales por operaciones**
Este gráfico le permite ver qué escenarios están utilizando la mayoría de las operaciones. Puede seleccionar equipos específicos o ver los datos del último día, semana o mes.

<!--

* **Executions waiting to be processed**
   This chart shows the number of executions waiting to be processed (also known as the execution backlog) at a given point in time. 

   A high number of executions waiting to be processed may affect performance in your Fusion instance. You will receive a notification if your execution backlog reaches 5000 executions. We recommend identifying responsible scenarios and modifying or disabling them. If the high execution backlog persists, the Fusion team will protect the performance of your Fusion instance by disabling the responsible scenarios.
* **Pool Utilization**
   This chart shows worker pool utilization over time. If this chart routinely shows worker pool utilization, you may want to assign some scenarios to another pool.

   If a pool is nearing 100% utilization, other resources that use the same pool may be delayed or disrupted. If this occurs, we recommend reassigning a high-usage scenario to another worker pool, or modifying existing scenarios to be less resource intensive.
* **Executions per scenario**
   This chart displays executions per scenario. Different colors represent different scenarios. When you hover over the chart, a window appears that shows which color is which scenario.

   You can use this chart to identify which scenarios may be causing an execution backlog or high worker pool utilization. 
* **Duration of executions**
   This chart displays executions per scenario. Different colors represent different scenarios. When you hover over the chart, a window appears that shows which color is which scenario.

   You can use this chart to identify scenarios that are taking longer than usual, including those affected by issues with a connected app or service.

-->

## Ver el panel de información de Fusion

1. En Fusion, haga clic en **Información** en el panel de navegación izquierdo.

   Se abrirá el panel.

1. Para ver los datos de un punto específico en el tiempo, pase el ratón sobre un panel y ajuste el cursor para que esté sobre el punto en el tiempo que desee ver.

   Aparece una línea sobre ese punto en el tiempo en todos los gráficos y en cada gráfico aparece una ventana que muestra los datos de ese tiempo.
1. Para ver los datos de un escenario específico en el gráfico Ejecuciones por escenario o en el gráfico Duración de las ejecuciones, haga clic en una barra del color del escenario cuyos datos desee ver. Para volver a la vista que muestra todos los escenarios, haga clic de nuevo en el gráfico.
1. Para ir a un escenario específico que se muestra en el gráfico Ejecuciones por escenario o en el gráfico Duración de las ejecuciones, haga clic con el botón derecho en una barra de color para el escenario y seleccione **Abrir escenario en nueva pestaña**.
1. Para expandir un gráfico, haz clic en el icono **Expandir** ![Expandir icono](assets/expand-icon.png) en la esquina superior derecha del gráfico.
1. Para cambiar el intervalo de tiempo del panel, haga clic en el campo Intervalo de tiempo en la esquina superior derecha del panel y, a continuación, seleccione un nuevo lapso de tiempo. El lapso de tiempo más largo disponible es de 24 horas, y el más corto es de 15 minutos.
1. Para actualizar los gráficos, haga clic en el icono Actualizar situado cerca de la esquina superior derecha del panel.
1. Para ver un grupo de trabajo diferente, haga clic en el campo Grupo situado cerca de la esquina superior izquierda del panel y, a continuación, seleccione el grupo que desee ver.

## Personalización del panel de información

Puede elegir qué widgets aparecen en el panel de Insights y en qué orden.

### Agregar, quitar o reordenar widgets

1. En el panel de navegación de la izquierda, haga clic en **Insights** ![Icono de Insights](assets/insights-icon.png).
1. Haga clic en **[!UICONTROL Personalizar]** en el encabezado de Insights.

   Se abrirá un panel lateral. Enumera cada widget como una tarjeta que muestra una vista previa, el nombre del widget y una descripción.

1. Para mostrar u ocultar un widget, haz clic en su tarjeta o haz clic en el botón **[!UICONTROL Agregar widget]** o **[!UICONTROL Quitar widget]** de la tarjeta.

   Los widgets que se muestran tienen una marca de verificación.
1. Para reordenar los widgets, arrastre una tarjeta de widget a una nueva posición en el panel.

   Un marcador de posición con guiones y una barra de colocación muestran dónde aterrizará la tarjeta.

Las opciones se guardan por explorador. Los widgets que se añaden en versiones posteriores aparecen automáticamente en el panel.

Si elimina todos los widgets, la página muestra el mensaje &quot;No hay widgets en esta página&quot;.

## Actualizar el panel de información

Para volver a cargar los datos de cada widget, haz clic en **[!UICONTROL Actualizar]** junto a **[!UICONTROL Personalizar]**.

* Cada widget mantiene sus filtros.
* El botón **[!UICONTROL Actualizar]** muestra un estado pendiente hasta que todos los widgets terminen de cargarse.
* Los gráficos mantienen el gráfico anterior bajo un control de giro de carga y el registro de ejecuciones atenúa su tabla bajo un control de giro mientras los datos se recargan.
* Si una actualización falla, los widgets conservan los últimos datos válidos.

## Realizar la visita guiada de Insights

La primera vez que abra el panel de perspectivas, un cuadro de diálogo de bienvenida le dará la opción de iniciar un recorrido u omitirlo.

El recorrido resalta cada widget en el orden guardado, así como el botón **[!UICONTROL Personalizar]**, el botón **[!UICONTROL Actualizar]** y el botón **[!UICONTROL Reproducir recorrido]** de la barra de título.

Para reiniciar el recorrido en cualquier momento, haga clic en el icono de información del recorrido ![icono de información](assets/insights-tour-information.png) en la barra de título.

El recorrido no se inicia al abrir el panel de perspectivas desde un vínculo en un escenario. Para obtener más información, consulte [Abrir el panel de información desde un escenario](#open-the-insights-dashboard-from-a-scenario) en este artículo.

## Buscar escenarios y equipos por identificador

En los widgets **[!UICONTROL Operaciones de organización]** y **[!UICONTROL Escenarios principales por operaciones]**, los campos **[!UICONTROL Escenario]** y **[!UICONTROL Equipo]** coinciden tanto en el ID como en el nombre. Cada opción muestra su ID con el nombre, por ejemplo, &quot;ID 123&quot;.

* Las listas cargan los primeros 500 escenarios y los primeros 200 equipos. Si introduce un ID que no está en la lista cargada, Fusion lo busca automáticamente después de un breve retraso.
* Si borra un escenario, también se borra el equipo que se rellenó automáticamente para ese escenario.

>[!NOTE]
>
>El filtro de escenario del registro de ejecuciones no coincide con el ID.

## Abra el panel de información de un escenario

Puede abrir el panel de información con el widget **[!UICONTROL Operaciones de organización]** filtrado para un escenario y equipo específicos.

Para ir a la página de perspectivas desde un escenario:

1. Abra la página de detalles del escenario:

   1. Haga clic en la pestaña **[!UICONTROL Escenario]** en el panel izquierdo y, a continuación, haga clic en un escenario sobre el que desea obtener detalles.

      O

      Si está trabajando en el escenario en el editor de escenarios, haga clic en la flecha izquierda ![Salir de la flecha de edición](assets/exit-editing-arrow.png) cerca de la esquina superior izquierda de la ventana.
      1. Haga clic en la ficha **Informes** cerca de la parte superior de la página.

* El widget **[!UICONTROL Operaciones de organización]** se abre filtrado a ese escenario y equipo, y la página se desplaza al widget.
* Si ha eliminado el widget de la página, aparecerá en su lugar una advertencia con el botón **[!UICONTROL Agregar widget]**.

## Usar modo oscuro

El panel de Insights y sus widgets siguen automáticamente la configuración del modo oscuro. Cuando cambia la configuración, la página se actualiza inmediatamente, sin volver a cargarse, y mantiene el estado actual. El modo claro no cambia.

## Acceso al widget de rendimiento

El widget **[!UICONTROL Rendimiento]** solo se muestra a los usuarios que tienen uno de los siguientes permisos:

* Edición de la organización en la organización activa
* Vista de organización en la página de administración

El widget se oculta en la página y en el panel **[!UICONTROL Personalizar]** para otros usuarios. Si se concede acceso a un usuario más adelante, el widget vuelve a su posición guardada. Al abrir la URL de Insights directamente, no se omite esta comprobación.

## Filtrar y triplicar ejecuciones en el registro de ejecución

Utilice el Registro de ejecución para buscar ejecuciones de escenarios que han fallado o devuelto una advertencia en toda la organización y reactivar cualquier escenario que se haya desactivado automáticamente después de errores repetidos.

1. En el Registro de ejecución, filtre las ejecuciones mediante cualquiera de las siguientes opciones:

   * [!UICONTROL Equipo]
   * [!UICONTROL Escenario]
   * [!UICONTROL Tipo de ejecución]
   * [!UICONTROL Intervalo de fecha]
   * [!UICONTROL Estado de desactivación]
   * [!UICONTROL Mensaje de error]

   Para la mayoría de los filtros, puede elegir hacer coincidir solo los valores seleccionados, o todo excepto ellos.

1. Haga clic en una ejecución para ver más detalles sobre su error.
1. Para reactivar uno o más escenarios que se desactivaron automáticamente después de errores repetidos, seleccione las ejecuciones y haga clic en **Activar**.

   >[!NOTE]
   >
   >Antes de reactivar un escenario, investigue la causa de los errores, como credenciales caducadas o un problema con el conector, para que el escenario no vuelva a fallar inmediatamente.
