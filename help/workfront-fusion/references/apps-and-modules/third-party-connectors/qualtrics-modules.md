---
title: Módulos de Qualtrics
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan Qualtrics, así como conectarlos a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: 80b441b7-c808-4c4f-b9ff-d614650dbb73
TQID: https://experienceleague.adobe.com/gbH5KTIEYyIAVMSjhmnAyuApEPu7i3eicmMvmJC-gi4
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 352
ht-degree: 88%

---

# Módulos de Qualtrics

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!DNL Qualtrics], así como conectarlo a varias aplicaciones y servicios de terceros.

Para obtener instrucciones sobre cómo crear un escenario, consulte los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, consulte los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

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

## Requisitos previos

Para utilizar módulos de [!DNL Qualtrics], debe tener una cuenta de [!UICONTROL Qualtrics].

## Información de API de Qualtrics

El conector Qualtrics utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL base</td> 
   <td><pre><code>https://&#123;&#123;connection.dataCenterCode&#125;&#125;.qualtrics.com/API/v3</code></pre></td> 
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
      <td role="rowheader">[!UICONTROL Data Center ID] </td> 
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
