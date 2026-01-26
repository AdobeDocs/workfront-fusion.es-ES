---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: scenarios
title: Usar plantillas para conectar Adobe Workfront Fusion y Jira
description: Utilice estas plantillas para automatizar los flujos de trabajo entre Adobe Workfront Fusion y Jira.
author: Becky
feature: Workfront Fusion
source-git-commit: 4ede5c7a75725a6540d6a8ff9cd056e6147d5c55
workflow-type: tm+mt
source-wordcount: '4171'
ht-degree: 5%

---

# Usar plantillas para conectar Adobe Workfront Fusion y Jira

Adobe Workfront Fusion ofrece plantillas que pueden automatizar flujos de trabajo comunes entre Fusion y Jira.

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
   <p>Workfront: Si su organización tiene un paquete Select o Prime Workfront que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</p><p>Jira: Debe tener una licencia de Jira Cloud</p>
   </td> 
  </tr>
  <tr> 
   <td role="rowheader">Configuraciones de nivel de acceso</td> 
   <td> <p>Workfront: permiso para crear usuarios, formularios personalizados y campos personalizados.</p> <p>Jira: Permisos para crear usuarios y campos personalizados, así como para modificar pantallas y webhooks.</td> 
  </tr> 
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte los [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Requisitos previos

### Workfront

* Debe tener una cuenta técnica en Adobe Developer Console.

  Para obtener información e instrucciones, consulte [Configuración de cuenta técnica](https://developer.adobe.com/cloud-storage/guides/getting-started/technical-account-setup) en la documentación de Adobe.
* Debe aplicar permisos de administrador del sistema a la cuenta técnica en el área Perfiles de producto de Adobe Admin Console.

  Para obtener información e instrucciones, consulte [Crear administradores de sistemas en Workfront con Adobe Admin Console](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/add-users/create-manage-users/admin-console#create-system-administrators-in-workfront-with-the-adobe-admin-console)

### Jira

Si está usando la autorización de OAuth2 para Jira (recomendado), debe configurar una aplicación de OAuth2 en [https://developer.atlassian.com/console](https://developer.atlassian.com/console). Para obtener información e instrucciones, consulte [Crear una conexión OAuth2 con Jira](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/jira-modules-new.md#create-an-oauth2-connection-to-jira) en el artículo Módulos Jira.

<!--

When configuring this application, you will need the following scopes:

* `read:jira-work` 
* `read:jira-user`
* `write:jira-work`

-->

## Suposiciones

Estos módulos suponen lo siguiente:

* Workfront es la fuente fiable del proyecto general de la campaña de marketing
* Jira está siendo utilizado por equipos técnicos, cumpliendo parte de un proyecto que comenzó en Workfront.
* No todos los usuarios de Jira tienen acceso a Workfront o viceversa.
* Workfront y Jira están alojados en la nube.

## Modelo de datos (asignaciones de campos)


| Workfront | Jira | Dirección | Notas |
|---|---|---|---|
| ObjId | ID de WF * | WF → Jira | Tras la creación del problema Jira |
| Clave Jira * | Clave de problema | Jira → WF | Tras la creación del problema Jira |
| URL de Jira * | - | Jira → WF | Vínculo en el que se puede hacer clic en WF a Jira |
| - | Vínculo WF * | WF → Jira | Vínculo en el que se puede hacer clic en Jira a WF |
| Nombre | Resumen | WF → Jira |  |
| Descripción | Descripción | WF → Jira |  |
| Estado | Estado de WF | WF → Jira | Estado de WF |
| Estado de Jira * | Estado | Jira → WF | Estado de Jira |
| Fecha planificada de finalización | Fecha de vencimiento | WF → Jira | Fecha planificada de finalización |
| Notas | Comentarios | WF ↔ Jira | Copia bidireccional |
| Documento | Archivos adjuntos | WF → Jira | Como archivos adjuntos en la creación de problemas y comentarios en nuevos documentos después de la creación. |

\* Estos campos se configuran como parte de esta configuración de integración. Para obtener instrucciones, consulte [Configuración de requisitos previos en Workfront, Jira y Workfront Fusion](/help/workfront-fusion/create-and-manage-templates/use-jira-scenario-templates.md#configure-prerequisites-in-workfront-jira-and-workfront-fusion).

## Configuración de requisitos previos en Workfront, Jira y Workfront Fusion

Para utilizar las plantillas de integración de Jira, debe realizar las siguientes configuraciones:

* [Configuración de Jira](#configure-jira)
* [Configuración de Workfront](#configure-workfront)
* [Configuración de conexiones en Workfront Fusion](#configure-connections-in-workfront-fusion)

### Configuración de Jira

Para utilizar estos módulos, se debe crear lo siguiente en Jira:

* Un usuario de integración del sistema
* Tres campos personalizados específicos

#### Creación de un usuario de integración del sistema en Jira

1. En Jira, cree un usuario específico llamado Usuario de integración del sistema. Este usuario solo debe utilizarlo Workfront Fusion y no debe representar a un usuario humano. Las credenciales de este usuario se utilizarán en las conexiones de Workfront Fusion.

#### Cree los campos personalizados necesarios en Jira

Esta integración espera tres campos específicos en la cuenta de Jira a la que se conecta. Sin estos campos, la integración no tendrá éxito

1. En Jira, ve a **Configuración** (icono de engranaje) y selecciona **Elementos de trabajo**.
1. En el panel de navegación izquierdo, seleccione **Campos personalizados**.
1. En la esquina superior derecha de la pantalla, haga clic en **Crear campo personalizado.**
1. Cree los campos siguientes:

   | Nombre de campo | Tipo de campo |
   |---|---|
   | ID de WF | Campo de texto (una sola línea) |
   | Estado de WF | Campo de texto (una sola línea) |
   | Vínculo WF | Campo de URL |

   Para obtener información sobre la creación de vínculos en Jira, consulte la documentación de Jira sobre la creación de campos.
1. Agregue los campos recién creados a la pantalla asociada con su proyecto Jira.

   Para obtener información sobre las pantallas de Jira, consulte la documentación de Jira sobre la configuración de pantallas de elementos de trabajo.


### Configuración de Workfront

Para utilizar estos módulos, se debe crear lo siguiente en Workfront:

* Un usuario de integración del sistema
* Un formulario personalizado específico

#### Creación de un usuario de integración del sistema en Workfront

1. En Workfront, cree un usuario de integración del sistema. Este usuario solo lo utiliza Workfront Fusion y no representa a un usuario humano. Las tareas asignadas a este usuario almacenarán en déclencheur el escenario que sincroniza Workfront con Jira.

   Para obtener instrucciones, consulte [Agregar usuarios](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/add-users/create-manage-users/add-users) en la documentación de Workfront.

#### Creación de un formulario personalizado en Workfront

1. En Workfront, empiece a crear un formulario personalizado.

   Para obtener instrucciones, consulte [Crear un formulario personalizado](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/customize/custom-forms/design-a-form/design-a-form) en la documentación de Workfront.
1. Asigne un nombre al formulario &quot;**Campos JIRA**&quot;.
1. Incluya los siguientes campos en el formulario personalizado:

| Nombre de campo | Tipo de campo |
|---|---|
| Clave Jira | Campo de texto de línea única |
| URL de Jira | Campo de texto de línea única |
| Estado de Jira | Campo de texto de línea única |

1. Añada cualquier campo adicional que quiera asignar entre Jira y Workfront.
1. Guarde el formulario personalizado.

>[!NOTE]
>
>Se recomienda restringir este formulario de las ediciones realizadas por otros usuarios. Puede hacerlo asegurándose de que los usuarios agregados al formulario personalizado solo tengan acceso de visualización.
>
>Para obtener instrucciones, consulte [Compartir un formulario personalizado](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/customize/custom-forms/manage-custom-forms/share-access-to-a-custom-form) en la documentación de Workfront.

### Configuración de conexiones en Workfront Fusion

Debe haber creado los usuarios de integración del sistema en Jira y Workfront para poder crear conexiones.

Al crear estas conexiones, asegúrese de utilizar las credenciales de los usuarios de integración del sistema creados.

Si lo desea, puede crear estas conexiones como parte de la configuración de las plantillas.

* Para obtener instrucciones sobre cómo crear una conexión con Workfront, consulte [Conectar Workfront a Workfront Fusion](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#connect-workfront-to-workfront-fusion) en el artículo Módulos de Workfront.
* Para obtener instrucciones sobre cómo crear una conexión con Jira, consulte [Conectar Jira a Workfront Fusion](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/jira-modules-new.md#connect-jira-to-workfront-fusion) en el artículo Módulos de software de Jira.


## Escenarios

Ocho plantillas listas para usar para Jira sirven para ayudar a replicar flujos de trabajo comunes y acelerar la implementación. Las plantillas son totalmente personalizables para satisfacer necesidades comerciales específicas y se pueden ampliar a medida que evolucionan los requisitos.

No es necesario implementar todos los escenarios. La implementación mínima requeriría el Escenario 1, que crearía una integración de una sola dirección para un problema de JIRA a partir de una asignación en Workfront.  Puede agregar los escenarios adicionales para agregar solidez y una mayor interconectividad bidireccional entre Workfront y JIRA.  También puede crear escenarios adicionales para tratar casos como la integración de un proyecto a épico o un problema de JIRA a un problema o tareas de Workfront.

Cualquier uso de estas plantillas o extensiones de estas plantillas se considera configuración personalizada, y recomendamos utilizar Adobe Professional Services o un socio de Adobe para el soporte y la implementación.

* **[Workfront a Jira: crear problema JIRA a partir de la asignación de tarea o problema de Workfront](#scenario-1-workfront-to-jira-create-jira-issue-from-workfront-task-or-issue-assignment)**
* [JIRA a Workfront: JIRA a Workfront: Enviar actualizaciones sobre problemas y comentarios de vuelta a Workfront desde JIRA](#scenario-2-jira-to-workfront-send-updates-on-issues-and-comments-back-to-workfront-from-jira)
* [Workfront a Jira: cambios en la tarea de Workfront a un problema con JIRA](#scenario-3-workfront-to-jira-changes-to-workfront-task-to-jira-issue)
* [Workfront a Jira: cambios en el problema de Workfront a un problema de JIRA](#scenario-4-workfront-to-jira-changes-to-workfront-issue-to-jira-issue)
* [Workfront a Jira: Crear comentarios en JIRA cuando se cree una nota nueva sobre una tarea o un problema de Workfront](#scenario-5-workfront-to-jira-create-comment-in-jira-when-new-note-on-workfront-task-or-issue)
* [De Workfront a Jira: Crear comentario en JIRA sobre una nota eliminada en una tarea o un problema de Workfront](#scenario-6-workfront-to-jira-create-comment-in-jira-on-deleted-note-on-workfront-task-or-issue)
* [Workfront a Jira: crear un comentario en JIRA cuando se cree un nuevo documento sobre una tarea o un problema de Workfront](#scenario-7-workfront-to-jira-create-comment-in-jira-when-new-document-on-workfront-task-or-issue)
* [Workfront a Jira: crear un comentario en JIRA sobre un documento eliminado en una tarea o un problema de Workfront](#scenario-8-workfront-to-jira-create-comment-in-jira-on-deleted-document-on-workfront-task-or-issue)

### Parámetros generales

Al configurar estas plantillas, utilice los siguientes parámetros generales:

* **JiraBaseURL**: URL base de la instancia de Jira. Ejemplo: `https://myjira.atlassian.net/`
* **wfBaseURL**: Dirección URL base de la instancia de Workfront.  Por lo general: `https://<domain>.my.workfront.com` donde `<domain>` es su nombre de dominio de Workfront en particular.
* **defaultJIRAReporterID**: ID del usuario en JIRA que crea problemas. (Ejemplo: `557058:5aedf933-2312-40bc-b328-0c21314167f0`)
Para obtener este ID, siga uno de estos procedimientos:
   * Haga clic en el perfil del usuario en JIRA y compruebe la URL en su explorador.
(Ejemplo`https://myjira.atlassian.net/jira/people/<JiraUserID>`)
   * Ejecute la siguiente llamada de API en la instancia de JIRA para obtener el ID de la cuenta específica en JIRA:
     `GET /rest/api/3/user/search?query=email@example.com`


### Escenario 1: de Workfront a Jira: crear un problema JIRA a partir de una asignación de tarea o problema de Workfront

Este escenario crea un problema con Jira cuando se asigna una tarea o un problema de Workfront al usuario de integración del sistema. El escenario se rellena en los campos Resumen, Descripción, Fecha de vencimiento, Estado de WF e ID de WF. Una vez creado el problema, este escenario también carga la lista de archivos adjuntos y el historial de notas relacionadas con la tarea o el problema original en Workfront.

Si se asigna una tarea de Workfront, el problema en Jira es una Tarea. Si se asigna un problema de Workfront, el problema de Jira es un error.

+++**Amplíe para ver las instrucciones para configurar el escenario 1:Workfront en Jira: cree un problema JIRA a partir de la asignación de tareas o problemas de Workfront**

#### Configuración del módulo de déclencheur

1. Haga clic en el **icono de plantillas** de la ficha ![Plantillas](assets/templates-icon.png) en el panel de navegación izquierdo.
1. Busque la plantilla utilizando la barra de búsqueda cerca de la esquina superior izquierda de la pantalla. Puede buscar por nombre de plantilla o aplicaciones incluidas.
1. Haga clic en **Workfront to Jira: crear problema JIRA a partir de la asignación de tarea o problema de Workfront**.

   Se abre una vista de la plantilla que muestra información y una animación del flujo de datos.
1. En el primer módulo, empiece a añadir un webhook.
1. Seleccione la conexión de Workfront que creó en [Configuración de conexiones en Workfront Fusion](#configure-connections-in-workfront-fusion).
1. En el campo **Tipo de registro**, seleccione `Assignment`.
1. En el campo **Estado**, seleccione `New state`.
1. Configure el filtro con las siguientes operaciones, usando la opción **And**:

   | Campo | Operador | Valor |
   |---|---|---|
   | assignedToID | Es igual a | (Introduzca el Workfront ID del usuario de integración del sistema) |
   | TaskID | Existe |  |
   | projectID | Es igual a | (Escriba el identificador del proyecto o proyectos que desea que vea el webhook) |

1. Habilite la opción **Excluir actualizaciones realizadas por esta conexión**.
1. En el campo **Origen del registro**, seleccione Solo nuevo registro.
1. Haga clic en **Guardar** para guardar el webhook y luego haga clic en **Aceptar** para guardar el módulo de déclencheur.
1. Continuar a [Conectar módulos de plantillas a Workfront y Jira](#connect-template-modules-to-workfront-and-jira)

#### Conexión de módulos de plantillas a Workfront y Jira

1. En **cada** módulo de Workfront, en el campo Conexión, seleccione la conexión de Workfront que creó en [Configurar conexiones en Workfront Fusion](#configure-connections-in-workfront-fusion) y, a continuación, haga clic en **Aceptar** para guardar la conexión con ese módulo.
1. En **cada** módulo Jira, en el campo Conexión, seleccione la conexión de Workfront que creó en [Configurar conexiones en Workfront Fusion](#configure-connections-in-workfront-fusion), luego haga clic en **Aceptar** para guardar la conexión a ese módulo.
1. Continúe con [Actualizar el módulo Parámetros generales](#update-the-general-parameters-module).

#### Actualización del módulo Parámetros generales

1. En el segundo módulo de la plantilla (Establecer detalles del entorno), para cada una de las siguientes variables, haga clic en **Agregar elemento** e introduzca el nombre y el valor de la variable

   | Nombre de variable | Valor variable |
   |---|---|
   | defaultJiraReporterID | Introduzca el ID del usuario predeterminado cuando el usuario creador no exista en Jira. Para encontrar este ID de usuario, haga clic en el perfil del usuario y compruebe la URL del explorador. Ejemplo: `https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | Introduzca la URL base de la cuenta de Jira a la que se está conectando. |
   | wfBaseURL | Introduzca la URL base de la cuenta de Workfront a la que se está conectando. |

1. Continuar a [Asignar campos personalizados en Jira](#map-custom-fields-in-jira)

<!--#### Map custom fields in Jira. 

Awaiting feedback-->

+++

### Escenario 2: de JIRA a Workfront: enviar actualizaciones sobre problemas y comentarios de vuelta a Workfront desde Jira

Este escenario crea una tarea o un problema de Workfront cuando se crea un problema en Jira.

>[!NOTE]
>
>Este escenario requiere una conexión OAuth2 para Jira.
>Para usar la autorización de OAuth2 para Jira, debe configurar una aplicación de OAuth2 en [https://developer.atlassian.com/console](https://developer.atlassian.com/console). Para obtener información e instrucciones, consulte la documentación de Jira.

+++**Amplíe para ver las instrucciones para configurar Scenario 2: JIRA en Workfront: envíe actualizaciones sobre problemas y comentarios de vuelta a Workfront desde Jira**

1. Haga clic en el **icono de plantillas** de la ficha ![Plantillas](assets/templates-icon.png) en el panel de navegación izquierdo.
1. Busque la plantilla utilizando la barra de búsqueda cerca de la esquina superior izquierda de la pantalla. Puede buscar por nombre de plantilla o aplicaciones incluidas.
1. Haga clic en **Parte 2: JIRA a Workfront: envía actualizaciones sobre problemas y comentarios de vuelta a Workfront desde la plantilla Jira**.

   Se abre una vista de la plantilla que muestra información y una animación del flujo de datos.
1. En el primer módulo, empiece a añadir un webhook.
1. Seleccione una conexión que utilice las credenciales del usuario de integración del sistema o cree una conexión con Jira con las credenciales de integración del sistema.

* Para obtener instrucciones sobre cómo crear una conexión con Jira, consulte [Conectar Jira a Workfront Fusion](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/jira-modules-new.md#connect-jira-to-workfront-fusion) en el artículo Módulos de software de Jira.

1. Configuración del filtro de ganchos web

1. Continuar a [Configurar un webhook en Jira](#configure-a-webhook-in-jira)

#### Configuración de un webhook en Jira

1. En Jira, cree un webhook.

   Para obtener instrucciones, consulte [Webhooks](https://developer.atlassian.com/server/jira/platform/webhooks/) en la documentación de Jira.

1. Al configurar el webhook, utilice los siguientes valores:

   * **JQL**: project = &quot;yourProjectName&quot; (donde yourProjectName = nombre de su proyecto JIRA)
   * **Problema**: creado, actualizado
   * **Comentario**: creado, eliminado


1. Continuar a [Conectar módulos de plantillas a Workfront y Jira (Módulo 2)](#connect-template-modules-to-workfront-and-jira-module-2)

#### Conexión de módulos de plantillas a Workfront y Jira (módulo 2)

1. En **cada** módulo de Workfront, en el campo Conexión, seleccione la conexión de Workfront que creó en [Configurar conexiones en Workfront Fusion](#configure-connections-in-workfront-fusion) y, a continuación, haga clic en **Aceptar** para guardar la conexión con ese módulo.
1. En **cada** módulo Jira, en el campo Conexión, seleccione la conexión de Workfront que creó en [Configurar conexiones en Workfront Fusion](#configure-connections-in-workfront-fusion), luego haga clic en **Aceptar** para guardar la conexión a ese módulo.
   <!--#### Map custom fields-->

+++

### Escenario 3: de Workfront a Jira: cambios en la tarea de Workfront a un problema con JIRA

+++**Amplíe para ver las instrucciones para configurar el escenario 3: cambios de WF a Jira (tareas)**

1. Haga clic en el **icono de plantillas** de la ficha ![Plantillas](assets/templates-icon.png) en el panel de navegación izquierdo.
1. Busque la plantilla utilizando la barra de búsqueda cerca de la esquina superior izquierda de la pantalla. Puede buscar por nombre de plantilla o aplicaciones incluidas.
1. Haga clic en la plantilla **Parte 3: Workfront to Jira: Changes to Workfront task to JIRA issue**.

   Se abre una vista de la plantilla que muestra información y una animación del flujo de datos.

1. Haga clic en la plantilla para introducir el editor.
1. Seleccione la organización y el equipo propietario de este escenario.
1. En el primer módulo, empiece a añadir un webhook.
1. En el campo Conexión, seleccione la conexión de Workfront que utiliza las credenciales de integración del sistema.
1. En el campo **Tipo de registro**, seleccione `Task`.
1. En el campo **Estado**, seleccione `New state`.
1. Configure el filtro con las siguientes operaciones, usando la opción **And**:

   | Campo | Operador | Valor |
   |---|---|---|
   | assignedToID | Es igual a | Introduzca el Workfront ID del usuario de integración del sistema |
   | projectID | Es igual a | Introduzca el ID del proyecto o proyectos que desea que vea el webhook. |
   | DE: Jira Key | Existe |  |

1. Habilite la opción **Excluir actualizaciones realizadas por esta conexión**.
1. En el campo **Origen del registro**, seleccione `Updated record only`.
1. Haga clic en **Guardar** para guardar el webhook y luego haga clic en **Aceptar** para guardar el módulo de déclencheur.
1. En el módulo **Establecer variables JIRA**, establezca las siguientes variables y haga clic en **Aceptar** para guardar el módulo.

   | Nombre de variable | Valor variable |
   |---|---|
   | defaultJiraReporterID | Este es el ID del usuario predeterminado cuando el Usuario creador no existe en Jira. Para encontrar este ID de usuario, haga clic en el perfil del usuario y compruebe la URL del explorador. Ejemplo: `https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | La URL base de la cuenta de Jira a la que se está conectando. |
   | wfBaseURL | La URL base de la cuenta de Workfront a la que se está conectando. |

1. En **cada** módulo de Workfront, en el campo Conexión, seleccione la conexión de Workfront que usa las credenciales de integración del sistema y, a continuación, haga clic en **Aceptar** para guardar el módulo.
1. En **cada** módulo Jira, en el campo Conexión, seleccione la conexión Jira que usa las credenciales de Integración del sistema, luego haga clic en **Aceptar** para guardar el módulo.

+++

### Escenario 4: de Workfront a Jira: cambios en el problema de Workfront a un problema de JIRA

Este escenario envía actualizaciones de problemas de Workfront a problemas de JIRA conectados anteriormente.

+++**Expanda para ver las instrucciones para configurar el escenario 4: Workfront a Jira: cambios en el problema de Workfront a problema de JIRA**

1. Haga clic en el **icono de plantillas** de la ficha ![Plantillas](assets/templates-icon.png) en el panel de navegación izquierdo.
1. Busque la plantilla utilizando la barra de búsqueda cerca de la esquina superior izquierda de la pantalla. Puede buscar por nombre de plantilla o aplicaciones incluidas.
1. Haga clic en la plantilla **Escenario 4: cambios de WF a Jira (problemas)**.

   Se abre una vista de la plantilla que muestra información y una animación del flujo de datos.

1. Haga clic en la plantilla para introducir el editor.
1. Seleccione la organización y el equipo propietario de este escenario.
1. En el primer módulo, empiece a añadir un webhook.
1. En el campo Conexión, seleccione la conexión de Workfront que utiliza las credenciales de integración del sistema.
1. En el campo **Tipo de registro**, seleccione `Issues`.
1. En el campo **Estado**, seleccione `New state`.
1. Configure el filtro con las siguientes operaciones, usando la opción **And**:

   | Campo | Operador | Valor |
   |---|---|---|
   | assignedToID | Es igual a | Introduzca el Workfront ID del usuario de integración del sistema |
   | projectID | Es igual a | Introduzca el ID del proyecto o proyectos que desea que vea el webhook. |
   | DE: Jira Key | Existe |  |

1. Habilite la opción **Excluir actualizaciones realizadas por esta conexión**.
1. En el campo **Origen del registro**, seleccione `Updated record only`.
1. Haga clic en **Guardar** para guardar el webhook y luego haga clic en **Aceptar** para guardar el módulo de déclencheur.
1. En el módulo **Establecer variables JIRA**, establezca las siguientes variables y haga clic en **Aceptar** para guardar el módulo.

   | Nombre de variable | Valor variable |
   |---|---|
   | defaultJiraReporterID | Este es el ID del usuario predeterminado cuando el Usuario creador no existe en Jira. Para encontrar este ID de usuario, haga clic en el perfil del usuario y compruebe la URL del explorador. Ejemplo: `https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | La URL base de la cuenta de Jira a la que se está conectando. |
   | wfBaseURL | La URL base de la cuenta de Workfront a la que se está conectando. |

1. En **cada** módulo de Workfront, en el campo Conexión, seleccione la conexión de Workfront que usa las credenciales de integración del sistema y, a continuación, haga clic en **Aceptar** para guardar el módulo.
1. En **cada** módulo Jira, en el campo Conexión, seleccione la conexión Jira que usa las credenciales de Integración del sistema, luego haga clic en **Aceptar** para guardar el módulo.

+++

### Escenario 5: de Workfront a Jira: crear un comentario en JIRA cuando haya una nueva nota sobre una tarea o un problema de Workfront

+++**Amplíe para ver las instrucciones para configurar el Escenario 5: de Workfront a Jira: crear un comentario en JIRA cuando se cree una nota nueva sobre una tarea o un problema de Workfront**

1. Haga clic en el **icono de plantillas** de la ficha ![Plantillas](assets/templates-icon.png) en el panel de navegación izquierdo.
1. Busque la plantilla utilizando la barra de búsqueda cerca de la esquina superior izquierda de la pantalla. Puede buscar por nombre de plantilla o aplicaciones incluidas.
1. Haga clic en **Escenario 5: WF a Jira Nuevas notas (tareas y problemas)** plantilla.

   Se abre una vista de la plantilla que muestra información y una animación del flujo de datos.
1. En el primer módulo, empiece a añadir un webhook.
1. En el campo Conexión, seleccione la conexión de Workfront que utiliza las credenciales de integración del sistema.
1. En el campo **Tipo de registro**, seleccione `Note`.
1. En el campo **Estado**, seleccione `New state`.
1. Configure el filtro con las siguientes operaciones:

   | Campo | Operador | Valor |
   |---|---|---|
   | projectID<br>AND<br>TaskID | Es igual a <br><br>Existe | Introduzca el ID del proyecto o proyectos que desea que vea el webhook. |
   | O |  |  |
   | projectID<br>AND<br>OpTaskID | Es igual a <br><br>Existe | Introduzca el ID del proyecto o proyectos que desea que vea el webhook. |

1. Habilite la opción **Excluir actualizaciones realizadas por esta conexión**.
1. En el campo **Origen del registro**, seleccione `New record only`.
1. Haga clic en **Guardar** para guardar el webhook y luego haga clic en **Aceptar** para guardar el módulo de déclencheur.
1. En el módulo **Set variables**, configure las siguientes variables y haga clic en **Aceptar** para guardar el módulo.

   | Nombre de variable | Valor variable |
   |---|---|
   | defaultJiraReporterID | Este es el ID del usuario predeterminado cuando el Usuario creador no existe en Jira. Para encontrar este ID de usuario, haga clic en el perfil del usuario y compruebe la URL del explorador. Ejemplo: `https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | La URL base de la cuenta de Jira a la que se está conectando. |
   | wfBaseURL | La URL base de la cuenta de Workfront a la que se está conectando. |

1. En **cada** módulo de Workfront, en el campo Conexión, seleccione la conexión de Workfront que usa las credenciales de integración del sistema y, a continuación, haga clic en **Aceptar** para guardar el módulo.
1. En **cada** módulo Jira, en el campo Conexión, seleccione la conexión Jira que usa las credenciales de Integración del sistema, luego haga clic en **Aceptar** para guardar el módulo.

+++

### Escenario 6: de Workfront a Jira: crear comentario en JIRA sobre una nota eliminada de una tarea o un problema de Workfront

+++**Amplíe para ver las instrucciones para configurar el Escenario 6: de Workfront a Jira: crear comentario en JIRA sobre una nota eliminada en una tarea o un problema de Workfront**

1. Haga clic en el **icono de plantillas** de la ficha ![Plantillas](assets/templates-icon.png) en el panel de navegación izquierdo.
1. Busque la plantilla utilizando la barra de búsqueda cerca de la esquina superior izquierda de la pantalla. Puede buscar por nombre de plantilla o aplicaciones incluidas.
1. Haga clic en **Escenario 6: WF-to-Jira Quitar notas (Tareas y problemas)** plantilla.

   Se abre una vista de la plantilla que muestra información y una animación del flujo de datos.
1. En el primer módulo, empiece a añadir un webhook.
1. En el campo Conexión, seleccione la conexión de Workfront que utiliza las credenciales de integración del sistema.
1. En el campo **Tipo de registro**, seleccione `Note`.
1. En el campo **Estado**, seleccione `New state`.
1. Configure el filtro con las siguientes operaciones:

   | Campo | Operador | Valor |
   |---|---|---|
   | projectID<br>AND<br>TaskID | Es igual a <br><br>Existe | Introduzca el ID del proyecto o proyectos que desea que vea el webhook. |
   | O |  |  |
   | projectID<br>AND<br>OpTaskID | Es igual a <br><br>Existe | Introduzca el ID del proyecto o proyectos que desea que vea el webhook. |

1. Habilite la opción **Excluir actualizaciones realizadas por esta conexión**.
1. En el campo **Origen del registro**, seleccione `Deleted record only`.
1. Haga clic en **Guardar** para guardar el webhook y luego haga clic en **Aceptar** para guardar el módulo de déclencheur.
1. En el segundo módulo, configure las siguientes variables y luego haga clic en **Aceptar** para guardar el módulo.

   | Nombre de variable | Valor variable |
   |---|---|
   | defaultJiraReporterID | Este es el ID del usuario predeterminado cuando el Usuario creador no existe en Jira. Para encontrar este ID de usuario, haga clic en el perfil del usuario y compruebe la URL del explorador. Ejemplo: `https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | La URL base de la cuenta de Jira a la que se está conectando. |
   | wfBaseURL | La URL base de la cuenta de Workfront a la que se está conectando. |

1. En **cada** módulo de Workfront, en el campo Conexión, seleccione la conexión de Workfront que usa las credenciales de integración del sistema y, a continuación, haga clic en **Aceptar** para guardar el módulo.
1. En **cada** módulo Jira, en el campo Conexión, seleccione la conexión Jira que usa las credenciales de Integración del sistema, luego haga clic en **Aceptar** para guardar el módulo.

+++

### Escenario 7: de Workfront a Jira: crear un comentario en JIRA cuando se cree un nuevo documento sobre una tarea o un problema de Workfront

+++**Amplíe para ver las instrucciones para configurar el Escenario 7: de Workfront a Jira: crear un comentario en JIRA cuando se cree un nuevo documento sobre una tarea o un problema de Workfront**

1. Haga clic en el **icono de plantillas** de la ficha ![Plantillas](assets/templates-icon.png) en el panel de navegación izquierdo.
1. Busque la plantilla utilizando la barra de búsqueda cerca de la esquina superior izquierda de la pantalla. Puede buscar por nombre de plantilla o aplicaciones incluidas.
1. Haga clic en **Escenario 7: WF a Jira Nuevos archivos adjuntos (tareas y problemas)** plantilla.

   Se abre una vista de la plantilla que muestra información y una animación del flujo de datos.
1. En el primer módulo, empiece a añadir un webhook.
1. En el campo Conexión, seleccione la conexión de Workfront que utiliza las credenciales de integración del sistema.
1. En el campo **Tipo de registro**, seleccione `Document`.
1. En el campo **Estado**, seleccione `New state`.
1. Configure el filtro con las siguientes operaciones, usando la opción **And**:

   | Campo | Operador | Valor |
   |---|---|---|
   | assignedToID | Es igual a | Introduzca el Workfront ID del usuario de integración del sistema |
   | projectID | Es igual a | Introduzca el ID del proyecto o proyectos que desea que vea el webhook. |

1. En el segundo módulo, configure las siguientes variables.

   | Nombre de variable | Valor variable |
   |---|---|
   | defaultJiraReporterID | Este es el ID del usuario predeterminado cuando el Usuario creador no existe en Jira. Para encontrar este ID de usuario, haga clic en el perfil del usuario y compruebe la URL del explorador. Ejemplo: `https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | La URL base de la cuenta de Jira a la que se está conectando. |
   | wfBaseURL | La URL base de la cuenta de Workfront a la que se está conectando. |

1. Habilite la opción **Excluir actualizaciones realizadas por esta conexión**.
1. En el campo **Origen del registro**, seleccione `New record only`.
1. Haga clic en **Guardar** para guardar el webhook y luego haga clic en **Aceptar** para guardar el módulo de déclencheur.
1. En **cada** módulo de Workfront, en el campo Conexión, seleccione la conexión de Workfront que usa las credenciales de integración del sistema y, a continuación, haga clic en **Aceptar** para guardar el módulo.
1. En **cada** módulo Jira, en el campo Conexión, seleccione la conexión Jira que usa las credenciales de Integración del sistema, luego haga clic en **Aceptar** para guardar el módulo.

+++

### Escenario 8: de Workfront a Jira: crear un comentario en JIRA sobre un documento eliminado en una tarea o un problema de Workfront

+++**Expanda para ver las instrucciones para configurar el Escenario 8: de Workfront a Jira: crear un comentario en JIRA en un documento eliminado en una tarea o un problema de Workfront**

1. Haga clic en el **icono de plantillas** de la ficha ![Plantillas](assets/templates-icon.png) en el panel de navegación izquierdo.
1. Busque la plantilla utilizando la barra de búsqueda cerca de la esquina superior izquierda de la pantalla. Puede buscar por nombre de plantilla o aplicaciones incluidas.
1. Haga clic en **Escenario 8: WF-to-Jira Quitar archivos adjuntos (tareas y problemas)** plantilla.

   Se abre una vista de la plantilla que muestra información y una animación del flujo de datos.
1. En el primer módulo, empiece a añadir un webhook.
1. En el campo Conexión, seleccione la conexión de Workfront que utiliza las credenciales de integración del sistema.
1. En el campo **Tipo de registro**, seleccione `Document`.
1. En el campo **Estado**, seleccione `New state`.
1. Configure el filtro con las siguientes operaciones:

   | Campo | Operador | Valor |
   |---|---|---|
   | projectID<br>AND<br>TaskID | Es igual a <br><br>Existe | Introduzca el ID del proyecto o proyectos que desea que vea el webhook. |
   | O |  |  |
   | projectID<br>AND<br>OpTaskID | Es igual a <br><br>Existe | Introduzca el ID del proyecto o proyectos que desea que vea el webhook. |

1. En el módulo **Set variables**, establezca las siguientes variables.

   | Nombre de variable | Valor variable |
   |---|---|
   | defaultJiraReporterID | Este es el ID del usuario predeterminado cuando el Usuario creador no existe en Jira. Para encontrar este ID de usuario, haga clic en el perfil del usuario y compruebe la URL del explorador. Ejemplo: `https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | La URL base de la cuenta de Jira a la que se está conectando. |
   | wfBaseURL | La URL base de la cuenta de Workfront a la que se está conectando. |

1. Habilite la opción **Excluir actualizaciones realizadas por esta conexión**.
1. En el campo **Origen del registro**, seleccione `Deleted record only`.
1. Haga clic en **Guardar** para guardar el webhook y luego haga clic en **Aceptar** para guardar el módulo de déclencheur.
1. En **cada** módulo de Workfront, en el campo Conexión, seleccione la conexión de Workfront que usa las credenciales de integración del sistema y, a continuación, haga clic en **Aceptar** para guardar el módulo.
1. En **cada** módulo Jira, en el campo Conexión, seleccione la conexión Jira que usa las credenciales de Integración del sistema, luego haga clic en **Aceptar** para guardar el módulo.


+++

