---
title: Módulos OpenAI (ChatGPT)
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan OpenAI (ChatGPT), así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: c8138d82-fa5a-4e69-b3cb-aa232099cb33
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '1422'
ht-degree: 76%

---

# Módulos de [!DNL OpenAI (ChatGPT & DALL-E)]

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!DNL OpenAI (ChatGPT & DALL-E)], así como conectarlo a varias aplicaciones y servicios de terceros.

Para obtener instrucciones sobre cómo crear un escenario, vea los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront</td> 
   <td> <p>Cualquier paquete de flujo de trabajo de Adobe Workfront y cualquier paquete de integración y automatización de Adobe Workfront</p><p>Workfront Ultimate</p><p>Paquetes Workfront Prime y Select, con una compra adicional de Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencias de Adobe Workfront</td> 
   <td> <p>Estándar</p><p>Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion</td> 
   <td>
   <p>Basado en operaciones: no se requiere licencia de Workfront Fusion</p>
   <p>Basado en conectores (heredado): Workfront Fusion para la automatización e integración del trabajo </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete Select o Prime Workfront que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Para usar módulos de [!DNL OpenAI (ChatGPT & DALL-E)], debe tener una cuenta de [!DNL OpenAI], que incluya una clave API y un ID de organización.

## Información de la API de OpenAI (ChatGPT &amp; DALL-E)

El conector OpenAI (ChatGPT &amp; DALL-E) utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> Versión 1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.11.1</td> 
  </tr>
 </tbody> 
 </table>

## Conectando [!DNL OpenAI (ChatGPT & DALL-E)] a Workfront Fusion

Puede crear una conexión con su cuenta de [!DNL OpenAI (ChatGPT & DALL-E)] directamente desde un módulo de [!DNL OpenAI (ChatGPT & DALL-E)].

1. En cualquier módulo de [!DNL OpenAI (ChatGPT & DALL-E)], haga clic en **[!UICONTROL Añadir]** junto al campo [!UICONTROL Conexión].
1. Introduzca la siguiente información:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td> <p>Introduzca un nombre para la nueva conexión.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL API Key]</td> 
      <td>Puede localizar la clave API en la configuración de usuario de OpenAI.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Organization ID] </td> 
      <td>Puede localizar su ID de organización en la página Configuración de la organización en OpenAI.</td> 
     </tr> 
    </tbody> 
   </table>

1. Haga clic en **[!UICONTROL Continuar]** para crear la conexión y volver al módulo.


## Módulos de [!DNL OpenAI (ChatGPT & DALL-E)] y sus campos

Al configurar módulos de [!DNL OpenAI (ChatGPT & DALL-E)], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL OpenAI (ChatGPT & DALL-E)] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Crear una finalización

>[!IMPORTANT]
>
>Este módulo ha quedado en desuso.

<!--

This action module creates a completion for the provided prompt or chat.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your [!DNL OpenAI (ChatGPT & DALL-E)] account to Workfront Fusion, see <a href="#connecting-openaichatgpt-to-workfront-fusion" class="MCXref xref">Connecting [!DNL OpenAI (ChatGPT & DALL-E)] to Workfront Fusion</a> in this article.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Model]</td> 
   <td> Enter or map the ID of the model to use. You can use the Get models module to see all of your available models. </td> 
  </tr> 
 <tr> 
   <td role="rowheader">[!UICONTROL Temperature]</td> 
   <td> This value must be between 0 and 2, and determines the randomness of the output. Higher values produce output that is more random, while lower values produce more focused output. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Advanced settings]</td> 
   <td> <p>For information about the optional advanced settings in this module, see the information about creating completions in the <a href="https://platform.openai.com/docs/api-reference/completions/create" class="MCXref xref">OpenAI API documentation</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

-->

### Crear una moderación

Este módulo de acción determina si el texto infringe la política de contenido de OpenAI.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL OpenAI (ChatGPT & DALL-E)] a Workfront Fusion, consulte <a href="#connecting-openaichatgpt-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL OpenAI (ChatGPT & DALL-E)] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Input]</td> 
   <td> Para cada muestra de texto que desee incluir, haga clic en <b>Agregar elemento</b> y escriba o asigne el texto. Incluya la muestra de texto completa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Model]</td> 
   <td> Introduzca o asigne el ID del modelo que desea utilizar. Puede utilizar el módulo Obtener modelos para ver todos los modelos disponibles. </td> 
  </tr> 
 </tbody> 
</table>

### Crear una edición

Siguiendo sus instrucciones, este módulo de acción devuelve una versión editada de una indicación que ha proporcionado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL OpenAI (ChatGPT & DALL-E)] a Workfront Fusion, consulte <a href="#connecting-openaichatgpt-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL OpenAI (ChatGPT & DALL-E)] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Model]</td> 
   <td> Introduzca o asigne el ID del modelo que desea utilizar. Puede utilizar el módulo Obtener modelos para ver todos los modelos disponibles. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Input]</td> 
   <td> Escriba o asigne el texto que desea editar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Instruction]</td> 
   <td> Introduzca o asigne las instrucciones de edición. Ejemplo: “Corregir los errores ortográficos”. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Ajustes avanzados]</td> 
   <td> <p>Para obtener información sobre la configuración avanzada opcional de este módulo, consulte la información sobre la creación de ediciones en la <a href="https://platform.openai.com/docs/api-reference/edits/create" class="MCXref xref">documentación de la API de OpenAI</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Crear una incrustación

Este módulo de acción crea un vector de incrustación que representa el texto de entrada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL OpenAI (ChatGPT & DALL-E)] a Workfront Fusion, consulte <a href="#connecting-openaichatgpt-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL OpenAI (ChatGPT & DALL-E)] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Model]</td> 
   <td> Introduzca o asigne el ID del modelo que desea utilizar. Puede utilizar el módulo Obtener modelos para ver todos los modelos disponibles. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Texto de entrada para incrustar]</td> 
   <td> Escriba o asigne el texto que desea incrustar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL User ID]</td> 
   <td> Introduzca o asigne un identificador único que represente a su usuario final, lo que puede ayudar a OpenAI a monitorizar y detectar el abuso </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> Introduzca o asigne el número máximo de ediciones con las que desea que funcione el módulo durante cada ciclo de ejecución de escenario.</td> 
  </tr> 
 </tbody> 
</table>

### Crear la finalización de chat

Dada una lista de mensajes que describen una conversación, este módulo de acción devuelve una respuesta.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL OpenAI (ChatGPT & DALL-E)] a Workfront Fusion, consulte <a href="#connecting-openaichatgpt-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL OpenAI (ChatGPT & DALL-E)] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Model]</td> 
   <td> Introduzca o asigne el ID del modelo que desea utilizar. Puede utilizar el módulo Obtener modelos para ver todos los modelos disponibles. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mensajes]</td> 
   <td>Los mensajes describen la conversación hasta el momento. Para cada mensaje que desee añadir, haga clic en <b>Añadir elemento</b> y rellene lo siguiente:
   <ul>
   <li> <b>Función</b>: seleccione la función del autor de este mensaje.</li>
   <li> <b>Contenido</b>: escriba o asigne el contenido de este mensaje.</li>
   <li> <b>Nombre</b>: escriba o asigne el nombre del autor de este mensaje. El nombre puede contener letras en mayúsculas y minúsculas, números y guiones bajos. La longitud máxima del nombre es de 64 caracteres.</li>
   </ul>
    </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Ajustes avanzados]</td> 
   <td> <p>Para obtener más información acerca de la configuración avanzada opcional de este módulo, consulte la información sobre la creación de finalizaciones de chat en la <a href="https://platform.openai.com/docs/api-reference/chat/create" class="MCXref xref">documentación de la API de OpenAI</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

<!--

### Edit image

This action module makes edits or creates variations of existing images.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your [!DNL OpenAI (ChatGPT & DALL-E)] account to Workfront Fusion, see <a href="#connecting-openaichatgpt-to-workfront-fusion" class="MCXref xref">Connecting [!DNL OpenAI (ChatGPT & DALL-E)] to Workfront Fusion</a> in this article.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select the operation]</td> 
   <td> Select whether you want to create edits or variations of the image.
   <p>NOTE: Images must be a valid PNG file, less than 4MB, and square. If mask is not provided, the image must have transparency, which will be used as the mask.</p> 
 </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>Select a source file from a previous module, or map the source file's name and data.</td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Text description of desired image]</td> 
   <td> <p>If editing an image, enter or map a description of the edits you want to create. Maximum length is 1000 characters.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Advanced settings]</td> 
   <td> <p>For information about the optional advanced settings in this module, see the information about creating image edits or variations in the <a href="https://platform.openai.com/docs/api-reference/images/createEdit" class="MCXref xref">OpenAI API documentation</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

-->

### Generar imágenes

Este módulo de acción genera o manipula imágenes con modelos Dall-E.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL OpenAI (ChatGPT & DALL-E)] a Workfront Fusion, consulte <a href="#connecting-openaichatgpt-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL OpenAI (ChatGPT & DALL-E)] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text description of the desire image]</td> 
   <td> Introduzca o asigne una descripción de la imagen deseada. La longitud máxima de la descripción es de 1000 caracteres. 
 </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Ajustes avanzados]</td> 
   <td> <p>Para obtener información sobre lo ajustes avanzados opcionales de este módulo, consulte la información sobre la creación de imágenes en la <a href="https://platform.openai.com/docs/api-reference/images/create" class="MCXref xref">documentación de la API de OpenAI</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Obtener modelos

Este módulo enumera y describe los distintos modelos disponibles en la API de OpenAI.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL OpenAI (ChatGPT & DALL-E)] a Workfront Fusion, consulte <a href="#connecting-openaichatgpt-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL OpenAI (ChatGPT & DALL-E)] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Action]</td> 
   <td> Seleccione si desea obtener una lista de todos los modelos o recuperar un modelo específico.
    <ul>
    <li><p><b>Enumerar modelos </b></p><p>Esta acción enumera los modelos disponibles actualmente y proporciona información básica sobre cada uno, como el propietario y la disponibilidad.</p></li>
    <li><p><b>Recuperar modelo </b></p><p>Introduzca o asigne el ID del modelo que desea recuperar. </p></li>
   </ul>
 </td> 
  </tr>
 </tbody> 
</table>

### Realizar una llamada de API personalizada

Este módulo de acción envía una petición HTTP personalizada a la API de OpenAI.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL OpenAI (ChatGPT & DALL-E)] a Workfront Fusion, consulte <a href="#connecting-openaichatgpt-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL OpenAI (ChatGPT & DALL-E)] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> <p>Escriba una ruta relativa a <code>https://api.openai.com/v1/</code> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion añade los encabezados de autorización automáticamente.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Añada la consulta para la llamada de API en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la instrucción condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

<!--

### Manage Audio

This action modules converts audio to text.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your [!DNL OpenAI (ChatGPT & DALL-E)] account to Workfront Fusion, see <a href="#connecting-openaichatgpt-to-workfront-fusion" class="MCXref xref">Connecting [!DNL OpenAI (ChatGPT & DALL-E)] to Workfront Fusion</a> in this article.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select the operation]</td> 
   <td> Select whether you want to transcribe the audio into the input language, or into English.
   <p>If transcribing into the input language, you can select the language in this module's advanced settings. </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>Select a source file from a previous module, or map the source file's name and data.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> Enter or map the maximum number of edits you want the module to work with during each scenario execution cycle.</td> 
   <tr> 
   <td role="rowheader">[!UICONTROL Advanced settings]</td> 
   <td> <p>For information about the optional advanced settings in this module, see the information about creating transcriptions in the <a href="https://platform.openai.com/docs/api-reference/audio/createTranscription" class="MCXref xref">OpenAI API documentation</a>.</p> </td> 
  </tr> 
  </tr> 
 </tbody> 
</table>

-->

### Administrar archivos

Este módulo de acción enumera, elimina o recupera archivos o contenido de archivo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL OpenAI (ChatGPT & DALL-E)] a Workfront Fusion, consulte <a href="#connecting-openaichatgpt-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL OpenAI (ChatGPT & DALL-E)] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Action]</td> 
   <td> Seleccione la acción que desea realizar. 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td> Si desea eliminar un archivo, o recuperar un archivo o contenido de archivo, introduzca o asigne el ID del archivo. 
  </tr> 
</tbody>
</table>

### Administrar ajustes

Administre trabajos de ajuste para adaptar un modelo a datos de capacitación específicos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL OpenAI (ChatGPT & DALL-E)] a Workfront Fusion, consulte <a href="#connecting-openaichatgpt-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL OpenAI (ChatGPT & DALL-E)] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select the operation]</td> 
   <td> Seleccione la acción que desea realizar.
   <ul>
   <li><p>Ajustar un modelo de un conjunto de datos</p><p>Introduzca o asigne una descripción para la imagen deseada.</p>
     <li><p>Obtener información sobre un trabajo de ajuste</p><p>Introduzca o asigne el ID del trabajo.</p>
   <li><p>Cancelar un trabajo de ajuste</p><p>Introduzca o asigne el ID del trabajo.</p>
   <li><p>Cancelar un trabajo de ajuste</p><p>Introduzca o asigne el ID del trabajo.</p>
   <li><p>Obtener actualizaciones de estado para un trabajo de ajuste</p><p>Introduzca o asigne el ID del trabajo y seleccione si desea transmitir estas actualizaciones.</p>
   <li><p>Eliminar un modelo ajustado</p><p>Introduzca o asigne el ID del modelo que desea eliminar.</p>
 </ul> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td> Si desea eliminar un archivo, o recuperar un archivo o contenido de archivo, introduzca o asigne el ID del archivo. 
  </tr> 
</tbody>
