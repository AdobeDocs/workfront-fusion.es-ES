---
title: Conexión de Adobe Workfront Fusion a Google Services con un cliente de OAuth personalizado
description: Puede utilizar Adobe Workfront Fusion para conectarse a los servicios de Google mediante un cliente de OAuth personalizado. Este procedimiento requiere una cuenta de Google existente.
author: Becky
feature: Workfront Fusion
exl-id: 2f0bc289-4ecf-4a31-9d7b-641bbca6fc95
source-git-commit: b2ca63ca5af26ee79758798118817b55113b3bd0
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 27%

---

# Conexión de Adobe Workfront Fusion a Google Services con un cliente de OAuth personalizado

Puede utilizar Adobe Workfront Fusion para conectarse a los servicios de Google mediante un cliente de OAuth personalizado. Este procedimiento requiere una cuenta de Google existente.

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

Necesita una cuenta existente de Google para realizar esta conexión.

## Conectar Fusion a Google Services mediante un cliente de OAuth personalizado

Para crear esta conexión, debe crear y configurar un proyecto en la plataforma Google Cloud y, a continuación, configurar una conexión en Fusion basada en ese proyecto.

>[!NOTE]
>
>Este procedimiento está diseñado para:
>
>* Uso personal (usuarios de `@gmail.com` y `@googlemail.com`)
>* Uso interno (usuarios de Google Workspace que prefieren utilizar un cliente de OAuth personalizado)

* [Creación de un proyecto en Google Cloud Platform](#create-a-project-on-google-cloud-platform)
* [Configurar las opciones de consentimiento de OAuth](#configure-oauth-consent-settings)
* [Crear credenciales de OAuth](#create-oauth-credentials)
* [Conexión a Google en Workfront Fusion](#connect-to-google-in-workfront-fusion)

### Creación de un proyecto en Google Cloud Platform

Para crear un proyecto en Google Cloud Platform:

1. Comience a crear un proyecto en Google Cloud Platform.

   Para obtener instrucciones, consulte [Crear un proyecto de Google Cloud](https://developers.google.com/workspace/guides/create-project) en la documentación de Google.
1. Al habilitar las API, debe habilitar la API de Google Drive, así como la API de todas las aplicaciones de Google que desee utilizar (como la API de hojas de cálculo de Google).
1. Termine de crear el proyecto.
1. Continúe en la sección [Establecer la configuración de consentimiento de OAuth](#configure-oauth-consent-settings) de este artículo.

### Configuración del consentimiento de OAuth

1. Comience a configurar OAuth para su proyecto

   Para obtener instrucciones, consulte [Configuración de la pantalla de consentimiento de OAuth y selección de ámbitos](https://developers.google.com/workspace/guides/configure-oauth-consent) en la documentación de Google.
1. Seleccione **Externa** y haga clic en **Crear**.

   >[!NOTE]
   >
   >No se le aplicará ningún cargo si selecciona esta opción. Para obtener más información, consulte la información de Google sobre las excepciones a los requisitos de verificación.

1. Rellene los campos obligatorios tal como se indica a continuación:

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>Nombre de aplicación</p> </td> 
      <td> <p>Introduzca el nombre de la aplicación que solicita consentimiento.</p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Ejemplo: </b></span></span>Adobe Workfront Fusion </p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">Correo electrónico de asistencia al usuario</td> 
      <td>Introduzca una dirección de correo electrónico para que los usuarios se pongan en contacto con usted si tienen preguntas sobre su consentimiento al conectarse a esta aplicación.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">Direcciones de correo</td> 
      <td>Escriba una o más direcciones de correo electrónico que Google puede utilizar para notificarle sobre cualquier cambio en su proyecto.</td> 
     </tr> 
    </tbody> 
   </table>

1. En Dominios autorizados, haga clic en **Agregar dominio** e introduzca `workfrontfusion.com`.
1. Agregue los siguientes ámbitos:

   <table style="table-layout:auto">
    <col> 
    <col> 
    <thead> 
     <tr> 
      <th>Servicio/API</th> 
      <th>Ámbitos obligatorios</th> 
     </tr> 
    </thead> 
    <tbody> 
     <tr> 
      <td> <p>Gmail</p> </td> 
      <td> <p>https://mail.google.com/</p> <p>https://www.googleapis.com/auth/gmail.labels</p> <p>https://www.googleapis.com/auth/gmail.send</p> <p>https://www.googleapis.com/auth/gmail.readonly</p> <p>https://www.googleapis.com/auth/gmail.compose</p> <p>https://www.googleapis.com/auth/gmail.insert</p> <p>https://www.googleapis.com/auth/gmail.modify</p> <p>https://www.googleapis.com/auth/gmail.metadata</p> </td> 
     </tr> 
     <tr> 
      <td> <p>Google Drive</p> </td> 
      <td> <p>https://www.googleapis.com/auth/drive</p> <p>https://www.googleapis.com/auth/drive.readonly</p> </td> 
     </tr> 
    </tbody> 
   </table>

   Es posible que tenga que expandir la lista o ir a la siguiente página de la lista para verlos todos.

1. (Opcional) Añada al proyecto cualquier usuario de prueba.
1. Examine la información para comprobar su precisión y, a continuación, haga clic en **Volver al panel de control**.

   >[!NOTE]
   >
   >No es necesario que envíe la pantalla de consentimiento y la solicitud para que Google la verifique.

1. Continúe hasta [Crear credenciales de OAuth](#create-oauth-credentials).

### Crear credenciales de OAuth

1. Comience a crear credenciales de ID de cliente de OAuth.

   Para obtener instrucciones, consulte [Crear credenciales de acceso](https://developers.google.com/workspace/guides/create-credentials) en la documentación de Google.

   >[!NOTE]
   >
   >Si no es la primera API o servicio (Gmail o Google Drive) que habilita, no es necesario que cree nuevas credenciales.

1. Rellene los campos obligatorios tal como se indica a continuación:

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">Tipo de aplicación</td> 
      <td> <p> aplicación web</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">Nombre</td> 
      <td>Workfront Fusion </td> 
     </tr> 
    </tbody> 
   </table>

1. En URI de redireccionamiento autorizados, escriba **uno** de los siguientes elementos:

   * Para Gmail o Google Drive: `https://app.workfrontfusion.com/oauth/cb/google-restricted`

   * Para otras aplicaciones de Google: `https://app.workfrontfusion.com/oauth/cb/google`

1. Haga clic en **Crear**.

   Se muestran el ID de cliente y el Secreto de cliente.

1. Copie el ID de cliente y el Secreto del cliente a una ubicación segura. Los utilizará para establecer una conexión en Workfront Fusion.
1. Continuar a [Conectarse a Google en Workfront Fusion](#connect-to-google-in-workfront-fusion).

### Conexión a Google en Workfront Fusion

El proceso de creación de una conexión con Google varía en función de si utiliza un módulo de un servicio de Google (como Hojas de cálculo de Google o Google Docs) o si se conecta a Google mediante el módulo de solicitud HTTP >Crear una OAuth2.0.

* [Conectarse a Google en un servicio de Google](#connect-to-google-in-a-google-service)
* [Conéctese a Google en el módulo de solicitud HTTP > Crear una OAuth2.0](#connect-to-google-in-the-http--make-an-oauth20-request-module)

#### Conectarse a Google en un servicio de Google

1. En Workfront Fusion, busque el módulo de Google para el que debe crear una conexión.
1. Haga clic en **Create a connection** y luego haga clic en **Show advanced settings**.
1. Rellene los campos Nombre de conexión, Entorno y Tipo según corresponda.
1. Escriba el ID de cliente y el Secreto de cliente que recuperó en [Crear credenciales de OAuth](#create-oauth-credentials) en los campos respectivos y, a continuación, haga clic en **Continuar**.

1. Inicie sesión con su cuenta de Google.

   Se muestra la ventana **This app isn&#39;t verified**. Tenga en cuenta que la &quot;aplicación&quot; mencionada en el título de la ventana es el cliente de OAuth que ha creado anteriormente.

1. Haga clic en **Avanzado** y, a continuación, haga clic en **Ir a Workfront Fusion (inseguro)** para permitir el acceso con su cliente de OAuth personalizado.

1. Haga clic en **Permitir** para conceder permiso a Workfront Fusion.
1. En la ventana que aparece, vuelva a hacer clic en **Allow** para confirmar sus opciones.

   Se establece la conexión con el servicio de Google deseado mediante un cliente de OAuth personalizado.

#### Conéctese a Google en el módulo de solicitud HTTP > Crear una OAuth2.0 {#connect-to-google-in-the-http--make-an-oauth20-request-module}

Para obtener instrucciones sobre cómo conectarse a Google en el módulo de solicitud HTTP > Crear una OAuth2.0, consulte [Instrucciones para crear una conexión con Google en el artículo HTTP > Crear un módulo de solicitud OAuth 2.0](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-an-oauth-2-request.md#instructions-for-creating-a-connection-to-google-in-the-http-make-an-oauth-20-request-module) en el artículo HTTP > Crear un módulo de solicitud OAuth 2.0.

## Posible mensaje de error:[403 Acceso no configurado]

Si se muestra el mensaje de error `403 Access Not Configured`, debe habilitar la API correspondiente en Google Cloud Platform. Para habilitar la API, siga los pasos de la sección [Crear un proyecto en Google Cloud Platform](#create-a-project-on-google-cloud-platform) de este artículo.
