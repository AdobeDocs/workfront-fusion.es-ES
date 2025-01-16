---
title: Ejecución de escenarios, ciclos y fases
description: En este artículo se describen los eventos que se producen mientras se ejecuta un escenario de  [!DNL Adobe Workfront Fusion] , como la inicialización, las operaciones, las confirmaciones y las reversiones.
author: Becky
feature: Workfront Fusion
exl-id: abf41be5-df32-4eaf-b3f4-93ddf005bfe3
source-git-commit: fe503c27bc4e3beb5645f0efa7c2097297f19190
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 31%

---

# Ejecución de escenarios, ciclos y fases

Cada ejecución de escenario comienza con la fase de inicialización, continúa con al menos un ciclo compuesto por las fases de operación y compromiso/reversión, y finaliza con la fase de finalización

* Inicialización
* Ciclo núm. 1
   * Operación (lectura o escritura)
   * Confirmar o revertir
* Ciclo núm. 2
   * Operación (lectura o escritura)
   * Confirmar o revertir
* ...
* #n de ciclo
   * Operación (lectura o escritura)
   * Confirmar o revertir
* Finalización

En una escala menor, cada módulo también sigue estas fases. La información sobre las fases del módulo se encuentra en la información del paquete procesado, en la burbuja numerada situada en la parte superior derecha de cada módulo después de que se haya ejecutado el escenario. Para obtener más información sobre cómo buscar información de paquetes procesados, consulte [Información sobre paquetes procesados](/help/workfront-fusion/references/scenarios/scenario-execution-flow.md#information-about-processed-bundles) en el artículo Flujo de ejecución de escenario.

Puede encontrar información sobre las fases de escenario más grandes en los detalles de ejecución.

## Fases de ejecución de escenarios

### Inicialización

Durante la fase de inicialización, se crean y comprueban todas las conexiones necesarias (conexión a una base de datos, servicio de correo electrónico, etc.) para garantizar que el módulo sea capaz de realizar las operaciones previstas.

### Ciclos

Cada ciclo representa una unidad de trabajo indivisible compuesta por una serie de operaciones, cada una con una confirmación o reversión.

Puede establecer el número máximo de ciclos en el panel [!UICONTROL scenario settings]. El número predeterminado es 1.

* [Operación](#operation)
* [Confirmar](#commit)
* [Reversión](#rollback)

#### Operación

Durante la fase de operación, se realiza una operación de lectura o escritura:

* Una operación de lectura consiste en obtener datos de un servicio que luego procesan otros módulos de acuerdo con un escenario predefinido. Por ejemplo, el módulo [!UICONTROL Workfront] >[!UICONTROL Watch records] devuelve nuevos paquetes (registros) creados desde la última ejecución del escenario.
* Una operación de escritura consiste en enviar datos a un servicio determinado para un procesamiento posterior. Por ejemplo, el módulo [!DNL Workfront] >[!UICONTROL Upload Document] carga un archivo en Workfront.

#### Confirmar

Si la fase de operación es correcta, comienza la fase de confirmación durante la cual se confirman todas las operaciones realizadas por los módulos. Esto significa que [!DNL Workfront Fusion] envía información a todos los servicios involucrados en la fase de operación sobre su éxito.

### Reversión

Si se produce un error durante la fase de operación o confirmación en cualquier módulo, la fase se anula y se inicia la fase de reversión, lo que anula todas las operaciones durante el ciclo determinado.

>[!IMPORTANT]
>
>Todos los módulos de [!DNL Workfront Fusion] que admiten la reversión (también conocida como transaccionalidad) están marcados con la etiqueta ACID.
>
>![](assets/acid-modules.png)
>
>Los módulos no marcados con esta etiqueta no se pueden revertir a su estado inicial cuando se producen errores en otros módulos. Un ejemplo típico de un módulo que no es ACID es la acción [!UICONTROL Email] >[!UICONTROL Send an Email]. Una vez enviado el correo electrónico, no se puede deshacer el envío.

### Finalización

Durante la fase de finalización, las conexiones abiertas (por ejemplo, conexiones FTP, conexiones de base de datos, etc.) se cierran y se completa el escenario.

## Recursos

Para obtener más información, consulte [Configurar opciones de escenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md).
