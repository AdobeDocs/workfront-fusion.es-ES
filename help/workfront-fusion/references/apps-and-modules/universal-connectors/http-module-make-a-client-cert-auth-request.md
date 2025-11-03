---
title: HTTP > Crear un módulo de solicitud de autorización de certificados de cliente
description: Este módulo de Adobe Workfront Fusion le permite configurar una solicitud HTTP con autorización de certificado de cliente HTTP y enviarla a un servidor. La respuesta HTTP recibida se incluye entonces en el paquete de salida.
author: Becky
feature: Workfront Fusion
exl-id: cc33530c-3010-4955-8819-5eb8373a0e10
source-git-commit: 54c368d335b30f55cab19595a5b4740dde6013a7
workflow-type: tm+mt
source-wordcount: '1069'
ht-degree: 71%

---

# HTTP > [!UICONTROL Realizar una solicitud de autorización de certificado de cliente] módulo

>[!NOTE]
>
>Adobe Workfront Fusion requiere una licencia Adobe Workfront Fusion y de Adobe Workfront.

Este módulo de Adobe Workfront Fusion le permite configurar una solicitud HTTP con autorización de certificado de cliente HTTP y enviarla a un servidor. La respuesta HTTP recibida se incluye entonces en el paquete de salida.

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

## [!UICONTROL HTTP] > [!UICONTROL Realizar una solicitud de autorización de certificado de cliente] configuración del módulo

Al configurar el módulo [!UICONTROL HTTP] > [!UICONTROL Realizar una solicitud de autorización de certificado de cliente], Adobe Workfront Fusion muestra los campos que se indican a continuación. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, consulte [Asignar información de un módulo a otro en Adobe Workfront Fusion](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Credentials]</td> 
   <td> <p>Seleccione la clave que contiene las credenciales de autenticación de certificado de cliente o haga clic en <strong>[!UICONTROL Add]</strong> para añadir las credenciales a una clave nueva. </p> <p>Nota: Se pueden añadir más credenciales para cambiar fácilmente entre cada conexión.</p>           <p>Para extraer la clave privada o el certificado:</p>
          <ol>
            <li value="1">
              <p>Haga clic en <b>[!UICONTROL Extract]</b>.</p>
            </li>
            <li value="2">
              <p>Seleccione el tipo de archivo que va a extraer.</p>
            </li>
            <li value="3">
              <p>Seleccione el archivo que contiene la clave privada o el certificado.</p>
            </li>
            <li value="4">
              <p>Introduzca la contraseña del archivo.</p>
            </li>
            <li value="5">
              <p>Haga clic en <b>[!UICONTROL Save]</b> para extraer el archivo y volver a la configuración de conexión.</p>
            </li>
</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Evaluate all states as errors (except for 2xx and 3xx )] </td> 
   <td> <p>Utilice esta opción para configurar la gestión de errores.</p> <p>Para obtener más información, consulte <a href="/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md" class="MCXref xref">Control de errores en Adobe Workfront Fusion</a>.</p> </td> 
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
     <li> <p><strong>[!UICONTROL Raw]</strong> </p> <p>El tipo de cuerpo Raw es generalmente adecuado para la mayoría de las solicitudes de cuerpo HTTP, incluso en situaciones donde la documentación para desarrolladores no especifica los datos a enviar.</p> <p>Especifique una forma de analizar los datos en el campo [!UICONTROL Content type].</p> <p>A pesar del tipo de contenido seleccionado, el módulo introduce los datos en cualquier formato estipulado o requerido por la documentación del desarrollador.</p> </li> 
     <li> <p><strong>[!UICONTROL Application/x-www-form-urlencoded]</strong> </p> <p>Este tipo de cuerpo es para [!UICONTROL POST] datos que usan <code>application/x-www-form-urlencoded</code>.</p> <p>Para <code>[!UICONTROL application/x-www-form-urlencoded]</code>, el cuerpo del mensaje HTTP enviado al servidor es esencialmente una cadena de consulta. Las claves y los valores se codifican en pares clave-valor separados por <code>&amp;</code> y con un <code>=</code> entre la clave y el valor. </p> <p>Para los datos binarios, use <code>[!UICONTROL multipart/form-data]</code> en su lugar.</p> <p>Para cada par clave-valor que desee agregar, en el campo Campos, haga clic en <b>Agregar elemento</b> e introduzca la clave y el valor.</p>
      <div class="example" data-mc-autonum="<b>Example: </b>">
       <span class="autonumber"><span><b>Ejemplo:</b></span></span> 
       <p>Ejemplo del formato de petición HTTP resultante:</p> 
       <p><code>field1=value1&amp;field2=value2</code> </p> 
      </div> </li> 
     <li> <p><strong>[!UICONTROL Multipart/form-data]</strong> </p> <p>El [!UICONTROL Multipart/form-data] es una solicitud HTTP multipart utilizada para enviar archivos y datos. Normalmente se utiliza para cargar archivos en el servidor.</p> <p>Añada campos para enviarlos en la solicitud. Cada campo debe contener un par clave-valor.</p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Text]</strong> </p> <p>Introduzca la clave y el valor que se enviarán dentro del cuerpo de la solicitud.</p> </li> 
       <li> <p><strong>[!UICONTROL File]</strong> </p> <p>Introduzca la clave y especifique el archivo de origen que desea enviar en el cuerpo de la solicitud. Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo.</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Parse response]</p> </td> 
   <td> <p>Habilite esta opción para analizar automáticamente las respuestas y convertir las respuestas JSON y XML, de modo que no necesite usar los módulos [!UICONTROL JSON] &gt; [!UICONTROL Parse JSON] o [!UICONTROL XML] &gt; [!UICONTROL Parse XML].</p> <p>Antes de poder usar el contenido JSON o XML analizado, ejecute el módulo manualmente una vez para que el módulo pueda reconocer el contenido de la respuesta y le permita asociarlo en módulos posteriores.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Timeout] </td> 
   <td> <p>Especifique el tiempo de espera de la solicitud en segundos (1-300). El valor predeterminado es de 40 segundos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Share cookies with other HTTP modules]</td> 
   <td> <p> Habilite esta opción para compartir cookies del servidor con todos los módulos HTTP de su escenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Self-signed certificate]</td> 
   <td> <p>Para agregar un certificado autofirmado:</p>
          <ol>
            <li value="1">
              <p>Haga clic en <b>[!UICONTROL Extract]</b>.</p>
            </li>
            <li value="2">
              <p>Seleccione el tipo de archivo que va a extraer.</p>
            </li>
            <li value="3">
              <p>Seleccione el archivo que contiene el certificado o.</p>
            </li>
            <li value="4">
              <p>Introduzca la contraseña del archivo.</p>
            </li>
            <li value="5">
              <p>Haga clic en <b>[!UICONTROL Guardar]</b> para extraer el archivo y volver a la configuración del módulo.</p>
            </li>
          </ol>
</p> </td> 
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
   <td> <p> Habilite esta opción para solicitar una versión comprimida del sitio web.</p> <p>Añade un encabezado <code>[!UICONTROL Accept-Encoding]</code> para solicitar contenido comprimido.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Use Mutual TLS]</td> 
   <td> <p>Habilite esta opción para utilizar TLS mutuo en la solicitud HTTP.</p> <p>Para obtener más información sobre TLS mutuo, consulte <a href="/help/workfront-fusion/references/apps-and-modules/universal-connectors/use-mtls-in-http-modules.md" class="MCXref xref">Usar TLS mutuo en módulos HTTP</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>
