---
title: Creación de nuevas plantillas
description: Puede crear nuevas plantillas de escenario en  [!DNL Adobe] Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 9cb9bd04-e9ae-4162-a1b9-d71566582b7a
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 6%

---

# Creación de nuevas plantillas

Puede crear nuevas plantillas de escenario en [!DNL Adobe] Workfront Fusion.

>[!TIP]
>
>Antes de crear una plantilla nueva, puede comprobar la ficha [!UICONTROL Plantillas públicas] para asegurarse de que la plantilla que desea crear no esté disponible.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront</td> 
   <td> <p>Cualquiera</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencia de Adobe Workfront</td> 
   <td> <p>Nuevo: estándar</p><p>O</p><p>Actual: [!UICONTROL Work] o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion**</td> 
   <td>
   <p>Actual: no se requiere licencia de Workfront Fusion.</p>
   <p>O</p>
   <p>Heredado: cualquiera </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Plan de Workfront de [!UICONTROL Select] o [!UICONTROL Prime]: su organización debe adquirir Adobe Workfront Fusion.</li><li>Plan de Workfront de [!UICONTROL Ultimate]: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe comprar Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Crear una plantilla nueva

Puede crear una plantilla en un proceso similar a la creación de un escenario. Los administradores de Fusion también pueden crear plantillas a partir de escenarios existentes.

* [Creación de una plantilla](#build-a-template)
* [Creación de una plantilla a partir de un escenario](#create-a-template-from-a-scenario)

### Creación de una plantilla

1. Haga clic en **[!UICONTROL Plantillas]** ![Icono de plantillas](assets/templates-icon.png) en el panel de navegación izquierdo.
1. Haga clic en **[!UICONTROL Crear una nueva plantilla]** en la esquina superior derecha.
1. (Opcional) Cambie el nombre de la plantilla reemplazando el **[!UICONTROL Nuevo nombre de plantilla]** predeterminado en la esquina superior izquierda.
1. (Opcional) Para cambiar el idioma de la plantilla, haga clic en **[!UICONTROL Configurar una plantilla]** ![Icono de configuración de escenario](assets/scenario-settings-icon.png) y seleccione el idioma en la lista desplegable Idioma.

   >[!IMPORTANT]
   >
   >La selección Idiomas corresponde a los idiomas disponibles en la configuración del sistema y afecta únicamente al nombre de la plantilla pública y su descripción. No puede cambiar un idioma de plantilla una vez guardada la plantilla.

1. (Opcional) Para escribir una descripción de la plantilla, haga clic en **[!UICONTROL Configurar una plantilla]** ![icono de configuración de escenario](assets/scenario-settings-icon.png) e introduzca la descripción.
1. Añada aplicaciones, módulos y herramientas con los mismos procesos que al agregar módulos a un escenario.

   Para obtener instrucciones, consulte los artículos en [Agregar módulos](/help/workfront-fusion/create-scenarios/add-modules/add-modules-toc.md).

   Para agregar ayuda contextual a los módulos, consulte [Configurar la funcionalidad del Asistente](#set-up-wizard-functionality) en este artículo.

   Para obtener más información sobre cómo crear un escenario, consulte [Flujo de trabajo para crear un escenario](/help/workfront-fusion/create-scenarios/plan-a-scenario/create-a-scenario-workflow.md).

   >[!NOTE]
   >
   >Si la plantilla incluye módulos que requieren agregar la conexión, las credenciales u otra información confidencial, esta información no se comparte con los usuarios de la plantilla.

1. (Opcional) Haga clic en **[!UICONTROL Ejecutar una vez]** para probar la plantilla.
1. Haga clic en el icono **[!UICONTROL Guardar]** ![Guardar icono](assets/save-icon.png) para guardar la plantilla.

Al guardar la plantilla, los integrantes del equipo la verán. Si desea que la plantilla sea accesible fuera del equipo, debe enviar una solicitud para que se apruebe y publique. La solicitud se envía al equipo de Adobe Workfront Fusion para su aprobación. Una vez aprobada, otros miembros externos al equipo pueden acceder a la plantilla.

Para obtener información sobre las plantillas de publicación, consulte [Publicar y compartir plantillas de Adobe Workfront Fusion](/help/workfront-fusion/create-and-manage-templates/publish-and-share-fusion-templates.md).

### Creación de una plantilla a partir de un escenario

>[!NOTE]
>
>Debe ser administrador de Fusion para crear una plantilla a partir de un escenario.

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario desde el que desea crear una plantilla.
1. Haga clic en el menú desplegable **Administrador** situado cerca de la esquina superior derecha de la página.
1. Seleccione **Clonar como plantilla**.

   El escenario se copia en una página Nueva plantilla.
1. (Opcional) Cambie el nombre de la plantilla reemplazando el **[!UICONTROL Nuevo nombre de plantilla]** predeterminado en la esquina superior izquierda.
1. (Opcional) Para cambiar el idioma de la plantilla, haga clic en **[!UICONTROL Configurar una plantilla]** ![Icono de configuración de escenario](assets/scenario-settings-icon.png) y seleccione el idioma en la lista desplegable Idioma.

   >[!IMPORTANT]
   >
   >La selección Idiomas corresponde a los idiomas disponibles en la configuración del sistema y afecta únicamente al nombre de la plantilla pública y su descripción. No puede cambiar un idioma de plantilla una vez guardada la plantilla.

1. (Opcional) Para escribir una descripción de la plantilla, haga clic en **[!UICONTROL Configurar una plantilla]** ![icono de configuración de escenario](assets/scenario-settings-icon.png) e introduzca la descripción.
1. Edite las aplicaciones, los módulos y las herramientas según desee, utilizando los mismos procesos que al añadir módulos a un escenario.

   Para obtener instrucciones, consulte los artículos en [Agregar módulos](/help/workfront-fusion/create-scenarios/add-modules/add-modules-toc.md).

   Para agregar ayuda contextual a los módulos, consulte [Configurar la funcionalidad del [!UICONTROL Asistente]](#set-up-wizard-functionality) en este artículo.

   >[!NOTE]
   >
   >Si la plantilla incluye módulos que requieren agregar la conexión, las credenciales u otra información confidencial, esta información no se comparte con los usuarios de la plantilla.

1. (Opcional) Haga clic en **[!UICONTROL Ejecutar una vez]** para probar la plantilla.
1. Haga clic en el icono **[!UICONTROL Guardar]** ![Guardar icono](assets/save-icon.png).

## Configurar la funcionalidad de [!UICONTROL Wizard] {#set-up-wizard-functionality}

El [!DNL Workfront Fusion template] [!UICONTROL Asistente] le permite proporcionar a futuros usuarios de su plantilla instrucciones o información relacionada con los campos específicos utilizados en los módulos.

1. Al crear una plantilla, haga clic en un módulo agregado a la plantilla para ver los campos del módulo.
1. Busque el campo donde desea agregar información de [!UICONTROL Wizard] y habilite **[!UICONTROL Usar en Wizard]** para ese campo.
1. Escriba la información que desea que sea visible para los usuarios en el campo [!UICONTROL Ayuda].
1. (Opcional) Para permitir que los usuarios vean este texto al usar la plantilla, habilite **[!UICONTROL Usar como valor predeterminado]**.
1. Repita los pasos 2-4 para cada campo para el que desee proporcionar información.
1. Haga clic en **[!UICONTROL Aceptar]** para guardar los cambios y cerrar el módulo.
