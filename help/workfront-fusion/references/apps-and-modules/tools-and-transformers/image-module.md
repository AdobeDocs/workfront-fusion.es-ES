---
title: Módulos de imagen
description: Los módulos de imagen de Adobe Workfront Fusion le permiten obtener información sobre una imagen específica (dimensiones, tipo, etc.), convertir una imagen a otro formato de archivo y cambiar directamente el tamaño de la imagen.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: a7696c9d-002d-4bb4-ae10-1f69dc5e66fe
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 10%

---

# Módulos de imagen

[!DNL Adobe Workfront Fusion] [!UICONTROL Image] módulos le permiten obtener información sobre una imagen específica (dimensiones, tipo, etc.), convertir una imagen a otro formato de archivo y cambiar directamente el tamaño de la imagen.

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

## Módulos de [!UICONTROL Image] y sus campos

Al configurar este módulo, se muestran los campos siguientes. El título en negrita en un módulo indica un campo obligatorio.

* [[!UICONTROL Resize]](#resize)
* [[!UICONTROL Convert a format]](#convert-a-format)
* [[!UICONTROL Extract metadata]](#extract-metadata)

### [!UICONTROL Resize]

Este módulo transformador cambia la altura y anchura de una imagen según los criterios especificados.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione el origen de la imagen que desea convertir. Puede seleccionar la salida de un módulo anterior o asignar el archivo de datos y el nombre de archivo. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data]</td> 
   <td>Asigne el archivo que desea convertir. Este campo está disponible si ha seleccionado [!UICONTROL Map] en el campo [!UICONTROL Source file].</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File name]</td> 
   <td>Introduzca un nombre para el archivo convertido. Este campo está disponible si ha seleccionado [!UICONTROL Map] en el campo [!UICONTROL Source file].</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL I want to]</td> 
   <td>Seleccione si desea mantener la relación altura-anchura o cambiar las dimensiones a una altura y anchura especificadas.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL According to]</td> 
   <td> <p>Seleccione cómo desea que el módulo determine el nuevo tamaño de la imagen. Este campo aparece si ha seleccionado mantener la relación altura-anchura en el campo Deseo. Aparecerán otros campos en función de la selección de este campo.</p> 
    <ul> 
     <li> <p>[!UICONTROL Maximum width]</p> <p>Reduce una imagen al ancho especificado. La altura se calcula automáticamente.</p> </li> 
     <li> <p>[!UICONTROL Maximum height]</p> <p>Reduce una imagen a la altura especificada. La anchura se calcula automáticamente.</p> </li> 
     <li> <p>[!UICONTROL Maximum height or width]</p> <p>Reduce una imagen de forma que su altura y anchura no superen los valores especificados. Debido a que esta opción mantiene la relación altura-anchura, una de las dimensiones puede ser más pequeña de lo especificado. Por ejemplo, si la altura y la anchura se especifican como 40, una imagen de 400 x 300 se reducirá a 40 x 30.</p> </li> 
     <li> <p>[!UICONTROL Minimum width]</p> <p>Amplía una imagen a la anchura especificada. La altura se calcula automáticamente.</p> </li> 
     <li> <p>[!UICONTROL Minimum height]</p> <p>Aumenta el tamaño de una imagen hasta la altura especificada. La anchura se calcula automáticamente.</p> </li> 
     <li> <p>[!UICONTROL Minimum height or width]</p> <p>Amplía una imagen de forma que su altura y anchura no sean menores que los valores especificados. Debido a que esta opción mantiene la relación altura-anchura, una de las dimensiones puede ser más grande de lo especificado. Por ejemplo, si la altura y la anchura se especifican como 300, una imagen de 40x30 se ampliará a 400X300.</p> </li> 
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
 </tbody> 
</table>

### [!UICONTROL Convert a format]

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
   <td> <p>Seleccione el origen de la imagen que desea convertir. Puede seleccionar la salida de un módulo anterior o asignar el archivo de datos y el nombre de archivo. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data]</td> 
   <td>Asigne el archivo que desea convertir. Este campo está disponible si ha seleccionado [!UICONTROL Map] en el campo [!UICONTROL Source file].</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File name]</td> 
   <td>Introduzca un nombre para el archivo convertido. Este campo está disponible si ha seleccionado [!UICONTROL Map] en el campo [!UICONTROL Source file].</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output format]</td> 
   <td>Seleccione el formato en el que desea que el módulo convierta el archivo de origen. </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Extract metadata]

Este módulo transformador devuelve información básica sobre un módulo.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Seleccione el origen de la imagen que desea convertir. Puede seleccionar la salida de un módulo anterior o asignar el archivo de datos y el nombre de archivo. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data]</td> 
   <td>Asigne el archivo que desea convertir. Este campo está disponible si seleccionó Mapa en el campo [!UICONTROL Source file].</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File name]</td> 
   <td>Introduzca un nombre para el archivo convertido. Este campo está disponible si seleccionó Mapa en el campo [!UICONTROL Source file].</td> 
  </tr> 
 </tbody> 
</table>

## Posibles problemas

### La acción ha finalizado con un error

Existen tres casos en los que una acción puede finalizar con un error:

* Los datos recibidos no tenían el formato JPG/GIF/PNG/BMP en el que se han recibido los datos
* Se ha superado el límite máximo de anchura y altura al cambiar las dimensiones de la imagen. El tamaño de la imagen no debe superar los 3840 píxeles de anchura y los 2160 píxeles de altura
* Se ha superado el tamaño máximo permitido de una imagen al cambiar las dimensiones o el formato de la imagen.
