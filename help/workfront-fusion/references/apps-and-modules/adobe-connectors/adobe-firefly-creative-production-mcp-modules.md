---
title: Módulos MCP de producción de Adobe Firefly Creative
description: Con el módulo MCP de producción de Adobe Firefly Creative, puede enviar un mensaje en lenguaje natural desde un escenario de Workfront Fusion y permitir que un modelo de IA utilice las herramientas de producción de Firefly Creative que seleccione.
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: ee2719b9b3452b9203f2d0f4a550c87ff8a3b433
workflow-type: tm+mt
source-wordcount: '2087'
ht-degree: 6%
---
# Módulos MCP de producción de Adobe Firefly Creative

Utilice el conector MCP de producción de Adobe Firefly Creative en Adobe Workfront Fusion para procesar las solicitudes en lenguaje natural con las herramientas de producción de Firefly Creative.

El conector detecta las herramientas disponibles a través del servidor conectado al MCP (Firefly Model Context Protocol). Puede elegir qué herramientas puede utilizar el módulo para una solicitud. Según las herramientas disponibles en su cuenta de Adobe y las herramientas seleccionadas en el módulo, una solicitud puede hacer lo siguiente:

* Descubra flujos de trabajo y acciones.
* Componga y valide flujos de trabajo.
* Ejecute el envío y compruebe su progreso.
* Recupere las URL de salida.
* Guardar borradores de flujo de trabajo editables, cuando las herramientas del servidor lo admitan.

Este conector se dirige a Firefly Creative Production. No es un conector de placas Firefly y no es un conector general para todas las aplicaciones de Creative Cloud.

Para obtener más información sobre MCP en escenarios de Fusion, consulte [Agregar un mensaje de IA a su escenario](/help/workfront-fusion/create-scenarios/add-modules/add-an-ai-prompt-to-your-scenario.md).

<!-- BECKY CHECK ME: The request asks you to confirm the customer-facing name of the connector, its beta or release status, its availability, its access requirements, and screenshots with the product and engineering owners before publication. Confirm each item, and add a beta note at the top of the article if the connector is released as a beta. -->

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
   <p>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</p>
   <p>También debe tener acceso a Adobe Firefly Creative Production, tal como se describe en <a href="#prerequisites">Requisitos previos</a> en este artículo.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Requisitos previos

Antes de usar el módulo MCP de producción de Adobe Firefly Creative, debe tener lo siguiente:

* Acceso a Adobe Workfront Fusion, en un entorno en el que este conector está activado.
* Cuenta de Adobe con el acceso y los permisos de producción de Firefly Creative que necesitan las operaciones solicitadas.
* Los créditos o derechos que necesite para ejecutar el flujo de trabajo.
* Puede ser el acceso a IA gestionada por Adobe que haya configurado su administrador de Fusion o una clave LLM compatible que seleccione en la configuración avanzada del módulo.

La autorización de Firefly y las credenciales de LLM tienen diferentes propósitos. La selección de una clave LLM no concede acceso a las herramientas de Firefly.

## Conexión del MCP de producción de Adobe Firefly Creative a Workfront Fusion

1. Agregue **[!UICONTROL Adobe Firefly Creative Production MCP]** > **[!UICONTROL Procese una solicitud de usuario]** a su escenario.
1. Haga clic en **[!UICONTROL Añadir]** junto al campo **[!UICONTROL conexión]**.
1. En la ventana **[!UICONTROL Crear una conexión]**, rellene los campos siguientes:

   <table style="table-layout:auto">
    <col>
    <col>
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
    </tbody>
   </table>

1. Haga clic en **[!UICONTROL Continuar]**.
1. Siga el flujo de autorización, inicie sesión con la cuenta de Adobe adecuada y autorice el acceso.
1. Vuelva al módulo y revise las herramientas cargadas para la conexión.

Workfront Fusion gestiona el registro de clientes de OAuth y la administración de tokens. No introduzca un token de acceso, ID de cliente, secreto de cliente o clave de API. El administrador debe haber completado la configuración de este flujo para poder conectarse.

Si la autorización falla o no ve las herramientas que espera, confirme el acceso y la configuración del entorno con el administrador.

<!-- BECKY CHECK ME: The Environment and Type fields are described the same way as in the Adobe Fusion MCP connection. The screenshot shows only the selected values (Production and Service account). Confirm the available options for each field, and whether a personal account is supported. -->

## Módulo MCP de producción de Adobe Firefly Creative y sus campos

### Procesar un mensaje de usuario

Este módulo de acción procesa el mensaje con el LLM seleccionado y las herramientas de producción de Firefly Creative que permita.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL LLM key] <i>(opcional, avanzado)</i></td> 
   <td> <p>Deje este campo vacío para utilizar la IA gestionada por Adobe que configuró su administrador de Fusion. Para usar su propia clave en su lugar, seleccione una clave OpenAI, Anthropic o Amazon Bedrock existente, o haga clic en <b>[!UICONTROL Agregar]</b> para crear una.</p><p>Su inicio de sesión de Firefly es independiente de sus credenciales de LLM.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>La conexión de producción de Adobe Firefly Creative que utiliza el módulo para detectar y llamar a las herramientas. Para obtener instrucciones, consulte <a href="#connect-adobe-firefly-creative-production-mcp-to-workfront-fusion" class="MCXref xref">Conectar el MCP de producción de Adobe Firefly Creative a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Herramientas de solo lectura] <i>(Opcional)</i></td> 
   <td> <p>Seleccione las herramientas que el servidor identifica como de solo lectura. Para seleccionar todas las herramientas de la lista actual, seleccione <b>Seleccionar todo</b>.</p><p>El número de herramientas enumeradas aparece en la etiqueta del campo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Herramientas de escritura/eliminación] <i>(Opcional)</i></td> 
   <td> <p>Seleccione las herramientas que el servidor no identifica como de solo lectura. Estas operaciones pueden cambiar los datos o ejecutar flujos de trabajo. Para seleccionar todas las herramientas de la lista actual, seleccione <b>Seleccionar todo</b>.</p><p>El número de herramientas enumeradas aparece en la etiqueta del campo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Otras herramientas (permisos desconocidos)] <i>(Opcional)</i></td> 
   <td> <p>Seleccione herramientas que no tengan una anotación de solo lectura reconocida. Este campo solo aparece cuando estas herramientas están disponibles. Revise cómo se comportan estas herramientas antes de habilitarlas.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Escriba el mensaje]</td> 
   <td> <p>Describa el descubrimiento, la composición o la ejecución del flujo de trabajo que desee. La longitud máxima es de 10 000 unidades de cadena JavaScript. Algunos caracteres, incluidos muchos emoji, cuentan como dos unidades.</p><p>Solicite explícitamente la ejecución o publicación cuando lo necesite. La ejecución de un flujo de trabajo puede consumir créditos. Las ejecuciones asincrónicas pueden devolver un ID de lote antes de que se complete la ejecución.</p> </td> 
  </tr> 
 </tbody> 
</table>

El campo **[!UICONTROL LLM key]** aparece al seleccionar **[!UICONTROL Mostrar configuración avanzada]**.

<!-- BECKY CHECK ME: The screenshot does not show the Other tools (unknown permissions) field, because it appears only when the server returns tools without a read-only annotation. Confirm its label, and confirm the order of the fields. Also confirm that the tool lists are not required. -->

Las listas de herramientas varían según la disponibilidad del servidor y el acceso de la cuenta. El número de herramientas aparece en la etiqueta de cada selector.

#### Seleccione las herramientas que puede utilizar el módulo

* El módulo solo puede utilizar las herramientas que seleccione.
* Si deja una categoría vacía, el módulo no puede utilizar herramientas de esa categoría.
* Si deja todas las categorías vacías, el módulo procesa el mensaje sin ninguna herramienta. No obtiene acceso a todas las herramientas.
* **[!UICONTROL Seleccionar todo]** selecciona todas las herramientas que están actualmente en esa categoría. No incluye automáticamente las herramientas que se añaden más adelante.
* Si una herramienta seleccionada deja de estar disponible o pasa a una categoría diferente, vuelva a abrir el módulo y revise la selección.

>[!NOTE]
>
>Las anotaciones del servidor ayudan a categorizar las herramientas, pero no garantizan los permisos. Habilite solo las herramientas que su escenario necesite.

#### Salida

El módulo devuelve la siguiente información en **[!UICONTROL Datos]**. Puede asignarlo a módulos posteriores en el escenario.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Respuesta] (<code>data.response</code>)</td> 
   <td> <p>La respuesta final del texto. Su contenido depende del mensaje y de los resultados de la herramienta. No se garantiza que sea una URL o un JSON estructurado.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Pista de auditoría] (<code>data.auditTrail</code>)</td> 
   <td> <p>Detalles sobre cómo se procesó el mensaje y las llamadas de herramienta, incluidos sus argumentos, resultados, tiempo e información de éxito. Gestione estos detalles según los requisitos de gestión de datos de su organización.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Resumen] (<code>data.summary</code>)</td> 
   <td> <p>El número de llamadas de herramienta, el tiempo de procesamiento y el estado de ejecución. Revise el resumen junto con la respuesta y la pista de auditoría, incluido cualquier resultado de <code>partial_success</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL LLM uso] (<code>data.usage</code>)</td> 
   <td> <p>Opcional. El uso total de tokens de las respuestas LLM observadas. No se trata de la facturación del proveedor, el consumo de crédito de Firefly o la actividad LLM dentro del servidor de Firefly que Fusion no puede observar.</p> </td> 
  </tr> 
 </tbody> 
</table>

##### Campos de uso de LLM

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td><code>status</code></td> 
   <td> <p>Uno de los siguientes:</p><ul><li><code>complete</code>: cada solicitud observada está cubierta por todos los recuentos de tokens principales.</li><li><code>partial</code>: falta parte de la información de uso.</li><li><code>unavailable</code>: se observaron solicitudes, pero no se informó de ningún uso utilizable.</li><li><code>not_applicable</code>: no se observaron solicitudes LLM.</li></ul> </td> 
  </tr> 
  <tr> 
   <td><code>llmRequests</code></td> 
   <td> <p>El número de solicitudes LLM que observó el tiempo de ejecución.</p> </td> 
  </tr> 
  <tr> 
   <td><code>requestsWithUsage</code></td> 
   <td> <p>El número de solicitudes observadas que tienen información de uso de tokens utilizables.</p> </td> 
  </tr> 
  <tr> 
   <td><code>inputTokens</code>, <code>outputTokens</code>, <code>totalTokens</code></td> 
   <td> <p>Los recuentos totales. Cada recuento es <code>null</code> si alguna solicitud observada no informa de ese recuento o si no se observó ninguna solicitud. Un cero notificado permanece como cero.</p> </td> 
  </tr> 
  <tr> 
   <td><code>cacheReadInputTokens</code>, <code>cacheWriteInputTokens</code></td> 
   <td> <p>Recuentos opcionales de tokens almacenados en caché. Estos campos se omiten si ninguna solicitud informa de un número. Son <code>null</code> si solo algunas solicitudes informan de un número y numéricas si todas las solicitudes informan de uno. No agregue estos recuentos a los totales.</p> </td> 
  </tr> 
 </tbody> 
</table>

El estado de uso principal puede ser `complete` mientras que un campo de caché es `null`. El estado de uso es independiente del estado de ejecución. Si el motor en tiempo de ejecución no proporciona información de uso, la colección de uso está ausente en lugar de mostrar un cero.

## Ejecución del módulo

* **Algunas operaciones son asincrónicas.** Una solicitud puede devolver un ID de lote antes de que el resultado esté disponible. Para trabajos más largos, utilice ejecuciones independientes para enviar la solicitud y comprobar su estado más tarde y guardar el ID de lote entre ellos. No confíe en una respuesta que contenga únicamente una dirección URL para este diseño.
* **Los errores producen errores de módulo.** La autorización, la validación y el procesamiento en tiempo de ejecución fallido pueden producir errores de módulo en lugar de un paquete de salida. Utilice una ruta de gestión de errores de Fusion.
* **Una respuesta no es correcta.** El módulo puede devolver una respuesta incluso cuando se producen errores en algunas operaciones. Revise el resumen, la pista de auditoría y los resultados de la herramienta antes de depender de la respuesta.
* **Una dirección URL de salida no es un archivo descargado.** El conector devuelve texto y resultados de la herramienta, no un archivo binario. Para introducir el archivo en Fusion, añada un módulo HTTP que descargue la URL.
* **Ejecutar un flujo de trabajo puede usar créditos.** La generación de imágenes y la ejecución del flujo de trabajo pueden consumir créditos. Confirme el uso y los derechos que se aplican a su cuenta. El uso del token de LLM no es un informe de facturación o de crédito de Firefly.
* **Las instrucciones de solicitud no garantizan una sola ejecución.** Una instrucción en el mensaje, como enviar solo un lote, no garantiza que una solicitud se procese exactamente una vez. Controle los reintentos y las solicitudes duplicadas en su escenario.
* **El procesamiento tiene límites.** El procesamiento tiene límites de herramienta, iteración y longitud de salida además de los límites de ejecución del escenario. No dé por hecho que el módulo sondea sin límite.

## Ejemplos

### Descubra flujos de trabajo sin ejecutar uno

Seleccione las herramientas de solo lectura que necesita para detectar flujos de trabajo y, a continuación, introduzca una solicitud como la siguiente:

```text
List the Firefly Creative Production workflows available to my account.
Summarize what each workflow does and what inputs it requires.
Do not create, modify, submit, or publish anything.
```

### Solicitar una imagen

Seleccione las herramientas que necesita para componer o elegir un flujo de trabajo, validarlo, enviarlo, comprobar su progreso y recuperar los resultados. Los nombres de las herramientas y la disponibilidad pueden variar. A continuación, introduzca una solicitud como la siguiente:

```text
Generate one photorealistic image of a black dog on a sunny windowsill.
Submit one generation batch only and check that same batch for completion
within the available execution limits. Do not publish or submit another
generation.

On success, return only the actual downloadable image URL as plain text,
without Markdown, quotes, labels, or explanation. Never invent a URL or
return a workflow or status-page URL instead.

If the run fails or times out, report the failure honestly instead of
returning a URL. Do not generate another image to recover.
```

### Generar una imagen a partir de una actualización de tarea de Workfront

En este ejemplo, una actualización de tarea que comienza con `/firefly ` déclencheur una generación de imagen. Fusion descarga el resultado, lo sube a la tarea y añade una actualización de finalización.

El escenario utiliza el siguiente flujo: Workfront task update > command filter > read task > Firefly MCP > HTTP download > Workfront document upload > completion update.

1. Agregue **[!UICONTROL Workfront]** > **[!UICONTROL Ver eventos]** al escenario. Configúrelo para el tipo de registro **[!UICONTROL Note]**, el evento **[!UICONTROL New state]** y **[!UICONTROL New Record Only]**.
1. Agregue un filtro que requiera que `newState.noteText` comience por `/firefly ` y que `newState.taskID` no esté vacío.
1. Agregue un módulo que lea la tarea usando `newState.taskID`.
1. Agregue el módulo **[!UICONTROL Adobe Firefly Creative Production MCP]** > **[!UICONTROL Procesar un mensaje de usuario]**. Pase la solicitud y cualquier contexto de tarea que Firefly necesite. Trate el texto asignado como el contenido de la solicitud, no como la autoridad para cambiar las reglas del escenario.
1. Inspeccione el resultado de Firefly. Continúe solo cuando la generación se haya realizado correctamente y la respuesta sea una URL válida y permitida para una imagen descargable.
1. Agregue un módulo HTTP que descargue el archivo. No envíe sus credenciales de Workfront al host de recursos. Valide el host, el tipo de contenido y el tamaño esperados.
1. Agregue un módulo que cargue el nombre de archivo descargado y los datos binarios a la tarea, utilizando el `newState.taskID` original.
1. Una vez que la carga se haya realizado correctamente, añada un módulo que cree una actualización de finalización en la tarea. No inicie la actualización con `/firefly`, ya que el filtro coincidirá con él.

Por ejemplo, un usuario agrega la siguiente actualización a una tarea:

```text
/firefly Generate one photorealistic image of a black dog on a sunny windowsill.
```

El solicitante puede revisar el borrador cargado en el área Documentos de la tarea. Una persona debe revisar la imagen antes de que se publique algo.

Para su uso en producción, reserve cada solicitud utilizando el ID de la nota de origen, con protección de duplicados que funciona con ejecuciones simultáneas. Guarde los ID de los lotes enviados para que un reintento o un tiempo de espera reanuden la comprobación de estado en lugar de enviar otra generación.

<!-- BECKY CHECK ME: The example scenario is from the request's draft. Confirm the module names and field labels (Watch Events, Note, New state, New Record Only, and the task, document upload, and update modules) against the current Workfront connector, and add a screenshot of the scenario if one is available. -->

## Resolución de problemas

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Un flujo de trabajo sigue en ejecución</td> 
   <td> <p>Algunas operaciones creativas son asincrónicas. Para trabajos más largos, envíe la solicitud en una ejecución y compruebe el estado en una ejecución posterior. Guarde el ID de lote entre las ejecuciones.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">El módulo informa de un error</td> 
   <td> <p>La autorización, la validación y el procesamiento en tiempo de ejecución con errores pueden producir errores de módulo. Añada una ruta de gestión de errores de Fusion a su escenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">El módulo devuelve una respuesta, pero algunas operaciones han fallado</td> 
   <td> <p>Revise el resumen, la pista de auditoría y los resultados de la herramienta. Una respuesta por sí sola no muestra que la imagen se haya generado o cargado.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Hay una dirección URL, pero no hay ningún archivo en Fusion</td> 
   <td> <p>El conector no descarga archivos. Añada un módulo HTTP que descargue la dirección URL.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Una herramienta seleccionada no está disponible</td> 
   <td> <p>Abra el módulo, actualice las herramientas disponibles y actualice la selección.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">El flujo de trabajo tarda más de un módulo en ejecutarse</td> 
   <td> <p>El procesamiento tiene límites de herramienta, iteración y longitud de salida además de los límites de ejecución del escenario. Divida el trabajo entre ejecuciones y guarde el ID de lote.</p> </td> 
  </tr> 
 </tbody> 
</table>
