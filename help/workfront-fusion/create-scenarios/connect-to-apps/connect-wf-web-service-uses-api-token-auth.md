---
title: Conecte Adobe Workfront Fusion a un servicio web que utilice la autorización de tokens de API
description: Algunos servicios no permiten que soluciones de integración como Adobe Workfront Fusion creen una aplicación que pueda utilizar fácilmente en su situación.
author: Becky
feature: Workfront Fusion
exl-id: 4a8ac816-52de-41e8-96d7-1c8cde2ebe32
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 8%

---

# Conecte Adobe Workfront Fusion a un servicio web que utilice la autorización de tokens de API

Algunos servicios no permiten que soluciones de integración como Adobe Workfront Fusion creen una aplicación que pueda utilizar fácilmente en su situación.

La solución a esta situación es conectar el servicio deseado (aplicación) a Workfront Fusion mediante el módulo HTTP > Crear una solicitud.

Este artículo explica cómo conectar casi cualquier servicio web a Workfront Fusion mediante una clave de API/token de API.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront 
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
   <p>Heredado: cualquiera </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Plan Select or Prime Workfront: su organización debe adquirir Adobe Workfront Fusion.</li><li>Plan Ultimate Workfront: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe adquirir Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Conectarse a un servicio web que utiliza un token de API

El procedimiento para conectar el servicio a través de un token de API es similar para la mayoría de los servicios web.

1. Cree una aplicación en el sitio web del servicio web, como se explica en la sección [Cree una nueva aplicación y obtenga el token de API](#create-a-new-application-and-obtain-the-api-token) en este artículo.
1. Obtenga la clave de API o el token de API.
1. Añada el módulo HTTP > Crear una solicitud de Workfront Fusion a su escenario.
1. Configure el módulo según la documentación de API del servicio web y ejecute el escenario, tal como se explica en la sección [Configurar el módulo HTTP](#set-up-the-http-module) en este artículo.

>[!NOTE]
>
>En este ejemplo, se conecta al servicio de notificaciones push-over.

## Cree una nueva aplicación y obtenga el token de API

>[!NOTE]
>
>Existen muchas maneras diferentes en que los servicios web crean y distribuyen claves API o tokens API. Para obtener instrucciones sobre la obtención de una clave de API y un token para el servicio web deseado, vaya al sitio web del servicio y busque &quot;clave de API&quot; o &quot;token de API&quot;.
>
>Solo incluimos instrucciones para obtener una clave de API de Pushover como ejemplo de lo que podría encontrar.

1. Inicie sesión en su cuenta de Pushover.
1. Haga clic en **Crear una aplicación/token de API** en la parte inferior de la página.
1. Rellene la información de la aplicación y haga clic en **Crear una aplicación**.
1. Almacene el token de API proporcionado en un lugar seguro. Lo necesitará para que el módulo Workfront Fusion HTTP > Crear una solicitud se conecte al servicio web deseado (Pushover, en este caso).

## Configuración del módulo HTTP

Para conectar un servicio web a su situación de Workfront Fusion, debe utilizar el módulo HTTP > Crear una solicitud en dicha situación y configurar el módulo según la documentación de la API del servicio web.

1. Añada el módulo HTTP > Crear una solicitud a su escenario.
1. Para insertar un mensaje mediante Workfront Fusion, configure el módulo HTTP de la siguiente manera.

   >[!NOTE]
   >
   >Esta configuración del módulo corresponde a la documentación de la API del servicio web Pushover. La configuración puede ser diferente para otros servicios web. Por ejemplo, el token de API se puede insertar en el encabezado y no en el campo Cuerpo.

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> URL</td> 
      <td> <p><code>https://api.pushover.net/1/messages.json</code> </p> <p>El campo URL contiene el extremo que puede encontrar en la documentación de API del servicio web.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> Método</td> 
      <td> <p><code>POST</code> </p> <p>El método utilizado depende del punto de conexión correspondiente. El punto final de Pushover para insertar mensajes utiliza el método POST.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> Encabezados</p> </td> 
      <td> <p>Algunos servicios web pueden utilizar encabezados para especificar la autenticación de token de API u otros parámetros. Este no es el caso en nuestro ejemplo, ya que el extremo de Pushover para insertar mensajes utiliza Body (ver a continuación) para todos los tipos de solicitud.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> Cadena de consulta</p> </td> 
      <td> <p>Algunos servicios web pueden utilizar una cadena de consulta para especificar otros parámetros. Este no es el caso en nuestro ejemplo, ya que el servicio web Pushover utiliza Body (consulte a continuación) para todos los tipos de solicitud.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> Tipo de cuerpo</p> </td> 
      <td> <p><code>Raw</code> </p> <p>Esta configuración le permite seleccionar el tipo de contenido JSON en el campo Tipo de contenido que aparece a continuación.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> Tipo de contenido</p> </td> 
      <td> <p><code>JSON (application/json)</code> </p> <p>JSON es el tipo de contenido requerido por la aplicación Pushover. Esto puede diferir de otros servicios web.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> Solicitar contenido</p> </td> 
      <td> <p>Introduzca el contenido de la solicitud de cuerpo en formato JSON. Puede usar el módulo JSON &gt; Crear JSON como se explica en <a href="#map-the-json-body-using-the-json--create-json-module" class="MCXref xref">Asignar el cuerpo del JSON usando el módulo JSON &gt; Crear módulo JSON</a> en este artículo. O puede ingresar el contenido JSON manualmente, como se explica en <a href="#enter-the-json-body-manually" class="MCXref xref">Escriba el cuerpo de JSON manualmente</a> en este artículo.</p> <p>Consulte la documentación de la API del servicio web para conocer los parámetros necesarios para ese servicio web.</p> </td>

   </tr> 
    </tbody> 
   </table>

## Introduzca el cuerpo de JSON manualmente

Especifique parámetros y valores en formato JSON.

>[!BEGINSHADEBOX]

**Ejemplo:**

```
{"user":"12345c2ecu1hq42ypqzhswbyam34",
"token":"123459evz8aepwtxydndydgyumbfx",
"message":"Hello World!",
"title":"The Push Notification"}
```

>[!ENDSHADEBOX]

Este ejemplo incluye la siguiente información.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p> usuario</p> </td> 
   <td> <p>Su USER_KEY. Se encuentra en su panel Pushover.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> token </td> 
   <td> <p>Su token de API/clave de API que se generó al crear su aplicación Pushover.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> message </td> 
   <td> <p>El contenido de texto de la notificación push que se envía a los dispositivos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> title </td> 
   <td> <p>(Opcional) Título del mensaje. Si no se introduce ningún valor, se utiliza el nombre de la aplicación. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Asigne el cuerpo del JSON mediante el módulo JSON > Crear JSON

El módulo Crear JSON facilita la especificación de JSON. También le ofrece la posibilidad de definir valores de forma dinámica.

Para obtener más información sobre los módulos JSON, consulte [módulos JSON](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/json-modules.md).

1. Introduzca o asigne los valores desde los que desea crear un JSON.

   ![Valores JSON](/help/workfront-fusion/create-scenarios/connect-to-apps/assets/json-values-350x288.png)

1. Conecte el módulo JSON > Crear JSON al módulo HTTP > Crear una solicitud.
1. Asigne la cadena JSON del módulo Crear JSON al campo Solicitar contenido en el módulo HTTP > Crear una solicitud.

Cuando se ejecuta este escenario, la notificación push se envía al dispositivo que se ha registrado en la cuenta de Pushover.
