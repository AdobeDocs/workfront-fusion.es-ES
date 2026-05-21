---
title: Crear nuevas plantillas
description: Puede crear nuevas plantillas de escenario en  [!DNL Adobe] Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 9cb9bd04-e9ae-4162-a1b9-d71566582b7a
TQID: https://experienceleague.adobe.com/UywwjPpiSAHbtSIo72rBCGlSpwq0N7SAnBrPCXOVncI
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2:
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 815
ht-degree: 11%

---

# Crear nuevas plantillas

Puede crear nuevas plantillas de escenario en [!DNL Adobe] Workfront Fusion.

>[!TIP]
>
>Antes de crear una plantilla nueva, puede comprobar la ficha [!UICONTROL Plantillas públicas] para asegurarse de que la plantilla que desea crear no esté disponible.

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
