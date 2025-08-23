---
title: Módulos de Qualtrics
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan Qualtrics, así como conectarlos a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: 80b441b7-c808-4c4f-b9ff-d614650dbb73
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 48%

---

# Módulos de Qualtrics

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!DNL Qualtrics], así como conectarlo a varias aplicaciones y servicios de terceros.

Para obtener instrucciones sobre cómo crear un escenario, vea los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

## Requisitos de acceso

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Plan de Adobe Workfront*</td>
  <td> <p>[!UICONTROL Pro] o superior</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencia de Adobe Workfront*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion**</td> 
   <td>
   <p>Requisito de licencia actual: no se requiere licencia de Workfront Fusion.</p>
   <p>O</p>
   <p>Requisito de licencia heredado: [!UICONTROL Workfront Fusion para automatización e integración de trabajo] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Requisito actual del producto: si tiene el plan de Adobe Workfront de [!UICONTROL Select] o [!UICONTROL Prime], su organización debe adquirir Adobe Workfront Fusion y Adobe Workfront para utilizar la funcionalidad que se describe en este artículo. Workfront Fusion está incluido en el plan de Workfront de [!UICONTROL Ultimate].</p>
   <p>O</p>
   <p>Requisito de productos heredados: su organización debe adquirir Adobe Workfront Fusion así como Adobe Workfront para utilizar la funcionalidad descrita en este artículo.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Para saber qué plan, tipo de licencia o acceso tiene, póngase en contacto con el administrador de Workfront.

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## Requisitos previos

Para utilizar módulos de [!DNL Qualtrics], debe tener una cuenta de [!UICONTROL Qualtrics].

## Información de API de Qualtrics

El conector Qualtrics utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Dirección URL base</td> 
   <td> https://{{connection.dataCenterCode}}.qualtrics.com/API/v3 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> v3 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.1.1</td> 
  </tr>
 </tbody> 
 </table>

## Conectando [!DNL Qualtrics] a Workfront Fusion

Puede crear una conexión a su cuenta de [!DNL Qualtrics] directamente desde un módulo de [!UICONTROL Qualtrics].

1. En cualquier módulo de [!UICONTROL Qualtrics], haga clic en **[!UICONTROL Añadir]** junto al campo [!UICONTROL Conexión].
1. Introduzca la siguiente información:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td> <p>Introduzca un nombre para la nueva conexión.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Data Center ID] </td> 
      <td>Use el formato <code>&lt;Data Center ID>.qualtrics.com</code>.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL API Key]</td> 
      <td>Para encontrar su clave de API, consulte la documentación de [!DNL Qualtrics].</td> 
     </tr> 
    </tbody> 
   </table>

1. Haga clic en **[!UICONTROL Continuar]** para crear la conexión y volver al módulo.

## Módulos de [!DNL Qualtrics] y sus campos

Los siguientes módulos están disponibles para el conector de [!DNL Qualtrics]:

* [!UICONTROL Ver nueva respuesta de encuesta]
* [!UICONTROL Crear un contacto de directorio]
* [!UICONTROL Eliminar un contacto de directorio]
* [!UICONTROL Obtener un contacto de directorio]
* [!UICONTROL Actualizar un contacto de directorio]
* [!UICONTROL Crear una nueva distribución de encuesta mediante SMS]
* [!UICONTROL Distribuir una encuesta por correo electrónico]
* [!UICONTROL Realizar una llamada API]
* [!UICONTROL Lista de contactos de directorio]
