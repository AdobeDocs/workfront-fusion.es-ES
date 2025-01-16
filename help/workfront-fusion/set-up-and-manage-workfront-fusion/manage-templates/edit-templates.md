---
content-type: reference
title: Editar plantillas
description: Este artículo describe cómo editar las plantillas de Fusion.
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 473dba8b-faa4-432f-9357-c2146e86b261
source-git-commit: 86b0d7b16a4ed7e15888f6ee1a58f0279e96fb70
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 13%

---

# Editar plantillas

Las plantillas de Adobe Workfront Fusion son escenarios creados previamente y diseñados para automatizar y optimizar varios flujos de trabajo. Estas plantillas pueden ayudarle a configurar rápidamente integraciones y automatizaciones sin necesidad de crear todo desde cero.

Si es administrador, tiene permiso para ver, modificar, cambiar el nombre, publicar, aprobar y eliminar plantillas creadas por otros usuarios.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
  <col>
  <col>
  <tbody>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] plan</td>
      <td><p>Cualquiera</p></td>
    </tr>
    <tr data-mc-conditions="">
      <td role="rowheader">[!DNL Adobe Workfront] licencia</td>
      <td><p>Nuevo: [!UICONTROL Standard]</p><p>O</p><p>Actual: [!UICONTROL Work] o superior</p></td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront Fusion] licencia**</td>
      <td>
        <p>Actual: no se requiere licencia para [!DNL Workfront Fusion].</p>
        <p>O</p>
        <p>Heredado: cualquiera</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">Producto</td>
      <td>
        <p>Nuevo:</p>
        <ul>
          <li>[!UICONTROL Select] o plan [!UICONTROL Prime] [!DNL Workfront]: su organización debe comprar [!DNL Adobe Workfront Fusion].</li>
          <li>[!UICONTROL Ultimate] [!DNL Workfront] Plan: [!DNL Workfront Fusion] incluido.</li>
        </ul>
        <p>O</p>
        <p>Actual: su organización debe comprar [!DNL Adobe Workfront Fusion].</p>
      </td>
    </tr>
  </tbody>
</table>

<!--
For more detail about the information in this table, see [Access requirements in Workfront documentation](/help/quicksilver/administration-and-setup/add-users/access-levels-and-object-permissions/access-level-requirements-in-documentation.md). 

For information on [!DNL Adobe Workfront Fusion] licenses, see [[!DNL Adobe Workfront Fusion] licenses](../../workfront-fusion/get-started/license-automation-vs-integration.md). -->

+++

## Editar plantillas de [!DNL Workfront Fusion] como administrador

1. Haga clic en **[!UICONTROL Administration]** en el panel de navegación izquierdo para abrir el área [!UICONTROL Administration].
1. Haga clic en **[!UICONTROL All Templates]** en el panel de navegación izquierdo.
1. Haga clic en **[!UICONTROL Detail]** a la derecha de la plantilla que desee editar.
1. (Opcional) Cambie el nombre de la plantilla haciendo clic en **Opciones** en la esquina superior derecha y seleccionando **Cambiar nombre**.
1. (Opcional) Para cambiar el idioma de la plantilla, haga clic en **[!UICONTROL Create a new template]** ![](assets/fusion-scenario-settings-icon.png) y seleccione el idioma en la lista desplegable Idioma.

   >[!IMPORTANT]
   >
   >La selección Idiomas corresponde a los idiomas disponibles en la configuración del sistema y afecta únicamente al nombre de la plantilla pública y su descripción. No puede cambiar un idioma de plantilla una vez guardada la plantilla.

1. (Opcional) Para editar la descripción de la plantilla, haga clic en **[!UICONTROL Set up a template]** ![](assets/fusion-scenario-settings-icon.png) e introduzca la descripción.
1. Añada o edite aplicaciones, módulos y herramientas del mismo modo que lo haría al crear un escenario estándar.

   Para agregar ayuda contextual a los módulos, consulte [Configurar la funcionalidad de [!UICONTROL Wizard]](#set-up-wizard-functionality) en este artículo.

   <!--For more information on building a scenario, see [Create a scenario in [!DNL Adobe Workfront Fusion]](../../../workfront-fusion/scenarios/create-a-scenario.md).-->

   >[!NOTE]
   >
   >Si la plantilla incluye módulos que requieren agregar la conexión, las credenciales u otra información confidencial, esta información no se comparte con los usuarios de la plantilla.

1. (Opcional) Haga clic en **[!UICONTROL Run once]** para probar la plantilla.
1. Haga clic en el icono **[!UICONTROL Save]** ![](assets/save-icon.png).


## Configurar la funcionalidad de [!UICONTROL Wizard]

[!DNL Workfront Fusion template] [!UICONTROL Wizard] le permite proporcionar instrucciones o información a los futuros usuarios de su plantilla en relación con los campos específicos utilizados en los módulos.

1. Haga clic en el módulo agregado a la plantilla para ver los campos del módulo.
1. Busque el campo donde desea agregar información de [!UICONTROL Wizard] y habilite **[!UICONTROL Use in Wizard]** debajo de ese campo.
1. Escriba la información que desea hacer visible para los usuarios en el campo [!UICONTROL Help].
1. (Opcional) Para permitir que los usuarios vean este texto al usar la plantilla, habilite **[!UICONTROL Use as default value]**.
1. Repita los pasos 2-4 para cada campo para el que desee proporcionar información.
1. Haga clic en **[!UICONTROL OK]** para guardar los cambios y cerrar el módulo.

El proceso de publicación es el mismo que en el caso de un usuario estándar. Para obtener más información, vea la sección [Publish and share templates](/help/workfront-fusion/create-and-manage-templates/publish-and-share-fusion-templates.md) para obtener más detalles.

## Estados de plantilla

Puede comprobar el estado en la página de la plantilla bajo el nombre de la plantilla.

Están disponibles los siguientes estados:

* **[!UICONTROL Private]**: esta plantilla solo está visible para el autor de la plantilla y su equipo.
* **[!UICONTROL Published]**: esta plantilla solo está visible para el autor de la plantilla y su equipo. Una vez publicada, puede enviar la plantilla para su aprobación si lo desea. También puede copiar un vínculo compartible.
* **[!UICONTROL Approved]**: esta plantilla está visible para todos los usuarios de Workfront Fusion en la ficha [!UICONTROL Public templates]. También puede copiar un vínculo que se puede compartir haciendo clic en [!UICONTROL Options] en la esquina superior derecha de la pantalla.

También puede comprobar el estado desde la ficha [!UICONTROL Team templates]. Si se publica una plantilla, aparecerá un icono a la derecha del nombre de la plantilla.

* **Icono de ojo**: la plantilla está publicada; es visible para el equipo.
* **Icono de marca de verificación amarilla**: la plantilla está publicada; solo es visible para el equipo; y está pendiente de aprobación para agregarse a la pestaña Plantillas públicas.
* **Icono de marca de verificación verde**: la plantilla está disponible en la pestaña Plantillas públicas y es visible para cualquier usuario de Workfront Fusion. También sigue visible en la ficha [!UICONTROL Team templates]. El autor de la plantilla o el miembro de su equipo aún pueden editarla.

Las plantillas sin iconos tienen el estado [!UICONTROL Private]. No se publican y solo son visibles para el equipo.

## Localizar la información del SVG de una plantilla

1. Haga clic en **[!UICONTROL Administration]** en el panel de navegación izquierdo para abrir el área [!UICONTROL Administration].
1. Haga clic en **[!UICONTROL Templates]** en el panel de navegación izquierdo.
1. Haga clic en la plantilla para la que desee buscar información.
1. Haga clic en **Opciones** en la esquina superior derecha.
1. Seleccione *Diagrama del SVG*.

Aquí puede ver el diagrama del SVG y el código del SVG.
