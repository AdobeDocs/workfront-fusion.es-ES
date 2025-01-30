---
title: Adición de un filtro a un escenario
description: En algunos casos, solo debe trabajar con paquetes que cumplan criterios específicos. Los filtros le permiten seleccionar esos paquetes.
author: Becky
feature: Workfront Fusion
exl-id: b507dca0-0e85-4ab7-8310-b6e6bcb7ae12
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 9%

---

# Adición de un filtro a un escenario

En algunos casos, solo debe trabajar con paquetes que cumplan criterios específicos. Los filtros le permiten seleccionar esos paquetes.

Por ejemplo, podría crear un escenario con el déclencheur [!UICONTROL Watch records] para [!DNL Workfront] a fin de capturar solamente las tareas asignadas a un usuario específico.

Puede añadir un filtro entre dos módulos y comprobar si los paquetes recibidos de los módulos anteriores cumplen condiciones de filtro específicas:

* Si es así, los paquetes pasan al siguiente módulo del escenario.
* Si no es así, el procesamiento de los paquetes finaliza.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] paquete</td> 
   <td> <p>Cualquiera</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licencia</td> 
   <td> <p>Nuevo: [!UICONTROL Standard]</p><p>O</p><p>Actual: [!UICONTROL Work] o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licencia**</td> 
   <td>
   <p>Actual: no se requiere licencia para [!DNL Workfront Fusion].</p>
   <p>O</p>
   <p>Heredado: cualquiera </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>[!UICONTROL Select] o plan [!UICONTROL Prime] [!DNL Workfront]: su organización debe comprar [!DNL Adobe Workfront Fusion].</li><li>[!UICONTROL Ultimate] [!DNL Workfront] plan: [!DNL Workfront Fusion] está incluido.</li></ul>
   <p>O</p>
   <p>Actual: su organización debe comprar [!DNL Adobe Workfront Fusion].</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Debe agregar ambos módulos a un escenario para poder agregar un filtro entre ellos.

## Añada un filtro entre dos módulos:

1. Haga clic en la ficha **[!UICONTROL Scenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea agregar un filtro.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haga clic en el icono de llave inglesa ![Icono de llave inglesa](assets/wrench-icon.png) entre los módulos donde desea agregar un filtro y seleccione **Configurar un filtro**.
1. En el cuadro que se muestra, escriba un **[!UICONTROL Label]** para el filtro.
1. Defina el filtro **[!UICONTROL Condition]**.

   Introduzca el campo por el que desea filtrar en el primer campo, el operador y (si es necesario) el valor con el que desea comparar el campo.

   >[!TIP]
   >
   >Puede introducir valores en los campos de filtro desde el panel de asignación
   >Para obtener más información sobre la asignación, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

   Por ejemplo, si desea que el filtro pase los archivos de [!DNL Adobe Workfront] que terminen con XML, debe escribir **[!UICONTROL File name]** en el primer cuadro y .**[!UICONTROL xml]** en el segundo cuadro. En el menú desplegable que hay entre ellos, debe seleccionar **[!UICONTROL Ends with (case insensitive)]**. Este filtro se aplicaría a los paquetes entrantes del primer módulo (Workfront). Solo los paquetes que contengan archivos XML pasarán al siguiente módulo.

   ![Configurar un filtro](assets/set-up-filter-box.png)

1. Haga clic en **[!DNL OK]**.

## Copiar un filtro

Actualmente, el editor de escenarios no incluye una función para copiar un filtro.

>[!NOTE]
>
>Si copia los módulos a ambos lados del filtro, también se copia el filtro.
>
>Para obtener más información sobre cómo copiar módulos, consulte [Copiar módulos o escenarios en [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/create-scenarios/add-modules/copy-modules-or-scenarios.md).

Para copiar un filtro sin copiar módulos, puede utilizar Fusion DevTool

1. Haga clic en la ficha **[!UICONTROL Scenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea agregar un filtro.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Abra Fusion DevTool haciendo clic en el icono de DevTool ![DevTool](assets/debugger-icon.png) cerca de la parte inferior de la pantalla.

   Si no ve el icono DevTool, vea [Depurar un escenario](/help/workfront-fusion/manage-scenarios/debug-a-scenario.md) para obtener instrucciones sobre cómo abrir DevTool.

1. Haga clic en el icono **[!UICONTROL Tools]** ![Herramientas DevTool](assets/devtools-tools-icon.png) en la barra lateral izquierda.

1. Haga clic en **[!UICONTROL Copy Filter]** y, a continuación, configure la herramienta **[!UICONTROL Copy Filter]** en el panel derecho:

   1. Establezca **[!UICONTROL Source Module]** como el módulo directamente después del filtro que desea copiar.
   1. Establezca **[!UICONTROL Target Module]** como el módulo después del cual desea colocar el filtro.

1. Haga clic en **[!UICONTROL Run]**.
