---
title: Cifrador de datos
description: Los módulos del cifrador de datos de Adobe Workfront Fusion le permiten cifrar cualquier dato de texto. Actualmente, admiten el cifrado de mensajes mediante AES256 y PGP (OpenPGP).
author: Becky
feature: Workfront Fusion
exl-id: 4b119efe-6762-445e-bbc7-c59437fd5060
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 73%

---

# Cifrador de datos

[!DNL Adobe Workfront Fusion] [!UICONTROL Encryptor] módulos le permiten cifrar cualquier dato de texto. Actualmente admiten el cifrado de mensajes mediante AES256 y PGP ([!UICONTROL OpenPGP]).

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
   <p>Requisito de licencia heredado: [!UICONTROL [!DNL Workfront Fusion] para automatización e integración de trabajo, [!UICONTROL [!DNL Workfront Fusion] para automatización de trabajo</p>
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

Para saber qué plan, tipo de licencia o acceso tiene, póngase en contacto con el administrador de [!DNL Workfront].

Para obtener información sobre licencias de [!DNL Adobe Workfront Fusion], consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## Cifrado y descifrado de mensajes mediante PGP

Al cifrar y descifrar mediante PGP, es necesario utilizar un llavero y crear una clave privada o pública (o ambas).

Para obtener más información sobre las claves públicas y privadas, consulte [glosario de Adobe Workfront Fusion](/help/workfront-fusion/get-started-with-fusion/understand-fusion/fusion-glossary.md). <!--For more information on keychains, see [Keys in [!DNL Adobe Workfront Fusion]]().-->

## Módulos de [!UICONTROL Encryptor] y sus campos

Al configurar [!UICONTROL Encryptor] módulos, se muestran los siguientes campos. El título en negrita en un módulo indica un campo obligatorio.

### Cifrado de un mensaje PGP

Este módulo le permite cifrar un mensaje utilizando claves públicas y privadas.

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Private key]</td>
        <td>Introduzca la clave privada del remitente. Esto puede autenticar la identidad del remitente.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Public key]</td>
        <td>Introduzca la clave pública del destinatario.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Message]</td>
        <td>Escriba el mensaje que desea cifrar.</td>
    </tr>

### Descifrado de un mensaje PGP

Este módulo le permite descifrar un mensaje utilizando claves públicas y privadas.

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Private key]</td>
        <td>Introduzca la clave privada del destinatario.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Public key]</td>
        <td>Introduzca la clave pública del destinatario. Esto puede autenticar la identidad del remitente.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Message]</td>
        <td>Asigne el mensaje que desea descifrar.</td>
    </tr>
</table>
