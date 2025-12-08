---
title: Información general del módulo
description: 'Adobe Workfront Fusion distingue cinco tipos de módulos: módulos de acción, módulos de búsqueda, módulos de activador, agregadores e iteradores. Los agregadores e iteradores son para escenarios avanzados.'
author: Becky
feature: Workfront Fusion
exl-id: 4c8fe028-8425-426d-a006-f0c66871b3cd
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: ht
source-wordcount: '917'
ht-degree: 100%

---

# Información general del módulo

Adobe Workfront Fusion distingue cinco tipos de módulos:

* Módulos de acción
* Módulos de búsqueda
* Módulos de activador
* Agregadores
* Iteradores

Los agregadores e iteradores son para escenarios avanzados.

## Módulos de acción

Los módulos de acción son el tipo más común de módulo. Un módulo de acción típico lleva a cabo una acción y devuelve un solo paquete, que luego pasa al siguiente módulo para su procesamiento.

A diferencia de los módulos de activador, los de acción se pueden colocar al principio, al medio o al final de un escenario.

Los escenarios pueden contener un número ilimitado de módulos de acción, aunque un gran número de módulos (más de 150) puede afectar al rendimiento.

>[!BEGINSHADEBOX]

**Ejemplos:**

* **Workfront > [!UICONTROL Cargar un archivo]** envía un archivo a Workfront y devuelve su identificador.
* **[!UICONTROL Imagen] > [!UICONTROL Cambiar tamaño]** recibe una imagen, la cambia a las dimensiones especificadas y pasa la imagen cambiada a la siguiente acción.

>[!ENDSHADEBOX]

El tipo de acción tiene cuatro subtipos:

* Crear
* Leer
* Actualizar
* Eliminar

El subtipo Actualizar incluye las tres operaciones siguientes:

* **Borrar el contenido de un campo**. Esta operación tiene lugar cuando el contenido del campo se evalúa como la palabra clave `erase` (no confundir con `empty`).

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
>* Actualmente, no es posible dejar un campo sin cambiar cuando su contenido se evalúa como vacío.

## Módulos de búsqueda

Los módulos de búsqueda devuelven cero, uno o más paquetes que luego pasan al siguiente módulo para su procesamiento.

Puede colocar módulos de búsqueda al principio, al medio o al final de un escenario.

Los escenarios pueden contener un número ilimitado de módulos de búsqueda, aunque un gran número de módulos (más de 150) puede afectar al rendimiento.

>[!BEGINSHADEBOX]

**Ejemplo:**

**Workfront > [!UICONTROL Leer registros relacionados]** lee los registros que coinciden con la consulta de búsqueda especificada en un objeto principal concreto.

>[!ENDSHADEBOX]

## Módulos de activador

Los activadores generan paquetes cuando se ha producido un cambio en un servicio determinado, como la creación o actualización de un registro.

Los activadores puede devolver cero, uno o más paquetes que luego pasan al siguiente módulo para su procesamiento.

Debido a que los activadores hacen que los escenarios comiencen a ejecutarse, solo se pueden colocar al principio de un escenario.

Cada escenario solo puede contener un activador.

Workfront Fusion utiliza dos tipos de activadores: de sondeo e instantáneos.

### Activadores de sondeo

Los activadores de sondeo sondean de manera regular un servicio determinado, aunque no haya habido cambios desde la ejecución anterior del escenario. Le recomendamos que programe un escenario que contenga un activador de sondeo para que se ejecute a intervalos regulares. Si hay un cambio que coincide con la configuración del activador, este devuelve paquetes que contienen información sobre el cambio. Si no se produce ningún cambio que coincida con la configuración, el activador no genera ningún paquete.

Para obtener más información sobre cómo programar un escenario, consulte [Programar un escenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md).

Los activadores de sondeo le permiten seleccionar el primer paquete a generar mediante un panel que se muestra automáticamente después de guardar un activador o cambiar su configuración. Esta selección solo afecta a la primera ejecución del módulo. Una vez que el módulo se ha ejecutado una vez, las ejecuciones posteriores solo inspeccionan los cambios que se producen después de la ejecución más reciente.

Para obtener más información, consulte [Elegir dónde se inicia un módulo de activador](/help/workfront-fusion/create-scenarios/add-modules/choose-where-trigger-module-starts.md).

>[!BEGINSHADEBOX]

**Ejemplos:**

* **Worfront > [!UICONTROL Ver registros]** devuelve registros que se han añadido recientemente desde la última vez que se ejecutó el escenario.

* **[!DNL Google Sheets]> [!UICONTROL Ver filas]** devuelve las nuevas filas añadidas desde la última vez que se ejecutó el escenario.

>[!ENDSHADEBOX]

### Activadores instantáneos

Los activadores instantáneos permiten que un servicio notifique a Workfront Fusion un cambio inmediatamente después de que se produzca. Le recomendamos que programe un escenario que contenga un activador instantáneo para que se ejecute de inmediato. 

Para obtener instrucciones, consulte [Programar un escenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md).

Para obtener más información sobre cómo un activador instantáneo gestiona los datos entrantes, consulte [Activadores instantáneos (webhooks)](/help/workfront-fusion/references/modules/webhooks-reference.md).

>[!BEGINSHADEBOX]

**Ejemplos:**

* **Workfront > [!UICONTROL Ver eventos]** devuelve información cuando se produce un determinado tipo de evento en Workfront, como la creación de una tarea.
* **[!DNL Google Sheets]> [!UICONTROL Observar cambios]** devuelve información cada vez que se actualiza una celda.

>[!ENDSHADEBOX]

## Agregadores

Un módulo agregador acumula varios paquetes en uno solo.

Cada agregador devuelve solo un paquete, que luego pasa al siguiente módulo para su posterior procesamiento.

Puede colocar agregadores solo en medio de un escenario.

Los escenarios pueden contener un número ilimitado de agregadores, aunque un gran número de módulos (más de 150) puede afectar al rendimiento.

>[!BEGINSHADEBOX]

**Ejemplos:**

* **[!UICONTROL Archivo] > [!UICONTROL Crear un archivo]** comprime varios archivos en un archivo zip.
* **[!UICONTROL CSV] > [!UICONTROL Agregado a CSV]** combina varias cadenas de un archivo CSV en una sola fila.
* **[!UICONTROL Herramientas] > [!UICONTROL Agregador de texto]** combina varias cadenas en una sola.

>[!ENDSHADEBOX]

Para obtener más información, consulte [Módulo agregador](/help/workfront-fusion/references/modules/aggregator-module.md).

## Iteradores

Un iterador es un tipo de módulo que divide las matrices en paquetes independientes.

Los iteradores devuelven uno o más paquetes, que luego pasan al siguiente módulo para su procesamiento.

Puede colocar iteradores solamente en medio de un escenario.

Los escenarios pueden contener un número ilimitado de iteradores, aunque un gran número de módulos (más de 150) puede afectar al rendimiento.

>[!BEGINSHADEBOX]

**Ejemplo:**

**[!UICONTROL Correo electrónico] > [!UICONTROL Recuperar archivos adjuntos]** divide una matriz de archivos adjuntos en paquetes separados.

>[!ENDSHADEBOX]

Para obtener más información, consulte [Módulo iterador](/help/workfront-fusion/references/modules/iterator-module.md) y [Asignar una matriz](/help/workfront-fusion/create-scenarios/map-data/map-an-array.md).
