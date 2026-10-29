---
title: Añadir un módulo a un escenario
description: Este artículo describe el proceso básico de agregar un módulo a un escenario.
author: Becky
feature: Workfront Fusion
exl-id: f3757468-3e11-4862-a83e-ed447805545b
TQID: 'https://experienceleague.adobe.com/R2JCX7aaYzmYHgiLqj1WDlVFHI-s-qanltoOrycQ5JU'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: cc160f0e8c2465b4f102b6d1755088335b2a9fe5
workflow-type: tm+mt
source-wordcount: '1508'
ht-degree: 8%
---
# Añadir un módulo a un escenario

Un escenario se compone de una serie de módulos que indican cómo se deben transformar los datos dentro de una aplicación o transferirse entre aplicaciones y servicios web. Para generar un módulo, agregue y configure módulos.

Este artículo describe el proceso básico de agregar un módulo a un escenario. Para obtener instrucciones más específicas sobre cómo agregar un escenario, consulte los demás artículos en [Agregar módulos: índice de artículos](/help/workfront-fusion/create-scenarios/add-modules/add-modules-toc.md).

>[!NOTE]
>
>Workfront Fusion está cambiando el editor de escenarios a una nueva experiencia. Durante esta transición, tanto las experiencias clásicas como las nuevas están disponibles y puede cambiar entre ellas en cualquier momento. Recomendamos utilizar la nueva experiencia. Para obtener más información, consulte [Experiencias nuevas y clásicas](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md#new-and-classic-experiences) en el artículo Editor de escenarios.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Paquete de Adobe Workfront</td> 
   <td> <p>Cualquier paquete del flujo de trabajo de Adobe Workfront y cualquier paquete de integración y automatización de Adobe Workfront</p><p>Workfront Ultimate</p><p>Paquetes Workfront Prime y Select, con una compra adicional de Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencias de Adobe Workfront</td> 
   <td> <p>Estándar</p><p>Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Adición del primer módulo a un escenario

El primer módulo de un escenario suele ser un módulo de déclencheur.

Para obtener más información sobre los módulos de déclencheur, consulte [módulos de Déclencheur](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#trigger-modules) en el artículo Información general sobre el módulo.

* [Añadir el primer módulo en la nueva experiencia (recomendado)](#add-the-first-module-in-the-new-experience-recommended)
* [Añadir el primer módulo de la experiencia clásica](#add-the-first-module-in-the-classic-experience)

### Añadir el primer módulo en la nueva experiencia (recomendado)

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Comience a crear un escenario haciendo clic en **Crear un nuevo escenario** en la esquina superior derecha de la pantalla.

   Se abre el editor de escenarios, con un módulo de marcador de posición y la lista de conectores disponibles.

   ![Módulo de marcador de posición](/help/workfront-fusion/build-practice-scenarios/assets/new-placeholder-module.png)

   ![Selector de aplicaciones y servicios](/help/workfront-fusion/build-practice-scenarios/assets/new-connector-picker.png)

1. Seleccione el conector o el gancho web que iniciará este escenario:

   * Examine por categoría utilizando el panel de la izquierda ([!UICONTROL Favoritos], [!UICONTROL Todas las aplicaciones], [!UICONTROL Adobe Workfront], [!UICONTROL Adobe Firefly Services], [!UICONTROL Adobe Creative &amp; Content], [!UICONTROL Adobe Cloud Services], [!UICONTROL IA generativa] o [!UICONTROL Integrada]), o
   * Introduzca un término en el cuadro de búsqueda. Los resultados se actualizan a medida que escribe y las coincidencias del conector se enumeran antes de que coincidan el nombre del módulo y la descripción.

1. Haga clic en el módulo que desee agregar al escenario.

1. Configure el módulo.

   La configuración del módulo se abre en el panel situado en el lado derecho del lienzo.

   Para obtener instrucciones sobre cómo configurar módulos específicos, consulte el artículo de las aplicaciones seleccionadas, que se enumeran en [Referencias de aplicaciones Fusion y sus módulos: índice de artículos](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).

>[!NOTE]
>
>* En la lista de conectores, los distintivos identifican aplicaciones privadas, premium y beta.
>* Los módulos para aplicaciones grandes se organizan en grupos.
>* Cuando se añade un gestor de errores, las directivas se enumeran primero.
>* Si un conector tiene más de una versión, podrá seleccionarla después de seleccionar el conector.

>[!NOTE]
>
>Si ha quitado el primer módulo de un escenario y desea reemplazarlo, haga clic en el módulo de marcador de posición para abrir la lista de conectores.

### Añadir el primer módulo de la experiencia clásica

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

* [Añadir otro módulo en la nueva experiencia (recomendado)](#add-another-module-in-the-new-experience-recommended)
* [Añadir otro módulo en la experiencia clásica](#add-another-module-in-the-classic-experience)

### Añadir otro módulo en la nueva experiencia (recomendado)

1. Si no se encuentra en el editor de escenarios donde desea agregar un módulo, haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Para agregar un módulo después de otro, pasa el ratón sobre el borde derecho del módulo después del cual quieres agregar un módulo y luego haz clic en **Agregar otro módulo** cuando aparezca.

   Se abrirá la lista de conectores, con los conectores que ya se hayan utilizado en la situación.

1. (Opcional) Para seleccionar otro conector, haga clic en **Agregar otro módulo** en la lista y, a continuación, seleccione el conector:

   * Examine por categoría utilizando el panel de la izquierda ([!UICONTROL Favoritos], [!UICONTROL Todas las aplicaciones], [!UICONTROL Adobe Workfront], [!UICONTROL Adobe Firefly Services], [!UICONTROL Adobe Creative &amp; Content], [!UICONTROL Adobe Cloud Services], [!UICONTROL IA generativa] o [!UICONTROL Integrada]), o
   * Introduzca un término en el cuadro de búsqueda. Los resultados se actualizan a medida que escribe y las coincidencias del conector se enumeran antes de que coincidan el nombre del módulo y la descripción.

1. Haga clic en el módulo que desee agregar al escenario.

1. Configure el módulo.

   La configuración del módulo se abre en el panel situado en el lado derecho del lienzo.

   Para obtener instrucciones sobre cómo configurar módulos específicos, consulte el artículo de las aplicaciones seleccionadas, que se enumeran en [Referencias de aplicaciones Fusion y sus módulos: índice de artículos](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).

### Añadir otro módulo en la experiencia clásica

1. Si no se encuentra en el editor de escenarios donde desea agregar un módulo, haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Para agregar un módulo a otro módulo, pasa el ratón sobre el controlador derecho del módulo tras el cual quieres agregar un módulo y luego haz clic en **Agregar otro módulo** cuando aparezca.

   Se abrirá la lista de conectores, con los conectores que ya se hayan utilizado en la situación.

1. (Opcional) Para seleccionar otro conector, haga clic en **Agregar otro módulo** en la lista y, a continuación, seleccione el conector. Puede escribir el nombre del conector en la barra de búsqueda de la lista para filtrar la lista.
1. Configure el módulo.

   Para obtener instrucciones sobre cómo configurar módulos específicos, consulte el artículo de las aplicaciones seleccionadas, que se enumeran en [Referencias de aplicaciones Fusion y sus módulos: índice de artículos](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).

## Inserción de un módulo entre módulos existentes en un escenario

* [Insertar un módulo en la nueva experiencia (recomendado)](#insert-a-module-in-the-new-experience-recommended)
* [Inserte un módulo en la experiencia clásica](#insert-a-module-in-the-classic-experience)

### Insertar un módulo en la nueva experiencia (recomendado)

1. Si no se encuentra en el editor de escenarios donde desea agregar un módulo, haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haga clic con el botón derecho en la ruta entre los módulos donde desea insertar un módulo y, a continuación, seleccione **Agregar módulo**.

   ![Agregar un módulo entre módulos existentes](assets/add-a-module-between-modules.png)

   Se abrirá la lista de conectores, con los conectores que ya se hayan utilizado en la situación.

1. (Opcional) Para seleccionar otro conector, haga clic en **Agregar otro módulo** en la lista y, a continuación, seleccione el conector:

   * Examine por categoría utilizando el panel de la izquierda ([!UICONTROL Favoritos], [!UICONTROL Todas las aplicaciones], [!UICONTROL Adobe Workfront], [!UICONTROL Adobe Firefly Services], [!UICONTROL Adobe Creative &amp; Content], [!UICONTROL Adobe Cloud Services], [!UICONTROL IA generativa] o [!UICONTROL Integrada]), o
   * Introduzca un término en el cuadro de búsqueda. Los resultados se actualizan a medida que escribe y las coincidencias del conector se enumeran antes de que coincidan el nombre del módulo y la descripción.

1. Haga clic en el módulo que desee agregar al escenario.

1. Configure el módulo.

   La configuración del módulo se abre en el panel situado en el lado derecho del lienzo.

   Para obtener instrucciones sobre cómo configurar módulos específicos, consulte el artículo de las aplicaciones seleccionadas, que se enumeran en [Referencias de aplicaciones Fusion y sus módulos: índice de artículos](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).

>[!NOTE]
>
>Para crear un vínculo a un módulo específico, agregue `?moduleId=<module-id>` a la dirección URL cuando visualice las siguientes páginas:
>
>* Página de edición de escenario (la dirección URL termina en `/edit`)
>* Ejecución de un escenario específico (la dirección URL termina en `/logs/<log-id>`)
>
>`<module-id>` hace referencia al número que hay junto a la etiqueta del módulo cuando visualiza el escenario.
>
>Esto puede resultar útil al depurar escenarios o copiar la configuración del módulo.

### Inserte un módulo en la experiencia clásica

1. Si no se encuentra en el editor de escenarios donde desea agregar un módulo, haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haga clic en la ruta de puntos entre los módulos en los que desea insertar un módulo.
1. En el menú que aparece, seleccione **Agregar un módulo**.

Se abrirá la lista de conectores, con los conectores que ya se hayan utilizado en la situación.

1. (Opcional) Para seleccionar otro conector, haga clic en **Agregar otro módulo** en la lista y, a continuación, seleccione el conector. Puede escribir el nombre del conector en la barra de búsqueda de la lista para filtrar la lista.
1. Configure el módulo.

   Para obtener instrucciones sobre cómo configurar módulos específicos, consulte el artículo de las aplicaciones seleccionadas, que se enumeran en [Referencias de aplicaciones Fusion y sus módulos: índice de artículos](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).

>[!NOTE]
>
>Para crear un vínculo a un módulo específico, agregue `?moduleId=<module-id>` a la dirección URL cuando visualice las siguientes páginas:
>
>* Página de edición de escenario (la dirección URL termina en `/edit`)
>* Ejecución de un escenario específico (la dirección URL termina en `/logs/<log-id>`)
>
>`<module-id>` hace referencia al número que hay junto a la etiqueta del módulo cuando visualiza el escenario.
>
>Esto puede resultar útil al depurar escenarios o copiar la configuración del módulo.
