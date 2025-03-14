---
title: Módulos de Adobe Firefly
description: En un escenario de  [!DNL Adobe Workfront Fusion] , puede automatizar los flujos de trabajo que utilizan  [!DNL Adobe Firefly], así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 3b29ba3d-a769-4e97-b2c2-0b4eeed5b029
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '2432'
ht-degree: 19%

---

# Módulos de [!DNL Adobe Firefly]

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!DNL Adobe Firefly], así como conectarlo a varias aplicaciones y servicios de terceros.

Si necesita instrucciones sobre cómo crear un escenario, vea los artículos en [Crear un escenario: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront</td> 
   <td> <p>Cualquiera</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencia de Adobe Workfront</td> 
   <td> <p>Nuevo: estándar</p><p>O</p><p>Actual: Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion**</td> 
   <td>
   <p>Actual: No se requiere licencia de Workfront Fusion</p>
   <p>O</p>
   <p>Heredado: Workfront Fusion para la automatización e integración del trabajo </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Seleccione o paquete de Prime Workfront: su organización debe adquirir Adobe Workfront Fusion.</li><li>Paquete de Ultimate Workfront: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe adquirir Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

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
        <td>Introduzca su [!DNL Adobe] [!UICONTROL Client Secret].  Esto se puede encontrar en la sección de detalles de [!UICONTROL Credentials] de [!DNL Adobe Developer Console].</td>
        </tr>
      </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.

## Módulos de [!DNL Adobe Firefly] y sus campos

Al configurar módulos de [!DNL Adobe Firefly], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Adobe Firefly] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

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
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Campaign], consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con [!DNL Adobe Firefly]</a> en este artículo.</td> 
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
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Campaign], consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con [!DNL Adobe Firefly]</a> en este artículo.</td> 
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

## Generar una imagen

Este módulo de acción genera una imagen basada en una solicitud proporcionada. También puede proporcionar una imagen de referencia opcional, y la imagen generada coincidirá con el estilo de la imagen de referencia.

Este módulo funciona con la API de Firefly V3 asincrónica. La versión anterior de este módulo ha quedado obsoleta y se eliminará en un futuro próximo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Campaign], consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con [!DNL Adobe Firefly]</a> en este artículo.</td> 
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
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Campaign], consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con [!DNL Adobe Firefly]</a> en este artículo.</td> 
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

### Generación de imágenes similares

Este módulo de acción genera imágenes similares a la imagen de origen especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Campaign], consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión con [!DNL Adobe Firefly]</a> en este artículo.</td> 
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


### Realizar una llamada de API personalizada

Este módulo de acción realiza una llamada personalizada a la API de Firefly.

Para ver las API disponibles específicas, consulte [API de Adobe Firefly](https://developer.adobe.com/firefly-services/docs/firefly-api/) en la documentación de Adobe Developer.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre la creación de una conexión a [!DNL Adobe Firefly], consulte <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Crear una conexión a [!DNL Adobe Firefly]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p>Escriba una ruta relativa a <code>https://firefly-api.adobe.io/</code>.</p>
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
      <td role="rowheader">[!UICONTROL Body]</td>
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la instrucción condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>

