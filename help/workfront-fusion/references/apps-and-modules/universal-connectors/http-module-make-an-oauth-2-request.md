---
title: Módulo HTTP > Realizar una solicitud OAuth 2.0
description: Para realizar una solicitud HTTP(S)  [!DNL Adobe Workfront Fusion] a servidores que requieran una autorización de OAuth 2.0, primero debe crear una conexión OAuth. [!DNL Adobe Workfront Fusion] garantiza que todas las llamadas realizadas con esta conexión tengan los encabezados de autorización adecuados y que actualicen automáticamente los tokens asociados cuando sea necesario.
author: Becky
feature: Workfront Fusion
exl-id: a302a1d4-fddf-4a71-adda-6b87ff7dba4b
source-git-commit: 3ba5d67806e0d495bd4a91589d06cfb9adb25c0c
workflow-type: tm+mt
source-wordcount: '1918'
ht-degree: 83%

---

# [!UICONTROL HTTP] > [!UICONTROL Make an OAuth 2.0 request] módulo

>[!NOTE]
>
>[!DNL Adobe Workfront Fusion] requiere una licencia de [!DNL Adobe Workfront Fusion] además de una licencia de [!DNL Adobe Workfront].

Para realizar una petición HTTP(S) [!DNL Adobe Workfront Fusion] a servidores que requieran una autorización de OAuth 2.0, primero debe crear una conexión OAuth. [!DNL Adobe Workfront Fusion] garantiza que todas las llamadas realizadas con esta conexión tengan los encabezados de autorización adecuados y que actualicen automáticamente los tokens asociados cuando sea necesario.

[!DNL Workfront Fusion] admite los siguientes flujos de autenticación de OAuth 2.0:

* Flujo de código de autorización
* Flujo implícito

Otros flujos, como el flujo de credenciales de contraseña de propietario de recursos y el flujo de credenciales de cliente, no se admiten automáticamente a través de este módulo.

Para obtener más información sobre la autenticación de OAuth 2.0, consulte [El marco de autorización de OAuth 2.0](https://tools.ietf.org/html/rfc6749).

>[!NOTE]
>
>Si se está conectando a un producto de Adobe que actualmente no tiene un conector dedicado, le recomendamos utilizar el módulo de Adobe Authenticator.
>
>Para obtener más información, consulte [Módulo de Adobe Authenticator](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-authenticator-modules.md).

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

Para obtener información sobre licencias de [!DNL Adobe Workfront Fusion], consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)

## Creación de una conexión para una solicitud [!DNL OAuth]

* [Instrucciones generales para crear una conexión en el módulo de solicitud HTTP > Crear una OAuth 2.0](#general-instructions-for-creating-a-connection-in-the-http--make-an-oauth-20-request-module)
* [Instrucciones para crear una conexión con Google en el módulo de solicitud HTTP >[!UICONTROL Make] y OAuth 2.0](#instructions-for-creating-a-connection-to-google-in-the-http-make-an-oauth-20-request-module)
* [Instrucciones para conectarse a la API de Microsoft Graph mediante el módulo de solicitud HTTP > Crear una OAuth 2.0](#instructions-for-connecting-to-microsoft-graph-api-via-the-http--make-an-oauth-20-request-module)

### Instrucciones generales para crear una conexión en el módulo [!UICONTROL HTTP] > [!UICONTROL Make an OAuth 2.0 request]

1. Cree un cliente OAuth en el servicio de [!DNL target] con el que desea que se comunique [!DNL Adobe Workfront Fusion]. Es muy probable que esta opción se encuentre en la sección [!UICONTROL Developer] del servicio dado.

   1. Al crear un cliente, introduzca la dirección URL correspondiente en el campo `[!UICONTROL Redirect URL]` o `[!UICONTROL Callback URL]`:

      | América/APAC | `https://app.workfrontfusion.com/oauth/cb/oauth2` |
      |---|---|
      | EMEA | `https://app-eu.workfrontfusion.com/oauth/cb/oauth2` |

   1. Después de crear el cliente, el servicio dado muestra 2 claves: `[!UICONTROL Client ID]` y `[!UICONTROL Client Secret]`. Algunos servicios los denominan `[!UICONTROL App Key]` y `[!UICONTROL App Secret]` . Guarde la clave y el secreto en una ubicación segura, para que pueda proporcionarlos al crear la conexión en Workfront Fusion.

1. Busque `[!UICONTROL Authorize URI]` y `[!UICONTROL Token URI]` en la documentación de API del servicio proporcionado. Son direcciones URL a través de las cuales [!DNL Workfront Fusion] se comunica con el servicio [!DNL target]. Las direcciones sirven para la autorización de OAuth.

   >[!NOTE]
   >
   >Si el servicio utiliza un flujo implícito, solo necesitará el `[!UICONTROL Authorize URI]`.

   >[!INFO]
   >
   >**Ejemplo:** Direcciones de Yahoo:
   >
   >* URI autorizado:
   >
   >`https://api.login.yahoo.com/oauth2/request_auth`
   >
   >* URI de token:
   >
   >`https://api.login.yahoo.com/oauth2/get_token`

1. (Condicional) Si el servicio de destino utiliza ámbitos (derechos de acceso), compruebe cómo separa los ámbitos individuales y asegúrese de establecer el separador en los ajustes avanzados en consecuencia. Si el separador no se ha establecido correctamente, [!DNL Workfront Fusion] no consigue crear la conexión y se recibe un error de ámbito no válido.
1. Después de completar los pasos anteriores, puede comenzar a crear la conexión OAuth en [!DNL Workfront Fusion]. Añada el módulo de procesamiento de respuestas y solicitudes HTTP de OAuth 2.0 a su escenario.
1. En el campo Conexión del módulo, haga clic en **[!UICONTROL Add]**.

1. Rellene los campos siguientes para crear una conexión:

   <table style="table-layout:auto">  
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Connection name] </td> 
      <td> <p>Introduzca el nombre de la conexión.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Flow type]</p> </td> 
      <td> <p>Seleccione el flujo para obtener tókenes.</p> 
       <ul> 
        <li><strong>[!UICONTROL Authorization Code]</strong>: escriba <code>[!UICONTROL Authorize URI]</code> y <code>[!UICONTROL Token URI]</code> desde la documentación de API del servicio.</li> 
        <li><strong>[!UICONTROL Implicit]</strong>: introduzca <code>[!UICONTROL Authorize URI]</code> desde la documentación de API del servicio.</li> 
       </ul> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Scope] </td> 
      <td> <p>Añada ámbitos individuales. Puede encontrar esta información en la documentación para desarrolladores (API) de un servicio determinado.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Scope separator] </td> 
      <td> <p>Seleccione por qué se deben separarse los ámbitos especificados anteriormente. Puede encontrar esta información en la documentación para desarrolladores (API) de un servicio determinado.</p> <p>Advertencia: si el separador no se establece correctamente, [!DNL Workfront Fusion] no crea la conexión y se recibe un error de ámbito no válido.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Client ID] </td> 
      <td> <p>Introduzca el ID de cliente. Ha obtenido el ID de cliente al crear un cliente de OAuth en el servicio al que desea conectarse.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Client Secret]</td> 
      <td> <p> Introduzca el secreto de cliente. Ha obtenido el secreto de cliente al crear un cliente de OAuth en el servicio al que desea conectarse.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Authorize parameters]</p> </td> 
      <td> <p>Añada los parámetros que desee incluir en la llamada de autorización. Los siguientes parámetros estándar siempre se incluyen automáticamente y no es necesario añadirlos.</p> <p>Parámetros estándar:</p> 
       <ul> 
        <li> <p><strong>[!UICONTROL response_type]</strong> </p> <p> <code>code </code>para [!UICONTROL Authorization Code flow] y <code>token </code>para [!UICONTROL Implicit flow]</p> </li> 
        <li> <p><strong>[!UICONTROL redirect_uri]</strong> </p> 
         <table style="table-layout:auto">  
          <col> 
          <col> 
          <tbody> 
           <tr> 
            <td role="rowheader">América/APAC</td> 
            <td>https://app.workfrontfusion.com/oauth/cb/oauth2</td> 
           </tr> 
           <tr> 
            <td role="rowheader">EMEA </td> 
            <td>https://app-eu.workfrontfusion.com/oauth/cb/oauth2</td> 
           </tr> 
          </tbody> 
         </table> </li> 
        <li> <p><strong>[!UICONTROL client_id]</strong> </p> <p> El ID de cliente que recibió al crear la cuenta</p> </li> 
       </ul> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Access token parameters]</p> </td> 
      <td> <p>Añada cualquier parámetro que desee incluir en la llamada de token. Los siguientes parámetros estándar siempre se incluyen automáticamente y no es necesario añadirlos.</p> <p>Parámetros estándar:</p> 
       <ul> 
        <li><strong>[!UICONTROL grant_type]</strong>: <code>authorization_code</code></li> 
        <li> <p><strong>[!UICONTROL redirect_uri]:</strong> </p> 
         <table style="table-layout:auto">  
          <col> 
          <col> 
          <tbody> 
           <tr> 
            <td role="rowheader">América/APAC</td> 
            <td>https://app.workfrontfusion.com/oauth/cb/oauth2</td> 
           </tr> 
           <tr> 
            <td role="rowheader">EMEA </td> 
            <td>https://app-eu.workfrontfusion.com/oauth/cb/oauth2</td> 
           </tr> 
          </tbody> 
         </table> </li> 
        <li><strong>[!UICONTROL client_id]</strong>: el ID de cliente que recibió al crear la cuenta se incluye automáticamente en el cuerpo de la solicitud</li> 
        <li><strong>client_secret</strong>: el secreto de cliente que recibió al crear la cuenta se incluye automáticamente en el cuerpo de la solicitud</li> 
        <li><strong>code</strong>: código devuelto por la solicitud de autorización</li> 
       </ul> <p>Nota:  <p>El estándar OAuth 2.0 admite al menos 2 métodos de autenticación de cliente durante este paso (<code>[!UICONTROL client_secret_basic]</code> y <code>[!UICONTROL client_secret_post]</code>). [!DNL Workfront Fusion] envía automáticamente el secreto y el ID de cliente especificados a través del método <code>[!UICONTROL client_secret_post]</code>. Por lo tanto, estos parámetros se incluyen automáticamente como parte del cuerpo de solicitud de token. </p> <p>Para obtener más información sobre la autenticación de OAuth 2.0, consulte <a href="https://tools.ietf.org/html/rfc6749">El marco de autorización de OAuth 2.0</a>.</p> </p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Refresh token parameters]</p> </td> 
      <td> <p>Añada cualquier parámetro que desee incluir en la llamada de token. Los siguientes parámetros estándar siempre se incluyen automáticamente y no es necesario añadirlos.</p> <p>Parámetros estándar:</p> 
       <ul> 
        <li> <p><strong>[!UICONTROL grant_type]</strong>: <code>refresh_token</code></p> </li> 
        <li> <p><strong>[!UICONTROL refresh_token]</strong>: el token de actualización más reciente obtenido por el servicio al que se está conectando</p> </li> 
        <li> <p><strong>[!UICONTROL client_id]</strong>: el ID de cliente que recibió al crear la cuenta se incluye automáticamente en el cuerpo de la solicitud</p> </li> 
        <li> <p><strong>[!UICONTROL client_secret]</strong>: el Secreto de cliente que recibió al crear la cuenta se incluye automáticamente en el cuerpo de la solicitud</p> </li> 
       </ul> <p>Nota:  <p>El estándar OAuth 2.0 admite al menos 2 métodos de autenticación de cliente durante este paso (<code>[!UICONTROL client_secret_basic]</code> y <code>[!UICONTROL client_secret_post]</code>). [!DNL Workfront Fusion] envía automáticamente el secreto y el ID de cliente especificados a través del método <code>[!UICONTROL client_secret_post]</code>. Por lo tanto, estos parámetros se incluyen automáticamente como parte del cuerpo de solicitud de token. </p> <p>Para obtener más información sobre la autenticación de OAuth 2.0, consulte <a href="https://tools.ietf.org/html/rfc6749">El marco de autorización de OAuth 2.0</a>.</p> </p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Custom Headers]</p> </td> 
      <td> <p>Especifique claves y valores adicionales para incluir en el encabezado de los pasos [!UICONTROL Token] y R[!UICONTROL efresh Token].</p> <p>Nota:  <p>El estándar OAuth 2.0 admite al menos 2 métodos de autenticación de cliente durante este paso (<code>[!UICONTROL client_secret_basic]</code> y <code>[!UICONTROL client_secret_post]</code>). [!DNL Workfront Fusion] no admite automáticamente el método <code>[!UICONTROL client_secret_basic]</code>. Si el servicio al que se está conectando espera que el ID de cliente y el secreto del cliente se combinen en una sola cadena y luego se codifique base64 en el encabezado Autorización, debe añadir ese encabezado y valor clave aquí.</p> <p> Para obtener más información sobre la autenticación de OAuth 2.0, consulte <a href="https://tools.ietf.org/html/rfc6749">El marco de autorización de OAuth 2.0</a>.</p> </p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Token placement]</p> </td> 
      <td> <p>Seleccione si desea enviar el token en [!UICONTROL header], [!UICONTROL query string] o en ambos al conectarse a la dirección URL especificada.</p> <p>Normalmente, los tokens se envían en el encabezado de la solicitud.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Header token name] </td> 
      <td> <p>Introduzca el nombre del token de autorización en el encabezado. Predeterminado: <code>[!UICONTROL Bearer]</code>.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Query string parameter name] </td> 
      <td> <p>Introduzca el nombre del token de autorización en la cadena de consulta. Predeterminado: <code>[!UICONTROL access_token]</code>.</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. Haga clic **[!UICONTROL Continue]** para guardar la configuración de conexión.
1. Continúe en [Configuración del módulo de solicitud OAuth 2.0](#oauth-20-request-module-setup).

### Instrucciones para crear una conexión con [!DNL Google] en [!UICONTROL HTTP] >[!UICONTROL Make an OAuth 2.0 request module]

El siguiente ejemplo muestra cómo usar el módulo de solicitud [!UICONTROL HTTP] > [!UICONTROL Make an OAuth 2.0] para conectarse a [!DNL Google].

1. Asegúrese de haber creado un proyecto, establecido las opciones de configuración de OAuth y generado sus credenciales tal como se describe en [Conectar [!DNL Adobe Workfront Fusion]  a  [!DNL Google Services]  mediante un cliente de OAuth personalizado](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md).
1. Abra el módulo [!UICONTROL HTTP] >[!UICONTROL Make an OAuth 2.0 request].
1. Haga clic en **[!UICONTROL Add]** junto al cuadro de conexión.
1. Introduzca los siguientes valores:

   <table style="table-layout:auto">  
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Connection name] </td> 
      <td> <p>Introduzca el nombre de la conexión.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Flow type]</p> </td> 
      <td> <p>[!UICONTROL Authorization Code]</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Authorize URI]</td> 
      <td><code>https://accounts.google.com/o/oauth2/v2/auth</code> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Token URI]</td> 
      <td><code>https://www.googleapis.com/oauth2/v4/token</code> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Scope] </td> 
      <td> <p>Añada ámbitos individuales. Para obtener más información sobre los ámbitos, consulte <a href="https://developers.google.com/identity/protocols/oauth2/scopes">Ámbitos de OAuth 2.O para las API de [!DNL Google]</a> en la documentación de [!DNL Google].</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Scope separator] </td> 
      <td> <p>[!UICONTROL SPACE]</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Client ID] </td> 
      <td> <p>Introduzca su ID de cliente de [!DNL Google]. </p> <p>Para crear un ID de cliente, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md#create2" class="MCXref xref">Crear credenciales de OAuth</a> en <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md" class="MCXref xref">[!DNL Connect Adobe Workfront Fusion] a los [!DNL Google Services] mediante un cliente de OAuth personalizado</a>.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Client Secret]</td> 
      <td> <p>Introduzca el secreto de cliente de [!DNL Google]. </p> <p>Para crear un secreto de cliente, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md#create2" class="MCXref xref">Crear credenciales de OAuth</a> en <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md" class="MCXref xref">[!DNL Connect Adobe Workfront Fusion] a los servicios de [!DNL Google] mediante un cliente de OAuth personalizado</a>.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Authorize parameters]</p> </td> 
      <td> <p>Añada el par clave-valor <code>[!UICONTROL access_type]</code> - <code>[!UICONTROL offline] </code>.</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/google-authentication-http.png"> </p> <p>Nota: Si tiene problemas para autenticarse, por ejemplo, al actualizar el token, intente añadir el par clave-valor <code>[!UICONTROL prompt] </code>- <code>[!UICONTROL consent] </code>.</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. Haga clic **[!UICONTROL Continue]** para guardar la configuración de conexión.
1. Continúe en [Configuración del módulo de solicitud OAuth 2.0](#oauth-20-request-module-setup).

<!--### Instructions for connecting to [!DNL Microsoft Graph API] via the [!UICONTROL HTTP] > [!UICONTROL Make an OAuth 2.0 request] module 

For instructions regarding [!DNL Microsoft Graph API], see [Call the [!DNL MS Graph REST API] via the [!DNL Adobe Workfront Fusion] [!UICONTROL HTTP] > [!UICONTROL Make an OAuth 2.0 request] module](/help/workfront-fusion/create-scenarios/connect-to-apps/call-the-ms-graph-rest-api.md).-->

## Configuración del módulo de solicitud OAuth 2.0

Cuando haya establecido una conexión [!DNL Oauth 2].0 como se describe en [Creación de una conexión para una solicitud  [!DNL OAuth] ](#creating-a-connection-for-an-oauth-request), continúe configurando el módulo como desee. Todos los tókenes de autorización se incluyen automáticamente en esta solicitud y en cualquier otra que utilice la misma conexión.

Al configurar el módulo [!UICONTROL HTTP] >[!UICONTROL Make an OAuth 2.0 request], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, consulte [Asignar información de un módulo a otro en [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

<!--
<img src="" style="width: 350;height: 74;">
-->

<table style="table-layout:auto">  
 <col> 
 <col> 
 <tbody> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener información sobre la configuración de una conexión, consulte <a href="#creating-a-connection-for-an-oauth-request" class="MCXref xref">Creación de una conexión para una solicitud OAuth</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Evaluate all states as errors (except for 2xx and 3xx]) </td> 
   <td> <p>Utilice esta opción para configurar la gestión de errores.</p> <p>Para obtener más información, consulte <a href="/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md" class="MCXref xref">Control de errores en [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL] </td> 
   <td> <p>Introduzca la dirección URL a la que desea enviar una solicitud, como un punto final de API, un sitio web, etc.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Métodos de petición HTTP en [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers] </td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar. Por ejemplo: <code>{"Content-type":"application/json"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> Introduzca los pares de clave-valor de consulta deseados.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Body type]</p> </td> 
   <td> <p>El cuerpo HTTP son los bytes de datos transmitidos en un mensaje de transacción HTTP inmediatamente después de los encabezados, si los hay.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Raw]</strong> </p> <p>El tipo de cuerpo Raw es generalmente adecuado para la mayoría de las solicitudes de cuerpo HTTP, incluso en situaciones donde la documentación para desarrolladores no especifica los datos a enviar.</p> <p>Especifique una forma de analizar los datos en el campo [!UICONTROL Content type].</p> <p>A pesar del tipo de contenido seleccionado, los datos se introducen en cualquier formato estipulado o requerido por la documentación del desarrollador.</p> </li> 
     <li> <p><strong>[!UICONTROL Application/x-www-form-urlencoded]</strong> </p> <p>Este tipo de cuerpo es para PUBLICAR datos que utilizan <code>[!UICONTROL application/x-www-form-urlencoded]</code>.</p> <p>Para <code>[!UICONTROL application/x-www-form-urlencoded]</code>, el cuerpo del mensaje HTTP enviado al servidor es esencialmente una cadena de consulta. Las claves y los valores se codifican en pares clave-valor separados por <code>&amp;</code> y con un <code>=</code> entre la clave y el valor. </p> <p>Para datos binarios, se utiliza <code>use [!UICONTROL multipart/form-data]</code> en su lugar.</p> 
      <div class="example" data-mc-autonum="<b>Example: </b>">
       <span class="autonumber"><span><b>Ejemplo: </b></span></span> 
       <p>Ejemplo del formato de petición HTTP resultante:</p> 
       <p><code>field1=value1&amp;field2=value2</code> </p> 
      </div> </li> 
     <li> <p><strong>[!UICONTROL Multipart/form-data]</strong> </p> <p>[!UICONTROL Multipart/form-data] es una solicitud HTTP de varias partes que se usa para enviar archivos y datos. Normalmente se utiliza para cargar archivos en el servidor.</p> <p>Añada campos para enviarlos en la solicitud. Cada campo debe contener un par clave-valor.</p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Text]</strong> </p> <p>Introduzca la clave y el valor que se enviarán dentro del cuerpo de la solicitud.</p> </li> 
       <li> <p><strong>[!UICONTROL File]</strong> </p> <p>Introduzca la clave y especifique el archivo de origen que desea enviar en el cuerpo de la solicitud.</p> <p>Asigne el archivo que desea cargar desde el módulo anterior (como [!UICONTROL HTTP] &gt;[!UICONTROL Get a File] o [!UICONTROL Google Drive] &gt;[!UICONTROL Download a File)]), o bien ingrese el nombre de archivo y los datos de archivo manualmente.</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Parse response]</p> </td> 
   <td> <p>Habilite esta opción para analizar automáticamente las respuestas y convertir las respuestas JSON y XML para que no necesite utilizar los módulos [!UICONTROL JSON] &gt; [!UICONTROL Parse JSON] o [!UICONTROL XML] &gt; [!UICONTROL Parse XML].</p> <p>Antes de poder usar el contenido JSON o XML analizado, ejecute el módulo manualmente una vez para que el módulo pueda reconocer el contenido de la respuesta y le permita asociarlo en módulos posteriores.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Timeout] </td> 
   <td> <p>Introduzca el tiempo de espera de la solicitud en segundos (1-300). El valor predeterminado es de 40 segundos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Share cookies with other HTTP modules]</td> 
   <td> <p> Active esta opción para compartir cookies del servidor con todos los módulos HTTP de su escenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Self-signed certificate]</td> 
   <td> <p> Cargue el certificado si desea utilizar TLS con el certificado autofirmado.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reject connections that are using unverified (self-signed) certificates] </td> 
   <td> <p>Active esta opción para rechazar conexiones que utilicen certificados TLS no verificados.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Follow redirect]</td> 
   <td> <p> Active esta opción para seguir las redirecciones de URL con respuestas 3xx.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Follow all redirects] </td> 
   <td> <p>Active esta opción para seguir las redirecciones URL con todos los códigos de respuesta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Disable serialization of multiple same query string keys as arrays]</p> </td> 
   <td> <p>De manera predeterminada, [!DNL Workfront Fusion] administra varios valores para la misma clave de parámetro de cadena de consulta de URL que las matrices. Por ejemplo, <code>www.test.com?foo=bar&amp;foo=baz</code> se convertirá en <code>www.test.com?foo[0]=bar&amp;foo[1]=baz</code>. Active esta opción para deshabilitar esta función. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Request compressed content]</td> 
   <td> <p> Active esta opción para solicitar una versión comprimida del sitio web.</p> <p>Esto añade un encabezado <code>[!UICONTROL Accept-Encoding]</code> para solicitar contenido comprimido.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Use Mutual TLS]</td> 
   <td> <p>Active esta opción para utilizar TLS mutuo en la solicitud HTTP.</p> <p>Para obtener más información sobre TLS mutuo, consulte <a href="/help/workfront-fusion/references/apps-and-modules/universal-connectors/use-mtls-in-http-modules.md" class="MCXref xref">Usar TLS mutuo en módulos HTTP en [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>
