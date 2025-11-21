---
title: Módulos de Adobe Substance
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan  [!DNL Adobe Substance], así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
source-git-commit: 2e44c89d487100b3245b40f6927185a0ff12ef2f
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 27%

---

# Módulos de [!DNL Adobe Substance]

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!DNL Adobe Substance], así como conectarlo a varias aplicaciones y servicios de terceros.

Si necesita instrucciones sobre cómo crear un escenario, vea los artículos en [Crear un escenario: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Paquete de Adobe Workfront</td> 
   <td> <p>Cualquier paquete de flujo de trabajo de Adobe Workfront y cualquier paquete de integración y automatización de Adobe Workfront</p><p>Workfront Ultimate</p><p>Paquetes Workfront Prime y Select, con una compra adicional de Workfront Fusion.</p> </td> 
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
   <p>Si su organización tiene un paquete Select o Prime Workfront que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Antes de poder usar el conector de [!DNL Adobe Substance], debe asegurarse de que se cumplen los siguientes requisitos previos:

* Debe tener una cuenta de [!DNL Adobe Substance] activa.



## Módulos de [!DNL Adobe Substance] y sus campos

Al configurar módulos de [!DNL Adobe Substance], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL Adobe Substance] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. Un asterisco junto al nombre del campo en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, consulte [Asignar información de un módulo a otro en](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Compuestos](#composites)
* [Escenas](#scenes)
* [Espacios](#spaces)

### Compuestos

#### Generar compuesto de objeto 3D

Este módulo de acción genera contenido para un compuesto 3D que incluye el recurso a pantalla completa seleccionado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Adobe Substance] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Otros campos</td> 
   <td>Configure otros campos como desee. Para obtener detalles sobre los campos, consulte la <a href="https://s3d.adobe.io/docs#/operations/v1/composites/compose">documentación de la API de Adobe Substance</a>.</td> 
  </tr> 
<!--  <tr> 
   <td role="rowheader">Camera name</td> 
   <td>Enter or map the name of an existing camera that has been previously defined in the source 3D file.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Content class</td> 
   <td>Select whether you want the composite to have the style of art or of a photo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Enable ground plane</td> 
   <td>Enable this to enable the auto-generated ground plane under the hero asset. This is useful if the 3D scene contains only a hero asset, without additional elements.</td> 
  </tr> -->
 </tbody> 
</table>

### Escenas

* [Conversión de archivos 3D](#convert-3d-files)
* [Crear escena 3D](#create-3d-scene)
* [Describir escena 3D](#describe-3d-scene)
* [Procesar objeto 3D](#render-3d-object)
* [Procesar objeto 3D (versión básica)](#render-3d-object-basic-version)

#### Conversión de archivos 3D

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Adobe Substance] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Formato</td> 
   <td>Seleccione el formato en el que está convirtiendo el archivo.</td> 
  </tr> 
<tr> 
   <td role="rowheader">Punto de entrada del modelo</td> 
   <td>La conversión generalmente toma el primer archivo que se considera un modelo 3D válido. Defina este punto de entrada para desambiguar cuando haya varias opciones.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Fuentes</td> 
   <td>Para cada archivo que desee convertir, haga clic en <b> Agregar elemento</b> e introduzca la información del archivo.</td> 
  </tr> 
 </tbody> 
</table>

#### Crear escena 3D

Este módulo de acción crea una escena con los recursos especificados.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Adobe Substance] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
   <td role="rowheader">Codificación</td> 
   <td>Seleccione el tipo de fichero de la escena.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre de base de archivo</td> 
   <td>Introduzca o asigne un nombre para el archivo de salida.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Otros campos</td> 
   <td>Configure otros campos como desee. Para obtener detalles sobre los campos, consulte la <a href="https://s3d.adobe.io/docs#/operations/v1/scenes/assemble">documentación de la API de Adobe Substance</a>.</td> 
  </tr> 
   <tr> 
   <td role="rowheader">Fuentes</td> 
   <td>Para cada archivo que desee usar, haga clic en <b> Agregar elemento</b> e introduzca la información del archivo.</td> 
  </tr> 
 </tbody> 
</table>

#### Describir escena 3D

Este módulo de acción recupera información sobre el contenido de escenas 3D.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Adobe Substance] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
   <td role="rowheader">Archivo de escena</td> 
   <td>Introduzca o asigne la ruta al fichero de escena que desee describir.</td> 
  </tr> 
   <tr> 
   <td role="rowheader">Fuentes</td> 
   <td>Para cada archivo que desee describir, haga clic en <b> Agregar elemento</b> e introduzca la información del archivo.</td> 
  </tr> 
 </tbody> 
</table>

#### Procesar objeto 3D

Este módulo de acción procesa una imagen de una escena.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Adobe Substance] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
   <td role="rowheader">Otros campos</td> 
   <td>Configure otros campos como desee. Para obtener detalles sobre los campos, consulte la <a href="https://s3d.adobe.io/docs#/operations/v1/scenes/render">documentación de la API de Adobe Substance</a>.</td> 
  </tr> 
   <tr> 
   <td role="rowheader">Fuentes</td> 
   <td>Para cada archivo que desee usar, haga clic en <b> Agregar elemento</b> e introduzca la información del archivo.</td> 
  </tr> 
 </tbody> 
</table>

#### Procesar objeto 3D (versión básica)

Este módulo de acción procesa una imagen de una escena, pero tiene menos opciones que el módulo de objeto Procesar 3D.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Adobe Substance] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
   <td role="rowheader">Otros campos</td> 
   <td>Configure otros campos como desee. Para obtener detalles sobre los campos, consulte la <a href="https://s3d.adobe.io/docs#/operations/v1/scenes/render-basic">documentación de la API de Adobe Substance</a>.</td> 
  </tr> 
   <tr> 
   <td role="rowheader">Fuentes</td> 
   <td>Para cada archivo que desee usar, haga clic en <b> Agregar elemento</b> e introduzca la información del archivo.</td> 
  </tr> 
 </tbody> 
</table>

### Espacios

#### Crear espacio

Este módulo de acción le permite cargar y almacenar archivos temporalmente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Adobe Substance] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
   <td role="rowheader">Nombre del archivo</td> 
   <td>Introduzca o asigne el nombre del archivo que se está cargando.</td> 
  </tr> 
   <tr> 
   <td role="rowheader">Datos de archivo</td> 
   <td>Introduzca o asigne los datos binarios del archivo.</td> 
  </tr> 
   <tr> 
   <td role="rowheader">Nombre</td> 
   <td>Introduzca o asigne un nombre para el valor del formulario de varias partes.</td> 
  </tr> 
 </tbody> 
</table>
