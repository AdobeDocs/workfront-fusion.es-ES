---
title: Uso de TLS mutuo en módulos HTTP en Adobe Workfront Fusion
description: Puede utilizar TLS mutuo en los módulos HTTP de Adobe Workfront Fusion, lo que permite que ambas partes de la transacción de información comprueben la identidad del otro.
author: Becky
feature: Workfront Fusion
exl-id: 1e0b4c3b-9a0b-491d-aaf2-0011d8386abe
source-git-commit: e0b25da3d0c7a2cab454adafc7525f14c4f0b4eb
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 16%

---

# Uso de TLS mutuo en módulos HTTP en Adobe Workfront Fusion

## Información general de TLS mutuo

Al enviar datos a través de Internet, es importante asegurarse de que vayan a o vengan de la ubicación correcta y de que solo el destinatario deseado pueda leerlos. Con TLS habilitado, el cliente (equipo que solicita información) utiliza certificados para comprobar la identidad del servidor (equipo que proporciona información). Esto hace que las conexiones HTTP sean seguras.

TLS mutuo permite que esta confirmación de identidad funcione en ambos sentidos. Cuando el servidor envía su certificado para comprobar su identidad al cliente, también solicita el certificado del cliente. Esto garantiza que el servidor no envíe información a un sitio o usuario que pueda hacer un uso indebido de ella.

>[!INFO]
>
>**Ejemplo:**
>
>* **TLS**: Cuando una persona escribe &quot;MyGreatBank.com&quot; en un explorador, quiere estar segura de que va a My Great Bank, no a un sitio web que podría usar indebidamente o vender su información bancaria. También quieren asegurarse de que la información de su cuenta bancaria esté cifrada.
>
>   Cuando el explorador (el cliente) se conecta a MyGreatBank.com (el servidor), TLS requiere un certificado de MyGreatBank.com para comprobar su identidad. El certificado lo proporciona una entidad emisora de certificados como [!DNL DigiCert] o [!DNL Thawte]. Dado que el explorador confía en la autoridad de certificación, permite la conexión.
>
>* **TLS mutuo**: MySoftware.com es un cliente de software que necesita información de la API de MyGreatBank.com. MyGreatBank solo permite a los clientes de confianza conectarse a sus servidores. Por lo tanto, además del TLS normal que verifica la identidad de MyGreatBank.com, el proceso de autoridad de TLS/certificados también verifica la solicitud de MySoftware.com.

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

## Suministro del certificado público de Workfront Fusion

Cuando se conecta a un servicio web con una solicitud HTTP, el servicio web suele requerir un certificado público de Workfront Fusion para la verificación. Esto permite al servicio web comparar el certificado presentado en la solicitud HTTP con el que está archivado, como una forma de asegurarse de que el certificado esté en la lista de permitidos del servicio web.

Para obtener instrucciones sobre cómo cargar el certificado público de Adobe Workfront Fusion en un servicio web, consulte la documentación del servicio web.

>[!NOTE]
>
>Es posible que deba proporcionar otra información además del certificado. Para obtener información sobre lo que requiere un servicio web, consulte la documentación de la API del servicio web.

Puede utilizar los siguientes vínculos para descargar los certificados públicos de Workfront Fusion. Para localizar su centro de datos, consulte [Identifique su centro de datos](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/set-up-ip-addresses-for-fusion.md) en el artículo Configuración de direcciones IP para Fusion en la lista de permitidos de su organización.

### Certificados para 2026

>[!IMPORTANT]
>
>* Estos certificados públicos de Workfront Fusion caducan el **2 de marzo de 2027** (EE.UU. y la UE) o el **8 de marzo de 2027** (Azure). Una vez que caduque el suyo, deberá cargar un nuevo certificado en el servicio web. Le recomendamos que:
>
>   * Tome nota de la fecha de caducidad y configure un recordatorio para que usted mismo cargue el certificado en su servicio web.
>   * Marque esta página para encontrar fácilmente los nuevos certificados.
>
>* Son certificados mTLS no comodín.

| Datacenter | Vínculo de descarga | Fechas válidas |
| --- | --- | --- |
| US Datacenter | [Descargar certificado Workfront Fusion US 2026](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/2026-certs/fusion-prod-us-mtls-certificate-2026.pem) | Del 29 de enero de 2026 al 2 de marzo de 2027 |
| Centro de datos UE | [Descargar el certificado Workfront Fusion EU 2026](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/2026-certs/fusion-prod-eu-mtls-certificate-2026.pem) | Del 29 de enero de 2026 al 2 de marzo de 2027 |
| Azure Cluster | [Descargar certificado de Workfront Fusion Azure 2026](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/2026-certs/fusion-prod-eu-az-mtls-certificate-2026.pem) | Del 4 de febrero de 2026 al 8 de marzo de 2027 |


### Certificados para 2025

>[!IMPORTANT]
>
>* Se recomienda instalar los certificados para 2026, disponibles más arriba.
>* Estos certificados públicos de Workfront Fusion caducan el **4 de abril de 2026** (EE.UU. y la UE) o el **25 de noviembre de 2025** (Azure). Una vez que caduque el suyo, deberá cargar un nuevo certificado en el servicio web. Le recomendamos que:
>
>   * Tome nota de la fecha de caducidad y configure un recordatorio para que usted mismo cargue el certificado en su servicio web.
>   * Marque esta página para encontrar fácilmente los nuevos certificados.
>
>* Son certificados mTLS no comodín.

| Datacenter | Vínculo de descarga | Fechas válidas |
| --- | --- | --- |
| US Datacenter | [Descargar certificado Workfront Fusion US 2025](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/2025-certs/fusion-prod-us-mtls-certificate.pem) | Del 3 de marzo de 2025 al 4 de abril de 2026 |
| Centro de datos UE | [Descargar el certificado Workfront Fusion EU 2025](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/2025-certs/fusion-prod-eu-mtls-certificate.pem) | Del 3 de marzo de 2025 al 4 de abril de 2026 |
| Azure Cluster | [Descargar certificado de Workfront Fusion Azure 2025](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/2025-certs/fusion-prod-az-mtls-certificate.pem) | Del 24 de octubre de 2024 al 25 de noviembre de 2025 |

<!--

### Certificates for 2024

>[!IMPORTANT]
>
>* We recommend installing the certificates for 2025, available above.
>* These Workfront Fusion public certificates expire on **May 7, 2025**. After yours expires you will need to upload a new certificate to the web service. We recommend that you:
>
>   * Make note of the expiration date and set a reminder for yourself to upload the certificate to your web service.
>   * Bookmark this page to easily find the new certificates.
>
>* These are non-wildcard mTLS certificates.

| Datacenter | Download link | Dates valid |
|---|---|---|
| US Datacenter | [Download Workfront Fusion Certificate 2024](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/fusion-prod-us-mtls-certificate.pem) | April 5, 2024 to May 7, 2025 |
| EU Datacenter | [Download Workfront Fusion EU Certificate 2024](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/fusion-prod-eu-mtls-certificate.pem) | April 5, 2024 to May 7, 2025 |

-->

## Activación de TLS mutuo en módulos HTTP de Workfront Fusion

Todos los módulos de solicitud [!UICONTROL HTTP] de Workfront Fusion tienen la opción de habilitar TLS mutuo.

Para habilitar TLS mutuo en un módulo de solicitud [!UICONTROL HTTP]:

1. Agregue un módulo de solicitud [!UICONTROL HTTP] a su escenario.
1. Comience a configurar el módulo.

   Para obtener instrucciones sobre cómo configurar un módulo de solicitud [!UICONTROL HTTP], consulte el artículo correspondiente en [Conectores universales](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#universal-connectors).

1. Habilitar **[!UICONTROL Mostrar configuración avanzada]** cerca de la parte inferior del módulo.
1. Habilitar **[!UICONTROL Usar TLS mutuo]**.
