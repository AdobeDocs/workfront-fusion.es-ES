---
title: 'Actividad de la versión de Workfront Fusion: &nbsp;semana del 30 de agosto de 2021'
description: 'Actividad de la versión de Workfront Fusion: &nbsp;semana del 30 de agosto de 2021'
author: Luke
draft: Probably
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
hidefromtoc: true
exl-id: cac11147-5b3d-477b-869b-e255528c4bec
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 100%

---

# Actividad de la versión de Workfront Fusion: semana del 30 de agosto de 2021

Esta página describe todas las mejoras realizadas en Adobe Workfront Fusion durante la semana del 30 de agosto de 2021.

Para obtener una lista de todos los cambios recientes, consulte [Actividad de la versión de Adobe Workfront Fusion](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md).

Para obtener una lista de las correcciones de errores recientes en Workfront Fusion, consulte la página [Actualizaciones de mantenimiento de Workfront](https://experienceleague.adobe.com/docs/workfront-known-issues/releases/current-updates.html?lang=es) y busque cualquier actualización etiquetada como Actualización de mantenimiento de Workfront Fusion.

## Filtrar eventos que activan el módulo Workfront > Ver eventos

1. Configure un filtro personalizado para los eventos que activan el módulo Workfront > Ver eventos

   Para reducir el número de ejecuciones de escenarios innecesarias, hemos actualizado el módulo Workfront > Ver registros para habilitar el filtrado de eventos. Ahora, puede establecer un filtro cuando cree un webhook. Esto permite que el escenario se active únicamente cuando el evento cumpla determinados criterios.

   El filtro de eventos ofrece actualmente las siguientes operaciones:

   * Igual: activa un escenario solo cuando un evento coincida con las condiciones del filtro. Por ejemplo, puede configurar un filtro que active un escenario solo si el evento se produce en un proyecto específico.
   * No es igual: activa un escenario solo si un evento no coincide con las condiciones del filtro. Por ejemplo, puede crear un filtro que active un escenario solo si el problema en el que se produce un evento no tiene el estado Cerrado.

   Anteriormente, el módulo Observar registros recuperaba todos los registros. Los usuarios solo podían filtrar configurando filtros más adelante en el escenario.

   Para aprovechar el filtrado de eventos, cree un nuevo webhook en el módulo Ver eventos. Actualmente, no es posible editar los webhooks existentes para incluir esta funcionalidad. Le recomendamos encarecidamente que cree nuevos webhooks utilizando filtros de evento para sus escenarios existentes.

1. Filtrar los eventos activados por la conexión actual.

   Para que sus webhooks sean más fáciles de configurar para el módulo Workfront > Ver eventos, hemos incluido el filtro de eventos más común. Ahora, el webhook tiene la opción de filtrar cualquier cambio realizado por módulos usando la conexión especificada para el módulo Ver eventos. En otras palabras, con este filtro habilitado, cualquier cambio realizado por el usuario de Workfront asociado con esa conexión no podrá activar el escenario.

   Anteriormente, este filtro no estaba disponible. Por lo tanto, era más fácil para los cambios realizados en los módulos de Workfront activar los escenarios que contenían esos módulos, lo que provocaba que los escenarios se activasen ellos mismos en bucle.
