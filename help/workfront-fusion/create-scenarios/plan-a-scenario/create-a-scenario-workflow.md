---
title: Flujo de trabajo para crear un escenario
description: Follow this general workflow to create a scenario
author: Becky
feature: Workfront Fusion
exl-id: 49f8edd7-e29a-4ead-9134-a9f0d1cc244d
source-git-commit: 0390bb875eb10278967d7d1c9cd61e5243e5f37e
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 22%

---

# Flujo de trabajo para crear un escenario

Scenarios are built to meet the needs of your organization, with applications and modules that address your use cases. However, creating a scenario follows the same basic workflow regardless of use case. This article describes the basic process of creating a scenario.


* [Create and name the scenario](#create-and-name-the-scenario)
* [Añadir y configurar el primer módulo](#configure-the-first-module)
* [Crear conexiones](#create-connections)
* [Add and configure additional modules](#add-and-configure-additional-modules)
* [Map data between modules](#map-data-between-modules)
* [Configure routing](#configure-routing)
* [Configurar la gestión de errores](#configure-error-handling)
* [Establecer la configuración del escenario](#onfigure-scenario-settings)
* [Test and revise](#test-and-revise)
* [Activar el escenario](#activate-the-scenario)
* [Métodos abreviados del teclado para escenarios de Workfront Fusion](#workfront-fusion-scenario-keyboard-shortcuts)

Métodos abreviados de teclado



## Create and name the scenario

1. Sign into your Workfront Fusion account.
1. Click **[!UICONTROL Scenarios]** ![Scenarios icon](assets/scenarios-icon.png) in the left panel.

   >[!NOTE]
   >
   >Si no ve el panel de navegación izquierdo o sus iconos, haga clic en el icono Menú ![Menu](assets/main-menu-icon-left-nav.png).

1. (Optional)In the [!UICONTROL **Folders**] panel, click the **[!UICONTROL Add folder]** icon ![Add folder icon](assets/add-folder-icon.png), then type a name like &quot;Practice scenarios&quot; for your first folder.

1. (Optional) Open the folder, then click **[!UICONTROL Create a new scenario]** in the upper-right corner of the page.

1. Seleccione el nombre del marcador de posición **[!UICONTROL Nuevo escenario]** en la esquina superior izquierda y, a continuación, escriba un nombre como “Práctica de escenario 1&quot;.

   ![Name the scenario](assets/name-the-scenario.png)

1. Continúe con el apartado siguiente [Conectar el primer módulo](#2-connect-the-first-module).

## Añadir y configurar el primer módulo

The first module for your scenario is a trigger module, which will start the scenario when certain conditions are met.

For instructions on adding the first module to a scenario, see [Add the first module to a scenario](/help/workfront-fusion/create-scenarios/add-modules/add-a-module-basic.md#add-the-first-module-to-a-scenario) in the article Add a module to a scenario.

For instructions on configuring a module, see [Configure a module](/help/workfront-fusion/create-scenarios/add-modules/configure-a-modules-settings.md)

## Crear conexiones

When configuring a module, you must enter or create a connection. The module uses this connection and the permissions it contains to access date in the application.

For basic instructions on how to create a connection, see [Create a connection - Basic instructions](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md).

For specific use cases involving Google, Microsoft, or applications without dedicated connectors, see the other articles under [Connect to applications: article index](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-apps-toc.md).

## Add and configure additional modules

Continue adding and configuring additional modules.

For instructions on the ways to add modules, see the articles listed under [Add modules: article index](/help/workfront-fusion/create-scenarios/add-modules/add-modules-toc.md).

## Asignación de datos entre módulos

Puede utilizar la salida de módulos anteriores como entrada en módulos posteriores. Por ejemplo, puede crear un proyecto de Workfront en un módulo y cargar un documento en ese módulo en un módulo posterior.

Para obtener instrucciones, vea los artículos en [Asignar datos: índice de artículo](/help/workfront-fusion/create-scenarios/map-data/map-data-toc.md).

## Configurar enrutamiento

El enrutamiento permite que el escenario realice diferentes acciones en función de los valores de los datos.

Para obtener instrucciones, vea [Agregar un módulo de enrutador y configurar rutas](/help/workfront-fusion/create-scenarios/add-modules/router-module.md).

## Configurar la gestión de errores

La administración de errores permite que el escenario se recupere de los errores. Puede seleccionar cómo desea que reaccione el escenario en diferentes situaciones de error.

Para obtener instrucciones, consulte [Agregar administración de errores](/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md).

## Establecer la configuración del escenario

Puede configurar las opciones para el escenario en su conjunto, como programar un escenario, tomar notas o determinar cómo se almacenan los datos.

Para obtener instrucciones, vea los artículos en [Configurar opciones de escenario: índice de artículo](/help/workfront-fusion/create-scenarios/config-scenarios-settings/config-scenario-settings-toc.md).

## Prueba y revisión

La prueba del escenario permite determinar si el escenario funciona según lo previsto. A continuación, puede revisar el escenario en función de los resultados y, después, volver a probar.

1. Haga clic en **[!UICONTROL Ejecutar una vez]** en la esquina inferior izquierda del editor de escenarios.
1. Una vez que el escenario termine de ejecutarse, haga clic en la burbuja del inspector de ejecución situada encima de cada módulo para ver la entrada de información y la salida de ese módulo.

   * Para obtener información general sobre cómo leer información de ejecución de escenarios, consulte [Flujo de ejecución de escenarios](/help/workfront-fusion/references/scenarios/scenario-execution-flow.md).
   * Para obtener información sobre los paquetes procesados, consulte [Ejecución de escenarios, ciclos y fases en Adobe Workfront Fusion](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md).

1. En Workfront Fusion, haga clic en **[!UICONTROL Guardar]** ![Guardar icono](assets/save-icon.png) cerca de la esquina inferior izquierda para guardar su progreso en el escenario.

   >[!IMPORTANT]
   >
   >Se recomienda guardar con frecuencia mientras se perfeccionan y prueban escenarios.

## Activar el escenario

Después de activar un escenario, de forma predeterminada, se ejecuta cada 15 minutos. Puede cambiar esto definiendo cuándo y con qué frecuencia desea que se ejecute.

Para obtener más información sobre cómo activar escenarios, vea [Activar o desactivar un escenario](/help/workfront-fusion/manage-scenarios/activate-deactivate-scenarios.md).

Para obtener información sobre las programaciones, consulte [Programar un escenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md).

## Métodos abreviados del teclado para escenarios de Workfront Fusion

Puede utilizar los siguientes métodos abreviados del teclado al crear o editar un escenario:

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <thead> 
  <tr> 
   <th> <p>Acción</p> </th> 
   <th>[!DNL Windows]</th> 
   <th> <p>[!DNL MacOS]</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Save] </td> 
   <td>Ctrl + Mayús + S</td> 
   <td>Cmd + Mayús + S</span> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Run Once]</td> 
   <td>Ctrl + Mayús + Intro</td> 
   <td>Cmd+Mayús+Entrar</span> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Abrir DevTool]</td> 
   <td>F12</td> 
   <td>Ctrl + Fn + F12 </span> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Seleccionar varios módulos]</td> 
   <td>Mayús + Arrastrar</td> 
   <td>Mayús + Arrastrar</span> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy]</td> 
   <td>Ctrl + C</td> 
   <td>Cmd+C</span> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Pegar]</td> 
   <td>Ctrl + V</td> 
   <td>Cmd+V</span> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Buscar módulos]</td> 
   <td>Ctrl + K</td> 
   <td>Cmd+K</span> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Pegue cURL en el escenario para crear el módulo HTTP</td> 
   <td colspan="2">Copie cURL y, a continuación, pegue en cualquier lugar del editor de escenarios.<p>Para obtener más información, consulte <a href="/help/workfront-fusion/create-scenarios/add-modules/use-curl-create-http.md">Usar cURL para agregar un módulo HTTP</a>.</td> 
  </tr> 
 </tbody> 
</table>





