---
title: Módulos de AWS S3
description: Los módulos S3 de  [!DNL Adobe Workfront Fusion AWS]  le permiten realizar operaciones en sus bloques de S3.
author: Becky
feature: Workfront Fusion
exl-id: 6b2d9dd5-0b33-4297-aea0-aba26072b26a
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '1468'
ht-degree: 67%

---

# Módulos de AWS S3

Los módulos S3 de [!DNL Adobe Workfront Fusion AWS] le permiten realizar operaciones en los bloques de S3.

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

Para usar los módulos [!UICONTROL AWS S3] debe tener una cuenta de [!DNL Amazon Web Service].

## Información de la API de AWS S3

El conector AWS S3 utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Dirección URL base</td> 
   <td>https://s3.{{parameters.region}}.amazonaws.com</td> 
  </tr>
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.5.21</td> 
  </tr>
 </tbody> 
 </table>

## Conexión de [!DNL AWS] a Workfront Fusion {#connect-aws-to-workfront-fusion}

Para conectar a [!DNL AWS S3] a Workfront Fusion, debe conectar su cuenta de [!DNL AWS] a Workfront Fusion. Para hacerlo, primero necesitará crear un usuario de API en [!DNL AWS] [!UICONTROL IAM].

1. Inicie sesión en su cuenta de [!DNL AWS] [!UICONTROL IAM].
1. Navegue a **[!UICONTROL Gestión de Identidad y Accesos]** > **[!UICONTROL Gestión de Accesos]** > **[!UICONTROL Usuarios]**.

1. Haga clic en **[!UICONTROL Agregar usuario]**.
1. Introduce el nombre del nuevo usuario y selecciona la opción **[!UICONTROL Acceso programático]** en la sección [!UICONTROL Tipo de acceso].
1. Haga clic en **[!UICONTROL Vincular políticas existentes directamente]**, luego busque **[!UICONTROL AmazonS3FullAccess]** en la barra de búsqueda. Haga clic en él cuando aparezca y luego haga clic en **[!UICONTROL Siguiente]**.

1. Continúe con las otras pantallas de diálogo y luego haga clic en **[!UICONTROL Crear usuario]**.
1. Copie el **[!UICONTROL ID de clave de acceso]** y la **[!UICONTROL Clave de acceso secreta]** proporcionados.

1. Vaya a Workfront Fusion y abra el diálogo [!DNL AWS S3]Crear una conexión **[!UICONTROL del módulo]**.
1. Introduzca el [!UICONTROL ID de clave de acceso] y la [!UICONTROL Clave de acceso secreta] del paso 7 en los campos correspondientes y haga clic en **[!UICONTROL Continuar]** para establecer la conexión.

Se ha establecido la conexión. Puede continuar con la configuración del módulo.

## [!DNL AWS S3] módulos y sus campos

Al configurar módulos de [!DNL AWS S3], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL AWS S3] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Acciones](#actions)
* [Búsquedas](#searches)

### Acciones

* [[!UICONTROL Crear cubo]](#create-bucket)
* [[!UICONTROL Obtener archivo]](#get-file)
* [[!UICONTROL Realización de una llamada de API]](#make-an-api-call)
* [[!UICONTROL Cargar archivo]](#upload-file)

#### [!UICONTROL Crear cubo]

Este módulo de acción crea un bloque en AWS.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL AWS] a Workfront Fusion, consulte <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">Conectar [!DNL AWS] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>Introduzca el nombre del cubo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>Seleccione el punto final regional. Para obtener más información, consulte <a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">extremos regionales</a> en la documentación de AWS.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Obtener archivo]

Este módulo de acción descarga un archivo desde un bloque.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL AWS] a Workfront Fusion, consulte <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">Conectar [!DNL AWS] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>Seleccione el punto final regional. Para obtener más información, vea <a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">extremos regionales</a> en la documentación de [!DNL AWS].</p> </td> 
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

#### [!UICONTROL Realización de una llamada de API]

Este módulo de acción realiza una llamada personalizada a la API de AWS S3.

Para obtener una explicación sobre la API de [!DNL Amazon S3], consulte Introducción a la API REST de [[!DNL Amazon S3] ](https://docs.aws.amazon.com/AmazonS3/latest/API/Welcome.html).

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL AWS] a Workfront Fusion, consulte <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">Conectar [!DNL AWS] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Region] </td> 
   <td> <p>Seleccione el punto final regional. Para obtener más información, vea <a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">extremos regionales</a> en la documentación de [!DNL AWS].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL URL]</td> 
   <td> <p>Introduzca una URL de host. La ruta debe ser relativa a <code> https://s3.&lt;selected-region>.amazonaws.com/</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de petición [!UICONTROL HTTP] que necesita para configurar la llamada de API. Para obtener más información, consulte <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">[!UICONTROL HTTP] métodos de solicitud en Adobe Workfront Fusion</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Headers]</td> 
   <td> <p>Añada un encabezado de solicitud. Para cada encabezado que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca el encabezado. Puede utilizar los siguientes encabezados de solicitud comunes. Para obtener más encabezados de solicitud, consulte la documentación de la API de <a href="https://docs.aws.amazon.com/AmazonS3/latest/API/RESTCommonRequestHeaders.html?lang=es">[!DNL AWS S3]</a>.</p> <p>Workfront Fusion añade encabezados de autorización automáticamente.</p> 
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
       <td> <p>Resumen MD5 de 128 bits codificado en base64 del mensaje (sin los encabezados) según RFC 1864. Este encabezado se puede utilizar como comprobación de integridad de mensajes para comprobar que los datos son los mismos que se enviaron originalmente. Aunque es opcional, se recomienda utilizar el mecanismo [!UICONTROL Content-MD5] como comprobación de integridad de extremo a extremo. Para obtener más información acerca de la autenticación de solicitudes de [!UICONTROL REST], consulte <a href="https://docs.aws.amazon.com/AmazonS3/latest/dev/RESTAuthentication.html?r=1821">Firma y autenticación de solicitudes REST</a> en la documentación de AWS.</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Date]</p> </td> 
       <td> <p>La fecha y hora actuales según el solicitante. Ejemplo: <code>Wed, 01 Mar 2006 12:00:00 GMT</code>.  Cuando especifique el encabezado <code>Authorization </code>, debe especificar el encabezado <code>x-amz-date</code> o <code>Date </code>.</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Expect]</p> </td> 
       <td> <p>Cuando la aplicación utiliza [!UICONTROL 100-continue], no envía el cuerpo de la solicitud hasta que reciba una confirmación. Si el mensaje se rechaza en función de los encabezados, no se envía el cuerpo del mensaje. Este encabezado solo se puede utilizar si envía un cuerpo.</p> <p>Valores válidos: [!UICONTROL 100-continue]</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Host]</p> </td> 
       <td> <p>Para solicitudes path-style, el valor es <code>s3.amazonaws.com</code>. Para solicitudes de estilo virtual, el valor es <code>BucketName.s3.amazonaws.com</code>. Para obtener más información, consulte <a href="https://docs.aws.amazon.com/AmazonS3/latest/dev/VirtualHosting.html?lang=es">Alojamiento virtual</a> en la documentación de AWS.</p> <p>Este encabezado es necesario para HTTP 1.1 (la mayoría de los kits de herramientas lo añaden automáticamente); opcional para las solicitudes HTTP/1.0.</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL x-amz-content-sha256]</p> </td> 
       <td> <p>Cuando se utiliza la versión de firma 4 para autenticar la solicitud, este encabezado proporciona un hash de la carga útil de la solicitud. Al cargar un objeto en fragmentos, establezca el valor en <code>STREAMING-AWS4-HMAC-SHA256-PAYLOAD</code> para indicar que la firma cubre solo los encabezados y que no hay carga útil. Para obtener más información, consulte <a href="https://docs.aws.amazon.com/AmazonS3/latest/API/sigv4-streaming.html?lang=es">Cálculos de firma para el encabezado de autorización</a> en la documentación de AWS.</p> </td> 
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
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:   <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>">  
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Cargar archivo]

Este módulo de acción carga un archivo en un contenedor de AWS S3.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL AWS] a Workfront Fusion, consulte <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">Conectar [!DNL AWS] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>Seleccione el punto final regional. Para obtener más información, vea <a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">extremos regionales</a> en la documentación de [!DNL AWS].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Folder] </p> </td> 
   <td> <p>Especifique la carpeta de destino en la que desea cargar un archivo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Headers] (opcional)</p> </td> 
   <td> <p> Para cada encabezado que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca la clave y el valor del encabezado.</p><p> Para ver los encabezados disponibles, consulte <a href="https://docs.aws.amazon.com/AmazonS3/latest/API/API_PutObject.html?lang=es">PutObject</a> en la documentación de AWS.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Búsquedas

* [[!UICONTROL Listar archivos]](#list-files)
* [[!UICONTROL Listar carpetas]](#list-folders)

#### [!UICONTROL Listar archivos]

Devuelve una lista de archivos de una ubicación especificada.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL AWS] a Workfront Fusion, consulte <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">Conectar [!DNL AWS] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>Seleccione el punto final regional. Para obtener más información, vea <a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">extremos regionales</a> en la documentación de [!DNL AWS].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bucket] </td> 
   <td> <p>Seleccione el grupo [!DNL Amazon S3] en el que desea buscar archivos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Prefijo]</p> </td> 
   <td> <p> Introduzca una ruta a una carpeta en la que buscar archivos, como <code>workfrontfusion/work.</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Listar carpetas]

Devuelve una lista de carpetas desde una ubicación especificada.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL AWS] a Workfront Fusion, consulte <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">Conectar [!DNL AWS] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>Seleccione el punto final regional. Para obtener más información, vea <a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">extremos regionales</a> en la documentación de [!DNL AWS].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bucket] </td> 
   <td> <p>Seleccione el cubo de [!DNL Amazon S3] en el que desea buscar carpetas.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Prefix] (opcional)</p> </td> 
   <td> <p> Ruta a una carpeta en la que buscar carpetas, como <code>workfrontfusion/work.</code></p> </td> 
  </tr> 
 </tbody> 
</table>
