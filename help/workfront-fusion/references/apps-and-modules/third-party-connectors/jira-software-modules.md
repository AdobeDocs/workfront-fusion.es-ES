---
title: Módulos de software Jira
description: En un escenario de  [!DNL Adobe Workfront Fusion]  puede automatizar los flujos de trabajo que utilizan  [!DNL Jira] Software, así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: 92cac080-d8f6-4770-a6a6-8934538c978b
source-git-commit: d4187aff574ceaf4d27112fc2ce8880421e77d0d
workflow-type: tm+mt
source-wordcount: '2208'
ht-degree: 81%

---

# Módulos de [!DNL Jira Software]

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!DNL Jira Software], así como conectarlo a varias aplicaciones y servicios de terceros.

Estas instrucciones se aplican tanto a los módulos de Jira Cloud como al servidor Jira.

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
   <p>Actual: no se requiere licencia de Workfront Fusion.</p>
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

Para conectar [!DNL Jira Software] a [!DNL Workfront Fusion], debe crear un token de API e insertarlo junto con la URL de servicio y el nombre de usuario en el campo [!UICONTROL Create a connection] de [!DNL Workfront Fusion].

#### Crear un token de API en [!DNL Jira]

1. Cree un token de API en Jira.

   Para obtener instrucciones, recomendamos buscar &quot;Crear un token de API&quot; en la documentación de Jira.
1. Después de crear el token, cópielo en una ubicación segura.

   >[!IMPORTANT]
   >
   >No se puede volver a ver el token después de cerrar este diálogo.
1. Almacene el token generado en un lugar seguro.
1. Continúe en [Configurar el token de API  [!DNL Jira]  en  [!DNL Workfront Fusion]](#configure-the-jira-api-token-in-workfront-fusion).

#### Configurar el token de la API [!DNL Jira] en [!DNL Workfront Fusion]

1. En cualquier módulo de [!DNL Jira Cloud] en [!DNL Workfront Fusion], haga clic en **[!UICONTROL Añadir]** junto al campo [!UICONTROL conexión].
1. Especifique la siguiente información:

   * **Entorno**
   * **Tipo**
   * **[!UICONTROL URL de servicio]:** Esta es la URL base que usas para acceder a tu cuenta Jira. Ejemplo: `yourorganization.atlassian.net`
   * **[!UICONTROL Username]**
   * **[!UICONTROL API token]:**: se trata del token de API que ha creado en la sección [Crear un token de API [!DNL Jira]](#create-an-api-token-in-jira) de este artículo.

1. Haga clic en [!UICONTROL Continue] para crear la conexión y volver al módulo.

### Conectar [!DNL Jira Server] a [!DNL Workfront Fusion]

Para autorizar una conexión entre [!DNL Workfront Fusion] y [!DNL Jira Server], necesita su clave de cliente, clave privada y URL del servicio. Es posible que deba comunicarse con el administrador de [!DNL Jira] para obtener esta información.

* [Generación de claves públicas y privadas para su conexión a  [!DNL Jira] ](#generate-public-and-private-keys-for-your-jira-connection)
* [Configuración de la aplicación cliente como consumidor en  [!DNL Jira]](#configure-the-client-app-as-a-consumer-in-jira)
* [Creación de una conexión a  [!DNL Jira] Server o Jira Data Center en  [!DNL Workfront Fusion]](#create-a-connection-to-jira-server-or-jira-data-center-in-workfront-fusion)

#### Generación de claves públicas y privadas para su conexión a [!DNL Jira]

Para adquirir una clave privada para la conexión de [!DNL Workfront Fusion Jira], debe generar claves públicas y privadas. Esto se realiza a través del terminal del equipo. Puede localizar el terminal buscando terminal en el menú de inicio o en la barra de búsqueda del equipo (no en la barra de búsqueda del explorador).

1. En su terminal, ejecute los comandos `openssl` siguientes.

   * `openssl genrsa -out jira_privatekey.pem 1024`

     Este comando genera una clave privada de 1024 bits.

   * `openssl req -newkey rsa:1024 -x509 -key jira_privatekey.pem -out jira_publickey.cer -days 365`

     Este comando crea un certificado X509.

   * `openssl pkcs8 -topk8 -nocrypt -in jira_privatekey.pem -out jira_privatekey.pcks8`

     Este comando extrae la clave privada (formato PKCS8) al archivo `jira_privatekey.pcks8`.

   * `openssl x509 -pubkey -noout -in jira_publickey.cer  > jira_publickey.pem`

     Este comando extrae la clave pública del certificado al archivo `jira_publickey.pem`.

     >[!NOTE]
     >
     >Si utiliza Windows, es posible que tenga que guardar manualmente la clave pública del archivo `jira_publickey.pem`:
     >
     >1. En el terminal, ejecute el comando siguiente:
     >   
     >   `openssl x509 -pubkey -noout -in jira_publickey.cer`
     >   
     >1. Copie la salida de terminal, incluidos `-------BEGIN PUBLIC KEY--------` y `-------END PUBLIC KEY--------`.
     >   
     >1. Pegue la salida de terminal en un archivo con nombre `jira_publickey.pem`.


1. Continúe con [Configuración de la aplicación cliente como consumidor en  [!DNL Jira]](#configure-the-client-app-as-a-consumer-in-jira)

#### Configuración de la aplicación cliente como consumidor en [!DNL Jira]

1. Inicie sesión en su instancia de [!DNL Jira].
1. En el panel de navegación izquierdo, haga clic en **[!UICONTROL [!DNL Jira]Configuración]** ![Icono de configuración de Jira](/help/workfront-fusion/references/apps-and-modules/assets/jira-settings-icon.png) > **[!UICONTROL Aplicaciones]**> **[!UICONTROL Vínculos de aplicación]**.
1. En el campo **[!UICONTROL Introduzca la dirección URL de la aplicación que desea vincular]**, escriba

   ```
   https://app.workfrontfusion.com/oauth/cb/workfront-jiraserver-oauth1
   ```

1. Haga clic en **[!UICONTROL Crear nuevo vínculo]**. Ignore el mensaje de error “No se ha recibido respuesta de la dirección URL que ha introducido”.
1. En la ventana **[!UICONTROL Vincular aplicaciones]**, introduzca valores en los campos **[!UICONTROL Clave del cliente]** y **[!UICONTROL Secreto compartido]**.

   Puede elegir los valores de estos campos.

1. Copie los valores de los campos **[!UICONTROL Clave del cliente]** y **[!UICONTROL Secreto compartido]** en una ubicación segura.

   Necesitará estos valores más adelante en el proceso de configuración.

1. Rellene los campos de la dirección URL tal como se indica a continuación:

   | Campo | Descripción |
   |---|---|
   | [!UICONTROL URL de token de solicitud] | `<Jira base url>/plugins/servlet/oauth/request-token` |
   | [!UICONTROL URL de autorización] | `<Jira base url>/plugins/servlet/oauth/authorize` |
   | [!UICONTROL URL de token de acceso] | `<Jira base url>/plugins/servlet/oauth/access-token` |

1. Seleccione la casilla de verificación **[!UICONTROL Crear vínculo entrante]**.
1. Haga clic en **[!UICONTROL Continuar]**.
1. En la ventana **[!UICONTROL Vincular aplicaciones]**, rellene los campos siguientes:

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

1. Haga clic en **[!UICONTROL Continuar]**.
1. Continúe para [Crear una conexión a  [!DNL Jira Server]  o a  [!DNL Jira Data Center]  en  [!DNL Workfront Fusion]](#create-a-connection-to-jira-server-or-jira-data-center-in-workfront-fusion)

#### Crear una conexión a [!DNL Jira Server] o a [!DNL Jira Data Center] en [!DNL Workfront Fusion]

>[!NOTE]
>
>Utilice la aplicación [!DNL Jira Server] para conectarse a [!DNL Jira Server] o a [!DNL Jira Data Center].

1. En cualquier módulo de [!DNL Jira Server] en [!DNL Workfront Fusion], haga clic en **[!UICONTROL Añadir]** junto al campo [!UICONTROL conexión].
1. En el panel [!UICONTROL Crear una conexión], rellene los campos siguientes:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td> <p>Introduzca un nombre para la conexión</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Environment]</p> </td> 
      <td> <p>Seleccione si está utilizando un entorno de producción o de no producción.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Type]</p> </td> 
      <td> <p>Seleccione si utiliza una cuenta de servicio o una cuenta personal.</p> </td> 
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

1. Haga clic en **[!UICONTROL Continuar]** para crear la conexión y volver al módulo.

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
     <li value="1">Haga clic en <strong>[!UICONTROL Add]</strong></li> 
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
* [[!UICONTROL Crear un registro]](#create-a-record)
* [[!UICONTROL Llamada de API personalizada]](#custom-api-call)
* [[!UICONTROL Delete a record]](#delete-a-record)
* [[!UICONTROL Download an attachment]](#download-an-attachment)
* [[!UICONTROL Leer un registro]](#read-a-record)
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
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Jira Software] a [!DNL Workfront Fusion], consulte <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL Jira Software] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sprint ID]</td> 
   <td>Introduzca o asigne el ID de sprint del sprint al que desea añadir un problema.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Issue ID or Keys]</td> 
   <td>Para cada problema o clave que desee ver en la experiencia, haga clic en <b>[!UICONTROL Agregar elemento]</b> e introduzca el identificador o la clave del problema. Puede introducir hasta 50 en un módulo.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Crear un registro]

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
   <td> <p>Seleccione el tipo de registro que desea que cree el módulo y, a continuación, rellene los demás campos específicos de ese tipo de registro que aparecen en el módulo.</p> 
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

#### [!UICONTROL Llamada de API personalizada]

Este módulo de acción le permite realizar una llamada autenticada personalizada a la API [!DNL Jira Software]. Utilice este módulo para crear una automatización del flujo de datos que no puedan realizar los otros [!DNL Jira Software] módulos.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Jira Software] a [!DNL Workfront Fusion], consulte <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL Jira Software] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Introduzca una ruta relativa a<code>&lt;Instance URL>/rest/api/2/ </code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   td&gt; <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td> 
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
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la instrucción condicional.</p> 
     <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png">  </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Eliminar un registro]

Este módulo de acción elimina el registro especificado.

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
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Jira Software] a [!DNL Workfront Fusion], consulte <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL Jira Software] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Introduzca o asigne el ID del archivo adjunto que desea descargar.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Leer un registro]

Este módulo de acción lee datos de un único registro de [!DNL Jira Software].

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
   <td>Seleccione las salidas que desea recibir. Las opciones de salida están disponibles en función del tipo de registro seleccionado en el campo “[!UICONTROL Record Type]”.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td> <p>Introduzca o asigne el ID único de [!DNL Jira Software] del registro que desea que lea el módulo.</p> </td> 
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
   <td>Introduzca o asigne el ID o la clave del registro que desea actualizar y, a continuación, rellene los demás campos específicos de ese tipo de registro que aparecen en el módulo.</td> 
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
