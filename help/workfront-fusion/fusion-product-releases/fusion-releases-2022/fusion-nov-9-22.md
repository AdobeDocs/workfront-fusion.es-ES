---
product-previous: workfront-fusion
content-type: release-notes
product-area: workfront-integrations
navigation-topic: fusion-release-activity
title: 'Actividad de la versión de Workfront Fusion: semana del 7 de noviembre de 2022'
description: En esta página se describen todas las mejoras realizadas en Adobe Workfront Fusion durante la semana del martes, 07 de noviembre de 2022.
author: Luke
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 9d58abd0-1fe7-43c8-a1ea-2fadea738590
TQID: https://experienceleague.adobe.com/iigr0fKWxXA-DvvPZVjZvIQ3s-dW6XUBWgMYaxoGZRs
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 233
ht-degree: 100%

---

# Actividad de la versión de Workfront Fusion: semana del 7 de noviembre de 2022

**Optimización de la cola de webhooks**

La cola de webhooks de Fusion se ha optimizado con esta versión. El servicio que acepta webhooks ahora está separado de la cola y otros procesos. Este cambio hace posible que Fusion procese las colas de los webhooks a una velocidad más rápida y constante.

Durante la implementación de este cambio, pudimos comprender mejor el tiempo previsto de procesamiento de registros para los eventos de webhook en cola. Se espera que la página del visor de webhooks de Fusion no tenga más de 1 minuto.

Para ver los eventos de webhook en cola, vaya a Webhooks, en la navegación de la izquierda. Los iconos de camión con un número en el numerador indican eventos de cola para ese webhook. Haga clic en el icono del camión para ver los eventos en cola.


**Ahora se desactivarán o eliminarán los webhooks que no se usen**

Hemos realizado algunos cambios en la forma en que Workfront Fusion gestiona los webhooks que no se utilizan. Ahora, los webhooks se desactivan automáticamente si se aplica cualquiera de las siguientes opciones:

* El webhook no ha estado conectado a ningún escenario durante más de 5 días.
* El webhook solo se utiliza en escenarios inactivos, que han estado inactivos durante más de 30 días.

Los webhooks desactivados se borran y no se registran automáticamente si no están conectados a ningún escenario y han permanecido en estado desactivado durante más de 30 días.
