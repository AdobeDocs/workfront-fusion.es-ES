---
title: Módulos de Adobe Lightroom
description: Con los módulos de Adobe Lightroom, puede iniciar un escenario de Adobe Workfront Fusion basado en los eventos de su cuenta de Adobe Lightroom.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 3f29ab35-7a90-4afb-a283-4faaacec5b15
source-git-commit: e1e15985db9683525250d1f9f9276224b2baf0e6
workflow-type: tm+mt
source-wordcount: '2019'
ht-degree: 22%

---

# Módulos de [!DNL Adobe Lightroom]

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!DNL Adobe Lightroom], así como conectarlo a varias aplicaciones y servicios de terceros.

Si necesita instrucciones sobre cómo crear un escenario, vea los artículos en [Crear un escenario: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

## Requisitos de acceso

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

## Requisitos previos

Antes de poder usar el conector de [!DNL Adobe Lightroom], debe asegurarse de que se cumplen los siguientes requisitos previos:

* Debe tener una cuenta de [!DNL Adobe Lightroom] activa.

## Información de API de Adobe Lightroom

El conector de Adobe Lightroom utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL básica</td> 
   <td>https://lr.adobe.io</td> 
  </tr>
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.17.128</td> 
  </tr>
 </tbody> 
 </table>



## Creación de una conexión con Adobe Lightroom

Para crear una conexión para los módulos de [!DNL Adobe Lightroom]:

1. Haga clic en **[!UICONTROL Add]** junto al cuadro Conexión.

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
        <td>Escriba su [!UICONTROL Adobe] [!UICONTROL Client ID]. Esto se puede encontrar en la sección de detalles [!UICONTROL Credentials] del [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Escriba su [!DNL Adobe] [!UICONTROL Client Secret]. Esto se puede encontrar en la sección de detalles [!UICONTROL Credentials] del [!DNL Adobe Developer Console]</td>
        </tr>
      </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continue]** para guardar la conexión y volver al módulo.




## Módulos Adobe Lightroom y sus campos

Al configurar módulos de [!DNL Adobe Lightroom], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Adobe Lightroom] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Otro](#other)
* [Recursos](#assets)
* [Álbumes](#albums)

### Otro

* [Comprobación de estado](#health-check)
* [Recuperar metadatos del catálogo de usuarios](#retrieve-user-catalog-metadata)

#### Comprobación de estado

Este módulo de acción recupera un ID de versión de servidor de Lightroom, que prueba si el servicio de Lightroom se está ejecutando actualmente.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Lightroom], consulte <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Crear una conexión con [!DNL Adobe Lightroom]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Credentials]</td>
      <td>
        <p>Si desea proporcionar credenciales específicas para asegurarse de que se está ejecutando un servidor específico, haga clic en Agregar elemento e introduzca las credenciales.</p><p>Los encabezados de autorización se añaden automáticamente.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Recuperar metadatos del catálogo de usuarios

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Lightroom], consulte <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Crear una conexión con [!DNL Adobe Lightroom]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Credentials]</td>
      <td>
        <p>Si desea proporcionar credenciales específicas para asegurarse de que puede acceder a la cuenta de usuario correcta, haga clic en Agregar elemento e introduzca las credenciales.</p><p>Los encabezados de autorización se añaden automáticamente.</p>
      </td>
    </tr>
  </tbody>
</table>

### Recursos

* [Crear un archivo original de recurso](#create-an-asset-external-xmp-develop-setting-file)
* [Crear un recurso](#create-an-asset)
* [Crear un archivo de configuración de desarrollo de XMP externo de recursos](#create-an-asset-external-xmp-develop-setting-file)
* [Generar representaciones para un archivo original](#generate-renditions-for-an-original-file)
* [Obtener un recurso de catálogo](#get-a-catalog-asset)
* [Obtenga la configuración de desarrollo de XMP externo de recursos más reciente](#get-the-latest-asset-external-xmp-develop-setting-file)
* [Obtener la última representación de recursos](#get-the-latest-asset-rendition)
* [Recuperar recursos](#retrieve-assets)

#### Crear un archivo original de recurso

Este módulo de acción crea y carga un archivo original para un recurso.


<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Lightroom], consulte <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Crear una conexión con [!DNL Adobe Lightroom]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo que contiene el recurso.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>Introduzca o asigne el ID del recurso para el que desea crear y cargar un archivo.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Length of content in bytes]</td>
      <td>
        <p>Introduzca o asigne la longitud del contenido en bytes.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Byte range]</td>
      <td>
        <p>Introduzca o asigne el rango de bytes para la solicitud, incluidos los bytes primero y último y la longitud de entidad definida en RFC 2616. Solo debe incluirse cuando los datos sean demasiado grandes para cargarse en una sola llamada.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Content type]</td>
      <td>
        <p>Seleccione el tipo de contenido del nuevo archivo.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Crear un recurso

Este módulo de acción crea un nuevo recurso con metadatos iniciales e información de importación.


<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Lightroom], consulte <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Crear una conexión con [!DNL Adobe Lightroom]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo en el que se creará el recurso.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>Introduzca o asigne el ID del nuevo recurso.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset type]</td>
      <td>
        <p>Seleccione si el recurso es una imagen o un vídeo.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Datetime user created]</td>
      <td>
        <p>Escriba o asigne una fecha con el formato <code>YYYY-MM-DDT00:00:00-00:00</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Datetime user updated]</td>
      <td>
        <p>Escriba o asigne una fecha con el formato <code>YYYY-MM-DDT00:00:00-00:00</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Date captured]</td>
      <td>
        <p>Escriba o asigne una fecha con el formato <code>YYYY-MM-DDT00:00:00-00:00</code>.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Crear un archivo de configuración de desarrollo de XMP externo de recursos

Este módulo de acción admite dos flujos de trabajo. El primer flujo de trabajo es cargar el archivo de configuración de desarrollo de XMP externo para el recurso. El segundo flujo de trabajo es crear un archivo de configuración de desarrollo de XMP externo copiando del archivo de configuración de desarrollo de xmp externo de otro recurso.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Lightroom], consulte <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Crear una conexión con [!DNL Adobe Lightroom]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Length of content in bytes]</td>
      <td>
        <p>Introduzca o asigne la longitud del contenido en bytes.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Upload new or copy XMP/develop file]</td>
      <td>
        <p>Seleccione si desea cargar un archivo nuevo o copiar un archivo de un recurso existente.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo que contiene el recurso.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>Introduzca o asigne el ID del recurso en el que desea cargar o copiar un archivo.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Link to XMP/develop file]</td>
      <td>
        <p>Introduzca o asigne un vínculo al archivo que desee cargar o copiar.</p><p>Este archivo debe ser JSON si copia un archivo, o XML si carga un archivo.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Generar representaciones para un archivo original

Este módulo de acción genera de forma asíncrona representaciones para un archivo original.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Lightroom], consulte <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Crear una conexión con [!DNL Adobe Lightroom]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Rendition Type(s) (semi-colon separated)]</td>
      <td>
        <p>Introduzca el tipo de representación para la representación que desea crear. Si introduce más de un tipo, sepárelos con punto y coma (;). <p>Tipos posibles:</p><ul><li><code>fullsize</code></li><li><code>2560</code></li></ul></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Length of content in bytes]</td>
      <td>
        <p>Introduzca o asigne la longitud del contenido en bytes.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo que contiene el recurso.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>Introduzca o asigne el ID del recurso para el que desea crear una representación de un archivo.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Obtener un recurso de catálogo

Este módulo de acción recupera información sobre un único recurso de un catálogo. El catálogo debe ser propiedad del usuario cuyas credenciales se representen en la conexión utilizada en este módulo.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Lightroom], consulte <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Crear una conexión con [!DNL Adobe Lightroom]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo que contiene el recurso.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>Introduzca o asigne el ID del recurso para el que desea recuperar información.</p>
      </td>
    </tr>
  </tbody>
</table>


#### Obtenga el archivo de configuración de desarrollo de XMP externo de recursos más reciente

Este módulo de acción recupera el archivo de configuración de XMP externo de recursos más reciente.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Lightroom], consulte <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Crear una conexión con [!DNL Adobe Lightroom]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo que contiene el recurso.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>Introduzca o asigne el ID del recurso asociado al archivo de configuración de desarrollo de XMP.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Obtener la última representación de recursos

Este módulo de acción recupera la última representación de recursos del tipo especificado.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Lightroom], consulte <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Crear una conexión con [!DNL Adobe Lightroom]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo que contiene el recurso.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>Introduzca o asigne el ID del recurso asociado al archivo de configuración de desarrollo de XMP.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Rendition type]</td>
      <td>
        <p>Seleccione el tipo de representación que desea recuperar.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Recuperar recursos

Este módulo de acción recupera recursos propiedad del usuario cuyas credenciales se representan en la conexión utilizada en este módulo.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Lightroom], consulte <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Crear una conexión con [!DNL Adobe Lightroom]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo que contiene el recurso.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Starting timestamp]</td>
      <td>
        <p>Introduzca o asigne una marca de tiempo. El módulo devuelve los registros que se han actualizado después de esta marca de tiempo.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Return assets captured before]</td>
      <td>
        <p>Escriba una fecha con el formato <code>YYYY-MM-DDT00:00:00</code>. El módulo devuelve los resultados capturados antes de esta fecha.</p><p> Este campo no se puede usar con el campo <code>Return assets captured after</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Maximum number of returned assets]</td>
      <td>
        <p>Introduzca el número máximo de registros que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL SHA256 Hash value of original file]</td>
      <td>
        <p></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Hide assets that are inside stacks?"]</td>
      <td>
        <p></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset subtype values]</td>
      <td>
        <p></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset IDs]</td>
      <td>
        <p>Introduzca o asigne hasta 100 ID de recurso, separados por comas.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Types of assets to exclude]</td>
      <td>
        <p>Seleccione si desea excluir los recursos completos o incompletos. Para incluir todos los recursos, deje este campo en blanco.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Group values]</td>
      <td>
        <p></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Name values]</td>
      <td>
        <p></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Favorite status]</td>
      <td>
        <p></p>
      </td>
    </tr>
    </tr>
  </tbody>
</table>

### Álbumes

* [Añadir recursos a un álbum](#add-assets-to-an-album)
* [Crear un álbum](#create-an-album)
* [Eliminar un álbum](#delete-an-album)
* [Consigue un álbum](#get-an-album)
* [Enumerar los recursos de un álbum](#list-assets-of-an-album)
* [Recuperar álbumes](#retrieve-albums)
* [Actualizar un álbum](#update-album)

#### Añadir recursos a un álbum

Este módulo de acción añade uno o más recursos al álbum especificado. Puede añadir hasta 50 recursos en un ciclo de ejecución.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Lightroom], consulte <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Crear una conexión con [!DNL Adobe Lightroom]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo que contiene el álbum al que desea agregar recursos.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Album ID]</td>
      <td>
        <p>Introduzca o asigne el ID del álbum al que desea agregar recursos.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Assets]</td>
      <td>
        <p>Para cada recurso que desee agregar al álbum, haga clic en <b>Agregar elemento</b> e introduzca los campos siguientes.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>Introduzca o asigne el ID del recurso que desea agregar al álbum</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Is this asset an album cover?]</td>
      <td>
        <p>Seleccione si desea que este recurso se muestre como la imagen que representa el álbum.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Order]</td>
      <td>
        <p></p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Metadata]</td>
      <td>
        <p>Introduzca o asigne cualquier metadato que desee incluir en el recurso. Debe ser una sola cadena de texto con una longitud máxima de 1 a 24 caracteres.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Remote ID]</td>
      <td>
        <p>Introduzca un identificador para el recurso.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Crear un álbum

Este módulo de acción crea un nuevo álbum en Lightroom.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Lightroom], consulte <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Crear una conexión con [!DNL Adobe Lightroom]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo en el que desea crear un álbum.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Album ID]</td>
      <td>
        <p>Introduzca o asigne un ID para el nuevo álbum.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Subtype]</td>
      <td>
        <p>Seleccione el subtipo del álbum.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL API key]</td>
      <td>
        <p>Introduzca la clave API del servicio que está creando el álbum.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Datetime user created]</td>
      <td>
        <p>Escriba o asigne una fecha con el formato <code>YYYY-MM-DDT00:00:00-00:00Z</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Datetime user updated]</td>
      <td>
        <p>Escriba o asigne una fecha con el formato <code>YYYY-MM-DDT00:00:00-00:00Z</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Album name]</td>
      <td>
        <p>Introduzca o asigne un nombre para el nuevo álbum.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Cover ID]</td>
      <td>
        <p>Introduzca o asigne el ID de un recurso para utilizarlo como portada de este álbum.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Remote ID]</td>
      <td>
        <p>Introduzca un identificador para el recurso.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Created date]</td>
      <td>
        <p>Escriba o asigne una fecha con el formato <code>YYYY-MM-DDT00:00:00-00:00Z</code>.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Updated date]</td>
      <td>
        <p>Escriba o asigne una fecha con el formato <code>YYYY-MM-DDT00:00:00-00:00Z</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Is the album deleted?]</td>
      <td>
        <p>Active esta opción si se ha eliminado el contenido afiliado externo.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL of location to edit affiliated content]</td>
      <td>
        <p>Si hay una URL donde los usuarios pueden editar el contenido de este álbum, ingrese la URL aquí.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL of location to view affiliated content]</td>
      <td>
        <p>Si hay una URL donde los usuarios pueden ver el contenido de este álbum, ingrese la URL aquí.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Eliminar un álbum

Este módulo de acción elimina un álbum.

El álbum eliminado debe haber sido creado por la misma aplicación cliente que ahora lo está eliminando, y debe ser del subtipo `project` o `project_set`.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Lightroom], consulte <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Crear una conexión con [!DNL Adobe Lightroom]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo que contiene el álbum que desea eliminar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Album ID]</td>
      <td>
        <p>Introduzca o asigne el ID del álbum que desea eliminar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Delete child albums?]</td>
      <td>
        <p>Seleccione si desea eliminar los álbumes secundarios del álbum eliminado.</p>
      </td>
    </tr>
  </tbody>
</table>

### Consigue un álbum

Este módulo de acción recupera el álbum especificado

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Lightroom], consulte <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Crear una conexión con [!DNL Adobe Lightroom]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo que contiene el álbum que desea recuperar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Album ID]</td>
      <td>
        <p>Introduzca o asigne el ID del álbum que desea recuperar.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Enumerar los recursos de un álbum

Este módulo de acción recupera una lista de recursos en el álbum especificado.



#### Recuperar álbumes

Este módulo de acción recupera una lista de álbumes en el catálogo especificado.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Lightroom], consulte <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Crear una conexión con [!DNL Adobe Lightroom]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo que contiene los álbumes que desea recuperar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Subtypes]</td>
      <td>
        <p>Introduzca o asigne el ID del álbum que desea recuperar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Name of album to precede current results]</td>
      <td>
        <p>Si está paginando los resultados, escriba o asigne el nombre del último álbum de la página anterior.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Maximum number of returned albums]</td>
      <td>
        <p>Establezca el número máximo de recursos que [!DNL Workfront Fusion] devolverá durante un ciclo de ejecución. El valor predeterminado de este campo es 100. Este módulo puede devolver más álbumes que este límite si varios álbumes en el límite del límite tienen el mismo valor <code>name_after</code>.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Actualizar álbum

Este módulo de acción actualiza el álbum especificado.

El álbum actualizado debe haber sido creado por la misma aplicación cliente que ahora lo está actualizando y debe ser del subtipo `project` o `project_set`.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Lightroom], consulte <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Crear una conexión con [!DNL Adobe Lightroom]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo que contiene el álbum que desea actualizar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Album ID]</td>
      <td>
        <p>Introduzca o asigne el ID del álbum que desea actualizar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">Otros campos</td>
      <td>
      <td>Para obtener descripciones de otros campos de este módulo, consulte <a href="#create-an-album" class="MCXref xref" >Crear un álbum</a> en este artículo.</td>
      </td>
    </tr>
  </tbody>
</table>
