---
title: Editar webhooks
description: Puede editar los webhooks existentes para los conectores de Workfront y Workfront Planning.
author: Becky
feature: Workfront Fusion
source-git-commit: 2561c911b9b542a7b143fae745baf4e1de45be38
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 5%

---

# Editar webhooks

Puede editar los webhooks existentes. Los escenarios que utilicen estos webhooks utilizarán la nueva configuración en adelante, lo que elimina la necesidad de crear un nuevo webhook y asignarlo manualmente a todos los escenarios afectados.

Los webhooks solo se pueden editar para los siguientes conectores:

* Workfront
* Workfront Planning

>[!IMPORTANT]
>
>Tenga en cuenta lo siguiente al actualizar un webhook:
>
>* Las suscripciones a eventos de Workfront tratan el webhook editado como una suscripción nueva. El historial de suscripción de eventos no se conserva para la configuración de ganchos web anterior, ya que se considera una suscripción de evento independiente.
>* Es posible que el cambio de la suscripción de evento antigua a la nueva no esté perfectamente sincronizado. Por lo tanto, es posible recibir un evento dos veces (si la nueva suscripción empieza a ejecutarse antes de que la anterior se detenga) o perderse un evento (si la antigua suscripción se detiene antes de que la nueva comience a ejecutarse).

## Editar un webhook

Puede editar los webhooks desde un escenario o desde la lista de Webhooks.

### Edición de un webhook en un escenario

>[!NOTE]
>
>Esta funcionalidad solo está disponible para escenarios que tienen un módulo de déclencheur instantáneo de Workfront o Workfront Planning.

1. Vaya al escenario que incluye el webhook que desea editar.
1. En el módulo de déclencheur del escenario, haga clic en el menú desplegable situado junto al campo Webhook y seleccione **Editar elemento**.

   Se abre la ventana de configuración del gancho web, rellenada con la configuración existente.

1. Realice los cambios que desee en el webhook.
1. Haga clic en **Guardar** para guardar el webhook y volver al módulo.

### Editar un webhook desde la lista Webhooks

1. En el panel de navegación de la izquierda, seleccione **Webhooks** ![Icono de Webhooks](assets/webhooks-icon.png).
1. Haga clic en la casilla de verificación situada junto al webhook que desee editar.
1. En el banner azul en la parte inferior de la pantalla, haz clic en **Editar**.
1. Realice los cambios que desee en el webhook.
1. Haga clic en **Guardar** para guardar el webhook y volver a la lista de webhooks.

