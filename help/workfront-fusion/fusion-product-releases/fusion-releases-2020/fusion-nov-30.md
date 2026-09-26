---
product-previous: workfront-fusion
content-type: release-notes
product-area: workfront-integrations
keywords: fusion
navigation-topic: fusion-release-activity
title: 'Actividad de la versión de Workfront Fusion: semana del martes, 30 de noviembre de 2020'
description: En esta página se describen todas las mejoras realizadas en Adobe Workfront Fusion durante la semana del martes, 30 de noviembre de 2020.
author: Luke
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 76cc14b3-ffec-4d49-b471-f3eb9dd89658
TQID: 'https://experienceleague.adobe.com/1y9rppDRn9QYIcG5SJyNfVcyi7eHbGK-NcrF-hWjX-Y'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
    internal-label: Integrations
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
  - id: d968a1bc-9a90-4926-a531-bcf272c32aad
    internal-label: Administration
subfeature_v2:
  - id: a29813d3-f0cc-4b60-9396-13b558370803
    internal-label: Product announcements
source-git-commit: 01689332f97c15b317e686d11a27cb4dc7e2e8bd
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 89%
---
# Actividad de la versión de Workfront Fusion: semana del martes, 30 de noviembre de 2020

En esta página se describen todas las mejoras realizadas en Adobe Workfront Fusion durante la semana del martes, 30 de noviembre de 2020.

Para obtener una lista de todos los cambios recientes, consulte [Actividad de la versión de Adobe Workfront Fusion](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md).

Para obtener una lista de las correcciones de errores recientes en Workfront Fusion, consulte la página [Actualizaciones de mantenimiento de Workfront](https://experienceleague.adobe.com/docs/workfront-known-issues/releases/current-updates.html?lang=es) y busque cualquier actualización etiquetada como Actualización de mantenimiento de Workfront Fusion.

## Límite de velocidad para los webhooks de Workfront Fusion 2.0.

Hemos introducido una nueva protección de rendimiento para Workfront Fusion 2.0. Ahora, los webhooks tienen un límite de 100 solicitudes por segundo. Cuando se alcanza este límite, Workfront Fusion 2.0 envía un estado 429 (Demasiadas solicitudes).

Anteriormente, las solicitudes de webhook no estaban limitadas.


## Añadir un formulario personalizado a un objeto de Workfront en Workfront Fusion 2.0

Para permitirle añadir formularios personalizados a objetos de Workfront Fusion 2.0, hemos añadido la acción AssignCategories a Workfront > Varias. Módulo de acción.

Anteriormente, no era posible utilizar un módulo de Workfront Fusion 2.0 para añadir un formulario personalizado a un objeto en Workfront.
