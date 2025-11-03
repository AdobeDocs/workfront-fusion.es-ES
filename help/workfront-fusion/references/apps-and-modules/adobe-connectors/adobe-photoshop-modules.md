---
title: Módulos de Adobe Photoshop
description: Con los módulos de Adobe Photoshop, puede iniciar un escenario de Adobe Workfront Fusion basado en los eventos de su cuenta de Adobe Photoshop, crear, leer o actualizar acuerdos y otros registros, buscar registros utilizando los criterios definidos y cargar documentos.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 0e41d1af-af69-4f9b-a5b3-479562254084
source-git-commit: d4bdc4005a3b7b22d64adc8ca1d20bcf534ddfd1
workflow-type: tm+mt
source-wordcount: '5398'
ht-degree: 83%

---

# Módulos de [!DNL Adobe Photoshop]

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!DNL Adobe Photoshop], así como conectarlo a varias aplicaciones y servicios de terceros.


Si necesita instrucciones sobre cómo crear un escenario, vea los artículos en [Crear un escenario: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

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

Antes de poder usar el conector de [!DNL Adobe Photoshop], debe asegurarse de que se cumplen los siguientes requisitos previos:

* Debe tener una cuenta de [!DNL Adobe Photoshop] activa.
* Debe tener una licencia de Firefly Services.
* Debe tener un ID de cliente y un Secreto de cliente. Puede adquirirlos en Adobe Developer Console.

## Información de API de Adobe Photoshop

El conector de Adobe Photoshop utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Dirección URL base</td> 
   <td>https://image.adobe.io/pie/psdService</td> 
  </tr>
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.12.31</td> 
  </tr>
 </tbody> 
 </table>

## Crear una conexión a [!DNL Adobe Photoshop]

Para crear una conexión para los módulos de [!DNL Adobe Photoshop]:

1. En cualquier módulo, haga clic en **[!UICONTROL Agregar]** junto al cuadro Conexión.

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
          <p>Seleccione si desea utilizar una conexión JWT o una conexión servidor a servidor.</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>Introduzca un nombre para esta conexión.</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Introduzca el [!UICONTROL Adobe] [!UICONTROL Client ID]. Esto se puede encontrar en la sección de detalles de [!UICONTROL Credentials] del [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Escriba su [!UICONTROL Client Secret] de [!DNL Adobe]. Esto se puede encontrar en la sección de detalles de [!UICONTROL Credentials] del [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Technical account ID]</td>
        <td>Si utiliza una conexión JWT, escriba su [!DNL Adobe] ID de cuenta técnica de [!UICONTROL]. Esto se puede encontrar en la sección de detalles de [!UICONTROL Credentials] del [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Organization ID]</td>
        <td>Si utiliza una conexión JWT, escriba su [!DNL Adobe] [!UICONTROL Organization ID]. Esto se puede encontrar en la sección de detalles de [!UICONTROL Credentials] del [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Private key]</td>
        <td>
          <p>Si está usando una conexión JWT, escriba la clave privada que se generó cuando se crearon sus credenciales en [!DNL Adobe Developer Console]. </p>
          <p>Para extraer la clave privada o el certificado:</p>
          <ol>
            <li value="1">
              <p>Haga clic en <b>[!UICONTROL Extract]</b>.</p>
            </li>
            <li value="2">
              <p>Seleccione el tipo de archivo que va a extraer.</p>
            </li>
            <li value="3">
              <p>Seleccione el archivo que contiene la clave privada o el certificado.</p>
            </li>
            <li value="4">
              <p>Introduzca la contraseña del archivo.</p>
            </li>
            <li value="5">
              <p>Haga clic en <b>Guardar</b> para extraer el archivo y volver a la configuración de conexión.</p>
            </li>
          </ol>
        </td>
        </tr>
      </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.

## Módulos de [!DNL Adobe Photoshop] y sus campos

Al configurar módulos de [!DNL Adobe Photoshop], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL Adobe Photoshop] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Aplicar ediciones de PSD](#apply-psd-edits)
* [Corregir automáticamente el color de una imagen](#auto-color-correct-an-image)
* [Convertir formato de imagen](#convert-image-format)
* [Crear una máscara](#create-a-mask)
* [Crear un nuevo PSD](#create-a-new-psd)
* [Editar capas de texto](#edit-text-layers)
* [Edición de capas de texto (heredadas)](#edit-text-layers-legacy)
* [Ejecutar un JSON de acción](#execute-an-action-json)
* [Ejecutar desenfoque de la profundidad](#execute-depth-blur)
* [Ejecutar acciones de Photoshop](#execute-photoshop-actions)
* [Ejecutar recorte de producto](#execute-product-crop)
* [Obtener información de capa](#get-layer-info)
* [Realizar una llamada de API personalizada](#make-a-custom-api-call)
* [Quitar el fondo](#remove-background)
* [Reemplazar un objeto inteligente](#replace-a-smart-object)
* [Reemplazar un objeto inteligente (heredado)](#replace-a-smart-object-legacy)
* [Cambiar el tamaño de una imagen](#resize-an-image)
* [Aplicar una marca de agua a una imagen](#watermark-an-image)

### Aplicar ediciones de PSD

Este módulo de acción aplica una variedad de ediciones a nivel de documento y capa.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivo donde se almacena el archivo que desea editar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo que desea editar. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options &gt; Document &gt; Image size) Height]</p>
      </td>
      <td> Introduzca o asigne la altura de la imagen en píxeles. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options &gt; Document &gt; Image size) Width]</p>
      </td>
      <td> Introduzca o asigne la anchura de la imagen en píxeles. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options &gt; Document &gt; Canvas size) Top]</p>
      </td>
   <td> Escriba o asigne, en píxeles, la coordenada y de la esquina superior izquierda del documento. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options &gt; Document &gt; Canvas size) Bottom]</p>
      </td>
   <td> Escriba o asigne, en píxeles, la coordenada y de la esquina inferior derecha del documento. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options &gt; Document &gt; Canvas size) Left]</p>
      </td>
   <td> Escriba o asigne, en píxeles, la coordenada x de la esquina superior izquierda del documento. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options &gt; Document &gt; Canvas size) Right]</p>
      </td>
   <td> Escriba o asigne, en píxeles, la coordenada x de la esquina inferior derecha del documento. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options &gt; Document) Trim]</p>
      </td>
   <td> Seleccione Píxeles transparentes para basar el recorte en píxeles transparentes de la imagen. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Default font]</p>
      </td>
   <td> Introduzca el nombre completo del PostScript de la fuente que se vaya a utilizar como valor predeterminado global para el documento. Esta fuente se utilizará para cualquier capa de texto a la que le falte una fuente y no se haya proporcionado específicamente ninguna otra fuente para esa capa. Si falta esa fuente, la opción que se haya especificado en Administrar fuentes que faltan es la que se aplicará. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Fonts]</p>
      </td>
   <td> Para cada fuente que necesite el documento, haga clic en Agregar elemento e introduzca la ubicación de almacenamiento y la ubicación de archivo de la fuente. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Manage missing fonts]</p>
      </td>
   <td> Seleccione la acción que debe realizarse si en el documento faltan una o más fuentes. <ul><li><code>fail</code>: el trabajo no se realizará correctamente y el estado se establecerá en fallido; los detalles del error se proporcionarán en la sección de detalles del estado.</li><li><code>useDefault</code>: el trabajo se realizará correctamente y todas las fuentes que faltan se reemplazarán con ArialMT.</li></ul></td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Layers]</p>
      </td>
   <td> Para cada capa que desee añadir, haga clic en Añadir elemento y rellene los detalles de la capa. <p>Para obtener más información sobre las opciones de capa, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/modifyDocumentAsync">Aplicar ediciones de PSD</a> en la documentación de Adobe Photoshop.  </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>Para cada archivo editado que desee crear, haga clic en Agregar elemento e introduzca el almacenamiento, la ubicación y el tipo como se indica en esta tabla.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde desea almacenar el nuevo archivo.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta donde se almacenará el nuevo archivo. Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Type]</p>
      </td>
   <td>Seleccione el tipo de archivo al que desea convertir el archivo. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado ha de sobrescribir cualquier archivo de salida que ya exista. Esto solo se aplica a los archivos en el almacenamiento de Adobe.</p>
      </td>
    </tr>
        <tr>
      <td role="rowheader">
        <p>[!UICONTROL (salida) Recortar a lienzo]</p>
      </td>
   <td>Seleccione si las representaciones deben ser de tamaño Lienzo. True recorta las representaciones al tamaño Lienzo, mientras que False hace que las representaciones tengan el tamaño Tamaño</td> 
    </tr>
    </tbody>
</table>

### Corregir automáticamente el color de una imagen

El color automático de este módulo de acción corrige la imagen especificada.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde se almacena el archivo con el color correcto.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo cuyo color desea corregir. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde desea almacenar el nuevo archivo.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta donde se almacenará el nuevo archivo. Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Type]</p>
      </td>
   <td>Seleccione el tipo de archivo al que desea convertir el archivo. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado ha de sobrescribir cualquier archivo de salida que ya exista. Esto solo se aplica a los archivos en el almacenamiento de Adobe.</p>
      </td>
    </tr>
    </tbody>
</table>

### Convertir formato de imagen

Este módulo de acción convierte un archivo en JPEG, PNG, PSD o TIFF.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que se almacena el archivo del que desea quitar el fondo.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo del que desea quitar el fondo. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>Para cada archivo convertido que desee crear, haga clic en Añadir elemento e introduzca el almacenamiento, la ubicación y el tipo como se indica en esta tabla.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde desea almacenar el nuevo archivo.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta donde se almacenará el nuevo archivo. Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Type]</p>
      </td>
   <td>Seleccione el tipo de archivo al que desea convertir el archivo. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado ha de sobrescribir cualquier archivo de salida que ya exista. Esto solo se aplica a los archivos en el almacenamiento de Adobe.</p>
      </td>
    </tr>
    </tbody>
</table>

### Crear una máscara

Este módulo de acción devuelve un archivo PNG con una máscara aplicada alrededor del asunto.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos desde el que se almacena el archivo del que desea crear una máscara.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Escriba o asigne la dirección URL o la ruta de acceso del archivo del que desea crear una máscara. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde desea almacenar el archivo de máscara.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta de acceso donde se almacenará el archivo de máscara. Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista. Esto solo se aplica a los archivos en el almacenamiento de Adobe.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Color space]</p>
      </td>
   <td>Seleccione si la imagen de salida utiliza RGB o color RGBA. </td> 
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Mask format]</p>
      </td>
   <td>Seleccione si la máscara debe ser suave (con calado) o binaria. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Optimize]</p>
      </td>
   <td>Seleccione Rendimiento para optimizar la velocidad o Lote para permitir el tiempo de espera. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Post process]</p>
      </td>
   <td>Seleccione si desea habilitar el posprocesamiento.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Version]</p>
      </td>
   <td>El valor predeterminado es 4.0</td> 
    </tr> 
    </tbody>
</table>

### Crear un nuevo PSD

Este módulo de acción crea un nuevo PSD con capas opcionales y genera representaciones o las guarda como un PSD.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options &gt; Document &gt; Image size) Height]</p>
      </td>
      <td> Introduzca o asigne la altura de la imagen en píxeles. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options &gt; Document &gt; Image size) Width]</p>
      </td>
      <td> Introduzca o asigne la anchura de la imagen en píxeles. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Resolución de [!UICONTROL (Opciones &gt; Documento)]</p>
      </td>
   <td> Especifique o asigne la resolución de la imagen en píxeles por pulgada. Debe estar entre 72 y 300. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Opciones &gt; Documento) Modo]</p>
      </td>
   <td> Seleccione el modo de la imagen. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Opciones &gt; Documento) Fill]</p>
      </td>
   <td> Seleccione si desea que el relleno de la capa de fondo sea transparente, blanco o el color de fondo de la imagen. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Opciones &gt; Documento) Profundidad]</p>
      </td>
   <td> Seleccione la profundidad de bits de la imagen. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Layers]</p>
      </td>
   <td> Para cada capa que desee añadir, haga clic en Añadir elemento y rellene los detalles de la capa. <p>Para obtener más información sobre las opciones de capa, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/createDocumentAsync">Crear PSD</a> en la documentación de Adobe Photoshop.  </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Opciones) Fuente global]</p>
      </td>
   <td> Introduzca el nombre completo del PostScript de la fuente que se vaya a utilizar como valor predeterminado global para el documento. Esta fuente se utilizará para cualquier capa de texto a la que le falte una fuente y no se haya proporcionado específicamente ninguna otra fuente para esa capa. Si falta esa fuente, la opción que se haya especificado en Administrar fuentes que faltan es la que se aplicará. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Fonts]</p>
      </td>
   <td> Para cada fuente que necesite el documento, haga clic en Agregar elemento e introduzca la ubicación de almacenamiento y la ubicación de archivo de la fuente. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Manage missing fonts]</p>
      </td>
   <td> Seleccione la acción que debe realizarse si en el documento faltan una o más fuentes. <ul><li><code>fail</code>: el trabajo no se realizará correctamente y el estado se establecerá en fallido; los detalles del error se proporcionarán en la sección de detalles del estado.</li><li><code>useDefault</code>: el trabajo se realizará correctamente y todas las fuentes que faltan se reemplazarán con ArialMT.</li></ul></td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>Para cada archivo que desee crear, haga clic en Agregar elemento e introduzca el almacenamiento, la ubicación y el tipo que se muestran en esta tabla.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde desea almacenar el nuevo archivo.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta donde se almacenará el nuevo archivo. Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Type]</p>
      </td>
   <td>Seleccione el tipo de archivo al que desea convertir el archivo. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Salida) Otros campos]</td>
      <td>
        <p><p>Para obtener más información sobre las opciones de salida, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/createDocumentAsync">Crear PSD</a> en la documentación de Adobe Photoshop.  </p>
      </td>
    </tr>
    </tbody>
</table>

### Editar capas de texto

Este módulo de acción edita las capas de texto en un archivo Photoshop. Puede introducir detalles de edición independientes para varias capas en el mismo archivo.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], vea <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Input file storage]</td>
      <td>
        <p>Seleccione el servicio de archivo donde se almacena el archivo que desea editar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Input file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo que desea editar. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Manage missing fonts]</td>
      <td>
        <p>Seleccione la acción que debe realizarse si en el documento faltan una o más fuentes. Si no se proporciona la fuente, el módulo utilizará la fuente predeterminada.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Default font]  </td>
      <td>
        <p>Introduzca el nombre completo del PostScript de la fuente que se vaya a utilizar como valor predeterminado global para el documento. Esta fuente se utilizará para cualquier capa de texto a la que le falte una fuente y no se haya proporcionado específicamente ninguna otra fuente para esa capa. Si falta esa fuente, la opción que se haya especificado en Administrar fuentes que faltan es la que se aplicará.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Fonts]</p>
      </td>
   <td> Introduzca la ubicación de almacenamiento y la ubicación del archivo de la fuente. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Layers]</td>
   <td> <p>Para cada capa de texto que desee editar, haga clic en <b>Agregar elemento</b> e introduzca las opciones de capa.<p>Para obtener detalles sobre las opciones de capa, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/editTextLayerAsync">Editar texto</a> en la documentación de Adobe Photoshop.</p>  </td>     </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que desea almacenar el archivo editado.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta de acceso donde se desea almacenar el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Type]</p>
      </td>
   <td> Seleccione el tipo de archivo para el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista.</p>
      </td>
    </tr>
  </tbody>
</table>

### Edición de capas de texto (heredadas)

Este módulo de acción edita una capa de texto en un archivo Photoshop.

Para editar varias capas, use el módulo [Editar capas de texto](#edit-text-layers).

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], vea <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Input file storage]</td>
      <td>
        <p>Seleccione el servicio de archivo donde se almacena el archivo que desea editar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Input file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo que desea editar. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Manage missing fonts]</td>
      <td>
        <p>Seleccione la acción que debe realizarse si en el documento faltan una o más fuentes. Si no se proporciona la fuente, el módulo utilizará la fuente predeterminada.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Default font]  </td>
      <td>
        <p>Introduzca el nombre completo del PostScript de la fuente que se vaya a utilizar como valor predeterminado global para el documento. Esta fuente se utilizará para cualquier capa de texto a la que le falte una fuente y no se haya proporcionado específicamente ninguna otra fuente para esa capa. Si falta esa fuente, la opción que se haya especificado en Administrar fuentes que faltan es la que se aplicará.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Fonts]</p>
      </td>
   <td> Introduzca la ubicación de almacenamiento y la ubicación del archivo de la fuente. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Layers]</td>
   <td> <p>Para obtener detalles sobre las opciones de capa, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/editTextLayerAsync">Editar capa de texto</a> en la documentación de Adobe Photoshop.</p>  </td>     </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Output file storage]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que desea almacenar el archivo editado.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que desea almacenar el archivo editado.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta de acceso donde se desea almacenar el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Type]</p>
      </td>
   <td> Seleccione el tipo de archivo para el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista.</p>
      </td>
    </tr>
  </tbody>
</table>


### Ejecutar un JSON de acción

Este módulo de acción ejecuta acciones de Photoshop mediante comandos JSON.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivo donde se almacena el archivo que desea editar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo que desea editar. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Action JSON]</td>
      <td>
        <p>Introduzca el comando JSON para la acción que desea realizar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Fonts / Patterns / Brushes / Additional images]</td>
      <td>
        <p>Para cada fuente, patrón, pincel o imagen adicional que desee utilizar en esta acción, haga clic en Agregar elemento e introduzca el almacenamiento y la ubicación de archivo del elemento.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Font / Pattern / Brush file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo que desea utilizar. </td> 
    </tr>
    <tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>Para cada archivo que desee crear, haga clic en Agregar elemento e introduzca las opciones de almacenamiento, ubicación, tipo y sobrescritura que se indican en esta tabla.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Salidas) Almacenamiento]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que desea almacenar el archivo editado.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Salidas) Archivo URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta de acceso donde se desea almacenar el archivo editado.  Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Salidas) Tipo]</p>
      </td>
   <td> Seleccione el tipo de archivo para el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Salidas) Sobrescribir]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista.</p>
      </td>
    </tr>
      </tbody>
</table>

### Ejecutar desenfoque de la profundidad

Este módulo de acción ejecuta el desenfoque de la profundidad en el archivo seleccionado.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], vea <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Input file storage]</td>
      <td>
        <p>Seleccione el servicio de archivo donde se almacena el archivo que desea editar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Input file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo que desea editar. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Salidas) Almacenamiento]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que desea almacenar el archivo editado.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Salidas) Archivo URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta de acceso donde se desea almacenar el archivo editado.  Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Salidas) Tipo]</p>
      </td>
   <td> Seleccione el tipo de archivo para el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Salidas) Sobrescribir]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista.</p>
      </td>
    </tr>
   <tr>
      <td role="rowheader">[!UICONTROL Other fields]</td>
      <td>
        <p>Para obtener más información sobre otras opciones de desenfoque de la profundidad, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/applyDepthBlurAsync">Ejecutar desenfoque de la profundidad </a> en la documentación de la API de Adobe Photoshop.</p>
      </td>
    </tr>
  </tbody>
</table>

### Ejecutar acciones de Photoshop

Este módulo de acción ejecuta una acción de Photoshop en la imagen seleccionada.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], vea <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Input file storage]</td>
      <td>
        <p>Seleccione el servicio de archivo donde se almacena el archivo que desea editar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Input file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo que desea editar. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Actions file storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde se almacena el archivo de acciones.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Actions file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo de acciones. </td> 
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Action name]</p>
      </td>
   <td> Si solo desea ejecutar una acción concreta, puede especificar la acción que se debe reproducir desde ActionSet. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Font / Pattern / Brush storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde se almacena el archivo que desea utilizar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Font / Pattern / Brush file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo que desea utilizar. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Salidas) Almacenamiento]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que desea almacenar el archivo editado.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Salidas) Archivo URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta de acceso donde se desea almacenar el archivo editado.  Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Salidas) Tipo]</p>
      </td>
   <td> Seleccione el tipo de archivo para el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Salidas) Sobrescribir]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista.</p>
      </td>
    </tr>
   <tr>
      <td role="rowheader">[!UICONTROL Other fields]</td>
      <td>
        <p>Para obtener más información sobre otras opciones de desenfoque de la profundidad, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/applyDepthBlurAsync">Ejecutar desenfoque de la profundidad </a> en la documentación de la API de Adobe Photoshop.</p>
      </td>
    </tr>
  </tbody>
</table>

### Ejecutar recorte de producto

Este módulo de acción ejecuta el recorte de productos en la imagen seleccionada.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], vea <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Input file storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde almacenar el archivo que desea recortar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Input file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo que desea recortar. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Unit]</p>
      </td>
   <td> Seleccione si desea describir el ajuste de altura y anchura en píxeles o como un porcentaje. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Width]</p>
      </td>
   <td> Introduzca o asigne la cantidad de relleno de anchura que desea añadir. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Height]</p>
      </td>
   <td> Introduzca o asigne la cantidad de relleno de altura que desea añadir. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Salidas) Almacenamiento]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que desea almacenar el archivo editado.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Salidas) Archivo URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta de acceso donde se desea almacenar el archivo editado.  Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Salidas) Tipo]</p>
      </td>
   <td> Seleccione el tipo de archivo para el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Salidas) Sobrescribir]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista.</p>
      </td>
    </tr>
   <tr>
      <td role="rowheader">[!UICONTROL Other fields]</td>
      <td>
        <p>Para obtener más información sobre otras opciones de desenfoque de la profundidad, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/applyDepthBlurAsync">Ejecutar desenfoque de la profundidad </a> en la documentación de la API de Adobe Photoshop.</p>
      </td>
    </tr>
  </tbody>
</table>

### Obtener información de capa

Este módulo de acción recupera información de capa del archivo de PSD especificado.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], vea <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Input file storage]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que se almacena el archivo del que desea recuperar información de capa.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Input file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo del que desea recuperar información de capa. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Thumbnails]</p>
      </td>
   <td> Seleccione el tipo de archivo que desea que tengan las miniaturas. Las miniaturas son pequeñas previsualizaciones para cualquier capa procesable.</td> 
    </tr>
  </tbody>
</table>

### Realizar una llamada de API personalizada

Este módulo de acción realiza una llamada personalizada a la API de Photoshop.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre la creación de una conexión a [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión a [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p>Introduzca una ruta relativa a <code>https://image.adobe.io/pie/psdService</code>. Ejemplo: <code>/photoshopActions</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
      </td>
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p>
        <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion añade encabezados de autorización automáticamente.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Query String]  </td>
      <td>
        <p>Introduzca la cadena de consulta de la solicitud.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Body]</td>
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su archivo JSON, coloque las comillas fuera de la instrucción condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>

### Quitar el fondo

Este módulo de acción identifica el asunto principal de la imagen y elimina el fondo.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que se almacena el archivo del que desea quitar el fondo.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo del que desea quitar el fondo. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde desea almacenar el nuevo archivo.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta donde se almacenará el nuevo archivo.  Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista. Esto solo se aplica a los archivos en el almacenamiento de Adobe.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Color space]</p>
      </td>
   <td>Seleccione si la imagen de salida utiliza RGB o color RGBA. </td> 
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Mask format]</p>
      </td>
   <td>Seleccione si los bordes de la imagen deben ser suaves (calados) o binarios. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Optimize]</p>
      </td>
   <td>Seleccione Rendimiento para optimizar la velocidad o Lote para permitir el tiempo de espera. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Post process]</p>
      </td>
   <td>Seleccione si desea habilitar el posprocesamiento.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Version]</p>
      </td>
   <td>El valor predeterminado es 4.0</td> 
    </tr> 
    </tbody>
</table>

### Reemplazar un objeto inteligente

Este módulo de acción sustituye un objeto inteligente en una capa de PSD y genera nuevas representaciones.

Este módulo utiliza la versión 2 de la API de objetos inteligentes.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde se almacena el objeto inteligente.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del objeto inteligente. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Layers]</p>
      </td>
   <td>Para cada capa que desee añadir al objeto inteligente, haga clic en Añadir elemento e introduzca el nombre o ID del objeto, el servicio de archivos donde se almacena el objeto inteligente y la dirección URL o la ruta de la capa.<p>Para obtener descripciones de la configuración avanzada en esta área, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/replaceSmartObjectAsync">Reemplazar un objeto inteligente</a> en la documentación de la API de Photoshop </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Cambiar tamaño de imagen durante la ubicación]</p>
      </td>
   <td> Seleccione si desea cambiar el tamaño de la imagen.</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>Para cada nueva representación que desee que produzca el módulo, haga clic en Añadir elemento y rellene los campos siguientes. Se pueden tener un máximo de 25 archivos de salida.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde desea almacenar el nuevo archivo.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta donde se almacenará el nuevo archivo.  Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Salidas) Tipo]</p>
      </td>
   <td> Seleccione el tipo de archivo para el archivo editado. </td> 
    </tr>
     </tbody>
</table>

### Reemplazar un objeto inteligente (heredado)

Este módulo de acción sustituye un objeto inteligente en una capa de PSD y genera nuevas representaciones.

Este módulo utiliza la versión heredada de los objetos inteligentes.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde se almacena el objeto inteligente.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del objeto inteligente. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Layers]</p>
      </td>
   <td>Para cada capa que desee añadir al objeto inteligente, haga clic en Añadir elemento e introduzca el nombre o ID del objeto, el servicio de archivos donde se almacena el objeto inteligente y la dirección URL o la ruta de la capa.<p>Para obtener descripciones de la configuración avanzada en esta área, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/replaceSmartObjectAsync">Reemplazar un objeto inteligente</a> en la documentación de la API de Photoshop </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>Para cada nueva representación que desee que produzca el módulo, haga clic en Añadir elemento y rellene los campos siguientes. Se pueden tener un máximo de 25 archivos de salida.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde desea almacenar el nuevo archivo.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta donde se almacenará el nuevo archivo.  Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Width]</p>
      </td>
   <td> La anchura, en píxeles, del archivo de salida. El módulo conservará la relación de aspecto original. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado ha de sobrescribir cualquier archivo de salida que ya exista. Esto solo se aplica a los archivos en el almacenamiento de Adobe.</p>
      </td>
    </tbody>
</table>

### Cambiar el tamaño de una imagen

Esta acción cambia el tamaño de una imagen con la misma relación de aspecto.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], vea <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde se almacena el archivo cuyo tamaño desea cambiar.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo cuyo tamaño desea cambiar.  Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>Para cada archivo convertido que desee crear, haga clic en Añadir elemento e introduzca las opciones de almacenamiento, ubicación u otras opciones según se enumeran en esta tabla.</p>
      </td>
    </tr>
    <tr>
    <tr>
      <td role="rowheader">[!UICONTROL Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde desea almacenar el nuevo archivo.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta donde se almacenará el nuevo archivo.  Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Width]</p>
      </td>
   <td> La anchura, en píxeles, del archivo de salida. El módulo conservará la relación de aspecto original. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Max width]</p>
      </td>
   <td>Cuando la anchura es 0, se puede proporcionar el valor máximo para obtener el tamaño. La anchura máxima tiene prioridad porque es más pequeña que la anchura del documento.</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista. Esto solo se aplica a los archivos en el almacenamiento de Adobe.</p>
      </td>
    </tr>
        <tr>
      <td role="rowheader">
        <p>[!UICONTROL Trim to canvas]</p>
      </td>
   <td>Seleccione Sí para recortar las representaciones al tamaño de lienzo o No para que su tamaño sea de capa.</td> 
    </tr>
    </tbody>
</table>

### Aplicar una marca de agua a una imagen

Este módulo de acción añade una marca de agua a la imagen seleccionada.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">Almacenamiento de [!UICONTROL (Base &gt; Entrada)]</td>
      <td>
        <p>Seleccione el servicio de archivos donde se almacena el archivo al que quiera añadir una marca de agua.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Base &gt; Entrada) Ubicación del archivo]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo al que quiera añadir una marca de agua. </td> 
    </tr>
    <tr>
      <td role="rowheader">Almacenamiento de [!UICONTROL (filigrana &gt; entrada)]</td>
      <td>
        <p>Seleccione el servicio de archivos donde se almacene la marca de agua que se quiera añadir.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">Almacenamiento de [!UICONTROL (filigrana &gt; entrada)]</td>
      <td>
        <p>Seleccione el servicio de archivos donde se almacene la marca de agua que se quiera añadir.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Marca de agua &gt; Límites) Altura]</p>
      </td>
   <td>Introduzca o asigne la altura deseada de la marca de agua en píxeles.</td> 
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Marca de agua &gt; Límites) Anchura]</p>
      </td>
   <td> Especifique o asigne el ancho deseado de la marca de agua en píxeles. </td> 
    </tr>  
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Marca de agua &gt; Límites) Izquierda]</p>
      </td>
   <td> Especifique o asigne la distancia en píxeles desde el lado izquierdo de la imagen a la que debería estar la marca de agua.</td> 
    </tr>  
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Marca de agua &gt; Límites) Superior]</p>
      </td>
   <td> Especifique o asigne la distancia en píxeles desde la parte superior de la imagen a la que debería estar la marca de agua.</td> 
    </tr>  
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde quiera almacenar el archivo de marca de agua.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Escriba o asigne la dirección URL o ruta donde se almacenará el archivo de marca de agua. Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Type]</p>
      </td>
   <td>Seleccione el tipo de archivo al que desea convertir el archivo. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Width]</p>
      </td>
   <td> La anchura, en píxeles, del archivo de salida. El módulo conservará la relación de aspecto original. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado ha de sobrescribir cualquier archivo de salida que ya exista. Esto solo se aplica a los archivos en el almacenamiento de Adobe.</p>
      </td>
    </tbody>
</table>
