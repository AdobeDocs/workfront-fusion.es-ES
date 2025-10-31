---
title: Creación de conexiones
description: Una conexión debe cumplir los requisitos establecidos por la API de la aplicación o del servicio web al que se conecta. Por este motivo, las instrucciones para configurar una conexión varían en función de la aplicación o el servicio web. Este artículo puede ayudarle a identificar y localizar las instrucciones para conectar Adobe Workfront Fusion a la aplicación o al servicio web que haya elegido.
author: Becky
feature: Workfront Fusion
exl-id: 281403a6-6f88-4976-8a10-1d0848ef9b35
source-git-commit: b2ca63ca5af26ee79758798118817b55113b3bd0
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 36%

---

# Creación de conexiones

Una conexión debe cumplir los requisitos establecidos por la API de la aplicación o del servicio web al que se conecta. Por este motivo, las instrucciones para configurar una conexión varían en función de la aplicación o el servicio web. Este artículo puede ayudarle a identificar y localizar las instrucciones para conectar Adobe Workfront Fusion a la aplicación o al servicio web que haya elegido.

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
   <p>Basado en conectores (heredado): para conectarse a aplicaciones fuera de la familia de productos de Workfront, debe tener Workfront Fusion para la automatización e integración del trabajo </p>
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

## Conectarse a una aplicación o servicio web que no requiera configuración

En la mayoría de los casos, puede utilizar el módulo para crear una conexión con poca o ninguna información adicional. Workfront Fusion gestiona la autenticación automáticamente.

Para obtener instrucciones sobre cómo crear una conexión sin consideraciones especiales, consulte [Crear una conexión: instrucciones básicas](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md).

## Conectarse a una aplicación o servicio de Adobe

Para conectarse a una aplicación o servicio de Adobe, es posible que necesite información de Adobe Admin Console, como su ID de organización o el ID de cuenta técnica.

También puede utilizar el módulo Adobe Authenticator para conectarse a cualquier API de Adobe mediante una sola conexión. Esto le permite conectarse más fácilmente a los productos de Adobe que aún no tienen un conector Fusion específico.

Para obtener instrucciones específicas, vea [el artículo del conector](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#connectors-for-adobe-products).

## Conectarse a una aplicación o servicio web de [!DNL Microsoft]

La mayoría de las aplicaciones de [!DNL Microsoft] de Workfront Fusion le permiten crear una conexión sin información adicional.

Las siguientes circunstancias requieren pasos adicionales para crear una conexión:

* Uso de módulos de Microsoft Dynamics 365.

  Para obtener instrucciones, consulte [módulos de Microsoft Dynamics 365](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/microsoft-dynamics-365-modules.md).

* Conexión a la API de Microsoft Graph mediante un módulo HTTP

  Para obtener instrucciones, consulte [Llamar a la API de REST de MS Graph](/help/workfront-fusion/create-scenarios/connect-to-apps/call-the-ms-graph-rest-api.md).

## Conectarse a una aplicación o servicio web de [!DNL Google]

El proceso de conexión a las aplicaciones de [!DNL Google] puede diferir según el tipo de cuenta de [!DNL Google] que esté usando. Además, las medidas de seguridad de [!DNL Google] pueden requerir una configuración adicional al conectarse a Workfront Fusion.

Para obtener más información, consulte lo siguiente:

* [Conexión de Adobe Workfront Fusion a Google Services con un cliente de OAuth personalizado](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md)
* [Conexión de Adobe Workfront Fusion a los servicios de Google con medidas de seguridad actualizadas](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-google-with-new-security-measures.md)

## Otras aplicaciones que requieren configuración adicional

Algunas aplicaciones y servicios no siguen la configuración básica de las conexiones de Workfront Fusion. Puede encontrar instrucciones para conectar estas aplicaciones en el artículo correspondiente a esa aplicación.

Para obtener instrucciones específicas, vea [el artículo del conector](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#connectors-for-third-party-applications).
