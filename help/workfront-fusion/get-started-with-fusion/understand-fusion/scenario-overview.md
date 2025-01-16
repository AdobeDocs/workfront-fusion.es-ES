---
title: Información general del escenario
description: Adobe Workfront Fusion requiere una licencia Adobe Workfront Fusion y de Adobe Workfront.
author: Becky
feature: Workfront Fusion
exl-id: de81ad4c-27e5-4b6c-acf0-f01a8c85922e
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 27%

---

# Información general del escenario

La función de Adobe Workfront Fusion es automatizar sus procesos para que los usuarios no tengan que dedicar tanto tiempo a tareas rutinarias. Funciona vinculando acciones dentro de las aplicaciones y servicios y entre ellos para crear un escenario que transfiera y transforme los datos automáticamente. El escenario que crea ve los datos de una aplicación o servicio y los procesa para proporcionar el resultado deseado.

Un escenario se compone de una serie de módulos que indican cómo se deben transformar los datos dentro de una aplicación o transferirse entre aplicaciones y servicios web.

## Información general sobre elementos de escenario

Se crea un escenario de diferentes elementos. Entender la terminología de estos elementos facilita el uso de la documentación.

* [Escenario](#scenario)
* [Activador](#trigger)
* [Módulo](#module)
* [Ruta](#route)
* [Segmento de escenario](#scenario-segment)
* [Conector](#connector)

### Escenario

Un **escenario** es una serie de pasos automatizados creados por el usuario para mover y manipular datos. El término &quot;escenario&quot; hace referencia a todo el grupo de pasos conectados.

![Escenario](assets/entire-scenario-scenario.png)

### Activador

Un escenario comienza con un **déclencheur**. El déclencheur inspecciona la existencia de datos nuevos y actualizados e inicia el escenario cuando se aplican determinadas condiciones configuradas en el módulo. Los déclencheur se pueden configurar para que inicien un escenario según una programación (sondeo) o siempre que se produzcan cambios en los datos (instantáneo).

![Déclencheur](assets/scenario-trigger.png)

### Módulo

El déclencheur va seguido de **módulos**. Un módulo representa un solo paso en un escenario que realiza una acción específica. Los módulos se configuran y encadenan para crear escenarios.

![Módulo](assets/scenario-module.png)

### Ruta

Un escenario se puede dividir en **rutas**. Una ruta es una sección del escenario que puede utilizarse o no para un conjunto determinado de datos. Las rutas se configuran mediante un módulo de enrutador y filtros.

![Ruta](assets/scenario-route.png)

### Segmento de escenario

Un segmento de escenario es una sección de un escenario que consta de una serie de módulos contiguos que se conectan a la misma aplicación. Los segmentos de escenario suelen representar un flujo de trabajo corto en la aplicación.

![Segmento de escenario](assets/scenario-segment.png)

### Conector

Un conector es el conjunto de módulos de una aplicación determinada. Workfront Fusion ofrece conectores a muchas aplicaciones de trabajo comunes, como Workfront, Salesforce y Jira, así como conectores genéricos que pueden utilizarse para cualquier servicio web.

![Conectores](assets/scenario-connectors.png)

## Ejemplos

Expanda las siguientes secciones para ver escenarios de ejemplo y sus explicaciones.

+++**Automatizar procesos en Adobe Workfront**

Workfront Fusion le permite automatizar flujos de trabajo simples o complejos dentro de Workfront, lo que ahorra tiempo y garantiza que el proceso se ejecute de forma coherente.

En este ejemplo, el escenario se activa cuando un campo especificado cambia en una tarea o problema en [!DNL Workfront]. Cuando se activa, el escenario obtiene información del proyecto relacionado y crea una actualización adaptada para una persona asignada a una función específica en el proyecto.

![](assets/fusion-template-example.png)

+++

+++**Conectando Workfront a otra aplicación o servicio web**

>[!NOTE]
>
>Si su organización utiliza el modelo de licencias heredado, su organización debe tener una licencia de integración y automatización de trabajo de Workfront Fusion para conectarse a otras aplicaciones.

Workfront Fusion puede conectarse a otras aplicaciones y servicios web. Puede acceder, importar, manipular o exportar datos de otras aplicaciones, integrándolos con Workfront o entre sí.

Muchas aplicaciones tienen conectores de [!DNL Workfront Fusion] dedicados. Si no hay ningún conector específico para la aplicación a la que desee acceder, puede utilizar los módulos HTTP o de la aplicación de Workfront SOAP Fusion para conectarse a la aplicación a través de su API.

En este ejemplo, el escenario se activa cuando se añade un usuario a una hoja de cálculo de [!DNL Excel]. El escenario comprueba si el usuario está en [!DNL Workfront]. Si no es así, el escenario creará el usuario en [!DNL Workfront] y volverá a añadir su ID de usuario de Workfront a la hoja de cálculo.

![](assets/fusion-integration-example.png)

Para obtener una lista de conectores dedicados, consulte [Referencias de aplicaciones Fusion y sus módulos: índice de artículos](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).


>[!IMPORTANT]
>
>[!DNL Adobe Workfront Fusion] puede conectarse a casi cualquier servicio web. Si la aplicación con la que desea trabajar no tiene un conector [!DNL Workfront Fusion] dedicado, utilice conectores universales para conectarse a la aplicación o al servicio.
>
>Para obtener una lista de conectores universales, consulte [Conectores universales](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#universal-connectors)

+++

## Referencias

* Para ver un glosario de términos utilizados en Workfront Fusion, consulte [glosario de Adobe Workfront Fusion](/help/workfront-fusion/get-started-with-fusion/understand-fusion/fusion-glossary.md).
* Para empezar a crear un escenario de práctica, vea [Crear un escenario básico](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md).
* Para obtener información sobre la creación y administración de escenarios, consulte los artículos que se enumeran en:
   * [Crear escenarios](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)
   * [Administrar escenarios](/help/workfront-fusion/manage-scenarios/manage-scenarios-toc.md)
