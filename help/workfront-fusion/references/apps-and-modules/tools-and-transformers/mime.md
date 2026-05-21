---
title: Módulos MIME
description: Puede utilizar tipos MIME en Adobe Workfront Fusion. Los tipos MIME (Multipurpose Internet Extension) son etiquetas que permiten al software identificar diferentes tipos de datos compartidos en Internet. Los servidores y exploradores web utilizan el tipo MIME para determinar qué se debe hacer con un archivo. Por ejemplo, un archivo con el tipo MIME text/html se procesará en un explorador de forma distinta que un archivo con el tipo MIME image/jpeg. Los tipos MIME funcionan independientemente del sistema operativo y del hardware.
author: Becky
feature: Workfront Fusion
exl-id: 9259356b-5b42-4b6d-9854-fce9718d14e3
TQID: https://experienceleague.adobe.com/65lJuH7aL35rZCYDowjJuxuQAh88LHNyL3XRQVDJoOY
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 358
ht-degree: 93%

---

# [!UICONTROL Módulos MIME]

Puede utilizar tipos MIME en Adobe Workfront Fusion. Los tipos MIME (Multipurpose Internet Extension) son etiquetas que permiten al software identificar diferentes tipos de datos compartidos en Internet. Los servidores y exploradores web utilizan el tipo MIME para determinar qué se debe hacer con un archivo. Por ejemplo, un archivo con el tipo MIME `text/html` se procesará en un explorador de forma distinta que un archivo con el tipo MIME `image/jpeg`. Los tipos MIME funcionan independientemente del sistema operativo y del hardware.

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
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++



## Módulos [!UICONTROL MIME] y sus campos

* [Obtener una extensión de archivo](#get-a-file-extension)
* [Obtener un tipo MIME](#get-a-mime-type)

### [!UICONTROL Obtener una extensión de archivo]

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

### [!UICONTROL Obtener un tipo MIME]

Este módulo transformador devuelve el tipo MIME asociado con un nombre de archivo, ruta o extensión determinados.

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
