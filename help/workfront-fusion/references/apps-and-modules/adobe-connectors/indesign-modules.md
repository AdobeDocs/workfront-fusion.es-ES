---
filename: adobe-indesign-modules
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: apps-and-their-modules
title: Módulos de Adobe InDesign
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan Adobe InDesign, así como conectarlos a varias aplicaciones y servicios de terceros.
author: Becky
exl-id: 8164487a-d114-4e31-9d1c-8404fc89a04b
TQID: https://experienceleague.adobe.com/D2JdaOqvTA5SUsKm9U8Sjss6dJFMZv2Uo5RGk25QphQ
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 18401e01219383f86e1553e16b21057497d24cc0
workflow-type: tm+mt
source-wordcount: 2240
ht-degree: 17%

---

# Módulos Adobe InDesign

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan Adobe InDesign, así como conectarlos a varias aplicaciones y servicios de terceros.

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

Para poder usar el conector de Adobe InDesign, debe tener una cuenta de Adobe InDesign activa.

## Creación de una conexión con Adobe InDesign

Para crear una conexión para los módulos de Adobe InDesign:

1. En cualquier módulo de Adobe InDesign, haga clic en **Agregar** junto al cuadro Conexión.

1. Rellene los campos siguientes:

   <table style="table-layout:auto"> 
      <col>
      </col>
      <col>
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
          <p>Seleccione si se está conectando a un entorno de producción o de no producción.</p>
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
          <td>Introduzca su ID de cliente de Adobe. Esto se puede encontrar en la sección de detalles de credenciales de Adobe Developer Console</td>
        </tr>
        <tr>
          <td role="rowheader">Secreto de cliente</td>
          <td>Escriba el Secreto de cliente de Adobe. Esto se puede encontrar en la sección de detalles de credenciales de Adobe Developer Console</td>
        </tr>
        <tr>
          <td role="rowheader">ID de organización de IMS</td>
          <td>Introduzca su ID de organización de Adobe. Esto se puede encontrar en la sección de detalles de credenciales de Adobe Developer Console</td>
        </tr>
      </tbody>
    </table>
1. Haga clic en **Continuar** para guardar la conexión y volver al módulo.

## Módulos InDesign y sus campos

Al configurar los módulos de Adobe InDesign, Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden mostrarse campos de Adobe InDesign adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, consulte [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Acciones

* [Crear representación](#create-rendition)
* [Eliminar un script personalizado](#delete-a-custom-script)
* [Combinación de datos](#merge-data)
* [Reasignar vínculos](#remap-links)
* [Enviar una solicitud de ejecución de script personalizada](#submit-a-custom-script-execution-request)

#### Crear representación

Este módulo de acción crea y devuelve una representación JPEG, PNG o PDF de un documento de InDesign específico. Para la estructura de `StatusCompletedRespons/output/data`, consulte `RenditionOutputData`. También para obtener la lista de posibles códigos de error en `FailedEvent`, consulte `RenditionFailedData`.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe InDesign, consulte <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Crear una conexión con Adobe InDesign</a> en este artículo.</td>
    </tr>
       <tr>
      <td role="rowheader">
        <p>Tipo</p>
      </td>
      <td>Seleccione el tipo de archivo de la representación que desea crear. 
      <ul><li>JPEG</li><li>PNG</li><li>PDF</li></ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>Recursos</p>
      </td>
      <td>Para cada recurso que desee agregar a la representación:<ol><li>Haga clic en <b>Agregar elemento</b>.</li><li>Seleccione o asigne el origen del recurso.</li><li>Introduzca un destino. El destino es una ruta relativa a un directorio base temporal (directorio de trabajo) en el que se descarga el recurso. Esto identifica los recursos dentro de los parámetros. No puede subir usando '..' o '/'. Debe haber un nombre de archivo válido.</td>
    </tr>
    <tr>
      <td role="rowheader">Documento de destino</td>
      <td>Introduzca o asigne el documento que se procesará y procesará. Actualmente, solo se admite un documento a la vez.</td>
    </tr>
    <tr>
      <td role="rowheader">Otros campos</td>
   <td>Para otros campos, consulte la información incluida en el módulo.</td>     </tr>
  </tbody>
</table>

#### Eliminar un script personalizado

Este módulo de acción elimina un único script personalizado registrado. Todas las versiones del script se eliminarán de forma permanente.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe InDesign, consulte <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Crear una conexión con Adobe InDesign</a> en este artículo.</td>
    </tr>
       <tr>
      <td role="rowheader">
        <p>Nombre del script</p>
      </td>
      <td>Introduzca o asigne el nombre del script que desea eliminar.</td>
    </tr>
  </tbody>
</table>

#### Combinación de datos

Este módulo crea documentos o PDF de InDesign combinando datos CSV con plantillas de InDesign. Los formatos de salida incluyen documentos de JPEG, PNG, PDF y InDesign.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe InDesign, consulte <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Crear una conexión con Adobe InDesign</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>Recursos</p>
      </td>
      <td>Para cada recurso que desee agregar a la combinación de datos:<ol><li>Haga clic en <b>Agregar elemento</b>.</li><li>Seleccione o asigne el origen del recurso.</li><li>Introduzca un destino. El destino es una ruta relativa a un directorio base temporal (directorio de trabajo) en el que se descarga el recurso. Esto identifica los recursos dentro de los parámetros. No puede subir usando '..' o '/'. Debe haber un nombre de archivo válido.</td>
    </tr>
    <tr>
      <td role="rowheader">Documento de destino</td>
      <td>Introduzca o asigne el documento que se utilizará como plantilla para la combinación.</td>
    </tr>
    <tr>
      <td role="rowheader">Fuente de datos</td>
      <td>Introduzca o asigne los archivos de origen que se van a utilizar.</td>
    </tr>
    <tr>
      <td role="rowheader">Otros campos</td>
   <td>Para otros campos, consulte la información incluida en el módulo.</td>     </tr>
  </tbody>
</table>

#### Reasignar vínculos

Este módulo reemplaza los vínculos basados en archivos de los documentos de InDesign por las direcciones URL de Adobe Experience Manager (AEM). Esto puede resultar útil para trabajar con Adobe Experience Manager mediante Adobe Asset Link.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe InDesign, consulte <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Crear una conexión con Adobe InDesign</a> en este artículo.</td>
      </tr>
    <tr>
      <td role="rowheader">Token de AEM</td>
      <td>Introduzca o asigne el token de portador generado para la cuenta técnica de AEM, sin la palabra clave portador.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>Recursos</p>
      </td>
      <td>Para cada recurso que desee agregar al módulo:<ol><li>Haga clic en <b>Agregar elemento</b>.</li><li>Seleccione o asigne el origen del recurso.</li><li>Introduzca un destino. El destino es una ruta relativa a un directorio base temporal (directorio de trabajo) en el que se descarga el recurso. Esto identifica los recursos dentro de los parámetros. No puede subir usando '..' o '/'. Debe haber un nombre de archivo válido.</td>
    </tr>
    <tr>
      <td role="rowheader">Documento de destino</td>
      <td>Introduzca o asigne el documento en el que desea reasignar vínculos.</td>
    </tr>
    <tr>
      <td role="rowheader">Fuente de datos</td>
      <td>Introduzca o asigne los archivos de origen que se utilizarán para extraer y hacer coincidir etiquetas.</td>
    </tr>
    <tr>
      <td role="rowheader">Otros campos</td>
   <td>Para otros campos, consulte la información incluida en el módulo.</td>     </tr>
  </tbody>
</table>

#### Enviar una solicitud de ejecución de script personalizada

Este módulo de acción envía una solicitud de ejecución para un script personalizado. Defina los recursos de entrada y los parámetros que el script personalizado utilizará durante la ejecución.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe InDesign, consulte <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Crear una conexión con Adobe InDesign</a> en este artículo.</td>
    </tr>
       <tr>
      <td role="rowheader">
        <p>ID de script</p>
      </td>
      <td>Introduzca o asigne el ID del script personalizado.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>Recursos</p>
      </td>
      <td>Para cada recurso para el que desee enviar una solicitud de ejecución, <ol><li>Haga clic en <b>Agregar elemento</b>.</li><li>Seleccione o asigne el origen del recurso.</li><li>Introduzca un destino. El destino es una ruta relativa a un directorio base temporal (directorio de trabajo) en el que se descarga el recurso. Esto identifica los recursos dentro de los parámetros. No puede subir usando '..' o '/'. Debe haber un nombre de archivo válido.</td>
    </tr>
    <tr>
      <td role="rowheader">Otros campos</td>
   <td>Para otros campos, consulte la información incluida en el módulo.</td>     </tr>
  </tbody>
</table>

### Búsquedas

* [Obtener detalles del script personalizado](#get-custom-script-details)
* [Obtener etiquetas de combinación de datos](#get-data-merge-tags)
* [Obtener información de documentos](#get-document-information)
* [Enumerar scripts personalizados](#list-custom-scripts)

#### Obtener detalles del script personalizado

Este módulo de búsqueda recupera los detalles de un único script personalizado registrado, incluida la versión, el vínculo de descarga, la fecha de registro y el nombre del script.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe InDesign, consulte <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Crear una conexión con Adobe InDesign</a> en este artículo.</td>
    </tr>
       <tr>
      <td role="rowheader">
        <p>Nombre del script</p>
      </td>
      <td>Introduzca o asigne el nombre del script cuyos detalles desea recuperar.</td>
    </tr>
  </tbody>
</table>

#### Obtener etiquetas de combinación de datos

Este módulo recupera las etiquetas de combinación de datos de un documento.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe InDesign, consulte <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Crear una conexión con Adobe InDesign</a> en este artículo.</td>
      </tr>
    <tr>
      <td role="rowheader">
        <p>Recursos</p>
      </td>
      <td>Para cada recurso que desee agregar al módulo:<ol><li>Haga clic en <b>Agregar elemento</b>.</li><li>Seleccione o asigne el origen del recurso.</li><li>Introduzca un destino. El destino es una ruta relativa a un directorio base temporal (directorio de trabajo) en el que se descarga el recurso. Esto identifica los recursos dentro de los parámetros. No puede subir usando '..' o '/'. Debe haber un nombre de archivo válido.</td>
    </tr>
    <tr>
      <td role="rowheader">Documento de destino</td>
      <td>Introduzca o asigne el documento del que desea recuperar las etiquetas.</td>
    </tr>
    <tr>
      <td role="rowheader">Fuente de datos</td>
      <td>Introduzca o asigne los archivos de origen que se utilizarán para extraer y hacer coincidir etiquetas.</td>
    </tr>
    <tr>
      <td role="rowheader">Otros campos</td>
   <td>Para otros campos, consulte la información incluida en el módulo.</td>     </tr>
  </tbody>
</table>

#### Obtener información de documentos

Este módulo recupera información completa sobre documentos INDD/IDML y devuelve datos en función de los tipos de información habilitados especificados en la solicitud.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe InDesign, consulte <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Crear una conexión con Adobe InDesign</a> en este artículo.</td>
      </tr>
    <tr>
      <td role="rowheader">
        <p>Recursos</p>
      </td>
      <td>Para cada recurso que desee agregar al módulo:<ol><li>Haga clic en <b>Agregar elemento</b>.</li><li>Seleccione o asigne el origen del recurso.</li><li>Introduzca un destino. El destino es una ruta relativa a un directorio base temporal (directorio de trabajo) en el que se descarga el recurso. Esto identifica los recursos dentro de los parámetros. No puede subir usando '..' o '/'. Debe haber un nombre de archivo válido.</td>
    </tr>
    <tr>
      <td role="rowheader">Documento de destino</td>
      <td>Introduzca o asigne el documento del que desea recuperar información.</td>
    </tr>
     <tr>
      <td role="rowheader">Otros campos</td>
   <td>Para otros campos, consulte la información incluida en el módulo.</td>     </tr>
  </tbody>
</table>

#### Enumerar scripts personalizados

Este módulo recupera detalles de la última versión de todos los scripts personalizados registrados, incluida la versión, el vínculo de descarga, la fecha de registro y el nombre del script. Los resultados se paginan según la longitud de la lista.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe InDesign, consulte <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Crear una conexión con Adobe InDesign</a> en este artículo.</td>
      </tr>
    <tr>
      <td role="rowheader">Número de página</td>
      <td>Escriba o asigne el número de página desde el que desea comenzar.</td>
    </tr>
  <tr> 
   <td>Número máximo de resultados devueltos</td> 
   <td>Establezca el número máximo de equipos o grupos que Workfront Fusion devolverá durante un ciclo de ejecución.</td> 
  </tr> 
  </tbody>
</table>


### Otros

#### Realizar una llamada API personalizada

Este módulo realiza una llamada de API personalizada a la API de Adobe InDesign

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe InDesign, consulte <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Crear una conexión con Adobe InDesign</a> en este artículo.</td>
    </tr>
       <tr>
      <td role="rowheader">
        <p>Ruta</p>
      </td>
      <td>
        <p>Escriba una ruta relativa a <code>https://indesign.adobe.io/v3</code>.</p><p> Ejemplo: <code>/create-rendition</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>Método</p>
      </td>
      <td>
        <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, consulte [Métodos de solicitud HTTP](/help/workfront-fusion/references/modules/http-request-methods.md).</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">Encabezados</td>
      <td>
        <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p>
        <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion añade encabezados de autorización automáticamente.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">Cadena de consulta  </td>
      <td>
        <p>Introduzca la cadena de consulta de la solicitud.</p>
      </td>
    </tr>
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
  </tbody>
</table>

### Sin categoría

#### Convertir PDF a InDesign

Este módulo convierte el documento de PDF al formato InDesign editable (INDD o IDML). La salida es un archivo ZIP (nombre predeterminado &quot;output.zip&quot;) que contiene subcarpetas con el nombre de cada PDF de entrada, con el documento convertido y los recursos asociados. Si la opción Insertar vínculos es falsa, los recursos se proporcionan en una carpeta independiente dentro del ZIP. Si el valor es True, todos los vínculos se incrustan en el archivo InDesign.



<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe InDesign, consulte <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Crear una conexión con Adobe InDesign</a> en este artículo.</td>
      </tr>
    <tr>
      <td role="rowheader">Recursos de entrada</td>
      <td>Para cada recurso que desee convertir, haga clic en <b>Agregar elemento</b>, escriba la dirección URL del recurso y asigne un nombre de archivo local. Se hará referencia al nombre de archivo más adelante en el módulo.</td>
    </tr>
  <tr> 
   <td>Documentos de destino</td> 
   <td>Para cada documento que desee convertir, haga clic en <b>Agregar elemento</b> e introduzca el nombre de archivo asignado del campo Recursos de entrada.</td> 
  </tr> 
  <tr> 
   <td>Formato de salida</td> 
   <td>Seleccione si desea convertir los archivos a archivos INDD o IDML.</td> 
  </tr> 
  <tr> 
   <td>Incrustar vínculos</td> 
   <td>Seleccione Sí si desea que todos los vínculos de imágenes y recursos estén incrustados directamente en el archivo INDD o IDML. Seleccione No para colocar estos recursos en una carpeta independiente en el archivo ZIP.</td> 
  </tr> 
  <tr> 
   <td>Nombre del archivo ZIP de salida</td> 
   <td>Introduzca o asigne un nombre al archivo ZIP de salida.</td> 
  </tr> 
  <tr> 
   <td>Salidas</td> 
   <td>Para cada archivo que desee generar, seleccione el tipo de almacenamiento e introduzca los detalles de almacenamiento.</td> 
  </tr> 
  <tr> 
   <td>Número máximo de resultados devueltos</td> 
   <td>Introduzca el número máximo de resultados que desea que devuelva el módulo para cada ciclo de ejecución.</td> 
  </tr> 
  </tbody>
</table>

#### Enviar un script personalizado

Este módulo envía paquetes de scripts personalizados para su registro y devuelve una URL para publicar solicitudes de ejecución para el script registrado.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe InDesign, consulte <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Crear una conexión con Adobe InDesign</a> en este artículo.</td>
      </tr>
    <tr>
      <td role="rowheader">Paquete de script</td>
      <td>Asigne el archivo de origen desde un módulo anterior, como un módulo Descargar un documento. Debe ser un archivo ZIP.</td>
    </tr>
  <tr> 
   <td>Nombre del archivo</td> 
   <td>Introduzca o asigne el nombre del archivo cargado que contiene el paquete de secuencias de comandos.</td> 
  </tr> 
  </tbody>
</table>

#### Actualizar versión de aplicación de script personalizada

Este módulo actualiza la configuración de la versión de la aplicación de InDesign para un script personalizado registrado. Esto le permite especificar estrategias de versión, incluido el uso de la versión más reciente, la corrección de una versión principal o la corrección de una versión principal y secundaria específica.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe InDesign, consulte <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Crear una conexión con Adobe InDesign</a> en este artículo.</td>
      </tr>
    <tr>
      <td role="rowheader">Nombre del script</td>
      <td>Introduzca o asigne el nombre del script personalizado que desea actualizar. Este es el valor <code>capability</code> devuelto cuando se registró el script.</td>
    </tr>
  <tr> 
   <td>Estrategia de versión de aplicación</td> 
   <td>Seleccione la estrategia de versión de la aplicación que desee utilizar.
   <ul>
   <li><b>Utilice siempre la versión más reciente</b></li>
   <li><b>Anclar a una versión principal</b><p>Introduzca o asigne el número de la versión principal a la que desea aplicar esto.</p></li>
   <li><b>Anclar a una versión principal y secundaria</b><p>Introduzca la versión principal y secundaria a la que desea aplicar esto.</p></li>
   </ul></td> 
  </tr> 
  </tbody>
</table>

#### Obtener versiones actuales de la aplicación

Este módulo recupera información sobre todas las versiones de la aplicación de InDesign disponibles, incluida la versión principal, la versión secundaria y el estado de cada versión de la aplicación registrada.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe InDesign, consulte <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Crear una conexión con Adobe InDesign</a> en este artículo.</td>
      </tr>
  <tr> 
   <td>Número máximo de resultados devueltos</td> 
   <td>Introduzca el número máximo de resultados que desea que devuelva el módulo para cada ciclo de ejecución.</td> 
  </tr> 
  </tbody>
</table>

