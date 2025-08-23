---
title: Módulos Bynder
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan  [!DNL Bynder], así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: 0a45f8a7-12cc-41cc-9135-92f4779afac0
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1847'
ht-degree: 70%

---

# Módulos de [!DNL Bynder]

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!DNL Bynder], así como conectarlo a varias aplicaciones y servicios de terceros.

Para obtener instrucciones sobre cómo crear un escenario, vea los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

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
   <p>Actual: Su organización debe comprar Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Para usar módulos [!DNL Bynder], debe tener una cuenta de [!DNL Bynder].

## Información de API de Bynder

El conector Bynder utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> v4 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.25.21</td> 
  </tr>
 </tbody> 
 </table>

## Conexión de [!DNL Bynder] a Workfront Fusion  {#connect-bynder-to-workfront-fusion}

>[!NOTE]
>
>Bynder utiliza el tipo de concesión de código de autorización o token de actualización. Este es el único tipo de concesión que utiliza el conector Fusion Bynder.

* [Crear una conexión con  [!DNL Bynder] desde Workfront Fusion](#create-a-connection-to-bynder-from-workfront-fusion)
* [Generar un [!UICONTROL ID de cliente] y [!UICONTROL Secreto de cliente] en [!DNL Bynder] (opcional)](#generate-a-client-id-and-client-secret-in-bynder-optional)

### Crear una conexión con [!DNL Bynder] desde Workfront Fusion

Puede crear una conexión desde Workfront Fusion a su cuenta de [!DNL Bynder] directamente desde un módulo de [!DNL Bynder].

1. En cualquier módulo de [!DNL Bynder], haga clic en **[!UICONTROL Añadir]** junto al campo [!UICONTROL Conexión].
1. Seleccione el dominio de [!DNL Bynder] al que desea conectarse.
1. (Opcional) Haga clic en **[!UICONTROL Ajustes avanzados]** y, a continuación, introduzca su [!UICONTROL ID de cliente] y [!UICONTROL Secreto de cliente].

   Para obtener instrucciones sobre cómo generar el ID de cliente y el Secreto de cliente, consulte [Generar un ID de cliente y un Secreto de cliente en [!DNL Bynder] (opcional)](#generate-a-client-id-and-client-secret-in-bynder-optional) en este artículo.

1. En la ventana de [!UICONTROL inicio de sesión], introduzca su nombre de usuario (dirección de correo electrónico) y contraseña.
1. Haga clic en **[!UICONTROL Continuar]** para crear la conexión y volver al módulo.

### Generar un [!UICONTROL ID de cliente] y [!UICONTROL Secreto de cliente] en [!DNL Bynder] (opcional)

Si desea crear una conexión utilizando el ID de cliente y el Secreto de cliente, puede generarlos desde su cuenta de [!DNL Bynder]. El ID de cliente y el Secreto de cliente se generan al crear una aplicación en [!DNL Bynder].

Para obtener instrucciones para crear una aplicación en [!DNL Bynder], consulte [Aplicaciones de Oauth 2.0](https://developer-docs.bynder.com/api/authentication-oauth2-oauth-apps/) en la documentación de [!DNL Bynder].

>[!NOTE]
>
>* Al crear la aplicación en [!DNL Bynder], escriba lo siguiente como `redirect uri`:
>
>   * clúster de EE. UU.: `https://app.workfrontfusion.com/oauth/cb/workfront-bynder`
>   * Clúster de la UE: `https://app-eu.workfrontfusion.com/oauth/cb/workfront-bynder`
>   * clúster de Azure: `https://app-az.workfrontfusion.com/oauth/cb/workfront-bynder`
>* Bynder utiliza el tipo de concesión de código de autorización o token de actualización. Este es el único tipo de concesión que utiliza el conector Fusion Bynder.

## Módulos de [!DNL Bynder] y sus campos

Al configurar módulos de [!DNL Bynder], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL Bynder] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Acciones](#actions)
* [Búsquedas](#searches)
* [Activadores](#triggers)

### Acciones

* [[!UICONTROL Añadir una etiqueta a los recursos]](#add-a-tag-to-assets)
* [[!UICONTROL Añadir recursos a una colección]](#add-assets-to-a-collection)
* [[!UICONTROL Llamada de API personalizada]](#custom-api-call)
* [[!UICONTROL Descargar recurso]](#download-asset)
* [[!UICONTROL Leer metadatos de recursos]](#read-asset-metadata)
* [[!UICONTROL Quitar una etiqueta] de los recursos](#remove-a-tag-from-assets)
* [[!UICONTROL Quitar recursos de la colección]](#remove-assets-from-collection)
* [[!UICONTROL Actualizar metadatos de recursos]](#update-asset-metadata)
* [[!UICONTROL Cargar recurso]](#upload-asset)

#### [!UICONTROL Añadir una etiqueta a los recursos]

Este módulo de acción agrega una etiqueta a uno o varios recursos

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Bynder] a Workfront Fusion, consulte <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Bynder] a Workfront Fusion </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tag ID]</td> 
   <td> <p>Introduzca o asigne el ID de la etiqueta que desea añadir a los recursos.</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset IDs]</td> 
   <td> <p>Para cada recurso que desee etiquetar, haga clic en <strong>[!UICONTROL Add item]</strong> y, a continuación, escriba o asigne el ID del recurso.</p> </td> 
  </tr> 
 </tbody> 
 </table>

#### [!UICONTROL Añadir recursos a una colección]

Este módulo de acción añade uno o más recursos a una colección.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Bynder] a Workfront Fusion, consulte <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Bynder] a Workfront Fusion </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collection ID]</td> 
   <td> <p>Introduzca o asigne el ID de la colección a la que desea añadir recursos.</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset IDs]</td> 
   <td> <p>Para cada recurso que desee añadir a la colección, haga clic en <strong>[!UICONTROL Add item]</strong> y, a continuación, escriba o asigne el ID del recurso.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Llamada de API personalizada]

Este módulo de acción le permite realizar una llamada autenticada personalizada a la API [!DNL Bynder]. De este modo, puede crear una automatización del flujo de datos imposibles de realizar por los otros [!DNL Bynder] módulos.

Al configurar este módulo, se muestran los campos siguientes.

El módulo devuelve un código de estado, junto con los encabezados y el cuerpo de la llamada de API.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Bynder] a Workfront Fusion, consulte <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Bynder] a Workfront Fusion </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>Escriba una ruta relativa a <code>https://{your-bynder-domain}/api/{api-version}/</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion añade los encabezados de autorización para usted.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Añada la consulta para la llamada de API en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"name":"something-urgent"}</code></p> </td> 
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

#### [!UICONTROL Descargar recurso]

Este módulo de acción descarga un solo recurso.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Bynder] a Workfront Fusion, consulte <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Bynder] a Workfront Fusion </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td>Introduzca o asigne el ID del recurso que desea descargar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset version]</td> 
   <td> <p>Introduzca o asigne la versión del recurso que desea descargar. Para descargar la última versión del recurso, deje el campo vacío.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Leer metadatos de recursos]

Este módulo de acción lee los metadatos de un recurso.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Bynder] a Workfront Fusion, consulte <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Bynder] a Workfront Fusion </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td>Introduzca o asigne el ID del recurso para el que desea recuperar los metadatos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Seleccione la información que desea incluir en el paquete de salida para este módulo.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Quitar una etiqueta de los recursos]

Este módulo de acción elimina una etiqueta de uno o varios recursos

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Bynder] a Workfront Fusion, consulte <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Bynder] a Workfront Fusion </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tag ID]</td> 
   <td> <p>Introduzca o asigne el ID de la etiqueta que desea quitar de los recursos.</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset IDs]</td> 
   <td> <p>Para cada recurso del que desee quitar una etiqueta, haga clic en <strong>[!UICONTROL Add item]</strong> y, a continuación, escriba o asigne el ID del recurso.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Quitar recursos de la colección]

Este módulo de acción quita uno o varios recursos de una colección.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Bynder] a Workfront Fusion, consulte <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Bynder] a Workfront Fusion </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collection ID]</td> 
   <td> <p>Introduzca o asigne el ID de la colección en la que desea quitar los recursos.</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset IDs]</td> 
   <td> <p>Para cada recurso que desee quitar de la colección, haga clic en <strong>[!UICONTROL Add item]</strong> y, a continuación, escriba o asigne el ID del recurso.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Actualizar metadatos de recursos]

Este módulo de acción actualiza los metadatos de un recurso existente.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Bynder] a Workfront Fusion, consulte <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Bynder] a Workfront Fusion </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td>Introduzca o asigne el ID del recurso para el que desea actualizar los metadatos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td> <p>Seleccione los campos para los que desea introducir información y, a continuación, introduzca o asigne la información con la que desea actualizar los metadatos en esos campos. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Metaproperties]</p> </td> 
   <td>Seleccione las opciones que desea actualizar y, a continuación, introduzca o asigne la información en esas propiedades. Las metapropiedades son información sobre el recurso que no representa campos específicos en el recurso.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Cargar recurso]

Este módulo de acción carga un solo recurso.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Bynder] a Workfront Fusion, consulte <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Bynder] a Workfront Fusion </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Save as]</td> 
   <td> <p>Seleccione cómo desea guardar el archivo que está cargando.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL New asset]</strong> </p> <p>Seleccione los campos y las metapropiedades para los que desea introducir información y, a continuación, escriba la información en esos campos.</p> <p>Introduzca o asigne el ID de la marca que desea utilizar para el recurso cargado.</p> </li> 
     <li> <p><strong>[!UICONTROL New asset version]</strong> </p> <p>Introduzca el ID del recurso para el que está cargando una nueva versión.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Carga asincrónica de archivos]</td> 
   <td>Active esta opción al cargar archivos grandes. Esto evita que los archivos grandes bloqueen la ejecución de escenarios.</td> 
  </tr> 
 </tbody> 
</table>

### Búsquedas

* [[!UICONTROL Enumerar registro]](#list-record)
* [[!UICONTROL Buscar en Assets]](#search-assets)

#### [!UICONTROL Enumerar registro]

Este módulo de búsqueda recupera todos los elementos de un tipo específico.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Bynder] a Workfront Fusion, consulte <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Bynder] a Workfront Fusion </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro que desea enumerar. </p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Read all collections]</strong> </p> </li> 
     <li> <p><strong>[!UICONTROL Read information about all tags]</strong> </p> </li> 
     <li> <p><strong>[!UICONTROL Read all assets of a collection]</strong> </p> <p>Introduzca o asigne el ID de la colección de la que desea enumerar los recursos.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Seleccione los campos que desea incluir en la salida del módulo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de recursos que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Buscar en Assets]

Este módulo de búsqueda busca recursos en función de los criterios suministrados.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Bynder] a Workfront Fusion, consulte <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Bynder] a Workfront Fusion </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search criteria]</td> 
   <td> <p>Introduzca los criterios de búsqueda. </p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Field]</strong> </p> <p>Seleccione el campo que desea utilizar en la búsqueda</p> </li> 
     <li> <p><strong>[!UICONTROL Logical Operator]</strong> </p> <p>Seleccione el operador que desea utilizar en la búsqueda.</p> </li> 
     <li> <p><strong>[!UICONTROL Value]</strong> </p> <p>Introduzca o asigne el valor que desea buscar en el campo seleccionado. El tipo de valor debe ser el mismo que el tipo de datos del campo seleccionado. </p> <p>Para obtener más información sobre los tipos de datos, vea <a href="/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md" class="MCXref xref">Tipos de datos de elementos</a>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Result set]</td> 
   <td>Seleccione si desea devolver el primer recurso coincidente o todos los recursos coincidentes.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort by]</td> 
   <td> <p>Seleccione el campo por el que desea ordenar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort Direction]</td> 
   <td> <p>Seleccione si desea ordenar de forma ascendente o descendente.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Seleccione los campos que desea incluir en la salida del módulo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de recursos que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Activadores

#### [!UICONTROL Ver recursos]

Este módulo activador inicia un escenario cuando se crea o actualiza un recurso.

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Bynder] a Workfront Fusion, consulte <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Bynder] a Workfront Fusion </a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">Tipo de evento</td>
    <td>Seleccione si desea iniciar el escenario cuando se cree un nuevo recurso o cuando se actualice un recurso existente.</td>
  </tr> 
  <tr>
     <td role="rowheader">[!UICONTROL Collections]</td>
   <td> <p>Seleccione la colección que desea supervisar en busca de nuevos recursos. Para ver todas las colecciones, deje este campo vacío.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">Salidas</td>
    <td>Seleccione los campos que desea incluir en la salida.</td>
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Limit]</td>

<td> <p>Introduzca el número máximo de registros que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>
