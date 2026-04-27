---
title: Conectar Adobe Workfront Fusion a Google Services con medidas de seguridad actualizadas
description: Google has introduced restrictions on how users can use their API. This article describes how to connect Adobe Workfront Fusion to Google, accounting for these update security measures.
author: Becky
feature: Workfront Fusion
exl-id: eac7ba26-664e-464c-b05c-8c2ebf407fb3
source-git-commit: bbd1ec27e52127c8814188612a1e8d5cfab0cd25
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 29%

---

# Conectar Adobe Workfront Fusion a Google Services con medidas de seguridad actualizadas

Google has introduced restrictions on how users can use their API. This article describes how to connect Adobe Workfront Fusion to Google, accounting for these update security measures.

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
   <p>Basado en operaciones: no se requiere licencia de Workfront Fusion</p>
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

## Google Services restrictions

Google introduced restrictions on how users can use their API as of June 1st, 2020. These security measures protect Google users from leakage or misuse of their personal data on Google.

These restrictions are related to the Gmail and Google Drive apps.

For more information about these restrictions, see &quot;Additional Requirements for Specific API Scopes&quot; in the [Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy#additional_requirements_for_specific_api_scopes)

To access restricted scopes, the connected service (Adobe Workfront Fusion or any other service that accesses the user&#39;s data via the API) must be verified, and must have a Letter of Assessment to prove that the service is secure and transparent about how they use the data. Workfront Fusion complies with all of Google&#39;s requirements for access to restricted scopes. However, most of the third-party connected services in Workfront Fusion don&#39;t have the Letter of Assessment, and therefore don&#39;t comply with Google terms. Because of that, Workfront Fusion is not permitted to send data to these services.

## Exceptions to Google Services restrictions

Hay algunas excepciones que permiten enviar datos a un servicio de terceros no aprobado que no tiene la carta de evaluación sin violar ninguna de las nuevas restricciones. They differ based on Google Workspace with the Workfront Fusion OAuth client, Google Workspace with another OAuth client, or @gmail.com and @googlemail.com.

* [Google Workspace with Workfront Fusion OAuth client](#google-workspace-with-workfront-fusion-oauth-client)
* [Google Workspace with another OAuth client](#google-workspace-with-another-oauth-client)
* [@gmail.com and @googlemail.com](#gmailcom-and-googlemailcom)

### Google Workspace with Workfront Fusion OAuth client

Workfront Fusion uses the Domain-wide Installation exception. Domain-wide Installation is suited for Google Workspace users, and allows users to integrate unapproved services without any limitations. Si es un usuario de Google Workspace, no tiene que realizar ningún paso adicional y puede conectarse directamente a servicios no aprobados.

### Google Workspace with another OAuth client

Google Workspace users that prefer to use their own OAuth client instead of using the Workfront Fusion OAuth client can connect to Google Services through the Internal Use approach. Esta opción está destinada a usuarios avanzados. For instructions, see [Connect Adobe Workfront Fusion to Google Services using a custom OAuth client](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md).

### @gmail.com and @googlemail.com {#gmailcom-and-googlemailcom}

Users that access Google Services through @gmail.com or @googlemail.com can connect to Google Services through the Personal Use approach. Esta opción está destinada a usuarios avanzados. For instructions, see [Connect Adobe Workfront Fusion to Google Services using a custom OAuth client](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md).

## Preguntas frecuentes

* [What apps in Adobe Workfront Fusion are affected?](#what-apps-in-adobe-workfront-fusion-are-affected)
* [Do I have a Google Workspace account?](#do-i-have-a-g-suite-account)
* [What should I do if I&#39;m a @gmail.com or @googlemail.com user?](#what-should-i-do-if-im-gmailcom-or-googlemailcom-user)
* [What should I do if I&#39;m a Google Workspace user?](#what-should-i-do-if-im-a-g-suite-user)

### What apps in Adobe Workfront Fusion are affected? {#what-apps-in-adobe-workfront-fusion-are-affected}

Google Drive, Gmail, and Email (connected to Gmail account).

### Do I have a Google Workspace account? {#do-i-have-a-g-suite-account}

If your email address ends with @gmail.com or @googlemail.com, your account is not a Google Workspace account. If your Google account ends with a custom domain such as @my-company.com, then it is a Google Workspace account.

### What should I do if I&#39;m @gmail.com or @googlemail.com user? {#what-should-i-do-if-im-gmailcom-or-googlemailcom-user}

These new restrictions only apply if you are integrating Google Drive or Gmail. If you want to connect to Google Drive or Gmail, you can

* Switch to Google Workspace.

  o

* Cree un cliente de OAuth personalizado. Esta opción está destinada a usuarios avanzados.

  For instructions, see [Connect Adobe Workfront Fusion to Google Services using a custom OAuth client](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md).

If you want to integrate any other service than Google Drive or Gmail, these restrictions do not apply.

### What should I do if I&#39;m a Google Workspace user? {#what-should-i-do-if-im-a-g-suite-user}

No se requiere ninguna acción.
