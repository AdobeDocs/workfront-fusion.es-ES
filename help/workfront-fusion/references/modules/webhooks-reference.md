---
title: Déclencheur instantáneos (webhooks)
description: Muchos servicios proporcionan webhooks para entregar notificaciones instantáneas cada vez que se produce un determinado cambio en el servicio. Para procesar estas notificaciones, le recomendamos que utilice activadores instantáneos. En este artículo se describe el uso y la funcionalidad de los activadores instantáneos en Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 5bfda2b2-dc1c-4ff6-9236-b480bfda2e58
source-git-commit: d4bdc4005a3b7b22d64adc8ca1d20bcf534ddfd1
workflow-type: tm+mt
source-wordcount: '1182'
ht-degree: 23%

---

# Déclencheur instantáneos (webhooks)

Muchos servicios proporcionan enlaces web para enviar notificaciones instantáneas cada vez que se produce un determinado cambio (evento) en el servicio. Para procesar estos eventos, le recomendamos que utilice déclencheur instantáneas. Los déclencheur instantáneos muestran la etiqueta `Instant` en la lista de módulos de un conector determinado.

![Instantáneo](assets/instant.png)

>[!TIP]
>
>Puede comprobar la lista de módulos de un conector para ver si tiene un déclencheur instantáneo o puede comprobar la documentación del conector en [Aplicaciones Fusion y sus referencias de módulos](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).
>
>Para obtener documentación de déclencheur instantáneo de Adobe Workfront, consulte [Déclencheur](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#triggers) en el artículo Módulos de Workfront.

Si un conector no incluye un gancho web, puede realizar una de las siguientes acciones:

* Cree un webhook personalizado con el módulo Webhook.
Para obtener más información, consulte [Webhooks](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md).
* Utilice los déclencheur de sondeo para sondear periódicamente el servicio.
Para obtener más información, consulte [Programar un escenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md)

Para ver un vídeo introductorio a los webhooks en Workfront Fusion, consulte lo siguiente:

* [Introducción a Webhooks](https://video.tv.adobe.com/v/3427025/){target=_blank}
* [Webhooks intermedios](https://video.tv.adobe.com/v/3427030/){target=_blank}

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

## Ver detalles del webhook

Puede ver una lista de los webhooks en el área de Webhooks.

1. Para abrir el área de Webhooks, haga clic en el icono de Webhooks ![Webhooks](assets/webhooks-icon.png) en el panel de navegación izquierdo.

   Aquí puede ver una lista de webhooks.

   ![Lista de webhook](assets/list-of-webhooks.png)

1. Para buscar un webhook específico, ingrese el término de búsqueda en el cuadro Buscar.
1. Para copiar un gancho web, haga clic en el icono Copiar ![Copiar el icono del gancho web](assets/copy-webhook-icon.png) cerca de la dirección URL de la fila correspondiente.
1. Para deshabilitar o habilitar un webhook, deshabilite o habilite la opción en la columna Estado de la fila correspondiente a dicho webhook.
1. Para ver si una cola de webhooks está llena, marque la columna Full Queue. El número de esta columna es el número de elementos que hay actualmente en la cola.
1. Para ver las operaciones administradas por un webhook, haga clic en **Operaciones** en la columna Cola completa de ese webhook.
1. Para ver si un webhook ha caducado, marque la columna Caducado. Los webhooks caducados no están adjuntos a ningún escenario o no han recibido ningún evento durante 120 horas.
1. Para ver el escenario donde se usa un webhook, haga clic en el botón **Escenario** de la columna Escenario para ese webhook.
1. Para ver la conexión usada para este webhook, haga clic en el botón **Conexión** en la columna Conexión para ese webhook.
1. Para ocultar columnas o mostrar columnas previamente ocultas, haga clic en el icono **Columnas** ![Icono de columnas](assets/glist-column.png) y marque o desmarque los nombres de columna.


## Programar activadores instantáneos

Cuando se configura un déclencheur instantáneo, se le pide que seleccione cuándo se ejecuta.

![Configuración de horario](assets/schedule-setting.png)

Seleccione `Immediately` para ejecutar el escenario inmediatamente cuando Workfront Fusion reciba nuevos eventos del servicio. Estos eventos se envían inmediatamente a una cola y, a continuación, se procesan en el escenario de uno en uno, en el mismo orden en que se reciben los datos.

Cuando se ejecuta el escenario, se cuenta la cantidad total de eventos pendientes que esperan en la cola y el escenario realiza tantos ciclos como eventos pendientes, procesando un evento por ciclo.

Para obtener más información sobre los ciclos, vea [Ejecución de escenarios, ciclos y fases](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md).

>[!NOTE]
>
>* Un ciclo no es lo mismo que una ejecución de escenario. Puede haber varios ciclos dentro de una ejecución de escenario.
>* Cuando ejecuta un escenario con un déclencheur instantáneo programado para ejecutarse `Immediately`, se aplican las siguientes excepciones:
>
>     * El intervalo entre dos ejecuciones no está sujeto al intervalo mínimo según el plan de precios.
>
>       Por ejemplo, una vez que el escenario termina de ejecutarse, la cola del webhook se vuelve a comprobar. Si hay algún webhook pendiente, el escenario se ejecuta inmediatamente de nuevo, procesando todos los webhooks pendientes una vez más.
>   
>     * La configuración del escenario Número máximo de ciclos se ignora y se establece en 100, lo que significa que no se procesarán más de 100 webhooks pendientes durante una sola ejecución de escenario (a razón de 1 evento por ciclo).
>


Si usa cualquier otra configuración de programación distinta de [!UICONTROL Inmediatamente], el escenario se ejecutará a los intervalos especificados. Dado que se pueden agrupar varios enlaces web en la cola durante el intervalo, se recomienda establecer la opción [!UICONTROL Número máximo de ciclos] en un valor mayor que el predeterminado 1 para procesar más enlaces web en una ejecución de escenario:

1. Haga clic en el icono [!UICONTROL Configuración de escenario] ![Icono de configuración de escenario](assets/scenario-settings-icon.png) en la parte inferior del escenario.
1. En el panel **[!UICONTROL Configuración de escenario]** que aparece, escriba un número en el campo **[!UICONTROL Número máximo de ciclos]** para indicar el número de eventos de la cola que desea ejecutar cada vez que ejecute el escenario.

Los eventos que permanecen en cola se procesarán la próxima vez que se ejecute el escenario, hasta el número establecido en el campo Número máximo de ciclos.

## Protecciones de webhook

Para garantizar un buen rendimiento, Workfront Fusion dispone de las siguientes protecciones para los webhooks.

### Límites de velocidad

El límite de velocidad actual es de 5 webhooks por segundo. Si se supera el límite, se devuelve un código de estado `429`.

### Caducidad de webhooks inactivos

Se eliminará un webhook que no se haya asignado a ningún escenario durante más de 120 horas.

### Cargas útiles de webhook

Workfront Fusion almacena las cargas útiles de los ganchos web durante 30 días. Acceder a una carga útil de gancho web más de 30 días después de crearla provoca el error [!UICONTROL `Failed to read file from storage.`]

### Gestión de errores

Cuando hay un error en su escenario con un activador instantáneo, el escenario:

* Se detiene inmediatamente cuando el escenario está configurado para ejecutarse [!UICONTROL Inmediatamente].
* Se detiene después de tres intentos fallidos (tres errores) cuando el escenario está configurado para ejecutarse según lo programado.

Si se produce un error durante la ejecución del escenario, el evento se vuelve a colocar en la cola durante la fase de reversión del déclencheur instantáneo. En tal situación, puede corregir el escenario y ejecutarlo de nuevo.

Para obtener más información, consulte [Inversión](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md#rollback) en el artículo Ejecución de escenarios, ciclos y fases.

Si hay un módulo de respuesta de webhook en su escenario, el error se envía ahí. El módulo de respuesta Webhook siempre se ejecuta en último lugar (cuando la opción [!UICONTROL Confirmación automática] en la configuración de Escenario no está habilitada).

Para obtener más información, consulte [Respuesta a los webhooks](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md#responding-to-webhooks) en el artículo Webhooks.

### Desactivación de un webhook

Los webhooks se desactivan automáticamente si se aplica cualquiera de las siguientes opciones:

* El webhook no ha estado conectado a ningún escenario durante más de 5 días.
* El webhook solo se utiliza en escenarios inactivos, que han estado inactivos durante más de 30 días.

Los webhooks desactivados se eliminan y no se registran automáticamente si no están conectados a ningún escenario, y han estado en estado desactivado durante más de 30 días.

## Webhooks personalizados

Puede crear sus propios webhooks. Para obtener más información, consulte [Webhooks](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md).

## Recursos

Para obtener más información sobre los ciclos, vea [Ejecución de escenarios, ciclos y fases](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md).
