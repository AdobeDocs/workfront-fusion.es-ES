---
title: Módulos de imagen
description: Los módulos de imagen de Adobe Workfront Fusion le permiten obtener información sobre una imagen específica (dimensiones, tipo, etc.), convertir una imagen a otro formato de archivo y cambiar directamente el tamaño de la imagen.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: a7696c9d-002d-4bb4-ae10-1f69dc5e66fe
source-git-commit: 4697ea1449f77ddb8648658990098b3b4bc58ad2
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 13%

---

# Módulos de imagen

Los módulos [!UICONTROL Image] de Adobe Workfront Fusion le permiten obtener información sobre una imagen específica (dimensiones, tipo, etc.), convertir una imagen a otro formato de archivo y cambiar directamente el tamaño de la imagen.

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
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete Select o Prime Workfront que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++



## Módulos [!UICONTROL Image] y sus campos

Al configurar este módulo, se muestran los campos siguientes. El título en negrita en un módulo indica un campo obligatorio.

* [[!UICONTROL Convertir un formato]](#convert-a-format)
* [[!UICONTROL Extraer metadatos]](#extract-metadata)
* [[!UICONTROL Cambiar tamaño]](#resize)

### [!UICONTROL Convertir un formato]

Este módulo transformador cambia el formato de un archivo de imagen. Este módulo es compatible con los siguientes formatos:

* PNG
* JPG
* GIF
* BMP

Tanto el archivo de origen como la salida deben tener uno de estos formatos. Por ejemplo, el módulo [!UICONTROL Image] >[!UICONTROL Convert a format] puede transformar un archivo PNG en un archivo BMP o un BMP en un JPG.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Formato de salida]</td> 
   <td>Seleccione el formato en el que desea que el módulo convierta el archivo de origen. </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Extraer metadatos]

Este módulo transformador devuelve información básica sobre un módulo.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Cambiar tamaño]

Este módulo transformador cambia la altura y anchura de una imagen según los criterios especificados.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Deseo]</td> 
   <td>Seleccione si desea mantener la relación altura-anchura o cambiar las dimensiones a una altura y anchura especificadas.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Según]</td> 
   <td> <p>Seleccione cómo desea que el módulo determine el nuevo tamaño de la imagen. Este campo aparece si ha seleccionado mantener la relación altura-anchura en el campo Deseo. Aparecerán otros campos en función de la selección de este campo.</p> 
    <ul> 
     <li> <p>[!UICONTROL Anchura máxima]</p> <p>Reduce una imagen al ancho especificado. La altura se calcula automáticamente.</p> </li> 
     <li> <p>[!UICONTROL Altura máxima]</p> <p>Reduce una imagen a la altura especificada. La anchura se calcula automáticamente.</p> </li> 
     <li> <p>[!UICONTROL Alto o ancho máximo]</p> <p>Reduce una imagen de forma que su altura y anchura no superen los valores especificados. Debido a que esta opción mantiene la relación altura-anchura, una de las dimensiones puede ser más pequeña de lo especificado. Por ejemplo, si la altura y la anchura se especifican como 40, una imagen de 400 x 300 se reducirá a 40 x 30.</p> </li> 
     <li> <p>[!UICONTROL Anchura mínima]</p> <p>Amplía una imagen a la anchura especificada. La altura se calcula automáticamente.</p> </li> 
     <li> <p>[!UICONTROL Altura mínima]</p> <p>Aumenta el tamaño de una imagen hasta la altura especificada. La anchura se calcula automáticamente.</p> </li> 
     <li> <p>[!UICONTROL Altura o anchura mínima]</p> <p>Amplía una imagen de forma que su altura y anchura no sean menores que los valores especificados. Debido a que esta opción mantiene la relación altura-anchura, una de las dimensiones puede ser más grande de lo especificado. Por ejemplo, si la altura y la anchura se especifican como 300, una imagen de 40x30 se ampliará a 400X300.</p> </li> 
     <li> <p>[!UICONTROL Percent]</p> <p>Cambia el tamaño de la imagen en un porcentaje basado en el valor especificado. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Width]</td> 
   <td>Introduzca o asigne la anchura deseada de la imagen cuyo tamaño se ha cambiado en píxeles.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Height]</td> 
   <td>Introduzca o asigne la altura deseada de la imagen cuyo tamaño se ha cambiado en píxeles.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Cambio por porcentaje]</td> 
   <td>Si ha elegido cambiar la imagen por porcentaje, introduzca o asigne el porcentaje por el que desea cambiar la imagen.</td> 
  </tr> 
 </tbody> 
</table>

## Resolución de problemas

### La acción ha finalizado con un error

una acción puede finalizar con un error debido a una de las siguientes causas:

* Los datos recibidos no tienen el formato JPG/GIF/PNG/BMP
* Se ha superado el límite máximo de anchura y altura al cambiar las dimensiones de la imagen. El tamaño de la imagen no debe superar los 3840 píxeles de anchura y los 2160 píxeles de altura
* Se ha superado el tamaño máximo permitido de una imagen al cambiar las dimensiones o el formato de la imagen.
