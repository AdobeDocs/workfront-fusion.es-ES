---
title: Módulos de software Jira
description: En un escenario de  [!DNL Adobe Workfront Fusion]  puede automatizar los flujos de trabajo que utilizan  [!DNL Jira] Software, así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: 92cac080-d8f6-4770-a6a6-8934538c978b
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1809'
ht-degree: 85%

---

# Módulos de [!DNL Jira Software]

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!DNL Jira Software], así como conectarlo a varias aplicaciones y servicios de terceros.

Para obtener instrucciones sobre cómo crear un escenario, vea los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

<!-- Bob Fix this compared to original -->

## Requisitos de acceso

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] plan*</td>
  <td> <p>[!UICONTROL Pro] o superior</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licencia*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licencia**</td> 
   <td>
   <p>Requisito de licencia actual: no se requiere ninguna licencia de [!DNL Workfront Fusion].</p>
   <p>O</p>
   <p>Requisito de licencia heredado: [!UICONTROL [!DNL Workfront Fusion] para automatización e integración de trabajo </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Requisito de producto actual: si tiene el plan [!UICONTROL Select] o [!UICONTROL Prime] [!DNL Adobe Workfront], su organización debe adquirir [!DNL Adobe Workfront Fusion] así como [!DNL Adobe Workfront] para utilizar la funcionalidad descrita en este artículo. [!DNL Workfront Fusion] está incluido en el plan [!UICONTROL Ultimate] [!DNL Workfront].</p>
   <p>O</p>
   <p>Requisito de productos heredados: su organización debe comprar [!DNL Adobe Workfront Fusion] y [!DNL Adobe Workfront] para utilizar la funcionalidad descrita en este artículo.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Para saber de qué plan, tipo de licencia o acceso dispone, póngase en contacto con el administrador de [!DNL Workfront].

Para obtener información sobre las licencias de [!DNL Adobe Workfront Fusion], consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)

## Requisitos previos

Para usar módulos de [!DNL Jira], debe tener una cuenta de [!DNL Jira].

## Información de API de Jira

El conector Jira utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"></td> 
   <td> Jira Cloud</td> 
   <td> Servidor Jira</td> 
  </tr> 
  <tr> 
   <td role="rowheader">apiVersion</td> 
   <td> 2</td> 
   <td> 2</td> 
  </tr> 
  <tr> 
   <td role="rowheader">apiVersionAgile</td> 
   <td> 1,0 </td> 
   <td> 1,0</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>1.7.29</td> 
   <td>1.0.19</td> 
  </tr>
 </tbody> 
 </table>

## Conectar [!DNL Jira Software] a [!DNL Workfront Fusion]

El método de conexión se basa en si se está usando [!DNL Jira Cloud] o [!DNL Jira Server].

* [Conectar  [!DNL Jira Cloud]  a Workfront Fusion](#connect-jira-cloud-to-workfront-fusion)
* [Conectar  [!DNL Jira Server]  a  [!DNL Workfront Fusion]](#connect-jira-server-to-workfront-fusion)

### Conectar [!DNL Jira Cloud] a [!DNL Workfront Fusion]

Conectar [!DNL Jira Cloud] a [!DNL Workfront Fusion]

Para conectar [!DNL Jira Software] a [!DNL Workfront Fusion], debe crear un token de API e insertarlo junto con la URL de servicio y el nombre de usuario en el campo [!UICONTROL Create a connection] en [!DNL Workfront Fusion].

#### Crear un token de API en [!DNL Jira]

1. Vaya a [https://id.atlassian.com/manage/api-tokens](https://id.atlassian.com/manage/api-tokens) e inicie sesión.
1. Haga clic en **[!UICONTROL Create API token]**.
1. Escriba un nombre para el token, como *Workfront Fusion*.
1. Copie el token utilizando el botón **[!UICONTROL Copy to clipboard]**.

   >[!IMPORTANT]
   >
   >No se puede volver a ver el token después de cerrar este diálogo.
1. Almacene el token generado en un lugar seguro.
1. Continúe en [Configurar el token de API  [!DNL Jira]  en  [!DNL Workfront Fusion]](#configure-the-jira-api-token-in-workfront-fusion).

#### Configurar el token de la API [!DNL Jira] en [!DNL Workfront Fusion]

1. En [!DNL Workfront Fusion], agregue un módulo [!DNL Jira] a un escenario para abrir el cuadro **[!UICONTROL Create a connection]**.
1. Especifique la siguiente información:

   * **[!UICONTROL Service URL]:** Esta es la URL base que usa para acceder a su cuenta de Jira. Ejemplo: `yourorganization.atlassian.net`
   * **[!UICONTROL Username]**
   * **[!UICONTROL API token]:** Este es el token de API que creó en la sección [Crear un token de API en [!DNL Jira]](#create-an-api-token-in-jira) de este artículo.

1. Haga clic en [!UICONTROL Continue] para crear la conexión y volver al módulo.

### Conectar [!DNL Jira Server] a [!DNL Workfront Fusion]

<!--
<p style="color: #ff1493;">Becky: Find out and document how to find these things</p>
-->

Para autorizar una conexión entre [!DNL Workfront Fusion] y [!DNL Jira Server], necesita su clave de cliente, clave privada y URL del servicio. Es posible que deba ponerse en contacto con el administrador de [!DNL Jira] para obtener esta información.

* [Generación de claves públicas y privadas para su conexión a  [!DNL Jira] ](#generate-public-and-private-keys-for-your-jira-connection)
* [Configuración de la aplicación cliente como consumidor en  [!DNL Jira]](#configure-the-client-app-as-a-consumer-in-jira)
* [Creación de una conexión a  [!DNL Jira] Server o Jira Data Center en  [!DNL Workfront Fusion]](#create-a-connection-to-jira-server-or-jira-data-center-in-workfront-fusion)

#### Generación de claves públicas y privadas para su conexión a [!DNL Jira]

Para adquirir una clave privada para su conexión a [!DNL Workfront Fusion Jira], debe generar claves públicas y privadas.

1. En su terminal, ejecute los comandos `openssl` siguientes.

   * `openssl genrsa -out jira_privatekey.pem 1024`

     Este comando genera una clave privada de 1024 bits.

   * `openssl req -newkey rsa:1024 -x509 -key jira_privatekey.pem -out jira_publickey.cer -days 365`

     Este comando crea un certificado X509.

   * `openssl pkcs8 -topk8 -nocrypt -in jira_privatekey.pem -out jira_privatekey.pcks8`

     Este comando extrae la clave privada (formato PKCS8) en el archivo `jira_privatekey.pcks8`
.

   * `openssl x509 -pubkey -noout -in jira_publickey.cer  > jira_publickey.pem`

     Este comando extrae la clave pública del certificado al archivo `jira_publickey.pem`.

     >[!NOTE]
     >
     >Si utiliza Windows, es posible que tenga que guardar la clave pública en el archivo `jira_publickey.pem` manualmente:
     >
     >1. En el terminal, ejecute el comando siguiente:
     >   
     >   `openssl x509 -pubkey -noout -in jira_publickey.cer`
     >   
     >1. Copie la salida de terminal (incluidos `-------BEGIN PUBLIC KEY--------` y `-------END PUBLIC KEY--------`
     >   
     >1. Pegue la salida de terminal en un archivo con nombre `jira_publickey.pem`.


1. Continúe con [Configuración de la aplicación cliente como consumidor en  [!DNL Jira]](#configure-the-client-app-as-a-consumer-in-jira)

#### Configuración de la aplicación cliente como consumidor en [!DNL Jira]

1. Inicie sesión en su instancia de [!DNL Jira].
1. En el panel de navegación izquierdo, haga clic en **[!UICONTROL [!DNL Jira] Settings]** ![](/help/workfront-fusion/references/apps-and-modules/assets/jira-settings-icon.png) > **[!UICONTROL Applications]**> **[!UICONTROL Application links]**.
1. En el campo **[!UICONTROL Enter the URL of the application you want to link]**, escriba

   ```
   https://app.workfrontfusion.com/oauth/cb/workfront-jiraserver-oauth1
   ```

1. Haga clic en **[!UICONTROL Create new link]**. Ignore el mensaje de error “No se ha recibido respuesta de la dirección URL que ha introducido”.
1. En la ventana **[!UICONTROL Link applications]**, escriba valores en los campos **[!UICONTROL Consumer key]** y **[!UICONTROL Shared secret]**.

   Puede elegir los valores de estos campos.

1. Copie los valores de los campos **[!UICONTROL Consumer key]** y **[!UICONTROL Shared secret]** en una ubicación segura.

   Necesitará estos valores más adelante en el proceso de configuración.

1. Rellene los campos de la dirección URL tal como se indica a continuación:

   | Campo | Descripción |
   |---|---|
   | [!UICONTROL Request Token URL] | `<Jira base url>/plugins/servlet/oauth/request-token` |
   | [!UICONTROL Authorization URL] | `<Jira base url>/plugins/servlet/oauth/authorize` |
   | [!UICONTROL Access Token URL] | `<Jira base url>/plugins/servlet/oauth/access-token` |

1. Seleccione la casilla de verificación **[!UICONTROL Create incoming link]**.
1. Haga clic en **[!UICONTROL Continue]**.
1. En la ventana **[!UICONTROL Link applications]**, rellene los campos siguientes:

   <table style="table-layout:auto"> 
    <col data-mc-conditions=""> 
    <col data-mc-conditions=""> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Consumer Key]</p> </td> 
      <td> Pegue la clave del cliente que ha copiado en una ubicación segura.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Consumer name]</td> 
      <td>Introduzca un nombre de su elección. Este nombre es para su propia referencia.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Public key]</td> 
      <td>Pegue la clave pública de su archivo <code>[!DNL jira_publickey.pem]</code>.</td> 
     </tr> 
    </tbody> 
   </table>

1. Haga clic en **[!UICONTROL Continue]**.
1. Continúe para [Crear una conexión a  [!DNL Jira Server]  o a  [!DNL Jira Data Center]  en  [!DNL Workfront Fusion]](#create-a-connection-to-jira-server-or-jira-data-center-in-workfront-fusion)

#### Crear una conexión a [!DNL Jira Server] o a [!DNL Jira Data Center] en [!DNL Workfront Fusion]

>[!NOTE]
>
>Utilice la aplicación [!DNL Jira Server] para conectarse a [!DNL Jira Server] o a [!DNL Jira Data Center].

1. En cualquier módulo de [!DNL Jira Server] de [!DNL Workfront Fusion], haga clic en **[!UICONTROL Add]** junto al campo [!UICONTROL connection].
1. En el panel [!UICONTROL Create a connection], rellene los campos siguientes:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td> <p>Introduzca un nombre para la conexión</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Consumer Key]</td> 
      <td>Pegue la clave del cliente que ha copiado en una ubicación segura de <a href="#configure-the-client-app-as-a-consumer-in-jira" class="MCXref xref">Configurar la aplicación cliente como consumidor en [!DNL Jira]</a></td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!DNL Private Key]</td> 
      <td>Pegue la clave privada del archivo <code>[!DNL jira_privatekey.pcks8]</code> que creó en <a href="#generate-public-and-private-keys-for-your-jira-connection" class="MCXref xref">Generar claves públicas y privadas para la conexión de [!DNL Jira]</a>.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!DNL Service URL]</td> 
      <td>Escriba la URL de instancia [!DNL Jira]. Ejemplo: <code>yourorganization.atlassian.net</code></td> 
     </tr> 
    </tbody> 
   </table>

1. Haga clic en **[!UICONTROL Continue]** para crear la conexión y volver al módulo.

## Módulos de [!DNL Jira Software] y sus campos

Al configurar módulos de [!DNL Jira Software], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Jira Software] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Activadores](#triggers)
* [Acciones](#actions)
* [Búsquedas](#searches)

### Activadores

#### [!UICONTROL Watch for records]

Este módulo de activación inicia un escenario cuando se añade, actualiza o elimina un registro.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>Seleccione el webhook que desee utilizar para buscar registros. </p> <p>Para añadir un nuevo webhook:</p> 
    <ol> 
     <li value="1">Haga clic <strong>[!UICONTROL Add]</strong></li> 
     <li value="2">Introduzca un nombre para el webhook. </li> 
     <li value="3"> <p>Seleccione la conexión que desea utilizar para su webhook. </p> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Jira Software] a [!DNL Workfront Fusion], consulte <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL Jira Software] a [!DNL Workfront Fusion]</a> en este artículo.</p> </li> 
     <li value="4"> <p>Seleccione el tipo de registro que desea que vea el software:</p> 
      <ul> 
       <li>[!UICONTROL Comment] </li> 
       <li>[!UICONTROL Issue]</li> 
       <li>[!UICONTROL Project] </li> 
       <li>[!UICONTROL Sprint]</li> 
      </ul> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### Acciones

* [[!UICONTROL Add issue to sprint]](#add-issue-to-sprint)
* [[!UICONTROL Create a Record]](#create-a-record)
* [[!UICONTROL Custom API Call]](#custom-api-call)
* [[!UICONTROL Delete a record]](#delete-a-record)
* [[!UICONTROL Download an attachment]](#download-an-attachment)
* [[!UICONTROL Read a record]](#read-a-record)
* [[!UICONTROL Update a record]](#update-a-record)

#### [!UICONTROL Add issue to sprint]

Este módulo de acción añade uno o más problemas a un sprint.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Jira Software] a [!DNL Workfront Fusion], consulte <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL Jira Software] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sprint ID]</td> 
   <td>Introduzca o asigne el ID de sprint del sprint al que desea añadir un problema.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Issue ID or Keys]</td> 
   <td>Añada un ID o una clave de problema para cada problema que desee añadir al sprint.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Record]

Este módulo de acción crea un nuevo registro en Jira.

El módulo devuelve cualquier campo estándar asociado con el registro, junto con los campos y valores personalizados a los que accede la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Jira Software] a [!DNL Workfront Fusion], consulte <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL Jira Software] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro que desea que cree el módulo. Al seleccionar un tipo de registro, en el módulo aparecerán otros campos específicos de dicho tipo de registro.</p> 
    <ul> 
     <li>[!UICONTROL Attachment]</li> 
     <li>[!UICONTROL Comment]</li> 
     <li>[!UICONTROL Issue]</li> 
     <li>[!UICONTROL Project]</li> 
     <li>[!UICONTROL Sprint] </li> 
     <li>[!UICONTROL Worklog]</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Custom API Call]

Este módulo de acción le permite realizar una llamada autenticada personalizada a la API [!DNL Jira Software]. De este modo, puede crear una automatización del flujo de datos imposibles de realizar por los otros [!DNL Jira Software] módulos.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Jira Software] a [!DNL Workfront Fusion], consulte <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL Jira Software] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Introduzca una ruta relativa a<code>&lt;Instance URL>/rest/api/2/ </code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   td&gt; <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de petición HTTP en [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] añade los encabezados de autorización automáticamente.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Añada la consulta para la llamada de API en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png">  </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a record]

Este módulo de acción elimina un registro en particular.

Especifique el identificador del registro.

El módulo devuelve el identificador del registro y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Jira Software] a [!DNL Workfront Fusion], consulte <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL Jira Software] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro que desea que elimine el módulo. </p> 
    <ul> 
     <li>[!UICONTROL Attachment]</li> 
     <li>[!UICONTROL Comment]</li> 
     <li>[!UICONTROL Issue]</li> 
     <li>[!UICONTROL Project]</li> 
     <li>[!UICONTROL Sprint] </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID or Key]</td> 
   <td>Introduzca o asigne el ID o la clave del registro que desea eliminar.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download an attachment]

Este módulo de acción descarga un archivo adjunto concreto.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Jira Software] a [!DNL Workfront Fusion], consulte <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL Jira Software] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Introduzca o asigne el ID del archivo adjunto que desea descargar.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Read a record]

Este módulo de acción lee datos de un único registro en [!DNL Jira Software].

Especifique el identificador del registro.

El módulo devuelve cualquier campo estándar asociado con el registro, junto con los campos y valores personalizados a los que accede la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Jira Software] a [!DNL Workfront Fusion], consulte <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL Jira Software] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro [!DNL Jira] que desea que lea el módulo.</p> 
    <ul> 
     <li>[!UICONTROL Attachment]</li> 
     <li>[!UICONTROL Issue]</li> 
     <li>[!UICONTROL Project]</li> 
     <li>[!UICONTROL Sprint] </li> 
     <li>[!UICONTROL User]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Seleccione las salidas que desea recibir. Las opciones de salida están disponibles según el tipo de registro seleccionado en el campo "[!UICONTROL Record Type]".</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td> <p>Escriba o asigne el identificador único [!DNL Jira Software] del registro que desea que lea el módulo.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a record]

Este módulo de acción actualiza un registro existente, como un problema o un proyecto.

Especifique el identificador del registro.

El módulo devuelve el identificador del registro y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Jira Software] a [!DNL Workfront Fusion], consulte <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL Jira Software] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro que desea que actualice el módulo. Al seleccionar un tipo de registro, en el módulo aparecerán otros campos específicos de dicho tipo de registro.</p> 
    <ul> 
     <li>[!UICONTROL Comment]</li> 
     <li>[!UICONTROL Issue]</li> 
     <li>[!UICONTROL Project]</li> 
     <li>[!UICONTROL Sprint] </li> 
     <li>[!UICONTROL Transition issue]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID or Key]</td> 
   <td>Introduzca o asigne el ID o la clave del registro que desea actualizar.</td> 
  </tr> 
 </tbody> 
</table>

### Búsquedas

* [[!UICONTROL List records]](#list-records)
* [[!UICONTROL Search for records]](#search-for-records)

#### [!UICONTROL List records]

Este módulo de búsqueda recupera todos los elementos de un tipo específico que coinciden con la consulta de búsqueda

Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Jira Software] a [!DNL Workfront Fusion], consulte <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL Jira Software] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro que desea que enumere el módulo. Al seleccionar un tipo de registro, en el módulo aparecerán otros campos específicos de dicho tipo de registro.</p> 
    <ul> 
     <li>[!UICONTROL Comment]</li> 
     <li>[!UICONTROL Issue]</li> 
     <li>[!UICONTROL Project]</li> 
     <li>[!UICONTROL Sprint issue]</li> 
     <li>[!UICONTROL Worklog]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Max Results]</p> </td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo recupere durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> <!--
   <tr> 
    <td role="rowheader">Offset</td> 
    <td> Enter or map the ID of the first item you want to retrieve details for. This is a way to paginate the records. If you enter the 5000th item as the offset, the module would return items 5000-9999.</td> 
   </tr>
  --> 
 </tbody> 
</table>

#### [!UICONTROL Search for records]

Este módulo de búsqueda busca registros en un objeto de [!DNL Jira Software] que coincidan con la consulta de búsqueda especificada.

Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Jira Software] a [!DNL Workfront Fusion], consulte <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL Jira Software] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro que desea que busque el módulo. Al seleccionar un tipo de registro, en el módulo aparecerán otros campos específicos de dicho tipo de registro.</p> 
    <ul> 
     <li>[!UICONTROL Issues]</li> 
     <li> <p>[!UICONTROL Issues by JQL (Jira Query Lanuguage)] </p> <p>Para obtener más información sobre JQL, consulte <a href="https://www.atlassian.com/blog/jira-software/jql-the-most-flexible-way-to-search-jira-14#:~:text=JQLstandsforJiraQuery,projectmanagers%2Candbusinessusers.">JQL</a> en el sitio de ayuda de Atlassian. </p> </li> 
     <li>[!UICONTROL Project]</li> 
     <li>[!UICONTROL Project by issue]</li> 
     <li>[!UICONTROL User]</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
