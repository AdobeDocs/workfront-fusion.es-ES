---
title: Adición de un filtro a un escenario
description: En algunos casos, solo debe trabajar con paquetes que cumplan criterios específicos. Los filtros le permiten seleccionar esos paquetes.
author: Becky
feature: Workfront Fusion
exl-id: b507dca0-0e85-4ab7-8310-b6e6bcb7ae12
source-git-commit: c83070a7c2d1d048000a4eace4aaede73c7ec49d
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 3%

---

# Adición de un filtro a un escenario

En algunos casos, solo debe trabajar con paquetes que cumplan criterios específicos. Los filtros le permiten seleccionar esos paquetes.

Por ejemplo, podría crear un escenario con el déclencheur [!UICONTROL Observar registros] para Workfront para capturar solo las tareas asignadas a un usuario específico.

Puede añadir un filtro entre dos módulos y comprobar si los paquetes recibidos de los módulos anteriores cumplen condiciones de filtro específicas:

* Si es así, los paquetes pasan al siguiente módulo del escenario.
* Si no es así, el procesamiento de los paquetes finaliza.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront</td> 
   <td> <p>Cualquier paquete de flujo de trabajo de Adobe Workfront y cualquier paquete de integración y automatización de Adobe Workfront</p><p>Workfront Ultimate</p><p>Paquetes Workfront Prime y Select, con una compra adicional de Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencias de Adobe Workfront</td> 
   <td> <p>Estándar</p><p>Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete Select o Prime Workfront que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++## Requisitos previos

Debe agregar ambos módulos a un escenario para poder agregar un filtro entre ellos.

## Añada un filtro entre dos módulos:

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea agregar un filtro.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haga clic en el icono de llave inglesa ![Icono de llave inglesa](assets/wrench-icon.png) entre los módulos donde desea agregar un filtro y seleccione **Configurar un filtro**.
1. En el cuadro que se muestra, escriba una **[!UICONTROL Etiqueta]** para el filtro.
1. Defina el filtro **[!UICONTROL Condición]**.

   Introduzca el campo por el que desea filtrar en el primer campo, el operador y (si es necesario) el valor con el que desea comparar el campo.

   >[!TIP]
   >
   >Puede introducir valores en los campos de filtro desde el panel de asignación
   >Para obtener más información sobre la asignación, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

   Por ejemplo, si desea que el filtro pase archivos en Adobe Workfront que terminen con XML, debe introducir **[!UICONTROL Nombre de archivo]** en el primer cuadro y .**[!UICONTROL xml]** en el segundo cuadro. En el menú desplegable que hay entre ellos, debe seleccionar **[!UICONTROL Finaliza con (sin distinción de mayúsculas y minúsculas)]**. Este filtro se aplicaría a los paquetes entrantes del primer módulo (Workfront). Solo los paquetes que contengan archivos XML pasarán al siguiente módulo.

   ![Configurar un filtro](assets/set-up-filter-box.png)

1. Haga clic en **[!DNL OK]**.

## Copiar un filtro

Actualmente, el editor de escenarios no incluye una función para copiar un filtro.

>[!NOTE]
>
>Si copia los módulos a ambos lados del filtro, también se copia el filtro.
>
>Para obtener más información sobre cómo copiar módulos, consulte [Copiar módulos o escenarios en Adobe Workfront Fusion](/help/workfront-fusion/create-scenarios/add-modules/copy-modules-or-scenarios.md).

Para copiar un filtro sin copiar módulos, puede utilizar Fusion DevTool

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea agregar un filtro.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Abra Fusion DevTool haciendo clic en el icono de DevTool ![DevTool](assets/debugger-icon.png) cerca de la parte inferior de la pantalla.

   Si no ve el icono DevTool, vea [Depurar un escenario](/help/workfront-fusion/manage-scenarios/debug-a-scenario.md) para obtener instrucciones sobre cómo abrir DevTool.

1. Haga clic en el icono **[!UICONTROL Herramientas]** ![Herramientas DevTool](assets/devtools-tools-icon.png) en la barra lateral izquierda.

1. Haga clic en **[!UICONTROL Copiar filtro]** y, a continuación, configure la herramienta **[!UICONTROL Copiar filtro]** en el panel derecho:

   1. Establezca **[!UICONTROL Source Module]** como el módulo que se encuentra justo después del filtro que desea copiar.
   1. Establezca **[!UICONTROL Target Module]** como el módulo después del cual desea colocar el filtro.

1. Haga clic en **[!UICONTROL Ejecutar]**.
