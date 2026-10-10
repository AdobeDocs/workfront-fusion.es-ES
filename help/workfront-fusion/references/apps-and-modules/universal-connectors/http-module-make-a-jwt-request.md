---
title: HTTP > Crear un módulo de solicitud JWT
description: El módulo de petición HTTP > Make a JWT de Adobe Workfront Fusion envía una petición HTTP(S) a una URL y la autoriza con un token web JSON que Fusion firma automáticamente.
author: Becky
feature: Workfront Fusion
exl-id: 2f8c0b0d-085a-4b49-b350-4fd4cca1d0a7
TQID: 'https://experienceleague.adobe.com/es'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 5e6403abee4e5767da9134529b9e88070bad5f44
workflow-type: tm+mt
source-wordcount: '1437'
ht-degree: 21%
---
# [!UICONTROL HTTP] > [!UICONTROL Realizar una solicitud JWT] módulo

El módulo Adobe Workfront Fusion [!UICONTROL HTTP] > [!UICONTROL Realizar una solicitud JWT] envía una solicitud HTTP(S) a una dirección URL y la autoriza con un token web JSON (JWT) que el módulo firma por usted en cada llamada. La respuesta se procesará del mismo modo que en el módulo estándar [!UICONTROL HTTP] > [!UICONTROL Realizar una solicitud].

Este módulo se comporta como el módulo estándar [!UICONTROL Realizar una solicitud], con una diferencia principal: firma automáticamente un JWT de las notificaciones que proporcione y lo agrega a la solicitud, de forma predeterminada como `Authorization: Bearer <token>`.

Utilice este módulo para llamar a cualquier API que espere un JWT firmado para la autenticación, como servicios que requieran un token de portador de corta duración firmado con un secreto compartido (HMAC) o una clave privada (RSA/ECDSA), sin crear el token en un paso independiente.

Si la API utiliza OAuth 2.0, autenticación básica, una clave de API o un certificado de cliente, utilice el módulo HTTP dedicado correspondiente en su lugar.

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
   <td role="rowheader">Paquete de Adobe Workfront</td> 
   <td> <p>Cualquier paquete del flujo de trabajo de Adobe Workfront y cualquier paquete de integración y automatización de Adobe Workfront</p><p>Workfront Ultimate</p><p>Paquetes Workfront Prime y Select, con una compra adicional de Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencias de Adobe Workfront</td> 
   <td> <p>Estándar</p><p>Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion</td> 
   <td>
   <p>Basado en operaciones: disponible para organizaciones con licencias basadas en operaciones</p>
   <p>Basado en conector (heredado): Workfront Fusion for Work Automation and Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Creación de una conexión JWT

El módulo requiere una conexión JWT. La conexión almacena el material de firma para que la clave secreta o privada no tenga que aparecer en el escenario.

### Creación de una conexión JWT en Fusion

1. Agregue el módulo [!UICONTROL HTTP] > [!UICONTROL Realizar una solicitud JWT] a su escenario.
1. Haga clic en **[!UICONTROL Añadir]** junto al campo **[!UICONTROL conexión]**.
1. Configure los campos de conexión:

   <table style="table-layout:auto">
    <col>
    <col>
    <tbody>
     <tr>
      <td role="rowheader"><p>Nombre de la conexión</p></td>
      <td><p>Introduzca un nombre para la conexión.</p></td>
     </tr>
     <tr>
      <td role="rowheader"><p>Algoritmo</p></td>
      <td>
       <p>Seleccione el algoritmo de firma para la conexión.</p>
       <ul>
        <li><code>HS256</code></li>
        <li><code>HS384</code></li>
        <li><code>HS512</code></li>
        <li><code>RS256</code></li>
        <li><code>RS384</code></li>
        <li><code>RS512</code></li>
        <li><code>PS256</code></li>
        <li><code>PS384</code></li>
        <li><code>PS512</code></li>
        <li><code>ES256</code></li>
        <li><code>ES384</code></li>
        <li><code>ES512</code></li>
       </ul>
      </td>
     </tr>
     <tr>
      <td role="rowheader"><p>Secreto</p></td>
      <td>
       <p>Introduzca la clave de firma.</p>
       <ul>
        <li>Para algoritmos de <code>HS*</code>, use la cadena secreta compartida.</li>
        <li>Para los algoritmos <code>RS*</code>, <code>PS*</code> y <code>ES*</code>, use la clave privada con codificación PEM.</li>
       </ul>
      </td>
     </tr>
    </tbody>
   </table>

1. Haga clic en **[!UICONTROL Continue]** para crear la conexión y volver al módulo.

>[!IMPORTANT]
>
>Una conexión JWT firma con un solo algoritmo. Si su escenario requiere más de un algoritmo de firma, cree una conexión independiente para cada algoritmo. Esto coincide con el comportamiento de la aplicación JWT independiente existente.

## [!UICONTROL HTTP] > [!UICONTROL Realizar una solicitud JWT] módulo y sus campos

Al configurar el módulo [!UICONTROL HTTP] > [!UICONTROL Realizar una solicitud JWT], Adobe Workfront Fusion muestra los campos que se indican a continuación en el mismo orden en que aparecen en la interfaz de usuario del módulo. El título en negrita en un módulo indica un campo obligatorio. Los campos marcados como avanzados están ocultos a menos que seleccione **[!UICONTROL Mostrar configuración avanzada]**.

<table style="table-layout:auto">
 <col>
 <col>
 <tbody>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Connection]</p></td>
   <td><p>Seleccione una conexión JWT existente o cree una nueva.</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL URL]</p></td>
   <td><p>Dirección URL de destino de la solicitud.</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Method]</p></td>
   <td><p>Método HTTP como GET, POST, PUT, PATCH o DELETE.</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Headers]</p></td>
   <td><p>Encabezados de solicitud personalizados en formato clave/valor.</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Query String]</p></td>
   <td><p>Parámetros de cadena de consulta en formato clave/valor.</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Body type]</p></td>
   <td><p>Cómo se codifica el cuerpo de la solicitud. Las opciones son Raw, application/x-www-form-urlencoded y multipart/form-data.</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Parse response]</p></td>
   <td><p>Cuando está habilitado, Fusion analiza el cuerpo de la respuesta en función del tipo de contenido de la respuesta.</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL JWT Payload (Reclamaciones)]</p></td>
   <td><p>Pares de clave/valor incluidos como reclamaciones en la carga útil JWT. Las notificaciones reservadas <code>exp</code>, <code>iat</code> y <code>nbf</code> deben ser un NumericDate (varios segundos desde la época de Unix). Los valores de reclamación mantienen su tipo JSON, por lo que los números permanecen como números y los booleanos permanecen como booleanos.</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Timeout] (avanzado)</p></td>
   <td><p>Especifique el tiempo de espera de la solicitud en segundos (1-300). El valor predeterminado es de 40 segundos.</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Recuento de reintentos] (avanzado)</p></td>
   <td><p>Especifique cuántas veces la solicitud debe reintentarse si la solicitud falla debido a un error de reintento.</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Códigos de estado de reintento adicionales] (avanzado)</p></td>
   <td><p>Especifique códigos de estado HTTP adicionales que deban tratarse como reintentos.</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Compartir cookies con otros módulos HTTP] (avanzado)</p></td>
   <td><p>Habilite esta opción para compartir cookies del servidor con todos los módulos HTTP de su escenario.</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Certificado autofirmado] (avanzado)</p></td>
   <td><p>Cargue el certificado si desea utilizar TLS con el certificado autofirmado.</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Rechazar conexiones que utilizan certificados no verificados (autofirmados)] (avanzado)</p></td>
   <td><p>Habilite esta opción para rechazar conexiones que utilicen certificados TLS no verificados.</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Seguir redirección] (avanzado)</p></td>
   <td><p>Habilite esta opción para seguir las redirecciones de URL con respuestas 3xx.</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Deshabilitar la serialización de varias claves de cadena de consulta iguales que matrices] (avanzado)</p></td>
   <td><p>De forma predeterminada, Workfront Fusion gestiona varios valores para la misma clave de parámetro de cadena de consulta de URL que las matrices. Por ejemplo, <code>www.test.com?foo=bar&amp;foo=baz</code> se convertirá en <code>www.test.com?foo[0]=bar&amp;foo[1]=baz</code>. Active esta opción para deshabilitar esta función.</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Solicitar contenido comprimido] (avanzado)</p></td>
   <td><p>Habilite esta opción para solicitar una versión comprimida del sitio web. Añade un encabezado <code>[!UICONTROL Accept-Encoding]</code> para solicitar contenido comprimido.</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Utilizar TLS mutuo] (avanzado)</p></td>
   <td><p>Habilite esta opción para utilizar TLS mutuo en la solicitud HTTP.</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Opciones de firma] (avanzado)</p></td>
   <td><p>Para cada opción de firma que desee agregar a la solicitud, haga clic en <b>Agregar elemento</b> e introduzca el nombre y el valor del parámetro.</p><p>Se han pasado opciones adicionales al firmante de JWT, como <code>expiresIn</code>, <code>issuer</code>, <code>audience</code>, <code>subject</code> y <code>keyid</code>. La biblioteca <code>jsonwebtoken</code> interpreta los valores de duración como <code>expiresIn</code>. Un número sin formato se trata como milisegundos, así que use una cadena de unidad como <code>"1h"</code> o <code>"3600s"</code> para ser explícito. El algoritmo se toma de la conexión y no se puede anular aquí.</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Nombre de encabezado] (avanzado)</p></td>
   <td><p>Introduzca o asigne el nombre del encabezado de solicitud que recibe el JWT firmado. Predeterminado: <code>Authorization</code>. El nombre del encabezado no debe contener un punto (<code>.</code>), ya que los nombres de puntos se rechazan y no se pueden ocultar en los registros de solicitudes.</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Tipo de token] (avanzado)</p></td>
   <td><p>Escriba o asigne el esquema de autenticación colocado antes del token, como <code>Bearer</code>. Deje esto en blanco para enviar el token sin procesar sin prefijo.</p></td>
  </tr>
 </tbody>
</table>

## Cómo se crea el token

1. El módulo recopila las notificaciones en el campo [!UICONTROL Carga útil JWT (notificaciones)].
1. Notificaciones reservadas como <code>exp</code>, <code>iat</code>y <code>nbf</code> se convierten en valores NumericDate.
1. El módulo aplica [!UICONTROL Opciones de firma] y firma el token usando el algoritmo de la conexión.
1. El token firmado se coloca en el encabezado de solicitud definido por [!UICONTROL Nombre de encabezado].
1. Si se establece [!UICONTROL Token Type], el módulo agrega el prefijo antes del token. Por ejemplo, <code>clave de portador...</code>.
1. La solicitud se envía y la respuesta se procesa del mismo modo que el módulo estándar [!UICONTROL HTTP] > [!UICONTROL Realizar una solicitud].

El token firmado se enmascara automáticamente en los registros de depuración y error para que nunca se exponga.

## Ejemplo

### Conexión

- Algoritmo: `HS256`
- Secreto: `my-shared-secret`

### Configuración del módulo

- URL: `https://api.example.com/v1/orders`
- Método: `GET`
- Carga útil JWT (reclamaciones):
  - `sub` = `service-account-42`
  - `iss` = `make-integration`
- Opciones de firma:
  - `expiresIn` = `1h`
- Nombre de encabezado: `Authorization`
- Tipo de token: `Bearer`

### Resultado

El módulo envía la solicitud con un encabezado similar al siguiente:

```text
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
```

## Preguntas frecuentes / gotchas

### ¿Por qué caducó mi token tan rápido?

Es probable que haya especificado un número sin formato para `expiresIn`, como `3600`. La biblioteca `jsonwebtoken` interpreta los números simples como milisegundos. En su lugar, use una cadena de unidad como `"1h"` o `"3600s"`.

### ¿Cuándo se crea el token?

El módulo firma un JWT nuevo cada vez que se ejecuta el módulo, no cuando crea la conexión. La conexión almacena únicamente el material de firma y el algoritmo, por lo que notificaciones como `iat` y `exp` reflejan el momento en que se ejecuta ese módulo.

Si la solicitud se reintenta dentro de la misma ejecución de módulo, Fusion volverá a utilizar el mismo token firmado para esos intentos de reintento en lugar de firmar un nuevo token para cada intento. Debido a esto, un valor `expiresIn` muy corto puede caducar antes de que se produzca un reintento y hacer que este envíe un token que ya ha caducado. Para evitarlo, use una cadena de unidad transparente como `"1h"` o `"3600s"` y evite duraciones de tokens demasiado cortas.

### ¿Puedo cambiar el algoritmo por solicitud?

No. La conexión corrige el algoritmo. Si necesita un algoritmo diferente, cree una conexión JWT diferente.

### ¿Puedo enviar el token en un encabezado personalizado?

Sí. Establezca el campo [!UICONTROL Nombre de encabezado] en un nombre personalizado, pero no puede contener un punto (`.`).

### ¿Puedo enviar el token sin procesar sin `Bearer`?

Sí. Deje [!UICONTROL Tipo de token] vacío.

### ¿El token es visible en los registros?

No. El token firmado se enmascara automáticamente en los registros de depuración y error.


>[!NOTE]
>
>Nota técnica: la firma utiliza la biblioteca `jsonwebtoken` y refleja el comportamiento de firma de la aplicación JWT independiente, de modo que las mismas entradas producen el mismo token que la aplicación JWT independiente.
