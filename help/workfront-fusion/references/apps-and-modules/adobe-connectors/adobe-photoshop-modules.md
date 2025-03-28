---
title: Módulos de Adobe Photoshop
description: Con los módulos de Adobe Photoshop, puede iniciar un escenario de Adobe Workfront Fusion basado en los eventos de su cuenta de Adobe Photoshop, crear, leer o actualizar acuerdos y otros registros, buscar registros utilizando los criterios definidos y cargar documentos.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 0e41d1af-af69-4f9b-a5b3-479562254084
source-git-commit: db1d6f5bf29063b069681395c6ff6d3554c67dc3
workflow-type: tm+mt
source-wordcount: '4359'
ht-degree: 96%

---

# Módulos de [!DNL Adobe Photoshop]

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!DNL Adobe Photoshop], así como conectarlo a varias aplicaciones y servicios de terceros.


Si necesita instrucciones sobre cómo crear un escenario, vea los artículos en [Crear un escenario: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

## Requisitos de acceso

+++**Amplíe para ver los requisitos de acceso para la funcionalidad de este artículo.**

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] plan*</td>
      <td>
        <p>[!UICONTROL Pro] o superior</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] licencia*</td>
      <td>
        <p>[!UICONTROL Plan], [!UICONTROL Work]</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront Fusion] licencia**</td>
      <td >
        <p>[!UICONTROL Workfront Fusion for Work Automation and Integration]</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">Producto</td>
      <td>Su organización debe comprar [!DNL Adobe Workfront Fusion] así como [!DNL Adobe Workfront] para usar la funcionalidad que se describe en este artículo.</td>
    </tr>
    </tr>
  </tbody>
</table>


&#42;Para saber qué plan, tipo de licencia o acceso tiene, póngase en contacto con el administrador de [!DNL Workfront].

&#42;&#42;Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [!DNL [Adobe Workfront Fusion] licenses](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

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
   <td role="rowheader">URL básica</td> 
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
        <td>Introduzca su [!DNL Adobe] [!UICONTROL Technical account ID]. Esto se puede encontrar en la sección de detalles de [!UICONTROL Credentials] del [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Organization ID]</td>
        <td>Escriba su [!UICONTROL Organization ID] de [!DNL Adobe]. Esto se puede encontrar en la sección de detalles de [!UICONTROL Credentials] del [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Private key]</td>
        <td>
          <p>Introduzca la clave privada que se generó cuando se crearon sus credenciales en [!DNL Adobe Developer Console]. </p>
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

Al configurar módulos de [!DNL Adobe Photoshop], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Adobe Photoshop] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Aplicar ediciones de PSD](#apply-psd-edits)
* [Corregir automáticamente el color de una imagen](#auto-color-correct-an-image)
* [Convertir formato de imagen](#convert-image-format)
* [Crear una máscara](#create-a-mask)
* [Crear un nuevo PSD](#create-a-new-psd)
* [Editar capas de texto](#edit-text-layers)
* [Ejecutar desenfoque de la profundidad](#execute-depth-blur)
* [Ejecutar acciones de Photoshop](#execute-photoshop-actions)
* [Ejecutar acciones de Photoshop (JSON)](#execute-photoshop-actions-json)
* [Ejecutar recorte de producto](#execute-product-crop)
* [Obtener información de capa](#get-layer-info)
* [Realizar una llamada de API personalizada](#make-a-custom-api-call)
* [Quitar el fondo](#remove-background)
* [Reemplazar un objeto inteligente](#replace-a-smart-object)
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
   <td> Seleccione la acción que debe realizarse si en el documento faltan una o más fuentes. <ul><li><code>fail</code>: el trabajo no se realizará correctamente y el estado se establecerá en fallido; los detalles del error se proporcionarán en la sección de detalles del estado.</li><li><code>useDefault</code>: el trabajo se realizará correctamente; sin embargo, de forma predeterminada, todas las fuentes que falten se reemplazarán con ArialMT.</li></ul></td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Layers]</p>
      </td>
   <td> Para cada capa que desee añadir, haga clic en Añadir elemento y rellene los detalles de la capa. <p>Para obtener más información sobre las opciones de capa, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/photoshop_applyPsdEdits/">Aplicar ediciones de PSD</a> en la documentación de Adobe Photoshop.  </td> 
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
        <p>[!UICONTROL Maximum number of returned results]</p>
      </td>
   <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td> 
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
        <tr>
      <td role="rowheader">
        <p>[!UICONTROL Maximum number of returned results]</p>
      </td>
   <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td> 
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
        <tr>
      <td role="rowheader">
        <p>[!UICONTROL Maximum number of returned results]</p>
      </td>
   <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td> 
    </tr>
    </tbody>
</table>



### Crear una máscara

Este módulo de acción devuelve un archivo PNG con un más aplicado alrededor del asunto.

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
   <td></td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Version]</p>
      </td>
   <td>El valor predeterminado es 4.0</td> 
    </tr> 
        <tr>
      <td role="rowheader">
        <p>[!UICONTROL Maximum number of returned results]</p>
      </td>
   <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td> 
    </tr>
    </tbody>
</table>

### Crear un nuevo PSD

Este módulo de acción crea un nuevo PSD con capas opcionales y genera representaciones o las guarda como un PSD.

Para ver los campos relacionados con este módulo, consulte [Crear un nuevo PSD](https://developer.adobe.com/photoshop/photoshop-api-docs/api/#tag/Photoshop/operation/documentCreate) en la documentación de Adobe Photoshop.

### Editar capas de texto

Este módulo de acción edita las capas de texto en un archivo Photoshop.

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
      <td role="rowheader">[!UICONTROL Layers]</td>
   <td> <p>Para obtener detalles sobre las opciones de capa, consulte <a href="https://developer.adobe.com/photoshop/photoshop-api-docs/api/#tag/Photoshop/operation/text">Editar capa de texto</a> en la documentación de Adobe Photoshop.</p>  </td>     </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Output file storage]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que desea almacenar el archivo editado.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Output file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta de acceso donde se desea almacenar el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Output file type]</p>
      </td>
   <td> Seleccione el tipo de archivo para el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Compression]</p>
      </td>
   <td> Seleccione el nivel de compresión del archivo de salida. </td> 
    </tr>
  </tbody>
</table>



### Ejecutar acciones de Photoshop (JSON)

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
      <td role="rowheader">[!UICONTROL Outputs file storage]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que desea almacenar el archivo editado.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Output file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta de acceso donde se desea almacenar el archivo editado.  Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Output file type]</p>
      </td>
   <td> Seleccione el tipo de archivo para el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Compression]</p>
      </td>
   <td> Seleccione el nivel de compresión del archivo de salida. </td> 
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
        <p>Seleccione el servicio de archivos donde desea almacenar el nuevo archivo.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta donde se almacenará el nuevo archivo. </td> 
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
        <p>[!UICONTROL Maximum number of returned results]</p>
      </td>
   <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td> 
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
      <td role="rowheader">[!UICONTROL Output file storage]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que desea almacenar el archivo editado.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Output file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta de acceso donde se desea almacenar el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Output file type]</p>
      </td>
   <td> Seleccione el tipo de archivo para el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Other fields]</td>
      <td>
        <p>Para obtener más información sobre otras opciones de desenfoque de la profundidad, consulte <a href="https://developer.adobe.com/photoshop/photoshop-api-docs/api/#tag/Photoshop/operation/depthBlur">Ejecutar desenfoque de la profundidad </a> en la documentación de la API de Adobe Photoshop.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Compression]</p>
      </td>
   <td> Seleccione el nivel de compresión del archivo de salida. </td> 
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
      <td role="rowheader">[!UICONTROL Output file storage]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que desea almacenar el archivo editado.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Output file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta de acceso donde se desea almacenar el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Output file type]</p>
      </td>
   <td> Seleccione el tipo de archivo para el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Compression]</p>
      </td>
   <td> Seleccione el nivel de compresión del archivo de salida. </td> 
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
      <td role="rowheader">[!UICONTROL Output file storage]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que desea almacenar el archivo editado.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Output file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta de acceso donde se desea almacenar el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Output file type]</p>
      </td>
   <td> Seleccione el tipo de archivo para el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Compression]</p>
      </td>
   <td> Seleccione el nivel de compresión del archivo de salida. </td> 
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
   <td> </td> 
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
        <p>[!DNL Workfront Fusion] añade encabezados de autorización automáticamente.</p>
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
   <td></td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Version]</p>
      </td>
   <td>El valor predeterminado es 4.0</td> 
    </tr> 
        <tr>
      <td role="rowheader">
        <p>[!UICONTROL Maximum number of returned results]</p>
      </td>
   <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td> 
    </tr>
    </tbody>
</table>



### Reemplazar un objeto inteligente

Este módulo de acción sustituye un objeto inteligente en una capa de PSD y genera nuevas representaciones.

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
   <td>Para cada capa que desee añadir al objeto inteligente, haga clic en Añadir elemento e introduzca el nombre o ID del objeto, el servicio de archivos donde se almacena el objeto inteligente y la dirección URL o la ruta de la capa.<p>Para obtener descripciones de la configuración avanzada de esta área, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/photoshop_replaceSmartObject/">Reemplazar un objeto inteligente</a> en la documentación de la API de Photoshop </td> 
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
    </tr>
        <tr>
      <td role="rowheader">
        <p>[!UICONTROL Maximum number of returned results]</p>
      </td>
   <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td> 
    </tr>
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
      <td role="rowheader">
        <p>[!UICONTROL Type]</p>
      </td>
   <td>Seleccione el tipo de archivo al que desea convertir el archivo. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Width]</p>
      </td>
   <td>Introduzca un número que represente la anchura, en píxeles, de la imagen cuyo tamaño se ha cambiado. Se conservará la relación de aspecto.</td> 
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
      <td>Para obtener instrucciones sobre cómo crear conexiones con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Creación de conexiones con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Base / Input) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde se almacena el archivo al que quiera añadir una marca de agua.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Base / Input) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo al que quiera añadir una marca de agua. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Watermark / Input) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde se almacene la marca de agua que se quiera añadir.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Watermark / Input) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde se almacene la marca de agua que se quiera añadir.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Watermark / Bounds) Height]</p>
      </td>
   <td>Introduzca o asigne la altura deseada de la marca de agua en píxeles.</td> 
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Watermark / Bounds) Width]</p>
      </td>
   <td> Especifique o asigne el ancho deseado de la marca de agua en píxeles. </td> 
    </tr>  
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Watermark / Bounds) Left]</p>
      </td>
   <td> Especifique o asigne la distancia en píxeles desde el lado izquierdo de la imagen a la que debería estar la marca de agua.</td> 
    </tr>  
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Watermark / Bounds) Top]</p>
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
    </tr>
        <tr>
      <td role="rowheader">
        <p>[!UICONTROL Maximum number of returned results]</p>
      </td>
   <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td> 
    </tr>
    </tbody>
</table>
