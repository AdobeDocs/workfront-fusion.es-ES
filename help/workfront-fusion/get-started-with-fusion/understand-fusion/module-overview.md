---
title: Resumen del módulo
description: 'Adobe Workfront Fusion distingue cinco tipos de módulos: módulos de acción, módulos de búsqueda, módulos de déclencheur, agregadores e iteradores. Los agregadores e iteradores son para escenarios avanzados.'
author: Becky
feature: Workfront Fusion
exl-id: 4c8fe028-8425-426d-a006-f0c66871b3cd
source-git-commit: 190bfe5992fb21b789a7246c4ae732a5dc7672fa
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 22%

---

# Resumen del módulo

Adobe Workfront Fusion distingue cinco tipos de módulos:

* Módulos de acción
* Buscar módulos
* Módulos de activador
* Agregadores
* Iteradores

Los agregadores e iteradores son para escenarios avanzados.

## Módulos de acción

Los módulos de acción son el tipo más común de módulo. Un módulo de acción típico realiza una acción y devuelve un solo paquete, que luego pasa al siguiente módulo para su procesamiento.

A diferencia de los módulos de déclencheur, los módulos de acción se pueden colocar al principio, en el centro o al final de un escenario.

Los escenarios pueden contener un número ilimitado de módulos de acción, aunque un gran número de módulos (150+) puede afectar al rendimiento.

>[!BEGINSHADEBOX]

**Ejemplos:**

* **[!DNL Workfront]>[!UICONTROL Upload a file]** envía un archivo a [!DNL Workfront] y devuelve su identificador.
* **[!UICONTROL Image]>[!UICONTROL Resize]** recibe una imagen, cambia su tamaño a las dimensiones especificadas y pasa la imagen redimensionada a la siguiente acción.

>[!ENDSHADEBOX]

El tipo de acción tiene cuatro subtipos:

* Crear
* Leer
* Actualizar
* Eliminar

El subtipo Update incluye las tres operaciones siguientes:

* **Borrar el contenido de un campo**. Esta operación tiene lugar cuando el contenido del campo se evalúa como la palabra clave `erase` (no debe confundirse con `empty`).

  ![Borrar palabra clave](assets/erase-content-of-field.png)

* **No modificar el contenido de un campo**. Esta operación se realiza cuando el campo se deja vacío o cuando el contenido del campo se evalúa como vacío (representado mediante “null” en JSON).

  ![Paquete vacío](assets/leave-content-field-unchanged.png)

* **Reemplazar el contenido de un campo**. Esta operación tiene lugar en todos los demás casos que no sean los dos descritos anteriormente.

>[!NOTE]
>
>* Si no ve la palabra clave `erase` en el panel de asignación, el módulo no es un módulo de actualización o no se ha actualizado a las especificaciones más recientes para la aplicación.
>* `Empty` no cambia el contenido del campo. Si es necesario borrar el campo, se puede utilizar la siguiente fórmula:
>
>   ![Si está vacío](assets/formula-ifempty-name-erase.png)
>
>* Actualmente no se admite dejar un campo sin cambiar cuando su contenido se evalúa como vacío.

## Buscar módulos

Los módulos de búsqueda devuelven cero, uno o más paquetes, que luego pasan al siguiente módulo para su procesamiento.

Puede colocar Módulos de búsqueda al principio, al medio o al final de un escenario.

Los escenarios pueden contener un número ilimitado de módulos de búsqueda, aunque un gran número de módulos (150+) puede afectar al rendimiento.

>[!BEGINSHADEBOX]

**Ejemplo:**

**[!DNL Workfront]>[!UICONTROL Read Related Records]** lee registros que coinciden con la consulta de búsqueda especificada, en un objeto primario concreto.

>[!ENDSHADEBOX]

## Módulos de activador

Los déclencheur generan paquetes cuando se ha producido un cambio en un servicio determinado, como la creación o actualización de un registro.

Los déclencheur devuelven cero, uno o más paquetes, que luego pasan al siguiente módulo para su procesamiento.

Debido a que los Déclencheur hacen que los escenarios comiencen a ejecutarse, solo se pueden colocar al principio de un escenario.

Cada escenario solo puede contener un activador.

[!DNL Workfront Fusion] usa dos tipos de déclencheur: déclencheur de sondeo y déclencheur instantáneos.

### Activador de sondeo

Los déclencheur en encuestas encuestan con regularidad un servicio determinado aunque no haya habido cambios desde que se ejecutó el escenario anterior. Le recomendamos que programe un escenario que contenga un activador de sondeo para que se ejecute a intervalos regulares. Si hay un cambio que coincide con la configuración del déclencheur, el déclencheur devuelve paquetes que contienen información sobre el cambio. Si no hay ningún cambio que coincida con la configuración, el déclencheur no genera ningún paquete.

Para obtener instrucciones sobre cómo programar un escenario, vea [Programar un escenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md).

Los déclencheur de sondeo le permiten seleccionar el primer paquete que debe mostrarse a través de un panel que se muestra automáticamente después de guardar un déclencheur o cambiar la configuración del déclencheur. Esta selección solo afecta a la primera ejecución del módulo. Una vez que el módulo se ha ejecutado una vez, las ejecuciones posteriores solo inspeccionan los cambios que se producen después de la ejecución más reciente.

Para obtener más información, consulte [Elegir dónde se inicia un módulo de déclencheur](/help/workfront-fusion/create-scenarios/add-modules/choose-where-trigger-module-starts.md).

>[!BEGINSHADEBOX]

**Ejemplos:**

* **[!DNL Workfront]>[!UICONTROL Watch records]** devuelve registros que se agregaron recientemente después de la última vez que se ejecutó el escenario.

* **[!DNL Google Sheets]>[!UICONTROL Watch Rows]** devuelve las filas nuevas agregadas después de la última vez que se ejecutó el escenario.

>[!ENDSHADEBOX]

### Activadores instantáneos

Las déclencheur instantáneas permiten que un servicio notifique a [!DNL Workfront Fusion] un cambio inmediatamente después de que se produzca. Le recomendamos que programe un escenario que contenga un déclencheur instantáneo para que se ejecute de inmediato.

Para obtener instrucciones, consulte [Programar un escenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md).

Para obtener más información sobre cómo un déclencheur instantáneo gestiona los datos entrantes, consulte [déclencheur instantáneos (webhooks)](/help/workfront-fusion/references/modules/webhooks-reference.md).

>[!BEGINSHADEBOX]

**Ejemplos:**

* **[!DNL Workfront]>[!UICONTROL Watch Events]** devuelve información cuando se produce un determinado tipo de evento en Workfront, como la creación de una tarea.
* **[!DNL Google Sheets]>[!UICONTROL Watch Changes]** devuelve información cada vez que se actualiza una celda.

>[!ENDSHADEBOX]

## Agregadores

Un módulo Aggregator acumula varios paquetes en uno solo.

Los acumuladores solo devuelven un paquete, que luego pasa al siguiente módulo para un procesamiento posterior.

Puede colocar agregadores solo en medio de un escenario.

Los escenarios pueden contener un número ilimitado de agregadores, aunque un gran número de módulos (150+) puede afectar al rendimiento.

>[!BEGINSHADEBOX]

**Ejemplos:**

* **[!UICONTROL Archive]>[!UICONTROL Create an archive]** comprime varios archivos en un archivo zip.
* **[!UICONTROL CSV]>[!UICONTROL Aggregate to CSV]** combina varias cadenas de un archivo CSV en una sola fila.
* **[!UICONTROL Tools]>[!UICONTROL Text aggregator]** combina varias cadenas en una sola.

>[!ENDSHADEBOX]

Para obtener más información, consulte [Módulo de agregado](/help/workfront-fusion/references/modules/aggregator-module.md).

## Iteradores

Un iterador es un tipo de módulo que divide las matrices en paquetes independientes.

Los iteradores devuelven uno o más paquetes, que luego pasan al siguiente módulo para su procesamiento.

Puede colocar iteradores solamente en medio de un escenario.

Los escenarios pueden contener un número ilimitado de iteradores, aunque un gran número de módulos (150+) puede afectar al rendimiento.

>[!BEGINSHADEBOX]

**Ejemplo:**

**[!UICONTROL Email]>[!UICONTROL Retrieve attachments]** divide una matriz de archivos adjuntos en paquetes separados.

>[!ENDSHADEBOX]

Para obtener más información, consulte [Módulo iterador](/help/workfront-fusion/references/modules/iterator-module.md) y [Asignar una matriz](/help/workfront-fusion/create-scenarios/map-data/map-an-array.md).
