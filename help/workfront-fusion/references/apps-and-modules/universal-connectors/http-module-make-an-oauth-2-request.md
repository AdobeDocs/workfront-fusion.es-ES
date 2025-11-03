---
title: HTTP > Crear un módulo de solicitud OAuth 2.0
description: Para realizar una solicitud HTTP(S) de Adobe Workfront Fusion a servidores que requieran una autorización de OAuth 2.0, primero debe crear una conexión OAuth. Adobe Workfront Fusion garantiza que todas las llamadas realizadas con esta conexión tengan los encabezados de autorización adecuados y actualicen automáticamente los tokens asociados cuando sea necesario.
author: Becky
feature: Workfront Fusion
exl-id: a302a1d4-fddf-4a71-adda-6b87ff7dba4b
source-git-commit: 54c368d335b30f55cab19595a5b4740dde6013a7
workflow-type: tm+mt
source-wordcount: '2320'
ht-degree: 70%

---

# Módulo [!UICONTROL HTTP] > [!UICONTROL Realizar una solicitud OAuth 2.0]

>[!NOTE]
>
>Adobe Workfront Fusion requiere una licencia Adobe Workfront Fusion y de Adobe Workfront.

Para realizar una solicitud HTTP(S) de Adobe Workfront Fusion a servidores que requieran una autorización de OAuth 2.0, primero debe crear una conexión OAuth. Adobe Workfront Fusion garantiza que todas las llamadas realizadas con esta conexión tengan los encabezados de autorización adecuados y actualicen automáticamente los tokens asociados cuando sea necesario.

Workfront Fusion admite los siguientes flujos de autenticación de OAuth 2.0:

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

## Crear una conexión para una solicitud [!DNL OAuth]

* [Instrucciones generales para crear una conexión en el módulo de solicitud HTTP > Crear una OAuth 2.0](#general-instructions-for-creating-a-connection-in-the-http--make-an-oauth-20-request-module)
* [Instrucciones para crear una conexión con Google en el módulo de solicitud http > [!UICONTROL Make] an OAuth 2.0](#instructions-for-creating-a-connection-to-google-in-the-http-make-an-oauth-20-request-module)
* [Instrucciones para conectarse a la API de Microsoft Graph mediante el módulo de solicitud HTTP > Crear una OAuth 2.0](#instructions-for-connecting-to-microsoft-graph-api-via-the-http--make-an-oauth-20-request-module)

### Instrucciones generales para crear una conexión en el módulo [!UICONTROL HTTP] > [!UICONTROL Realizar una solicitud OAuth 2.0]

1. Cree un cliente de OAuth en el servicio [!DNL target] con el que desee que Adobe Workfront Fusion se comunique. Es muy probable que esta opción se encuentre en la sección [!UICONTROL Desarrollador] del servicio proporcionado.

   1. Al crear un cliente, introduzca la dirección URL correspondiente en el campo `[!UICONTROL Redirect URL]` o `[!UICONTROL Callback URL]`:

      | América/APAC | `https://app.workfrontfusion.com/oauth/cb/oauth2` |
      |---|---|
      | **EMEA** | `https://app-eu.workfrontfusion.com/oauth/cb/oauth2` |

   1. Después de crear el cliente, el servicio dado muestra 2 claves: `[!UICONTROL Client ID]` y `[!UICONTROL Client Secret]`. Algunos servicios llaman a estos `[!UICONTROL App Key]` y `[!UICONTROL App Secret]`. Guarde la clave y el secreto en una ubicación segura, para que pueda proporcionarlos al crear la conexión en Workfront Fusion.

1. Busque `[!UICONTROL Authorize URI]` y `[!UICONTROL Token URI]` en la documentación de API del servicio proporcionado. Son direcciones URL a través de las cuales Workfront Fusion se comunica con el servicio [!DNL target]. Las direcciones sirven para la autorización de OAuth.

   >[!NOTE]
   >
   >Si el servicio utiliza un flujo implícito, solo necesitará el `[!UICONTROL Authorize URI]`.

1. (Condicional) Si el servicio de destino utiliza ámbitos (derechos de acceso), compruebe cómo separa los ámbitos individuales y asegúrese de establecer el separador en los ajustes avanzados en consecuencia. Si el separador no se ha definido correctamente, Workfront Fusion no podrá crear la conexión y recibirá un error de ámbito no válido.
1. Después de completar los pasos anteriores, puede empezar a crear la conexión OAuth en Workfront Fusion. Añada el módulo de solicitud HTTP > Crear un OAuth 2 a su escenario.
1. En el campo Conexión del módulo, haga clic en **[!UICONTROL Añadir]**.

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
      <td role="rowheader">[!UICONTROL Environment] </td> 
      <td> <p>Seleccione si está utilizando un entorno de producción o de no producción.</p> </td> 
     </tr> 
      <tr> 
      <td role="rowheader">[!UICONTROL Type] </td> 
      <td> <p>Seleccione si utiliza una cuenta de servicio o una cuenta personal.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Flow type]</p> </td> 
      <td> <p>Seleccione el flujo para obtener tókenes.</p> 
       <ul> 
        <li><strong>[!UICONTROL Authorization Code]</strong>: introduzca el <code>[!UICONTROL Authorize URI]</code> y el <code>[!UICONTROL Token URI]</code> de la documentación de la API del servicio.</li> 
        <li><strong>[!UICONTROL Implicit]</strong>: introduzca el <code>[!UICONTROL Authorize URI]</code> de la documentación de la API del servicio.</li> 
       </ul> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Scope] </td> 
      <td> <p>Añada ámbitos individuales. Puede encontrar esta información en la documentación para desarrolladores (API) de un servicio determinado.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Scope separator] </td> 
      <td> <p>Seleccione por qué se deben separarse los ámbitos especificados anteriormente. Puede encontrar esta información en la documentación para desarrolladores (API) de un servicio determinado.</p> <p>Advertencia: Si el separador no está configurado correctamente, Workfront Fusion no creará la conexión y recibirá un error de ámbito no válido.</p> </td> 
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
       </ul> <p>Nota:  <p>El estándar OAuth 2.0 admite al menos 2 métodos de autenticación de cliente durante este paso (<code>[!UICONTROL client_secret_basic]</code> y <code>[!UICONTROL client_secret_post]</code>). Workfront Fusion envía automáticamente el ID de cliente y el secreto especificados mediante el método <code>[!UICONTROL client_secret_post]</code>. Por lo tanto, estos parámetros se incluyen automáticamente como parte del cuerpo de solicitud de token. </p> <p>Para obtener más información sobre la autenticación de OAuth 2.0, consulte <a href="https://tools.ietf.org/html/rfc6749">El marco de autorización de OAuth 2.0</a>.</p> </p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Refresh token parameters]</p> </td> 
      <td> <p>Añada cualquier parámetro que desee incluir en la llamada de token. Los siguientes parámetros estándar siempre se incluyen automáticamente y no es necesario añadirlos.</p> <p>Parámetros estándar:</p> 
       <ul> 
        <li> <p><strong>[!UICONTROL grant_type]</strong>: <code>refresh_token</code></p> </li> 
        <li> <p><strong>[!UICONTROL refresh_token]</strong>: el token de actualización más reciente obtenido por el servicio al que se está conectando</p> </li> 
        <li> <p><strong>[!UICONTROL client_id]</strong>: el ID de cliente que recibió al crear la cuenta se incluye automáticamente en el cuerpo de la solicitud</p> </li> 
        <li> <p><strong>[!UICONTROL client_secret]</strong>: el secreto de cliente que recibió al crear la cuenta se incluye automáticamente en el cuerpo de la solicitud</p> </li> 
       </ul> <p>Nota:  <p>El estándar OAuth 2.0 admite al menos 2 métodos de autenticación de cliente durante este paso (<code>[!UICONTROL client_secret_basic]</code> y <code>[!UICONTROL client_secret_post]</code>). Workfront Fusion envía automáticamente el ID de cliente y el secreto especificados mediante el método <code>[!UICONTROL client_secret_post]</code>. Por lo tanto, estos parámetros se incluyen automáticamente como parte del cuerpo de solicitud de token. </p> <p>Para obtener más información sobre la autenticación de OAuth 2.0, consulte <a href="https://tools.ietf.org/html/rfc6749">El marco de autorización de OAuth 2.0</a>.</p> </p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Custom Headers]</p> </td> 
      <td> <p>Especifique las claves y los valores adicionales que se incluirán en el encabezado de los pasos de [!UICONTROL Token] y [!UICONTROL Refresh Token].</p> <p>Nota:  <p>El estándar OAuth 2.0 admite al menos 2 métodos de autenticación de cliente durante este paso (<code>[!UICONTROL client_secret_basic]</code> y <code>[!UICONTROL client_secret_post]</code>). Workfront Fusion no admite automáticamente el método <code>[!UICONTROL client_secret_basic]</code>. Si el servicio al que se está conectando espera que el ID de cliente y el secreto del cliente se combinen en una sola cadena y luego se codifique base64 en el encabezado Autorización, debe añadir ese encabezado y valor clave aquí.</p> <p> Para obtener más información sobre la autenticación de OAuth 2.0, consulte <a href="https://tools.ietf.org/html/rfc6749">El marco de autorización de OAuth 2.0</a>.</p> </p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Token placement]</p> </td> 
      <td> <p>Seleccione si desea enviar el token en el [!UICONTROL header], la [!UICONTROL query string] o en ambos al conectarse a la dirección URL especificada.</p> <p>Normalmente, los tokens se envían en el encabezado de la solicitud.</p> </td> 
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

1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.
1. Continúe con [Configurar el módulo de solicitud Crear un OAuth 2.0](#configure-the-make-an-oauth-20-request-module).

### Instrucciones para crear una conexión con [!DNL Google] en el [!UICONTROL HTTP] > [!UICONTROL Crear un módulo de solicitud OAuth 2.0]

El siguiente ejemplo muestra cómo se usa el módulo de solicitud [!UICONTROL HTTP] > [!UICONTROL Make an OAuth 2.0] para conectarse a [!DNL Google].

1. Asegúrese de haber creado un proyecto, de haber configurado la configuración de OAuth y de haber generado sus credenciales tal como se describe en el artículo[Conectar Adobe Workfront Fusion a [!DNL Google Services] mediante un cliente de OAuth personalizado](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md).
1. Abra el módulo [!UICONTROL HTTP] > [!UICONTROL Realizar una solicitud OAuth 2.0].
1. En cualquier módulo, haga clic en **[!UICONTROL Agregar]** junto al cuadro Conexión.
1. Introduzca los siguientes valores:

   <table style="table-layout:auto">  
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Connection name] </td> 
      <td> <p>Introduzca un nombre para la conexión. </p> </td> 
     </tr> 
      <tr> 
      <td role="rowheader">[!UICONTROL Environment] </td> 
      <td> <p>Seleccione si está utilizando un entorno de producción o de no producción.</p> </td> 
     </tr> 
      <tr> 
      <td role="rowheader">[!UICONTROL Type] </td> 
      <td> <p>Seleccione si utiliza una cuenta de servicio o una cuenta personal.</p> </td> 
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
      <td> <p>Introduzca su ID de cliente de [!DNL Google]. </p> <p>Para crear un ID de cliente, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md#create-oauth-credentials" class="MCXref xref">Crear credenciales de OAuth</a> en el artículo [!DNL Connect Adobe Workfront Fusion] para [!DNL Google Services] mediante un cliente de OAuth personalizado</a>.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Client Secret]</td> 
      <td> <p>Introduzca el secreto de cliente de [!DNL Google]. </p> <p>Para crear un secreto de cliente, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md#create-oauth-credentials" class="MCXref xref">Crear credenciales de OAuth</a> en el artículo [!DNL Connect Adobe Workfront Fusion] para [!DNL Google] servicios mediante un cliente de OAuth personalizado</a>.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Authorize parameters]</p> </td> 
      <td> <p>Añada el par clave-valor <code>[!UICONTROL access_type]</code> - <code>[!UICONTROL offline] </code>.</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/google-authentication-http.png"> </p> <p>Nota: Si tiene problemas para autenticarse, por ejemplo, al actualizar el token, intente añadir el par clave-valor <code>[!UICONTROL prompt] </code>- <code>[!UICONTROL consent] </code>.</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. Haga clic en **[!UICONTROL Continuar]** para guardar la configuración de conexión.
1. Continúe con [Configurar el módulo de solicitud Crear un OAuth 2.0](#configure-the-make-an-oauth-20-request-module).

## Configuración del módulo de solicitud Make a OAuth 2.0

Después de establecer una conexión OAuth 2.0, siga configurando el módulo como desee. Todos los tókenes de autorización se incluyen automáticamente en esta solicitud y en cualquier otra que utilice la misma conexión.

Al configurar el módulo [!UICONTROL HTTP] > [!UICONTROL Realizar una solicitud OAuth 2.0], Workfront Fusion muestra los campos que se indican a continuación. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, consulte [Asignar información de un módulo a otro en Adobe Workfront Fusion](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

<table style="table-layout:auto">  
 <col> 
 <col> 
 <tbody> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener información sobre cómo configurar una conexión, consulte <a href="#create-a-connection-for-an-oauth-request" class="MCXref xref">Crear una conexión para una solicitud de OAuth</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Evaluate all states as errors (except for 2xx and 3xx)] </td> 
   <td> <p>Utilice esta opción para configurar la gestión de errores.</p> <p>Para obtener más información, consulte <a href="/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md" class="MCXref xref">Control de errores</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL] </td> 
   <td> <p>Introduzca la dirección URL a la que desea enviar una solicitud, como un punto final de API, un sitio web, etc.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Métodos de solicitud HTTP</a>.</p> </td> 
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
     <li> <p><strong>[!UICONTROL Multipart/form-data]</strong> </p> <p>El [!UICONTROL Multipart/form-data] es una solicitud HTTP multipart utilizada para enviar archivos y datos. Normalmente se utiliza para cargar archivos en el servidor.</p> <p>Añada campos para enviarlos en la solicitud. Cada campo debe contener un par clave-valor.</p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Text]</strong> </p> <p>Introduzca la clave y el valor que se enviarán dentro del cuerpo de la solicitud.</p> </li> 
       <li> <p><strong>[!UICONTROL File]</strong> </p> <p>Introduzca la clave y especifique el archivo de origen que desea enviar en el cuerpo de la solicitud.</p> <p>Asigne el archivo que desea cargar desde el módulo anterior (como [!UICONTROL HTTP] &gt; [!UICONTROL Obtener un archivo]) o introduzca el nombre de archivo y los datos de archivo manualmente.</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Parse response]</p> </td> 
   <td> <p>Habilite esta opción para analizar automáticamente las respuestas y convertir las respuestas JSON y XML, de modo que no necesite usar los módulos [!UICONTROL JSON] &gt; [!UICONTROL Parse JSON] o [!UICONTROL XML] &gt; [!UICONTROL Parse XML].</p> <p>Antes de poder usar el contenido JSON o XML analizado, ejecute el módulo manualmente una vez para que el módulo pueda reconocer el contenido de la respuesta y le permita asociarlo en módulos posteriores.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Timeout] </td> 
   <td> <p>Introduzca el tiempo de espera de la solicitud en segundos (1-300). El valor predeterminado es de 40 segundos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Share cookies with other HTTP modules]</td> 
   <td> <p> Habilite esta opción para compartir cookies del servidor con todos los módulos HTTP de su escenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Self-signed certificate]</td> 
   <td> <p>Para usar un certificado autofirmado o una clave privada para TLS, haga clic en <b>Extraer</b> y proporcione el archivo y la contraseña del certificado o la clave privada.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reject connections that are using unverified (self-signed) certificates] </td> 
   <td> <p>Habilite esta opción para rechazar conexiones que utilicen certificados TLS no verificados.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Follow redirect]</td> 
   <td> <p> Habilite esta opción para seguir las redirecciones de URL con respuestas 3xx.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Follow all redirects] </td> 
   <td> <p>Habilite esta opción para seguir las redirecciones URL con todos los códigos de respuesta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Disable serialization of multiple same query string keys as arrays]</p> </td> 
   <td> <p>De forma predeterminada, Workfront Fusion gestiona varios valores para la misma clave de parámetro de cadena de consulta de URL que las matrices. Por ejemplo, <code>www.test.com?foo=bar&amp;foo=baz</code> se convertirá en <code>www.test.com?foo[0]=bar&amp;foo[1]=baz</code>. Active esta opción para deshabilitar esta función. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Request compressed content]</td> 
   <td> <p> Habilite esta opción para solicitar una versión comprimida del sitio web.</p> <p>Esto añade un encabezado <code>[!UICONTROL Accept-Encoding]</code> para solicitar contenido comprimido.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Use Mutual TLS]</td> 
   <td> <p>Habilite esta opción para utilizar TLS mutuo en la solicitud HTTP.</p> <p>Para obtener más información sobre TLS mutuo, consulte <a href="/help/workfront-fusion/references/apps-and-modules/universal-connectors/use-mtls-in-http-modules.md" class="MCXref xref">Usar TLS mutuo en módulos HTTP en Adobe Workfront Fusion</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>
