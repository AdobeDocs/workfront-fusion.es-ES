---
product-previous: workfront-fusion
content-type: release-notes
product-area: workfront-integrations
navigation-topic: fusion-release-activity
title: 'Actividad de la versión de Workfront Fusion: semana del 3 de mayo de 2021'
description: En esta página se describen todas las mejoras realizadas en Adobe Workfront Fusion durante la semana del martes, 03 de mayo de 2021.
author: Luke
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
hidefromtoc: true
exl-id: 8858fc79-5eda-4938-9bb5-c05be38f02bc
source-git-commit: 0e8f73afb2ab60bb1b601abf3c4f3d611e97d125
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 35%

---

# Actividad de la versión de Workfront Fusion: semana del 3 de mayo de 2021

En esta página se describen todas las mejoras realizadas en Adobe Workfront Fusion durante la semana del martes, 03 de mayo de 2021.

Para obtener una lista de todos los cambios recientes, consulte [Actividad de la versión de Adobe Workfront Fusion](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md).

Para obtener una lista de las correcciones de errores recientes en Workfront Fusion, consulte la página [Actualizaciones de mantenimiento de Workfront](https://experienceleague.adobe.com/docs/workfront-known-issues/releases/current-updates.html?lang=es) y busque cualquier actualización etiquetada como Actualización de mantenimiento de Workfront Fusion.

## El conector de Salesforce ahora puede buscar mediante SOQL

El módulo Salesforce > Buscar registros tiene ahora la opción de buscar mediante SOQL (Salesforce Object Query Language). También puede buscar utilizando las opciones disponibles anteriormente (SOSL y búsquedas simples).

## El nuevo tipo de conexión en el conector DevOps de Azure requiere menos ámbitos

Para mejorar la seguridad, hemos añadido un nuevo tipo de conector al conector de desarrollo de Workfront Fusion Azure. Ahora, al crear una conexión en un módulo DevOps de Azure, puede seleccionar entre dos tipos de conexiones:

* DevOps de Azure

  Este nuevo tipo de conexión limita los ámbitos a los que necesita específicamente Workfront Fusion.

* DevOps de Azure (solicitar todos los ámbitos)

  Este es el tipo de conexión heredada, que solicita todos los ámbitos disponibles en una conexión a Azure DevOps.

Le recomendamos que utilice el tipo de conexión DevOps de Azure en todos los escenarios nuevos que utilicen DevOps de Azure. También le recomendamos que cambie cualquier módulo de DevOps de Azure en sus escenarios existentes para utilizar el nuevo tipo de conexión. El tipo de conexión heredada de Azure DevOps (Solicitar todos los ámbitos) quedará obsoleta en un futuro próximo.
