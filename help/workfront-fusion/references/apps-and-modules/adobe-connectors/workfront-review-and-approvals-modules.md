---
title: Módulos de contenido y aprobaciones de Adobe Workfront
description: Con los módulos Contenido y aprobaciones de Adobe Workfront, puede obtener detalles de aprobación, tomar una decisión sobre un recurso, agregar o eliminar participantes de aprobación, agregar o actualizar etapas de aprobación, bloquear o desbloquear etapas y hacer llamadas de API personalizadas.
author: Becky
feature: Workfront Fusion
exl-id: d1bc9e39-da49-4090-a106-14b52855bc8f
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
    internal-label: Integrations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 4f637dcb9d7865f73b41faa5b0acf397944bb559
workflow-type: tm+mt
source-wordcount: '5202'
ht-degree: 12%
---
# Módulos de revisión y aprobaciones unificados de Adobe Workfront

Con los módulos Adobe Workfront Unified Review and Approvals, puede obtener detalles de aprobación, tomar una decisión sobre un recurso, agregar o eliminar participantes de aprobación, agregar o actualizar etapas de aprobación, bloquear o desbloquear etapas y hacer llamadas de API personalizadas.

Para obtener información acerca de la revisión unificada y las aprobaciones de Workfront, consulte [Revisión unificada y descripción general de la aprobación](https://experienceleague.adobe.com/en/docs/workfront/using/review-and-approve-work/document-approvals-overview) en la documentación de Workfront.

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

## Requisitos previos

Debe tener lo siguiente para acceder al contenido y las aprobaciones de Workfront:

* Debe contar con una versión de Workfront que admita el almacenamiento en la nube de Adobe. Si su organización aún no tiene una versión compatible, póngase en contacto con el representante de cuentas de Adobe.

## Conectarse a Adobe Workfront Unified Review and Approvals


1. En cualquier módulo de revisión y aprobaciones unificadas de Adobe Workfront, haga clic en **Agregar** junto al campo Conexión.
1. Rellene los campos siguientes:

   <table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL Connection type]</td>
        <td>
          <p>Seleccione <b>Conexión de servidor a servidor de Adobe Workfront</b>.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>Introduzca un nombre para la nueva conexión.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Instance name]</td>
        <td>
          <p>Introduzca el nombre de su instancia, también conocido como su dominio.</p><p>Ejemplo: si su URL es <code>https://example.my.workfront.com</code>, introduzca <code>example</code>.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Instance lane]</td>
        <td>
          <p>Introduzca el tipo de entorno al que se conectará esta conexión.</p><p>Ejemplo: si su URL es <code>https://example.my.workfront.com</code>, introduzca <code>my</code>.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Introduzca su ID de cliente de Workfront. Esto se puede encontrar en el área Aplicaciones OAuth2 del área Configuración en Workfront. Abra la aplicación específica a la que se está conectando para ver el ID de cliente.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Introduzca el secreto de cliente de Workfront. Esto se puede encontrar en el área Aplicaciones OAuth2 del área Configuración en Workfront. Si no dispone de un secreto de cliente para la aplicación OAuth2 en Workfront, puede generar otro. Para obtener instrucciones, consulte la documentación de Workfront.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Scopes]</td>
        <td>Escriba los ámbitos aplicables para esta conexión.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Host prefix]</td>
        <td>En la mayoría de los casos, este valor debe ser <code>origin</code>.
      </tr>
    </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.

   Si no ha iniciado sesión en Workfront Unified Review and Approvals, se le dirigirá a una pantalla de inicio de sesión. Después de iniciar sesión, puede permitir la conexión.

## Módulos de revisión y aprobaciones unificados de Adobe Workfront

Al configurar los módulos de Workfront, Workfront Fusion muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse campos adicionales de Workfront, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, consulte [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).


![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Acciones](#actions)
* [Búsquedas](#searches)
* [Otros](#other)

### Acciones

* [Adición o actualización de participantes](#add-or-update-participants)
* [Eliminar plantillas por lotes](#bulk-delete-templates)
* [Creación de una plantilla](#create-a-template)
* [Crear aprobación agrupada](#create-grouped-approval)
* [Creación de fases](#create-stages)
* [Bloquear un escenario](#lock-a-stage)
* [Tomar una decisión](#make-a-decision)
* [Tomar una decisión en un escenario](#make-a-decision-on-a-stage)
* [Administrar recursos en una aprobación agrupada](#manage-assets-on-a-grouped-approval)
* [Administrar participantes del escenario](#manage-stage-participants)
* [Administración de fases en una aprobación agrupada](#manage-stages-on-a-grouped-approval)
* [Recordar a un participante de un escenario](#remind-a-participant-on-a-stage)
* [Recordar participante](#remind-participant)
* [Recordar a los participantes que no han tomado una decisión](#remind-undecided-participants)
* [Recordatorio de participantes indecisos en un escenario](#remind-undecided-participants-on-a-stage)
* [Desbloquear una fase](#unlock-a-stage)
* [Actualización de una fase](#update-a-stage)
* [Actualizar una plantilla](#update-a-template)
* [Actualizar todas las fases](#update-all-stages)
* [Actualizar aprobación agrupada (estado completo)](#update-grouped-approval-full-state)


#### Adición o actualización de participantes

Este módulo de acción añade o actualiza participantes en la fase predeterminada de una aprobación.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>Identificador del documento</p>
      </td>
      <td>Introduzca o asigne el ID del activo para el que desea añadir o actualizar un participante.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>Agregar participantes a las fases</p>
      </td>
      <td>Para cada etapa a la que desee agregar participantes, haga clic en <b>Agregar elemento</b> e ingrese a la etapa.<p> A continuación, para cada participante que desee agregar al escenario, haga clic en <b>Agregar elemento</b> e introduzca los detalles del participante.</p>
      <ul>
      <li><b>ID de participante</b><p>Introduzca o asigne el ID del participante.</p></li>
      <li><b>Tipo de participante</b><p>Seleccione si el participante es un usuario o un equipo.</p></li>
      <li><b>Función de participante</b><p>Seleccione si el participante es aprobador o revisor.</p></li>
      </ul> 
      </td> 
      </tr>
  </tbody>
</table>

#### Eliminar plantillas por lotes

Este módulo elimina las plantillas de aprobación especificadas.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ID de plantilla</p></td>
      <td>Para cada plantilla que desee eliminar, haga clic en <b>Agregar elemento</b> e introduzca el identificador de la plantilla.</td> 
      </tr>
  </tbody>
</table>

#### Creación de una plantilla

Este módulo de acción crea una plantilla de aprobación

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Nombre</p></td>
      <td>Introduzca o asigne un nombre para la plantilla.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Identificador de compañía</p></td>
      <td>Si desea agregar un ámbito de empresa a la plantilla, introduzca o asigne el ID de empresa.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>Fases</p>
      </td>
      <td>Para cada fase que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca los datos de la fase.<p>Para obtener detalles específicos, consulte <a href="#stages-fields" class="MCXref xref" >Campos de etapas</a> en este artículo. </p> </td> 
      </tr>
    <tr>
      <td role="rowheader"><p>Compartido con</p></td>
      <td>Para cada usuario con el que desee compartir la plantilla, haga clic en <b>Agregar elemento</b>, el identificador de usuario y el nivel de acceso deseado.</td> 
      </tr>
  </tbody>
</table>

#### Crear aprobación agrupada

Este módulo de acción crea una aprobación agrupada: un conjunto de versiones de documento que se mueven juntas a través de una o más rutas de aprobación, cada una de las cuales crea una secuencia ordenada de etapas con sus propios participantes.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Nombre</p></td>
      <td>Introduzca o asigne un nombre para mostrar para la aprobación agrupada. El nombre debe tener entre 1 y 255 caracteres.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Recursos</p></td>
      <td>Para cada versión del documento que desee incluir en el grupo, haga clic en <b>Agregar elemento</b> e introduzca el identificador de la versión del documento (DOCV).</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Rutas</p></td>
      <td>Para cada ruta de aprobación que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca la ID de ruta, el nombre y las fases. Cada ruta contiene una secuencia ordenada de etapas. Para cada fase, en el campo Fases, haga clic en <b>Agregar elemento</b> e introduzca los siguientes datos:
      <ul>
      <li><b>ID de fase</b><p>Introduzca un identificador asignado por el cliente para la fase, único en todas las rutas. Debe ser alfanumérico, con guiones bajos o guiones permitidos y no más de 64 caracteres.</p></li>
      <li><b>Nombre de la fase</b><p>Introduzca o asigne un nombre para la etapa.</p></li>
      <li><b>Identificadores de fase principal</b><p>Para cada etapa principal que desee agregar a la etapa, haga clic en <b>Agregar elemento</b> e introduzca el identificador principal.</p></li>
      <li><b>Participantes</b><p>Para cada participante que desee agregar al escenario, haga clic en <b>Agregar elemento</b> e introduzca los detalles del participante.
      <ul>
      <li><b>ID de participante</b><p>Introduzca o asigne el ID del participante.</p></li>
      <li><b>Tipo de participante</b><p>Seleccione si el participante es un usuario o un equipo.</p></li>
      <li><b>Función de participante</b><p>Seleccione si el participante es aprobador o revisor.</p></li>
      </ul>
      </p></li>
      <li><b>Fecha límite</b><p>Si la fecha límite es una fecha específica, introduzca o asigne la fecha.</p></li>
      <li><b>Días laborables hasta la fecha límite</b><p>Si la fecha límite es posterior a un número específico de días hábiles, introduzca o asigne el número de días.</p></li>
      <li><b>Hora límite: horas</b><p>Introduzca o asigne la hora del día para la fecha límite (0-23). Emparejar con tiempo de espera: minutos.</p></li>
      <li><b>Tiempo de vencimiento: minutos</b><p>Introduzca o asigne el minuto de la hora para la fecha límite (0-59). Emparejar con tiempo de espera: horas.</p></li>
      <li><b>Mensaje personalizado</b><p>Introduzca o asigne un mensaje personalizado para el escenario.</p></li>
      </ul>
      </td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Identificador de objeto principal</p></td>
      <td>Introduzca o asigne el ID del objeto principal de Workfront (por ejemplo, un proyecto o una tarea) que desee asociar a la aprobación agrupada. Si utiliza este campo, también debe introducir el Object Code.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Código de objeto</p></td>
      <td>Escriba o asigne el código de tipo de objeto Workfront para el objeto principal (por ejemplo, <code>PROJ</code> o <code>TASK</code>). Obligatorio si se introduce un ID de objeto principal.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Identificador de plantilla</p></td>
      <td>(Opcional) Introduzca o asigne un ID de plantilla para registrarlo en la aprobación agrupada para rastrear.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Límite</p></td>
      <td>Introduzca o asigne el número máximo de resultados con los que desea que trabaje el módulo durante cada ciclo de ejecución de escenario.</td> 
      </tr>
  </tbody>
</table>

#### Creación de fases

Este módulo de acción crea una aprobación con los datos de fase dados.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificador del documento</p></td>
      <td>Introduzca o asigne el ID del recurso para el que desea crear o actualizar una fase.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>Fases</p>
      </td>
      <td>Para cada fase que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca los datos de la fase.<p>Para obtener detalles específicos, consulte <a href="#stages-fields" class="MCXref xref" >Campos de etapas</a> en este artículo. </p> </td> 
      </tr>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificador de plantilla</p></td>
      <td>Introduzca o asigne el ID del recurso para el que desea crear fases.</td> 
      </tr>
  </tbody>
</table>

<!--
BECKY CHECK ME: The following block of Delete-prefixed Actions modules (Delete a decision on a stage, Delete a stage, Delete a template, Delete an approval, Delete decisions, Delete grouped approval, Delete participants) is not confirmed to be current in the live connector as of this update - status uncertain. Commented out for now; restore (and remove this comment) once confirmed, or delete for good if confirmed removed.

#### Delete a decision on a stage

This module removes the current user's decision from the specified stage. The current user is the user whose credentials are used in the connection used in this module.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Connection</td>
      <td>For instructions on creating a connection to Adobe Workfront Unified Review and Approvals, see <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Connect to Adobe Workfront Unified Review and Approvals</a> in this article.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Document ID</p></td>
      <td>Enter or map the ID of the document that you want to delete a decision from.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Stage ID</p></td>
      <td>Enter or map the ID of the stage that you want to delete.</td> 
      </tr>
   </tbody>
</table>


#### Delete a stage

This action module deletes the specified stage from the approval.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Connection</td>
      <td>For instructions on creating a connection to Adobe Workfront Unified Review and Approvals, see <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Connect to Adobe Workfront Unified Review and Approvals</a> in this article.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Document ID</p></td>
      <td>Enter or map the ID of the document that you want to delete a stage from.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Stage ID</p></td>
      <td>Enter or map the ID of the stage that you want to delete.</td> 
      </tr>
  </tbody>
</table>

#### Delete a template

This module deletes the specified approval template.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Connection</td>
      <td>For instructions on creating a connection to Adobe Workfront Unified Review and Approvals, see <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Connect to Adobe Workfront Unified Review and Approvals</a> in this article.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Template ID</p></td>
      <td>Enter or map the ID of the template that you want to delete.</td> 
      </tr>
  </tbody>
</table>

#### Delete an approval

This action module deletes the approval for the given document.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Connection</td>
      <td>For instructions on creating a connection to Adobe Workfront Unified Review and Approvals, see <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Connect to Adobe Workfront Unified Review and Approvals</a> in this article.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Document ID</p></td>
      <td>Enter or map the ID of the document that you want to delete an approval from.</td> 
      </tr>
  </tbody>
</table>

#### Delete decisions

This module removes the current user's decision from the specified stage. The current user is the user whose credentials are used in the connection used in this module.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Connection</td>
      <td>For instructions on creating a connection to Adobe Workfront Unified Review and Approvals, see <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Connect to Adobe Workfront Unified Review and Approvals</a> in this article.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Document ID</p></td>
      <td>Enter or map the ID of the document that you want to delete a decision from.</td> 
      </tr>
  </tbody>
</table>

#### Delete grouped approval

This action module deletes a grouped approval, cascading to its child asset approvals and paths.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Connection</td>
      <td>For instructions on creating a connection to Adobe Workfront Unified Review and Approvals, see <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Connect to Adobe Workfront Unified Review and Approvals</a> in this article.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Group GUID</p></td>
      <td>Enter or map the GUID of the grouped approval that you want to delete.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Limit</p></td>
      <td>Enter or map the maximum number of results you want the module to work with during each scenario execution cycle.</td> 
      </tr>
  </tbody>
</table>

#### Delete participants

This action module deletes participants from an approval.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Connection</td>
      <td>For instructions on creating a connection to Adobe Workfront Unified Review and Approvals, see <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Connect to Adobe Workfront Unified Review and Approvals</a> in this article.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Document ID</p></td>
      <td>Enter or map the ID of the asset that you want to delete participants from.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>Participant type</p>
      </td>
      <td>Select whether the participants is a user or a team.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>Participant ID</p>
      </td>
      <td>Enter or map the ID of the participant.</td> 
      </tr>
  </tbody>
</table>
-->

#### Bloquear un escenario

Estos módulos de acción bloquean la fase de aprobación especificada y la establece en inactiva.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificador del documento</p></td>
      <td>Introduzca o asigne el ID del recurso que desea bloquear.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>ID de fase</p>
      </td>
      <td>Introduzca o asigne el ID del escenario que desea bloquear.</td> 
      </tr>
  </tbody>
</table>

#### Tomar una decisión

Este módulo de acción aplica una decisión a una fase de aprobación o aprobación.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificador del documento</p></td>
      <td>Introduzca o asigne el ID del recurso que desea bloquear.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Decisión</p></td>
      <td>Seleccione la decisión que desea aplicar a la aprobación o fase.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>ID de fase</p>
      </td>
      <td>Para cada fase a la que desee aplicar la decisión, haga clic en <b>Agregar elemento</b> e introduzca el ID de la fase.</td> 
      </tr>
  </tbody>
</table>

#### Tomar una decisión en un escenario

Este módulo aplica una decisión a la fase especificada.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificador del documento</p></td>
      <td>Introduzca o asigne el ID del documento sobre el que desea tomar una decisión.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>ID de fase</p></td>
      <td>Introduzca o asigne el ID de la etapa en la que desea tomar una decisión.</td> 
      </tr>
    <tr>
      <td role="rowheader"><p>Decisión</p></td>
      <td>Seleccione la decisión que desee aplicar a esta fase.</td> 
      </tr>
  </tbody>
</table>

#### Administrar recursos en una aprobación agrupada

Este módulo de acción añade o elimina versiones de documentos en una aprobación agrupada.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificador de aprobación agrupada</p></td>
      <td>Introduzca o asigne el GUID de la aprobación agrupada en la que desea administrar los recursos.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Añadir Assets</p></td>
      <td>Para cada versión de documento que desee agregar al grupo, haga clic en <b>Agregar elemento</b> e introduzca el identificador de la versión del documento (DOCV).</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Eliminar Assets</p></td>
      <td>Para cada versión de documento que desee quitar del grupo, haga clic en <b>Agregar elemento</b> e introduzca el identificador de la versión del documento (DOCV).</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Límite</p></td>
      <td>Introduzca o asigne el número máximo de resultados con los que desea que trabaje el módulo durante cada ciclo de ejecución de escenario.</td> 
      </tr>
  </tbody>
</table>

#### Administrar participantes del escenario

Este módulo de acción agrega, actualiza o elimina participantes en una fase específica de una aprobación agrupada.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificador de aprobación agrupada</p></td>
      <td>Introduzca o asigne el GUID de la aprobación agrupada.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>ID de fase</p></td>
      <td>Introduzca o asigne el ID de la etapa en la que desea administrar participantes.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Agregar participantes</p></td>
      <td>Para cada participante que desee agregar al escenario, haga clic en <b>Agregar elemento</b> e introduzca los siguientes detalles:
      <ul>
      <li><b>Tipo de participante</b><p>Seleccione si el participante es un usuario o un equipo.</p></li>
      <li><b>Participante</b><p>Introduzca o asigne el ID del participante.</p></li>
      <li><b>Función</b><p>Seleccione si el participante es aprobador o revisor.</p></li>
      </ul>
      </td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Actualizar participantes</p></td>
      <td>Para cada participante que desee actualizar en el escenario, haga clic en <b>Agregar elemento</b> e introduzca los siguientes detalles:
      <ul>
      <li><b>Tipo de participante</b><p>Seleccione si el participante es un usuario o un equipo.</p></li>
      <li><b>Participante</b><p>Introduzca o asigne el ID del participante.</p></li>
      <li><b>Función</b><p>Seleccione si el participante es aprobador o revisor.</p></li>
      </ul>
      </td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Quitar participantes</p></td>
      <td>Para cada participante que desee eliminar del escenario, haga clic en <b>Agregar elemento</b> e introduzca los siguientes detalles:
      <ul>
      <li><b>Tipo de participante</b><p>Seleccione si el participante es un usuario o un equipo.</p></li>
      <li><b>Participante</b><p>Introduzca o asigne el ID del participante.</p></li>
      </ul>
      </td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Límite</p></td>
      <td>Introduzca o asigne el número máximo de resultados con los que desea que trabaje el módulo durante cada ciclo de ejecución de escenario.</td> 
      </tr>
  </tbody>
</table>

#### Administración de fases en una aprobación agrupada

Este módulo de acción añade, actualiza o elimina etapas en una aprobación agrupada.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificador de aprobación agrupada</p></td>
      <td>Introduzca o asigne el GUID de la aprobación agrupada.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Agregar fases</p></td>
      <td>Para cada fase que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca los siguientes detalles:
      <ul>
      <li><b>ID de fase</b><p>Introduzca o asigne un identificador para la fase.</p></li>
      <li><b>Nombre de la fase</b><p>Introduzca o asigne un nombre para la etapa.</p></li>
      <li><b>Fecha límite</b><p>Si la fecha límite es una fecha específica, introduzca o asigne la fecha.</p></li>
      <li><b>Días laborables hasta la fecha límite</b><p>Si la fecha límite es posterior a un número específico de días hábiles, introduzca o asigne el número de días.</p></li>
      <li><b>Mensaje personalizado</b><p>Introduzca o asigne un mensaje personalizado para el escenario.</p></li>
      </ul>
      </td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Actualizar fases</p></td>
      <td>Para cada fase que desee actualizar, haga clic en <b>Agregar elemento</b> e introduzca los siguientes detalles:
      <ul>
      <li><b>ID de fase</b><p>Introduzca o asigne el ID de la fase que desea actualizar.</p></li>
      <li><b>Nombre de la fase</b><p>Introduzca o asigne un nombre para la etapa.</p></li>
      <li><b>Fecha límite</b><p>Si la fecha límite es una fecha específica, introduzca o asigne la fecha.</p></li>
      <li><b>Días laborables hasta la fecha límite</b><p>Si la fecha límite es posterior a un número específico de días hábiles, introduzca o asigne el número de días.</p></li>
      <li><b>Mensaje personalizado</b><p>Introduzca o asigne un mensaje personalizado para el escenario.</p></li>
      </ul>
      </td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Eliminar etapas</p></td>
      <td>Para cada fase que desee eliminar, haga clic en <b>Agregar elemento</b> e introduzca el ID de la fase.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Límite</p></td>
      <td>Introduzca o asigne el número máximo de resultados con los que desea que trabaje el módulo durante cada ciclo de ejecución de escenario.</td> 
      </tr>
  </tbody>
</table>

#### Recordar a un participante de un escenario

Este módulo envía un recordatorio a un participante específico sobre una fase específica.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificador del documento</p></td>
      <td>Introduzca o asigne el ID del recurso para el que desea enviar un recordatorio.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>ID de fase</p>
      </td>
      <td>Introduzca o asigne el ID de la fase para la que desea enviar un recordatorio.</td> 
      </tr>
    </tr>
     <tr>
      <td role="rowheader"><p>ID de participante</p></td>
      <td>Introduzca o asigne el ID del participante al que desea enviar un recordatorio.</td> 
      </tr>
  </tbody>
</table>

#### Recordar participante

Este módulo envía una notificación recordatoria al participante especificado.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificador del documento</p></td>
      <td>Introduzca o asigne el ID del recurso para el que desea enviar un recordatorio.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>ID de participante</p>
      </td>
      <td>Introduzca o asigne el ID del participante que desea recordar.</td> 
      </tr>
      <tr>
      <td role="rowheader">
        <p>Tipo de participante</p>
      </td>
      <td>Introduzca o asigne el tipo de participante que desea recordar.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>Función de participante</p>
      </td>
      <td>Introduzca o asigne la función del participante que desea recordar.</td> 
      </tr>
  </tbody>
</table>

#### Recordar a los participantes que no han tomado una decisión

Este módulo envía notificaciones de recordatorio a todos los participantes indecisos sobre la aprobación especificada.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificador del documento</p></td>
      <td>Introduzca o asigne el ID del recurso para el que desea enviar un recordatorio.</td> 
      </tr>
  </tbody>
</table>

#### Recordatorio de participantes indecisos en un escenario

Este módulo envía notificaciones recordatorias a todos los participantes indecisos en una fase.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificador del documento</p></td>
      <td>Introduzca o asigne el ID del recurso para el que desea enviar un recordatorio.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>ID de fase</p>
      </td>
      <td>Introduzca o asigne el ID de la fase para la que desea enviar un recordatorio.</td> 
      </tr>
  </tbody>
</table>

#### Desbloquear una fase

Estos módulos de acción desbloquean la fase de aprobación especificada y la establecen como activa.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificador del documento</p></td>
      <td>Introduzca o asigne el ID del recurso que desea desbloquear.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>ID de fase</p>
      </td>
      <td>Introduzca o asigne el ID del escenario que desea bloquear.</td> 
      </tr>
  </tbody>
</table>


#### Actualización de una fase

Este módulo de acción actualiza los campos del paso especificado.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificador del documento</p></td>
      <td>Introduzca o asigne el ID del documento sobre el que desea tomar una decisión.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>ID de fase</p></td>
      <td>Introduzca o asigne el ID de la etapa en la que desea tomar una decisión.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Nombre de la fase</p></td>
      <td>Introduzca o asigne un nombre para la plantilla.</td> 
      </tr>
      <td role="rowheader">
        <p>Otros campos</p>
      </td>
      <td>Introduzca datos en los campos de fase.<p>Para obtener más información, consulte <a href="#stages-fields" class="MCXref xref" >Campos de etapas</a> en este artículo. </p> </td> 
      </tr>
    <tr>
      <td role="rowheader"><p>Compartido con</p></td>
      <td>Para cada usuario con el que desee compartir la plantilla, haga clic en <b>Agregar elemento</b>, el identificador de usuario y el nivel de acceso deseado.</td> 
      </tr>
  </tbody>
</table>

#### Actualizar una plantilla

Este módulo actualiza los campos de la plantilla de aprobación especificada.



<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificador de plantilla</p></td>
      <td>Introduzca o asigne un nombre para la plantilla.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Nombre</p></td>
      <td>Introduzca o asigne el ID de la plantilla que desea actualizar.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Identificador de compañía</p></td>
      <td>Si desea agregar un ámbito de empresa a la plantilla, introduzca o asigne el ID de empresa.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>Fases</p>
      </td>
      <td>Para cada fase que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca los datos de la fase.<p>Para obtener detalles específicos, consulte <a href="#stages-fields" class="MCXref xref" >Campos de etapas</a> en este artículo. </p> </td> 
      </tr>
    <tr>
      <td role="rowheader"><p>Compartido con</p></td>
      <td>Para cada usuario con el que desee compartir la plantilla, haga clic en <b>Agregar elemento</b>, el identificador de usuario y el nivel de acceso deseado.</td> 
      </tr>
  </tbody>
</table>

#### Actualizar todas las fases

Este módulo reemplaza todas las etapas de una aprobación existente con los datos de etapa dados. El documento debe estar en un estado editable.



<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificador del documento</p></td>
      <td>Introduzca o asigne el ID del recurso para el que desea actualizar las fases.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>Fases</p>
      </td>
      <td>Para cada fase que desee actualizar, haga clic en <b>Agregar elemento</b> e introduzca los datos de la fase.<p>Para obtener detalles específicos, consulte <a href="#stages-fields" class="MCXref xref" >Campos de etapas</a> en este artículo. </p> </td> 
      </tr>
  </tbody>
</table>

#### Actualizar aprobación agrupada (estado completo)

Este módulo de acción aplica una actualización de estado completo a una aprobación agrupada.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificador de aprobación agrupada</p></td>
      <td>Introduzca o asigne el GUID de la aprobación agrupada que desea actualizar. Por ejemplo, <code>9f8b60820000462ecf66c409d1248fa9</code>.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Rutas</p></td>
      <td>Para cada ruta de aprobación que desee que tenga la aprobación agrupada, haga clic en <b>Agregar elemento</b> e introduzca el identificador de ruta, el nombre y las fases. Fusion lo concilia con el estado actual, añadiendo, actualizando y eliminando rutas para que coincidan con lo que envía. Cada ruta contiene una secuencia ordenada de etapas. Para cada fase, en el campo Fases, haga clic en <b>Agregar elemento</b> e introduzca los siguientes datos:
      <ul>
      <li><b>ID de fase</b><p>Introduzca un identificador asignado por el cliente para la fase, único en todas las rutas. Debe ser alfanumérico, con guiones bajos o guiones permitidos y no más de 64 caracteres.</p></li>
      <li><b>Nombre de la fase</b><p>Introduzca o asigne un nombre para la etapa.</p></li>
      <li><b>Identificadores de fase principal</b><p>Para cada etapa principal que desee agregar a la etapa, haga clic en <b>Agregar elemento</b> e introduzca el identificador principal.</p></li>
      <li><b>Participantes</b><p>Para cada participante que desee agregar al escenario, haga clic en <b>Agregar elemento</b> e introduzca los detalles del participante.
      <ul>
      <li><b>ID de participante</b><p>Introduzca o asigne el ID del participante.</p></li>
      <li><b>Tipo de participante</b><p>Seleccione si el participante es un usuario o un equipo.</p></li>
      <li><b>Función de participante</b><p>Seleccione si el participante es aprobador o revisor.</p></li>
      </ul>
      </p></li>
      <li><b>Fecha límite</b><p>Si la fecha límite es una fecha específica, introduzca o asigne la fecha.</p></li>
      <li><b>Días laborables hasta la fecha límite</b><p>Si la fecha límite es posterior a un número específico de días hábiles, introduzca o asigne el número de días.</p></li>
      <li><b>Hora límite: horas</b><p>Introduzca o asigne la hora del día para la fecha límite (0-23). Emparejar con tiempo de espera: minutos.</p></li>
      <li><b>Tiempo de vencimiento: minutos</b><p>Introduzca o asigne el minuto de la hora para la fecha límite (0-59). Emparejar con tiempo de espera: horas.</p></li>
      <li><b>Mensaje personalizado</b><p>Introduzca o asigne un mensaje personalizado para el escenario.</p></li>
      </ul>
      </td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Recursos</p></td>
      <td>(Opcional) Para cada versión del documento que desee que contenga el grupo, haga clic en <b>Agregar elemento</b> e introduzca el identificador de la versión del documento (DOCV). Si omite este campo, los recursos actuales no se cambiarán.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Clave de idempotencia</p></td>
      <td>(Opcional) Introduzca o asigne una clave proporcionada por el cliente (máximo 128 caracteres) que haga segura una solicitud reintentada. Si vuelve a enviar la misma clave, el módulo no aplica la actualización por segunda vez.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Límite</p></td>
      <td>Introduzca o asigne el número máximo de resultados con los que desea que trabaje el módulo durante cada ciclo de ejecución de escenario.</td> 
      </tr>
  </tbody>
</table>

### Búsquedas

* [Obtener una plantilla](#get-a-template)
* [Obtener detalles de aprobación](#get-approval-details)
* [Obtener aprobaciones en una aprobación agrupada](#get-approvals-in-a-grouped-approval)
* [Obtener detalles de aprobación agrupados](#get-grouped-approval-details)
* [Obtener varias aprobaciones](#get-multiple-approvals)
* [Obtener aprobaciones sugeridas](#get-suggested-approvals)
* [Obtener participantes sugeridos](#get-suggested-participants)
* [Enumerar bots](#list-bots)
* [Enumeración de aprobaciones agrupadas por elemento principal](#list-grouped-approvals-by-parent)
* [Enumerar plantillas](#list-templates)
* [Buscar reseñas de marcas AI](#search-ai-brand-reviews)
* [Buscar aprobaciones agrupadas](#search-grouped-approvals)


#### Obtener una plantilla

Este módulo devuelve la plantilla de aprobación especificada.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificador de plantilla</p></td>
      <td>Introduzca o asigne el ID del documento para el que desea obtener participantes de aprobación sugeridos.</td> 
      </tr>
       <tr>
         <td role="rowheader">
           Número máximo de plantillas devueltas
         </td>
         <td>
              Introduzca o asigne el número máximo de plantillas que desea que devuelva el módulo durante cada ciclo de ejecución de escenario. 
         </td>
       </tr>
  </tbody>
</table>

#### Obtener detalles de aprobación

Este módulo de búsqueda recupera los detalles de aprobación de un recurso.



<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>Documento</p>
      </td>
      <td>Introduzca o asigne el ID del recurso para el que desea recuperar los detalles de aprobación.</td> 
      </tr>
  </tbody>
</table>

#### Obtener aprobaciones en una aprobación agrupada

Este módulo de búsqueda devuelve las aprobaciones de recursos individuales que conforman una aprobación agrupada.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>GUID de grupo</p></td>
      <td>Introduzca o asigne el GUID de la aprobación agrupada para la que desea obtener aprobaciones.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Datos de versión del documento</p></td>
      <td>Seleccione si desea adjuntar el registro documentVersion de Redrock a cada aprobación de versión de documento (DOCV). </td>
      </tr>
     <tr>
      <td role="rowheader"><p>Límite</p></td>
      <td>Introduzca o asigne el número máximo de resultados con los que desea que trabaje el módulo durante cada ciclo de ejecución de escenario.</td> 
      </tr>
  </tbody>
</table>

#### Obtener detalles de aprobación agrupados

Este módulo de búsqueda devuelve una aprobación agrupada por su GUID.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>GUID de grupo</p></td>
      <td>Introduzca o asigne el GUID de la aprobación agrupada para la que desea obtener detalles.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Límite</p></td>
      <td>Introduzca o asigne el número máximo de resultados con los que desea que trabaje el módulo durante cada ciclo de ejecución de escenario.</td> 
      </tr>
  </tbody>
</table>

#### Obtener varias aprobaciones

Este módulo recupera detalles de aprobaciones para una lista de documentos de un tipo específico.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificadores de documento</p></td>
      <td>Para cada documento para el que desee recuperar los detalles de aprobación, haga clic en <b>Agregar elemento</b> e introduzca el ID del documento.</td> 
      </tr>
       <tr>
         <td role="rowheader">
           Número máximo de resultados devueltos
         </td>
         <td>
              Introduzca o asigne el número máximo de resultados que desea que devuelva el módulo durante cada ciclo de ejecución de escenario. 
         </td>
       </tr>
  </tbody>
</table>

#### Obtener aprobaciones sugeridas

Este módulo devuelve cargas útiles de aprobación sugeridas de versiones de documentos anteriores.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificador del documento</p></td>
      <td>Introduzca o asigne el ID del documento para el que desea obtener aprobaciones sugeridas.</td> 
      </tr>
       <tr>
         <td role="rowheader">
           Número máximo de aprobaciones devueltas
         </td>
         <td>
              Introduzca o asigne el número máximo de aprobaciones que desea que devuelva el módulo durante cada ciclo de ejecución de escenario. 
         </td>
       </tr>
  </tbody>
</table>

#### Obtener participantes sugeridos

Este módulo devuelve las sugerencias de los participantes desde la aprobación para la aprobación previa del documento.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificador del documento</p></td>
      <td>Introduzca o asigne el ID del documento para el que desea obtener participantes de aprobación sugeridos.</td> 
      </tr>
       <tr>
         <td role="rowheader">
           Número máximo de participantes devueltos
         </td>
         <td>
              Introduzca o asigne el número máximo de participantes que desea que devuelva el módulo durante cada ciclo de ejecución de escenario. 
         </td>
       </tr>
  </tbody>
</table>

#### Enumerar bots

Este módulo devuelve una lista paginada de cuentas de bots.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Página</p></td>
      <td>Introduzca o asigne la página de resultados que desea devolver.</td> 
      </tr>
       <tr>
         <td role="rowheader">
           Número máximo de resultados devueltos
         </td>
         <td>
              Introduzca o asigne el número máximo de resultados que desea que devuelva el módulo durante cada ciclo de ejecución de escenario. 
         </td>
       </tr>
  </tbody>
</table>

#### Enumeración de aprobaciones agrupadas por elemento principal

Este módulo de búsqueda devuelve las aprobaciones agrupadas asociadas a un objeto principal de Workfront.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Identificador principal</p></td>
      <td>Introduzca o asigne el ID del objeto principal de Workfront (por ejemplo, un proyecto o una tarea) para el que desea obtener aprobaciones agrupadas.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Código de objeto</p></td>
      <td>(Opcional) Escriba o asigne el código de tipo de objeto Workfront para el objeto principal (por ejemplo, <code>PROJ</code> o <code>TASK</code>).</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Límite</p></td>
      <td>Introduzca o asigne el número máximo de resultados con los que desea que trabaje el módulo durante cada ciclo de ejecución de escenario.</td> 
      </tr>
  </tbody>
</table>

#### Enumerar plantillas

Este módulo devuelve una lista de todas las plantillas de aprobación disponibles para el usuario actual. El usuario actual es el usuario cuyas credenciales se utilizan en la conexión utilizada en este módulo.



<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
   </tbody>
</table>

#### Buscar reseñas de marcas AI

Este módulo devuelve los resultados de la revisión de marca de IA que se produjeron para una versión del documento como parte de una aprobación.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ID de usuario de bots</p></td>
      <td>Introduzca o asigne el ID de usuario del bot que desea buscar y que revisa.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Identificador de documento principal</p></td>
      <td>Introduzca o asigne el ID del documento principal que desea buscar en las revisiones.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>ID de versión de documento</p></td>
      <td>Introduzca o asigne el ID del recurso para el que desea enviar un recordatorio.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>ID de fase</p></td>
      <td>Introduzca o asigne un ID de fase para limitar los resultados a una fase específica de la aprobación.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Página</p></td>
      <td>Introduzca o asigne un número de página para limitar los resultados a esa página.</td> 
      </tr>
       <tr>
         <td role="rowheader">
           Número máximo de críticas devueltas
         </td>
         <td>
              Introduzca o asigne el número máximo de revisiones que desea que devuelva el módulo durante cada ciclo de ejecución de escenario. 
         </td>
       </tr>
  </tbody>
</table>

#### Buscar aprobaciones agrupadas

Este módulo de búsqueda busca aprobaciones agrupadas utilizando una vista con nombre.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Ver</p></td>
      <td>(Opcional) Seleccione o asigne la vista con nombre que determina la forma de la respuesta. Actualmente, solo se admite Esperando aprobaciones.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Límite</p></td>
      <td>(Opcional) Introduzca o asigne el tamaño de página para la primera página de resultados. El máximo es 100 y el valor predeterminado es 20.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Cursor</p></td>
      <td>(Opcional) Introduzca o asigne el cursor opaco de una respuesta anterior, para recuperar la página siguiente de resultados. Si proporciona un cursor, el módulo ignorará el campo Limit.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Identificadores de equipo</p></td>
      <td>(Opcional) Para cada equipo por el que también desea hacer coincidir las aprobaciones agrupadas (donde el equipo es un participante), haga clic en <b>Agregar elemento</b> e introduzca el ID de equipo.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Límite</p></td>
      <td>Introduzca o asigne el número máximo de resultados con los que desea que trabaje el módulo durante cada ciclo de ejecución de escenario.</td> 
      </tr>
  </tbody>
</table>

<!-- BECKY CHECK ME: the screenshot shows two separate fields both labeled "Limit" - an optional pagination page-size field (max 100, default 20, ignored if Cursor is set) and a required general execution-cycle limit, matching the Limit field used in every other module in this article. Confirm this isn't a UI labeling issue before publishing, and that both rows are needed/correctly distinguished. -->

### Otros

* [Realizar una llamada API personalizada](#make-a-custom-api-call)
* [Campos de etapas](#stages-fields)


#### Realizar una llamada API personalizada

Este módulo realiza una llamada de API personalizada a la API de revisión unificada y aprobaciones de Adobe Workfront.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión a Adobe Workfront Unified Review and Approvals, consulte <a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Conectarse a Adobe Workfront Unified Review and Approvals</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>Ruta relativa</p>
      </td>
      <td>
        <p>Introduzca una ruta relativa a <code>https://workfront.adobe.io</code>. Por ejemplo: <code>/unified-approvals/public/api/v1/approvals/&lt;ASSET_TYPE&gt;/&lt;ASSET_ID&gt;</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>Método</p>
      </td>
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, consulte <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de petición HTTP</a>.</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">Encabezados</td>
      <td>
        <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p>
        <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion añade encabezados de autorización automáticamente.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Query String]  </td>
      <td>
        <p>Para cada par clave/valor que desee agregar a la cadena de consulta, haga clic en <b>Agregar elemento</b> e introduzca la clave y el valor.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Body]</td>
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>



#### Campos de etapas

Los campos siguientes están disponibles al configurar las fases. Es posible que no todos los campos estén disponibles para todos los módulos.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Nombre de la fase</td>
      <td>Introduzca o asigne un nombre para la etapa.</td>
    </tr>
     <tr>
      <td role="rowheader"><p>Fecha límite</p></td>
      <td>Si la fecha límite es una fecha específica, introduzca o asigne la fecha.</td> 
      </tr>
  </tbody>
     <tr>
      <td role="rowheader"><p>Plazo días laborables</p></td>
      <td>Si la fecha límite es posterior a un número específico de días hábiles, introduzca o asigne el número de días.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Plazo</p></td>
      <td>Si la fecha límite es una hora específica, introduzca o asigne la hora.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Participantes</p></td>
      <td>Para cada participante que desee agregar al escenario, haga clic en <b>Agregar elemento</b> e introduzca los detalles del participante.      
      <ul>
      <li><b>ID de participante</b><p>Introduzca o asigne el ID del participante.</p></li>
      <li><b>Tipo de participante</b><p>Seleccione si el participante es un usuario o un equipo.</p></li>
      <li><b>Función de participante</b><p>Seleccione si el participante es aprobador o revisor.</p></li>
      </ul> 
      </td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Bloqueo automático activado</p></td>
      <td>Especifique si desea bloquear automáticamente el escenario.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Reglas de decisión</p></td>
      <td>Seleccione si desea requerir solo una decisión para la fase.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>ID de padre/ID de etapa de padre</p></td>
      <td>Para cada etapa principal que desee agregar a la etapa, haga clic en <b>Agregar elemento</b> e introduzca el identificador principal.</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Activadores</p></td>
      <td>Para configurar un déclencheur para esta fase de aprobación, haga clic en <b>Agregar elemento</b> e introduzca los detalles del déclencheur.      <ul>
      <li><b>Tipo</b><p>Seleccionar <b>activación</b></p></li>
      <li><b>Cuando</b><p>Seleccione si desea almacenar en déclencheur la fase cuando se cree la aprobación o cuando se complete otra fase.</p></li>
      <li><b>Fases</b><p>Para cada fase que desee agregar al déclencheur, haga clic en <b>Agregar elemento</b> e introduzca o asigne el ID de la fase.</p></li>
      <li><b>Decisiones</b><p>Para cada decisión que desee agregar al déclencheur, haga clic en <b>Agregar elemento</b> y escriba o asigne la decisión.</p></li>
      </ul> 
      </td> 
      </tr>
     <tr>
      <td role="rowheader"><p>Mensaje personalizado</p></td>
      <td>Introduzca o asigne un mensaje personalizado para el escenario.</td> 
      </tr>
</table>
