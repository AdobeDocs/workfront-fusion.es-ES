---
title: Servicios Adobe PDF
description: Servicios Adobe PDF
author: Becky
draft: Probably
feature: Workfront Fusion, Digital Content and Documents
exl-id: e6fbbc20-4315-4668-9e11-af7cfa82ae66
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '3623'
ht-degree: 80%

---

# [!DNL Adobe PDF Services]

Con [!DNL Adobe Workfront Fusion] [!DNL Adobe PDF Services], puede extraer datos de un archivo PDF o generar un nuevo archivo PDF a partir de los datos que proporcione. Además, puede convertir distintos tipos de archivo a PDF o de PDF a otros tipos de archivo. PDF Services también permite combinar, comprimir o leer metadatos de un archivo PDF, así como controlar la protección con contraseña del archivo.

Para obtener instrucciones sobre cómo crear un escenario, vea los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

Para obtener información sobre la API utilizada para PDF Services, consulte [Adobe Document Generation API](https://www.adobe.io/apis/documentcloud/dcsdk/doc-generation.html).

## Consideraciones de seguridad al usar [!DNL Adobe PDF Services]

[!DNL Adobe PDF Services] puede leer, convertir o modificar sus archivos, pero ni [!DNL Adobe] ni [!DNL Workfront Fusion] almacenan sus archivos o datos. Esto significa lo siguiente:

* Usted mantiene el control sobre sus archivos, incluyendo su seguridad
* No necesita tener una cuenta de almacenamiento o almacenamiento en la nube de [!UICONTROL Adobe] para usar los servicios de PDF.

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
   <p>Actual: no se requiere licencia de Workfront Fusion.</p>
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

Para crear una conexión de servidor a servidor OAuth, debe agregar la API de servicios de Adobe PDF a la consola de desarrolladores de Adobe. Al añadir la API, seleccione la opción OAuth de servidor a servidor.

Para obtener instrucciones, consulte [Añadir API al proyecto mediante OAuth](https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth/) en la documentación de Adobe developer.

## Información de API de servicios Adobe PDF

El conector de Adobe PDF Services utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL básica</td> 
   <td>https://pdf-services-stage.adobe.io</td> 
  </tr>
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 2.1.4</td> 
  </tr>
 </tbody> 
 </table>

## Crear una conexión a [!DNL Adobe PDF Services]

Para crear una conexión para los módulos de [!DNL Adobe PDF Services]:

1. En cualquier módulo de [!DNL Adobe PDF Services], haga clic en **[!UICONTROL Add]** junto al cuadro Conexión.

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
            <p>Seleccione si desea crear una conexión servidor a servidor o una conexión JWT.</p>
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
          <td>Escriba su [!DNL Adobe] [!UICONTROL Client ID]. Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].<p>Para obtener instrucciones sobre cómo localizar las credenciales, consulte <a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth/#credentials" class="MCXref xref" >Credentials</a> en la documentación de Adobe developer.</p></td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]</td>
          <td>Escriba su [!DNL Adobe] [!UICONTROL Client Secret]. Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].<p>Para obtener instrucciones sobre cómo localizar las credenciales, consulte <a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth/#credentials" class="MCXref xref" >Credentials</a> en la documentación de Adobe developer.</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Technical account ID] (solo JWT)</td>
          <td>Escriba su [!DNL Adobe] [!UICONTROL Technical account ID]. Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].<p>Para obtener instrucciones sobre cómo localizar las credenciales, consulte <a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth/#credentials" class="MCXref xref" >Credentials</a> en la documentación de Adobe developer.</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Organization ID] (solo JWT)</td>
          <td>Escriba su [!DNL Adobe] [!UICONTROL Organization ID]. Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].<p>Para obtener instrucciones sobre cómo localizar las credenciales, consulte <a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth/#credentials" class="MCXref xref" >Credentials</a> en la documentación de Adobe developer.</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Meta scopes] (solo JWT)</td>
          <td>
            Entre los meta ámbitos necesarios para la conexión.
          </td>
        </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Private key]</td>
        <td>
          <p>Si ha seleccionado una conexión JWT, introduzca la clave privada que se generó cuando se crearon sus credenciales en [!DNL Adobe Developer Console]. </p>
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
              <p>Haga clic en <b>[!UICONTROL Save]</b> para extraer el archivo y volver a la configuración de conexión.</p>
            </li>
          </ol>
        </td>
      </tr>
       </tbody>
    </table>
1. Haga clic en **[!UICONTROL Continue]** para guardar la conexión y volver al módulo.


## Módulos de [!DNL Adobe PDF Services] y sus campos

Al configurar [!DNL PDF Services], [!DNL Workfront Fusion] muestra los campos que se enumeran a continuación. Además, es posible que aparezcan otros campos en función de factores como el nivel de acceso a la aplicación o al servicio. Un título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [[!UICONTROL Combine PDF files]](#combine-pdf-files)
* [[!UICONTROL Compress PDF files]](#compress-pdf-files)
* [[!UICONTROL Convert document to PDF file]](#convert-document-to-pdf-file)
* [[!UICONTROL Convert HTML to PDF file]](#convert-html-to-pdf-file)
* [[!UICONTROL Convert image to PDF file]](#convert-image-to-pdf-file)
* [[!UICONTROL Convert PDF to document]](#convert-pdf-to-document)
* [[!UICONTROL Convert PDF to image]](#convert-pdf-to-image)
* [[!UICONTROL Extract Text / Table]](#extract-text--table)
* [[!UICONTROL Generate document]](#generate-document)
* [[!UICONTROL Linearize a PDF file]](#linearize-a-pdf-file)
* [Realizar una llamada de API personalizada](#make-a-custom-api-call)
* [[!UICONTROL OCR for PDF file]](#ocr-for-pdf-file)
* [[!UICONTROL Page manipulation]](#page-manipulation)
* [[!UICONTROL PDF accessibility auto-tag]](#pdf-accessibility-auto-tag)
* [[!UICONTROL PDF file properties]](#pdf-file-properties)
* [[!UICONTROL Protect PDF file]](#protect-pdf-file)
* [[!UICONTROL Remove protection of a PDF file]](#remove-protection-of-a-pdf-file)
* [División de un archivo PDF](#split-a-pdf-file)

### [!UICONTROL Combine PDF files]

Este módulo de acción toma varios archivos PDF y los combina en un solo archivo PDF. Por ejemplo, este módulo podría combinar todos los documentos de un proyecto de [!UICONTROL Workfront] en un solo PDF al finalizar el proyecto.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la conexión que usará en ese módulo.</p> Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe PDF Services], consulte <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Crear una conexión a [!DNL Adobe PDF Services]</a> en este artículo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Documents]</td> 
   <td> <p>Puede utilizar un módulo de agregador para recopilar documentos para combinarlos en un PDF o puede añadir los documentos manualmente. </p> <p>Se recomienda utilizar un módulo [!UICONTROL Array Aggregator] para agregar el resultado de un módulo anterior. Al utilizar un agregador, no es necesario conocer los nombres, ubicaciones o números de archivos que se van a combinar. Por lo tanto, el uso de un agregador es mucho más flexible y escalable que la introducción manual de los documentos que se van a combinar.</p> <p>Para usar el módulo de archivos de [!UICONTROL Combine PDF] con un agregador, debe habilitar la asignación en el campo [!UICONTROL Documents]. </p> <p>En este ejemplo, el módulo [!UICONTROL Read Related Records] identifica los documentos asociados con un proyecto y el módulo [!UICONTROL Download Documents] descarga cada uno de ellos. Todos los PDF se agregan a una matriz, que se pasa al módulo de archivos [!UICONTROL Combine PDF].</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/combine-example-350x104.png" style="width: 350;height: 104;"> </p> <p>También puede introducir documentos manualmente.</p> <p>Para que cada documento se incluya en el PDF combinado:</p> 
    <ol> 
     <li value="1"> <p>Haga clic [!UICONTROL Add a Document]</p> </li> 
     <li value="2"> <p>En el campo [!UICONTROL Source file], seleccione el módulo que genera el documento que desea incluir o asigne el nombre y los datos del archivo de origen. </p> </li> 
     <li value="3"> <p>(Opcional) Si desea incluir solo ciertas páginas del archivo de origen, para cada intervalo de páginas que desee agregar, haga clic en <strong>[!UICONTROL Add item]</strong> en el campo [!UICONTROL Pages], luego introduzca la primera y la última página del intervalo de páginas que desea incluir y haga clic en <strong>[!UICONTROL Add]</strong>. Puede incluir más de un intervalo de páginas de un solo documento.</p> </li> 
     <li value="4"> <p>Haga clic en <strong>[!UICONTROL Add]</strong>. </p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Compress PDF files]

Este módulo de acción toma un archivo de PDF y lo comprime. Esto puede resultar útil para conservar ancho de banda o memoria.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la conexión que usará en ese módulo.</p> Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe PDF Services], consulte <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Crear una conexión a [!DNL Adobe PDF Services]</a> en este artículo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> <p>El archivo de origen debe estar en formato PDF. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Compression level]</td> 
   <td>Seleccione el nivel de compresión que desee utilizar.</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Convert document to PDF file]

Esta herramienta convierte un documento en un archivo PDF. El archivo de origen debe tener uno de los siguientes formatos de documento:

* DOC
* XLS
* PPT
* TXT
* RTF

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la conexión que usará en ese módulo.</p> Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe PDF Services], consulte <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Crear una conexión a [!DNL Adobe PDF Services]</a> en este artículo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> <p>El archivo de origen debe tener uno de los siguientes formatos:</p> 
    <ul> 
     <li> <p>DOC</p> </li> 
     <li> <p>XLS</p> </li> 
     <li> <p>PPT</p> </li> 
     <li> <p>TXT</p> </li> 
     <li> <p>RTF</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Language]</td> 
   <td> <p>Seleccione el idioma predeterminado para el documento de origen. Esto permite al módulo seleccionar una fuente adecuada, si no se incluye en el archivo de origen.</p> <p>Seleccione entre los siguientes idiomas:</p> 
    <ul> 
     <li> <p>en-US (predeterminado): Inglés (Estados Unidos)</p> </li> 
     <li> <p>ca-ES: Catalán (España)</p> </li> 
     <li> <p>cs-CZ: Checo (República Checa)</p> </li> 
     <li> <p>da-DK: Danés (Dinamarca)</p> </li> 
     <li> <p>de-DE: Alemán (Alemania)</p> </li> 
     <li> <p>en-AE: Inglés (Emiratos Árabes Unidos)</p> </li> 
     <li> <p>en-GB: Inglés (Reino Unido)</p> </li> 
     <li> <p>en-IL: Inglés (Israel)</p> </li> 
     <li> <p>en-US: Inglés (Estados Unidos)</p> </li> 
     <li> <p>es-ES: Español (España)</p> </li> 
     <li> <p>es-MX: Español (México)</p> </li> 
     <li> <p>eu-ES: Vasco (España)</p> </li> 
     <li> <p>fi-FI: Finés (Finlandia)</p> </li> 
     <li> <p>fr-CA: Francés (Canadá)</p> </li> 
     <li> <p>fr-FR: Francés (Francia)</p> </li> 
     <li> <p>fr-MA: Francés (Marruecos)</p> </li> 
     <li> <p>hr-HR: Croata (Croacia)</p> </li> 
     <li> <p>hu-HU: Húngaro (Hungría)</p> </li> 
     <li> <p>it-IT: Italiano (Italia)</p> </li> 
     <li> <p>ja-JP: Japonés (Japón)</p> </li> 
     <li> <p>kr-KR: Coreano (Corea del Sur)</p> </li> 
     <li> <p>nb-NO: Noruego Bokmål (Noruega)</p> </li> 
     <li> <p>nl-NL: Neerlandés (Países Bajos)</p> </li> 
     <li> <p>pl-PL: Polaco (Polonia)</p> </li> 
     <li> <p>pt-BR: Portugués (Brasil)</p> </li> 
     <li> <p>pt-PT: Portugués (Portugal)</p> </li> 
     <li> <p>ro-RO: Rumano (Rumanía)</p> </li> 
     <li> <p>ru-RU: Ruso (Rusia)</p> </li> 
     <li> <p>sk-SK: Eslovaco (Eslovaquia)</p> </li> 
     <li> <p>sl-SI: Esloveno (Eslovenia)</p> </li> 
     <li> <p>sv-SE: Sueco (Suecia)</p> </li> 
     <li> <p>tr-TR: Turco (Turquía)</p> </li> 
     <li> <p>uk-UA: Ucraniano (Ucrania)</p> </li> 
     <li> <p>zh-CN: Chino (China continental)</p> </li> 
     <li> <p>zh-TW: Chino (Taiwán)</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Convert HTML to PDF file]

Esta herramienta convierte un archivo HTML a un archivo PDF.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la conexión que usará en ese módulo.</p> Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe PDF Services], consulte <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Crear una conexión a [!DNL Adobe PDF Services]</a> en este artículo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> <p>Importante: el archivo de origen debe estar en formato HTML o ZIP. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL JSON]</td> 
   <td> <p>Si el HTML hace referencia a variables de JavaScript, puede incluirlas aquí. </p> <p>Para cada variable, haga clic en <strong>[!UICONTROL Add item]</strong> e incluya la clave y el valor de la variable.</p> <p>Nota:   
     <ul> 
      <li> <p>Al crear un PDF a partir de un archivo ZIP, el material colateral de origen debe incluir un elemento de script como: <code> &lt;script src='./json.js' type='text/javascript'&gt;&lt;/script&gt;</code> </p> </li> 
      <li> <p>Al crear un PDF a partir de una dirección URL, el contenido de este objeto JSON se inserta en la máquina virtual del explorador antes de que se procese la página. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include header and footer]</td> 
   <td> <p>Active esta opción para crear encabezados y pies de página para el documento en PDF.</p> 
    <ul> 
     <li> <p>El encabezado incluye una fecha y el título del documento.</p> </li> 
     <li> <p>El pie de página incluye el nombre del archivo y un número de página.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Page width]</td> 
   <td>Escriba la anchura del papel, en pulgadas. El módulo utiliza esta información para dar formato a las páginas en el archivo PDF creado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Page height]</td> 
   <td>Escriba la altura del papel, en pulgadas. El módulo utiliza esta información para dar formato a las páginas en el archivo PDF creado.</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Convert image to PDF file]

Esta herramienta convierte una imagen en un archivo PDF.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la conexión que usará en ese módulo.</p> Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe PDF Services], consulte <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Crear una conexión a [!DNL Adobe PDF Services]</a> en este artículo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y el archivo de imagen del archivo de origen.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Convert PDF to document]

Esta herramienta convierte un archivo PDF en un documento. Puede seleccionar uno de los siguientes formatos para el archivo de salida.

* DOC
* DOCX
* PPTX
* XLSX
* RTF

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la conexión que usará en ese módulo.</p> Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe PDF Services], consulte <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Crear una conexión a [!DNL Adobe PDF Services]</a> en este artículo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> <p>El archivo de origen debe estar en formato PDF. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Files Format]</td> 
   <td> <p>Seleccione el formato de salida de los archivos:</p> 
    <ul> 
     <li> <p>DOC</p> </li> 
     <li> <p>DOCX</p> </li> 
     <li> <p>PPTX</p> </li> 
     <li> <p>XLSX</p> </li> 
     <li> <p>RTF</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Language]</td> 
   <td> <p>Seleccione el idioma predeterminado para el documento de origen. Esto permite al módulo seleccionar una fuente adecuada, si no se incluye en el archivo de origen.</p> <p>Seleccione entre los siguientes idiomas:</p> 
    <ul> 
     <li> <p>en-US (predeterminado): Inglés (Estados Unidos)</p> </li> 
     <li> <p>ca-ES: Catalán (España)</p> </li> 
     <li> <p>cs-CZ: Checo (República Checa)</p> </li> 
     <li> <p>da-DK: Danés (Dinamarca)</p> </li> 
     <li> <p>de-DE: Alemán (Alemania)</p> </li> 
     <li> <p>en-AE: Inglés (Emiratos Árabes Unidos)</p> </li> 
     <li> <p>en-GB: Inglés (Reino Unido)</p> </li> 
     <li> <p>en-IL: Inglés (Israel)</p> </li> 
     <li> <p>en-US: Inglés (Estados Unidos)</p> </li> 
     <li> <p>es-ES: Español (España)</p> </li> 
     <li> <p>es-MX: Español (México)</p> </li> 
     <li> <p>eu-ES: Vasco (España)</p> </li> 
     <li> <p>fi-FI: Finés (Finlandia)</p> </li> 
     <li> <p>fr-CA: Francés (Canadá)</p> </li> 
     <li> <p>fr-FR: Francés (Francia)</p> </li> 
     <li> <p>fr-MA: Francés (Marruecos)</p> </li> 
     <li> <p>hr-HR: Croata (Croacia)</p> </li> 
     <li> <p>hu-HU: Húngaro (Hungría)</p> </li> 
     <li> <p>it-IT: Italiano (Italia)</p> </li> 
     <li> <p>ja-JP: Japonés (Japón)</p> </li> 
     <li> <p>kr-KR: Coreano (Corea del Sur)</p> </li> 
     <li> <p>nb-NO: Noruego Bokmål (Noruega)</p> </li> 
     <li> <p>nl-NL: Neerlandés (Países Bajos)</p> </li> 
     <li> <p>pl-PL: Polaco (Polonia)</p> </li> 
     <li> <p>pt-BR: Portugués (Brasil)</p> </li> 
     <li> <p>pt-PT: Portugués (Portugal)</p> </li> 
     <li> <p>ro-RO: Rumano (Rumanía)</p> </li> 
     <li> <p>ru-RU: Ruso (Rusia)</p> </li> 
     <li> <p>sk-SK: Eslovaco (Eslovaquia)</p> </li> 
     <li> <p>sl-SI: Esloveno (Eslovenia)</p> </li> 
     <li> <p>sv-SE: Sueco (Suecia)</p> </li> 
     <li> <p>tr-TR: Turco (Turquía)</p> </li> 
     <li> <p>uk-UA: Ucraniano (Ucrania)</p> </li> 
     <li> <p>zh-CN: Chino (China continental)</p> </li> 
     <li> <p>zh-TW: Chino (Taiwán)</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Convert PDF to image]

Esta herramienta convierte un PDF en una imagen en formato PNG o JPEG., que luego se muestra como una lista o se combina en un ZIP.

Si se muestra como un ZIP, el PDF se convierte en una imagen por página y cada imagen termina con el número de página. A continuación, los archivos de imagen se combinan en un archivo ZIP.

Por ejemplo, un archivo denominado &quot;TestFile&quot; con 8 páginas produciría 8 imágenes, denominadas &quot;TestFile_1&quot; hasta &quot;TestFile_8&quot;. La salida del módulo es un archivo ZIP que contiene las 8 imágenes.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la conexión que usará en ese módulo.</p> Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe PDF Services], consulte <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Crear una conexión a [!DNL Adobe PDF Services]</a> en este artículo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> <p>El archivo de origen debe estar en formato PDF. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Files Format]</td> 
   <td> <p>Seleccione el formato de salida de los archivos:</p> 
    <ul> 
     <li>PNG</li> 
     <li>JPEG</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output type]</td> 
   <td> <p>Seleccione si desea que los archivos se muestren como una lista de archivos o como un archivo ZIP.</td> 
  </tr> 
  <tr> 
 </tbody> 
</table>

### [!UICONTROL Extract Text / Table]

Este módulo de acción le permite extraer datos de un archivo de PDF. El módulo genera elementos de texto individuales, como un párrafo o el texto en una sola celda de una tabla.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la conexión que usará en ese módulo.</p> Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe PDF Services], consulte <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Crear una conexión a [!DNL Adobe PDF Services]</a> en este artículo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Elements that should be extracted as JSON]</td> 
   <td> 
    <ul> 
     <li> <p>[!UICONTROL Text]</p> </li> 
     <li> <p>[!UICONTROL Tables]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Extract Bounding boxes?]</td> 
   <td>Active esta opción para extraer datos sobre el cuadro delimitador del texto.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include styling information for output?]</td> 
   <td>Active esta opción para añadir información de estilo al JSON de salida.</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Generate document]

El módulo [!UICONTROL Generate document] es una forma eficaz de crear un PDF que contenga los datos seleccionados. Puede aplicarle formato utilizando una plantilla [!DNL Microsoft Word] o proporcionando datos en formato JSON.

Para obtener más información sobre la funcionalidad [!UICONTROL [!DNL Adobe PDF Services] Generate document], consulte la [Información general sobre la generación de documentos](https://www.adobe.io/apis/documentcloud/dcsdk/docs.html) en la documentación de [!DNL Adobe Document Services].

* [Usar el módulo [!UICONTROL Generate document] con una [!DNL Microsoft Word] plantilla](#use-the-generate-document-module-with-a-microsoft-word-template)
* [Usar el módulo [!UICONTROL Generate document] con JSON](#use-the-generate-document-module-with-json)

#### Usar el módulo [!UICONTROL Generate document] con una plantilla [!DNL Microsoft Word]


>[!NOTE]
>
>Para ver un análisis de las plantillas de Microsoft Word, consulte [Módulos de plantillas de Microsoft Word](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/microsoft-word-templates-modules.md).
>
>No es necesario utilizar módulos de plantilla de Microsoft Word para utilizar una plantilla de Microsoft Word con el módulo de documento Generar de servicios de PDF.


Para usar el módulo [!UICONTROL Generate document] con una plantilla [!UICONTROL Microsoft Word], primero debe crear la plantilla. Para obtener instrucciones, busque “Crear una plantilla” en la documentación de [!DNL Microsoft Office].

Rellene los campos del módulo [!UICONTROL Generate document] de la siguiente manera:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la conexión que usará en ese módulo.</p> Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe PDF Services], consulte <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Crear una conexión a [!DNL Adobe PDF Services]</a> en este artículo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source File]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> <p>Este archivo de origen es la plantilla [!DNL Microsoft Word] que utiliza el módulo para generar el nuevo PDF.</p> <p>Se recomienda crear un proyecto en [!DNL Workfront] para las plantillas [!DNL Microsoft Word] que usa en [!DNL Workfront Fusion]. A continuación, puede usar el módulo [!DNL Workfront] &gt; [!UICONTROL Download document] para extraer la plantilla adecuada a su escenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Format]</td> 
   <td> <p>Seleccione el formato del documento generado.</p> 
    <ul> 
     <li> <p>PDF</p> </li> 
     <li> <p>DOCX</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data for merge]</td> 
   <td> <p>Para cada etiqueta de valor de la plantilla que desee reemplazar con texto, rellene el siguiente cuadro:</p> 
    <ul> 
     <li> <p>[!UICONTROL Key]</p> <p>Introduzca una clave. En la plantilla, la clave es el texto que se muestra en la etiqueta de valor. Por ejemplo, si desea colocar texto en la etiqueta de valor <code>&#123;&#123;name&#125;&#125;</code>, escriba <code>name </code> en el campo clave.</p> </li> 
     <li> <p>Tipo de valor</p> <p>Seleccione si los datos del campo de valor son un valor, un objeto o una matriz de objetos.</p> </li> 
     <li> <p>[!UICONTROL Value]</p> <p>Introduzca o asigne el texto que desea que aparezca en el documento generado en lugar de la etiqueta de valor.</p> </li> 
    </ul> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/generate-with-template-350x241.png" style="width: 350;height: 241;"> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### Usar el módulo [!UICONTROL Generate document] con JSON

Para utilizar el módulo [!UICONTROL Generate document] con JSON, rellene los campos de la siguiente manera:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la conexión que usará en ese módulo.</p> Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe PDF Services], consulte <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Crear una conexión a [!DNL Adobe PDF Services]</a> en este artículo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source File]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Format]</td> 
   <td> <p>Seleccione el formato del documento generado.</p> 
    <ul> 
     <li> <p>PDF</p> </li> 
     <li> <p>DOCX</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data for merge]</td> 
   <td> <p>Para utilizar JSON en este módulo, debe habilitar la asignación en este campo.</p> <p>Introduzca o asigne el JSON desde el que generar el documento. </p> <p>Puede escribir JSON directamente en este campo o asignar la salida JSON desde un módulo JSON.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Linearize a PDF file]

Esta herramienta linealiza un documento PDF para crear un documento PDF optimizado para web. Un documento PDF linealizado puede visualizarse página por página sin necesidad de descargar todo el documento.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la conexión que usará en ese módulo.</p> Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe PDF Services], consulte <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Crear una conexión a [!DNL Adobe PDF Services]</a> en este artículo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Realizar una llamada de API personalizada

Este módulo de acción envía una petición HTTP personalizada a la API de servicios de PDF.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la conexión que usará en ese módulo.</p> Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe PDF Services], consulte <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Crear una conexión a [!DNL Adobe PDF Services]</a> en este artículo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> Introduzca una ruta relativa o una dirección URL. </p> </td> 
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
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td> <p>Para cada campo que desee añadir a la llamada de API, haga clic en <b>Añadir elemento</b> e introduzca la clave y el valor opcional del campo.</p> <p>Nota:  <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>


### [!UICONTROL OCR for PDF file]

Esta herramienta realiza el reconocimiento óptico de caracteres (OCR) en un archivo y produce un PDF.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la conexión que usará en ese módulo.</p> Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe PDF Services], consulte <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Crear una conexión a [!DNL Adobe PDF Services]</a> en este artículo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Language]</td> 
   <td>Seleccione el idioma de este documento.<p>Para ver las opciones de idioma, consulte <a href="#convert-document-to-pdf-file" class="MCXref xref" >Convertir documento en archivo PDF</a> en este artículo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL OCR type]</td> 
   <td> 
    <ul> 
     <li> <p>[!UICONTROL Modified original image] type garantiza que el texto se pueda buscar y seleccionar, pero modifica la imagen original durante el proceso de limpieza (por ejemplo, lo deskews) antes de colocar una capa de texto invisible sobre ella. Este tipo elimina los artefactos no deseados y puede resultar en un documento más legible en algunos casos. </p> </li> 
     <li> <p>[!UICONTROL Unchanged original image] texto también superpone una capa de texto en la que se puede buscar sobre la imagen original, pero en este caso, la imagen original no cambia. Este tipo produce la máxima fidelidad con respecto a la imagen original.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Page manipulation]

Este módulo le permite rotar o eliminar selectivamente páginas de un documento de PDF. Por ejemplo, puede cambiar la vista vertical a la horizontal o quitar determinadas páginas del documento de PDF.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la conexión que usará en ese módulo.</p> Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe PDF Services], consulte <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Crear una conexión a [!DNL Adobe PDF Services]</a> en este artículo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Action]</td> 
   <td> <p>Seleccione la acción que desea realizar en el archivo.</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Delete]</b> </p> <p>Seleccione esta opción para eliminar páginas del documento.</p><p>Para cada intervalo de páginas que desee eliminar, haga clic en <strong>[!UICONTROL Add]</strong> y, a continuación, escriba la primera y la última página del intervalo de páginas. </p> <p>Nota:   
     <ul> 
      <li> <p>Puede utilizar números negativos para contar desde el final del documento. La última página de un documento es -1, la penúltima es -2, y así sucesivamente.</p> </li> 
      <li> <p>Para eliminar una sola página, indique el mismo número de página para el inicio y el final del intervalo.</p></ul> </li> 
     <li> <p><b>[!UICONTROL Rotate]</b> </p> <p>Seleccione esta opción para girar las páginas y luego introduzca el ángulo, en grados en el sentido de las agujas del reloj, que desea girar las páginas del documento en relación con su orientación inicial.</p> <p>Para girar de la posición vertical a la horizontal o viceversa, gire la página 90 o 270 grados.</p> <p>Si una página está al revés, gírela 180 grados.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Pages]</td> 
   <td> <p>Para cada intervalo de páginas que desee eliminar, haga clic en <strong>[!UICONTROL Add]</strong> y, a continuación, escriba la primera y la última página del intervalo de páginas. </p> <p>Nota:   
     <ul> 
      <li> <p>Puede utilizar números negativos para contar desde el final del documento. La última página de un documento es -1, la penúltima es -2, y así sucesivamente.</p> </li> 
      <li> <p>Para eliminar una sola página, indique el mismo número de página para el inicio y el final del intervalo.</p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros con los que desea que trabaje el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL PDF accessibility auto-tag]

Este módulo de acción crea un PDF etiquetado para casos de uso de accesibilidad. También crea un informe opcional de Microsoft Excel que enumera los problemas y sugiere correcciones.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la conexión que usará en ese módulo.</p> Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe PDF Services], consulte <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Crear una conexión a [!DNL Adobe PDF Services]</a> en este artículo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Shift Headings]</td> 
   <td> <p>Active esta opción para cambiar los encabezados del documento.</p> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Generate Report]</td> 
   <td> <p>Active esta opción para generar un informe que enumere los problemas de accesibilidad en el PDF junto con su ubicación y proporcione sugerencias para solucionarlos.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL PDF file properties]

Esta herramienta extrae información básica sobre el documento, como:

* Recuento de páginas
* Versión del PDF
* Si el archivo está cifrado
* Si el archivo está linearizado
* Si el archivo contiene archivos incrustados

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la conexión que usará en ese módulo.</p> Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe PDF Services], consulte <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Crear una conexión a [!DNL Adobe PDF Services]</a> en este artículo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Protect a PDF file]

Esta herramienta asegura un documento PDF con una contraseña de usuario o de propietario. También establece restricciones en determinadas funciones, como imprimir, editar y copiar en el documento PDF. Usted selecciona el tipo de contenido que desea cifrar y el algoritmo de cifrado.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la conexión que usará en ese módulo.</p> Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe PDF Services], consulte <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Crear una conexión a [!DNL Adobe PDF Services]</a> en este artículo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> <p>El archivo de origen debe estar en formato PDF. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Password Protection Type]</td> 
   <td> <p>Active esta opción para utilizar contraseñas para cifrar el documento PDF de entrada. Si activa esta opción, debe especificar e introducir un valor para una o ambas de las siguientes opciones: </p> 
    <ul> 
     <li> <p>[!UICONTROL User Password]</p> </li> 
     <li> <p>[!UICONTROL Owner Password] </p> </li> 
    </ul> <p>Cada contraseña puede tener hasta 128 caracteres de longitud.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Encryption Algorithm]</td> 
   <td> <p>Seleccione el algoritmo de cifrado. </p> 
    <ul> 
     <li> <p>[!UICONTROL AES-128 encryption]</p> <p>La contraseña solo admite caracteres LATIN-I. </p> </li> 
     <li> <p>[!UICONTROL AES-256 encryption]</p> <p>La contraseña admite conjuntos de caracteres Unicode</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content to Encrypt]</td> 
   <td> <p>Seleccione el tipo de contenido que desea cifrar.</p> 
    <ul> 
     <li> <p>[!UICONTROL All content]</p> </li> 
     <li> <p>[!UICONTROL All content except metadata]</p> </li> 
     <li> <p>[!UICONTROL Only embedded data] </p> </li> 
    </ul> <p>Si se selecciona "[!UICONTROL Only embedded data]", los permisos de acceso proporcionados se considerarán ineficaces.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Permissions]</td> 
   <td> <p>Seleccione los permisos que desee incluir para permitir la impresión, edición o copia de contenido.</p> <p>La configuración de permisos solo se usa si [!UICONTROL Owner Password] está establecido en el campo [!UICONTROL Password Protection Type].</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Remove protection of a PDF file]

Esta herramienta elimina la seguridad (protección con contraseña) de un documento de PDF.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la conexión que usará en ese módulo.</p> Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe PDF Services], consulte <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Crear una conexión a [!DNL Adobe PDF Services]</a> en este artículo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> <p>El archivo de origen debe estar en formato PDF.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Password]</td> 
   <td>Introduzca la contraseña que protege actualmente el archivo.</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Split a PDF file]

Este módulo de acción divide un documento PDF en varios documentos más pequeños. Especifique si desea dividirlo por número de archivos, páginas por archivo o intervalos de páginas.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la conexión que usará en ese módulo.</p> Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe PDF Services], consulte <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Crear una conexión a [!DNL Adobe PDF Services]</a> en este artículo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> <p>El archivo de origen debe estar en formato PDF.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split option]</td> 
   <td>Seleccione cómo desea dividir el archivo. 
   <ul>
   <li><p><b>Intervalos de página</b></p><p>Para cada intervalo de páginas que desee dividir en un documento independiente, haga clic en <b>Añadir</b> e introduzca la página en la que desea comenzar y la página en la que desea finalizar.</p></li>
   <li><p><b>Recuento de páginas</b></p><p>Introduzca el número de páginas que desea incluir en los nuevos documentos.</p></li>
   <li><p><b>Cuenta de archivo</b></p><p>Introduzca el número de archivos de tamaño uniforme en los que desea dividir el documento.</p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>