---
title: Adición de un módulo a un escenario
description: Este artículo describe el proceso básico de agregar un módulo a un escenario.
author: Becky
feature: Workfront Fusion
exl-id: f3757468-3e11-4862-a83e-ed447805545b
source-git-commit: 860209fdcf2e7707663cc2d454c0499972b1261e
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 9%

---

# Adición de un módulo a un escenario

Un escenario se compone de una serie de módulos que indican cómo se deben transformar los datos dentro de una aplicación o transferirlos entre aplicaciones y servicios web. Para generar un módulo, agregue y configure módulos.

Este artículo describe el proceso básico de agregar un módulo a un escenario. Para obtener instrucciones más específicas sobre cómo agregar un escenario, consulte los demás artículos en [Agregar módulos: índice de artículos](/help/workfront-fusion/create-scenarios/add-modules/add-modules-toc.md).

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
   <p>Nuevo:</p> <ul><li>Plan [!UICONTROL Select] o [!UICONTROL Prime] [!DNL Workfront]: su organización debe adquirir [!DNL Adobe Workfront Fusion].</li><li>Se incluye el plan [!DNL Workfront] de [!UICONTROL Ultimate]: [!DNL Workfront Fusion].</li></ul>
   <p>O</p>
   <p>Actual: su organización debe comprar [!DNL Adobe Workfront Fusion].</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Adición del primer módulo a un escenario

El primer módulo de un escenario suele ser un módulo de déclencheur.

Para obtener más información sobre los módulos de déclencheur, consulte [módulos de Déclencheur](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#trigger-modules) en el artículo Información general sobre el módulo.

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Comience a crear un escenario haciendo clic en **Crear un nuevo escenario** en la esquina superior derecha de la pantalla.

   Se abre el editor de escenarios, con un módulo de marcador de posición (signo de interrogación) y la lista de conectores disponibles.

   ![Módulo de marcador de posición](assets/placeholder-module.png)

1. Seleccione el conector o el webhook que iniciará este escenario. Puede escribir el nombre del conector en la barra de búsqueda de la lista para filtrar la lista.
1. Configure el módulo.

   Para obtener instrucciones sobre cómo configurar módulos específicos, consulte el artículo de las aplicaciones seleccionadas, que se enumeran en [Referencias de aplicaciones Fusion y sus módulos: índice de artículos](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).

>[!NOTE]
>
>Si ha eliminado el primer módulo de un escenario y desea reemplazarlo, haga clic en el módulo de marcador de posición (signo de interrogación) para abrir la lista de conectores.

## Agregar otro módulo a un escenario

1. Si no se encuentra en el editor de escenarios donde desea agregar un módulo, haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Para agregar un módulo a otro módulo, pasa el ratón sobre el controlador derecho del módulo tras el cual quieres agregar un módulo y luego haz clic en **Agregar otro módulo** cuando aparezca.

   Se abrirá la lista de conectores, con los conectores que ya se hayan utilizado en la situación.

1. (Opcional) Para seleccionar otro conector, haga clic en **Agregar otro módulo** en la lista y, a continuación, seleccione el conector. Puede escribir el nombre del conector en la barra de búsqueda de la lista para filtrar la lista.
1. Configure el módulo.

   Para obtener instrucciones sobre cómo configurar módulos específicos, consulte el artículo de las aplicaciones seleccionadas, que se enumeran en [Referencias de aplicaciones Fusion y sus módulos: índice de artículos](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).

## Inserción de un módulo entre módulos existentes en un escenario

1. Si no se encuentra en el editor de escenarios donde desea agregar un módulo, haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haga clic en la ruta de puntos entre los módulos en los que desea insertar un módulo.
1. En el menú que aparece, seleccione **Agregar un módulo**.

Se abrirá la lista de conectores, con los conectores que ya se hayan utilizado en la situación.

1. (Opcional) Para seleccionar otro conector, haga clic en **Agregar otro módulo** en la lista y, a continuación, seleccione el conector. Puede escribir el nombre del conector en la barra de búsqueda de la lista para filtrar la lista.
1. Configure el módulo.

   Para obtener instrucciones sobre cómo configurar módulos específicos, consulte el artículo de las aplicaciones seleccionadas, que se enumeran en [Referencias de aplicaciones Fusion y sus módulos: índice de artículos](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).
