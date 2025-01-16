---
title: Módulos SharePoint
description: En un escenario de [!DNL Adobe Workfront Fusion] , puede automatizar los flujos de trabajo que utilizan SharePoint, así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: 1a09aa86-5e0e-4347-b4cf-2b0a95e5b049
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '2271'
ht-degree: 85%

---

# Módulos de [!DNL SharePoint]

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!DNL SharePoint], así como conectarlo a varias aplicaciones y servicios de terceros.

Para obtener instrucciones sobre cómo crear un escenario, vea los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

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
   <p>Requisito de licencia heredado: [!UICONTROL [!DNL Workfront Fusion] para automatización e integración de trabajo </p>
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

## Requisitos previos

Para usar módulos [!DNL SharePoint], debe tener una cuenta de [!DNL SharePoint].

## Información de API de SharePoint

El conector de SharePoint utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL básica</td> 
   <td> https://graph.microsoft.com/v1.0</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> Versión 1.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.14.2</td> 
  </tr>
 </tbody> 
 </table>

## Conectar [!DNL SharePoint] a [!DNL Workfront Fusion] {#connect-sharepoint-to-workfront-fusion}

* [Conectar [!DNL SharePoint] a [!DNL Workfront Fusion] mediante una cuenta de [!DNL Microsoft] ](#connect-sharepoint-to-workfront-fusion-using-a-microsoft-account)
* [Conectar [!DNL SharePoint] a [!DNL Workfront Fusion] mediante ajustes avanzados](#connect-sharepoint-to-workfront-fusion-using-advanced-settings)

### Conectar [!DNL SharePoint] a [!DNL Workfront Fusion] mediante una cuenta de [!DNL Microsoft]

Puede usar su cuenta de [!DNL Microsoft] para crear una conexión con [!DNL SharePoint]. Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Sharepoint] a [!DNL Workfront Fusion], consulte [Crear una conexión con [!DNL Adobe Workfront Fusion] : instrucciones básicas](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

### Conectar [!DNL SharePoint] a [!DNL Workfront Fusion] mediante ajustes avanzados

Para conectar [!DNL SharePoint] con [!DNL Workfront Fusion] sin una cuenta de [!DNL Microsoft], necesita un ID de cliente, un secreto de cliente y un identificador de inquilino.

1. Haga clic en **[!UICONTROL Add]** cerca de la parte superior del cuadro **[!DNL SharePoint]** para abrir el cuadro **[!UICONTROL Create a connection]**.

1. (Opcional) Cambie el valor predeterminado **[!UICONTROL Connection name]**.
1. Haga clic en **[!UICONTROL Show advanced settings]**.
1. Escriba [!DNL SharePoint] **[!UICONTROL Client ID]** y **[!UICONTROL Client Secret]**.

1. Haga clic en **[!UICONTROL Continue]**.
1. En la ventana de inicio de sesión que aparece, introduzca sus credenciales para iniciar sesión en la aplicación si aún no lo ha hecho.
1. (Condicional) Si aparece un botón **[!UICONTROL Allow]**, haga clic en el botón para conectar la aplicación a [!DNL Workfront Fusion].

## Módulos de [!DNL SharePoint] y sus campos

Al configurar módulos de [!DNL SharePoint], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL SharePoint] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Elemento de Drive](#drive-item)
* [Elemento](#item)
* [Lista](#list)
* [Página (Beta)](#page-beta)
* [Sitio](#site)
* [Otro](#other)

### Elemento de Drive

* [Crear un archivo](#create-a-file)
* [Crear una carpeta](#create-a-folder)
* [Obtener un archivo](#get-a-file)
* [Ver elementos de la carpeta](#watch-folder-items)

#### Obtener cambios

Este módulo devuelve los cambios realizados en SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL SharePoint] a [!DNL Workfront Fusion], consulte <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL SharePoint] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>Seleccione cómo desea identificar la ubicación de la carpeta en la que desea recuperar los cambios.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL List ID]</strong> y <strong>[!UICONTROL Folder ID]</strong> en los campos que aparecen.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>Seleccione la ubicación donde desea recuperar los cambios. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Token]</td> 
   <td> </td> 
  </tr>  </tbody> 
</table>

#### Crear una carpeta

Este módulo de acción crea una nueva carpeta en SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL SharePoint] a [!DNL Workfront Fusion], consulte <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL SharePoint] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>Seleccione cómo identificar la ubicación de la carpeta que desea crear.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL List ID]</strong> y <strong>[!UICONTROL Folder ID]</strong> en los campos que aparecen.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>Seleccione la ubicación donde desea crear la carpeta. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder name]</td> 
   <td>Introduzca o asigne un nombre para la nueva carpeta.</td> 
  </tr>
  </tbody> 
</table>

#### Obtener un archivo

Este módulo de acción recupera el archivo SharePoint especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL SharePoint] a [!DNL Workfront Fusion], consulte <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL SharePoint] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>Seleccione cómo identificar la ubicación del archivo que desea obtener.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL List ID]</strong> y <strong>[!UICONTROL File ID]</strong> en los campos que aparecen.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>Seleccione la ubicación del archivo. </p> </li> 
    </ul> </td> 
  </tr> 
</tbody> 
</table>

#### Ver elementos de la carpeta

Este módulo de activación inicia un escenario cuando se actualiza un elemento en una carpeta seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL SharePoint] a [!DNL Workfront Fusion], consulte <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL SharePoint] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>Seleccione cómo identificar la ubicación del archivo que desea obtener.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL List ID]</strong> y <strong>[!UICONTROL folder ID]</strong> en los campos que aparecen.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>Seleccione la ubicación de la carpeta que desea ver. </p> </li> 
    </ul> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Introduzca el número máximo de elementos que [!DNL Workfront Fusion] debe devolver durante un ciclo de ejecución de escenario.</td> 
  <tr>
  </tr>
</tbody> 
</table>

### Elemento

* [[!UICONTROL Copy an item]](#copy-an-item)
* [[!UICONTROL Create an item]](#create-an-item)
* [[!UICONTROL Delete an item]](#delete-an-item)
* [[!UICONTROL Get an Item]](#get-an-item)
* [[!UICONTROL List Items]](#list-items)
* [[!UICONTROL Move Item]](#move-an-item)
* [[!UICONTROL Update an item]](#update-an-item)
* [[!UICONTROL Watch Items] (Programado)](#watch-items-scheduled)


#### [!UICONTROL Copy Item]

Este módulo de acción copia un elemento existente en una lista de SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL SharePoint] a [!DNL Workfront Fusion], vea <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL SharePoint] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Introducir ID de sitio, unidad y carpeta</td> 
   <td> <p>Seleccione cómo desea identificar el sitio y la lista que contiene el elemento que desea copiar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL List ID]</strong> y <strong>[!UICONTROL Item ID]</strong> en los campos que aparecen.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from list that you follow]</strong> </p> <p>En el campo Tipo de elemento, seleccione si va a mover un campo o una carpeta.  Seleccione el sitio que contiene el elemento que desea copiar, seleccione la lista y, a continuación, seleccione el elemento. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination ID]</td> 
   <td> Introduzca o asigne el ID de la carpeta en la que desea copiar el elemento. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New name]</td> 
   <td>Introduzca o asigne un nombre para la nueva copia del elemento. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create an item]

Este módulo de acción crea un nuevo elemento en una lista de SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL SharePoint] a [!DNL Workfront Fusion], consulte <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL SharePoint] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Create an Item]</td> 
   <td> <p>Seleccione cómo desea identificar el sitio y la lista donde desea crear un elemento.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne <strong>[!UICONTROL Site ID]</strong> y <strong>[!UICONTROL List ID]</strong> en los campos que aparecen.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el sitio que contiene la lista donde desea crear un elemento y, a continuación, seleccione la lista. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td>Para cada campo que desee establecer para el nuevo elemento, introduzca la clave del campo (identifica el campo) y el valor que desea que tenga el nuevo elemento para ese campo.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete an item]

Este módulo de acción elimina un elemento existente de una lista de SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL SharePoint] a [!DNL Workfront Fusion], consulte <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL SharePoint] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Update an Item]</td> 
   <td> <p>Seleccione cómo desea identificar el sitio y la lista que contiene el elemento que desea eliminar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL List ID]</strong> y <strong>[!UICONTROL Item ID]</strong> en los campos que aparecen.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el sitio que contiene el elemento que desea eliminar, seleccione la lista y, a continuación, seleccione el elemento. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get an Item]

Este módulo de acción devuelve los datos de un elemento especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL SharePoint] a [!DNL Workfront Fusion], consulte <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL SharePoint] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get an Item]</td> 
   <td> <p>Seleccione cómo desea identificar el sitio y la lista que contiene el elemento que desea obtener.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL List ID]</strong> y <strong>[!UICONTROL Item ID]</strong> en los campos que aparecen.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el sitio que contiene la lista de la que desea recuperar un elemento, seleccione la lista y, a continuación, seleccione el elemento. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Items]

Este módulo de acción recupera una lista de todos los elementos de una lista especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL SharePoint] a [!DNL Workfront Fusion], consulte <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL SharePoint] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List Items]</td> 
   <td> <p>Seleccione cómo desea identificar la lista de la que desea recuperar elementos.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne <strong>[!UICONTROL Site ID]</strong> y <strong>[!UICONTROL List ID]</strong> en los campos que aparecen.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el sitio que contiene la lista de la que desea recuperar elementos y, a continuación, seleccione la lista. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de elementos que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move an Item]

Este módulo de acción copia un elemento existente en una lista de SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL SharePoint] a [!DNL Workfront Fusion], vea <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL SharePoint] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Introducir ID de sitio, unidad y carpeta</td> 
   <td> <p>Seleccione cómo desea identificar el sitio y la lista que contiene el elemento que desea mover.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL List ID]</strong> y <strong>[!UICONTROL Item ID]</strong> en los campos que aparecen.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from list that you follow]</strong> </p> <p>En el campo Tipo de elemento, seleccione si va a mover un campo o una carpeta. Seleccione el sitio que contiene el elemento que desea copiar, seleccione la lista y, a continuación, seleccione el elemento. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination ID]</td> 
   <td> Introduzca o asigne el ID de la carpeta a la que desea mover el elemento. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New name]</td> 
   <td>Introduzca o asigne un nombre para el elemento movido. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update an item]

Este módulo de acción actualiza un elemento existente en una lista de SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL SharePoint] a [!DNL Workfront Fusion], consulte <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL SharePoint] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Update an Item]</td> 
   <td> <p>Seleccione cómo desea identificar el sitio y la lista que contiene el elemento que desea actualizar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL List ID]</strong> y <strong>[!UICONTROL Item ID]</strong> en los campos que aparecen.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el sitio que contiene el elemento que desea actualizar, seleccione la lista y, a continuación, seleccione el elemento. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td>Para cada campo que desee actualizar para el nuevo elemento, introduzca la clave del campo (identifica el campo) y el nuevo valor que desea que tenga el elemento para ese campo.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Items] (Programado)

Este módulo de activación inicia un escenario cuando se crea o modifica un elemento.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL SharePoint] a [!DNL Workfront Fusion], consulte <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL SharePoint] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch Lists]</td> 
   <td>Seleccione si desea ver listas por hora de creación (elementos nuevos) o por hora de modificación (elementos actualizados).</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site and List ID]</td> 
   <td> <p>Seleccione cómo desea identificar el sitio y la lista que desea ver.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne <strong>[!UICONTROL Site ID]</strong> y <strong>[!UICONTROL List ID]</strong> en los campos que aparecen.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>Seleccione el sitio que desea ver y, a continuación, seleccione la lista. Estos desplegables solo recuperan los sitios seguidos.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de elementos que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Lista

* [[!UICONTROL Create a List]](#create-a-list)
* [[!UICONTROL Get a List]](#get-a-list)
* [[!UICONTROL List Lists]](#list-lists)
* [[!UICONTROL Watch Lists]](#watch-lists)

#### [!UICONTROL Create a List]

Este módulo de acción crea una nueva lista en SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL SharePoint] a [!DNL Workfront Fusion], consulte <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL SharePoint] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a Site ID]</td> 
   <td> <p>Seleccione cómo desea identificar el sitio y la lista donde desea crear una lista.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne el elemento <strong>[!UICONTROL Site ID]</strong> en el que desea crear una lista.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el sitio en el que desea crear una lista. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Display Name]</td> 
   <td>Introduzca o asigne un nombre para la nueva lista.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Introduzca o asigne una descripción para la nueva lista.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Add Columns]</td> 
   <td>Para cada columna que desee establecer para la nueva lista, escriba un <strong>[!UICONTROL Name]</strong> para el campo y seleccione el <strong>[!UICONTROL Type]</strong> de valor que desea que tenga la nueva columna.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a List]

Este módulo de acción devuelve los datos de una lista especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL SharePoint] a [!DNL Workfront Fusion], consulte <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL SharePoint] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get a List]</td> 
   <td> <p>Seleccione cómo desea identificar el sitio y la lista que contiene el elemento que desea obtener.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne <strong>[!UICONTROL Site ID]</strong> y <strong>Id. de lista</strong> en los campos que aparecen.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el sitio que contiene la lista que desea recuperar y, a continuación, seleccione la lista. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Lists]

Este módulo de acción recupera una lista de todos los elementos de una lista especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL SharePoint] a [!DNL Workfront Fusion], consulte <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL SharePoint] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List Lists]</td> 
   <td> <p>Seleccione cómo desea identificar el sitio del que desea recuperar listas.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne <strong>[!UICONTROL Site ID]</strong>.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el sitio que contiene las listas que desea recuperar. La lista desplegable recupera solo los sitios que sigue.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de listas que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Lists]

Este módulo de activación inicia un escenario cuando se crea o modifica una lista.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL SharePoint] a [!DNL Workfront Fusion], consulte <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL SharePoint] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch Lists]</td> 
   <td>Seleccione si desea ver listas por hora de creación (elementos nuevos) o por hora de modificación (elementos actualizados).</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site and List ID]</td> 
   <td> <p>Seleccione cómo desea identificar el sitio y la lista que desea ver.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne el(la) <strong>[!UICONTROL Site ID]</strong> donde se encuentra la lista que desea ver.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>Seleccione el sitio que desea ver. La lista desplegable solo recupera el sitio que sigue.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de listas que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Página (Beta)

>[!NOTE]
>
>Las API de la versión `beta` en [!DNL Microsoft Graph] están sujetas a cambios. No se admite el uso de estas API en aplicaciones de producción.

#### [!UICONTROL Get a Page]

Este módulo de acción devuelve los datos de una página especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL SharePoint] a [!DNL Workfront Fusion], consulte <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL SharePoint] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get a Page]</td> 
   <td> <p>Seleccione cómo desea identificar la página que desea recuperar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne <strong>[!UICONTROL Site ID]</strong> y <strong>[!UICONTROL Page ID]</strong>.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el sitio que contiene la página que desea recuperar y, a continuación, seleccione la página.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Sitio

* [[!UICONTROL Get a Site]](#get-a-site)
* [[!UICONTROL Search Sites]](#search-sites)

#### [!UICONTROL Get a Site]

Este módulo de acción devuelve los datos de un sitio especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL SharePoint] a [!DNL Workfront Fusion], consulte <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL SharePoint] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get a Site]</td> 
   <td> <p>Seleccione cómo desea identificar la página que desea recuperar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne <strong>[!UICONTROL Site ID]</strong>.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el sitio que desea recuperar.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search Sites]

Este módulo de acción busca los sitios según el parámetro que especifique.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL SharePoint] a [!DNL Workfront Fusion], consulte <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL SharePoint] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Keyword of Display Name]</td> 
   <td> <p>Introduzca o asigne el término de búsqueda que desea buscar en los sitios.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de sitios que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Otro

* [Obtener cambios](#get-changes)
* [Realizar una llamada de API](#make-an-api-call)
* [Ver eventos](#watch-events)

#### Obtener cambios

Este módulo recupera las adiciones, actualizaciones y eliminaciones realizadas en la carpeta SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL SharePoint] a [!DNL Workfront Fusion], consulte <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL SharePoint] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>Seleccione cómo desea identificar el sitio y la lista que contiene el elemento que desea actualizar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL Drive ID]</strong> y <strong>[!UICONTROL Folder ID]</strong> en los campos que aparecen.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el sitio que contiene el elemento que desea actualizar, seleccione la unidad y, a continuación, seleccione la carpeta. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Token]</td> 
   <td> El token identifica desde qué punto el módulo debe comenzar a recuperar los cambios.  </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Make an API Call]

Este módulo le permite realizar una llamada de API personalizada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL SharePoint] a [!DNL Workfront Fusion], consulte <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar [!DNL SharePoint] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>Introduzca una ruta relativa a <code>https://graph.microsoft.com</code>. Ejemplo:<code> /beta/sites</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de petición HTTP en [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar. Por ejemplo, <code>{"Content-type":"application/json"}</code>. [!DNL Workfront Fusion] añade los encabezados de autorización en su lugar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> Añada la consulta para la llamada de API en forma de objeto JSON estándar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>Seleccione el tipo de datos que desea enviar en la llamada de API.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### Ver eventos

Este módulo de activación instantáneo inicia un escenario cuando se agrega, actualiza o elimina un elemento en SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
  <!--
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your [!DNL SharePoint] account to [!DNL Workfront Fusion], see <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Connect [!DNL SharePoint] to [!DNL Workfront Fusion]</a> in this article.</p> </td> 
  </tr> 
  -->
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>Seleccione un webhook existente o haga clic en Agregar para crear un nuevo webhook.</p> 
   </td> 
  </tr> 
 </tbody> 
</table>
