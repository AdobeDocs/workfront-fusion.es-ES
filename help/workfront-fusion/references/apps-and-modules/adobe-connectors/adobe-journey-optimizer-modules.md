---
title: Módulos de Adobe Journey Optimizer
description: En un escenario de  [!DNL Adobe Workfront Fusion] , puede automatizar los flujos de trabajo que utilizan  [!DNL Adobe Journey Optimizer], así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: 1d0ccf4d-9f06-4210-86ec-7da7970f6a47
source-git-commit: 4f97980dce7c8df47ab73d51537d4700ac34dedf
workflow-type: tm+mt
source-wordcount: '3704'
ht-degree: 97%

---

# Módulos de [!DNL Adobe Journey Optimizer]

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!DNL Adobe Journey Optimizer], así como conectarlo a varias aplicaciones y servicios de terceros. Los módulos [!DNL Adobe Journey Optimizer] le permiten crear, leer, actualizar o eliminar registros, o realizar una llamada de API personalizada a la API de [!DNL Adobe Journey Optimizer].


Si necesita instrucciones sobre cómo crear un escenario, vea los artículos en [Crear un escenario: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] plan*</td>
      <td>
        <p>[!UICONTROL Pro] o superior</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] licencia*</td>
      <td>
        <p>[!UICONTROL Plan], [!UICONTROL Work]</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront Fusion] licencia**</td>
      <td>
   <p>Requisito de licencia actual: no se requiere ninguna licencia de [!DNL Workfront Fusion].</p>
   <p>O</p>
   <p>Requisito de licencia heredado: [!UICONTROL [!DNL Workfront Fusion] for Work Automation and Integration] </p>
   </td>
    </tr>
    <tr>
      <td role="rowheader">Producto</td>
      <td>
   <p>Requisito de producto actual: si tiene el plan [!UICONTROL Select] o [!UICONTROL Prime] [!DNL Adobe Workfront] su organización debe adquirir [!DNL Adobe Workfront Fusion] así como [!DNL Adobe Workfront] para utilizar la funcionalidad descrita en este artículo. [!DNL Workfront Fusion] está incluido en el plan [!DNL Workfront] de [!UICONTROL Ultimate].</p>
   <p>O</p>
   <p>Requisito de productos heredados: su organización debe comprar [!DNL Adobe Workfront Fusion] y [!DNL Adobe Workfront] para utilizar la funcionalidad descrita en este artículo.</p>
   </td>
    </tr>
  </tbody>
</table>


Para saber qué plan, tipo de licencia o acceso tiene, póngase en contacto con el administrador de [!DNL Workfront].

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Antes de poder usar el conector de [!DNL Adobe Journey Optimizer], debe asegurarse de que se cumplen los siguientes requisitos previos:

* Debe tener una cuenta de [!DNL Adobe Journey Optimizer] activa.

## Información de API de Adobe Journey Optimizer

El conector de Adobe Journey Optimizer utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL básica</td> 
   <td>{{connection.url}}</td> 
  </tr>
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.7.11</td> 
  </tr>
 </tbody> 
 </table>

## Creación de una conexión con Adobe Journey Optimizer

Puede crear una conexión en cualquier módulo de Adobe Journey Optimizer.

1. En cualquier módulo, haga clic en **[!UICONTROL Agregar]** junto al cuadro Conexión.

1. Rellene los campos siguientes:

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>Introduzca un nombre para esta conexión.</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>Seleccione si desea conectarse a un entorno de producción o de no producción.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>Seleccione si desea conectarse a una cuenta de servicio o a una personal.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Introduzca el [!UICONTROL Adobe] [!UICONTROL Client ID]. Esto se puede encontrar en la sección de detalles de [!UICONTROL Credentials] del [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Escriba su [!UICONTROL Client Secret] de [!DNL Adobe]. Esto se puede encontrar en la sección de detalles de [!UICONTROL Credentials] del [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Organization ID]</td>
        <td>Escriba su [!UICONTROL Organization ID] de [!DNL Adobe]. Esto se puede encontrar en la sección de detalles de [!UICONTROL Credentials] del [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Sandbox Name]</td>
        <td>Introduzca el nombre de la zona protegida que utilizará esta conexión.</td>
        </tr>
      </tbody>
    </table>



   <!--Markdown 0032 placeholder-->


## Módulos de [!DNL Adobe Journey Optimizer] y sus campos

Al configurar módulos de [!DNL Adobe Journey Optimizer], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Adobe Journey Optimizer] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Administración de la configuración](#configuration-management)
* [Administración de paquetes](#package-management)
* [Administración de registros](#record-management)
* [Administración de mensajes](#message-management)
* [Comprobaciones del estado](#status-checks)
* [Búsquedas](#searches)
* [Otro](#other)




### Administración de la configuración

* [Crear una configuración](#create-a-configuration)
* [Implementar una configuración](#deploy-a-configuration)
* [Actualizar una configuración](#update-a-configuration)
* [Anular la implementación de una configuración](#undeploy-a-configuration)
* [Comprobar si la configuración se puede implementar](#check-if-configuration-can-be-deployed)
* [Eliminar una configuración](#delete-a-configuration)
* [Obtener una configuración](#get-a-configuration)

#### Crear una configuración

Este módulo de acción crea un punto final de límite o una configuración de restricción.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión con [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select configuration type]</td> 
   <td>Seleccione esta opción si desea crear una configuración de límite o una configuración de restricción.<ul><li><p><b>Límite</b></p>Continúe con <a href="#capping-fields" class="MCXref xref" >Campos de límite</a>.</li><li><p><b>Restricción</b></p>Continuar a <a href="#throttling-fields" class="MCXref xref" >Campos de restricción</a>.</li></ul></td> 
  </tr> 
   </tbody> 
</table>

##### Campos de límite

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Introduzca o asigne la dirección URL del punto final que desea configurar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL IMS Org ID]</td> 
   <td>Introduzca o asigne el ID de Adobe IMS de la organización.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Methods]</td> 
   <td>Seleccione los métodos que desea utilizar en esta configuración.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Service]</td> 
   <td>Seleccione si está utilizando una acción o una fuente de datos para esta configuración.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum HTTP connections]</td> 
   <td>Introduzca o asigne el número máximo de conexiones simultáneas a este punto final.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum calls]</td> 
   <td>Introduzca o asigne el número máximo de llamadas que se realizarán en el periodo especificado en el campo Periodo de tiempo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Time period (milliseconds)]</td> 
   <td>Introduzca o asigne el número de milisegundos relacionados con el campo Máximo de llamadas.</td> 
  </tr> 
 </tbody> 
</table>

##### Campos de restricción

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>Escriba o asigne un nombre para esta configuración.</td> 
<tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Escriba o asigne una descripción para esta configuración.</td> 
  </tr> 
<tr> 
   <td role="rowheader">[!UICONTROL URL pattern]</td> 
   <td>Introduzca o asigne la URL del punto final que desea restringir.</td> 
  </tr> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Methods]</td> 
   <td>Seleccione los métodos que desea utilizar en esta configuración.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Max throughput]</td> 
   <td>Seleccione si está utilizando una acción o una fuente de datos para esta configuración.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum HTTP connections]</td> 
   <td>Introduzca o asigne el número máximo de conexiones simultáneas a este punto final.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum calls]</td> 
   <td>Especifique o asigne el rendimiento máximo que desea para este punto final. Este valor debe estar entre 200 y 5000.</td> 
  </tr> 
 </tbody> 
</table>

#### Implementar una configuración

Este módulo de acción implementa la configuración de límite o restricción especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión con [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select configuration type]</td> 
   <td>Seleccione esta opción si desea implementar una configuración de límite o de restricción.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Configuration ID]</td> 
   <td>Introduzca o asigne el ID de la configuración que desea implementar.</td> 
  </tr> 
 </tbody> 
</table>

#### Actualizar una configuración

Este módulo de acción actualiza la configuración de límite o de restricción especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión con [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select configuration type]</td> 
   <td>Seleccione si va a actualizar una configuración de límite o de restricción.<ul><li><p><b>Límite</b></p>Para ver los campos, consulte <a href="#capping-fields" class="MCXref xref" >Campos de límite</a> en la sección Crear una configuración de este artículo.</li><li><p><b>Restricción</b></p>Para ver los campos, consulte <a href="#throttling-fields" class="MCXref xref" >Campos de restricción</a> en la sección Crear una configuración de este artículo.</li></ul></td> 
  </tr> 
  </tbody> 
</table>

#### Anular la implementación de una configuración

Este módulo de acción anula la implementación de una configuración de límite o de restricción. El estado de configuración vuelve a cambiarse al estado anterior a la implementación (`created` o `updated`).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión con [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select configuration type]</td> 
   <td>Seleccione si va a anular la implementación de una configuración de límite o de restricción.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Configuration ID]</td> 
   <td>Introduzca o asigne el ID de la configuración para la que desea anular la implementación.</td> 
  </tr> 
 </tbody> 
</table>

#### Comprobar si la configuración se puede implementar

Este módulo de acción verifica si se puede implementar una configuración de restricción o de límite.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión con [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select configuration type]</td> 
   <td>Seleccione si está comprobando una configuración de límite o de restricción.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Configuration ID]</td> 
   <td>Introduzca o asigne el ID de la configuración que desea comprobar.</td> 
  </tr> 
 </tbody> 
</table>

#### Eliminar una configuración

Este módulo de acción elimina un punto final de límite o una configuración de restricción.

Si la configuración se ha implementado, debe anular su implementación para poder eliminarla.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión con [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select configuration type]</td> 
   <td>Seleccione si desea eliminar una configuración de límite o de restricción.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Configuration ID]</td> 
   <td>Introduzca o asigne el ID de la configuración que desea eliminar.</td> 
  </tr> 
 </tbody> 
</table>

#### Obtener una configuración

Este módulo de acción devuelve la configuración de límite o restricción identificada por el ID especificado. Se devuelve la definición más reciente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión con [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select configuration type]</td> 
   <td>Seleccione si va a recuperar una configuración de límite o de restricción.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Configuration ID]</td> 
   <td>Introduzca o asigne el ID de la configuración que desea recuperar.</td> 
  </tr> 
 </tbody> 
</table>




### Administración de paquetes

* [Crear un paquete](#create-a-package)
* [Actualización de un paquete](#update-a-package)
* [Eliminación de un paquete](#delete-a-package)
* [Búsqueda de un paquete](#look-up-a-package)
* [Importación de un paquete](#import-a-package)
* [Publicación de un paquete](#publish-a-package)
* [Envío de una importación](#submit-an-import)



#### Crear un paquete

Este módulo de acción crea un paquete de varios artefactos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión con [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>Introduzca o asigne un nombre para el paquete.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Introduzca o asigne una descripción del paquete.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expiration date]</td> 
   <td>Introduzca o asigne la marca de tiempo que define la fecha de caducidad del paquete. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Package type]</td> 
   <td>Seleccione el tipo de paquete que desea crear.<ul><li><p><b>Completo</b></p>El paquete incluirá todos los artefactos.</p></li><li><p><b>Parcial</b></p><p>El paquete incluirá solo los artefactos que añada. </p></li><ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Artifacts]</td> 
   <td>Si va a crear un paquete parcial, para cada artefacto que desee añadir, haga clic en <b>Añadir artefacto</b> y especifique el identificador, el tipo y el título del artefacto. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Sandbox]</td> 
   <td>Introduzca o asigne el nombre y el ID de organización de IMS de la zona protegida que contiene los elementos que desea que contenga el paquete.</td> 
  </tr> 
 </tbody> 
</table>

#### Actualización de un paquete

Este módulo de acción añade o elimina artefactos de un paquete, o actualiza los metadatos del paquete.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe Journey Optimizer]&rbrace;, vea <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión a [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select action]</td> 
   <td>Seleccione la acción que desee realizar.<ul><li><p><b>Añadir artefacto</b></p><p>Para cada artefacto que desee añadir, haga clic en <b>Añadir artefacto</b>, especifique el identificador, el tipo y el título del artefacto y, a continuación, escriba o asigne la fecha de caducidad del paquete. </p></li><li><p><b>Eliminación del artefacto</b></p><p>Para cada artefacto que desee eliminar, haga clic en <b>Añadir artefacto</b> y especifique el identificador, el tipo y el título del artefacto. </p></li><li><p><b>Actualización de metadatos</b></p><p>Introduzca nuevos valores para el nombre, la descripción o el nombre de la zona protegida de origen o el ID de organización de IMS.</p></li></ul></td> 
  </tr> 
 </tbody> 
</table>

#### Eliminación de un paquete

Este módulo de acción elimina un paquete de varios artefactos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe Journey Optimizer], vea <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión a [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Package ID]</td> 
   <td>Introduzca o asigne el ID del paquete que desea eliminar.</td> 
  </tr> 
 </tbody> 
</table>

#### Búsqueda de un paquete

Este módulo de acción recupera los detalles del paquete especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe Journey Optimizer], vea <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión a [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Package ID]</td> 
   <td>Introduzca o asigne el ID del paquete cuyos detalles desea devolver.</td> 
  </tr> 
 </tbody> 
</table>

#### Importación de un paquete

Este módulo de acción recupera los objetos en conflicto de la zona protegida de destino especificada. Los objetos en conflicto representan objetos similares que ya están presentes en la zona protegida de destino.

Debe publicar un paquete para poder importarlo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe Journey Optimizer], vea <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión a [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Package ID]</td> 
   <td>Introduzca o asigne el ID del paquete que desea importar.</td> 
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL Target sandbox]</td> 
   <td>Introduzca o asigne el nombre de la zona protegida en la que desea importar el paquete.</td> 
  </tr> 
 </tbody> 
</table>

#### Publicación de un paquete

Debe publicar un paquete para poder importarlo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe Journey Optimizer], vea <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión a [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Package ID]</td> 
   <td>Introduzca o asigne el ID del paquete que desea publicar.</td> 
  </tr> 
 </tbody> 
</table>

#### Envío de una importación

Este módulo de acción envía una importación para un paquete después de haber revisado los conflictos y proporcionado las sustituciones. El resultado se proporciona como carga útil, que inicia el trabajo de importación para la zona protegida de destino según se especifica en la carga útil.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe Journey Optimizer], vea <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión a [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Package ID]</td> 
   <td>Introduzca o asigne el ID del paquete que desea publicar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>Introduzca o asigne un nombre para el trabajo de importación.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Introduzca o asigne una descripción del trabajo de importación</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL (Destination sandbox) Name]</td> 
   <td>Introduzca o asigne el nombre de la zona protegida a la que está enviando la importación.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL (Destination sandbox) IMS Org ID]</td> 
   <td>Introduzca o asigne el ID de organización de Adobe IMS para la zona protegida a la que envía la importación.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL (Source sandbox) ID]</td> 
   <td>Introduzca o asigne el ID de la zona protegida que contiene el paquete que desea publicar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL (Source sandbox) Type]</td> 
   <td></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL (Source sandbox) Link]</td> 
   <td>Introduzca o asigne el vínculo del paquete que desea publicar.</td> 
  </tr> 
 </tbody> 
</table>


<!--

### Artifact management

* [Copy artifacts synchronously](#copy-artifacts-synchronously)
* [Export artifacts asynchronously](#export-artifacts-asynchronously)
* [Import artifacts asynchronously](#import-artifacts-asynchronously)

#### Copy artifacts synchronously

This action module copies artifacts from a source sandbox into a destination sandbox.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>For instructions on creating a connection to [!DNL Adobe Journey Optimizer], see <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Create a connection to [!DNL Adobe Journey Optimizer]</a> in this article.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>Enter or map a name for the new file</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Enter or map a description for the new file</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Visibility]</td> 
   <td></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination sandbox]</td> 
   <td></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Artifacts]</td> 
   <td>For each artifact you want to copy, click <b>Add artifact</b> and continue to <a href="#artifact-fields" class="MCXref xref" >Artifact fields</a>.</td> 
  </tr> 
 </tbody> 
</table>

##### Artifact fields

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Enter or map the ID of the artifact.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>Enter or map the artifact type, such as <code>REGISTRY_SCHEMA<code> or <code>JOURNEY</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Version]</td> 
   <td>Enter or map the visibility of the artifact. This applies only to Registry objects.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Visibility]</td> 
   <td>Enter or map the visibility (tenant or global). This applies only to Registry objects.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Found]</td> 
   <td>Select <b>Yes</b> if this item was found using a GET operation.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tasks]</td> 
   <td>For each task you want to add, click <b>Add task</b> and fill in the following:
   <ul>
   <li><p><b>Method</b></p></li>
   <li><p><b>Action</b></p></li>
   <li><p><b>Using</b></p></li>
   <li><p><b>With</b></p></li>
   </ul>
   </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Messages]</td> 
   <td>For each task you want to add, click <b>Add message</b> and fill in the following:
   <ul>
   <li><p><b>Status</b></p><p>Enter or map the status that this message represents, such as <code>ERROR</code>.</li>
   <li><p><b>Attempt</b></p><p>Enter or map the attempt number related to this message. This may be useful if different attempts produce different messages.</p></li>
   <li><p><b>Message</b></p><p>Enter or map the text of the message.</li>
   <li><p><b>Object</b></p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>

#### Export Artifacts asynchronously

This action module exports artifacts from the specified sandbox.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>For instructions on creating a connection to [!DNL Adobe Journey Optimizer], see <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Create a connection to [!DNL Adobe Journey Optimizer]</a> in this article.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>Enter or map a name for the export file</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Enter or map a description for the export file</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Visibility]</td> 
   <td></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Artifacts]</td> 
   <td>For each artifact you want to export, click <b>Add artifact</b> and continue to <a href="#artifact-fields" class="MCXref xref" >Artifact fields</a>.</td> 
  </tr> 
 </tbody> 
</table>

##### Artifact fields

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Enter or map the ID of the artifact.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>Enter or map the artifact type, such as <code>REGISTRY_SCHEMA<code> or <code>JOURNEY</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Version]</td> 
   <td>Enter or map the visibility of the artifact. This applies only to Registry objects.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Visibility]</td> 
   <td>Enter or map the visibility (tenant or global). This applies only to Registry objects.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Found]</td> 
   <td>Select <b>Yes</b> if this item was found using a GET operation.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tasks]</td> 
   <td>For each task you want to add, click <b>Add task</b> and fill in the following:
   <ul>
   <li><p><b>Method</b></p></li>
   <li><p><b>Action</b></p></li>
   <li><p><b>Using</b></p></li>
   <li><p><b>With</b></p></li>
   </ul>
   </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Messages]</td> 
   <td>For each task you want to add, click <b>Add message</b> and fill in the following:
   <ul>
   <li><p><b>Status</b></p><p>Enter or map the status that this message represents, such as <code>ERROR</code>.</li>
   <li><p><b>Attempt</b></p><p>Enter or map the attempt number related to this message. This may be useful if different attempts produce different messages.</p></li>
   <li><p><b>Message</b></p><p>Enter or map the text of the message.</li>
   <li><p><b>Object</b></p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>



#### Import Artifacts asynchronously

This action module imports a snapshot containing artifacts.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>For instructions on creating a connection to [!DNL Adobe Journey Optimizer], see <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Create a connection to [!DNL Adobe Journey Optimizer]</a> in this article.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Snapshot ID]</td> 
   <td>Enter or map the ID of the snapshot you want to import.</td> 
  </tr> 
 </tbody> 
</table>

-->

### Administración de registros

* [Crear un registro](#create-a-record)
* [Actualizar un registro](#update-a-record)
* [Eliminación de un registro](#delete-a-record)
* [Hacer un parche de un registro](#patch-a-record)
* [Obtener un registro](#get-a-record)

#### Crear un registro

Este módulo de acción crea una nueva plantilla de contenido o fragmento de contenido.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión a [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select content type]</td> 
   <td>Seleccione si va a crear una plantilla de contenido o un fragmento de contenido.<ul><li><p><b>Plantilla de contenido</b></p>Continuar a <a href="#template-fields" class="MCXref xref" >Campos de plantilla</a>.</li><li><p><b>Fragmento de contenido</b></p>Continuar a <a href="#fragment-fields" class="MCXref xref" >Campos de fragmento</a>.</li></ul></td> 
  </tr> 
  </tbody> 
</table>

##### Campos de plantilla

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>Escriba o asigne un nombre para esta plantilla de contenido.</td> 
<tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Escriba o asigne una descripción para esta plantilla de contenido.</td> 
  </tr> 
<tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>Seleccione el tipo de plantilla que desea crear. </td> 
  </tr> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channels]</td> 
   <td>Seleccione los canales incluidos en esta plantilla.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content template origin]</td> 
   <td>Seleccione la fuente de esta plantilla.</td>  
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata]</td> 
   <td>Para incluir propiedades personalizadas en la nueva plantilla, seleccione "Añadir metadatos" e introduzca o asigne la clave y el valor de los metadatos. Repita el proceso para cada campo personalizado que desee incluir.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Email HTML]</td> 
   <td>Introduzca o asigne el HTML del correo electrónico incluido en esta plantilla.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Editor context]</td> 
   <td>Para incluir propiedades personalizadas en el correo electrónico, seleccione “Añadir contexto del editor” e introduzca o asigne la clave y el valor del contexto. Repita el proceso para cada campo personalizado que desee incluir.</td> 
  </tr> 
 </tbody> 
</table>

##### Campos de fragmento

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>Introduzca o asigne un nombre para este fragmento de contenido.</td> 
<tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Escriba o asigne una descripción para este fragmento de contenido.</td> 
  </tr> 
<tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>Seleccione el tipo de plantilla que desea crear. </td> 
  </tr> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channels]</td> 
   <td>Seleccione los canales incluidos en esta plantilla.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content fragment origin]</td> 
   <td>Seleccione el origen de este fragmento.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata]</td> 
   <td>Para incluir propiedades personalizadas en la nueva plantilla, seleccione "Añadir metadatos" e introduzca o asigne la clave y el valor de los metadatos. Repita el proceso para cada campo personalizado que desee incluir.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content]</td> 
   <td>Introduzca o asigne el contenido del fragmento.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Editor context]</td> 
   <td>Para incluir propiedades personalizadas en el correo electrónico, seleccione “Añadir contexto del editor” e introduzca o asigne la clave y el valor del contexto. Repita el proceso para cada campo personalizado que desee incluir.</td> 
  </tr> 
 </tbody> 
</table>

#### Actualizar un registro

Este módulo de acción actualiza una plantilla de contenido o un fragmento.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión a [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select content type]</td> 
   <td>Seleccione si va a actualizar una configuración de límite o de restricción.<ul><li><p><b>Plantilla</b></p>Para los campos, consulte <a href="#template-fields" class="MCXref xref" >Campos de plantilla</a> en la sección Crear un registro de este artículo.</li><li><p><b>Fragmento</b></p>Para los campos, consulte <a href="#fragment-fields" class="MCXref xref" >Campos de fragmento</a> en la sección Crear un registro de este artículo.</li></ul></td> 
  </tr> 
  </tbody> 
  </table>

#### Eliminación de un registro

Este módulo de acción elimina una plantilla o un fragmento de contenido.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión a [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select content type]</td> 
   <td>Seleccione si desea eliminar una plantilla de contenido o un fragmento de contenido.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Template/Fragment ID]</td> 
   <td>Introduzca o asigne el ID de la plantilla o el fragmento que desea eliminar.</td> 
  </tr> 
 </tbody> 
</table>

#### Hacer un parche de un registro

Este módulo de acción actualiza un registro con un PATCH con formato de puntero JSON

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión a [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select content type]</td> 
   <td>Seleccione si va a aplicar parches a una plantilla de contenido o a un fragmento de contenido.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Template/Fragment ID]</td> 
   <td>Introduzca o asigne el ID de la plantilla o el fragmento al que desee aplicar el parche.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Payload data]</td> 
   <td>Para añadir un registro a la carga útil de este parche: <ol><li>Haga clic en <b>Añadir un registro</b>.</li><li>Seleccione la operación: Añadir, Quitar o Reemplazar.</li><li>En el campo Ruta, seleccione si desea aplicar un parche al nombre o a la descripción.</li><li> En el campo Desde, introduzca o asigne una cadena que contenga un valor de puntero JSON.</li><li>En el campo Valor, introduzca el valor que desea utilizar en la operación.</li></ol></td> 
  </tr> 
 </tbody> 
</table>

#### Obtener un registro

Este módulo de acción devuelve la plantilla de contenido o el fragmento de contenido identificado por el ID especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión a [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select content type]</td> 
   <td>Seleccione si va a recuperar una plantilla de contenido o un fragmento de contenido.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Template/Fragment ID]</td> 
   <td>Introduzca o asigne el ID de la plantilla o el fragmento que desea recuperar.</td> 
  </tr> 
 </tbody> 
</table>


### Administración de mensajes

* [Activar la ejecución de un mensaje unitario](#trigger-a-unitary-message-execution)
* [Activar un mensaje basado en el público](#trigger-an-audience-based-message)
* [Comprobar el estado de un mensaje basado en audiencias](#check-the-status-for-audience-based-message)



#### Activar la ejecución de un mensaje unitario

 Este módulo de acción activa un mensaje unitario para los destinatarios especificados.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión a [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Request ID]</td> 
   <td>Introduzca o asigne el ID de la solicitud asociada a este mensaje.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Campaign ID]</td> 
   <td>Introduzca o asigne el ID de la campaña asociada con este mensaje.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Recipients]</td> 
   <td>Para cada destinatario que desee recibir este mensaje, haga clic en <b>Añadir destinatario</b> e introduzca lo siguiente:
   <ul>
   <li><p><b>Tipo</b></p>Seleccione <code>aep</code>.</li>
   <li><p><b>Identificador del usuario</b></p>Introduzca o asigne el identificador de perfil de Adobe Experience Platform del destinatario.</li>
   <li><p><b>Área de nombres</b></p>Introduzca o asigne el área de nombres del perfil de Adobe Experience Platform del destinatario.</li>
   <li><p><b>Dirección de correo electrónico</b></p></li>
   <li><p><b>Número de teléfono móvil</b></p></li>
   <li><p><b>Nombre</b></p></li>
   <li><p><b>Apellido</b></p></li>
   <li><p><b>Producto</b></p>Introduzca o asigne el producto asociado a este mensaje. Se utiliza para la sustitución dinámica de variables en el contenido del mensaje.</li>
   </ul></td> 
  </tr> 
 </tbody> 
</table>

#### Activar un mensaje basado en el público

Este módulo de acción activa la ejecución de un mensaje basado en audiencias, según la solicitud y la campaña que especifique.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión a [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Request ID]</td> 
   <td>Introduzca o asigne el ID de la solicitud asociada a este mensaje.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Campaign ID]</td> 
   <td>Introduzca o asigne el ID de la campaña asociada con este mensaje.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Product]</td> 
   <td>Introduzca o asigne el producto asociado a este mensaje. Se utiliza para la sustitución dinámica de variables en el contenido del mensaje.</td> 
  </tr> 
 </tbody> 
</table>

#### Comprobar el estado de los mensajes basados en audiencias

Este módulo de acción comprueba el estado de un mensaje por lotes basado en audiencias.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión con [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message execution ID]</td> 
   <td>Introduzca o asigne el ID de la ejecución del mensaje que desea comprobar.</td> 
  </tr> 
 </tbody> 
</table>

### Comprobaciones del estado

<!--* [Check service health](#check-service-health)-->
* [Comprobación de las dependencias de importación](#check-the-import-dependencies)
* [Comprobación del estado de un trabajo de importación](#check-the-status-of-an-import-job)

<!--

#### Check service health

This action module checks that the service represented by the connection is running.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>For instructions on creating a connection to [!DNL Adobe Journey Optimizer], see <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Create a connection to [!DNL Adobe Journey Optimizer]</a> in this article.</td> 
  </tr> 
 </tbody> 
</table>

-->

#### Comprobación de las dependencias de importación

Este módulo de acción comprueba las dependencias de los artefactos del paquete. Esto le permite comprobar si tiene permisos para importar artefactos del paquete.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe Journey Optimizer], vea <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión a [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Package ID]</td> 
   <td>Introduzca o asigne el ID del paquete para el que desea comprobar los permisos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Target sandbox]</td> 
   <td>Introduzca o asigne el nombre de la zona protegida en la que desea importar el paquete.</td> 
  </tr> 
 </tbody> 
</table>

#### Comprobación del estado de un trabajo de importación

Este módulo de acción comprueba si un trabajo de importación se ha realizado correctamente o no.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión a [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Job ID]</td> 
   <td>Introduzca o asigne el ID del trabajo para el que desea recuperar datos.</td> 
  </tr> 
 </tbody> 
</table>

### Búsquedas

* [Enumerar todos los objetos dependientes](#list-all-dependent-objects)
* [Enumerar configuraciones](#list-configurations)
* [Enumerar trabajos de exportación e importación](#list-export-and-import-jobs)
* [Enumerar paquetes](#list-packages)
* [Enumerar registros](#list-records)

#### Enumerar todos los objetos dependientes

Este módulo de búsqueda enumera todos los objetos dependientes de los objetos del paquete especificado

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión a [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Package objects]</td> 
   <td>Para cada objeto del paquete para el que desee devolver un objeto dependiente, haga clic en <b>Añadir objeto</b> e introduzca el nombre y el tipo del objeto.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Package ID]</td> 
   <td>Introduzca o asigne el ID del paquete para el que desea enumerar los objetos dependientes.</td> 
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL Target sandbox]</td> 
   <td>Introduzca o asigne el nombre de la zona protegida que contiene el paquete para el que desea enumerar los objetos dependientes.</td> 
  </tr> 
 </tbody> 
</table>

#### Enumerar configuraciones

Este módulo de acción enumera todas las configuraciones de límite o restricción.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión con [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select configuration type]</td> 
   <td>Seleccione si desea enumerar las configuraciones de límite o de restricción.</td> 
  </tr> 
 </tbody> 
</table>

#### Enumerar trabajos de exportación e importación

Este módulo de búsqueda enumera los trabajos actuales de exportación e importación. Puede utilizar parámetros de consulta para filtrar la lista.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión a [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start]</td> 
   <td></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned results]</td> 
      <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order by]</td> 
      <td>Seleccione si desea ordenar los resultados por fecha de creación o de modificación.</td>
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL Query parameter]</td> 
   <td>Para cada parámetro de consulta por el que desee filtrar, haga clic en <b>Añadir parámetro de consulta</b>, seleccione el campo y el operador e introduzca el valor de campo para el filtro.</td> 
  </tr> 
 </tbody> 
</table>



#### Enumerar paquetes

Este módulo de búsqueda enumera todos los paquetes de la organización. Puede utilizar parámetros de consulta para filtrar la lista.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión a [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start]</td> 
   <td></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned results]</td> 
      <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order by]</td> 
      <td>Seleccione si desea ordenar los resultados por fecha de creación o de modificación.</td>
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL Query parameter]</td> 
   <td>Para cada parámetro de consulta por el que desee filtrar, haga clic en <b>Añadir parámetro de consulta</b>, seleccione el campo y el operador e introduzca el valor de campo para el filtro.</td> 
  </tr> 
 </tbody> 
</table>

#### Enumerar registros

Este módulo de búsqueda enumera todas las configuraciones de límite o restricción.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión a [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select content type]</td> 
   <td>Seleccione si va a recuperar una plantilla de contenido o un fragmento de contenido.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order by]</td> 
   <td>Introduzca o asigne el nombre del parámetro por el que desea ordenar esta lista. Añada <code>-</code> o <code>+</code> para ordenar de bajada o de subida. Si no se especifica ningún signo, la lista se ordena en sentido de bajada.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start]</td> 
   <td>Este campo se utiliza para la paginación. Introduzca o asigne los criterios de la página siguiente con respecto a la propiedad especificada en el campo Ordenar por.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order by]</td> 
   <td>Introduzca o asigne el nombre del parámetro por el que desea ordenar esta lista. Añada <code>-</code> o <code>+</code> para ordenar de bajada o de subida. Si no se especifica ningún signo, la lista se ordena en sentido de bajada.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter by property]</td> 
   <td>Para cada filtro de propiedad que desee añadir, haga clic en <b>Añadir elemento</b> e introduzca la clave y el valor de la propiedad. Los registros que incluyen el valor especificado para la propiedad se incluyen en la lista.</td> 
  </tr> 
 </tbody> 
</table>


### Otro


#### Realizar una llamada de API personalizada

Este módulo de acción realiza una llamada de API personalizada a la API de Adobe Journey Optimizer.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Para obtener instrucciones sobre la creación de una conexión a [!DNL Adobe Journey Optimizer], consulte <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Crear una conexión a [!DNL Adobe Journey Optimizer]</a> en este artículo.</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p>Introduzca una ruta relativa a la dirección URL base.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
      </td>
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p>
        <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p>
        <p>[!DNL Workfront Fusion] añade automáticamente los encabezados de autorización <code>x-api-key</code> y <code>x-gw-ims-org-id</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Query String]  </td>
      <td>
        <p>Introduzca la cadena de consulta de la solicitud.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Body]</td>
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la instrucción condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>







<!--

* [Check if configuration can be deployed](#check-if-configuration-can-be-deployed)
* [Check service health](#check-service-health)
* [Check the import dependencies](#check-the-import-dependencies)
* [Check the status for audience-based message](#status-for-audience-based-message)
* [Copy artifacts synchronously](#copy-artifacts-synchronously)
* [Create a configuration](#create-a-configuration)
* [Create a package](#create-a-package)
* [Create a record](#create-a-record)
* [Delete a configuration](#delete-a-configuration)
* [Delete a package](#delete-a-package)
* [Delete a record](#delete-a-record)
* [Deploy a configuration](#deploy-a-configuration)
* [Export artifacts asynchronously](#export-artifacts-asynchronously)
* [Get a configuration](#get-a-configuration)
* [Get a record](#get-a-record)
* [Import a package](#import-a-package)
* [Import artifacts asynchronously](#import-artifacts-asynchronously)
* [List all dependent objects](#list-all-dependent-objects)
* [List export and import jobs](#list-import-and-export-jobs)
* [Look up a package](#look-up-a-package)
* [Make a custom API call](#make-a-custom-api-call)
* [Patch a record](#patch-a-record)
* [Publish a package](#publish-a-package)
* [Submit an import](#submit-an-import)
* [Trigger a unitary message execution](#trigger-a-unitary-message-execution)
* [Trigger an audience-based message](#trigger-an-audience-based-message)
* [Undeploy a configuration](#undeploy-a-configuration)
* [Update a configuration](#update-a-configuration)
* [Update a package](#update-a-package)
* [Update a record](#update-a-record)
* [List configurations](#list-configurations)
* [List packages](#list-packages)
* [List records](#list-records)

-->
