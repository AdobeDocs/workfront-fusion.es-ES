---
title: Módulos MIME
description: Puede utilizar tipos MIME en Adobe Workfront Fusion. Los tipos MIME (Multipurpose Internet Extension) son etiquetas que permiten al software identificar diferentes tipos de datos compartidos en Internet. Los servidores y exploradores web utilizan el tipo MIME para determinar qué se debe hacer con un archivo. Por ejemplo, un archivo con el tipo MIME text/html se procesará en un explorador de forma distinta que un archivo con el tipo MIME image/jpeg. Los tipos MIME funcionan independientemente del sistema operativo y del hardware.
author: Becky
feature: Workfront Fusion
exl-id: 9259356b-5b42-4b6d-9854-fce9718d14e3
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 77%

---

# [!UICONTROL Módulos MIME]

Puede utilizar tipos MIME en Adobe Workfront Fusion. Los tipos MIME (Multipurpose Internet Extension) son etiquetas que permiten al software identificar diferentes tipos de datos compartidos en Internet. Los servidores y exploradores web utilizan el tipo MIME para determinar qué se debe hacer con un archivo. Por ejemplo, un archivo con el tipo MIME `text/html` se procesará en un explorador de forma distinta que un archivo con el tipo MIME `image/jpeg`. Los tipos MIME funcionan independientemente del sistema operativo y del hardware.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront</td> 
   <td> <p>Cualquiera</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencia de Adobe Workfront</td> 
   <td> <p>Nuevo: estándar</p><p>O</p><p>Actual: Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion**</td> 
   <td>
   <p>No se requiere licencia de Workfront Fusion</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Seleccione o paquete de Prime Workfront: su organización debe adquirir Adobe Workfront Fusion.</li><li>Paquete de Ultimate Workfront: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe comprar Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

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
