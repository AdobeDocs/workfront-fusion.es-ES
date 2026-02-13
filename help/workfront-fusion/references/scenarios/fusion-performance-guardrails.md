---
title: Mecanismos de protección de rendimiento Fusion
description: La automatización del trabajo requiere un procesamiento rápido. Es por ello que Adobe Workfront Fusion se ha diseñado para ofrecer un alto rendimiento. Como los escenarios de larga ejecución pueden ralentizar el ritmo de su trabajo, hemos diseñado Workfront Fusion con mecanismos de protección que preservan el rendimiento y que limitan el tiempo de ejecución, el tamaño de los datos y otros parámetros del escenario. Los diseñadores de Workfront Fusion deben tener en cuenta estos mecanismos de protección e incorporarlos en sus prácticas de diseño.
author: Becky
feature: Workfront Fusion
exl-id: d142a521-edbc-4d7b-b5cd-872a9d3d2e1c
source-git-commit: 086fef455017e19768969533ad63f39c34f962f4
workflow-type: tm+mt
source-wordcount: '1063'
ht-degree: 96%

---

# Mecanismos de protección de rendimiento Fusion

La automatización del trabajo requiere un procesamiento rápido. Es por ello que Adobe Workfront Fusion se ha diseñado para ofrecer un alto rendimiento. Como los escenarios de larga ejecución pueden ralentizar el ritmo de su trabajo, hemos diseñado Workfront Fusion con mecanismos de protección que preservan el rendimiento y que limitan el tiempo de ejecución, el tamaño de los datos y otros parámetros del escenario. Los diseñadores de Workfront Fusion deben tener en cuenta estos mecanismos de protección e incorporarlos en sus prácticas de diseño.

## Navegadores

* Workfront Fusion solo admite exploradores basados en Chrome.

## Escenarios

* El tiempo de espera de ejecución del escenario predeterminado es de **40 minutos**. Cuando la ejecución alcanza este tiempo de espera, Workfront Fusion interrumpe la ejecución del escenario después del siguiente ciclo u operación, según el escenario. Esto obliga al escenario a detenerse poco después de alcanzar el límite de 40 minutos

  Encadenar escenarios no cuenta para el tiempo de espera de ejecución del escenario. Un escenario principal no acumula tiempo mientras espera hasta que se ejecute un escenario secundario.
* El tamaño máximo de un modelo de escenario es de **5 MB**, pero se recomienda mantener el tamaño de escenario por debajo de **3 MB**.

  Los módulos de aplicaciones que crean o actualizan datos con una gran cantidad de campos pueden causar modelos muy grandes.

   * Cuando utilice la aplicación de Workfront, asegúrese de seleccionar solo los campos necesarios para los casos de uso de creación o actualización.
   * Cuando utilice otras aplicaciones, utilice módulos de API personalizados para interactuar con cualquier tipo de registro que tenga un gran número de campos.

* Aunque no hay límite en cuanto al número de módulos en un escenario, los escenarios con más de 150 módulos afectan negativamente al rendimiento del sistema Workfront Fusion. Por este motivo, no se recomienda crear escenarios con más de 150 módulos.

## Operaciones

* El tiempo de espera de operación predeterminado suele ser de **40 segundos**.

<!--
* The operation timeout for calls to Adobe Workfront is **120 seconds**.
-->

## Archivos

* La capacidad total de procesamiento de archivos de Fusion es de **1 GB**. El límite se basa en el coste total de la memoria. Cada operación contribuye a ese coste. Si se descarga y carga un solo archivo de 400 MB, el coste total de la capacidad del archivo sería de 800 MB.
* Las organizaciones del plan Workfront Ultimate tienen acceso a un mayor procesamiento de archivos que superan 1 GB. Sin embargo, hay otros factores que afectan a la transferencia de datos. El servicio al que se está conectando Fusion puede limitar el tamaño del archivo, lo que afectaría a cualquier archivo procesado por ese servicio. Además, los archivos grandes pueden afectar al tiempo de ejecución del escenario. Fusion procesará archivos hasta que se alcance el límite de ejecución de 40 minutos, momento en el que la ejecución fallará.
* Si un archivo se descarga mediante un módulo que admite archivos grandes y, a continuación, se pasa a un módulo que no admite archivos grandes, dicho módulo no procesará correctamente el archivo. Los archivos grandes deben gestionarse exclusivamente con módulos compatibles en todo el flujo de trabajo.
* Los módulos que no admiten archivos grandes pueden procesar archivos de hasta **200 MB** de tamaño.

Para obtener más información, consulte [Trabajo con archivos grandes](/help/workfront-fusion/references/scenarios/fusion-large-files.md).

## Uso de memoria del servidor

* El uso de memoria del servidor para una sola ejecución está limitado a **1 GB**.

  Muchos factores, como los archivos grandes o los módulos complejos, pueden afectar al uso de la memoria del servidor de formas difíciles de predecir o controlar. Debido a esto, la ejecución del escenario puede superar el límite de memoria de 1 GB, incluso si el escenario sigue todas las demás protecciones de rendimiento. Si se supera el límite de memoria, la ejecución falla.

## Webhooks

* El tamaño máximo predeterminado de una carga útil es de **5 MB**.
* Los enlaces web están limitados a **100 solicitudes por segundo**. Cuando se alcanza este límite, Workfront Fusion envía un estado 429 ([!UICONTROL Demasiadas solicitudes]).
* Workfront Fusion almacena cargas útiles de webhooks durante 30 días. Acceder a una carga útil de webhook más de 30 días después de recibirla provoca el error “[!UICONTROL No se pudo leer el archivo desde el almacenamiento.]”
* Los webhooks se desactivan automáticamente si se aplica cualquiera de las siguientes opciones:

   * El webhook no ha estado conectado a ningún escenario durante más de 5 días
   * El webhook solo se utiliza en escenarios inactivos, que han estado inactivos durante más de 30 días.

* Los webhooks desactivados se borran y no se registran automáticamente si no están conectados a ningún escenario y han permanecido en estado desactivado durante más de 30 días.
* El tiempo de espera para la respuesta de un webhook es de 5 minutos.

## Historial de ejecución

* Los registros del historial de ejecución están limitados a un tamaño de **100 MB**. Si el historial de ejecución supera este tamaño, solo se mostrarán los primeros 100 MB.
* Si un escenario tiene varias ejecuciones simultáneas, solo se muestran cinco ejecuciones en el área Ejecuciones de la página de detalles del escenario. Esto ocurre incluso cuando se están ejecutando más de 5 ejecuciones.

## Ejecuciones incompletas

* Las ejecuciones incompletas están limitadas a un tamaño total de **11 GB** o **100 ejecuciones incompletas** por escenario, el límite que se alcance primero. Si se alcanza un límite, no se almacenarán más ejecuciones incompletas para ese escenario.

## Reintentos

* Al utilizar el módulo Break y especificar la directiva de reintento, si un escenario falla de forma consecutiva 10 veces dentro de un periodo de tiempo de 2 minutos, el escenario se desactivará automáticamente.

## Recursividad

La recursividad se produce cuando un escenario activa una nueva ejecución de sí mismo, lo que activa una nueva ejecución, y así sucesivamente en un bucle infinito.

Por ejemplo, se activa un escenario cuando se crea una tarea y ese escenario crea dos tareas. Las tareas recién creadas vuelven a activar el escenario, lo que crea cuatro tareas nuevas. Cada vez que se crea una tarea, se activa el escenario y, cada vez que se ejecuta el escenario, se duplica el número de tareas. El número de tareas aumenta exponencialmente.

La recursividad puede causar problemas de rendimiento tanto para la organización propietaria del escenario recursivo como para otras organizaciones.

Tenga en cuenta lo siguiente con respecto a la recursividad:

* **Cuando un escenario está produciendo recursividad, el equipo de ingeniería de Fusion lo desactiva para evitar nuevos problemas de rendimiento.**
* Dado que la recursividad es el resultado del diseño de escenarios, debe diseñarlos de manera que se garantice que el escenario no incluya acciones que lo activen.

## TLS

* Fusion es compatible actualmente con TLS versión 1.2 de forma predeterminada.
* Fusion puede utilizar TLS 1.3 para las peticiones HTTPS de salida si TLS 1.3 está habilitado para el servicio de destino.
* Fusion es compatible con TLS 1.2 y TLS 1.3 para peticiones HTTPS de entrada a los webhooks.
* Las organizaciones pueden solicitar que se habilite TLS versión 1.3 para su instancia de Fusion.

>[!NOTE]
>
> Si se está conectando a Workfront, tenga en cuenta que esta funcionalidad TLS está habilitada en Workfront para llamadas a dominios que tienen el formato `https://<domain>.my.workfront.com`.
