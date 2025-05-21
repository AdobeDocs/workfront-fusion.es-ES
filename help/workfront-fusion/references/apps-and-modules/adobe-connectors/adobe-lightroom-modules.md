---
title: Módulos de Adobe Lightroom
description: Con los módulos de Adobe Lightroom, puede iniciar un escenario de Adobe Workfront Fusion basado en los eventos de su cuenta de Adobe Lightroom.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 3f29ab35-7a90-4afb-a283-4faaacec5b15
source-git-commit: 4d31a447d0d8d91ef4f86d8fd0bc63663b0f5ad0
workflow-type: tm+mt
source-wordcount: '2770'
ht-degree: 21%

---

# Módulos de [!DNL Adobe Lightroom]

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!DNL Adobe Lightroom], así como conectarlo a varias aplicaciones y servicios de terceros.

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

Antes de poder usar el conector de [!DNL Adobe Lightroom], debe asegurarse de que se cumplen los siguientes requisitos previos:

* Debe tener una cuenta de [!DNL Adobe Lightroom] activa.
* Debe tener una aplicación web de OAuth configurada en Adobe Admin Console. Para obtener más información, consulte [Configuración de una aplicación OAuth en Adobe Admin Console](#configure-an-oauth-application-in-the-adobe-admin-console) en este artículo.

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

Para conectarse a Adobe Lightroom, primero debe configurar una aplicación OAuth en Adobe Admin Console. Una vez configurada esta aplicación, puede crear conexiones desde Workfront Fusion.

### Configuración de una aplicación OAuth en Adobe Admin Console

1. Comience a configurar una aplicación web de OAuth en Adobe Admin Console.

   Para obtener instrucciones, consulte [Guía de implementación de autenticación de usuario](https://developer.adobe.com/developer-console/docs/guides/authentication/UserAuthentication/implementation) en la documentación para desarrolladores de Adobe.
1. Al configurar OAuth Web App, introduzca los siguientes valores:

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">[!UICONTROL Scopes]</td>
        <td>
          <ul>
            <li>Adobe ID</li>
            <li>lr_partner_rendition_apis</li>
            <li>opénido</li>
            <li>offline_access</li>
            <li>lr_partner_apis</li>
          </ul>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL URI de redireccionamiento]</td>
        <td><code>https://app.workfrontfusion.com/oauth/cb/adobe-lightroom5</code></td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Patrón URI de redireccionamiento]</td>
        <td><code>https://app\.workfrontfusion\.com/oauth/cb/adobe-lightroom5</code></td>
        </tr>
      </tbody>
    </table>

### Creación de una conexión a Adobe Lightroom desde Workfront Fusion

Para crear una conexión para los módulos de [!DNL Adobe Lightroom]:

1. En cualquier módulo de Adobe Lightroom, haga clic en **[!UICONTROL Agregar]** junto al cuadro Conexión.

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
        <td>Introduzca el [!UICONTROL Adobe] [!UICONTROL Client ID]. Esto se puede encontrar en la sección de detalles de [!UICONTROL Credentials] del [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Escriba su [!UICONTROL Client Secret] de [!DNL Adobe]. Esto se puede encontrar en la sección de detalles de [!UICONTROL Credentials] del [!DNL Adobe Developer Console]</td>
        </tr>
      </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.


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
        <p>Si desea proporcionar credenciales específicas para asegurarse de que se está ejecutando un servidor específico, haga clic en <b>Agregar elemento</b> e introduzca las credenciales.</p><p>Los encabezados de autorización se añaden automáticamente.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Recuperar metadatos del catálogo de usuarios

Este módulo de acción recupera metadatos de un catálogo en Adobe Lightroom. Un catálogo contiene recursos, álbumes u otros recursos.

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

* [Crear un archivo original de recurso](#create-an-asset-original-file)
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
      <td role="rowheader">[!UICONTROL ID de catálogo]</td>
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
      <td role="rowheader">[!UICONTROL Longitud del contenido en bytes]</td>
      <td>
        <p>Introduzca o asigne la longitud del contenido en bytes.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Rango de bytes]</td>
      <td>
        <p>Introduzca o asigne el rango de bytes para la solicitud, incluidos los bytes primero y último y la longitud de entidad definida en RFC 2616. Esta información debe incluirse únicamente cuando los datos sean demasiado grandes para cargarse en una sola llamada.</p>
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
      <td role="rowheader">[!UICONTROL ID de catálogo]</td>
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
      <td role="rowheader">[!UICONTROL Tipo de recurso]</td>
      <td>
        <p>Seleccione si el recurso es una imagen o un vídeo.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Fecha y hora de creación del usuario]</td>
      <td>
        <p>Escriba o asigne una fecha con el formato <code>YYYY-MM-DDT00:00:00-00:00</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Fecha y hora de actualización del usuario]</td>
      <td>
        <p>Escriba o asigne una fecha con el formato <code>YYYY-MM-DDT00:00:00-00:00</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Fecha de captura]</td>
      <td>
        <p>Escriba o asigne la fecha de captura del recurso con el formato <code>YYYY-MM-DDT00:00:00-00:00</code>. El servidor establecerá esto si la fecha capturada está establecida en <code>0000-00-00T00:00:00</code>. </p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL File name]</td>
      <td>
        <p>Introduzca o asigne el nombre de archivo del recurso que está importando a Lightroom.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Nombre del dispositivo importado en]</td>
      <td>
        <p>Escriba o asigne el nombre del dispositivo que importa el recurso.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL ID de cuenta del usuario que importó]</td>
      <td>
        <p>Introduzca o asigne el ID del usuario que importa el recurso.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Importar marca de tiempo]</td>
      <td>
        <p>Escriba o asigne una fecha con el formato <code>YYYY-MM-DDT00:00:00-00:00</code>.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Crear un archivo de configuración de desarrollo de XMP externo de recursos

Este módulo de acción admite dos flujos de trabajo: cargar el archivo de configuración de desarrollo de XMP externo para el recurso o crear un archivo de configuración de desarrollo de XMP externo copiando del archivo de configuración de desarrollo de xmp externo de otro recurso.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Lightroom], consulte <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Crear una conexión con [!DNL Adobe Lightroom]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Longitud de contenido en bytes]</td>
      <td>
        <p>Introduzca o asigne la longitud del contenido en bytes.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Cargar nuevo o copiar XMP/desarrollar archivo]</td>
      <td>
        <p>Seleccione si desea cargar un archivo nuevo o copiar un archivo de un recurso existente.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL ID de catálogo]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo en el que desea crear el recurso.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>Introduzca o asigne el ID del recurso en el que desea cargar o copiar un archivo.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Vínculo a XMP/desarrollar archivo]</td>
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
      <td role="rowheader">[!UICONTROL Tipo(s) de representación (separados por punto y coma)]</td>
      <td>
        <p>Introduzca el tipo de representación para la representación que desea crear. Si introduce más de un tipo, sepárelos con punto y coma (;). <p>Tipos posibles:</p><ul><li><code>fullsize</code></li><li><code>2560</code></li></ul></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Longitud del contenido en bytes]</td>
      <td>
        <p>Introduzca o asigne la longitud del contenido en bytes.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL ID de catálogo]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo en el que desea generar las representaciones.</p>
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
      <td role="rowheader">[!UICONTROL ID de catálogo]</td>
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
      <td role="rowheader">[!UICONTROL ID de catálogo]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo que contiene el recurso asociado al archivo de configuración de desarrollo de XMP.</p>
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
      <td role="rowheader">[!UICONTROL ID de catálogo]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo que contiene el recurso para el que desea recuperar una representación.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>Introduzca o asigne el ID del recurso para el que desea recuperar una representación.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Tipo de representación]</td>
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
      <td role="rowheader">[!UICONTROL ID de catálogo]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo que contiene el recurso.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Marca de tiempo de inicio]</td>
      <td>
        <p>Introduzca o asigne una marca de tiempo. El módulo devuelve los registros que se han actualizado después de esta marca de tiempo.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Devolver recursos capturados antes de un tiempo determinado]</td>
      <td>
        <p>Escriba una fecha con el formato <code>YYYY-MM-DDT00:00:00</code>. El módulo devuelve los resultados capturados antes de esta fecha.</p><p> Este campo no se puede usar con el campo <code>Return assets captured after given time</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Devolver recursos capturados después de un tiempo determinado]</td>
      <td>
        <p>Escriba una fecha con el formato <code>YYYY-MM-DDT00:00:00</code>. El módulo devuelve los resultados capturados antes de esta fecha.</p><p> Este campo no se puede usar con el campo <code>Return assets captured before given time</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Número máximo de recursos devueltos]</td>
      <td>
        <p>Introduzca el número máximo de registros que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL SHA256 Valor hash del archivo original]</td>
      <td>
        <p>Introduzca o asigne el valor hash del archivo original. Se devuelven Assets con un hash coincidente.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL ¿Ocultar recursos que están dentro de pilas?"]</td>
      <td>
        <p>Seleccione Sí para ocultar los recursos de las pilas (no se devolverán los recursos de las pilas). Seleccione No para incluir recursos dentro de las pilas en los resultados.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Valores de subtipo de recurso]</td>
      <td>
        <p>Introduzca o asigne una lista de valores de subtipo separados por punto y coma para que se devuelvan.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset IDs]</td>
      <td>
        <p>Introduzca o asigne hasta 100 ID de recurso, separados por comas.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Tipos de recursos que se excluirán]</td>
      <td>
        <p>Seleccione si desea excluir los recursos completos o incompletos. Para incluir todos los recursos, deje este campo en blanco.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Valores de grupo]</td>
      <td>
        <p>Escriba o asigne una lista de valores de grupo separados por punto y coma.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Name values]</td>
      <td>
        <p>Introduzca o asigne una lista de valores de nombre separados por punto y coma.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Estado favorito]</td>
      <td>
        <p>Introduzca o asigne el estado favorito para el que desea obtener resultados.</p>
      </td>
    </tr>
    </tr>
  </tbody>
</table>

<!--BECKY START HERE-->

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
      <td role="rowheader">[!UICONTROL ID de catálogo]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo que contiene el álbum al que desea agregar recursos.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL ID de álbum]</td>
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
      <td role="rowheader">[!UICONTROL ¿Es este recurso una portada de álbum?]</td>
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
      <td role="rowheader">[!UICONTROL ID remoto]</td>
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
      <td role="rowheader">[!UICONTROL ID de catálogo]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo en el que desea crear un álbum.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL ID de álbum]</td>
      <td>
        <p>Introduzca o asigne un ID para el nuevo álbum.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Subtipo]</td>
      <td>
        <p>Seleccione el subtipo del álbum.</p>
      </td>
    <tr>
      <td role="rowheader">Clave de API [!UICONTROL]</td>
      <td>
        <p>Introduzca la clave API del servicio que está creando el álbum.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Fecha y hora de creación del usuario]</td>
      <td>
        <p>Escriba o asigne una fecha con el formato <code>YYYY-MM-DDT00:00:00-00:00Z</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Fecha y hora de actualización del usuario]</td>
      <td>
        <p>Escriba o asigne una fecha con el formato <code>YYYY-MM-DDT00:00:00-00:00Z</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Nombre del álbum]</td>
      <td>
        <p>Introduzca o asigne un nombre para el nuevo álbum.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL ID de portada]</td>
      <td>
        <p>Introduzca o asigne el ID de un recurso para utilizarlo como portada de este álbum.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL ID remoto]</td>
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
      <td role="rowheader">[!UICONTROL Fecha de actualización]</td>
      <td>
        <p>Escriba o asigne una fecha con el formato <code>YYYY-MM-DDT00:00:00-00:00Z</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL ¿Se ha eliminado el álbum?]</td>
      <td>
        <p>Active esta opción si se ha eliminado el contenido afiliado externo.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL de la ubicación para editar contenido afiliado]</td>
      <td>
        <p>Si hay una URL donde los usuarios pueden editar el contenido de este álbum, ingrese la URL aquí.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL de la ubicación para ver el contenido afiliado]</td>
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
      <td role="rowheader">[!UICONTROL ID de catálogo]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo que contiene el álbum que desea eliminar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL ID de álbum]</td>
      <td>
        <p>Introduzca o asigne el ID del álbum que desea eliminar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL ¿Desea eliminar los álbumes secundarios?]</td>
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
      <td role="rowheader">[!UICONTROL ID de catálogo]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo que contiene el álbum que desea recuperar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL ID de álbum]</td>
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
      <td role="rowheader">[!UICONTROL ID de catálogo]</td>
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
      <td role="rowheader">[!UICONTROL Nombre del álbum que precederá a los resultados actuales]</td>
      <td>
        <p>Si está paginando los resultados, escriba o asigne el nombre del último álbum de la página anterior.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Número máximo de álbumes devueltos]</td>
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
      <td role="rowheader">[!UICONTROL ID de catálogo]</td>
      <td>
        <p>Introduzca o asigne el ID del catálogo que contiene el álbum que desea actualizar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL ID de álbum]</td>
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
