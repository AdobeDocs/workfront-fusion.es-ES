---
title: Flujo de trabajo para crear un escenario
description: Siga este flujo de trabajo general para crear un escenario
author: Becky
feature: Workfront Fusion
exl-id: 49f8edd7-e29a-4ead-9134-a9f0d1cc244d
source-git-commit: 394f80a2d7c124bbd00e1a5b51ad3dc6e73a996b
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 21%

---

# Flujo de trabajo para crear un escenario

Los escenarios están diseñados para satisfacer las necesidades de su organización, con aplicaciones y módulos que se ocupan de sus casos de uso. Sin embargo, la creación de un escenario sigue el mismo flujo de trabajo básico, independientemente del caso de uso. Este artículo describe el proceso básico de creación de un escenario.


* [Cree y asigne un nombre al escenario](#create-and-name-the-scenario)
* [Añadir y configurar el primer módulo](#configure-the-first-module)
* [Creación de conexiones](#create-connections)
* [Añadir y configurar módulos adicionales](#add-and-configure-additional-modules)
* [Asignación de datos entre módulos](#map-data-between-modules)
* [Configurar enrutamiento](#configure-routing)
* [Configuración de la gestión de errores](#configure-error-handling)
* [Configuración de escenarios](#onfigure-scenario-settings)
* [Prueba y revisión](#test-and-revise)
* [Activar el escenario](#activate-the-scenario)
* [Métodos abreviados del teclado para escenarios de Workfront Fusion](#workfront-fusion-scenario-keyboard-shortcuts)

Métodos abreviados del teclado



## Cree y asigne un nombre al escenario

1. Inicie sesión en la cuenta de [!DNL Workfront Fusion].
1. Haga clic en **[!UICONTROL Scenarios]** ![icono de escenarios](assets/scenarios-icon.png) en el panel izquierdo.

   >[!NOTE]
   >
   >Si no ve el panel de navegación izquierdo o sus iconos, haga clic en el icono Menú ![Menu](assets/main-menu-icon-left-nav.png).

1. (Opcional) En el panel [!UICONTROL **Carpetas**], haga clic en el icono **[!UICONTROL Add folder]** ![Agregar icono de carpeta](assets/add-folder-icon.png) y, a continuación, escriba un nombre como &quot;Escenarios de práctica&quot; para la primera carpeta.

1. (Opcional) Abra la carpeta y, a continuación, haga clic en **[!UICONTROL Create a new scenario]** en la esquina superior derecha de la página.

1. Seleccione el nombre del marcador de posición **[!UICONTROL New scenario]** en la esquina superior izquierda y, a continuación, escriba un nombre como &quot;Escenario de práctica 1&quot;.

   ![Nombrar el escenario](assets/name-the-scenario.png)

1. Continúe con el apartado siguiente [Conectar el primer módulo](#2-connect-the-first-module).

## Añadir y configurar el primer módulo

El primer módulo del escenario es un módulo de déclencheur, que iniciará el escenario cuando se cumplan determinadas condiciones.

Para obtener instrucciones sobre cómo agregar el primer módulo a un escenario, vea [Agregar el primer módulo a un escenario](/help/workfront-fusion/create-scenarios/add-modules/add-a-module-basic.md#add-the-first-module-to-a-scenario) en el artículo Agregar un módulo a un escenario.

Para obtener instrucciones sobre cómo configurar un módulo, consulte [Configurar un módulo](/help/workfront-fusion/create-scenarios/add-modules/configure-a-modules-settings.md)

## Creación de conexiones

Al configurar un módulo, debe introducir o crear una conexión. El módulo utiliza esta conexión y los permisos que contiene para acceder a la fecha en la aplicación.

Para obtener instrucciones básicas sobre cómo crear una conexión, consulte [Crear una conexión: instrucciones básicas](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md).

Para casos de uso específicos relacionados con Google, Microsoft o aplicaciones sin conectores específicos, consulte los demás artículos en [Conectar a aplicaciones: índice de artículos](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-apps-toc.md).

## Añadir y configurar módulos adicionales

Siga agregando y configurando módulos adicionales.

Para obtener instrucciones sobre cómo agregar módulos, consulte los artículos que se enumeran en [Agregar módulos: índice de artículos](/help/workfront-fusion/create-scenarios/add-modules/add-modules-toc.md).

## Asignación de datos entre módulos

Puede utilizar la salida de módulos anteriores como entrada en módulos posteriores. Por ejemplo, puede crear un proyecto de Workfront en un módulo y cargar un documento en ese módulo en un módulo posterior.

Para obtener instrucciones, vea los artículos en [Asignar datos: índice de artículo](/help/workfront-fusion/create-scenarios/map-data/map-data-toc.md).

## Configurar enrutamiento

El enrutamiento permite que el escenario realice diferentes acciones en función de los valores de los datos.

Para obtener instrucciones, vea [Agregar un módulo de enrutador y configurar rutas](/help/workfront-fusion/create-scenarios/add-modules/router-module.md).

## Configuración de la gestión de errores

La administración de errores permite que el escenario se recupere de los errores. Puede seleccionar cómo desea que reaccione el escenario en diferentes situaciones de error.

Para obtener instrucciones, consulte [Agregar administración de errores](/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md).

## Configuración de escenarios

Puede configurar las opciones para el escenario en su conjunto, como programar un escenario, tomar notas o determinar cómo se almacenan los datos.

Para obtener instrucciones, vea los artículos en [Configurar opciones de escenario: índice de artículo](/help/workfront-fusion/create-scenarios/config-scenarios-settings/config-scenario-settings-toc.md).

## Prueba y revisión

La prueba del escenario permite determinar si el escenario funciona según lo previsto. A continuación, puede revisar el escenario en función de los resultados y, después, volver a probar.

1. Haga clic en **[!UICONTROL Run once]** en la esquina inferior izquierda del editor de escenarios.
1. Una vez que el escenario termine de ejecutarse, haga clic en la burbuja del inspector de ejecución situada encima de cada módulo para ver la entrada de información y la salida de ese módulo.

   * Para obtener información general sobre cómo leer información de ejecución de escenarios, consulte [Flujo de ejecución de escenarios](/help/workfront-fusion/references/scenarios/scenario-execution-flow.md).
   * Para obtener información acerca de los paquetes procesados, consulte [Ejecución de escenarios, ciclos y fases en  [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md).

1. En [!DNL Workfront Fusion], haga clic en **[!UICONTROL Save]** ![icono de guardar](assets/save-icon.png) cerca de la esquina inferior izquierda para guardar su progreso en el escenario.

   >[!IMPORTANT]
   >
   >Se recomienda guardar con frecuencia mientras se perfeccionan y prueban escenarios.

## Activar el escenario

Este escenario de ejemplo no tiene un módulo de activador. Si este fuera un escenario que usaría para datos reales, empezaría con un módulo de activador y lo último que haría es activarlo. Después de activar un escenario, de forma predeterminada, se ejecuta cada 15 minutos. Puede cambiar esto definiendo cuándo y con qué frecuencia desea que se ejecute.

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
   <td role="rowheader">[!UICONTROL Open the DevTool]</td> 
   <td>F12</td> 
   <td>Ctrl + Fn + F12 </span> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select multiple modules]</td> 
   <td>Mayús + Arrastrar</td> 
   <td>Mayús + Arrastrar</span> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy]</td> 
   <td>Ctrl + C</td> 
   <td>Cmd+C</span> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Paste]</td> 
   <td>Ctrl + V</td> 
   <td>Cmd+V</span> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Pegue cURL en el escenario para crear el módulo HTTP</td> 
   <td colspan="2">Copie cURL y, a continuación, pegue en cualquier lugar del editor de escenarios.<p>Para obtener más información, consulte <a href="/help/workfront-fusion/create-scenarios/add-modules/use-curl-create-http.md">Usar cURL para agregar un módulo HTTP</a>.</td> 
  </tr> 
 </tbody> 
</table>





