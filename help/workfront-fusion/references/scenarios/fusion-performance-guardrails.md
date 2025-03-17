---
title: Protecciones de rendimiento de Fusion
description: La automatización del trabajo requiere un procesamiento rápido, por lo que [!DNL Adobe Workfront Fusion] está diseñado para ofrecer un alto rendimiento. Dado que los escenarios de larga duración pueden ralentizar el ritmo de su trabajo, hemos diseñado  [!DNL Workfront Fusion] con protecciones que preservan el rendimiento y limitan el tiempo de ejecución, el tamaño de los datos y otros parámetros de escenario. [!DNL Workfront Fusion] los diseñadores deben tener en cuenta estas protecciones e incorporarlas en sus prácticas de diseño.
author: Becky
feature: Workfront Fusion
exl-id: d142a521-edbc-4d7b-b5cd-872a9d3d2e1c
source-git-commit: 1253470a23a2a9124824d5ab1ff2b5013d773517
workflow-type: tm+mt
source-wordcount: '880'
ht-degree: 64%

---

# Protecciones de rendimiento Fusion

La automatización del trabajo requiere un procesamiento rápido, por lo que [!DNL Adobe Workfront Fusion] está diseñado para ofrecer un alto rendimiento. Como los escenarios de larga duración pueden ralentizar el ritmo de su trabajo, [!DNL Workfront Fusion] se ha diseñado con protecciones que preservan el rendimiento y que limitan el tiempo de ejecución, el tamaño de los datos y otros parámetros de escenario. Los diseñadores de escenarios de [!DNL Workfront Fusion] deben tener en cuenta estas protecciones e incorporarlas en sus prácticas de diseño.

## Navegadores

* Workfront Fusion solo admite exploradores basados en Chrome.

## Escenarios

* El tiempo de espera de ejecución del escenario predeterminado es de **40 minutos**. Cuando la ejecución alcanza este tiempo de espera, [!DNL Workfront Fusion] interrumpe la ejecución del escenario después del siguiente ciclo u operación, según el escenario. Esto obliga al escenario a detenerse poco después de alcanzar el límite de 40 minutos
* El tamaño máximo de un modelo de escenario es de **5 MB**, pero se recomienda mantener el tamaño de escenario por debajo de **3 MB**.

  Los módulos de aplicaciones que crean o actualizan datos con una gran cantidad de campos pueden causar modelos muy grandes.

   * Al usar la aplicación [!DNL Workfront], asegúrese de seleccionar solo los campos necesarios para los casos de uso de creación o actualización.
   * Cuando utilice otras aplicaciones, utilice módulos de API personalizados para interactuar con cualquier tipo de registro que tenga un gran número de campos.

* Aunque no hay límite para el número de módulos en un escenario, los escenarios con más de 150 módulos afectan negativamente al rendimiento del sistema [!DNL Workfront Fusion]. Por este motivo, no se recomienda crear escenarios con más de 150 módulos.

## Operaciones

* El tiempo de espera de operación predeterminado suele ser de **40 segundos**.

<!--
* The operation timeout for calls to Adobe Workfront is **120 seconds**.
-->

## Archivos

* La capacidad total de procesamiento de archivos de Fusion es de **1 GB**. El límite se basa en el coste total de la memoria. Cada operación contribuye a ese coste. Si se descarga y carga un solo archivo de 400 MB, el coste total de la capacidad del archivo sería de 800 MB.
* Las organizaciones del plan Workfront Ultimate tienen acceso a un mayor procesamiento de archivos que supera los 1 GB. La plataforma Fusion puede admitir archivos individuales de hasta 15 GB para una sola acción (por ejemplo, cargar archivo), pero hay otros factores que afectan a la transferencia de datos. El límite de tamaño de archivo de una sola acción depende del servicio web al que se conecte Fusion. La transferencia de datos es el procesamiento total de una sola ejecución. Esto significa que varias acciones en una sola ejecución contribuyen a la transferencia total de datos. Fusion procesará archivos hasta que se alcance el límite de ejecución de 40 minutos.

Para obtener más información, vea [Trabajar con archivos grandes](/help/workfront-fusion/references/scenarios/fusion-large-files.md).

## Uso de memoria del servidor

* El uso de memoria del servidor para una sola ejecución está limitado a **1 GB**.

  Muchos factores, como los archivos grandes o los módulos complejos, pueden afectar al uso de la memoria del servidor de formas difíciles de predecir o controlar. Debido a esto, la ejecución del escenario puede superar el límite de memoria de 1 GB, incluso si el escenario sigue todas las demás protecciones de rendimiento. Si se supera el límite de memoria, la ejecución falla.

## Webhooks

* El tamaño máximo predeterminado de una carga útil es de **5 MB**.
* Los enlaces web están limitados a **100 solicitudes por segundo**. Cuando se alcanza este límite, Workfront Fusion envía un estado 429 ([!UICONTROL Demasiadas solicitudes]).
* [!DNL Workfront Fusion] almacena cargas útiles de webhooks durante 30 días. Acceder a una carga útil de webhook más de 30 días después de recibirla provoca el error “[!UICONTROL No se pudo leer el archivo desde el almacenamiento.]”
* Los webhooks se desactivan automáticamente si se aplica cualquiera de las siguientes opciones:

   * El webhook no ha estado conectado a ningún escenario durante más de 5 días
   * El webhook solo se utiliza en escenarios inactivos, que han estado inactivos durante más de 30 días.

* Los webhooks desactivados se borran y no se registran automáticamente si no están conectados a ningún escenario y han permanecido en estado desactivado durante más de 30 días.

## Historial de ejecución

* Los registros del historial de ejecución están limitados a un tamaño de **100 MB**. Si el historial de ejecución supera este tamaño, solo se mostrarán los primeros 100 MB.
* Si un escenario tiene varias ejecuciones simultáneas. solo se muestran 5 ejecuciones en el área Ejecuciones de la página de detalles del escenario. Esto ocurre incluso cuando se están ejecutando más de 5 ejecuciones.

## Ejecuciones incompletas

* Las ejecuciones incompletas están limitadas a un tamaño total de **500 MB**. Si se alcanza el límite de 500 MB, no se almacenarán más ejecuciones incompletas.

## Reintentos

* Al utilizar el módulo Break y especificar la directiva de reintento, si un escenario falla de forma consecutiva 10 veces dentro de un periodo de tiempo de 2 minutos, el escenario se desactivará automáticamente.

## Recursión

La recursión se produce cuando un escenario déclencheur déclencheur una nueva ejecución de sí mismo, lo que provoca una nueva ejecución, y así sucesivamente en un bucle infinito.

Por ejemplo, se activa un escenario cuando se crea una tarea y ese escenario crea dos tareas. Las tareas recién creadas vuelven a almacenar en déclencheur el escenario, lo que crea cuatro tareas nuevas. Cada vez que se crea una tarea, se activa el escenario y, cada vez que se ejecuta, se duplica el número de tareas. El número de tareas aumenta exponencialmente.

La recursión puede causar problemas de rendimiento tanto para la organización propietaria del escenario recursivo como para otras organizaciones.

Tenga en cuenta lo siguiente con respecto a la recursión:

* **Cuando un escenario está causando recursión, el equipo de ingeniería de Fusion lo desactiva para evitar nuevos problemas de rendimiento.**
* Dado que la recursividad es el resultado del diseño de escenarios, debe diseñarlos de manera que se garantice que el escenario no incluya acciones que lo déclencheur.

