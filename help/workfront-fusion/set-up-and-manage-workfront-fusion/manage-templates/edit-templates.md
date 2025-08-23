---
content-type: reference
title: Editar plantillas
description: Este artículo describe cómo editar las plantillas de Fusion.
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 473dba8b-faa4-432f-9357-c2146e86b261
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 26%

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
      <td role="rowheader">Plan de Adobe Workfront</td>
      <td><p>Cualquiera</p></td>
    </tr>
    <tr data-mc-conditions="">
      <td role="rowheader">Licencia de Adobe Workfront</td>
      <td><p>Nuevo: estándar</p><p>O</p><p>Actual: [!UICONTROL Work] o superior</p></td>
    </tr>
    <tr>
      <td role="rowheader">Licencia de Adobe Workfront Fusion**</td>
      <td>
        <p>Actual: no se requiere licencia de Workfront Fusion.</p>
        <p>O</p>
        <p>Heredado: cualquiera</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">Producto</td>
      <td>
        <p>Nuevo:</p>
        <ul>
          <li>Plan de Workfront de [!UICONTROL Select] o [!UICONTROL Prime]: su organización debe adquirir Adobe Workfront Fusion.</li>
          <li>Plan de Workfront de [!UICONTROL Ultimate]: Workfront Fusion está incluido.</li>
        </ul>
        <p>O</p>
        <p>Actual: Su organización debe comprar Adobe Workfront Fusion.</p>
      </td>
    </tr>
  </tbody>
</table>

<!--
For more detail about the information in this table, see [Access requirements in Workfront documentation](/help/quicksilver/administration-and-setup/add-users/access-levels-and-object-permissions/access-level-requirements-in-documentation.md). 

For information on Adobe Workfront Fusion licenses, see [Adobe Workfront Fusion licenses](../../workfront-fusion/get-started/license-automation-vs-integration.md). -->

+++

## Edición de plantillas de Workfront Fusion como administrador

1. Haga clic en **[!UICONTROL Administración]** en el panel de navegación izquierdo para abrir el área de [!UICONTROL Administración].
1. Haga clic en **[!UICONTROL Todas las plantillas]** en el panel de navegación izquierdo.
1. Haga clic en **[!UICONTROL Detalle]** a la derecha de la plantilla que desee editar.
1. (Opcional) Cambie el nombre de la plantilla haciendo clic en **Opciones** en la esquina superior derecha y seleccionando **Cambiar nombre**.
1. (Opcional) Para cambiar el idioma de la plantilla, haga clic en **[!UICONTROL Crear una nueva plantilla]** ![Icono de configuración de escenario](assets/fusion-scenario-settings-icon.png) y seleccione el idioma en la lista desplegable Idioma.

   >[!IMPORTANT]
   >
   >La selección Idiomas corresponde a los idiomas disponibles en la configuración del sistema y afecta únicamente al nombre de la plantilla pública y su descripción. No puede cambiar un idioma de plantilla una vez guardada la plantilla.

1. (Opcional) Para editar la descripción de la plantilla, haga clic en **[!UICONTROL Configurar una plantilla]** ![icono de configuración de escenario](assets/fusion-scenario-settings-icon.png) e introduzca la descripción.
1. Añada o edite aplicaciones, módulos y herramientas del mismo modo que lo haría al crear un escenario estándar.

   Para agregar ayuda contextual a los módulos, consulte [Configurar la funcionalidad del [!UICONTROL Asistente]](#set-up-wizard-functionality) en este artículo.

   <!--For more information on building a scenario, see [Create a scenario in Adobe Workfront Fusion](../../../workfront-fusion/scenarios/create-a-scenario.md).-->

   >[!NOTE]
   >
   >Si la plantilla incluye módulos que requieren agregar la conexión, las credenciales u otra información confidencial, esta información no se comparte con los usuarios de la plantilla.

1. (Opcional) Haga clic en **[!UICONTROL Ejecutar una vez]** para probar la plantilla.
1. Haga clic en el icono **[!UICONTROL Guardar]** ![Guardar icono](assets/save-icon.png).


## Configurar la funcionalidad de [!UICONTROL Wizard]

El [!DNL Workfront Fusion template] [!UICONTROL Asistente] le permite proporcionar a futuros usuarios de su plantilla instrucciones o información relacionada con los campos específicos utilizados en los módulos.

1. Haga clic en el módulo agregado a la plantilla para ver los campos del módulo.
1. Busque el campo donde desea agregar información de [!UICONTROL Wizard] y habilite **[!UICONTROL Usar en el asistente]** debajo de ese campo.
1. Escriba la información que desea que sea visible para los usuarios en el campo [!UICONTROL Ayuda].
1. (Opcional) Para permitir que los usuarios vean este texto al usar la plantilla, habilite **[!UICONTROL Usar como valor predeterminado]**.
1. Repita los pasos 2-4 para cada campo para el que desee proporcionar información.
1. Haga clic en **[!UICONTROL Aceptar]** para guardar los cambios y cerrar el módulo.

El proceso de publicación es el mismo que en el caso de un usuario estándar. Para obtener más información, consulte la sección [Publicar y compartir plantillas](/help/workfront-fusion/create-and-manage-templates/publish-and-share-fusion-templates.md) para obtener más detalles.

## Estados de plantilla

Puede comprobar el estado en la página de la plantilla bajo el nombre de la plantilla.

Están disponibles los siguientes estados:

* **[!UICONTROL Privada]**: esta plantilla solo está visible para el autor de la plantilla y su equipo.
* **[!UICONTROL Publicada]**: esta plantilla solo es visible para el autor de la plantilla y su equipo. Una vez publicada, puede enviar la plantilla para su aprobación si lo desea. También puede copiar un vínculo compartible.
* **[!UICONTROL Aprobada]**: esta plantilla está visible para todos los usuarios de Workfront Fusion en la pestaña [!UICONTROL Plantillas públicas]. También puede copiar un vínculo que se puede compartir haciendo clic en [!UICONTROL Opciones] en la esquina superior derecha de la pantalla.

También puede comprobar el estado desde la pestaña [!UICONTROL Plantillas de equipo]. Si se publica una plantilla, aparecerá un icono a la derecha del nombre de la plantilla.

* **Icono de ojo**: la plantilla está publicada; es visible para el equipo.
* **Icono de marca de verificación amarilla**: la plantilla está publicada; solo es visible para el equipo; y está pendiente de aprobación para agregarse a la pestaña Plantillas públicas.
* **Icono de marca de verificación verde**: la plantilla está disponible en la pestaña Plantillas públicas y es visible para cualquier usuario de Workfront Fusion. También sigue visible en la ficha [!UICONTROL Plantillas de equipo]. El autor de la plantilla o el miembro de su equipo aún pueden editarla.

Las plantillas sin iconos tienen el estado [!UICONTROL Privado]. No se publican y solo son visibles para el equipo.

## Localizar la información de SVG de una plantilla

1. Haga clic en **[!UICONTROL Administración]** en el panel de navegación izquierdo para abrir el área de [!UICONTROL Administración].
1. Haga clic en **[!UICONTROL Plantillas]** en el panel de navegación izquierdo.
1. Haga clic en la plantilla para la que desee buscar información.
1. Haga clic en **Opciones** en la esquina superior derecha.
1. Seleccione *Diagrama de SVG*.

Aquí puede ver el diagrama de SVG y el código de SVG.
