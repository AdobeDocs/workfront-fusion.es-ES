---
title: Módulos de AWS S3
description: Los módulos S3 de [!DNL Adobe Workfront Fusion AWS] le permiten realizar operaciones en los bloques de S3.
author: Becky
feature: Workfront Fusion
exl-id: 6b2d9dd5-0b33-4297-aea0-aba26072b26a
TQID: 'https://experienceleague.adobe.com/FDkre6osF2kT7Kz-5VGradQLa7GPSJ6MHPH9-FgM-ag'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
source-git-commit: 7c25013f7a94000651e8331199ad985d40651ae3
workflow-type: tm+mt
source-wordcount: '2637'
ht-degree: 47%
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
   <p>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

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
   <td role="rowheader">URL base</td> 
   <td><pre><code>https://s3.&#123;&#123;parameters.region&#125;&#125;.amazonaws.com</code></pre></td> 
  </tr>
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.5.21</td> 
  </tr>
 </tbody> 
 </table>

## Conexión de [!DNL AWS] a Workfront Fusion {#connect-aws-to-workfront-fusion}

* [Conexión de AWS a Workfront Fusion mediante una conexión federada](#connect-aws-to-workfront-fusion-using-a-federated-connection)
* [Conexión de AWS a Workfront Fusion con un usuario de API](#connect-aws-to-workfront-fusion-using-an-api-user)

### Conexión de AWS a Workfront Fusion mediante una conexión federada

+++ Expanda para ver las instrucciones de este tipo de conexión.

* [Requisitos previos para conectar AWS a Workfront Fusion mediante una conexión federada](#prerequisites-to-connecting-aws-to-workfront-fusion-using-a-federated-connection)
* [Añadir Workfront Fusion como proveedor de identidad en AWS](#add-workfront-fusion-as-an-identity-provider-in-aws)
* [Creación de la función IAM](#create-the-iam-role)
* [Creación de la conexión en Workfront Fusion](#create-the-connection-in-workfront-fusion)
* [Agregar la conexión a la directiva de confianza de la función](#add-the-connection-to-the-roles-trust-policy)
* [Comprobar la conexión](#verify-the-connection)
* [Resolución de problemas](#troubleshooting)

Una conexión federada permite a Workfront Fusion acceder a su cuenta de AWS sin necesidad de crear un usuario de IAM ni almacenar una clave de acceso en Fusion.
En su lugar, registra Workfront Fusion como proveedor de identidad de confianza en su cuenta de AWS y configura qué conexión de Fusion única puede utilizar una función de IAM determinada. Cuando se ejecuta la conexión, Fusion presenta una prueba de identidad de corta duración y AWS devuelve credenciales temporales que caducan por su cuenta. Nunca se crea, almacena ni gira ninguna clave de larga duración.

>[!NOTE]
>
>La configuración de esta conexión requiere dos visitas a la consola de AWS. Primero cree la función, después cree la conexión en Workfront Fusion y, a continuación, vuelva a AWS para finalizar la directiva de confianza. Esto se debe a que parte de la directiva de confianza identifica una conexión específica y ese identificador no existe hasta que se crea la conexión.

#### Requisitos previos para conectar AWS a Workfront Fusion mediante una conexión federada

Para crear esta conexión, necesita lo siguiente:

* Permiso en AWS IAM para crear un proveedor de identidad y crear y editar funciones. Esto suele significar la política o equivalente. Si no tiene este acceso, pregunte a alguien en su nube o
Equipo de seguridad para completar los pasos de AWS por usted.
* La capacidad de crear conexiones en Workfront Fusion.


#### Añadir Workfront Fusion como proveedor de identidad en AWS

Este paso indica a AWS que se puede confiar en los tokens emitidos por Workfront Fusion. Haga esto una vez por cuenta de AWS. Si alguien de su organización ya agregó este proveedor, vaya a [Crear la función IAM](#create-the-iam-role).

1. Inicie sesión en la consola de AWS y vaya a **IAM** > **Proveedores de identidad**.
1. Seleccione **Agregar proveedor**.
1. Para el tipo de proveedor, seleccione **OpenID Connect**.
1. En la dirección URL del proveedor, escriba lo siguiente y, a continuación, seleccione **Obtener huella digital**:

   ```
   https://oidc.automations.adobe.com
   ```

1. En Audience, introduzca lo siguiente:

   ```
   sts.amazonaws.com
   ```

1. Seleccione **Agregar proveedor**.
1. Continúe con [Crear el rol de IAM](#create-the-iam-role).

#### Creación de la función IAM

La función define lo que la conexión puede hacer en su cuenta de AWS. Puede crear un rol por conexión, de modo que el acceso de cada conexión se pueda conceder y revocar de forma independiente.

1. En IAM, vaya a **Roles** y seleccione **Crear rol**.
1. Para el tipo de entidad de confianza, seleccione **Identidad web**.
1. En Proveedor de identidad, seleccione `oidc.automations.adobe.com`.
1. En Audiencia, seleccione `sts.amazonaws.com`.
1. Seleccione **Siguiente** y, a continuación, adjunte las directivas de permisos que necesita esta conexión.
Conceda únicamente los permisos que realmente utiliza la conexión. Por ejemplo, una conexión que solo lee de
un bloque no necesita `AmazonS3FullAccess`.
1. Asigne un nombre claro y reconocible a la función. Por ejemplo, `WorkfrontFusionFederatedConnection`.
1. Seleccione **Crear rol**.
1. Abra la función que acaba de crear y copie su ARN del área Resumen. Tiene el siguiente aspecto: `arn:aws:iam::123456789012:role/WorkfrontFusionFederatedConnection`

1. Continuar a [Crear la conexión en Workfront Fusion](#create-the-connection-in-workfront-fusion).

#### Creación de la conexión en Workfront Fusion

1. En la pantalla de configuración de la conexión del módulo, seleccione el tipo de conexión federada.
1. Escriba el ARN de la función que copió en [Crear la función IAM](#create-the-iam-role).
1. Seleccione **Crear**.
Workfront Fusion muestra tres valores. Los utiliza en el siguiente procedimiento.

<table>
  <tr>
    <td>Emisor</td>
    <td>Siempre <code>https://oidc.automations.adobe.com</code>. Esto coincide con el proveedor de identidad que agregó en AWS.</td>
  </tr>
  <tr>
    <td>Asunto</td>
    <td>Identifica esta conexión. Se ve como <code>fusion:6e5b1c2a345bd8d1ed98b6b4f1459818:28964</code>. Es diferente para cada conexión que cree.</td>
  </tr>
  <tr>
    <td>Público</td>
    <td>Siempre <code>sts.amazonaws.com</code>.</td>
  </tr>
</table>

1. Deje este panel abierto y copie el valor Asunto.

   >[!NOTE]
   >
   >No cierre el panel ni seleccione Cancelar. La conexión no finaliza hasta que complete los procedimientos restantes. Si cierra el panel, debe eliminar la conexión y volver a iniciarla, ya que una nueva conexión recibe un nuevo Asunto.

1. Continuar a [Agregar la conexión a la directiva de confianza del rol](#add-the-connection-to-the-roles-trust-policy).

#### Agregar la conexión a la directiva de confianza de la función

Hasta que complete este procedimiento, la función confía en Workfront Fusion en general, pero aún no permite que esta conexión específica la utilice.

1. En una nueva pestaña del explorador, vuelva a la consola de AWS y abra la función que ha creado.
1. Seleccione la ficha **Relaciones de confianza** y, a continuación, seleccione **Editar directiva de confianza**.
1. Reemplace la directiva por lo siguiente, reemplazando sus propios valores:

   * Reemplazar `123456789012` con su ID de cuenta de AWS
   * Reemplace el valor `sub` por el asunto que copió de Workfront Fusion.


   ```
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Effect": "Allow", 
         "Principal": {
           "Federated": "arn:aws:iam::123456789012:oidc-provider/oidc.automations.adobe.com"
       },
       "Action": "sts:AssumeRoleWithWebIdentity", "Condition": {
        "StringEquals": {
          "oidc.automations.adobe.com:sub": "fusion:6e5b1c2a345bd8d1ed98b6b4f1459818:28964", 
          "oidc.automations.adobe.com:aud": "sts.amazonaws.com"
        }
       }
      }
    ]
   }
   ```

1. Seleccione **Actualizar directiva**.
1. Continuar a [Verificar la conexión](#verify-the-connection).

>[!TIP]
>
>Para permitir que más de una conexión utilice el mismo rol, enumere los sujetos como una matriz. AWS permite utilizar la función si el token coincide con cualquier valor de la lista:
>
>```
>"oidc.automations.adobe.com:sub": [ "fusion:6e5b1c2a345bd8d1ed98b6b4f1459818:28964", "fusion:6e5b1c2a345bd8d1ed98b6b4f1459818:29011"
>]
>```
>
>No reemplace el subvalor por un comodín. Al hacerlo, cualquier conexión de su organización puede utilizar la función, incluidas las conexiones creadas posteriormente por otras personas


#### Comprobar la conexión

1. Vuelva a la pestaña del explorador de Workfront Fusion, donde el panel de conexión sigue abierto.
1. Haga clic en **Guardar**.

   Workfront Fusion se pone en contacto con AWS, que comprueba la directiva de confianza y devuelve credenciales temporales. Si todo está configurado correctamente, la conexión se valida correctamente y puede continuar con la configuración del módulo.
   Si la verificación falla, el panel permanece abierto y muestra el error. Corrija el problema en AWS y vuelva a seleccionar Guardar. No es necesario volver a crear la conexión y el asunto no cambia.

A partir de este punto, la conexión renueva sus propias credenciales. No hay ninguna clave para girar y no caduca nada que necesite mantener.

#### Resolución de problemas


<table>
  <tr>
    <th>Error</th>
    <th>Lo que significa</th>
    <th>Qué comprobar</th>
  </tr>
  <tr>
    <td>InvalidIdentityToken</td>
    <td>AWS no pudo relacionar el token con un proveedor de identidad registrado.</td>
    <td>Compruebe que ha añadido el proveedor de identidad descrito en Añadir Workfront Fusion como proveedor de identidad en AWS y que su URL es exactamente https://oidc.automations.adobe.com, sin barra diagonal.</td>
  </tr>
  <tr>
    <td>Acceso denegado al asumir la función</td>
    <td>El proveedor de identidad está registrado, pero la directiva de confianza no coincide con esta conexión.</td>
    <td>Compruebe que el subvalor de la política de confianza sea carácter a carácter idéntico al Asunto mostrado en Workfront Fusion y que aud sea sts.amazonaws.com. La causa más común es un asunto copiado de una conexión diferente.</td>
  </tr>
  <tr>
    <td>La conexión funciona y falla más tarde</td>
    <td> </td>
    <td>Compruebe si las directivas de permisos de la función han cambiado o si la función se ha eliminado y vuelto a crear. Volver a crear una función no cambia su ARN, pero restablece su directiva de confianza.</td>
  </tr>
</table>

+++

### Conexión de AWS a Workfront Fusion con un usuario de API

+++ Expanda para ver las instrucciones de este tipo de conexión.

Para conectar a [!DNL AWS S3] a Workfront Fusion, debe conectar su cuenta de [!DNL AWS] a Workfront Fusion. Para hacerlo, primero necesitará crear un usuario de API en [!DNL AWS] [!UICONTROL IAM].

1. Inicie sesión en su cuenta de [!DNL AWS] [!UICONTROL IAM].
1. Navegue a **[!UICONTROL Gestión de Identidad y Accesos]** > **[!UICONTROL Gestión de Accesos]** > **[!UICONTROL Usuarios]**.

1. Haga clic en **[!UICONTROL Agregar usuario]**.
1. Introduce el nombre del nuevo usuario y selecciona la opción **[!UICONTROL Acceso programático]** en la sección [!UICONTROL Tipo de acceso].
1. Haga clic en **[!UICONTROL Vincular políticas existentes directamente]**, luego busque **[!UICONTROL AmazonS3FullAccess]** en la barra de búsqueda. Haga clic en él cuando aparezca y luego haga clic en **[!UICONTROL Siguiente]**.

1. Continúe con las otras pantallas de diálogo y luego haga clic en **[!UICONTROL Crear usuario]**.
1. Copie el **[!UICONTROL ID de clave de acceso]** y la **[!UICONTROL Clave de acceso secreta]** proporcionados.

1. Vaya a Workfront Fusion y abra el diálogo **[!UICONTROL Crear una conexión]** del módulo [!DNL AWS S3].
1. Introduzca el [!UICONTROL ID de clave de acceso] y la [!UICONTROL Clave de acceso secreta] del paso 7 en los campos correspondientes y haga clic en **[!UICONTROL Continuar]** para establecer la conexión.

Se ha establecido la conexión. Puede continuar con la configuración del módulo.

+++

## Módulos de [!DNL AWS S3] y sus campos

* [Acciones](#actions)
* [Búsquedas](#searches)

Al configurar módulos de [!DNL AWS S3], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL AWS S3] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, consulte [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Acciones](#actions)
* [Búsquedas](#searches)

### Acciones

* [[!UICONTROL Crear cubo]](#create-bucket)
* [[!UICONTROL Obtener archivo]](#get-file)
* [[!UICONTROL Realización de una llamada API]](#make-an-api-call)
* [[!UICONTROL Cargar archivo]](#upload-file)

#### [!UICONTROL Crear cubo]

Este módulo de acción crea un bloque en AWS.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL AWS] a Workfront Fusion, consulte <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL AWS] a Workfront Fusion</a> en este artículo.</p> </td> 
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
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL AWS] a Workfront Fusion, consulte <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL AWS] a Workfront Fusion</a> en este artículo.</p> </td> 
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

#### [!UICONTROL Realización de una llamada API]

Este módulo de acción realiza una llamada personalizada a la API de AWS S3.

Para obtener una explicación sobre la API de [!DNL Amazon S3], consulte Introducción a la API REST de [[!DNL Amazon S3] &#x200B;](https://docs.aws.amazon.com/AmazonS3/latest/API/Welcome.html).

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL AWS] a Workfront Fusion, consulte <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL AWS] a Workfront Fusion</a> en este artículo.</p> </td> 
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
       <td> <p>La fecha y hora actuales según el solicitante. Ejemplo: <code>Wed, 01 Mar 2006 12:00:00 GMT</code>. Cuando especifique el encabezado <code>Authorization </code>, debe especificar el encabezado <code>x-amz-date</code> o <code>Date </code>.</p> </td> 
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
       <td> <p>La fecha y hora actuales según el solicitante. Ejemplo: <code>Wed, 01 Mar 2006 12:00:00 GMT</code>. Cuando especifique el encabezado <code>Authorization </code>, debe especificar el encabezado <code>x-amz-date</code> o <code>Date </code>. Si especifica ambos, el valor especificado del encabezado <code>x-amz-date</code> tiene prioridad.</p> </td> 
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
   <td> <p>Añada el contenido del cuerpo para la llamada API en forma de objeto JSON estándar.</p> <p>Nota:   <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
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
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL AWS] a Workfront Fusion, consulte <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL AWS] a Workfront Fusion</a> en este artículo.</p> </td> 
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
   <td role="rowheader">[!UICONTROL Archivo de origen]</td> 
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
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL AWS] a Workfront Fusion, consulte <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL AWS] a Workfront Fusion</a> en este artículo.</p> </td> 
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
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL AWS] a Workfront Fusion, consulte <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">Conexión de [!DNL AWS] a Workfront Fusion</a> en este artículo.</p> </td> 
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
