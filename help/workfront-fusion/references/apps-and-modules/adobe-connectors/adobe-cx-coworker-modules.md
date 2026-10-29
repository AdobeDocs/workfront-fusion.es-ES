---
title: Módulos de Adobe CX Enterprise Coworker
description: Utilice el conector de Adobe CX Enterprise Coworker en Adobe Workfront Fusion para enviar un mensaje en lenguaje natural al compañero y utilizar su respuesta en un escenario.
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: 6efe84af0487893a3c33ba2bf6e3db5200f25446
workflow-type: tm+mt
source-wordcount: '1974'
ht-degree: 7%
---
# Módulos de Adobe CX Enterprise Coworker

Utilice el conector de Adobe CX Enterprise Coworker en Adobe Workfront Fusion para enviar un mensaje en lenguaje natural al compañero y utilizar su respuesta en un escenario. El colaborador interpreta su solicitud y puede utilizar las herramientas disponibles en su cuenta para llevar a cabo el trabajo.

El conector proporciona dos módulos:

* **[!UICONTROL Ejecutar un mensaje]** inicia una nueva solicitud y, de manera predeterminada, espera el resultado.
* **[!UICONTROL Obtener estado de ejecución]** comprueba una solicitud que inició anteriormente.

## Requisitos de acceso

<!-- BECKY CHECK ME: This table is copied from other Fusion connector articles. The source material does not list access requirements, but says you need an Adobe account that has access to Coworker. Confirm the requirements and whether Coworker needs its own license or entitlement. -->

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
   <p>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Requisitos previos

Debe tener una cuenta de Adobe con acceso a Adobe CX Enterprise Coworker.

## Conexión de Adobe CX Enterprise Coworker a Workfront Fusion

Inicie sesión con una cuenta de Adobe que tenga acceso a sus colaboradores y a los servicios necesarios para realizar la solicitud.

Para crear una conexión:

1. En el módulo MCP de Adobe Fusion, haga clic en **[!UICONTROL Agregar]** junto al campo **Conexión**.
1. Rellene los campos siguientes:

   <table style="table-layout:auto">
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">Nombre de la conexión</td>
        <td>
          <p>Introduzca un nombre para esta conexión.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">Entorno</td>
        <td>
          <p>Seleccione si desea conectarse a un entorno de producción o de no producción.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">Tipo</td>
        <td>
          <p>Seleccione si desea conectarse a una cuenta de servicio o a una personal.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">ID de cliente</td>
        <td>
          <p>Escriba o asigne una anulación opcional para esta conexión. De lo contrario, utilice el clientId administrado por plataforma de este tipo de cuenta. Registre la URL de devolución de llamada de Fusion mostrada para la cuenta de Coworker dedicada.</p>
        </td>
      <tr>
        <td role="rowheader">Secreto de cliente</td>
        <td>
          <p>Escriba o asigne una anulación opcional para esta conexión. De lo contrario, utilice clientSecret administrado por plataforma de este tipo de cuenta. Utilice las credenciales emitidas para el entorno de IMS configurado.</p>
        </td>
    </tbody>
   </table>

1. Haga clic en **[!UICONTROL Continuar]**.

Si no puede iniciar sesión o utilizar un servicio requerido, póngase en contacto con el administrador.

## Módulos Adobe CX Enterprise Coworker y sus campos

>[!WARNING]
>
>Nunca incluya contraseñas u otras credenciales en una solicitud.

### Obtener estado de ejecución

Este módulo de acción comprueba el estado actual de una tarea iniciada por **[!UICONTROL Ejecutar un mensaje]**.

Este módulo comprueba la tarea una vez. No inicia una nueva tarea ni continúa comprobando hasta que se completa la tarea. Si el resultado sigue pendiente, vuelva a comprobarlo más tarde.

>[!NOTE]
>
>No convierta el ID de tarea en un número, ni lo redondee ni vuelva a darle formato. Si el Compañero de trabajo respondió a la solicitud original inmediatamente sin un ID de tarea, no es necesario que compruebe el estado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Incluir resultado sin procesar] <i>(Opcional, avanzado)</i></td> 
   <td> <p>Esta opción está desactivada de forma predeterminada. Incluya la respuesta completa de Compañero de trabajo en la salida. La respuesta puede contener información confidencial.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la misma conexión que utilizó en la ejecución original de <b>[!UICONTROL Ejecutar un indicador]</b>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Identificador de tarea]</td> 
   <td> <p>Asigne el ID de tarea devuelto por <b>[!UICONTROL Ejecutar un indicador]</b>. Manténgalo como texto exactamente como se devuelve.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Ejecutar un indicador

Este módulo de acción envía una instrucción al Compañero, como resumir texto o recopilar información mediante las herramientas disponibles en la cuenta.

Cada ejecución envía el mensaje una vez e inicia una nueva conversación. No es necesario seleccionar un modelo de IA ni proporcionar una clave de proveedor de IA independiente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la conexión de Coworker. Para obtener instrucciones, consulte <a href="#connect-adobe-cx-coworker-to-workfront-fusion" class="MCXref xref">Conectar Adobe CX Enterprise Coworker a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Mensaje de usuario]</td> 
   <td> <p>Introduzca las instrucciones. Puede utilizar varias líneas y asignar información de módulos anteriores.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Esperar la finalización] <i>(Opcional, avanzado)</i></td> 
   <td> <p>Esta opción está activada de forma predeterminada. Active esta opción si desea que el módulo espere a que finalice la tarea o si requiere atención. Desactívela para devolver el resultado inicial inmediatamente.</p><p>Para obtener más información, vea <a href="#wait-for-completion">Esperar a que se complete</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Incluir resultado sin procesar] <i>(Opcional, avanzado)</i></td> 
   <td> <p>Esta opción está desactivada de forma predeterminada. Active esta opción si desea que el módulo incluya la respuesta completa de Coworker en la salida. La respuesta puede contener información confidencial.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
> Recomendamos dejar **[!UICONTROL Incluir resultado sin procesar]** desactivado a menos que necesite la respuesta completa para un propósito específico. Los resultados sin procesar pueden contener información confidencial y no son un registro completo garantizado de cada acción. Revise el contenido de un resultado sin procesar antes de guardarlo, compartirlo o pasarlo a otro servicio.

#### Esperar a que se complete

Cuando **[!UICONTROL Esperar a que finalice]** está activado, el módulo comprueba la tarea después de una espera de cinco segundos. Si la tarea sigue pendiente, el módulo espera otros cinco segundos antes de volver a comprobarla. Cada cheque también tarda en recibir una respuesta. Comprobar el estado no vuelve a enviar la solicitud.

La espera se detiene cuando la tarea se completa, falla, se cancela o rechaza, o necesita su entrada o autorización. Si Coworker proporciona una respuesta inmediata, el módulo la devuelve sin realizar más comprobaciones.

Cuando **[!UICONTROL Esperar a que finalice]** está desactivado, el módulo devuelve el primer resultado sin esperar a que finalice la tarea. Inspeccionar **[!UICONTROL Estado]**, **[!UICONTROL Completado]** y **[!UICONTROL Requiere atención]** para decidir qué hacer a continuación. Ya se puede completar una tarea cuando llegue el primer resultado.

Esperar está sujeto al tiempo de espera del módulo de Fusion. Si el módulo agota el tiempo de espera o se detiene, es posible que el Compañero siga trabajando. En ese caso, es posible que no reciba un resultado o un ID de tarea.

Para trabajar más tiempo, desactive la espera y guarde la **[!UICONTROL Id. de tarea]** inicial para que pueda comprobar la tarea más tarde. No vuelva a ejecutar automáticamente la solicitud después de un tiempo de espera. Es posible que la primera solicitud ya esté en curso y que la repetición pueda duplicar cambios.


## Salida de módulo

Ambos módulos devuelven la siguiente información cuando finalizan sin error.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Identificador de tarea]</td> 
   <td> <p>Identifica la tarea. Este campo está vacío cuando Coworker proporciona una respuesta inmediata sin crear una tarea. Use este valor con <b>[!UICONTROL Obtener estado de ejecución]</b>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de contexto]</td> 
   <td> <p>Identifica la conversación. No es una entrada para continuar la conversación.</p><p>Para obtener más información, consulte <a href="#use-previous-answers">Usar respuestas anteriores</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL State]</td> 
   <td> <p>El estado de la tarea actual. Consulte <a href="#task-states" class="MCXref xref">Estados de tarea</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL completado]</td> 
   <td> <p>El valor es True cuando la tarea se completa o Coworker proporciona una respuesta inmediata.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Requiere atención]</td> 
   <td> <p>Es True cuando el Compañero de trabajo necesita entrada o autorización.</p><p>Para obtener más información, consulte <a href="#requests-that-need-attention">Solicitudes que requieren atención</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Texto del asistente final]</td> 
   <td> <p>La respuesta final cuando se completa la tarea. Está vacío mientras la tarea está pendiente o requiere atención. Una respuesta completada también puede no tener texto de respuesta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Artefactos de texto de [!UICONTROL (pueden incluir texto intermedio)]</td> 
   <td> <p>Texto devuelto durante el trabajo. Cada elemento puede incluir un ID de artefacto, un nombre y un texto. Estos elementos no son necesariamente respuestas finales.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resultado sin procesar (adhesión)]</td> 
   <td> <p>La respuesta completa. Esto solo se incluye cuando <b>[!UICONTROL Incluir resultado sin procesar]</b> está activado.</p> </td> 
  </tr> 
 </tbody> 
</table>

Use **[!UICONTROL texto del asistente final]** para la respuesta en lugar de combinar todos los artefactos de texto. Los artefactos pueden incluir descripciones de progreso u otro texto intermedio.

### Solicitudes que requieren atención

Es posible que el compañero necesite más información o autorización antes de poder continuar. Cuando esto sucede, **[!UICONTROL Requiere atención]** es verdadero y **[!UICONTROL Completado]** es falso. Enrute el resultado a una persona en lugar de tratarlo como trabajo completado.

Estos módulos no pueden responder a una pregunta de seguimiento ni aprobar una acción en su nombre. **[!UICONTROL Obtener estado de ejecución]** puede comprobar si el estado de la tarea ha cambiado, pero no resuelve la solicitud de entrada o autorización.

### Usar respuestas anteriores

Cada **[!UICONTROL ejecución de un indicador]** inicia una nueva conversación. Para referirse a una respuesta anterior, incluya la pregunta y la respuesta relevantes como texto en el nuevo mensaje. Esto proporciona contexto a Compañero de trabajo, pero no reanuda la conversación anterior.

**[!UICONTROL ID de contexto]** identifica la conversación asociada con el resultado. No puede suministrarlo a estos módulos para continuar una conversación.

>[!IMPORTANT]
>
>**[!UICONTROL Completada]** no garantiza que la acción empresarial solicitada se haya realizado correctamente. Por ejemplo, un compañero podría terminar explicando que una herramienta necesaria no estaba disponible. Revise la respuesta y compruebe los resultados necesarios antes de realizar la siguiente acción.

### Estados de tarea

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"><code>submitted</code>, <code>working</code></td> 
   <td> <p>La tarea está pendiente. <b>[!UICONTROL completado]</b> es falso. <b>[!UICONTROL Ejecutar un indicador]</b> continúa esperando cuando la espera está activada. De lo contrario, guarde el ID de tarea y compruébelo más tarde.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><code>completed</code></td> 
   <td> <p><b>[!UICONTROL Completed]</b> tiene un valor verdadero. Revise <b>[!UICONTROL Texto final del asistente]</b> y el resultado esperado.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><code>input-required</code>, <code>auth-required</code></td> 
   <td> <p>La tarea necesita atención. <b>[!UICONTROL completado]</b> es falso y <b>[!UICONTROL requiere atención]</b> es verdadero. La espera se detiene. Dirija el resultado para revisión humana.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><code>failed</code>, <code>canceled</code>, <code>rejected</code></td> 
   <td> <p>El módulo informa de un error en lugar de un resultado normal.</p> </td> 
  </tr> 
 </tbody> 
</table>

Un resultado pendiente o un resultado que requiera atención no es una finalización correcta, aunque el módulo se devuelva sin error.

## Ejemplos

### Resumir una actualización

1. Agregue **[!UICONTROL Ejecutar un indicador]** y seleccione su conexión.
1. Escriba lo siguiente en el campo **[!UICONTROL Mensaje de usuario]**:

   ```text
   Summarize the following project update in three bullet points.
   Use only the supplied text; do not call tools or change any records.
   
   The planning workshop is complete. Two dependencies need confirmation.
   The team will review the delivery estimate on Friday.
   ```

1. Deje **[!UICONTROL Esperar a que se complete]** el y **[!UICONTROL Incluir resultado sin procesar]** desactivado.
1. Si **[!UICONTROL Requiere atención]** es verdadero, enrute el resultado para revisión humana. Si **[!UICONTROL Completado]** es verdadero, asigne **[!UICONTROL Texto del asistente final]** a su siguiente paso.

El texto generado por IA puede variar. Revise los resultados donde la precisión importa.

### Comprobar una tarea más larga más tarde

1. Agregar **[!UICONTROL Ejecutar un indicador]**, seleccione su conexión e introduzca sus instrucciones.
1. Desactivar **[!UICONTROL Esperar a que finalice]**.
1. Inspeccione el resultado inicial.

   * Si la tarea se completa, procese el resultado.
   * Si la tarea requiere atención, enrute el resultado para su revisión.
   * Si la tarea está pendiente, guarde el **[!UICONTROL Id. de tarea]** como texto y anote la conexión que utilizó.

1. Más adelante, use **[!UICONTROL Obtener estado de ejecución]** con esa conexión e ID de tarea.
1. Si la tarea sigue pendiente, organice otra comprobación dentro de los límites del escenario. Procese el resultado una vez al finalizar y gestione la atención o los errores por separado.

No vuelva a ejecutar la solicitud original solo para comprobar su progreso.

## Consideraciones de uso

* Los compañeros de trabajo pueden utilizar herramientas y realizar las acciones permitidas por su cuenta, incluidos los cambios en los registros. Utilice mensajes de confianza y una cuenta con el acceso adecuado.
* Estos módulos no proporcionan una forma de restringir las herramientas individuales. Instrucciones como &quot;no cambiar nada&quot; describen su intención, pero no son un modo de solo lectura obligatorio.
* Las herramientas y habilidades disponibles varían según la cuenta. El conector no proporciona un selector de aptitudes ni garantiza una acción en particular, como crear un recorrido o actualizar un proyecto. No suponga que las solicitudes que necesitan aprobación se completarán sin atención.
* El conector se inicia y comprueba las solicitudes de Coworker. No supervisa los cambios del proyecto ni guarda automáticamente las respuestas en otra aplicación. Agregue los módulos de déclencheur, almacenamiento y seguimiento adecuados a su escenario según sea necesario.
* Las respuestas generadas por IA pueden ser incompletas o inexactas. Valide los resultados importantes antes de utilizarlos para realizar cambios o tomar decisiones.
* El conector no reintenta automáticamente una solicitud fallida. Asegúrese de que el tratamiento de errores de su escenario no repita un mensaje cuyo resultado sea incierto.

## Resolución de problemas

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Falta un campo obligatorio</td> 
   <td> <p>Seleccione una conexión e introduzca la solicitud de datos o el ID de tarea necesarios.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Error de inicio de sesión o acceso denegado</td> 
   <td> <p>Inicie sesión de nuevo y compruebe que su cuenta de Adobe tiene acceso a sus colaboradores y a los servicios necesarios. Póngase en contacto con el administrador si es necesario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tarea no encontrada</td> 
   <td> <p>Compruebe que el ID de tarea no haya cambiado y que esté utilizando la conexión original. Es posible que una nueva tarea no sea visible inmediatamente. Compruebe el estado más tarde en lugar de volver a enviar la solicitud.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Error en una comprobación de estado</td> 
   <td> <p>Si el error incluye el Id. de tarea aceptado, use <b>[!UICONTROL Obtener estado de ejecución]</b> para investigar esa tarea. No reinicie el mensaje automáticamente.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Ejecutar un indicador agota el tiempo de espera o pierde su respuesta</td> 
   <td> <p>Es posible que la tarea se haya iniciado aunque no haya recibido su ID. Investigue antes de repetir la solicitud para evitar trabajos duplicados.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Fusion agota el tiempo de espera mientras espera</td> 
   <td> <p>El compañero podría seguir trabajando. Compruebe la tarea si tiene su ID. Para futuras tareas largas, desactive la espera y guarde primero el ID inicial.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Compañero de trabajo o un servicio requerido no está disponible</td> 
   <td> <p>Comparta el error mostrado con el administrador, sin credenciales ni contenido de resultado confidencial.</p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- BECKY CHECK ME: Confirm the exact module and field labels in the UI (Run a Prompt, Get Execution Status, User prompt, Wait for completion, Include raw result, Task ID, and the output item names). Also confirm that the module is listed under "Adobe CX Enterprise Coworker" in the app picker. -->
