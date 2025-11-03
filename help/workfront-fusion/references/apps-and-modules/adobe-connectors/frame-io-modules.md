---
title: Módulos Frame.io (heredados)
description: La cuenta de  [!DNL Adobe Workfront Fusion Frame].io modules enable you to monitor, create, update, retrieve, or delete assets and comments in your [!DNL Frame.io] .
author: Becky
feature: Workfront Fusion
exl-id: 121b145c-d04d-44b9-b673-ea2928e2346d
source-git-commit: 1929bf897e9263ec551e93df776b96f419436715
workflow-type: tm+mt
source-wordcount: '2666'
ht-degree: 63%

---

# [!DNL Frame.io] módulos heredados

>[!IMPORTANT]
>
>Este artículo describe la versión heredada del conector Frame.io. Este conector se utiliza para conectarse a Frame.io versión 3.
>
>Para obtener instrucciones sobre la nueva versión (beta) del conector Frame.io, consulte [Conector Frame.io de Beta](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/frame-io-modules-new.md).

Los módulos de Adobe Workfront Fusion [!DNL Frame.io] le permiten supervisar, crear, actualizar, recuperar o eliminar recursos y comentarios en su cuenta de [!DNL Frame.io].

Workfront ofrece dos conectores Frame.io, basados en la versión de Frame.io a la que se está conectando.

| Conector | Versión de Frame.io |
|---|---|
| Frame.io (Beta) | V4 |
| Frame.io (heredado) | V3 |

Para obtener instrucciones sobre la nueva versión del conector Frame.io, consulte [Conector Frame.io de Beta](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/frame-io-modules-new.md).

Para ver un vídeo introductorio del conector Frame.io, consulte:

* [Frame.io](https://video.tv.adobe.com/v/3427032/){target=_blank}

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

Para usar módulos [!DNL Frame.io], debe tener una cuenta de [!DNL Frame.io]

## Información de la API Frame.io

El conector Frame.io utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Dirección URL base</td> 
   <td> https://api.frame.io/v2</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> Versión 2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.0.76</td> 
  </tr>
 </tbody> 
 </table>

## Conectar [!DNL Frame.io] a [!UICONTROL Adobe Workfront Fusion]

Puede conectarse a [!DNL Frame.io] mediante un token de API o mediante OAuth 2.0.

[Conectarse a  [!DNL Frame.io]  mediante un token de API](#connect-to-frameio-using-an-api-token)

[Conectarse a  [!DNL Frame.io]  mediante OAuth 2.0 PKCE](#connect-to-frameio-using-oauth-20-pkce)

### Conectarse a [!DNL Frame.io] mediante un token de API

Para conectar su cuenta de [!DNL Frame.io] a Workfront Fusion mediante un token de API, debe crear el token de API en su cuenta de [!DNL Frame.io] e insertarlo en el cuadro de diálogo de Workfront Fusion [!DNL Frame.io] [!UICONTROL Crear una conexión].

1. Inicie sesión en la cuenta de [!DNL Frame.io].
1. Vaya a la página **[!UICONTROL Tókenes]** del desarrollador de [!DNL Frame.io].
1. Haga clic en **[!UICONTROL Nuevo]**.
1. Introduzca el nombre del token, seleccione los ámbitos que desee usar y haga clic en **[!UICONTROL Crear]**.
1. Copie el token proporcionado.
1. Vaya a Workfront Fusion y abra el diálogo [!DNL Frame.io]Crear una conexión **[!UICONTROL del módulo]**.
1. En el campo **[!UICONTROL Tipo de conexión]**, seleccione **[!DNL Frame.io]**.
1. Escriba el token que copió en el paso 5 en el campo **[!UICONTROL Su clave de API [!DNL Frame.io]]**
1. Haga clic en **[!UICONTROL Continuar]** para establecer la conexión y volver al módulo.

### Conectarse a [!DNL Frame.io] mediante OAuth 2.0 PKCE

Puede crear una conexión a [!DNL Frame.io] mediante OAuth 2.0 PKCE con un ID de cliente opcional. Si desea incluir un ID de cliente en la conexión, debe crear una aplicación OAuth 2.0 en la cuenta de [!DNL Frame.io].

* [Conectarse a  [!DNL Frame.io]  mediante OAuth 2.0 PKCE (sin ID de cliente)](#connect-to-frameio-using-using-oauth-20-pkce-without-client-id)
* [Conectarse a  [!DNL Frame.io]  mediante OAuth 2.0 PKCE (con ID de cliente)](#connect-to-frameio-using-using-oauth-20-pkce-with-client-id)

#### Conectarse a [!DNL Frame.io] mediante OAuth 2.0 PKCE (sin ID de cliente)

1. Vaya a Workfront Fusion y abra el diálogo [!DNL Frame.io]Crear una conexión **[!UICONTROL del módulo]**.
1. En el campo **[!UICONTROL Tipo de conexión]**, seleccione **[!UICONTROL [!DNL Frame.io]OAuth 2.0 PKCE]**.
1. Escriba un nombre para la nueva conexión en el campo **[!UICONTROL Nombre de conexión]**.
1. Haga clic en **[!UICONTROL Continuar]** para establecer la conexión y volver al módulo.

#### Conexión a [!DNL Frame.io] mediante OAuth 2.0 PKCE (con ID de cliente)

1. Crear una aplicación OAuth 2.0 en [!DNL Frame.io]. Para obtener instrucciones, consulte la documentación de [!DNL Frame.io] en [!UICONTROL Flujo de autorización de código de OAuth 2.0].

   >[!IMPORTANT]
   >
   >Al crear la aplicación OAuth 2.0 en [!DNL Frame.io]:
   >
   >* Introduzca lo siguiente como URI de redireccionamiento:
   >   
   >     * **América / APAC**: `https://app.workfrontfusion.com/oauth/cb/frame-io5`
   >
   >     * **EMEA**: `https://app-eu.workfrontfusion.com/oauth/cb/frame-io5`
   >
   >* Habilite la opción PCKE.


1. Copie el `client_id` proporcionado.
1. Vaya a Workfront Fusion y abra el diálogo [!DNL Frame.io]Crear una conexión **[!UICONTROL del módulo]**.
1. En el campo **[!UICONTROL Tipo de conexión]**, seleccione **[!UICONTROL [!DNL Frame.io]OAuth 2.0 PKCE]**.
1. Escriba un nombre para la nueva conexión en el campo **[!UICONTROL Nombre de conexión]**.
1. Haga clic en **[!UICONTROL Mostrar ajustes avanzados]**.
1. Escriba el `client_id` que copió en el paso 2 en el campo **[!UICONTROL Client ID]**.
1. Haga clic en **[!UICONTROL Continuar]** para establecer la conexión y volver al módulo.

## Módulos de [!DNL Frame.io] y sus campos

Al configurar módulos de [!DNL Frame.io], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL Frame.io] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Recursos](#assets)
* [Comentarios](#comments)
* [Proyectos](#projects)
* [Otro](#other)

### Recursos

* [[!UICONTROL Crear un recurso]](#create-an-asset)
* [[!UICONTROL Eliminar un recurso]](#delete-an-asset)
* [[!UICONTROL Obtener un recurso]](#get-an-asset)
* [[!UICONTROL Lista de recursos]](#list-assets)
* [[!UICONTROL Actualizar un recurso]](#update-an-asset)
* [[!UICONTROL Ver recurso eliminado]](#watch-asset-deleted)
* [[!UICONTROL Ver etiqueta de recurso actualizado]](#watch-asset-label-updated)
* [[!UICONTROL Ver nuevo recurso]](#watch-new-asset)

#### [!UICONTROL Crear un recurso]

Este módulo de acción crea un nuevo recurso.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Seleccione o asigne el equipo propietario del proyecto para el que desea crear un recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Seleccione el proyecto o asigne el ID del proyecto para el que desea crear un recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>Seleccione la carpeta o asigne el ID de la carpeta en la que desea crear un recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type] </td> 
   <td> <p>Seleccione si desea crear una carpeta o un archivo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>Introduzca el nombre del nuevo archivo o carpeta.</p> </td> 
  </tr> <!--
   <tr> 
    <td role="rowheader">File Type </td> 
    <td> <p>Select the type of file you want to upload.</p> </td> 
   </tr>
  --> <!--
   <tr> 
    <td role="rowheader">File Size </td> 
    <td> <p>The file size in bytes.</p> </td> 
   </tr>
  --> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source URL] </td> 
   <td> <p>Si crea un archivo, introduzca la dirección URL del archivo que desea cargar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description] </td> 
   <td> <p>Si crea un archivo, introduzca una breve descripción del recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Etiqueta] </td> 
   <td> <p>Si crea un archivo, seleccione si el archivo está en curso, si necesita revisión o si está aprobado.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Eliminar un recurso]

Este módulo de acción elimina un recurso especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Seleccione o asigne el equipo propietario del proyecto que contiene el recurso que desea eliminar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p> Seleccione el proyecto que contiene el recurso que desea eliminar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>Seleccione la carpeta que contiene el recurso que desea eliminar</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Seleccione o asigne el recurso que desea eliminar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Obtener un recurso]

Este módulo de acción recupera los detalles de un recurso.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Seleccione o asigne el equipo propietario del proyecto que contiene el recurso cuyos detalles desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p> Seleccione el proyecto que contiene el recurso cuyos detalles desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>Seleccione la carpeta que contiene el recurso cuyos detalles desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Seleccione el recurso o asigne el ID del recurso cuyos detalles desea recuperar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Lista de recursos]

Este módulo de búsqueda recupera todos los recursos de la carpeta en el proyecto especificado.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Seleccione o asigne el equipo propietario del proyecto que contiene la carpeta cuyos recursos desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p> Seleccione el proyecto que contiene la carpeta cuyos recursos desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>Seleccione la carpeta cuyos recursos desea enumerar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Introduzca o asigne el número máximo de recursos que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Actualizar un recurso]

Este módulo de acción le permite actualizar el nombre, la descripción o los campos personalizados de un recurso existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Seleccione o asigne el equipo propietario del proyecto cuyo recurso desea actualizar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Seleccione el proyecto o asigne el ID del proyecto para el que desea actualizar un recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>Seleccione la carpeta o asigne el ID de la carpeta en la que desea actualizar un recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Introduzca o asigne el ID del recurso que desea actualizar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>Introduzca el nombre del archivo actualizado.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description] </td> 
   <td> <p>Introduzca una breve descripción del recurso actualizado.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Ver recurso eliminado]

Este módulo de déclencheur inicia un escenario cuando se elimina un recurso que pertenece al equipo especificado.

Como se trata de un déclencheur instantáneo, debe seleccionar o crear un webhook para que lo utilice el módulo.

Si agrega un gancho web, escriba la siguiente información.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name]</td> 
   <td> <p> Escriba un nombre para el webhook, como "Recurso eliminado".</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Seleccione el equipo para el que se crea este webhook.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Ver etiqueta de recurso actualizado]

Este módulo de déclencheur inicia un escenario en el que la etiqueta de un recurso propiedad del equipo especificado se establece, cambia o elimina.

Como se trata de un déclencheur instantáneo, debe seleccionar o crear un webhook para que lo utilice el módulo.

Si agrega un gancho web, escriba la siguiente información.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name]</td> 
   <td> <p> Introduzca un nombre para el webhook, como "Estado del recurso actualizado".</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Seleccione el equipo para el que se crea este webhook.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Ver nuevo recurso]

Este módulo de déclencheur inicia un escenario cuando se crea un nuevo recurso para el equipo especificado.

Como se trata de un déclencheur instantáneo, debe seleccionar o crear un webhook para que lo utilice el módulo.

Si agrega un gancho web, escriba la siguiente información.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name]</td> 
   <td> <p> Introduzca un nombre para el webhook, como "Recurso creado".</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Seleccione el equipo para el que se crea este webhook.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Comentarios

* [[!UICONTROL Crear un comentario]](#create-a-comment)
* [[!UICONTROL Eliminar un comentario]](#delete-a-comment)
* [[!UICONTROL Obtener un comentario]](#get-a-comment)
* [[!UICONTROL Enumerar comentarios]](#list-comments)
* [[!UICONTROL Actualizar un comentario]](#update-a-comment)
* [[!UICONTROL Ver comentario actualizado]](#watch-comment-updated)
* [[!UICONTROL Ver nuevo comentario]](#watch-new-comment)

#### [!UICONTROL Crear un comentario]

Este módulo de acción añade un nuevo comentario o respuesta al recurso.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type] </td> 
   <td> <p>Seleccione si desea crear un comentario o responder a un comentario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Seleccione o asigne el equipo propietario del proyecto que contiene el recurso al que desea añadir un comentario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Seleccione el proyecto o asigne el ID del proyecto que contiene el recurso al que desea añadir un comentario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>Seleccione la carpeta o asigne el ID de la carpeta que contiene el recurso al que desea añadir un comentario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Seleccione o asigne el recurso al que desea añadir un comentario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>Seleccione o asigne el comentario al que desea añadir una respuesta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text]</td> 
   <td> <p> Introduzca el contenido de texto del comentario o la respuesta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Timestamp] </td> 
   <td> <p>Introduzca el número de fotograma en el vídeo al que debe vincularse el comentario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Eliminar un comentario]

Este módulo de acción elimina un comentario existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID]</td> 
   <td> <p> Seleccione o asigne el equipo propietario del proyecto que contiene el recurso del que desea eliminar un comentario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p> Seleccione el proyecto o asigne el ID del proyecto que contiene el recurso del que desea eliminar un comentario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID]</td> 
   <td> <p> Seleccione la carpeta que contiene el recurso del que desea eliminar un comentario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Introduzca o asigne el ID del recurso que contiene el comentario que desea eliminar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>Introduzca o asigne el ID del comentario que desea eliminar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Obtener un comentario]

Este módulo de acción recupera los detalles del comentario especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Seleccione o asigne el equipo propietario del proyecto que contiene la carpeta de la que desea recuperar los recursos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Seleccione el proyecto que contiene la carpeta cuyos recursos desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>Seleccione la carpeta cuyos recursos desea enumerar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Seleccione el recurso que contiene el comentario que desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>Seleccione el comentario cuyos detalles desea recuperar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Lista de comentarios]

Este módulo de búsqueda recupera todos los comentarios del recurso especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Seleccione o asigne el equipo propietario del proyecto que contiene la carpeta cuyos comentarios desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Seleccione el proyecto que contiene la carpeta cuyos comentarios desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>Seleccione la carpeta que contiene el recurso cuyos comentarios desea enumerar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Seleccione el recurso cuyos comentarios desea enumerar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Introduzca o asigne el número máximo de comentarios que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Actualizar un comentario]

Este módulo de acción edita un comentario existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Seleccione o asigne el equipo propietario del proyecto que contiene el recurso en el que desea actualizar un comentario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Seleccione el proyecto que contiene el recurso en el que desea actualizar un comentario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>Seleccione la carpeta que contiene el recurso en el que desea actualizar un comentario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Seleccione el recurso en el que desea actualizar un comentario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>Seleccione el comentario que desea actualizar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text]</td> 
   <td> <p> Introduzca el contenido de texto del comentario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Timestamp] </td> 
   <td> <p>Introduzca el número de fotograma en el vídeo al que está vinculado el comentario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Ver comentario actualizado]

Este módulo de activador inicia un escenario cuando se edita un comentario.

Como se trata de un déclencheur instantáneo, debe seleccionar o crear un webhook para que lo utilice el módulo.

Si agrega un gancho web, escriba la siguiente información.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>Introduzca el nombre del webhook, por ejemplo: Comentario editado.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Seleccione el equipo para el que se crea este webhook.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Ver nuevo comentario]

Este módulo de activador inicia un escenario cuando se crea un nuevo comentario o respuesta.

Como se trata de un déclencheur instantáneo, debe seleccionar o crear un webhook para que lo utilice el módulo.

Si agrega un gancho web, escriba la siguiente información.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>Introduzca el nombre del webhook, p. ej. Nuevo comentario.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Seleccione el equipo para el que se crea este webhook.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Proyectos

#### [!UICONTROL Enumerar proyectos]

Este módulo de búsqueda recupera todos los proyectos del equipo especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Seleccione o asigne el equipo para el que desea recuperar proyectos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Introduzca o asigne el número máximo de proyectos que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Otro

#### [!UICONTROL Realizar una llamada de API]

Este módulo le permite realizar una llamada de API personalizada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>Introduzca una ruta relativa a <code>https://api.frame.io</code>. Ejemplo: <code> /v2/teams</code></p> <p>Nota: Para obtener la lista de los puntos finales disponibles, consulte la Referencia de la API de [!DNL Frame.io].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion añade encabezados de autorización automáticamente.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String] </td> 
   <td> <p>Introduzca la cadena de consulta de la solicitud. Para cada parámetro que desee incluir en la cadena de consulta, haga clic en <b>[!UICONTROL Add item]</b> e introduzca el nombre del campo y el valor deseado.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la instrucción condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>


<!-- 
**Example:** The following API call returns all teams and its details in your [!DNL Frame.io] account:

URL: `/v2/teams`

Method: `GET`

![API call example](/help/workfront-fusion/references/apps-and-modules/assets/api-call-example.png)

The result can be found in the module's Output under Bundle > Body.

In our example, the details of 1 team were returned:

![API call output](/help/workfront-fusion/references/apps-and-modules/assets/api-call-output.png)

-->
