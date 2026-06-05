---
title: Use Ejecutar una vez para probar un escenario
description: Puede probar un escenario sin un déclencheur externo utilizando el botón Ejecutar una vez.
author: Becky
feature: Workfront Fusion
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 0c732add9c1ec75d7aed43bb7097bb1c95aa6408
workflow-type: tm+mt
source-wordcount: 332
ht-degree: 0%

---

# Use Ejecutar una vez para probar un escenario

Al crear, actualizar o perfeccionar un escenario, puede utilizar el botón &quot;Ejecutar una vez&quot; para almacenar en déclencheur el escenario bajo demanda. De este modo, puede probar el escenario sin esperar a su lógica de déclencheur, como eventos específicos o intervalos de sondeo.

También puede ejecutar un escenario una vez para configurar estructuras de datos

>[!TIP]
>
>Se recomienda realizar pruebas con frecuencia a medida que crea y perfecciona escenarios.

## Usar la funcionalidad Ejecutar una vez

La función Ejecutar una vez se encuentra en el editor de escenarios.

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que quiere ejecutar el Experto en puntuación de escenarios.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haga clic en **Ejecutar una vez** en la esquina inferior izquierda del Editor de escenarios.
1. (Condicional) Si el escenario se activa mediante un gancho web o es un escenario secundario, seleccione la entrada para la ejecución de prueba.

   * **Esperar una llamada externa al webhook**: el escenario comenzará a escuchar una llamada entrante al webhook. Debe almacenar en déclencheur el webhook del sistema externo para proporcionar el webhook.

     Por ejemplo, si el gancho web está escuchando una nueva solicitud en Workfront, debe crear una nueva solicitud en Workfront para almacenarla en déclencheur y completar la funcionalidad &quot;Ejecutar una vez&quot;.

     >[!NOTE]
     >
     >Esta opción solo está disponible para escenarios de gancho web.

   * **Usar una entrada de ejecución anterior**: debe seleccionar una ejecución anterior. La ejecución &quot;Ejecutar una vez&quot; utiliza los datos de entrada que activaron la ejecución seleccionada.

     Para seleccionar una ejecución anterior, seleccione la ejecución y haga clic en **Ejecutar**.

     Para examinar los datos de entrada de la ejecución antes de seleccionarlos, haga clic en **Previsualizar entrada** para esa ejecución.

     >[!NOTE]
     >
     >El escenario debe haber completado ejecuciones anteriores antes de que esta opción esté disponible.

   * **Proporcionar datos introducidos manualmente**: debe proporcionar la carga útil del gancho web para la entrada del escenario. Debe estar en formato JSON.

     Para proporcionar la entrada, escriba el texto en el cuadro **Carga útil de webhook** y haga clic en **Ejecutar**.



