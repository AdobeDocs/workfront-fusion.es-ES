---
title: Preguntas frecuentes sobre planificación de escenarios
description: La información de este artículo puede ser útil cuando empiece a crear escenarios en Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 6a1d672d-0bd7-4a3a-b96d-6d8b4c97522d
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 33%

---

# Preguntas frecuentes sobre planificación de escenarios

La información de este artículo puede ser útil cuando empiece a crear escenarios en Workfront Fusion.

## ¿Qué es un escenario?

### Respuesta

Un escenario define una secuencia de pasos que Adobe Workfront Fusion ejecutará. Para cada escenario, se especifica la fuente de datos, qué datos utilizar y cómo se procesarán los datos. Fusion le permite crear escenarios simples o complejos, capaces de satisfacer los casos de uso de su organización.

Para obtener más información sobre los escenarios, vea [Información general sobre escenarios](/help/workfront-fusion/get-started-with-fusion/understand-fusion/scenario-overview.md).

## ¿Cuántos módulos puedo utilizar en un escenario?

### Respuesta

Puede utilizar tantos módulos como desee en un escenario concreto. Puede separar los módulos en rutas y especificar qué datos deben fluir a través de cada ruta. También puede utilizar la salida de un módulo como entrada para otro módulo.

Aunque no hay límite en el número de módulos en un escenario, más de 150 módulos pueden afectar al rendimiento del escenario.

Para obtener más información sobre los módulos, consulte [Información general sobre módulos](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md).

## ¿Puede Workfront Fusion trabajar con archivos?

### Respuesta

Sí. Workfront Fusion puede recibir, guardar, transformar, convertir y cifrar archivos. Fusion también proporciona una amplia gama de funciones integradas diseñadas para permitir a los usuarios trabajar de forma eficaz y creativa con los datos contenidos en los archivos.

Para obtener más información sobre cómo trabajar con archivos en Fusion, consulte [Asignar un archivo entre módulos](/help/workfront-fusion/create-scenarios/map-data/map-files.md).

## Algunos activadores permiten que los escenarios se ejecuten instantáneamente. ¿Qué significa “instantáneamente”?

### Respuesta

Los escenarios pueden ejecutarse a intervalos según la programación especificada, como cada hora o cada 5 minutos. Existen activadores especiales, llamados activadores instantáneos (webhooks), que pueden iniciar un escenario inmediatamente después de recibir datos de un servicio determinado. Fusion procesa los datos recibidos inmediatamente, sin esperar a la siguiente ejecución programada.

Para obtener más información sobre la diferencia entre los déclencheur sondeados e instantáneos, consulte [módulos de Déclencheur](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#trigger-modules) en el artículo Información general del módulo.

## ¿Qué es una operación?

### Respuesta

Una operación es cualquier tarea realizada por un módulo. Por ejemplo, se produce una operación cada vez que se ejecuta un activador y cada vez que una acción realiza una tarea.

Algunos planes Fusion se basan en el número de operaciones que utiliza su organización.

Para obtener más información sobre las operaciones, consulte [Operaciones](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/operations-in-workfront-fusion.md).

## ¿Qué es la transferencia de datos?

### Respuesta

La transferencia de datos se refiere a la cantidad de datos transferidos a través de su escenario. Por ejemplo, un escenario que recupera una imagen de 100 KB de Workfront y, a continuación, la carga en un proveedor de almacenamiento de documentos. La cantidad de datos utilizados en esta situación es de 200KB.

## ¿Qué es una conexión?

### Respuesta

Una conexión es el vínculo entre su cuenta de Workfront Fusion y el servicio de terceros que desea utilizar. La conexión se puede crear al editar un escenario.

Para obtener más información, consulte [Información general sobre la conexión](/help/workfront-fusion/get-started-with-fusion/understand-fusion/connection-overview.md).

## ¿Qué son los agregadores?

### Respuesta

Un [!UICONTROL Agregador] combina datos en una sola colección. Un ejemplo de esto son los archivos que se comprimen en un archivo zip y se envían como datos adjuntos de correo electrónico.

Para obtener más información, consulte [[!UICONTROL Agregador] módulo](/help/workfront-fusion/references/modules/aggregator-module.md).

## ¿Qué sucede si dejo que Workfront Fusion procese un correo electrónico que contenga más de un archivo adjunto?

### Respuesta

Si utiliza [!UICONTROL Retrieve attachments] del módulo [!UICONTROL Email],cada archivo adjunto se enviará individualmente a través del resto de los módulos del escenario. También hay módulos similares disponibles en otras aplicaciones que reciben varios archivos a la vez.
