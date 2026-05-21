---
title: Módulos de Adobe Firefly
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan  [!DNL Adobe Firefly], así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 3b29ba3d-a769-4e97-b2c2-0b4eeed5b029
TQID: https://experienceleague.adobe.com/1hI4NuUl2eEAgWyXRKLHQ3-6MM9-2tFyujGbRfHSBmU
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: b58ad82f-df6b-4b01-81a3-3a02ab9567a0
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 3886
ht-degree: 17%

---

# Módulos de [!DNL Adobe Firefly]

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!DNL Adobe Firefly], así como conectarlo a varias aplicaciones y servicios de terceros.

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

Antes de poder usar el conector de [!DNL Adobe Firefly], debe asegurarse de que se cumplen los siguientes requisitos previos:

* Debe tener una cuenta de [!DNL Adobe Firefly] activa.

## Información de API de Adobe Firefly

El conector de Adobe Firefly utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.4.24</td> 
  </tr>
 </tbody> 
 </table>

## Crear una conexión a [!DNL Adobe Firefly]

Para crear una conexión para los módulos de [!DNL Adobe Firefly]:

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
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>Seleccione si desea conectarse a un entorno de producción o de no producción.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>Seleccione si desea conectarse a una cuenta de servicio o a una personal.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Introduzca el [!UICONTROL Adobe] [!UICONTROL Client ID]. Esto se puede encontrar en la sección de detalles de [!UICONTROL Credentials] de [!DNL Adobe Developer Console].</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Introduzca su [!DNL Adobe] [!UICONTROL Client Secret]. Esto se puede encontrar en la sección de detalles de [!UICONTROL Credentials] de [!DNL Adobe Developer Console].</td>
        </tr>
      </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.

## Módulos de [!DNL Adobe Firefly] y sus campos

Al configurar módulos de [!DNL Adobe Firefly], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL Adobe Firefly] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, consulte [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Expandir una imagen

Este módulo de acción expande una imagen, de forma opcional con contenido de una solicitud proporcionada.

Este módulo funciona con la API de Firefly V3 asincrónica. La versión anterior de este módulo ha quedado obsoleta y se eliminará en un futuro próximo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Firefly], consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con [!DNL Adobe Firefly]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Prompt]</td> 
   <td>Introduzca o asigne un mensaje para el contenido con el que desea expandir la imagen. Si no se proporciona ningún mensaje, la imagen se expandirá con contenido que coincida con la imagen original.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Número de variaciones]</td> 
   <td>Escriba un número entre 1 y 4. El módulo generará este número de variaciones de imagen expandidas.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source]</td> 
   <td>Seleccione cómo va a proporcionar el archivo de origen:<ul><li><p><b>Archivo</b></p><p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre del archivo de imagen de referencia del archivo de origen y el archivo de imagen de referencia.</p></li><li><p><b>URL con prefijo</b></p><p>Introduzca o asigne la dirección URL de la imagen de origen.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Formato de imagen expandido]</td> 
   <td>Seleccione el formato de archivo con el que se guardará la imagen expandida.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expandir por]</td> 
   <td>  <p>Seleccione si desea expandir la imagen mediante la colocación de la imagen o mediante una máscara.</p> 
   <ul>
   <li><b>Ubicación</b><p>Introduzca la alineación horizontal y vertical, y el margen de la imagen colocada desde los bordes.</p></li>
   <li><b>Máscara</b><p>Seleccione el archivo de origen de la máscara y si ésta debe invertirse.</p></li>
   </ul>
</td> 
</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tamaño]</td> 
   <td>Seleccione la altura y anchura que desea que tenga la imagen expandida.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Semillas]</td> 
   <td>Para cada imagen que genere el módulo, haga clic en <b>Agregar elemento</b> y escriba o asigne un entero. Puede utilizar esta misma semilla en otro módulo Expandir una imagen para generar una imagen similar con estilos diferentes. El número de semillas que añada debe ser igual al campo Number of variaciones.</td> 
  </tr> 
 </tbody> 
</table>

### Expandir una imagen (obsoleta)

Este módulo ha quedado obsoleto y se eliminará en un futuro próximo. En su lugar, utilice el módulo Expandir una imagen.

### Rellenar una imagen

Este módulo de acción rellena el área enmascarada de una imagen, opcionalmente con contenido de una solicitud proporcionada.

Este módulo funciona con la API de Firefly V3 asincrónica. La versión anterior de este módulo ha quedado obsoleta y se eliminará en un futuro próximo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Firefly], consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con [!DNL Adobe Firefly]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Imagen &gt; Source]</td> 
   <td>Seleccione cómo va a proporcionar el archivo de origen de imagen:<ul><li><p><b>Archivo</b></p><p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre del archivo de imagen de referencia del archivo de origen y el archivo de imagen de referencia.</p></li><li><p><b>URL con prefijo</b></p><p>Introduzca o asigne la dirección URL de la imagen de origen.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mask &gt; Source]</td> 
   <td>Seleccione cómo va a proporcionar el archivo de origen de máscara:<ul><li><p><b>Archivo</b></p><p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre del archivo de imagen de referencia del archivo de origen y el archivo de imagen de referencia.</p></li><li><p><b>URL con prefijo</b></p><p>Introduzca o asigne la dirección URL de la imagen de origen.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Prompt]</td> 
   <td>Introduzca o asigne un mensaje para el contenido con el que desea rellenar la imagen. Si no se proporciona ningún mensaje, la imagen se rellenará con contenido que coincida con la imagen original.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Número de variaciones]</td> 
   <td>Escriba un número entre 1 y 4. El módulo generará este número de variaciones de imágenes rellenadas.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Formato de imagen rellena]</td> 
   <td>Seleccione el formato de archivo con el que se guardará la imagen rellenada.</td> 
  </tr> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Semillas]</td> 
   <td>Para cada imagen que genere el módulo, haga clic en <b>Agregar elemento</b> y escriba o asigne un entero. Puede utilizar esta misma semilla en otro módulo Expandir una imagen para generar una imagen similar con estilos diferentes. El número de semillas que añada debe ser igual al campo Number of variaciones.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tamaño]</td> 
   <td>Seleccione el tamaño que desea que tenga la imagen rellena.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Locale]</td> 
   <td>Si se proporciona una configuración regional, el módulo genera contenido más relevante para la configuración regional especificada. <p>La configuración regional debe proporcionarse en el código de idioma ISO 639-1 y en la región ISO 3166-1.</p><p> Ejemplo: <code>en-US</code></p></td> 
  </tr> 
 </tbody> 
</table>

### Rellenar una imagen (obsoleto)

Este módulo ha quedado obsoleto y se eliminará en un futuro próximo. En su lugar, utilice el módulo Fill an image.

### Generar compuesto adaptable

Este módulo de acción compone una imagen de asunto sin problemas en una imagen de fondo en una ubicación enmascarada. Puede controlar la intensidad con la que se aplican las sombras, cómo se armonizan la iluminación y el color del objeto con el fondo y si los detalles del fondo original se conservan dentro del área enmascarada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Firefly], consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con [!DNL Adobe Firefly]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fondo &gt; Imagen &gt; Source]</td> 
   <td>Seleccione cómo va a proporcionar la imagen de fondo. La imagen de fondo es la escena de destino donde se compondrá el objeto.<ul><li><p><b>Cargar imagen</b></p><p>Cargue la imagen de fondo o asigne el archivo de imagen de un módulo anterior.</p></li><li><p><b>URL de imagen</b></p><p>Introduzca o asigne la dirección URL de la imagen de fondo.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fondo &gt; Máscara de área de relleno &gt; Source]</td> 
   <td>Seleccione cómo va a proporcionar la máscara de área de relleno. La máscara de área de relleno indica el área del fondo donde se colocará el objeto.<ul><li><p><b>Cargar imagen</b></p><p>Cargue la imagen de máscara de área de relleno o asigne el archivo de imagen desde un módulo anterior.</p></li><li><p><b>URL de imagen</b></p><p>Escriba o asigne la dirección URL de la imagen de máscara de área de relleno.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Objeto &gt; Imagen &gt; Source]</td> 
   <td>Seleccione cómo va a proporcionar la imagen del objeto. La imagen del objeto es la imagen de origen del objeto que se va a componer en el fondo.<ul><li><p><b>Cargar imagen</b></p><p>Cargue la imagen del objeto o asigne el archivo de imagen de un módulo anterior.</p></li><li><p><b>URL de imagen</b></p><p>Introduzca o asigne la dirección URL de la imagen del objeto.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Objeto &gt; Máscara &gt; Source]</td> 
   <td>Seleccione cómo va a proporcionar la máscara de objeto. La máscara de objeto es la máscara de segmentación del objeto.<ul><li><p><b>Cargar imagen</b></p><p>Cargue la imagen de máscara de objeto o asigne el archivo de imagen de un módulo anterior.</p></li><li><p><b>URL de imagen</b></p><p>Introduzca o asigne la dirección URL de la imagen de máscara de objeto.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Número de variaciones]</td> 
   <td>Escriba un número entre 1 y 3. El módulo genera este número de variaciones compuestas.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Semillas]*</td> 
   <td>Haga clic en <b>Agregar elemento</b> para agregar un valor semilla y, a continuación, escriba o asigne un entero. Utilice una semilla por variación. El recuento de valores semilla debe coincidir con el valor de [!UICONTROL Número de variaciones] si se proporcionan ambos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Armonización]*</td> 
   <td>Escriba un número entre 0 y 1 para controlar cuánto se ajustan los colores y la iluminación del objeto para que coincidan con el fondo. <code>0.0</code> aplica una armonización mínima y <code>1.0</code> aplica una armonización máxima.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Intensidad de sombreado]*</td> 
   <td>Introduzca un número entre 0 y 1 para controlar la intensidad de la sombra en el resultado compuesto. Los valores más bajos reducen la sombra.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Conservar fondo]*</td> 
   <td>Seleccione si desea conservar los detalles de fondo originales dentro del área enmascarada durante la composición. <ul><li><b>Sí</b><p>Los detalles del fondo original dentro del área enmascarada se conservan durante la composición.</p></li><li><b>No</b><p>Los detalles del fondo original dentro del área enmascarada no se conservan durante la composición.</p></li><li><b>No definido</b><p>Utilice el comportamiento predeterminado para esta opción.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Salida &gt; Tipo de medio]*</td> 
   <td>Seleccione el formato de archivo con el que se guardará el compuesto generado.</td> 
  </tr> 
 </tbody> 
</table>

* Estos campos son campos avanzados y no se muestran a menos que seleccione **[!UICONTROL Mostrar configuración avanzada]**.

### Generar una imagen

Este módulo de acción genera una imagen basada en una solicitud proporcionada. También puede proporcionar una imagen de referencia opcional, y la imagen generada coincidirá con el estilo de la imagen de referencia.

Este módulo funciona con la API de Firefly V3 asincrónica. La versión anterior de este módulo ha quedado obsoleta y se eliminará en un futuro próximo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Firefly], consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con [!DNL Adobe Firefly]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Prompt]</td> 
   <td>Introduzca o asigne un mensaje para la imagen que desea generar. Más detalles en la solicitud le permitirá tener más control sobre lo que aparece en la imagen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Versión de modelo]</td> 
   <td>Seleccione la versión del modelo de Firefly que desee utilizar para generar la imagen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Número de variaciones]</td> 
   <td>Escriba un número entre 1 y 4. El módulo generará este número de variaciones de imagen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Formato de imagen generado]</td> 
   <td>Seleccione el formato de archivo con el que se guardará la imagen expandida. Si selecciona predeterminado, el formato de archivo será JPEG si no se proporciona ninguna imagen de referencia. Si se proporciona una imagen de referencia, el formato de archivo de la imagen generada será el mismo que la imagen de referencia.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Estructura &gt; Referencia de imagen]</td> 
    <td>Seleccione cómo va a proporcionar el archivo de origen para la estructura de la nueva imagen:<ul><li><p><b>Archivo</b></p><p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre del archivo de imagen de referencia del archivo de origen y el archivo de imagen de referencia.</p></li><li><p><b>URL con prefijo</b></p><p>Introduzca o asigne la dirección URL de la imagen de origen.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Estructura &gt; Intensidad]</td> 
    <td>Introduzca un número entre 0 y 100 para controlar la rigurosidad con la que Firefly sigue la estructura de la imagen de origen. Los números más altos significan que Firefly sigue la imagen más estrictamente.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Style &gt; Referencia de imagen]</td> 
    <td>Seleccione cómo va a proporcionar el archivo de origen para el estilo de la nueva imagen:<ul><li><p><b>Archivo</b></p><p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre del archivo de imagen de referencia del archivo de origen y el archivo de imagen de referencia.</p></li><li><p><b>URL con prefijo</b></p><p>Introduzca o asigne la dirección URL de la imagen de origen.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Estructura &gt; Intensidad]</td> 
    <td>Introduzca un número entre 0 y 100 para controlar la rigurosidad con la que Firefly sigue el estilo de la imagen de origen. Los números más altos significan que Firefly sigue la imagen más estrictamente.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Style &gt; Ajustes preestablecidos]</td> 
   <td>Si desea utilizar un estilo preestablecido, haga clic en Agregar elemento y escriba o asigne el estilo que desea utilizar.<p>Para obtener una lista de estilos preestablecidos, consulte <a href="https://developer.adobe.com/firefly-services/docs/firefly-api/guides/concepts/style-presets//" >Estilos de modelo de imagen</a> en la documentación para desarrolladores de Adobe.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mensaje negativo]</td> 
   <td>Introduzca o asigne las palabras que desea evitar en el contenido generado. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Clase de contenido]</td> 
   <td>Seleccione si desea que la imagen generada sea más similar a una foto o más similar al arte creado. <ul><li><b>Fotografía</b><p>Introduzca valores para la apertura, la velocidad de obturación (en segundos) y el campo de visión (en milímetros).</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Semilla]</td> 
   <td>Para cada imagen que genere el módulo, haga clic en <b>Agregar elemento</b> y escriba o asigne un entero. Puede utilizar esta misma semilla en otro módulo Expandir una imagen para generar una imagen similar con estilos diferentes. El número de semillas que añada debe ser igual al campo Number of variaciones.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tamaño]</td> 
   <td>Seleccione el tamaño que desea que tenga la imagen generada.</td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Intensidad visual]</td> 
   <td>Escriba o asigne un entero que represente la intensidad general de las características visuales existentes de la fotografía. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Locale]</td> 
   <td>Si se proporciona una configuración regional, el módulo genera contenido más relevante para la configuración regional especificada. <p>La configuración regional debe proporcionarse en el código de idioma ISO 639-1 y en la región ISO 3166-1.</p><p> Ejemplo: <code>en-US</code></p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mosaico]</td> 
   <td>Active esta opción para generar una imagen que se pueda repetir infinitamente en todas las direcciones.</td> 
  </tr> 
 </tbody> 
</table>

### Generar una imagen (en desuso)

Este módulo ha quedado obsoleto y se eliminará en un futuro próximo. En su lugar, utilice el módulo Generar una imagen.

### Generación de un compuesto de objeto

Este módulo de acción combina imágenes generadas por Firefly para crear una composición de imagen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Firefly], consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con [!DNL Adobe Firefly]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Prompt]</td> 
   <td>Introduzca o asigne un mensaje para la imagen que desea generar. Más detalles en la solicitud le permitirá tener más control sobre lo que aparece en la imagen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Número de variaciones]</td> 
   <td>Escriba un número entre 1 y 4. El módulo generará este número de variaciones de imagen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Clase de contenido]</td> 
   <td>Seleccione si desea que la imagen generada sea más similar a una foto o al arte.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Imagen &gt; Source]</td> 
    <td>Seleccione cómo va a proporcionar el archivo de origen para la estructura de la nueva imagen:<ul><li><p><b>Archivo</b></p><p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre del archivo de imagen de referencia del archivo de origen y el archivo de imagen de referencia.</p></li><li><p><b>URL con prefijo</b></p><p>Introduzca o asigne la dirección URL de la imagen de origen.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Formato de imagen generado]</td> 
   <td>Seleccione el formato de archivo con el que se guardará la imagen expandida. Si selecciona predeterminado, el formato de archivo será JPEG si no se proporciona ninguna imagen de referencia. Si se proporciona una imagen de referencia, el formato de archivo de la imagen generada será el mismo que la imagen de referencia.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Style &gt; Referencia de imagen]</td> 
    <td>Seleccione cómo va a proporcionar el archivo de origen para el estilo de la nueva imagen:<ul><li><p><b>Archivo</b></p><p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre del archivo de imagen de referencia del archivo de origen y el archivo de imagen de referencia.</p></li><li><p><b>URL con prefijo</b></p><p>Introduzca o asigne la dirección URL de la imagen de origen.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Estructura &gt; Intensidad]</td> 
    <td>Introduzca un número entre 0 y 100 para controlar la rigurosidad con la que Firefly sigue el estilo de la imagen de origen. Los números más altos significan que Firefly sigue la imagen más estrictamente.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Style &gt; Ajustes preestablecidos]</td> 
   <td>Si desea utilizar un estilo preestablecido, haga clic en Agregar elemento y escriba o asigne el estilo que desea utilizar.<p>Para obtener una lista de estilos preestablecidos, consulte <a href="https://developer.adobe.com/firefly-services/docs/firefly-api/guides/concepts/style-presets//" >Estilos de modelo de imagen</a> en la documentación para desarrolladores de Adobe.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tamaño]</td> 
   <td>Seleccione el tamaño que desea que tenga el compuesto generado. </td> 
  </tr> 
 </tbody> 
</table>

### Generación de imágenes con Image5

Este módulo de acción genera una imagen mediante el modelo [!DNL Adobe Firefly] Image5. Proporcione un mensaje de texto y, opcionalmente, una imagen de referencia para guiar la generación.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Firefly], consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con [!DNL Adobe Firefly]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Prompt]</td> 
   <td>Introduzca o asigne una descripción de la imagen que desea generar. El mensaje debe tener entre 1 y 1500 caracteres. Más detalles en el mensaje le permite tener más control sobre lo que aparece en la imagen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Proporción de aspecto]</td> 
   <td>Seleccione la forma de la imagen generada. Si se proporciona una imagen de referencia, seleccione <b>Automático</b>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resolución]</td> 
   <td>Seleccione la resolución de la imagen generada. Las resoluciones más altas tardan más en generarse.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Imagen de referencia]</td> 
   <td>Opcionalmente, proporcione una imagen de referencia para guiar la generación. Haga clic en <b>Agregar elemento</b> y proporcione la imagen. Cuando use una imagen de referencia, establezca [!UICONTROL Proporción de aspecto] en <b>Automático</b>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Semilla]*</td> 
   <td>Haga clic en <b>Agregar elemento</b> y escriba o asigne un entero para reproducir un resultado de generación específico. Déjelo en blanco para generar un resultado aleatorio.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Motivo del mensaje]*</td> 
   <td>Seleccione la estrategia de razonamiento rápido utilizada durante la generación.<ul><li><p><b>Calidad: genera la descripción de la imagen</b></p><p>Genera una descripción de imagen en la salida del módulo.</p></li><li><p><b>Velocidad: generación más rápida, sin descripción</b></p><p>Genera la imagen más rápido, pero deja vacía la descripción de la imagen.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Configuración regional]*</td> 
   <td>Introduzca o asigne un código de idioma y región para adaptar el contenido generado a un país e idioma específicos. <p>La configuración regional debe proporcionarse en el código de idioma ISO 639-1 y en la región ISO 3166-1.</p><p>Ejemplo: <code>en-US</code></p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Número de variaciones]*</td> 
   <td>Introduzca el número de imágenes que desea generar por solicitud. Actualmente, solo se admite 1. Para generar varias imágenes, envíe solicitudes independientes.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Modelo]*</td> 
   <td>Seleccione el modelo [!DNL Firefly] que desee usar para generar la imagen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Introduzca o asigne el número máximo de resultados con los que desea que funcione el módulo durante un ciclo de ejecución.</td> 
  </tr> 
 </tbody> 
</table>

*Estos campos son avanzados y no se muestran a menos que seleccione **[!UICONTROL Mostrar configuración avanzada]**.

### Generación de composiciones precisas

Este módulo de acción coloca un sujeto en la región enmascarada de una imagen de fondo y aplica una armonización generativa para que el sujeto se mezcle naturalmente con el fondo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Firefly], consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con [!DNL Adobe Firefly]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fondo &gt; Imagen &gt; Source]</td> 
   <td>Seleccione cómo va a proporcionar la imagen de fondo. La imagen de fondo es la escena de destino donde se compondrá el objeto.<ul><li><p><b>Cargar imagen</b></p><p>Cargue la imagen de fondo o asigne el archivo de imagen de un módulo anterior.</p></li><li><p><b>URL de imagen</b></p><p>Introduzca o asigne la dirección URL de la imagen de fondo.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fondo &gt; Máscara de área de relleno &gt; Source]</td> 
   <td>Seleccione cómo va a proporcionar la máscara de área de relleno. La máscara de área de relleno indica el área del fondo donde se colocará el objeto.<ul><li><p><b>Cargar imagen</b></p><p>Cargue la imagen de máscara de área de relleno o asigne el archivo de imagen desde un módulo anterior.</p></li><li><p><b>URL de imagen</b></p><p>Escriba o asigne la dirección URL de la imagen de máscara de área de relleno.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Objeto &gt; Imagen &gt; Source]</td> 
   <td>Seleccione cómo va a proporcionar la imagen del objeto. La imagen del objeto es la imagen de origen del objeto que se va a componer en el fondo.<ul><li><p><b>Cargar imagen</b></p><p>Cargue la imagen del objeto o asigne el archivo de imagen de un módulo anterior.</p></li><li><p><b>URL de imagen</b></p><p>Introduzca o asigne la dirección URL de la imagen del objeto.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Número de variaciones]</td> 
   <td>Escriba un número entre 1 y 3. El módulo genera este número de variaciones compuestas.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Semillas]*</td> 
   <td>Haga clic en <b>Agregar elemento</b> para agregar un valor semilla y, a continuación, escriba o asigne un entero. Utilice una semilla por variación. El recuento de valores semilla debe coincidir con el valor de [!UICONTROL Número de variaciones] si se proporcionan ambos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Blend]*</td> 
   <td>Introduzca un número entre 0 y 1 para controlar la mezcla entre el aspecto armonizado y el original del objeto. <code>0.0</code> aplica la armonización completa y <code>1.0</code> conserva el aspecto del objeto original.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Salida &gt; Tipo de medio]*</td> 
   <td>Seleccione el formato de archivo con el que se guardará el compuesto generado.</td> 
  </tr> 
 </tbody> 
</table>

* Estos campos son campos avanzados y no se muestran a menos que seleccione **[!UICONTROL Mostrar configuración avanzada]**.

### Generación de imágenes similares

Este módulo de acción genera imágenes similares a la imagen de origen especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Firefly], consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con [!DNL Adobe Firefly]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Número de variaciones]</td> 
   <td>Escriba un número entre 1 y 4. El módulo generará este número de variaciones de imagen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Versión de modelo]</td> 
   <td>Seleccione la versión del modelo de Firefly que desee utilizar para generar las imágenes.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Formato de imagen generado]</td> 
   <td>Seleccione el formato de archivo con el que se guardará la imagen expandida. Si selecciona predeterminado, el formato de archivo será JPEG si no se proporciona ninguna imagen de referencia. Si se proporciona una imagen de referencia, el formato de archivo de la imagen generada será el mismo que la imagen de referencia.</td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Imagen &gt; Source]</td> 
    <td>Seleccione cómo va a proporcionar el archivo de origen para la estructura de la nueva imagen:<ul><li><p><b>Archivo</b></p><p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre del archivo de imagen de referencia del archivo de origen y el archivo de imagen de referencia.</p></li><li><p><b>URL con prefijo</b></p><p>Introduzca o asigne la dirección URL de la imagen de origen.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Style &gt; Referencia de imagen]</td> 
    <td>Seleccione cómo va a proporcionar el archivo de origen para el estilo de la nueva imagen:<ul><li><p><b>Archivo</b></p><p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre del archivo de imagen de referencia del archivo de origen y el archivo de imagen de referencia.</p></li><li><p><b>URL con prefijo</b></p><p>Introduzca o asigne la dirección URL de la imagen de origen.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tamaño]</td> 
   <td>Seleccione el tamaño que desea que tenga el compuesto generado. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Semillas]</td> 
   <td>Para cada imagen que genere el módulo, haga clic en <b>Agregar elemento</b> y escriba o asigne un entero. Puede utilizar esta misma semilla en otro módulo Expandir una imagen para generar una imagen similar con estilos diferentes. El número de semillas que añada debe ser igual al campo Number of variaciones.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mosaico]</td> 
   <td>Active esta opción para generar una imagen que se pueda repetir infinitamente en todas las direcciones.</td> 
  </tr> 
 </tbody> 
</table>


### Generar vídeo

Este módulo de acción genera un vídeo a partir de un mensaje de texto. También puede proporcionar una o más imágenes de referencia para guiar la generación de vídeo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Firefly], consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con [!DNL Adobe Firefly]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Prompt]</td> 
   <td>Introduzca o asigne una descripción del vídeo que desea generar. Más detalles en el mensaje le permite tener más control sobre lo que aparece en el vídeo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Image &gt; Conditions]</td> 
   <td>Opcionalmente, se proporcionan una o más imágenes de referencia para guiar la generación de vídeo. Haga clic en <b>Agregar elemento</b> para cada imagen de referencia.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tamaños]</td> 
   <td>Haga clic en <b>Agregar elemento</b> e introduzca o asigne las dimensiones del vídeo generado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Factor de velocidad de bits]*</td> 
   <td>Escriba un número entre 0 y 63 para especificar el factor de velocidad de bits del vídeo generado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Configuración de vídeo &gt; Movimiento de cámara]*</td> 
   <td>Seleccione el movimiento de cámara que desee utilizar en el vídeo generado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Configuración de vídeo &gt; Estilo de mensaje]*</td> 
   <td>Seleccione el estilo de mensaje que desee utilizar para el vídeo generado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Configuración de vídeo &gt; Ángulo de toma]*</td> 
   <td>Seleccione el ángulo de toma que desee utilizar en el vídeo generado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Configuración de vídeo &gt; Tamaño de toma]*</td> 
   <td>Seleccione el tamaño de la toma que desee utilizar en el vídeo generado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Introduzca o asigne el número máximo de resultados con los que desea que funcione el módulo durante un ciclo de ejecución.</td> 
  </tr> 
 </tbody> 
</table>

* Estos campos son campos avanzados y no se muestran a menos que seleccione **[!UICONTROL Mostrar configuración avanzada]**.

### Realizar una llamada API personalizada

Este módulo de acción realiza una llamada personalizada a la API de Firefly.

Para ver las API disponibles específicas, consulte [API de Adobe Firefly](https://developer.adobe.com/firefly-services/docs/firefly-api/) en la documentación de Adobe Developer.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Firefly], consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con [!DNL Adobe Firefly]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p>Introduzca una ruta relativa a <code>https://firefly-api.adobe.io/</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
      </td>
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, consulte <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de petición HTTP</a>.</p> </td> 
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
      <td role="rowheader">[!UICONTROL Body]</td>
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>

