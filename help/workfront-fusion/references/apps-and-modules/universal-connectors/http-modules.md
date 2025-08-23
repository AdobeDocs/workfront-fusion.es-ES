---
title: HTTP > Otros módulos
description: La aplicación HTTP de Adobe Workfront Fusion proporciona varios módulos para la comunicación basados en el protocolo HTTP (Protocolo de transferencia de hipertexto). HTTP es la base de la comunicación de datos para la Internet. Puede utilizar los módulos para descargar páginas web y archivos, llamar a webhooks y extremos de API, etc.
author: Becky
feature: Workfront Fusion
exl-id: 7db97e6e-262d-4be2-823b-423f56a7d886
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 63%

---

# HTTP > Otros módulos

La aplicación Adobe Workfront Fusion [!UICONTROL HTTP] proporciona varios módulos de comunicación basados en el protocolo HTTP (protocolo de transferencia de hipertexto). HTTP es la base de la comunicación de datos para la Internet. Puede utilizar los módulos para descargar páginas web y archivos, llamar a webhooks y extremos de API, etc.

La elección correcta del módulo depende del mecanismo de autenticación/autorización que emplee el recurso al que desea acceder. A continuación, se muestran ejemplos de módulos

* **Realizar una solicitud**: destinado principalmente a recursos que no utilizan ningún tipo de autenticación o autorización
* **Realizar una solicitud de autenticación básica**: para recursos que usan [!DNL HTTP] autenticación básica (BA)
* **Realizar una solicitud OAuth 2.0**: Para recursos que utilizan el protocolo de autorización OAuth 2.0
* **Realizar una solicitud de autenticación de certificado de cliente**: Para recursos que emplean un protocolo de autorización que requiere un certificado del lado del cliente
* **Realizar una solicitud de autorización de clave API**: Para recursos que emplean claves API para la autorización

>[!NOTE]
>
>Si se está conectando a un producto de Adobe que actualmente no tiene un conector dedicado, le recomendamos utilizar el módulo de Adobe Authenticator.
>
>Para obtener más información, consulte [Módulo de Adobe Authenticator](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-authenticator-modules.md).

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
   <p>Actual: No se requiere licencia de Workfront Fusion</p>
   <p>O</p>
   <p>Heredado: Workfront Fusion para la automatización e integración del trabajo </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Seleccione o paquete de Prime Workfront: su organización debe adquirir Adobe Workfront Fusion.</li><li>Paquete de Ultimate Workfront: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe comprar Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Módulos de solicitud

Consulte los siguientes artículos para obtener instrucciones específicas sobre los módulos de solicitud:

* [[!UICONTROL HTTP] > [!UICONTROL Realizar una solicitud] módulo](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-a-request.md)
* [[!UICONTROL HTTP] > [!UICONTROL Realizar una solicitud de autorización básica] módulo](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-a-basic-auth-request.md)
* [Módulo [!UICONTROL HTTP] > [!UICONTROL Realizar una solicitud OAuth 2.0]](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-an-oauth-2-request.md)
* [[!UICONTROL HTTP] > [!UICONTROL Realizar una solicitud de autorización de certificado de cliente] módulo](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-a-client-cert-auth-request.md)
* [[!UICONTROL HTTP] > [!UICONTROL Realizar una solicitud de autorización de clave API]](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-an-api-key-auth-request.md)

## Otros módulos de acción

* [[!UICONTROL Obtener un archivo]](#get-a-file)
* [[!UICONTROL Resolver una dirección URL de destino]](#resolve-a-target-url)

### [!UICONTROL Obtener un archivo]

Este módulo de acción descarga un archivo desde la dirección URL especificada. Una vez descargado el archivo, puede procesarlo aún más (asignar los datos del archivo) mediante otros módulos en el escenario.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Evaluate all states as errors (except for 2xx and 3xx )] </td> 
   <td> <p>Utilice esta opción para configurar la gestión de errores.</p> <p>Para obtener más información, consulte <a href="/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md" class="MCXref xref">Control de errores en Adobe Workfront Fusion</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL] </td> 
   <td> <p>Introduzca o asigne la dirección URL del archivo que desea descargar. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Share cookies with other HTTP modules] </td> 
   <td> <p>Active esta opción si desea que las cookies de este sitio estén disponibles para otros módulos. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Resolver una dirección URL de destino]

Este módulo de acción resuelve una cadena de redirecciones HTTP y devuelve una dirección URL de destino.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL] </td> 
   <td> <p>Escriba o asigne la dirección URL que desea resolver, como una dirección URL de [!DNL bit.ly].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method] </td> 
   <td> <p>Seleccione si desea utilizar el método [!UICONTROL HEAD] o el método [!UICONTROL GET].</p> </td> 
  </tr> 
 </tbody> 
</table>

## Módulos de iterador

### [!UICONTROL Recuperar encabezados]

Este módulo devuelve cada encabezado (nombre y valor) del módulo HTTP especificado en un paquete independiente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Module]</td> 
   <td> <p> Seleccione el módulo del que desee recuperar los encabezados.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Generación de tokens web JSON (JWT)

Es posible generar un token JWT con la ayuda de funciones integradas:

Encabezado:

![Encabezado JWT](/help/workfront-fusion/references/apps-and-modules/assets/jwt-header-350x19.png)

Código para copiar y pegar:

```
{{replace(replace(replace(base64("{""alg"":""HS256"",""typ"":""JWT""}"); "/=/g"; emptystring); "/\+/g"; "-"); "/\//g"; "_")}}
```

Carga útil:

![Carga útil JWT](/help/workfront-fusion/references/apps-and-modules/assets/jwt-payload-350x17.png)

Código para copiar y pegar:

```
{{replace(replace(replace(base64("{""iss"":""key"",""exp"":" + (timestamp + 60) + "}"); "/=/g"; emptystring); "/\+/g"; "-"); "/\//g"; "_")}}
```

Token:

![Token JWT](/help/workfront-fusion/references/apps-and-modules/assets/jwt-token-350x15.png)

Código para copiar y pegar:

```
{{1.value}}.{{2.value}}.{{replace(replace(replace(sha256(1.value + "." + 2.value; "base64"; "secret"); "/=/g"; emptystring); "/\+/g"; "-"); "/\//g"; "_")}}
```
