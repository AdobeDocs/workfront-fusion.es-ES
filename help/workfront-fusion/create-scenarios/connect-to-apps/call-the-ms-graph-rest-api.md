---
title: Llamar a la API de REST de MS Graph
description: Llame a la API de REST de MS Graph a través de Adobe Workfront Fusion HTTP &> Cree un módulo de solicitud OAuth 2.0
author: Becky
feature: Workfront Fusion
exl-id: f411c807-955d-44fe-98b1-3ebba3fe0861
source-git-commit: b2ca63ca5af26ee79758798118817b55113b3bd0
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 18%

---

# Llamar a la API de REST de MS Graph

Se accede a muchos servicios web de Microsoft a través de la API de Microsoft Graph. Puede crear una conexión a la API de Microsoft Graph con el módulo de solicitud Workfront Fusion HTTP > Crear una OAuth 2.0.

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

## Registre Workfront Fusion en el portal de registro de aplicaciones de Microsoft

Para crear una conexión a la API de REST de Microsoft Graph, primero debe registrar Adobe Workfront Fusion.

1. Comience a registrar una nueva aplicación como se describe en [Registre una aplicación con Microsoft identity platform](https://docs.microsoft.com/en-us/graph/auth-register-app-v2) en la documentación de Microsoft.

   Como parte del registro, Microsoft requiere la siguiente información:

   <table style="table-layout:auto">
      <tr>
        <td>Nombre de aplicación</td>
        <td>Introduzca un nombre para la aplicación, como "Mi aplicación de Workfront Fusion".</td>
      </tr>
      <tr>
        <td>Dirección URL de redireccionamiento</td>
        <td><code>https://app.workfrontfusion.com/oauth/cb/oauth2</code></td>
      </tr>
    </table>

1. Cuando haya completado el registro de la aplicación, tome nota del ID de aplicación.

   >[!IMPORTANT]
   >
   >Necesitará el ID de aplicación para configurar la conexión en Workfront Fusion.

1. Genere un secreto de cliente. Anote este secreto.

   Para obtener instrucciones, consulte [Registrar una aplicación con Microsoft identity platform](https://docs.microsoft.com/en-us/graph/auth-register-app-v2) en la documentación de Microsoft.

   >[!IMPORTANT]
   >
   >Necesitará el Secreto del cliente para configurar su conexión en Workfront Fusion.

1. Configure los permisos para su aplicación.

   Para obtener información específica sobre cómo localizar y configurar estos campos, consulte la sección &quot;Configuración de permisos para Microsoft Graph&quot; en [Obtener acceso sin un usuario](https://docs.microsoft.com/en-us/graph/auth-v2-service) en la documentación de Microsoft.

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">¿Qué tipo de permisos requiere su aplicación?</td> 
      <td>Seleccione <code>Delegated permissions</code>.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">Seleccionar permisos</td> 
      <td> <p>Seleccione los siguientes permisos:</p> 
       <ul> 
        <li> <p><code>offline_access</code> </p> </li> 
        <li> <p><code>openid</code> </p> </li> 
        <li> <p>Cualquier otro permiso requerido por sus integraciones (Ejemplo: <code>User.Read</code>)</p> </li> 
       </ul> <p><b>Importante</b>: Necesitará los permisos seleccionados para configurar su conexión en Workfront Fusion.</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. Continúe con [Configuración de la conexión de la API de MS Graph en Workfront Fusion](#configure-your-ms-graph-api-connection-in-workfront-fusion).

## Configuración de la conexión de la API de MS Graph en Workfront Fusion

Después de registrar Workfront Fusion como se describe en [Registrar Workfront Fusion en el portal de registro de aplicaciones de Microsoft](#register-workfront-fusion-in-the-microsoft-application-registration-portal), puede configurar la conexión en el módulo de solicitud HTTP > Crear una Oauth 2.0.

1. Añada un módulo de llamada HTTP > Crear un módulo de llamada OAuth 2.0 a su escenario.
1. Haga clic en **Agregar** junto al campo de conexión.
1. Configure los campos de conexión de la siguiente manera:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">Nombre de conexión</td> 
      <td>Introduzca un nombre para la conexión. </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p role="rowheader">Entorno</p> </td> 
      <td>Seleccione si desea conectarse a una cuenta de producción o de no producción. </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p role="rowheader">Tipo</p> </td> 
      <td>Seleccione si desea conectarse a una cuenta de servicio o a una personal. </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p role="rowheader">Tipo de flujo</p> </td> 
      <td>Seleccione <code>Authorization Code</code>. </td> 
     </tr> 
     <tr> 
      <td role="rowheader">Autorizar URI</td> 
      <td>Escriba <code>https://login.microsoftonline.com/common/oauth2/v2.0/authorize</code>. </td> 
     </tr> 
     <tr> 
      <td role="rowheader">URI de token</td> 
      <td>Escriba <code>https://login.microsoftonline.com/common/oauth2/v2.0/token</code>. </td> 
     </tr> 
     <tr> 
      <td role="rowheader">Ámbito</td> 
      <td> <p>Escriba los permisos que seleccionó al registrarse, como se describe en <a href="#register-workfront-fusion-in-the-microsoft-application-registration-portal" class="MCXref xref">Registrar Workfront Fusion en el portal de registro de aplicaciones de Microsoft</a>.</p> <p>Para cada ámbito, haga clic en <b>Agregar</b> y escriba el permiso.</p> <p>Ejemplo: <code>offline_access</code>.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">Separador de ámbito</td> 
      <td>Seleccione <code>SPACE</code>. </td> 
     </tr> 
     <tr> 
      <td role="rowheader">Id. de cliente</td> 
      <td>Introduzca el ID de aplicación del paso 2 en <a href="#register-workfront-fusion-in-the-microsoft-application-registration-portal" class="MCXref xref">Registre Workfront Fusion en el portal de registro de aplicaciones de Microsoft</a>.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">Secreto de cliente</td> 
      <td>Escriba el Secreto de cliente que generó en el paso 3 de <a href="#register-workfront-fusion-in-the-microsoft-application-registration-portal" class="MCXref xref">Registrar Workfront Fusion en el Portal de registro de aplicaciones de Microsoft</a>.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">Autorizar parámetros</td> 
      <td> <p>Añada los siguientes parámetros Authorize. Para cada parámetro que esté agregando, haga clic en <b>Agregar elemento</b> e introduzca lo siguiente: </p> 
       <ul> 
        <li> <p>Clave:<code> response_mode</code> Valor: <code>query</code></p> </li> 
        <li> <p>Clave: <code>prompt </code>Valor: <code>consent</code></p> </li> 
       </ul> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">Parámetros de token de acceso</td> 
      <td>No es necesario que introduzca nada en este campo.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">Actualizar parámetros de token</td> 
      <td> 
       <ol> 
        <li value="1"> <p>Haga clic en <b>Agregar elemento</b>.</p> </li> 
        <li value="2"> <p>En el campo <b>Clave</b>, escriba <code>scope</code>.</p> </li> 
        <li value="3"> <p>En el campo <b>Valor</b>, escriba todos los ámbitos especificados en el campo de ámbito, separados por espacios.</p> <p>Ejemplo: <code>offline_access openid User.Read</code></p> </li> 
       </ol> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">Encabezados personalizados</td> 
      <td>No es necesario que introduzca nada en este campo.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">Ubicación del token</td> 
      <td><code>In the header</code> </td> 
     </tr> 
    </tbody> 
   </table>

1. Haga clic en **Continuar**.
1. En la ventana que aparece, haga clic en **Aceptar** para completar la conexión y volver al módulo.
