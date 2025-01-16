---
title: Licencias de Adobe Workfront Fusion
description: Adobe Workfront Fusion ofrece dos licencias diferentes que determinan la funcionalidad a la que puede acceder. Su organización eligió una de estas licencias al adquirir Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 6e2df1a0-c1f9-4833-b1c2-65efb3be9657
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 3%

---

# Licencias de Adobe Workfront Fusion

Workfront Fusion tiene dos modelos de licencias, un nuevo modelo basado en operaciones y un modelo basado en conectores heredados.

## Modelo de licencia basado en operaciones (Nuevo)

El nuevo modelo de licencias de Workfront Fusion se basa en el número de operaciones que utiliza su organización. En este modelo, todas las organizaciones tienen acceso a la misma funcionalidad.

Si su organización tiene un plan Workfront Ultimate, su instancia de Fusion está incluida en su plan y permite un número ilimitado de operaciones de Fusion por mes. Si su organización tiene un plan Workfront Prime o Select, se puede comprar Fusion y el precio se basa en el número de operaciones realizadas en un mes.

Para obtener información sobre lo que cuenta como una operación en el nuevo modelo de licencias, consulte [Operaciones](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/operations-in-workfront-fusion.md).

## Modelo de licencia basado en conectores (heredado)

En el modelo de licencia heredada de Adobe Workfront Fusion, Fusion ofrece dos licencias diferentes que determinan la funcionalidad a la que puede acceder. Su organización eligió una de estas licencias al adquirir Workfront Fusion.

* [Workfront Fusion para automatización de trabajo](#workfront-fusion-for-work-automation)
* [Workfront Fusion for Work Automation and Integration](#workfront-fusion-for-work-automation-and-integration)

Para saber qué tipo de licencia de Workfront Fusion tiene su organización, póngase en contacto con su administrador de Workfront Fusion.

### Workfront Fusion para automatización de trabajo

* [Ventajas de Workfront Fusion para la automatización del trabajo](#benefits-of-workfront-fusion-for-work-automation)
* [Conectores y módulos disponibles para Workfront Fusion for Work Automation](#connectors-and-modules-available-for-workfront-fusion-for-work-automation)
* [Ejemplo de Workfront Fusion para automatización de trabajo](#example-of-workfront-fusion-for-work-automation)

#### Ventajas de Workfront Fusion para la automatización del trabajo

Una licencia de Workfront Fusion for Work Automation le permite automatizar sus flujos de trabajo de [!DNL Workfront]. Con Workfront Fusion para la automatización del trabajo, puede crear escenarios para automatizar los procesos de trabajo únicos de su organización.

Entre los beneficios de automatizar los procesos de [!DNL Workfront] se incluyen los siguientes:

* La automatización es más rápida y menos propensa a errores.
* Los flujos de trabajo que no requieren ninguna decisión o que tienen decisiones se basan en una lógica simple, como si/entonces, son buenos candidatos para la automatización.
* La automatización puede abordar necesidades específicas en flujos de trabajo utilizados por su organización que no se abordan directamente en el producto de Workfront.

#### Conectores y módulos disponibles para Workfront Fusion for Work Automation

Con la licencia de Workfront Fusion para automatización de trabajo, tiene acceso a lo siguiente:

* Adobe Workfront
* Revisión de Workfront
* Webhooks
* Módulos de herramientas y transformadores como:

   * Archivo
   * CSV
   * Almacenes de datos
   * Imagen
   * JSON
   * Matemáticas
   * MIME
   * XML

#### Ejemplo de Workfront Fusion para automatización de trabajo

El siguiente ejemplo muestra un flujo de trabajo que:

1. Inspecciona un cambio de campo
1. Obtiene información sobre el objeto al que está adjunto el campo, incluido a quién está asignado el objeto
1. Envía una notificación sobre el cambio de campo al usuario al que está asignado el objeto

![Ejemplo de automatización](assets/fusion-template-example.png)

### Workfront Fusion for Work Automation and Integration

* [Ventajas de Workfront Fusion para la automatización e integración del trabajo](#benefits-of-workfront-fusion-for-work-automation-and-integration)
* [Conectores y módulos disponibles para Workfront Fusion para la automatización e integración del trabajo](#connectors-and-modules-available-for-workfront-fusion-for-work-automation-and-integration)
* [Ejemplo de integración y automatización de trabajo de Workfront Fusion](#example-of-workfront-fusion-for-work-automation-and-integration)

#### Ventajas de Workfront Fusion para la automatización e integración del trabajo {#benefits-of-workfront-fusion-for-work-automation-and-integration}

Una licencia de Workfront Fusion para automatización e integración de trabajo le permite acceder a todas las funcionalidades de la licencia de Workfront Fusion para automatización de trabajo. Además, esta licencia le permite utilizar otras aplicaciones y servicios en sus situaciones. Por ejemplo, puede utilizar Workfront Fusion para automatizar un proceso que importa tickets de Jira y, a continuación, convertirlos en tareas en Workfront. También puede utilizar los conectores HTTP o SFTP para conectarse a casi cualquier servicio web, aunque Workfront Fusion no tenga un conector específico para él.

Entre las ventajas de una licencia de integración y automatización de trabajo de Workfront Fusion se incluyen las siguientes:

* Workfront Fusion para la automatización e integración del trabajo incluye todas las ventajas asociadas con Workfront Fusion para la automatización del trabajo
* La integración reduce la necesidad de saltar dentro y fuera de varias aplicaciones al completar un flujo de trabajo.
* La automatización de la transferencia de datos entre aplicaciones es más rápida y menos propensa a errores que la transferencia manual de datos

#### Conectores y módulos disponibles para Workfront Fusion para la automatización e integración del trabajo

Para obtener una lista de los conectores dedicados disponibles, consulte [Referencias de las aplicaciones Fusion y sus módulos: índice de artículos](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).

>[!IMPORTANT]
>
>Workfront Fusion puede conectarse a casi cualquier servicio web. Si la aplicación con la que desea trabajar no tiene un conector específico, puede utilizar los conectores [!UICONTROL HTTP], [!UICONTROL SFTP] o [!UICONTROL JSON] para conectarse directamente al servicio web.

#### Ejemplo de integración y automatización de trabajo de Workfront Fusion

El siguiente ejemplo muestra un flujo de trabajo que:

1. Inspecciona una hoja de cálculo para nuevos usuarios
1. Comprueba si el usuario existe en [!DNL Workfront]
1. Crea el usuario en [!DNL Workfront] si el usuario no existe
1. Vuelve a cargar el identificador de usuario [!DNL Workfront] en la hoja de cálculo.

![Ejemplo de escenario de automatización](assets/fusion-integration-example.png)
