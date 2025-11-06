---
title: Módulos Frame.io
description: La cuenta de  [!DNL Adobe Workfront Fusion Frame].io modules enable you to monitor, create, update, retrieve, or delete assets and comments in your [!DNL Frame.io] .
author: Becky
feature: Workfront Fusion
exl-id: 16d32ebd-1807-495e-8aaf-27346056ec71
source-git-commit: b23255cb9585c58f025a0b2c99b824ecbf2c6879
workflow-type: tm+mt
source-wordcount: '3555'
ht-degree: 24%

---

# [!DNL Frame.io] módulos V4

>[!IMPORTANT]
>
>Este artículo describe la nueva versión del conector Frame.io. Este conector se utiliza para conectarse a Frame.io versión 4.
>
>Para obtener instrucciones sobre la versión heredada del conector Frame.io, consulte [Conector heredado Frame.io](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/frame-io-modules.md).

Los módulos de Adobe Workfront Fusion [!DNL Frame.io] le permiten supervisar, crear, actualizar, recuperar o eliminar recursos y comentarios en su cuenta de [!DNL Frame.io].

Workfront ofrece dos conectores Frame.io, basados en la versión de Frame.io a la que se está conectando.

| Conector | Versión de Frame.io |
|---|---|
| Frame.io | V4 |
| Frame.io (heredado) | V3 |

Para obtener instrucciones sobre la versión heredada del conector Frame.io, consulte [Conector heredado Frame.io](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/frame-io-modules.md).


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
   <td> https://api.frame.io/v4</td> 
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

Puede conectarse automáticamente con credenciales de usuario, crear manualmente una conexión de credenciales de usuario o crear una conexión servidor a servidor.

* [Conectar automáticamente con credenciales de usuario](#connect-automatically-with-user-credentials#)
* [Crear manualmente una conexión de credenciales de usuario](#create-a-user-credentials-connection-manually)
* [Creación de una conexión servidor a servidor](#create-a-server-to-server-connection)

### Conectar automáticamente con credenciales de usuario

Este método crea una conexión automáticamente si ha iniciado sesión en Frame.io o le conecta a la página de inicio de sesión de Frame.io para que pueda iniciar sesión.

1. En cualquier módulo Frame.io, haga clic en **[!UICONTROL Agregar]** junto al cuadro Conexión.
1. Introduzca un nombre para la conexión. 
1. Haga clic en **Continuar**.
1. Si se le pide que inicie sesión en su cuenta de Frame.io, hágalo.
1. Si forma parte de más de una organización Frame.io, seleccione la organización que desee utilizar para esta conexión.

Se crea la conexión.

### Crear manualmente una conexión de credenciales de usuario

Puede crear una conexión de credenciales de usuario iniciando sesión en Frame.io o proporcionando un ID de cliente o un Secreto de cliente.

Para crear una conexión servidor a servidor, primero debe configurar una aplicación en Adobe Developer Console.

* [Crear credenciales de usuario en Adobe Developer Console](#create-user-credentials-in-the-adobe-developer-console)
* [Configurar una conexión de autenticación de usuario](#configure-a-user-authentication-connection)

#### Crear credenciales de usuario en Adobe Developer Console

Si todavía no tiene credenciales de servidor a servidor en un proyecto de Adobe Developer Console, puede crearlas.

1. Abra [Adobe Developer Console](https://developer.adobe.com/).
1. Seleccione un proyecto existente en Adobe Developer Console para utilizarlo para esta conexión

   O

   Cree un nuevo proyecto en Adobe Developer Console. Para obtener instrucciones, vea [Crear un proyecto vacío](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty).

1. En la página Información general del proyecto o en la página Introducción a tu nuevo proyecto, haz clic en **Agregar API**.
1. En la página que se abre, busque y haga clic en **Frame.io API**.
1. En la página Seleccionar tipo de autenticación, seleccione **Autenticación de usuario** y haga clic en **Siguiente**.
1. En la página Agregar una credencial de autenticación de usuario, seleccione **Aplicación web de OAuth** y haga clic en **Siguiente**.
1. En la página Configurar credenciales de aplicación web de OAuth, introduzca lo siguiente:   <table style="table-layout:auto">
   <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
          <td role="rowheader">[!UICONTROL URI de redirección predeterminado]</td>
          <td>
            <p><code>https://oauth.app.workfrontfusion.com/oauth/cb/frame-io2</code></p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Patrón URI de redireccionamiento]</td>
          <td>
            <p><code>https://oauth\.app\.workfrontfusion\.com/oauth/cb/frame-io2</code></p>
          </td>
        </tr>
       </tbody>
    </table>
1. Haga clic en **Siguiente**.
1. Haga clic en **Guardar API configurada**.
1. En la página del producto, haga clic en la tarjeta de las credenciales que acaba de crear.

   Aquí puede encontrar su ID de cliente y su Secreto de cliente.

>[!NOTE]
>
> Se recomienda dejar esta ventana abierta a medida que comience a configurar la conexión en Adobe Workfront Fusion. Puede copiar el ID de cliente y recuperar y copiar el Secreto del cliente de esta página para pegarlo en los campos de conexión.


#### Configurar una conexión de autenticación de usuario

1. En cualquier módulo Frame.io, haga clic en **[!UICONTROL Agregar]** junto al cuadro Conexión.
1. En el cuadro Crear una conexión, haga clic en **Mostrar configuración avanzada**.

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
            <p>Seleccione <b>Autenticación de usuario de IMS</b>.</p>
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
          <td>Introduzca su [!UICONTROL Client ID] [!DNL Adobe]. Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].<p>Para obtener instrucciones sobre cómo crear credenciales, consulte <a href="#create-user-credentials-in-the-adobe-developer-console" class="MCXref xref">Crear credenciales de usuario en Adobe Developer Console</a> en este artículo.</p></td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]</td>
          <td>Introduzca su [!DNL Adobe] [!UICONTROL Client Secret].  Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].<p>Para obtener instrucciones sobre cómo crear credenciales, consulte <a href="#create-user-credentials-in-the-adobe-developer-console" class="MCXref xref">Crear credenciales de usuario en Adobe Developer Console</a> en este artículo.</p>
        </tr>
       </tbody>
    </table>
1. Si se le pide que inicie sesión en su cuenta de Frame.io, hágalo.
1. Si forma parte de más de una organización Frame.io, seleccione la organización que desee utilizar para esta conexión.

Se crea la conexión.


### Creación de una conexión servidor a servidor

Para crear una conexión servidor a servidor, primero debe configurar una aplicación en Adobe Developer Console.

* [Creación de credenciales de servidor a servidor en Adobe Developer Console](#create-server-to-server-credentials-in-the-adobe-developer-console)
* [Configuración de una conexión servidor a servidor](#configure-a-server-to-server-connection)

#### Creación de credenciales de servidor a servidor en Adobe Developer Console

Si todavía no tiene credenciales de servidor a servidor en un proyecto de Adobe Developer Console, puede crearlas.

1. Abra [Adobe Developer Console](https://developer.adobe.com/).
1. Seleccione un proyecto existente en Adobe Developer Console para utilizarlo para esta conexión

   O

   Cree un nuevo proyecto en Adobe Developer Console. Para obtener instrucciones, vea [Crear un proyecto vacío](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty).

1. En la página Información general del proyecto o en la página Introducción a tu nuevo proyecto, haz clic en **Agregar API**.
1. En la página que se abre, busque y haga clic en **Frame.io API**.
1. En la página Seleccionar tipo de autenticación, seleccione **Autenticación de servidor a servidor** y haga clic en **Siguiente**.
1. Introduzca un nombre para las credenciales. Esto le permite identificar las credenciales más adelante en el área Credenciales de API de Adobe Admin Console.
1. Haga clic en **Siguiente**.
1. En la página Seleccionar perfiles de producto, seleccione el perfil de producto que incluye la cuenta de Frame.io a la que desea conectarse.
1. Haga clic en **Guardar API configurada**.
1. En la página del producto, haga clic en la tarjeta de las credenciales que acaba de crear.

   Aquí puede encontrar su ID de cliente y su Secreto de cliente.

>[!NOTE]
>
> Se recomienda dejar esta ventana abierta a medida que comience a configurar la conexión en Adobe Workfront Fusion. Puede copiar el ID de cliente y recuperar y copiar el Secreto del cliente de esta página para pegarlo en los campos de conexión.


#### Configuración de una conexión servidor a servidor

1. En cualquier módulo Frame.io, haga clic en **[!UICONTROL Agregar]** junto al cuadro Conexión.

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
            <p>Seleccionar <b>servidor IMS para servidor</b>.</p>
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
          <td>Introduzca su [!UICONTROL Client ID] [!DNL Adobe]. Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].<p>Para obtener instrucciones sobre cómo crear credenciales, consulte <a href="#create-server-to-server-credentials-in-the-adobe-developer-console" class="MCXref xref">Crear credenciales de servidor a servidor en Adobe Developer Console</a> en este artículo.</p></td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]</td>
          <td>Introduzca su [!DNL Adobe] [!UICONTROL Client Secret].  Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].<p>Para obtener instrucciones sobre cómo crear credenciales, consulte <a href="#create-server-to-server-credentials-in-the-adobe-developer-console" class="MCXref xref">Crear credenciales de servidor a servidor en Adobe Developer Console</a> en este artículo.</p>
        </tr>
       </tbody>
    </table>
1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.




## Módulos de [!DNL Frame.io] y sus campos

Al configurar módulos de [!DNL Frame.io], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL Frame.io] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Recursos](#assets)
* [Comentarios](#comments)
* [Carpetas](#folders)
* [Proyectos](#projects)
* [Recursos compartidos](#shares)
* [Espacios de trabajo](#workspaces)
* [Otro](#other)

### Recursos

* [[!UICONTROL Crear un recurso]](#create-an-asset)
* [[!UICONTROL Eliminar un recurso]](#delete-an-asset)
* [[!UICONTROL Obtener un recurso]](#get-an-asset)
* [[!UICONTROL Enumerar recursos]](#list-assets)
* [Ver recurso eliminado](#watch-asset-deleted)
* [Ver nuevo recurso](#watch-new-asset)

#### [!UICONTROL Crear un recurso] <!--different for v4-->

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
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta que contiene el proyecto para el que desea crear un recurso.</p> </td> 
  </tr> 
 <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>Seleccione el espacio de trabajo o asigne el ID del espacio de trabajo que contiene el proyecto para el que desea crear un recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Seleccione el proyecto o asigne el ID del proyecto para el que desea crear un recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Path] </td> 
   <td> <p>Seleccione la ruta en la que desea crear un recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Nombre de archivo] </td> 
   <td> <p>Introduzca el nombre del archivo que desea utilizar para este recurso.</p> </td> 
  </tr>
    <tr> 
    <td role="rowheader">Tamaño del archivo </td> 
    <td> <p>Introduzca o asigne el tamaño del archivo en bytes.</p> </td> 
   </tr>
  <tr> 
   <td role="rowheader">[!UICONTROL Source URL] </td> 
   <td> <p>Si crea un archivo, introduzca la dirección URL del archivo que desea cargar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tipo de medio] </td> 
   <td> <p>Seleccione el tipo de medio para este recurso.</p> </td> 
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
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta que contiene el recurso que desea eliminar.</p> </td> 
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
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta que contiene el recurso que desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Seleccione o asigne el recurso que desea recuperar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Enumerar recursos]

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
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta que contiene los recursos que desea enumerar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Número máximo de recursos devueltos] </td> 
   <td> <p>Introduzca o asigne el número máximo de recursos que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Ver recurso eliminado

Este módulo de activador inicia un escenario cuando se elimina un recurso.

Seleccione el webhook que desee utilizar para este módulo o haga clic en Agregar junto al campo Webhook e introduzca la siguiente información:

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>Escriba un nombre para el nuevo webhook.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta que desea inspeccionar en busca de recursos eliminados.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Ver nuevo recurso

Este módulo de activador inicia un escenario cuando se crea un nuevo recurso.

Seleccione el webhook que desee utilizar para este módulo o haga clic en Agregar junto al campo Webhook e introduzca la siguiente información:

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>Escriba un nombre para el nuevo webhook.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta que desea ver para ver si hay nuevos recursos.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Comentarios

* [[!UICONTROL Crear un comentario]](#create-a-comment)
* [[!UICONTROL Eliminar un comentario]](#delete-a-comment)
* [[!UICONTROL Obtener un comentario]](#get-a-comment)
* [[!UICONTROL Enumerar comentarios]](#list-comments)
* [[!UICONTROL Actualizar un comentario]](#update-a-comment)
* [Ver comentario actualizado](#watch-comment-updated)
* [Ver nuevo comentario](#watch-new-comment)

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
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta que contiene el recurso al que desea agregar un comentario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID del espacio de trabajo que contiene el recurso al que desea agregar un comentario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Seleccione el proyecto o asigne el ID del proyecto que contiene el recurso al que desea añadir un comentario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Path] </td> 
   <td> <p>Seleccione la ruta al recurso al que desee agregar un comentario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text]</td> 
   <td> <p> Introduzca el contenido de texto del comentario o la respuesta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Timestamp] </td> 
   <td> <p>Introduzca el número de fotograma en el vídeo al que debe vincularse el comentario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Página] </td> 
   <td> <p>Si el recurso es un PDF, introduzca o asigne la página a la que debe adjuntarse el comentario.</p> </td> 
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
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta que contiene el comentario que desea eliminar.</p> </td> 
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
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta que contiene el comentario cuyos detalles desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>Seleccione el comentario cuyos detalles desea recuperar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Enumerar comentarios]

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
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione o asigne la cuenta que contiene el recurso del que desea recuperar comentarios.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>Seleccione o asigne el espacio de trabajo que contiene el recurso del que desea recuperar comentarios.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Seleccione el proyecto que contiene el recurso del que desea recuperar comentarios.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Path] </td> 
   <td> <p>Seleccione la ruta que lleva al recurso desde el que desea enumerar los comentarios.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned comments] </td> 
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
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione o asigne la cuenta que contiene el proyecto que contiene el recurso en el que desea actualizar un comentario.</p> </td> 
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
  <tr> 
   <td role="rowheader">[!UICONTROL Página] </td> 
   <td> <p>Si el recurso es un PDF, introduzca o asigne la página a la que está adjunto el comentario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Ver comentario actualizado

Este módulo de déclencheur inicia un escenario cuando se actualiza un comentario.

Seleccione el webhook que desee utilizar para este módulo o haga clic en Agregar junto al campo Webhook e introduzca la siguiente información:

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>Escriba un nombre para el nuevo webhook.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta que desea ver para ver los comentarios actualizados.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Ver nuevo comentario

Este módulo de déclencheur inicia un escenario cuando se crea un comentario.

Seleccione el webhook que desee utilizar para este módulo o haga clic en Agregar junto al campo Webhook e introduzca la siguiente información:

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>Escriba un nombre para el nuevo webhook.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta que desea ver para ver nuevos comentarios.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Carpetas

#### Crear una carpeta

Este módulo de acción crea una nueva carpeta en Frame.io.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione o asigne la cuenta donde desea crear una carpeta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>Seleccione o asigne el espacio de trabajo en el que desea crear una carpeta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Seleccione el donde desea crear una carpeta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Path] </td> 
   <td> <p>Seleccione la ruta donde desea crear una carpeta.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Nombre </td> 
   <td> <p>Introduzca o asigne un nombre para la nueva carpeta.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Proyectos

* [Crear un proyecto](#create-a-project)
* [Invitar a usuarios al proyecto Frame.io](#invite-users-to-frameio-project)
* [Enumerar proyectos](#list-projects)

#### Crear un proyecto

Este módulo de acción crea un nuevo proyecto en Frame.io.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione o asigne la cuenta donde desea crear un proyecto.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>Seleccione o asigne el espacio de trabajo donde desea crear un proyecto.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Nombre </td> 
   <td> <p>Escriba o asigne un nombre para el nuevo proyecto.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Invitar a usuarios al proyecto Frame.io

Este módulo de acción invita a los usuarios al proyecto Frame.io especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione o asigne la cuenta que contiene el proyecto al que desea invitar a un usuario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>Seleccione o asigne el espacio de trabajo que contiene el proyecto al que desea invitar a un usuario.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Identificador de proyecto </td> 
   <td> <p>Seleccione o asigne el proyecto al que desea invitar a un usuario.</p> </td> 
  </tr> 
  </tr> 
   <tr> 
   <td role="rowheader">Identificador del usuario </td> 
   <td> <p>Seleccione o asigne al usuario que desea invitar al proyecto.</p> </td> 
  </tr> 
 </tbody> 
</table>

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
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione o asigne la cuenta que contiene el recurso del que desea recuperar proyectos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>Seleccione o asigne el espacio de trabajo que contiene el recurso del que desea recuperar proyectos.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Número máximo de proyectos devueltos] </td> 
   <td> <p>Introduzca o asigne el número máximo de proyectos
   desea que el módulo se devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Recursos compartidos

* [Añadir un recurso a un vínculo compartido](#add-an-asset-to-a-share-link)
* [Crear un vínculo compartido](#create-a-share-link)

#### Añadir un recurso a un vínculo compartido

Estos módulos de acción añaden un recurso a un vínculo compartido en Frame.io.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione o asigne la cuenta que contiene el vínculo compartido al que desea agregar un recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Compartir vínculo ID] </td> 
   <td> <p>Seleccione o asigne el vínculo compartido al que desee agregar un recurso.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Introduzca o asigne el ID del recurso que desea agregar al vínculo compartido.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Crear un vínculo compartido

Este módulo de acción crea un nuevo vínculo compartido en Frame.io.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione o asigne la cuenta en la que desea crear un vínculo compartido.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>Seleccione o asigne el espacio de trabajo donde desea crear un vínculo compartido.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Seleccione o asigne el proyecto donde desea crear un vínculo compartido.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Acceso </td> 
   <td> <p>Seleccione si este vínculo tiene acceso público o restringido.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Recursos </td> 
   <td> <p>Para cada recurso que desee agregar al vínculo compartido, haga clic en <b>Agregar elemento</b> e introduzca el ID del recurso.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Descripción </td> 
   <td> <p>Introduzca o asigne una descripción para el vínculo compartido.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Nombre </td> 
   <td> <p>Introduzca o asigne la fecha de caducidad del vínculo compartido.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Nombre </td> 
   <td> <p>Introduzca o asigne un nombre para el nuevo vínculo compartido.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Nombre </td> 
   <td> <p>Introduzca o asigne una frase de contraseña para el vínculo compartido.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Espacios de trabajo

#### Crear un espacio de trabajo

Este módulo de acción crea un nuevo espacio de trabajo en Frame.io

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione o asigne la cuenta donde desea crear un espacio de trabajo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>Introduzca o asigne un nombre nuevo para el espacio de trabajo.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Enumerar espacios de trabajo

Este módulo enumera todos los espacios de trabajo de una cuenta.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione o asigne la cuenta que contiene el recurso del que desea recuperar espacios de trabajo.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Número máximo de espacios de trabajo devueltos] </td> 
   <td> <p>Introduzca o asigne el número máximo de espacios de trabajo
   desea que el módulo se devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Otro

* [Realizar una llamada de API personalizada](#make-a-custom-api-call)
* [Ver el valor de metadatos actualizado](#watch-metadata-value-updated)


#### [!UICONTROL Realizar una llamada de API personalizada]

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
   <td> <p>Introduzca una ruta relativa a <code>https://api.frame.io</code>. Ejemplo: <code> /v4/me</code></p> <p>Nota: Para obtener la lista de los puntos finales disponibles, consulte la Referencia de la API de [!DNL Frame.io].</p> </td> 
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
   <td role="rowheader">[!UICONTROL Cadena de consulta] </td> 
   <td> <p>Introduzca la cadena de consulta de la solicitud. Para cada parámetro que desee incluir en la cadena de consulta, haga clic en <b>[!UICONTROL Add item]</b> e introduzca el nombre del campo y el valor deseado.</p> </td> 
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

#### Ver el valor de metadatos actualizado

Este módulo de déclencheur inicia un escenario cuando se actualiza un comentario.

Seleccione el webhook que desee utilizar para este módulo o haga clic en Agregar junto al campo Webhook e introduzca la siguiente información:

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>Escriba un nombre para el nuevo webhook.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de cuenta] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta que desea ver para obtener valores de metadatos actualizados.</p> </td> 
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
