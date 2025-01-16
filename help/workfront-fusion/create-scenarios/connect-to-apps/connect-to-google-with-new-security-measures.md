---
title: Conexión de Adobe Workfront Fusion a los servicios de Google con medidas de seguridad actualizadas
description: Google ha introducido restricciones sobre cómo los usuarios pueden utilizar su API. En este artículo se describe cómo conectar Adobe Workfront Fusion a Google teniendo en cuenta estas medidas de seguridad de actualización.
author: Becky
feature: Workfront Fusion
exl-id: eac7ba26-664e-464c-b05c-8c2ebf407fb3
source-git-commit: 362952ec85b0df2306ba117ba530e95201330cca
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 20%

---

# Conexión de Adobe Workfront Fusion a los servicios de Google con medidas de seguridad actualizadas

Google ha introducido restricciones sobre cómo los usuarios pueden utilizar su API. En este artículo se describe cómo conectar Adobe Workfront Fusion a Google teniendo en cuenta estas medidas de seguridad de actualización.

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

## Restricciones de Google Services

Google introdujo restricciones sobre cómo los usuarios pueden utilizar su API a partir del 1 de junio de 2020. Estas medidas de seguridad protegen a los usuarios de Google de la filtración o el uso indebido de sus datos personales en Google.

Estas restricciones están relacionadas con las aplicaciones de Gmail y Google Drive.

Para obtener más información sobre estas restricciones, consulte &quot;Requisitos adicionales para ámbitos de API específicos&quot; en la [Directiva de datos de usuario de servicios de API de Google](https://developers.google.com/terms/api-services-user-data-policy#additional_requirements_for_specific_api_scopes)

Para acceder a ámbitos restringidos, el servicio conectado (Adobe Workfront Fusion o cualquier otro servicio que acceda a los datos del usuario a través de la API) debe verificarse y debe tener una carta de evaluación para probar que el servicio es seguro y transparente sobre cómo utilizan los datos. Workfront Fusion cumple con todos los requisitos de Google para acceder a ámbitos restringidos. Sin embargo, la mayoría de los servicios conectados de terceros en Workfront Fusion no tienen la carta de evaluación y, por lo tanto, no cumplen los términos de Google. Por ello, no se permite a Workfront Fusion enviar datos a estos servicios.

## Excepciones a las restricciones de los servicios de Google

Hay algunas excepciones que permiten enviar datos a un servicio de terceros no aprobado que no tiene la carta de evaluación sin violar ninguna de las nuevas restricciones. Difieren según Google Workspace con el cliente OAuth de Workfront Fusion, Google Workspace con otro cliente OAuth o @gmail.com y @googlemail.com.

* [Google Workspace con el cliente OAuth de Workfront Fusion](#google-workspace-with-workfront-fusion-oauth-client)
* [Google Workspace con otro cliente de OAuth](#google-workspace-with-another-oauth-client)
* [@gmail.com y @googlemail.com](#gmailcom-and-googlemailcom)

### Google Workspace con el cliente OAuth de Workfront Fusion

Workfront Fusion utiliza la excepción de instalación para todo el dominio. La instalación en todo el dominio es adecuada para los usuarios de Google Workspace y permite a los usuarios integrar servicios no aprobados sin ninguna limitación. Si es un usuario de Google Workspace, no tiene que realizar ningún paso adicional y puede conectarse directamente a servicios no aprobados.

### Google Workspace con otro cliente de OAuth

Los usuarios de Workspace de Google que prefieran utilizar su propio cliente de OAuth en lugar de utilizar el cliente de OAuth de Workfront Fusion pueden conectarse a los servicios de Google mediante el método de uso interno. Esta opción está destinada a usuarios avanzados. Para obtener instrucciones, consulte [Conectar Adobe Workfront Fusion a Google Services con un cliente OAuth personalizado](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md).

### @gmail.com y @googlemail.com {#gmailcom-and-googlemailcom}

Los usuarios que acceden a los servicios de Google a través de @gmail.com o @googlemail.com pueden conectarse a los servicios de Google a través del método de uso personal. Esta opción está destinada a usuarios avanzados. Para obtener instrucciones, consulte [Conectar Adobe Workfront Fusion a Google Services con un cliente OAuth personalizado](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md).

## Preguntas frecuentes

* [¿Qué aplicaciones de Adobe Workfront Fusion se ven afectadas?](#what-apps-in-adobe-workfront-fusion-are-affected)
* [¿Tengo una cuenta de Google Workspace?](#do-i-have-a-g-suite-account)
* [¿Qué debo hacer si soy usuario de @gmail.com o @googlemail.com?](#what-should-i-do-if-im-gmailcom-or-googlemailcom-user)
* [¿Qué debo hacer si soy usuario de Google Workspace?](#what-should-i-do-if-im-a-g-suite-user)

### ¿Qué aplicaciones de Adobe Workfront Fusion se ven afectadas? {#what-apps-in-adobe-workfront-fusion-are-affected}

Google Drive, Gmail y Correo electrónico (conectados a la cuenta de Gmail).

### ¿Tengo una cuenta de Google Workspace? {#do-i-have-a-g-suite-account}

Si su dirección de correo electrónico termina con @gmail.com o @googlemail.com, su cuenta no es una cuenta de Google Workspace. Si su cuenta de Google termina con un dominio personalizado como @my-company.com, entonces es una cuenta de Google Workspace.

### ¿Qué debo hacer si soy usuario de @gmail.com o @googlemail.com? {#what-should-i-do-if-im-gmailcom-or-googlemailcom-user}

Estas nuevas restricciones solo se aplican si integra Google Drive o Gmail. Si desea conectarse a Google Drive o Gmail, puede

* Cambiar a Google Workspace

  o

* Cree un cliente de OAuth personalizado. Esta opción está destinada a usuarios avanzados.

  Para obtener instrucciones, consulte [Conectar Adobe Workfront Fusion a Google Services con un cliente OAuth personalizado](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md).

Si desea integrar cualquier otro servicio que no sea Google Drive o Gmail, estas restricciones no se aplican.

### ¿Qué debo hacer si soy usuario de Google Workspace? {#what-should-i-do-if-im-a-g-suite-user}

No se requiere ninguna acción.
