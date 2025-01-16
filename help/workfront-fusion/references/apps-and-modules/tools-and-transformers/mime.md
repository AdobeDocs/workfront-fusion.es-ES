---
title: Módulos MIME
description: Puede utilizar tipos MIME en Adobe Workfront Fusion. Los tipos MIME (Multipurpose Internet Extension) son etiquetas que permiten al software identificar diferentes tipos de datos compartidos en Internet. Los servidores y exploradores web utilizan el tipo MIME para determinar qué se debe hacer con un archivo. Por ejemplo, un archivo con el tipo MIME text/html se procesará en un explorador de forma distinta que un archivo con el tipo MIME image/jpeg. Los tipos MIME funcionan independientemente del sistema operativo y del hardware.
author: Becky
feature: Workfront Fusion
exl-id: 9259356b-5b42-4b6d-9854-fce9718d14e3
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 88%

---

# Módulos de [!UICONTROL MIME]

Puede utilizar tipos MIME en Adobe Workfront Fusion. Los tipos MIME (Multipurpose Internet Extension) son etiquetas que permiten al software identificar diferentes tipos de datos compartidos en Internet. Los servidores y exploradores web utilizan el tipo MIME para determinar qué se debe hacer con un archivo. Por ejemplo, un archivo con el tipo MIME `text/html` se procesará en un explorador de forma distinta que un archivo con el tipo MIME `image/jpeg`. Los tipos MIME funcionan independientemente del sistema operativo y del hardware.

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

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## Módulos de [!UICONTROL MIME] y sus campos

### [!UICONTROL Get a MIME type]

Este módulo transformador devuelve el tipo MIME asociado con un nombre, ruta o extensión determinados.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL File]</td> 
   <td> <p>Introduzca o asigne el archivo para el que desea determinar el tipo MIME. </p> <p>Puede introducir el archivo mediante:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL File path]</strong> </p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Ejemplo: </b></span></span>/file/image.jpeg</p> </li> 
     <li><strong>[!UICONTROL File name]</strong>  <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Ejemplo: </b></span></span>image.jpeg</p> </li> 
     <li><strong>[!UICONTROL File extension]</strong>  <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Ejemplo: </b></span></span>jpeg</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Get a file extension]

Este módulo transformador devuelve la extensión de archivo original para un tipo MIME determinado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL MIME type]</td> 
   <td> <p>Introduzca o asigne el tipo MIME para el que desea determinar la extensión de archivo. </p> </td> 
  </tr> 
 </tbody> 
</table>
