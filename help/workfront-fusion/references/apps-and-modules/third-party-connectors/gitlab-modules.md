---
title: Módulos de GitLab
description: Adobe Workfront Fusion requiere una licencia Adobe Workfront Fusion y de Adobe Workfront.
author: Becky
feature: Workfront Fusion
exl-id: fabbadce-5669-4363-834e-6d7428520f62
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '3554'
ht-degree: 90%

---

# Módulos de [!UICONTROL GitLab]

Adobe Workfront Fusion requiere una licencia Adobe Workfront Fusion y de Adobe Workfront.

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!UICONTROL GitLab], así como conectarlo a varias aplicaciones y servicios de terceros.

>[!NOTE]
>
>Este artículo espera cierta familiaridad con la documentación de la API, y de la funcionalidad [!DNL GitLab] en general.

Para obtener instrucciones sobre cómo crear un escenario, vea los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

## Requisitos de acceso

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] plan*</td>
  <td> <p>[!UICONTROL Pro] o superior</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licencia*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licencia**</td> 
   <td>
   <p>Requisito de licencia actual: no se requiere ninguna licencia de [!DNL Workfront Fusion].</p>
   <p>O</p>
   <p>Requisito de licencia heredado: [!DNL Workfront Fusion] para automatización e integración de trabajo </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Requisito de producto actual: si tiene el plan [!UICONTROL Select] o [!UICONTROL Prime] [!DNL Adobe Workfront], su organización debe adquirir [!DNL Adobe Workfront Fusion] así como [!DNL Adobe Workfront] para utilizar la funcionalidad descrita en este artículo. [!DNL Workfront Fusion] está incluido en el plan [!UICONTROL Ultimate] [!DNL Workfront].</p>
   <p>O</p>
   <p>Requisito de productos heredados: su organización debe comprar [!DNL Adobe Workfront Fusion] y [!DNL Adobe Workfront] para utilizar la funcionalidad descrita en este artículo.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Para saber qué plan, tipo de licencia o acceso tiene, póngase en contacto con el administrador de [!DNL Workfront].

Para obtener información sobre las licencias de [!DNL Adobe Workfront Fusion], consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## Conectar [!DNL GitLab] a [!DNL Workfront Fusion] {#connect-gitlab-to-workfront-fusion}

1. En cualquier módulo [!DNL Workfront Fusion] [!DNL Gitlab], haga clic en **[!UICONTROL Add]** junto al campo de conexión.
1. Configure los campos siguientes:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Connection name]</td> 
      <td> <p>Introduzca un nombre para la conexión. </p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL [!DNL GitLab] URL]</td> 
      <td>Introduzca la dirección URL de su instancia de [!DNL GitLab].</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Access Token]</td> 
      <td><p>Escriba su [!UICONTROL Private Token] o [!UICONTROL Personal Access Token].</p><p>Para obtener información sobre la localización o creación de un token de acceso personal en [!DNL GitLab], consulte “Crear un token de acceso personal” en <a href="https://docs.gitlab.com/ee/user/profile/personal_access_tokens.html">Tókenes de acceso personal</a>, en la documentación de [!DNL GitLab].</p></td> 
     </tr> 
    </tbody> 
   </table>


1. Haga clic en **[!UICONTROL Continue]**.
1. Haga clic en **[!UICONTROL Authorize]** para crear la conexión y volver al módulo.

## Módulos de [!DNL GitLab] y sus campos

Al configurar módulos de [!DNL GitLab], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL GitLab] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Activadores

+++**[!UICONTROL Watch build status]**

Este módulo de activador instantáneo inicia un escenario cuando cambia el estado de una compilación.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Seleccione el webhook que desee utilizar para este activador o añada uno nuevo. </p><p>Para añadir un nuevo webhook, <ol><li>Haga clic en <b>[!UICONTROL Add]</b> junto al campo [!UICONTROL webhook].</li><li>Introduzca lo siguiente: <ul><li>El nombre del webhook</li><li>La conexión que desea utilizar para este webhook</li><li>El proyecto en el que desea que el webhook observe los cambios de estado de compilación</li></ul></li><li>Haga clic en <b>[!UICONTROL Save]</b> para guardar el webhook y volver al módulo. </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch commit/MR/issue/snippet comments]**

Este módulo de activador instantáneo inicia un escenario cuando se realiza un comentario en una confirmación, solicitud de combinación, problema o fragmento de código.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Seleccione el webhook que desee utilizar para este activador o añada uno nuevo. </p><p>Para añadir un nuevo webhook, <ol><li>Haga clic en <b>[!UICONTROL Add]</b> junto al campo [!UICONTROL webhook].</li><li>Introduzca lo siguiente: <ul><li>El nombre del webhook</li><li>La conexión que desea utilizar para este webhook</li><li>El proyecto en el que desea que el webhook busque comentarios</li></ul></li><li>Haga clic en <b>[!UICONTROL Save]</b> para guardar el webhook y volver al módulo. </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch commits (pushes)]**

Este módulo de activador instantáneo inicia un escenario cuando se inserta una confirmación en un repositorio. Este módulo no inicia un escenario cuando se inserta una etiqueta.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Seleccione el webhook que desee utilizar para este activador o añada uno nuevo. </p><p>Para añadir un nuevo webhook, <ol><li>Haga clic en <b>[!UICONTROL Add]</b> junto al campo [!UICONTROL webhook].</li><li>Introduzca lo siguiente: <ul><li>El nombre del webhook</li><li>La conexión que desea utilizar para este webhook</li><li>El proyecto que desea que el webhook vea para confirmar</li></ul></li><li>Haga clic en <b>[!UICONTROL Save]</b> para guardar el webhook y volver al módulo. </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch issue comment]**

Este módulo de activador instantáneo inicia un escenario cuando se realiza un comentario sobre un problema.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Seleccione el webhook que desee utilizar para este activador o añada uno nuevo. </p><p>Para añadir un nuevo webhook, <ol><li>Haga clic en <b>[!UICONTROL Add]</b> junto al campo [!UICONTROL webhook].</li><li>Introduzca lo siguiente: <ul><li>El nombre del webhook</li><li>La conexión que desea utilizar para este webhook</li><li>El proyecto que desea que el webhook vea para comentarios sobre problemas</li></ul></li><li>Haga clic en <b>[!UICONTROL Save]</b> para guardar el webhook y volver al módulo. </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch issues]**

Este módulo de [!UICONTROL instant trigger] inicia un escenario cuando se crea un problema o cuando se actualiza, cierra o vuelve a abrirse uno existente.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Seleccione el webhook que desee utilizar para este activador o añada uno nuevo. </p><p>Para añadir un nuevo webhook, <ol><li>Haga clic en <b>[!UICONTROL Add]</b> junto al campo [!UICONTROL webhook].</li><li>Introduzca lo siguiente: <ul><li>El nombre del webhook</li><li>La conexión que desea utilizar para este webhook</li><li>El proyecto en el que desea que el webhook busque problemas</li></ul></li><li>Haga clic en <b>[!UICONTROL Save]</b> para guardar el webhook y volver al módulo. </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch merge requests]**

Este módulo de activador instantáneo inicia un escenario cuando se produce una de las siguientes situaciones:

* Se crea una nueva solicitud de combinación
* Se actualiza, fusiona o cierra una solicitud de combinación existente
* Se añade una confirmación en la rama de fuente


<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Seleccione el webhook que desee utilizar para este activador o añada uno nuevo. </p><p>Para añadir un nuevo webhook, <ol><li>Haga clic en <b>[!UICONTROL Add]</b> junto al campo [!UICONTROL webhook].</li><li>Introduzca lo siguiente: <ul><li>El nombre del webhook</li><li>La conexión que desea utilizar para este webhook</li><li>El proyecto en el que desea que el webhook busque solicitudes de combinación</li></ul></li><li>Haga clic en <b>[!UICONTROL Save]</b> para guardar el webhook y volver al módulo. </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch merge request comments]**

Este módulo de activador instantáneo inicia un escenario cuando se realiza un comentario en una solicitud de combinación.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Seleccione el webhook que desee utilizar para este activador o añada uno nuevo. </p><p>Para añadir un nuevo webhook, <ol><li>Haga clic en <b>[!UICONTROL Add]</b> junto al campo [!UICONTROL webhook].</li><li>Introduzca lo siguiente: <ul><li>El nombre del webhook</li><li>La conexión que desea utilizar para este webhook</li><li>El proyecto en el que desea que el webhook busque comentarios de solicitudes de combinación</li></ul></li><li>Haga clic en <b>[!UICONTROL Save]</b> para guardar el webhook y volver al módulo. </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch pipeline status]**

Este módulo de activador instantáneo inicia un escenario cuando cambia el estado de una canalización.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Seleccione el webhook que desee utilizar para este activador o añada uno nuevo. </p><p>Para añadir un nuevo webhook, <ol><li>Haga clic en <b>[!UICONTROL Add]</b> junto al campo [!UICONTROL webhook].</li><li>Introduzca lo siguiente: <ul><li>El nombre del webhook</li><li>La conexión que desea utilizar para este webhook</li><li>El proyecto en el que desea que el webhook observe cambios en el estado de la canalización</li></ul></li><li>Haga clic en <b>[!UICONTROL Save]</b> para guardar el webhook y volver al módulo. </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch projects]**

Este módulo de activador programado inicia un escenario cuando se añade un nuevo proyecto del que es miembro el usuario autenticado.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo conectar su [!DNL GitLab]cuenta de[!DNL Workfront] a Fusion, consulte <a href="#connect-gitlab-to-workfront-fusion-connect-gitlab-to-workfront-fusion" class="MCXref xref">Conectar [!DNL GitLab] a [!DNL Workfront] Fusion</a> en este artículo.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Resultados máximos</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo vea durante cada ciclo de ejecución de escenario.</p> </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch repository branches]**

Este módulo de activador programado inicia un escenario cuando se añade una nueva rama a un repositorio.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo conectar su [!DNL GitLab]cuenta de[!DNL Workfront] a Fusion, consulte <a href="#connect-gitlab-to-workfront-fusion-connect-gitlab-to-workfront-fusion" class="MCXref xref">Conectar [!DNL GitLab] a [!DNL Workfront] Fusion</a> en este artículo.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Resultados máximos</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo vea durante cada ciclo de ejecución de escenario.</p> </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch repository tags]**

Este módulo de activador instantáneo inicia un escenario cuando se crea o elimina una etiqueta en un repositorio.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Seleccione el webhook que desee utilizar para este activador o añada uno nuevo. </p><p>Para añadir un nuevo webhook, <ol><li>Haga clic en <b>[!UICONTROL Add]</b> junto al campo [!UICONTROL webhook].</li><li>Introduzca lo siguiente: <ul><li>El nombre del webhook</li><li>La conexión que desea utilizar para este webhook</li><li>El proyecto que desea que el webhook inspeccione en busca de etiquetas</li></ul></li><li>Haga clic en <b>[!UICONTROL Save]</b> para guardar el webhook y volver al módulo. </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch snippet comments]**

Este módulo de activador instantáneo inicia un escenario cuando se realiza un nuevo comentario en un fragmento.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Seleccione el webhook que desee utilizar para este activador o añada uno nuevo. </p><p>Para añadir un nuevo webhook, <ol><li>Haga clic en <b>[!UICONTROL Add]</b> junto al campo [!UICONTROL webhook].</li><li>Introduzca lo siguiente: <ul><li>El nombre del webhook</li><li>La conexión que desea utilizar para este webhook</li><li>El proyecto en el que desea que el webhook busque comentarios</li></ul></li><li>Haga clic en <b>[!UICONTROL Save]</b> para guardar el webhook y volver al módulo. </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch todos]**

Este módulo de activador programado inicia un escenario cuando se añade una nueva tarea pendiente. Cuando no se aplica ningún filtro, el activador se ejecuta al añadir una nueva tarea pendiente.

Para obtener información sobre los campos, consulte [Obtener una lista de tareas pendientes](https://docs.gitlab.com/ee/api/todos.html#get-a-list-of-todos) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Watch wiki page]**

Este módulo de activador instantáneo inicia un escenario cuando se crea o edita una página wiki.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Seleccione el webhook que desee utilizar para este activador o añada uno nuevo. </p><p>Para añadir un nuevo webhook, <ol><li>Haga clic en <b>[!UICONTROL Add]</b> junto al campo [!UICONTROL webhook].</li><li>Introduzca lo siguiente: <ul><li>El nombre del webhook</li><li>La conexión que desea utilizar para este webhook</li><li>El proyecto en el que desea que el webhook observe las páginas de la wiki</li></ul></li><li>Haga clic en <b>[!UICONTROL Save]</b> para guardar el webhook y volver al módulo. </td> 
   </tr> 
   </tbody> 
</table>

+++

### Acciones

+++**[!UICONTROL Accept merge request]**

Este módulo de acción combina los cambios enviados con la solicitud de combinación en cuestión.

Para obtener información sobre los campos, consulte [Aceptar una solicitud de combinación](https://docs.gitlab.com/ee/api/merge_requests.html#accept-mr) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Cancel a build]**

Este módulo de acción cancela una sola versión de un proyecto.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL GitLab] a [!DNL Workfront] Fusion, consulte <a href="#connect-gitlab-to-workfront-fusion-connect-gitlab-to-workfront-fusion" class="MCXref xref">Conectar [!DNL GitLab] a [!DNL Workfront] Fusion</a> en este artículo.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p>Seleccione o asigne el proyecto que contiene la compilación que desea cancelar.</p> </td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Build ID]</td> 
   <td>Seleccione o asigne la compilación que desea cancelar.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Merge commit message]</td> 
   <td> Introduzca o asigne un mensaje de comprobación para la combinación.
    </td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Should remove source branch]</td> 
   <td>Seleccione si desea quitar la rama de fuente cuando se complete la combinación.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Merge when build succeeds]</td> 
   <td>Seleccione si desea combinar la solicitud de combinación en cuanto se complete la compilación.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL SHA]</td> 
   <td>Si está presente, este SHA debe coincidir con el HEAD de la rama de fuente. Si no coincide, la combinación fallará.</td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Cancel a pipeline's builds]**

Este módulo de acción cancela las compilaciones de una sola canalización.

Para obtener información sobre los campos, consulte [Cancelar los trabajos de una canalización](https://docs.gitlab.com/ee/api/pipelines.html#cancel-a-pipelines-jobs) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Cancel merge when pipeline succeeds]**

Si una solicitud de combinación está configurada para combinarse cuando una canalización se realiza correctamente, este módulo de acción cancela esa acción.

Para obtener información sobre los campos, consulte [Cancelar la combinación cuando la canalización se realice correctamente](https://docs.gitlab.com/ee/api/merge_requests.html) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Cherry pick a commit]**

Este módulo de acción elige un compromiso para una rama determinada.

Para obtener información sobre los campos, consulte [Elegir un compromiso](https://docs.gitlab.com/ee/api/commits.html#cherry-pick-a-commit) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Create a new label]**

Este módulo de acción crea una nueva etiqueta para el repositorio en cuestión.

Para obtener información sobre los campos, consulte [Crear una nueva etiqueta](https://docs.gitlab.com/ee/api/labels.html#create-a-new-label) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Create a new pipeline]**

Este módulo de acción crea una nueva canalización para el proyecto en cuestión.

Para obtener información sobre los campos, consulte [Crear una nueva canalización](https://docs.gitlab.com/ee/api/pipelines.html#create-a-new-pipeline) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Create a new release]**

Este módulo de acción añade notas de la versión a la etiqueta de Git existente.

Para obtener información sobre los campos, consulte [Crear una versión](https://docs.gitlab.com/ee/api/releases/#create-a-release) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Create a new tag]**

Este módulo de acción crea una nueva etiqueta en el repositorio que apunta a la referencia proporcionada.

Para obtener información sobre los campos, consulte [Crear una etiqueta nueva](https://docs.gitlab.com/ee/api/tags.html#create-a-new-tag) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Create a todo]**

Este módulo de acción crea una tarea pendiente para el usuario actual en el problema seleccionado. El usuario actual es el usuario identificado por las credenciales de la conexión utilizada para este módulo.

Para obtener información sobre los campos, consulte [Crear una tarea pendiente](https://docs.gitlab.com/ee/api/issues.html#create-a-todo) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Create a todo on a merge request]**

Este módulo de acción crea una tarea pendiente para el usuario actual en la solicitud de combinación seleccionada. El usuario actual es el usuario identificado por las credenciales de la conexión utilizada para este módulo.

Para obtener información sobre los campos, consulte [Crear una tarea pendiente](https://docs.gitlab.com/ee/api/merge_requests.html#create-a-todo) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Create merge request]**

Este módulo de acción crea una nueva solicitud de combinación en un proyecto.

Para obtener información sobre los campos, consulte [Crear solicitud de combinación](https://docs.gitlab.com/ee/api/merge_requests.html#create-mr) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Create new file in repository]**

Este módulo de acción crea un nuevo archivo en el repositorio seleccionado.

Para obtener información sobre los campos, consulte [Crear nuevo archivo en el repositorio](https://docs.gitlab.com/ee/api/repository_files.html#create-new-file-in-repository) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Create new issue note]**

Este módulo de acción crea una nota del problema para un solo problema de proyecto.

Para obtener información sobre los campos, consulte [Crear nueva nota de problema](https://docs.gitlab.com/ee/api/notes.html#create-new-issue-note) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Create new merge request note]**

Este módulo de acción crea una nota para una sola solicitud de combinación.

Para obtener información sobre los campos, consulte [Crear nueva nota de solicitud de combinación](https://docs.gitlab.com/ee/api/notes.html#create-new-merge-request-note) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Create a new milestone]**

Este módulo de acción crea un nuevo hito para un proyecto.

Para obtener información sobre los campos, consulte [Crear nuevo hito](https://docs.gitlab.com/ee/api/milestones.html#create-new-milestone) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Create new snippet note]**

Este módulo de acción crea una nota nueva para un solo fragmento. Las notas de fragmento son comentarios que los usuarios pueden publicar en un fragmento.

Para obtener información sobre los campos, consulte [Crear nueva nota de fragmento](https://docs.gitlab.com/ee/api/notes.html#create-new-snippet-note) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Create repository branch]**

Este módulo de acción crea una sola rama del repositorio.

Para obtener información sobre los campos, consulte [Crear rama de repositorio](https://docs.gitlab.com/ee/api/branches.html#create-repository-branch) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Create build variable]**

Este módulo de acción crea una nueva variable de compilación.

Para obtener información sobre los campos, consulte [Crear variable](https://docs.gitlab.com/ee/api/project_level_variables.html#create-variable) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Delete a merge request]**

Este módulo de acción es solo para administradores y propietarios de proyectos. Elimina la solicitud de combinación en cuestión

Para obtener información sobre los campos, consulte [Eliminar una solicitud de combinación](https://docs.gitlab.com/ee/api/merge_requests.html#delete-a-merge-request) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Delete existing file in repository]**

Este módulo de acción elimina un archivo existente del repositorio.

Para obtener información sobre los campos, consulte [Eliminar archivo existente en el repositorio](https://docs.gitlab.com/ee/api/repository_files.html#delete-existing-file-in-repository) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Delete repository branch]**

Este módulo de acción elimina una rama del repositorio.

Para obtener información sobre los campos, consulte [Eliminar la rama del repositorio](https://docs.gitlab.com/ee/api/branches.html#delete-repository-branch) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Edit issue]**

Este módulo de acción actualiza un problema existente del proyecto. Esta llamada también se utiliza para marcar un problema como cerrado.

Para obtener información sobre los campos, consulte [Editar problema](https://docs.gitlab.com/ee/api/issues.html#edit-issue) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Edit Milestone]**
Este módulo de acción actualiza un hito de proyecto existente.

Para obtener información sobre los campos, consulte [Editar hito](https://docs.gitlab.com/ee/api/milestones.html#edit-milestone) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Erase a build]**

Este módulo de acción borra una versión de un proyecto (elimina los artefactos de trabajo y el registro de trabajos).

Para obtener información sobre los campos, consulte [Borrar un trabajo](https://docs.gitlab.com/ee/api/jobs.html#erase-a-job) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Get a list of todos]**

Este módulo de búsqueda recupera una lista de elementos pendientes.

Para obtener información sobre los campos, consulte [Obtener una lista de elementos pendientes](https://docs.gitlab.com/ee/api/todos.html#get-a-list-of-todos) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Get a single build]**

Este módulo de acción recupera un solo trabajo de un proyecto.

Para obtener información sobre los campos, consulte [Obtener un solo trabajo](https://docs.gitlab.com/ee/api/jobs.html#get-a-single-job) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Get a single repository tag]**

Este módulo de acción recupera una etiqueta de repositorio específica determinada por su nombre.

Para obtener información sobre los campos, consulte [Obtener una sola etiqueta de repositorio](https://docs.gitlab.com/ee/api/tags.html#get-a-single-repository-tag) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Get a specific deployment]**

Este módulo de acción recupera una implementación específica.

Para obtener información sobre los campos, consulte [Obtener una implementación específica](https://docs.gitlab.com/ee/api/deployments.html#get-a-specific-deployment) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Get all issues assigned to a single milestone]**

Este módulo de búsqueda recupera todos los problemas asignados a un solo hito de proyecto.

Para obtener información sobre los campos, consulte [Obtener todos los problemas asignados a un solo hito](https://docs.gitlab.com/ee/api/milestones.html#get-all-issues-assigned-to-a-single-milestone) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Get file from repository]**

Este módulo de acción recupera información sobre un archivo del repositorio, como el nombre, tamaño o contenido.

Para obtener información sobre los campos, consulte [Obtener archivo del repositorio](https://docs.gitlab.com/ee/api/repository_files.html#get-file-from-repository) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Get project users]**

Este módulo de búsqueda recupera los usuarios del proyecto.

Para obtener información sobre los campos, consulte [Obtener usuarios del proyecto](https://docs.gitlab.com/ee/api/projects.html#get-project-users) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Get a single issue]**

Este módulo de acción recupera los detalles de un problema.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para crear una nueva conexión, consulte <a href="#connect-gitlab-to-workfront-fusion" class="MCXref xref">[!UICONTROL Connect [!DNL GitLab] a Workfront Fusion]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project]</td> 
   <td> <p>Seleccione el proyecto que contiene el problema del que desea obtener detalles.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Issue ID]</td> 
   <td> <p>Escriba o asigne el nombre del problema del que desea obtener detalles.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**[!UICONTROL Get single issue note]**

Este módulo de acción recupera una sola nota para un problema específico del proyecto.

Para obtener información sobre los campos, consulte [Obtener una sola nota de un problema](https://docs.gitlab.com/ee/api/notes.html#get-single-issue-note) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Get single merge request]**

Este módulo de acción recupera información sobre una única solicitud de combinación.

Para obtener información sobre los campos, consulte [Obtener una única solicitud de combinación](https://docs.gitlab.com/ee/api/merge_requests.html#get-single-mr) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Get single merge request changes]**

Este módulo de búsqueda recupera información sobre la solicitud de combinación, incluidos sus archivos y cambios.

Para obtener información sobre los campos, consulte [Obtener cambios de una solicitud de combinación](https://docs.gitlab.com/ee/api/merge_requests.html#get-single-mr-changes) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Get single merge request commits]**

Este módulo de acción recupera una lista de compromisos de solicitudes de combinación.

Para obtener información sobre los campos, consulte [Obtener compromisos de solicitudes de combinación única](https://docs.gitlab.com/ee/api/merge_requests.html#get-single-mr-commits) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Get single merge request note]**

Este módulo de acción devuelve una sola nota para una solicitud de combinación determinada.

Para obtener información sobre los campos, consulte [Obtener una nota de solicitud de combinación](https://docs.gitlab.com/ee/api/notes.html#get-single-merge-request-note) en la documentación de [!DNL GitLab],

+++

+++**[!UICONTROL Get a Milestone]**

Este módulo de acción recupera los detalles de un hito.

Para obtener información sobre los campos, consulte [Obtener un hito](https://docs.gitlab.com/ee/api/milestones.html#get-single-milestone) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Get single project]**

Este módulo de acción recupera los detalles de un proyecto.

Para obtener información sobre los campos, consulte [Obtener un proyecto](https://docs.gitlab.com/ee/api/projects.html#get-single-project) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Get single repository branch]**

Este módulo de acción recupera los detalles de una rama del repositorio.

Para obtener información sobre los campos, consulte [Obtener una rama del repositorio](https://docs.gitlab.com/ee/api/branches.html#get-single-repository-branch) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Get snippet note]**

Este módulo recupera una nota para un fragmento determinado.

Para obtener información sobre los campos, consulte [Obtener nota de un fragmento](https://docs.gitlab.com/ee/api/notes.html#get-single-snippet-note) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Get the comments of a commit]**

Este módulo de búsqueda recupera los comentarios de un compromiso en un proyecto.

Para obtener información sobre los campos, consulte [Obtener los comentarios de un compromiso](https://docs.gitlab.com/ee/api/commits.html#get-the-comments-of-a-commit) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Get the diff of a commit]**

Este módulo de acción obtiene la diferencia de un compromiso en un proyecto.

Para obtener información sobre los campos, consulte [Obtener la diferencia de un compromiso](https://docs.gitlab.com/ee/api/commits.html#get-the-diff-of-a-commit) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Keep artifacts]**

Evita que se eliminen artefactos cuando se establece la caducidad.

Para obtener información sobre los campos, consulte [Conservar artefactos](https://docs.gitlab.com/ee/api/job_artifacts.html#keep-artifacts) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL List all merge request notes]**

Este módulo de búsqueda recupera una lista de todas las notas de una única solicitud de combinación.

Para obtener información sobre los campos, consulte [Enumerar todas las notas de solicitudes de combinación](https://docs.gitlab.com/ee/api/notes.html#list-all-merge-request-notes) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL List all snippet notes]**

Este módulo obtiene una lista de todas las notas de un solo fragmento. Las notas de fragmento son comentarios que los usuarios pueden publicar en un fragmento.

Para obtener información sobre los campos, consulte [??](https://docs.gitlab.com/ee/api/notes.html#list-all-snippet-notes) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL List commit builds]**

Este módulo de búsqueda devuelve una lista de compilaciones para un compromiso específico en un proyecto.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para crear una nueva conexión, consulte <a href="#connect-gitlab-to-workfront-fusion" class="MCXref xref">[!UICONTROL Connect [!DNL GitLab] a Workfront Fusion]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p>Seleccione el proyecto que contiene el compromiso cuyas compilaciones desea enumerar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scope]</td> 
   <td> Para limitar la búsqueda a fin de que se genere con un estado específico, seleccione el estado. Si se deja este campo en blanco, se devuelven todas las compilaciones del compromiso.  </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**[!UICONTROL List issues]**

Este módulo de búsqueda devuelve todos los problemas según la configuración de filtro especificada.

Para obtener información sobre los campos, consulte [Listar problemas](https://docs.gitlab.com/ee/api/issues.html#list-issues) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL List Issues That Close on Merge]**

Este módulo de búsqueda recupera todos los problemas que se cerrarían combinando la solicitud de combinación proporcionada.

Para obtener información sobre los campos, consulte [Listar problemas que se cerrarán al combinar](https://docs.gitlab.com/ee/api/merge_requests.html#list-issues-that-will-close-on-merge) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL List Labels]**

Este módulo de búsqueda recupera todas las etiquetas del proyecto.

Para obtener información sobre los campos, consulte [Listar etiquetas](https://docs.gitlab.com/ee/api/labels.html#list-labels) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL List merge requests]**

Este módulo de búsqueda recupera todas las solicitudes de combinación mediante la configuración del filtro.

Para obtener información sobre los campos, consulte [Listar solicitudes de combinación](https://docs.gitlab.com/ee/api/merge_requests.html#list-merge-requests) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL List Owned Projects]**

Este módulo de búsqueda recupera proyectos en los que el usuario autenticado está establecido como propietario.

Para obtener información sobre los campos, consulte [Listar proyectos de usuario](https://docs.gitlab.com/ee/api/projects.html#list-all-projects) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL List project builds]**

Este módulo de búsqueda recupera una lista de compilaciones de un proyecto.

Para obtener información sobre los campos, consulte [Listar trabajos de un proyecto](https://docs.gitlab.com/ee/api/jobs.html#list-project-jobs) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL List project deployments]**

Este módulo de búsqueda recupera una lista de implementaciones en un proyecto.

Para obtener información sobre los campos, consulte [Listar implementaciones de un proyecto](https://docs.gitlab.com/ee/api/deployments.html#list-project-deployments) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL List project issue notes]**

Este módulo de búsqueda recupera una lista de todas las notas de un solo problema.

Para obtener información sobre los campos, consulte [Listar notas de un problema del proyecto](https://docs.gitlab.com/ee/api/notes.html#list-project-issue-notes) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL List project issues]**

Este módulo de búsqueda devuelve todos los problemas de un proyecto especificado.

Para obtener información sobre los campos, consulte [Listar problemas de un proyecto](https://docs.gitlab.com/ee/api/issues.html#list-project-issues) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL List project milestones]**

Este módulo de búsqueda recupera todos los hitos del proyecto.

Para obtener información sobre los campos, consulte [Listar hitos del proyecto](https://docs.gitlab.com/ee/api/milestones.html#list-project-milestones) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL List project pipelines]**

Este módulo de búsqueda recupera todas las canalizaciones del proyecto.

Para obtener información sobre los campos, consulte [Listar canalizaciones del proyecto](https://docs.gitlab.com/ee/api/pipelines.html#list-project-pipelines) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL List project repository tags]**

Este módulo de búsqueda recupera una lista de etiquetas de repositorio de un proyecto, ordenadas por el nombre en orden alfabético inverso.

Para obtener información sobre los campos, consulte [Listar etiquetas de repositorio de un proyecto](https://docs.gitlab.com/ee/api/tags.html#list-project-repository-tags) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL List project variables]**

Este módulo de búsqueda recupera una lista de variables de un proyecto.

Para obtener información sobre los campos, consulte [Lista de variables de proyecto](https://docs.gitlab.com/ee/api/project_level_variables.html#list-project-variables) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL List projects]**

Este módulo de búsqueda recupera todos los proyectos de los que es miembro el usuario autenticado.

Para obtener información sobre los campos, consulte [Lista de todos los proyectos](https://docs.gitlab.com/ee/api/projects.html#list-all-projects) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL List repository branches]**

Este módulo busca las ramas de repositorio por el término de búsqueda.

Para obtener información sobre los campos, consulte [Lista de ramas de repositorio](https://docs.gitlab.com/ee/api/branches.html#list-repository-branches) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL List repository commits]**

Este módulo de búsqueda recupera una lista de compromisos de repositorio de un proyecto.

Para obtener información sobre los campos, consulte [Lista de compromisos de repositorio](https://docs.gitlab.com/ee/api/commits.html#list-repository-commits) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL List repository contributors]**

Este módulo de búsqueda recupera una lista de colaboradores del repositorio.

Para obtener información sobre los campos, consulte [Colaboradores](https://docs.gitlab.com/ee/api/repositories.html#contributors) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL List repository tree]**

Este módulo de búsqueda recupera una lista de archivos y directorios de repositorio en un proyecto.

Para obtener información sobre los campos, consulte [Enumerar árbol de repositorios](https://docs.gitlab.com/ee/api/repositories.html#list-repository-tree) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Mark a todo as done]**

Este módulo de acción marca un solo elemento pendiente especificado por su ID para el usuario actual como listo.

Para obtener información sobre los campos, consulte [Marcar un elemento pendiente como listo](https://docs.gitlab.com/ee/api/todos.html#mark-a-todo-as-done) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Modify existing issue note]**

Modifica una nota existente de un problema.

Para obtener información sobre los campos, consulte [Modificar una nota existente de un problema](https://docs.gitlab.com/ee/api/notes.html#modify-existing-issue-note) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Modify existing merge request note]**

Modifica la nota existente de una solicitud de combinación.

Para obtener información sobre los campos, consulte [Modificar nota existente de solicitud de combinación ](https://docs.gitlab.com/ee/api/notes.html#modify-existing-merge-request-note) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Modify existing snippet note]**

Este módulo de acción modifica una nota existente de un fragmento.

Para obtener información sobre los campos, consulte [Modificar nota de fragmento existente](https://docs.gitlab.com/ee/api/notes.html#modify-existing-snippet-note) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL New issue]**

Este módulo de acción crea un nuevo problema de proyecto.

Para obtener información sobre los campos, consulte [Nuevo problema](https://www.integromat.com/en/help/app/gitlab) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Play a build]**

Este módulo de acción activa una acción manual para iniciar un trabajo.

Para obtener información sobre los campos, consulte [Reproducir un trabajo](https://docs.gitlab.com/ee/api/jobs.html#play-a-job) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Post comment to commit]**

Este módulo de acción añade un comentario a un compromiso.

Para obtener información sobre los campos, consulte [Publicar comentario para compromiso](https://docs.gitlab.com/ee/api/commits.html#post-comment-to-commit) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Remove variable]**

Este módulo de acción quita la variable de un proyecto.

Para obtener información sobre los campos, consulte [Quitar variable](https://docs.gitlab.com/ee/api/project_level_variables.html#remove-variable) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Retry a build]**

Este módulo de acción reintenta una sola compilación en un compromiso.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para crear una nueva conexión, consulte <a href="#connect-gitlab-to-workfront-fusion" class="MCXref xref">[!UICONTROL Connect [!DNL GitLab] a Workfront Fusion]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p>Seleccione el proyecto que contiene la compilación que desea volver a intentar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Build ID]</td> 
   <td> Seleccione la compilación que desea volver a intentar. </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**[!UICONTROL Retry Failed Jobs in a Pipeline]**

Este módulo de acción reintenta las compilaciones con errores en una canalización.

Para obtener información sobre los campos, consulte [Reintentar trabajos en una canalización](https://docs.gitlab.com/ee/api/pipelines.html#retry-jobs-in-a-pipeline) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Get a Variable]**

Este módulo recupera detalles de la variable específica de un proyecto.

Para obtener información sobre los campos, consulte [Mostrar detalles de la variable](https://docs.gitlab.com/ee/api/project_level_variables.html#show-variable-details) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Update a release]**

Este módulo de acción actualiza una versión.

Para obtener información sobre los campos, consulte [Actualizar una versión](https://docs.gitlab.com/ee/api/releases/#update-a-release) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Update merge request]**

Este módulo de acción actualiza una solicitud de combinación existente. Puede cambiar la rama de destino, el título o incluso cerrar la MR.

Para obtener información sobre los campos, consulte [Actualizar solicitud de combinación](https://docs.gitlab.com/ee/api/merge_requests.html#update-mr) en la documentación de [!DNL GitLab].

+++

+++**[!UICONTROL Update a Variable]**

Este módulo de acción actualiza la variable de un proyecto.

Para obtener información sobre los campos, consulte [Actualizar variable](https://docs.gitlab.com/ee/api/project_level_variables.html#update-variable) en la documentación de [!DNL GitLab].

+++
