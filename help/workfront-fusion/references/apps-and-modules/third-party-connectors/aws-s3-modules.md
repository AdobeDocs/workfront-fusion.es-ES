---
title: Módulos de AWS S3
description: Los módulos S3 de  [!DNL Adobe Workfront Fusion AWS]  le permiten realizar operaciones en sus bloques de S3.
author: Becky
feature: Workfront Fusion
exl-id: 6b2d9dd5-0b33-4297-aea0-aba26072b26a
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 79%

---

# Módulos de AWS S3

Los módulos S3 de [!DNL Adobe Workfront Fusion AWS] le permiten realizar operaciones en los bloques de S3.

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

Para saber qué plan, tipo de licencia o acceso tiene, póngase en contacto con el administrador de [!DNL Workfront].

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## Requisitos previos

Para usar módulos de [!UICONTROL AWS S3], debe disponer de una cuenta de [!DNL Amazon Web Service].

## Información de la API de AWS S3

El conector AWS S3 utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL básica</td> 
   <td>https://s3.{{parameters.region}}.amazonaws.com</td> 
  </tr>
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.5.21</td> 
  </tr>
 </tbody> 
 </table>

## Conectar [!DNL AWS] a [!DNL Workfront Fusion] {#connect-aws-to-workfront-fusion}

Para conectar [!DNL AWS S3] a [!DNL Workfront Fusion] debe conectar su cuenta de [!DNL AWS] a [!DNL Workfront Fusion]. Para ello, primero deberá crear un usuario de API en [!DNL AWS] [!UICONTROL IAM].

1. Inicie sesión en su cuenta de [!DNL AWS] [!UICONTROL IAM].
1. Vaya a **[!UICONTROL Identity and Access Management]** > **[!UICONTROL Access Management]** > **[!UICONTROL Users]**.

1. Haga clic en **[!UICONTROL Add User]**.
1. Escriba el nombre del nuevo usuario y seleccione la opción **[!UICONTROL Programmatic access]** en la sección [!UICONTROL Access type].
1. Haga clic en **[!UICONTROL Attach existing policies directly]** y luego busque **[!UICONTROL AmazonS3FullAccess]** en la barra de búsqueda. Haga clic en él cuando aparezca y luego haga clic en **[!UICONTROL Next]**.

1. Continúe con las otras pantallas de diálogo y luego haga clic en **[!UICONTROL Create User]**.
1. Copie los **[!UICONTROL Access key ID]** y **[!UICONTROL Secret access key]** proporcionados.

1. Vaya a [!DNL Workfront Fusion] y abra el diálogo **[!UICONTROL Create a connection]** del módulo [!DNL AWS S3].
1. Introduzca [!UICONTROL Access key ID] y [!UICONTROL Secret access key] del paso 7 a los campos respectivos y haga clic en **[!UICONTROL Continue]** para establecer la conexión.

Se ha establecido la conexión. Puede continuar con la configuración del módulo.

## [!DNL AWS S3] módulos y sus campos

Al configurar módulos de [!DNL AWS S3], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL AWS S3] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Acciones](#actions)
* [Búsquedas](#searches)

### Acciones

* [[!UICONTROL Create Bucket]](#create-bucket)
* [[!UICONTROL Get File]](#get-file)
* [[!UICONTROL Upload File]](#upload-file)
* [[!UICONTROL Make an API Call]](#make-an-api-call)

#### [!UICONTROL Create Bucket]

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL AWS] a [!DNL Workfront Fusion], consulte <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">Conectar [!DNL AWS] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>Introduzca el nombre del cubo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>Seleccione el punto final regional. Para obtener más información, consulte la descripción de <a href="https://docs.aws.amazon.com/general/latest/gr/rande.html?lang?=es">puntos finales regionales</a> en la documentación de AWS.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get File]

Descargue un archivo de un cubo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL AWS] a [!DNL Workfront Fusion], consulte <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">Conectar [!DNL AWS] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>Seleccione el punto final regional. Para obtener más información, consulte la explicación sobre <a href="https://docs.aws.amazon.com/general/latest/gr/rande.html?lang?=es">Puntos finales regionales</a> en la documentación de [!DNL AWS].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bucket] </td> 
   <td> <p>Seleccione el cubo desde el que desee descargar el archivo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Path]</p> </td> 
   <td> <p>Introduzca la ruta al archivo. Ejemplo: <code>/photos/2019/February/image023.jpg</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload File]

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL AWS] a [!DNL Workfront Fusion], consulte <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">Conectar [!DNL AWS] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>Seleccione el punto final regional. Para obtener más información, consulte la explicación sobre <a href="https://docs.aws.amazon.com/general/latest/gr/rande.html?lang?=es">Puntos finales regionales</a> en la documentación de [!DNL AWS].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Folder] (opcional) </p> </td> 
   <td> <p>Especifique la carpeta de destino en la que desea cargar un archivo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Headers] (opcional)</p> </td> 
   <td> <p> Insertar encabezados de solicitud. Los encabezados disponibles se encuentran en la documentación de <a href="https://docs.aws.amazon.com/AmazonS3/latest/API/API_PutObject.html?lang=es">[!DNL AWS S3]: [!UICONTROL PUT] objeto</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Make an API Call]

Para obtener un análisis detallado de la API [!DNL Amazon S3], consulte [[!DNL Amazon S3] [!UICONTROL REST] Introducción a la API ](https://docs.aws.amazon.com/AmazonS3/latest/API/Welcome.html).

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL AWS] a [!DNL Workfront Fusion], consulte <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">Conectar [!DNL AWS] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Region] </td> 
   <td> <p>Seleccione el punto final regional. Para obtener más información, consulte la explicación sobre <a href="https://docs.aws.amazon.com/general/latest/gr/rande.html?lang?=es">Puntos finales regionales</a> en la documentación de [!DNL AWS].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL URL]</td> 
   <td> <p>Introduzca una URL de host. La ruta debe ser relativa a <code> https://s3.&lt;selected-region>.amazonaws.com/</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de solicitud [!UICONTROL HTTP] que necesita para configurar la llamada de API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">[!UICONTROL HTTP] métodos de solicitud en [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Headers]</td> 
   <td> <p>Añada un encabezado de solicitud. Puede utilizar los siguientes encabezados de solicitud comunes. Para obtener más encabezados de solicitud, consulte la documentación de la API de <a href="https://docs.aws.amazon.com/AmazonS3/latest/API/RESTCommonRequestHeaders.html?lang=es">[!DNL AWS S3]</a>.</p> <p>[!DNL Workfront Fusion] añade encabezados de autorización automáticamente.</p> 
    <table style="table-layout:auto">
     <col> 
     <col> 
     <thead> 
      <tr> 
       <th>Nombre del encabezado</th> 
       <th> <p> Descripción</p> </th> 
      </tr> 
     </thead> 
     <tbody> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Content-Length]</p> </td> 
       <td> <p>Longitud del mensaje (sin encabezados) según RFC 2616. Este encabezado es necesario para [!UICONTROL PUT] y las operaciones que cargan XML, como el registro y las ACL.</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Content-Type]</p> </td> 
       <td> <p>El tipo de contenido del recurso, en caso de que el contenido de la solicitud esté en el cuerpo. Ejemplo: <code>text/plain</code>.</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Content-MD5]</p> </td> 
       <td> <p>Resumen MD5 de 128 bits codificado en base64 del mensaje (sin los encabezados) según RFC 1864. Este encabezado se puede utilizar como comprobación de integridad de mensajes para comprobar que los datos son los mismos que se enviaron originalmente. Aunque es opcional, se recomienda utilizar el mecanismo [!UICONTROL Content-MD5] como una comprobación de integridad de extremo a extremo. Para obtener más información acerca de la autenticación de solicitudes de [!UICONTROL REST], vaya a <a href="https://docs.aws.amazon.com/AmazonS3/latest/dev/RESTAuthentication.html?r=1821">[!UICONTROL REST] Authentication</a> en <i>[!DNL Amazon] Simple Storage Service Developer Guide</i>.</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Date]</p> </td> 
       <td> <p>La fecha y hora actuales según el solicitante. Ejemplo: <code>Wed, 01 Mar 2006 12:00:00 GMT</code>.  Cuando especifique el encabezado <code>Authorization </code>, debe especificar el encabezado <code>x-amz-date</code> o <code>Date </code>.</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Expect]</p> </td> 
       <td> <p>Cuando la aplicación utiliza [!UICONTROL 100-continue], no envía el cuerpo de la solicitud hasta que recibe una confirmación. Si el mensaje se rechaza en función de los encabezados, no se envía el cuerpo del mensaje. Este encabezado solo se puede utilizar si envía un cuerpo.</p> <p>Valores válidos: [!UICONTROL 100-continue]</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Host]</p> </td> 
       <td> <p>Para solicitudes path-style, el valor es <code>s3.amazonaws.com</code>. Para solicitudes de estilo virtual, el valor es <code>BucketName.s3.amazonaws.com</code>. Para obtener más información, consulte <a href="https://docs.aws.amazon.com/AmazonS3/latest/dev/VirtualHosting.html?lang=es">Virtual Hosting</a> en la publicación <i>[!DNL Amazon] Simple Storage Service Developer Guide</i>.</p> <p>Este encabezado es necesario para HTTP 1.1 (la mayoría de los kits de herramientas lo añaden automáticamente); opcional para las solicitudes HTTP/1.0.</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL x-amz-content-sha256]</p> </td> 
       <td> <p>Cuando se utiliza la versión de firma 4 para autenticar la solicitud, este encabezado proporciona un hash de la carga útil de la solicitud. Al cargar un objeto en fragmentos, establezca el valor en <code>STREAMING-AWS4-HMAC-SHA256-PAYLOAD</code> para indicar que la firma cubre solo los encabezados y que no hay carga útil. Para obtener más información, consulte <a href="https://docs.aws.amazon.com/AmazonS3/latest/API/sigv4-streaming.html?lang=es">Cálculos de firma para el encabezado de autorización: transferencia de la carga útil en varios fragmentos (carga interrumpida) ([!DNL AWS] versión de firma 4)</a>.</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL x-amz-date]</p> </td> 
       <td> <p>La fecha y hora actuales según el solicitante. Ejemplo: <code>Wed, 01 Mar 2006 12:00:00 GMT</code>.  Cuando especifique el encabezado <code>Authorization </code>, debe especificar el encabezado <code>x-amz-date</code> o <code>Date </code>. Si especifica ambos, el valor especificado del encabezado <code>x-amz-date</code> tiene prioridad.</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL x-amz-security-token]</p> </td> 
       <td> <p>Este encabezado se puede utilizar en los siguientes casos:</p> 
        <ul> 
         <li>Debe proporcionar tokens de seguridad para las operaciones de [!DNL Amazon DevPay]. Cada solicitud que usa [!DNL Amazon DevPay] requiere dos encabezados <code>x-amz-security-token</code>: uno para el token de producto y otro para el token de usuario. Cuando [!DNL Amazon S3] recibe una solicitud autenticada, compara la firma calculada con la firma proporcionada. El uso de encabezados de varios valores con un formato incorrecto para calcular una firma puede causar problemas de autenticación.</li> 
         <li>Debe proporcionar un token de seguridad cuando utilice credenciales de seguridad temporales. Al realizar solicitudes con credenciales de seguridad temporales obtenidas de IAM, debe proporcionar un token de seguridad mediante este encabezado. Para obtener más información sobre las credenciales de seguridad temporales, vaya a Creación de solicitudes.</li> 
        </ul> <p>Este encabezado es necesario para las solicitudes que usan [!DNL Amazon DevPay] y las solicitudes que se firman con credenciales de seguridad temporales.</p> </td> 
      </tr> 
     </tbody> 
    </table> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query String]</td> 
   <td> <p>Añada las cadenas de consulta deseadas, como parámetros o campos de formulario.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:   <p>Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la instrucción condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>">  
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Búsquedas

* [[!UICONTROL List Files]](#list-files)
* [[!UICONTROL List Folders]](#list-folders)

#### [!UICONTROL List Files]

Devuelve una lista de archivos de una ubicación especificada.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL AWS] a [!DNL Workfront Fusion], consulte <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">Conectar [!DNL AWS] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>Seleccione el punto final regional. Para obtener más información, consulte la explicación sobre <a href="https://docs.aws.amazon.com/general/latest/gr/rande.html?lang?=es">Puntos finales regionales</a> en la documentación de [!DNL AWS].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bucket] </td> 
   <td> <p>Seleccione el grupo [!DNL Amazon S3] en el que desea buscar archivos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Prefix] (opcional)</p> </td> 
   <td> <p> Ruta a una carpeta en la que se buscan archivos, por ejemplo, <code>workfrontfusion/work.</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Folders]

Devuelve una lista de carpetas desde una ubicación especificada.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL AWS] a [!DNL Workfront Fusion], consulte <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">Conectar [!DNL AWS] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>Seleccione el punto final regional. Para obtener más información, consulte la descripción de <a href="https://docs.aws.amazon.com/general/latest/gr/rande.html?lang?=es">puntos finales regionales</a> en la documentación de AWS.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bucket] </td> 
   <td> <p>Seleccione el cubo de [!DNL Amazon S3] en el que desea buscar carpetas.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Prefix] (opcional)</p> </td> 
   <td> <p> Ruta a una carpeta en la que se buscan carpetas, por ejemplo, <code>workfrontfusion/work.</code></p> </td> 
  </tr> 
 </tbody> 
</table>
