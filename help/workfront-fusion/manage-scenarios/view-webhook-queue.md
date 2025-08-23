---
title: cola de k
description: Muchos servicios proporcionan webhooks para entregar notificaciones instantáneas cada vez que se produce un determinado cambio en el servicio. Los déclencheur instantáneos, también conocidos como webhooks, pueden utilizar estos eventos para comenzar escenarios. Los eventos pasan a la cola del gancho web mientras esperan su procesamiento, como cuando el escenario ya se está ejecutando. Puede ver la cola del gancho web.
author: Becky
feature: Workfront Fusion
exl-id: 04aed0cb-e837-4c81-8eb1-113075d2ada8
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 32%

---

# Ver la cola del webhook

Muchos servicios proporcionan webhooks para entregar notificaciones instantáneas cada vez que se produce un determinado cambio en el servicio. Los déclencheur instantáneos, también conocidos como webhooks, pueden utilizar estos eventos para comenzar escenarios. Los eventos pasan a la cola del gancho web mientras esperan su procesamiento, como cuando el escenario ya se está ejecutando. Puede ver la cola del gancho web.

Los datos del gancho web entrante siempre se almacenan en la cola, independientemente de cómo haya configurado la opción Los datos son confidenciales en el panel de configuración de escenario. Una vez que los datos se procesan en un escenario, se eliminan de forma permanente de la cola.

Para obtener más información sobre los webhooks, consulte [déclencheur instantáneos (webhooks)](/help/workfront-fusion/references/modules/webhooks-reference.md).

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

## Ver la cola del webhook

Todos los mensajes de los webhooks entrantes se almacenan en la cola del webhook.

Si un escenario tiene actualmente una cola, se muestra un banner en ese escenario:

![Banner de cola](assets/queue-banner.png)

Para ver la cola de un gancho web:

1. Haga clic en **[!UICONTROL webhooks]** en el menú de la izquierda.
1. Busque el webhook para el que desea ver la cola.
1. Busque el número de eventos en el botón Eventos recibidos.

   ![Cola de ganchos web](assets/webhook-queue.png)

1. Haga clic en el botón para ver detalles sobre los eventos de la cola.
