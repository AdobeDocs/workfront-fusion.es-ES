---
title: Módulos Frame.io
description: La cuenta de  [!DNL Adobe Workfront Fusion Frame].io modules enable you to monitor, create, update, retrieve, or delete assets and comments in your [!DNL Frame.io] .
author: Becky
feature: Workfront Fusion
exl-id: 16d32ebd-1807-495e-8aaf-27346056ec71
source-git-commit: 3cb613c11500dfc94774783ee0b38e6f1768de20
workflow-type: ht
source-wordcount: '4539'
ht-degree: 100%

---

# [!DNL Frame.io] módulos versión 4.0

>[!IMPORTANT]
>
>Este artículo describe la nueva versión del conector Frame.io. Este conector se utiliza para conectarse a Frame.io versión 4.0.
>
>Para obtener instrucciones sobre la versión heredada del conector Frame.io, consulte [Conector heredado Frame.io](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/frame-io-modules.md).

Los módulos [!DNL Frame.io] de Adobe Workfront Fusion le permiten supervisar, crear, actualizar, recuperar o eliminar recursos y comentarios en la cuenta de [!DNL Frame.io].

Workfront ofrece dos conectores Frame.io, basados en la versión de Frame.io a la que se está conectando.

| Conector | Versión de Frame.io |
|---|---|
| Frame.io | Versión 4.0 |
| Frame.io (heredado) | Versión 3.0 |

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

Para usar módulos [!DNL Frame.io], debe tener una cuenta de [!DNL Frame.io]

## Información de la API de Frame.io

El conector Frame.io utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL base</td> 
   <td> https://api.frame.io/v4</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> Versión 2.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.0.76</td> 
  </tr>
 </tbody> 
 </table>

## Conectar [!DNL Frame.io] a [!UICONTROL Adobe Workfront Fusion]

Puede conectarse automáticamente con credenciales de usuario, crear manualmente una conexión de credenciales de usuario o crear una conexión servidor a servidor.

* [Conectar automáticamente con las credenciales de usuario](#connect-automatically-with-user-credentials#)
* [Crear manualmente una conexión con las credenciales de usuario](#create-a-user-credentials-connection-manually)
* [Crear una conexión de servidor a servidor](#create-a-server-to-server-connection)

### Conectar automáticamente con las credenciales de usuario

Este método crea una conexión automáticamente si ha iniciado sesión en Frame.io, o le conecta a la página de inicio de sesión de Frame.io para que pueda iniciar sesión.

1. En cualquier módulo de Frame.io, haga clic en **[!UICONTROL Añadir]** junto al cuadro Conexión.
1. Introduzca un nombre para la conexión. 
1. Haga clic en **Continuar**.
1. Si se le pide que inicie sesión en su cuenta de Frame.io, hágalo.
1. Si forma parte de más de una organización Frame.io, seleccione la que desee utilizar para esta conexión.

Se crea la conexión.

### Crear manualmente una conexión con las credenciales de usuario

Puede crear una conexión de credenciales de usuario iniciando sesión en Frame.io o proporcionando un ID o un secreto de cliente.

Para crear una conexión de servidor a servidor, primero debe configurar una aplicación en Adobe Developer Console.

* [Crear credenciales de usuario en Adobe Developer Console](#create-user-credentials-in-the-adobe-developer-console)
* [Configurar una conexión de autenticación de usuario](#configure-a-user-authentication-connection)

#### Crear credenciales de usuario en Adobe Developer Console

Si todavía no tiene credenciales de servidor a servidor en un proyecto de Adobe Developer Console, puede crearlas.

1. Abra [Adobe Developer Console](https://developer.adobe.com/).
1. Seleccione un proyecto existente en Adobe Developer Console para utilizarlo para esta conexión

   O

   Cree un nuevo proyecto en Adobe Developer Console. Para obtener instrucciones, consulte [Crear un proyecto vacío](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty).

1. En la página Información general del proyecto o en la página Introducción a tu nuevo proyecto, haga clic en **Añadir API**.
1. En la página que se abre, busque y haga clic en la **API de Frame.io**.
1. En la página Seleccionar tipo de autenticación, seleccione **Autenticación de usuario** y haga clic en **Siguiente**.
1. En la página Añadir una credencial de autenticación de usuario, seleccione **Aplicación web de OAuth** y haga clic en **Siguiente**.
1. En la página Configurar credenciales de aplicación web de OAuth, introduzca lo siguiente:   <table style="table-layout:auto">
   <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
          <td role="rowheader">[!UICONTROL Default redirect URI]</td>
          <td>
            <p><code>https://oauth.app.workfrontfusion.com/oauth/cb/frame-io2</code></p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Redirect URI pattern]</td>
          <td>
            <p><code>https://oauth\.app\.workfrontfusion\.com/oauth/cb/frame-io2</code></p>
          </td>
        </tr>
       </tbody>
    </table>
1. Haga clic en **Siguiente**.
1. Haga clic en **Guardar API configurada**.
1. En la página de producto, haga clic en la tarjeta de las credenciales que acaba de crear.

   Aquí puede encontrar su ID y su secreto de cliente.

>[!NOTE]
>
> Se recomienda dejar esta ventana abierta a medida que comience a configurar la conexión en Adobe Workfront Fusion. Puede copiar el ID de cliente y recuperar y copiar el Secreto del cliente de esta página para pegarlo en los campos de conexión.


#### Configurar una conexión de autenticación de usuario

1. En cualquier módulo de Frame.io, haga clic en **[!UICONTROL Añadir]** junto al cuadro Conexión.
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
1. Si forma parte de más de una organización Frame.io, seleccione la que desee utilizar para esta conexión.

Se crea la conexión.


### Crear una conexión de servidor a servidor

Para crear una conexión de servidor a servidor, primero debe configurar una aplicación en Adobe Developer Console.

* [Creación de credenciales de servidor a servidor en Adobe Developer Console](#create-server-to-server-credentials-in-the-adobe-developer-console)
* [Configuración de una conexión de servidor a servidor](#configure-a-server-to-server-connection)

#### Creación de credenciales de servidor a servidor en Adobe Developer Console

Si todavía no tiene credenciales de servidor a servidor en un proyecto de Adobe Developer Console, puede crearlas.

1. Abra [Adobe Developer Console](https://developer.adobe.com/).
1. Seleccione un proyecto existente en Adobe Developer Console para utilizarlo para esta conexión

   O

   Cree un nuevo proyecto en Adobe Developer Console. Para obtener instrucciones, consulte [Crear un proyecto vacío](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty).

1. En la página Información general del proyecto o en la página Introducción a tu nuevo proyecto, haga clic en **Añadir API**.
1. En la página que se abre, busque y haga clic en la **API de Frame.io**.
1. En la página Seleccionar tipo de autenticación, seleccione **Autenticación de servidor a servidor** y haga clic en **Siguiente**.
1. Introduzca un nombre para las credenciales. Esto le permite identificar las credenciales más adelante en el área Credenciales de API de Adobe Admin Console.
1. Haga clic en **Siguiente**.
1. En la página Seleccionar perfiles de producto, seleccione el perfil de producto que incluye la cuenta de Frame.io a la que desea conectarse.
1. Haga clic en **Guardar API configurada**.
1. En la página de producto, haga clic en la tarjeta de las credenciales que acaba de crear.

   Aquí puede encontrar su ID y su secreto de cliente.

>[!NOTE]
>
> Se recomienda dejar esta ventana abierta a medida que comience a configurar la conexión en Adobe Workfront Fusion. Puede copiar el ID de cliente y recuperar y copiar el Secreto del cliente de esta página para pegarlo en los campos de conexión.


#### Configuración de una conexión de servidor a servidor

1. En cualquier módulo de Frame.io, haga clic en **[!UICONTROL Añadir]** junto al cuadro Conexión.

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
            <p>Seleccione <b>de servidor a servidor IMS</b>.</p>
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

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, consulte [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Recursos](#assets)
* [Comentarios](#comments)
* [Carpetas](#folders)
* [Proyectos](#projects)
* [Recursos compartidos](#shares)
* [Espacios de trabajo](#workspaces)
* [Metadatos](#metadata)
* [Otros](#other)

### Recursos

* [[!UICONTROL Crear un recurso]](#create-an-asset)
* [[!UICONTROL Eliminar un recurso]](#delete-an-asset)
* [[!UICONTROL Obtener un recurso]](#get-an-asset)
* [[!UICONTROL Enumerar recursos]](#list-assets)
* [Ver recurso eliminado](#watch-asset-deleted)
* [Ver nuevo recurso](#watch-new-asset)

#### [!UICONTROL Crear un recurso] <!--different for v4-->

Este módulo de acción crea un nuevo recurso. Puede cargar un archivo local o proporcionar la dirección URL de un archivo remoto para crear el recurso a partir de él.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta que contiene el proyecto para el que desea crear un recurso.</p> </td> 
  </tr> 
 <tr> 
   <td role="rowheader">[!UICONTROL ID de espacio de trabajo] </td> 
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
<!--  <tr> 
   <td role="rowheader">[!UICONTROL File Name] </td> 
   <td> <p>Enter the name of the file that you want to use for this asset.</p> </td> 
  </tr> -->
    <tr> 
    <td role="rowheader">Tipo de carga </td> 
    <td> <p>Seleccione si va a crear un recurso a partir de un archivo local o remoto.</p> </td> 
   </tr>
    <tr> 
    <td role="rowheader">Tamaño del archivo </td> 
    <td> <p>Si va a cargar un archivo local, introduzca o asigne el tamaño del archivo en bytes.</p> </td> 
   </tr>
  <tr> 
   <td role="rowheader">[!UICONTROL URL de origen] </td> 
   <td> <p>Si va a crear el recurso desde un archivo remoto, introduzca la URL del archivo que desea cargar.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Archivo de origen]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre del archivo de origen.</p> </td> 
  </tr> 
<!--  <tr> 
   <td role="rowheader">[!UICONTROL Media type] </td> 
   <td> <p>Select the media type for this asset.</p> </td> 
  </tr> -->
  </tbody> 
</table>

#### [!UICONTROL Crear un recurso (heredado)] <!--different for v4-->

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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta que contiene el proyecto para el que desea crear un recurso.</p> </td> 
  </tr> 
 <tr> 
   <td role="rowheader">[!UICONTROL ID de espacio de trabajo] </td> 
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
   <td role="rowheader">[!UICONTROL File Name] </td> 
   <td> <p>Escriba el nombre del archivo que desea utilizar para este recurso.</p> </td> 
  </tr>
    <tr> 
    <td role="rowheader">Tamaño del archivo </td> 
    <td> <p>Introduzca o asigne el tamaño del archivo en bytes.</p> </td> 
   </tr>
  <tr> 
   <td role="rowheader">[!UICONTROL URL de origen] </td> 
   <td> <p>Si va a crear un archivo, introduzca la URL del archivo que desea cargar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Media type] </td> 
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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta que contiene los recursos que desea enumerar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned assets] </td> 
   <td> <p>Introduzca o asigne el número máximo de recursos que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Ver recurso eliminado

Este módulo de activador inicia un escenario cuando se elimina un recurso.

Seleccione el webhook que desee utilizar para este módulo o haga clic en Añadir junto al campo Webhook e introduzca la siguiente información:

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>Introduzca un nombre para el nuevo webhook.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta que desea ver para encontrar recursos eliminados.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Ver nuevo recurso

Este módulo de activador inicia un escenario cuando se crea un nuevo recurso.

Seleccione el webhook que desee utilizar para este módulo o haga clic en Añadir junto al campo Webhook e introduzca la siguiente información:

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>Introduzca un nombre para el nuevo webhook.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta que desea ver para comprobar si hay nuevos recursos.</p> </td> 
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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta que contiene el recurso al que desea añadir un comentario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de espacio de trabajo] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta del espacio de trabajo que contiene el recurso al que desea añadir un comentario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Seleccione el proyecto o asigne el ID del proyecto que contiene el recurso al que desea añadir un comentario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Path] </td> 
   <td> <p>Seleccione la ruta del recurso al que desea añadir un comentario.</p> </td> 
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
   <td role="rowheader">[!UICONTROL Page] </td> 
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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta que contenga el comentario cuyos detalles desea recuperar.</p> </td> 
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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione o asigne la cuenta que contenga el recurso cuyos comentarios desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de espacio de trabajo] </td> 
   <td> <p>Seleccione o asigne el espacio de trabajo que contiene el recurso cuyos comentarios desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Seleccione el proyecto que contiene el recurso cuyos comentarios desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Path] </td> 
   <td> <p>Seleccione la ruta que contiene el recurso cuyos comentarios desea enumerar.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned comments] </td> 
   <td> <p>Introduzca o asigne el número máximo de comentarios que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione o asigne la cuenta que contiene el proyecto con el recurso cuyo comentario desea actualizar.</p> </td> 
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
   <td role="rowheader">[!UICONTROL Page] </td> 
   <td> <p>Si el recurso es un PDF, introduzca o asigne la página a la que está adjunto el comentario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Ver comentario actualizado

Este módulo de activación inicia un escenario cuando se actualiza un comentario.

Seleccione el webhook que desee utilizar para este módulo o haga clic en Añadir junto al campo Webhook e introduzca la siguiente información:

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>Introduzca un nombre para el nuevo webhook.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta donde desea buscar comentarios actualizados.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Ver nuevo comentario

Este módulo de activación inicia un escenario cuando se crea un comentario.

Seleccione el webhook que desee utilizar para este módulo o haga clic en Añadir junto al campo Webhook e introduzca la siguiente información:

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>Introduzca un nombre para el nuevo webhook.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID de la cuenta donde desea buscar nuevos comentarios.</p> </td> 
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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione o asigne la cuenta en la que desea crear una carpeta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de espacio de trabajo] </td> 
   <td> <p>Seleccione o asigne el espacio de trabajo en el que desea crear una carpeta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Seleccione dónde desea crear una carpeta.</p> </td> 
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
* [Invitar a usuarios al proyecto de Frame.io](#invite-users-to-frameio-project)
* [Lista de proyectos](#list-projects)

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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione o asigne la cuenta donde desea crear un proyecto.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de espacio de trabajo] </td> 
   <td> <p>Seleccione o asigne el espacio de trabajo en el que desea crear un proyecto.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Nombre </td> 
   <td> <p>Introduzca o asigne un nombre para el nuevo proyecto.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Invitar a usuarios al proyecto de Frame.io

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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione o asigne la cuenta que contiene el proyecto al que desea invitar a un usuario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de espacio de trabajo] </td> 
   <td> <p>Seleccione o asigne el espacio de trabajo que contiene el proyecto al que desea invitar a un usuario.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Identificador de proyecto </td> 
   <td> <p>Seleccione o asigne el proyecto al que desea invitar a un usuario.</p> </td> 
  </tr> 
  </tr> 
   <tr> 
   <td role="rowheader">Identificador de usuario </td> 
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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Introduzca o asigne la cuenta que contiene el recurso del que desea recuperar los proyectos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de espacio de trabajo] </td> 
   <td> <p>Seleccione o asigne el espacio de trabajo que contiene el recurso del que desea recuperar los proyectos.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned projects] </td> 
   <td> <p>Introduzca o asigne el número máximo de proyectos
  que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione o asigne la cuenta que contiene el vínculo compartido al que desea añadir el recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Share link ID] </td> 
   <td> <p>Seleccione o asigne el vínculo compartido al que quiere añadir un recurso.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Introduzca o asigne el ID del recurso al que quiere añadir el vínculo compartido.</p> </td> 
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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione o asigne la cuenta en la que desea crear un vínculo compartido.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de espacio de trabajo] </td> 
   <td> <p>Seleccione o asigne el espacio de trabajo en el que desea crear un vínculo compartido.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Seleccione o asigne el proyecto en el que desea crear un vínculo compartido.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Acceso </td> 
   <td> <p>Seleccione si este vínculo tiene acceso público o restringido.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Recursos </td> 
   <td> <p>Para cada recurso que desee añadir al vínculo compartido, haga clic en <b>Añadir elemento</b> e introduzca el ID del recurso.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Descripción </td> 
   <td> <p>Introduzca o asigne una descripción para el vínculo compartido.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Nombre </td> 
   <td> <p>Introduzca o asigne la fecha de caducidad para el vínculo compartido.</p> </td> 
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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione o asigne la cuenta en la que desea crear un espacio de trabajo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>Introduzca o asigne un nuevo nombre para el espacio de trabajo.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Enumerar los espacios de trabajo

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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Introduzca o asigne la cuenta que contiene el recurso del que desea recuperar los espacios de trabajo.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned workspaces] </td> 
   <td> <p>Introduzca o asigne el número máximo de espacios de trabajo
   que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Metadatos

* [Crear un campo en el nivel de cuenta](#create-an-account-level-field)
* [Eliminar un campo en el nivel de cuenta](#delete-an-account-level-field)
* [Obtener metadatos](#get-metadata)
* [Lista de campos en el nivel de cuenta](#list-account-level-fields)
* [Actualizar una definición de campo en el nivel de cuenta](#update-an-account-level-field-definition)
* [Actualizar metadatos en varios archivos](#update-metadata-across-multiple-files)

#### Crear un campo en el nivel de cuenta

Este módulo de acción crea y configura un nuevo campo de metadatos en el nivel de cuenta.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione o asigne la cuenta en la que desea crear los metadatos.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Tipo de campo </td> 
   <td> <p>Seleccione el tipo de campo de metadatos que desea crear y, a continuación, configure las opciones de ese campo.</p> </td> 
  </tr> 
  </tr> 
   <tr> 
   <td role="rowheader">Nombre </td> 
   <td> <p>Introduzca o asigne un nombre para el nuevo campo.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Eliminar un campo en el nivel de cuenta

Este módulo de acción elimina un único campo de metadatos en el nivel de cuenta.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione o asigne la cuenta que contiene el campo de metadatos que desea eliminar.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">ID de definición de campo </td> 
   <td> <p>Introduzca o asigne el ID del campo que desea eliminar. Puede encontrar los ID de campo con el módulo Lista de campos en el nivel de cuenta.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Obtener metadatos

Este módulo de acción recupera los metadatos de un archivo en Frame.io.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione o asigne la cuenta que contiene el archivo del que desea recuperar los metadatos.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">ID de archivo </td> 
   <td> <p>Introduzca o asigne el ID del archivo del que desea recuperar los metadatos.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Mostrar nulo </td> 
   <td> <p>Active esta opción para incluir campos con un valor nulo en la salida.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Lista de campos en el nivel de cuenta

Este módulo recupera una lista de campos de metadatos en el nivel de cuenta para la cuenta especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione o asigne la cuenta de la que desea enumerar los campos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned agreements]</td> 
   <td> <p>Introduzca o asigne el número máximo de campos que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Actualizar una definición de campo en el nivel de cuenta

Este módulo actualiza la definición de un único campo de metadatos existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione o asigne la cuenta en la que desea crear los metadatos.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">ID de definición de campo </td> 
   <td> <p>Introduzca o asigne el ID del campo que desea actualizar. Puede encontrar los ID de campo con el módulo Lista de campos en el nivel de cuenta.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Tipo de campo </td> 
   <td> <p>Si desea cambiar el tipo de campo del campo, seleccione el tipo de campo de metadatos que desea crear y, a continuación, configure las opciones de ese campo.</p> </td> 
  </tr> 
  </tr> 
   <tr> 
   <td role="rowheader">Nombre </td> 
   <td> <p>Introduzca o asigne un nuevo nombre para el campo.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Actualizar metadatos en varios archivos

Este módulo actualiza los campos de metadatos de uno o varios archivos con los valores especificados.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione o asigne la cuenta que contiene los archivos para los que desea actualizar los metadatos.</p> </td> 
  </tr> 
 <tr> 
   <td role="rowheader">[!UICONTROL ID de espacio de trabajo] </td> 
   <td> <p>Seleccione el espacio de trabajo o asigne el ID del espacio de trabajo que contiene el proyecto para el que desea crear un recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Seleccione el proyecto o asigne el ID del proyecto para el que desea crear un recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de archivo] </td> 
   <td> <p>Para cada archivo para el que desee actualizar los metadatos, haga clic en <b>Añadir elemento</b> e introduzca o asigne el ID del archivo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Values] </td> 
   <td> <p>Para cada campo para el que desee actualizar los metadatos, haga clic en <b>Añadir elemento</b> e introduzca o asigne el identificador de la definición del campo y el valor que desee colocar en ese campo. Todos los archivos especificados en el campo ID de archivo se actualizan con este valor de campo.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Otros

* [Realizar una llamada API personalizada](#make-a-custom-api-call)
* [Ver eventos](#watch-events)
* [Ver el valor de metadatos actualizado](#watch-metadata-value-updated)


#### [!UICONTROL Realizar una llamada API personalizada]

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
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, consulte <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Métodos de petición HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion añade encabezados de autorización automáticamente.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query string] </td> 
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

#### Ver eventos

Este módulo de activación instantáneo inicia un escenario cuando se produce el evento seleccionado en Frame.io.

Puede seleccionar un webhook existente o crear uno nuevo.

Para crear un nuevo webhook, haga lo siguiente:

1. Haga clic en **Añadir** junto al campo Webhook.
1. Cumplimente la siguiente información:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
     <td role="rowheader">Nombre del webhook </td> 
      <td> <p>Introduzca un nombre para el nuevo webhook.</p> </td> 
     </tr> 
     <tr> 
       <td role="rowheader">[!UICONTROL Connection] </td> 
       <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
     </tr> 
     <tr> 
     <td role="rowheader">[!UICONTROL Account ID] </td> 
      <td> <p>Seleccione o asigne la cuenta que contenga el espacio de trabajo en el que desea ver eventos.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL ID de espacio de trabajo]</td> 
      <td> <p>Introduzca el identificador del espacio de trabajo donde desea ver eventos.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Eventos]</td> 
      <td> <p>Seleccione los eventos que desee que activen este módulo.</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. Haga clic en **Guardar** para guardar el webhook y volver al módulo.
1. Haga clic en **Aceptar** en el módulo Ver eventos para guardar la configuración.


#### Ver el valor de metadatos actualizado

Este módulo de activación inicia un escenario cuando se actualiza un comentario.

Seleccione el webhook que desee utilizar para este módulo o haga clic en Añadir junto al campo Webhook e introduzca la siguiente información:

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>Introduzca un nombre para el nuevo webhook.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Frame.io], consulte <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Frame.io] a Adobe Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Seleccione la cuenta o asigne el ID donde desea ver los valores de metadatos actualizados.</p> </td> 
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
