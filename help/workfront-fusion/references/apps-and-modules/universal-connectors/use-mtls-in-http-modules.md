---
title: Uso de TLS mutuo en módulos HTTP en Adobe Workfront Fusion
description: Puede utilizar TLS mutuo en los módulos HTTP de Adobe Workfront Fusion, lo que permite que ambas partes de la transacción de información comprueben la identidad del otro.
author: Becky
feature: Workfront Fusion
exl-id: 1e0b4c3b-9a0b-491d-aaf2-0011d8386abe
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '627'
ht-degree: 12%

---

# Usar TLS mutuo en módulos HTTP en [!DNL Adobe Workfront Fusion]

>[!NOTE]
>
>Adobe Workfront Fusion requiere una licencia de [!DNL Adobe Workfront Fusion] además de una licencia Adobe Workfront.

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

&#42;Para saber qué plan, tipo de licencia o acceso tiene, póngase en contacto con el administrador de [!DNL Workfront].

&#42;&#42;Para obtener información sobre licencias de [!DNL Adobe Workfront Fusion], consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)

## Proporcionar su certificado público [!DNL Workfront Fusion]


Cuando se conecta a un servicio web con una solicitud HTTP, el servicio web generalmente requiere un certificado público [!DNL Workfront Fusion] para la verificación. Esto permite al servicio web comparar el certificado presentado en la solicitud HTTP con el que está archivado, como una forma de asegurarse de que el certificado esté en la lista de permitidos del servicio web.

Para obtener instrucciones sobre cómo cargar el certificado público [!DNL Adobe Workfront Fusion] en un servicio web, consulte la documentación del servicio web.

>[!NOTE]
>
>Es posible que deba proporcionar otra información además del certificado. Para obtener información sobre lo que requiere un servicio web, consulte la documentación de la API del servicio web.

Puede utilizar los siguientes vínculos para descargar los certificados públicos de Workfront Fusion:

### Certificados para el 23 de abril de 2023 al 7 de mayo de 2024

>[!IMPORTANT]
>
>* Estos [!DNL Workfront Fusion] certificados públicos caducan el 7 de mayo de 2025. Una vez que caduque el suyo, deberá cargar un nuevo certificado en el servicio web. Le recomendamos que:
>
>   * Tome nota de la fecha de caducidad y configure un recordatorio para que usted mismo cargue el certificado en su servicio web.
>   * Marque esta página para encontrar fácilmente los nuevos certificados.
>
>* Son certificados mTLS no comodín.

* [Descargar  [!DNL Workfront Fusion] certificado 2023](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/fusion-prod-us-mtls-certificate.pem)
* [Descargar  [!DNL Workfront Fusion] Certificado de la UE 2023](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/fusion-prod-eu-mtls-certificate.pem)

  Para uso en la UE

<!--

### Certificates for November 14, 2022 - July 15, 2023

>[!IMPORTANT]
>
>* These [!DNL Workfront Fusion] public certificates expire on July 15, 2023.
>* These are wildcard mTLS certificates.

* [Download [!DNL Workfront Fusion] Certificate 2023](https://cdn.experience.workfront.com/Documentation/Workfront+Fusion+2.0+public+certificates/app_workfrontfusion_com-jul-15-2023+updated.cer)
* [Download [!DNL Workfront Fusion] EU Certificate 2023](https://cdn.experience.workfront.com/Documentation/Workfront+Fusion/app-eu_workfrontfusion_com-jul-15-2023.cer)

   For use in the EU 

   -->

## Habilitando TLS mutuo en [!DNL Workfront Fusion] módulos HTTP

Todos los módulos de solicitud [!DNL Workfront Fusion] [!UICONTROL HTTP] tienen la opción de habilitar TLS mutuo.

Para habilitar TLS mutuo en un módulo de solicitud [!UICONTROL HTTP]:

1. Agregue un módulo de solicitud [!UICONTROL HTTP] a su escenario.
1. Comience a configurar el módulo.

   <!--For instructions on configuring an [!UICONTROL HTTP] request module, see the appropriate article under [[!UICONTROL Universal connectors] modules](/help/workfront-fusion/references/apps-and-modules/universal-connectors/).-->

1. Habilite **[!UICONTROL Show advanced settings]** cerca de la parte inferior del módulo.
1. Habilitar **[!UICONTROL Use Mutual TLS]**.
