---
title: Módulos de audio y vídeo de Adobe Firefly
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan audio y vídeo de Adobe Firefly, así como conectarlos a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
source-git-commit: f54338aa35b8453ac991c9e16974f2b61fd30168
workflow-type: tm+mt
source-wordcount: '1618'
ht-degree: 15%

---

# Módulos de audio y vídeo de Adobe Firefly

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan audio y vídeo de Adobe Firefly, así como conectarlos a varias aplicaciones y servicios de terceros.

Si necesita instrucciones sobre cómo crear un escenario, vea los artículos en [Crear un escenario: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, consulte los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

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
   <td role="rowheader">Licencia de Adobe Workfront Fusion</td> 
   <td>
   <p>Basado en operaciones: no se requiere licencia de Workfront Fusion</p>
   <p>Basado en conector (heredado): Workfront Fusion for Work Automation and Integration </p>
   </td> 
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

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Antes de poder usar el conector de audio y vídeo de Adobe Firefly, debe asegurarse de que se cumplen los siguientes requisitos previos:

* Debe tener una cuenta activa de audio y vídeo de Adobe Firefly.

## Crear una conexión con audio y vídeo de Adobe Firefly

Para crear una conexión para los módulos de audio y vídeo de Adobe Firefly:

1. En cualquier módulo, haga clic en **[!UICONTROL Agregar]** junto al cuadro Conexión.

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
        <td>Seleccione si desea conectarse a un entorno de producción o de no producción.</td>
        </tr>
        <tr>
        <td role="rowheader">Tipo</td>
        <td>Seleccione si desea conectarse a una cuenta de servicio o a una personal.</td>
        </tr>
        <tr>
        <td role="rowheader">ID de cliente</td>
        <td>Introduzca su ID de cliente de Adobe. Esto se puede encontrar en la sección Detalles de credenciales de Adobe Developer Console.</td>
        </tr>
        <tr>
        <td role="rowheader">Secreto de cliente</td>
        <td>Escriba el Secreto de cliente de Adobe. Esto se puede encontrar en la sección Detalles de credenciales de Adobe Developer Console.</td>
        </tr>
      </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.


## Módulos de audio y vídeo de Adobe Firefly y sus campos

Al configurar los módulos de audio y vídeo de Adobe Firefly, Workfront Fusion muestra los campos que se indican a continuación. Junto con estos, pueden mostrarse campos adicionales de audio y vídeo de Adobe Firefly, en función de factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, consulte [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Acciones

* [Describir plantilla](#describe-template)
* [Copia de audio o vídeo](#dub-audio-or-video)
* [Generar vídeo de avatar a partir de texto o audio](#generate-avatar-video-from-text-or-audio)
* [Generar voz a partir de texto](#generate-speech-from-text)
* [Reencuadre de vídeo](#reframe-video)
* [Plantilla de procesamiento](#render-template)
* [Transcribir medios](#transcribe-media)

#### Describir plantilla

Este módulo de acción analiza un archivo MOGRT (plantilla de vídeo) y devuelve un manifiesto de controles editables, fuentes, imágenes, audio, vídeo y otros valores compatibles.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe Firefly, consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con Adobe Firefly</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>Introduzca o asigne la dirección URL con prefijo que apunta al archivo de plantilla de entrada.</td> 
  </tr>
 </tbody> 
</table>

#### Copia de audio o vídeo

Este módulo de acción genera audio o vídeo doblado. También puede incluir la sincronización de labios en el vídeo generado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe Firefly, consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con Adobe Firefly</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de volcado</td> 
   <td>Seleccione si desea generar una copia de audio o vídeo.</td> 
  </tr>
  <tr> 
   <td role="rowheader">URL con prefijo</td> 
   <td>Introduzca o asigne la dirección URL firmada previamente que el módulo utilizará para la entrada.<p>Firefly Audio and Video acepta los siguientes dominios para el almacenamiento de medios</p>
   <ul>
   <li>adobe.io</li>
   <li>frame.io</li>
   <li>amazonaws.com</li>
   <li>windows.net</li>
   <li>dropboxusercontent.com</li>
   <li>drive.google.com</li>
   <li>cloudfront.net</li>
   </ul>
   </td> 
  </tr>
  <tr> 
   <td role="rowheader">Tipo de medio</td> 
   <td>Seleccionar el tipo de medio del archivo de entrada</td> 
  </tr>
  <tr> 
   <td role="rowheader">Sincronización labial</td> 
   <td>Seleccione si desea generar una sincronización labial compuesta de alta calidad para la salida de vídeo.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Códigos de configuración regional de Target</td> 
   <td>Para cada código de configuración regional que desee agregar, haga clic en <b>Agregar elemento</b> y seleccione el código de configuración regional.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Transcripciones</td> 
   <td>Para cada transcripción que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca o asigne las direcciones URL prefirmadas para la transcripción.</td> 
  </tr>
 </tbody> 
</table>

#### Generar vídeo de avatar a partir de texto o audio

Este módulo de acción genera un vídeo de avatar a partir de la transcripción o el archivo de audio que proporcione.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe Firefly, consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con Adobe Firefly</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>Introduzca o asigne la dirección URL firmada previamente que el módulo utilizará para la entrada.   </td> 
  </tr>
  <tr> 
  <tr> 
   <td role="rowheader">Código de configuración regional</td> 
   <td>Seleccione el código de configuración regional que representa el idioma que desea utilizar en el resultado.</td> 
  </tr>
   <td role="rowheader">Tipo de medio (Source)</td> 
   <td>Seleccionar el tipo de medio del archivo de entrada</td> 
  </tr>
  <tr> 
   <td role="rowheader">Avatar</td> 
   <td>Seleccione el avatar que desee utilizar para el vídeo generado.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Tipo de medio</td> 
   <td>Seleccione el tipo de medio de salida del vídeo generado.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Ancho</td> 
   <td>Introduzca o asigne el ancho del vídeo generado.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Altura</td> 
   <td>Introduzca o asigne la altura del vídeo generado.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Contexto</td> 
   <td>Seleccione el tipo de fondo que desea utilizar para el vídeo generado:
   <ul>
   <li><b>Vídeo</b>: escriba o asigne la dirección URL del vídeo de fondo.</li> 
   <li><b>Imagen</b>: escriba o asigne la dirección URL de la imagen de fondo.</li>
   <li><b>Color</b>: escriba o asigne el valor hexadecimal del color que desea utilizar para el fondo del vídeo.</li> 
   </ul>
   </td>
  </tr>
 </tbody> 
</table>

#### Generar voz a partir de texto

Este módulo de acción genera voz a partir de una transcripción. Puede proporcionar una transcripción de texto sin formato o una dirección URL con firma previa. La respuesta incluye un ID de trabajo y una URL de estado para realizar el seguimiento del trabajo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe Firefly, consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con Adobe Firefly</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Script</td> 
   <td>Seleccione el tipo de script que desea proporcionar.
   <ul>
   <li><b>Texto</b>: escriba o asigne el texto de origen en el campo Texto.</li>
   <li><b>Archivo de texto</b>: escriba o asigne la dirección URL del archivo de texto en el campo URL.</li>
   </ul>
   </td> 
  </tr>
  <tr> 
   <td role="rowheader">Código de configuración regional</td> 
   <td>Seleccione el código de configuración regional que representa el idioma que desea utilizar en el resultado.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Tipo de medio</td> 
   <td>Debe ser <code>text/plain</code>.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Voz</td> 
   <td>Seleccione la voz que desee utilizar. Las voces disponibles provienen del catálogo de voces de Adobe Firefly.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Salida</td> 
   <td>Debe ser <code>audio/wav</code>.</td> 
  </tr>
 </tbody> 
</table>

#### Reencuadre de vídeo

Este módulo redistribuye los medios que ha proporcionado. El contenido se proporciona mediante una dirección URL prefirmada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe Firefly, consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con Adobe Firefly</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL con prefijo</td> 
   <td>Introduzca o asigne la dirección URL firmada previamente que el módulo utilizará para la entrada.<p>Firefly Audio and Video acepta los siguientes dominios para el almacenamiento de medios</p>
   <ul>
   <li>adobe.io</li>
   <li>frame.io</li>
   <li>amazonaws.com</li>
   <li>windows.net</li>
   <li>dropboxusercontent.com</li>
   <li>drive.google.com</li>
   <li>cloudfront.net</li>
   </ul>
   </td> 
  </tr>
  <tr> 
   <td role="rowheader">Detección de edición de escena</td> 
   <td>Seleccione si desea aplicar la detección de edición de escenas antes de reenmarcar. </td> 
  </tr>
  <tr> 
   <td role="rowheader">Punto focal</td> 
   <td>Para cada punto focal que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca o el identificador de palabra clave para el punto focal.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Superposiciones</td> 
   <td>Para cada superposición que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca la información de superposición.
   <ul>
   <li><b>Source</b>: escriba o asigne la dirección URL que señala al medio de origen.</li> 
   <li><b>Hora de inicio</b>: escriba o asigne la hora de inicio.</li>
   <li><b>Duración</b>: escriba o asigne la duración de la superposición.</li> 
   <li><b>Anchura</b>: escriba o asigne el ancho de la superposición a escala.</li> 
   <li><b>Altura</b>: escriba o asigne la altura de la superposición a escala.</li> 
   <li><b>Punto de anclaje</b>: seleccione el punto de anclaje para la superposición.</li> 
   <li><b>Desplazamiento X</b>: escriba o asigne el desplazamiento horizontal para la superposición.</li> 
   <li><b>Desplazamiento Y</b>: escriba o asigne el desplazamiento vertical para la superposición.</li> 
   <li><b>Repetir</b>: Escriba <code>loop</code> para que un GIF se reproduzca.</li> 
   </ul>
   </td> 
  </tr>
  <tr> 
   <td role="rowheader">Formato de medios</td> 
   <td>Seleccione el formato del vídeo reformulado.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Formato Sidecar</td> 
   <td>Seleccione el formato para metadatos adicionales.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Representaciones</td> 
   <td>Para agregar representaciones adicionales, haga clic en <b>Agregar elemento</b> e introduzca la información de la representación.<!--add additional info--></td> 
  </tr>
 </tbody> 
</table>

#### Plantilla de procesamiento

Este módulo procesa una o más variaciones de vídeo al aplicar anulaciones y ajustes preestablecidos de exportación.



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe Firefly, consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con Adobe Firefly</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL del archivo de plantilla de entrada</td> 
   <td>Introduzca o asigne la dirección URL firmada previamente que representa la plantilla que desea procesar.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Fuentes</td> 
   <td>Para cada fuente que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca el nombre del postscript de la fuente y la dirección URL del archivo de fuente.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Cuando falta una fuente</td> 
   <td>Seleccione si desea que falle el procesamiento o utilice la fuente predeterminada si falta una fuente.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Recursos de medios</td> 
   <td>Para cada recurso multimedia que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca o asigne la dirección URL firmada previamente que representa el recurso.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Exportar ajustes preestablecidos</td> 
   <td>Para cada ajuste preestablecido de exportación que desee agregar, haga clic en <b>Agregar elemento</b>, seleccione el ajuste preestablecido de vídeo e introduzca o asigne la dirección URL firmada previamente que representa el ajuste preestablecido.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Variaciones</td> 
   <td>Para cada variación que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca los detalles de la variación. Debe introducir los detalles de al menos una variación.<!--add data here--></td> 
  </tr>
  <tr> 
   <td role="rowheader">Definiciones de salida</td> 
   <td>Defina los resultados haciendo clic en <b>Agregar elemento</b>, seleccionando cuál de las variaciones y ajustes preestablecidos agregados desea utilizar y agregando un nombre de archivo. Las variaciones y los ajustes preestablecidos se indexan en 0 (el primer elemento de la lista de variaciones es 0, el siguiente es 1, etc.).</td> 
  </tr>
 </tbody> 
</table>

#### Transcribir medios

Este módulo transcribe audio o vídeo.



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe Firefly, consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con Adobe Firefly</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de transcripción</td> 
   <td>Seleccione si desea transcribir audio o vídeo.   </td> 
  </tr>
  <tr> 
   <td role="rowheader">URL con prefijo</td> 
   <td>Introduzca o asigne la dirección URL firmada previamente que el módulo utilizará para la entrada.   </td> 
  </tr>
  <tr> 
  </tr>
   <td role="rowheader">Tipo de medio </td> 
   <td>Seleccionar el tipo de medio del archivo de entrada</td> 
  </tr>
  <tr> 
   <td role="rowheader">Códigos de configuración regional de Target</td> 
   <td>Para cada código de configuración regional que desee agregar, haga clic en <b>Agregar elemento</b> y seleccione el código de configuración regional que represente el idioma que desea utilizar en el resultado.</td> 
  <tr> 
   <td role="rowheader">Formato de rótulo</td> 
   <td>Escriba <code>SRT</code> para incluir subtítulos, o déjelo en blanco si no desea subtítulos.</td> 
  </tr>
 </tbody> 
</table>



