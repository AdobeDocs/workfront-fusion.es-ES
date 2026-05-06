---
title: Módulos de Adobe Firefly
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan Adobe Firefly Lightroom, así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 3b29ba3d-a769-4e97-b2c2-0b4eeed5b029
source-git-commit: 965cb643039be36eb3608cd801439a6a055974e4
workflow-type: tm+mt
source-wordcount: '1430'
ht-degree: 17%

---

# Módulos de Adobe Firefly Lightroom

<!--add to tocs-->

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan Adobe Firefly Lightroom, así como conectarlo a varias aplicaciones y servicios de terceros.

Si necesita instrucciones sobre cómo crear un escenario, vea los artículos en [Crear un escenario: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

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

Antes de poder utilizar el conector de Lightroom de Adobe Firefly, debe asegurarse de que se cumplen los siguientes requisitos previos:

* Debe tener una cuenta activa de Adobe Firefly Lightroom.

## Creación de una conexión con Adobe Firefly Lightroom

Para crear una conexión para los módulos Lightroom de Adobe Firefly:

1. En cualquier módulo, haga clic en **[!UICONTROL Agregar]** junto al cuadro Conexión.

1. Rellene los campos siguientes:

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">Nombre de la conexión</td>
        <td>
          <p>Introduzca un nombre para esta conexión.</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">Entorno</td>
        <td>Seleccione si desea conectarse a un entorno de producción o de no producción.</td>
        </tr>
        <tr>
        <td role="rowheader">Tipo</td>
        <td>Seleccione si desea conectarse a una cuenta de servicio o a una personal.</td>
        </tr>
        <tr>
        <td role="rowheader">ID de cliente</td>
        <td>Introduzca su ID de cliente de Adobe. Esto se puede encontrar en la sección Detalles de credenciales de Adobe Developer Console.</td>
        </tr>
        <tr>
        <td role="rowheader">Secreto de cliente</td>
        <td>Escriba el Secreto de cliente de Adobe. Esto se puede encontrar en la sección Detalles de credenciales de Adobe Developer Console.</td>
        </tr>
      </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.


## Módulos Lightroom de Adobe Firefly y sus campos

Al configurar los módulos Lightroom de Adobe Firefly, Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden mostrarse campos de Adobe Firefly Lightroom adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, consulte [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Añadir XMP a la imagen](#add-xmp-to-image)
* [Aplicar ediciones de Lightroom](#apply-lightroom-edits)
* [Aplicar ajustes preestablecidos de Lightroom](#apply-lightroom-presets)
* [Enderezar automáticamente](#auto-straighten)
* [Tono automático](#auto-tone)


### Añadir XMP a la imagen

Este módulo aplica un ajuste preestablecido de Lightroom basado en XMP a una imagen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe Firefly Lightroom, consulte <a href="#create-a-connection-to-adobe-firefly-lightroom" class="MCXref xref" >Crear una conexión con Adobe Firefly Lightroom</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL de imagen</td> 
   <td>Introduzca o asigne una dirección URL firmada previamente que represente la imagen a la que desee aplicar XMP.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de almacenamiento</td> 
   <td>Seleccione el tipo de almacenamiento en el que se almacena la imagen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Contenido de XMP</td> 
   <td>Introduzca o asigne el texto del contenido de XMP que desea agregar a la imagen. Debe ser una cadena XML.</td> 
  </tr> 
   <tr> 
   <td role="rowheader">Orientación</td> 
    <td>Introduzca o asigne la orientación EXIF que se aplicará a la imagen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Almacenamiento de salida</td> 
    <td>Seleccione dónde desea almacenar el archivo de salida. <p>El almacenamiento interno de Fusion no almacena la imagen fuera del escenario, pero permite que otros módulos del escenario accedan a la imagen.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de salida</td> 
   <td>Seleccione el tipo de archivo para el archivo de salida.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Sobrescribir</td> 
   <td>Seleccione sí si desea permitir que el módulo sobrescriba la salida si ya existe. Esto solo se aplica al almacenamiento en la nube de Adobe.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Calidad</td> 
   <td>Introduzca o asigne la calidad de la imagen de salida. 1 es la calidad más baja y 12 es la más alta. Esto solo se aplica a los archivos JPEG.</td> 
  </tr> 
 </tbody> 
</table>

### Aplicar ediciones de Lightroom

Este módulo aplica una o más ediciones de Lightroom a una imagen. Las ediciones incluyen exposición, contraste, nitidez y saturación.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe Firefly Lightroom, consulte <a href="#create-a-connection-to-adobe-firefly-lightroom" class="MCXref xref" >Crear una conexión con Adobe Firefly Lightroom</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL de imagen</td> 
   <td>Introduzca o asigne una dirección URL firmada previamente que represente la imagen a la que desee aplicar XMP.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de almacenamiento</td> 
   <td>Seleccione el tipo de almacenamiento en el que se almacena la imagen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Editar opciones</td> 
   <td>Defina las opciones de edición que desee aplicar a la imagen.<p>Para obtener más información sobre las opciones, consulte <a href="https://developer.adobe.com/firefly-services/docs/lightroom/api/#operation/applyEdits">Aplicar ediciones de Lightroom</a> en la documentación de la API de Adobe Firefly Lightroom.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Almacenamiento de salida</td> 
    <td>Seleccione dónde desea almacenar el archivo de salida. <p>El almacenamiento interno de Fusion no almacena la imagen fuera del escenario, pero permite que otros módulos del escenario accedan a la imagen.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de salida</td> 
   <td>Seleccione el tipo de archivo para el archivo de salida.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Sobrescribir</td> 
   <td>Seleccione sí si desea permitir que el módulo sobrescriba la salida si ya existe. Esto solo se aplica al almacenamiento en la nube de Adobe.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Calidad</td> 
   <td>Introduzca o asigne la calidad de la imagen de salida. 1 es la calidad más baja y 12 es la más alta. Esto solo se aplica a los archivos JPEG.</td> 
  </tr> 
 </tbody> 
</table>

### Aplicar ajustes preestablecidos de Lightroom

Este módulo aplica uno o más ajustes preestablecidos de XMP Lightroom a la imagen determinada, utilizando los archivos de ajustes preestablecidos de XMP dados.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe Firefly Lightroom, consulte <a href="#create-a-connection-to-adobe-firefly-lightroom" class="MCXref xref" >Crear una conexión con Adobe Firefly Lightroom</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL de imagen</td> 
   <td>Introduzca o asigne una dirección URL firmada previamente que represente la imagen a la que desee aplicar XMP.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de almacenamiento</td> 
   <td>Seleccione el tipo de almacenamiento en el que se almacena la imagen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Ajustes preestablecidos</td> 
   <td>Para cada ajuste preestablecido que desee aplicar, haga clic en <b>Agregar elemento</b>, escriba la dirección URL del ajuste preestablecido y seleccione su tipo de almacenamiento.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Almacenamiento de salida</td> 
    <td>Seleccione dónde desea almacenar el archivo de salida. <p>El almacenamiento interno de Fusion no almacena la imagen fuera del escenario, pero permite que otros módulos del escenario accedan a la imagen.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de salida</td> 
   <td>Seleccione el tipo de archivo para el archivo de salida.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Sobrescribir</td> 
   <td>Seleccione sí si desea permitir que el módulo sobrescriba la salida si ya existe. Esto solo se aplica al almacenamiento en la nube de Adobe.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Calidad</td> 
   <td>Introduzca o asigne la calidad de la imagen de salida. 1 es la calidad más baja y 12 es la más alta. Esto solo se aplica a los archivos JPEG.</td> 
  </tr> 
 </tbody> 
</table>

### Enderezar automáticamente

Este módulo endereza automáticamente una imagen aplicando la transformación Auto Upright.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe Firefly Lightroom, consulte <a href="#create-a-connection-to-adobe-firefly-lightroom" class="MCXref xref" >Crear una conexión con Adobe Firefly Lightroom</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL de imagen</td> 
   <td>Introduzca o asigne una dirección URL firmada previamente que represente la imagen a la que desee aplicar XMP.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de almacenamiento</td> 
   <td>Seleccione el tipo de almacenamiento en el que se almacena la imagen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Modo vertical</td> 
   <td>Seleccione el tipo de modo vertical que desee utilizar. Si no define un valor, se proporcionará automáticamente un modo adecuado.</td> 
  </tr> 
   <tr> 
   <td role="rowheader">Restringir recorte</td> 
   <td>Seleccione si la imagen enderezada debe recortarse para eliminar todos los bordes en blanco.</td> 
  </tr> 
 <tr> 
   <td role="rowheader">Almacenamiento de salida</td> 
    <td>Seleccione dónde desea almacenar el archivo de salida. <p>El almacenamiento interno de Fusion no almacena la imagen fuera del escenario, pero permite que otros módulos del escenario accedan a la imagen.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de salida</td> 
   <td>Seleccione el tipo de archivo para el archivo de salida.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Sobrescribir</td> 
   <td>Seleccione sí si desea permitir que el módulo sobrescriba la salida si ya existe. Esto solo se aplica al almacenamiento en la nube de Adobe.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Calidad</td> 
   <td>Introduzca o asigne la calidad de la imagen de salida. 1 es la calidad más baja y 12 es la más alta. Esto solo se aplica a los archivos JPEG.</td> 
  </tr> 
 </tbody> 
</table>


### Tono automático

Este módulo corrige automáticamente la exposición, el contraste, la nitidez y la saturación de una imagen.



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe Firefly Lightroom, consulte <a href="#create-a-connection-to-adobe-firefly-lightroom" class="MCXref xref" >Crear una conexión con Adobe Firefly Lightroom</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL de imagen</td> 
   <td>Introduzca o asigne una dirección URL firmada previamente que represente la imagen a la que desee aplicar XMP.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de almacenamiento</td> 
   <td>Seleccione el tipo de almacenamiento en el que se almacena la imagen.</td> 
  </tr> 
  </tr> 
 <tr> 
   <td role="rowheader">Almacenamiento de salida</td> 
    <td>Seleccione dónde desea almacenar el archivo de salida. <p>El almacenamiento interno de Fusion no almacena la imagen fuera del escenario, pero permite que otros módulos del escenario accedan a la imagen.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de salida</td> 
   <td>Seleccione el tipo de archivo para el archivo de salida.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Sobrescribir</td> 
   <td>Seleccione sí si desea permitir que el módulo sobrescriba la salida si ya existe. Esto solo se aplica al almacenamiento en la nube de Adobe.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Calidad</td> 
   <td>Introduzca o asigne la calidad de la imagen de salida. 1 es la calidad más baja y 12 es la más alta. Esto solo se aplica a los archivos JPEG.</td> 
  </tr> 
 </tbody> 
</table>


