---
title: Módulos SharePoint
description: En un escenario  [!DNL Adobe Workfront Fusion] , puede automatizar los flujos de trabajo que utilizan Microsoft SharePoint Online, así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: 1a09aa86-5e0e-4347-b4cf-2b0a95e5b049
source-git-commit: 2bd3a9ba84182307af9349163db284514dd12aca
workflow-type: tm+mt
source-wordcount: '3393'
ht-degree: 58%

---

# Módulos de Microsoft SharePoint Online

En un escenario de [!DNL Adobe Workfront Fusion], puede automatizar los flujos de trabajo que utilizan Microsoft SharePoint Online, así como conectarlo a varias aplicaciones y servicios de terceros.

Para obtener instrucciones sobre cómo crear un escenario, vea los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

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
   <p>Actual: No se requiere licencia de Workfront Fusion</p>
   <p>O</p>
   <p>Heredado: Workfront Fusion para la automatización e integración del trabajo </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Seleccione o paquete de Prime Workfront: su organización debe adquirir Adobe Workfront Fusion.</li><li>Paquete de Ultimate Workfront: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe adquirir Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Para utilizar los módulos SharePoint Online de Microsoft, debe tener una cuenta SharePoint Online de Microsoft.

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

## Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion] {#connect-microsoft-sharepoint-online-to-workfront-fusion}

* [Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion] usando una [!DNL Microsoft] cuenta](#connect-microsoft-sharepoint-online-to-workfront-fusion-using-a-microsoft-account)
* [Conectar Microsoft SharePoint Online a  [!DNL Workfront Fusion] mediante la configuración avanzada](#connect-microsoft-sharepoint-online-to-workfront-fusion-using-advanced-settings)
* [Conectar Microsoft SharePoint Online a  [!DNL Workfront Fusion] mediante autorización de certificado](#connect-microsoft-sharepoint-online-to-workfront-fusion-using-certificate-authorization)

### Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion] mediante una cuenta de [!DNL Microsoft]

Puede usar su cuenta de [!DNL Microsoft] para crear una conexión con Microsoft SharePoint Online. Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Sharepoint] a [!DNL Workfront Fusion], consulte [Crear una conexión con [!DNL Adobe Workfront Fusion] : instrucciones básicas](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

### Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion] mediante la configuración avanzada

Para incluir credenciales en la conexión, habilite la opción Mostrar configuración avanzada. Para este tipo de conexión, necesita un ID de cliente, un secreto de cliente y un ID de inquilino.

1. En cualquier módulo de SharePoint, haga clic en **[!UICONTROL Agregar]** cerca del campo Conexión para abrir el cuadro **[!UICONTROL Crear una conexión]**.
1. Haga clic en **[!UICONTROL Mostrar ajustes avanzados]**.
1. Rellene los campos siguientes:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection type]</p> </td> 
      <td>Para usar las credenciales del cliente, seleccione <b>Correo electrónico de Microsoft 365</b>.</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td>Introduzca un nombre para la conexión. </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Client ID]</p> </td> 
      <td>Introduzca el ID de cliente de la aplicación de SharePoint a la que se está conectando. </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Client secret]</p> </td> 
      <td>Introduzca el secreto de cliente de la aplicación de SharePoint a la que se está conectando.</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Tenant ID]</p> </td> 
      <td>Introduzca el ID de inquilino de la aplicación de SharePoint a la que se está conectando.</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Instance]</p> </td> 
      <td> <p>Escriba la dirección de su cuenta de [!DNL ServiceNow] sin <code>https://</code> (normalmente, <code>&lt;company>.service-now.com</code>).</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. Haga clic en **Continuar** para guardar la conexión y volver al módulo.

### Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion] mediante autorización de certificado

Puede utilizar la autorización de certificados para conectarse a SharePoint.

>[!IMPORTANT]
>
>Para utilizar la autorización de certificados, primero debe crear una aplicación en Microsoft Entra y cargar el certificado allí.
>
>Para obtener instrucciones, consulte [Cómo configurar autoridades de certificación para la autenticación basada en certificados de Microsoft Entra](https://learn.microsoft.com/en-us/entra/identity/authentication/how-to-configure-certificate-authorities) en la documentación de Microsoft.

1. En cualquier módulo de SharePoint, haga clic en **[!UICONTROL Agregar]** cerca del campo Conexión para abrir el cuadro **[!UICONTROL Crear una conexión]**.
1. Haga clic en **[!UICONTROL Mostrar ajustes avanzados]**.
1. Rellene los campos siguientes:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection type]</p> </td> 
      <td>Para usar la autorización de certificados, seleccione <b>Microsoft SharePoint Online (Autenticación de certificado)</b>.</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td>Introduzca un nombre para la conexión. </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Client ID]</p> </td> 
      <td>Introduzca el ID de cliente de la aplicación de SharePoint a la que se está conectando. </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Huella digital]</p> </td> 
      <td>Introduzca la huella digital de la aplicación de SharePoint a la que se está conectando.</td> 
     </tr> 
      <tr>
        <td role="rowheader">[!UICONTROL Private key]</td>
        <td>
          <p>Introduzca el certificado o la clave privada que se generaron cuando se crearon las credenciales en Microsoft. </p>
          <p>Para extraer la clave privada o el certificado:</p>
          <ol>
            <li>
              <p>Haga clic en <b>[!UICONTROL Extract]</b>.</p>
            </li>
            <li>
            <p>Seleccione si va a extraer un certificado o una clave privada.</li>
            <li>
              <p>Seleccione el tipo de archivo que va a extraer.</p>
            </li>
            <li>
              <p>Seleccione el archivo que contiene la clave privada o el certificado.</p>
            </li>
            <li>
              <p>Introduzca la contraseña del archivo.</p>
            </li>
            <li>
              <p>Haga clic en <b>[!UICONTROL Save]</b> para extraer el archivo y volver a la configuración de conexión.</p>
            </li>
          </ol>
        </td>
      </tr>
    </tbody> 
   </table>

1. Haga clic en **Continue** para guardar la conexión y volver al módulo.

## Módulos SharePoint de Microsoft y sus campos

Al configurar los módulos SharePoint Online de Microsoft, [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto a estos, pueden mostrarse campos de Microsoft SharePoint Online adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

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

#### Crear un archivo

Este módulo devuelve los cambios realizados en SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft SharePoint Online a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>Seleccione cómo desea identificar la ubicación de la carpeta en la que desea recuperar los cambios.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne el <strong>[!UICONTROL Id. de sitio]</strong>, <strong>[!UICONTROL Id. de unidad]</strong> y <strong>[!UICONTROL Id. de carpeta]</strong> de la ubicación donde desea crear el archivo.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>Seleccione la ubicación en la que desea crear el archivo. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
      <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p>
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
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft SharePoint Online a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>Seleccione cómo identificar la ubicación de la carpeta que desea crear.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne el <strong>[!UICONTROL Id. de sitio]</strong>, <strong>[!UICONTROL Id. de unidad]</strong> y <strong>[!UICONTROL Id. de carpeta]</strong> de la ubicación donde desea crear la carpeta.</p> </li> 
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
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft SharePoint Online a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>Seleccione cómo identificar la ubicación del archivo que desea obtener.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne el <strong>[!UICONTROL Id. de sitio]</strong>, <strong>[!UICONTROL Id. de lista]</strong> y <strong>[!UICONTROL Id. de archivo]</strong> para el archivo que desea recuperar.</p> </li> 
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
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft SharePoint Online a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>Seleccione cómo identificar la ubicación del archivo que desea obtener.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne el <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL List ID]</strong> e <strong>[!UICONTROL folder ID]</strong> en los campos que aparecen.</p> </li> 
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

* [[!UICONTROL Copiar un elemento]](#copy-an-item)
* [[!UICONTROL Crear un elemento]](#create-an-item)
* [[!UICONTROL Eliminar un elemento]](#delete-an-item)
* [[!UICONTROL Obtener un elemento]](#get-an-item)
* [[!UICONTROL Enumerar elementos]](#list-items)
* [[!UICONTROL Mover elemento]](#move-an-item)
* [[!UICONTROL Actualizar un elemento]](#update-an-item)
* [[!UICONTROL Ver elementos] (Programados)](#watch-items-scheduled)


#### [!UICONTROL Copiar un elemento]

Este módulo de acción copia un elemento existente en una lista de SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft SharePoint Online a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Introducir ID de sitio, unidad y carpeta</td> 
   <td> <p>Seleccione cómo desea identificar el sitio y la unidad que contiene el elemento que desea copiar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne el <strong>[!UICONTROL Id. de sitio]</strong>, <strong>[!UICONTROL Id. de unidad]</strong> y <strong>[!UICONTROL Id. de elemento]</strong> del elemento que desea copiar.</p> </li> 
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

#### [!UICONTROL Crear un elemento]

Este módulo de acción crea un nuevo elemento en una lista de SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft SharePoint Online a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Create an Item]</td> 
   <td> <p>Seleccione cómo desea identificar el sitio y la unidad donde desea crear un elemento.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne <strong>[!UICONTROL Id. de sitio]</strong> y <strong>[!UICONTROL Id. de lista]</strong> donde desee crear el elemento.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el sitio que contiene la lista donde desea crear un elemento y, a continuación, seleccione la lista. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td>Para cada campo que desee establecer para el nuevo elemento, haga clic en <b>Agregar elemento</b> e introduzca la clave del campo (que identifica el campo) y el valor que desea que tenga el nuevo elemento para ese campo.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Eliminar un elemento]

Este módulo de acción elimina un elemento existente de una lista de SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft SharePoint Online a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Update an Item]</td> 
   <td> <p>Seleccione cómo desea identificar el sitio y la lista que contiene el elemento que desea eliminar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne el <strong>[!UICONTROL Id. de sitio]</strong>, <strong>[!UICONTROL Id. de lista]</strong> y <strong>[!UICONTROL Id. de elemento]</strong> del elemento que desea eliminar.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el sitio que contiene el elemento que desea eliminar, seleccione la lista y, a continuación, seleccione el elemento. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Obtener un elemento]

Este módulo de acción devuelve los datos de un elemento especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft SharePoint Online a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get an Item]</td> 
   <td> <p>Seleccione cómo desea identificar el sitio y la lista que contiene el elemento que desea obtener.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne el <strong>[!UICONTROL Id. de sitio]</strong>, <strong>[!UICONTROL Id. de lista]</strong> y <strong>[!UICONTROL Id. de elemento]</strong> del elemento para el que desea devolver datos.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el sitio que contiene la lista de la que desea recuperar un elemento, seleccione la lista y, a continuación, seleccione el elemento. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Enumerar elementos]

Este módulo de acción recupera una lista de todos los elementos de una lista especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft SharePoint Online a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List Items]</td> 
   <td> <p>Seleccione cómo desea identificar la lista de la que desea recuperar elementos.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne el <strong>[!UICONTROL Id. de sitio]</strong> y <strong>[!UICONTROL Id. de lista]</strong> para la lista para la que desea enumerar elementos.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el sitio que contiene la lista de la que desea recuperar elementos y, a continuación, seleccione la lista. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de elementos que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Mover un elemento]

Este módulo de acción copia un elemento existente en una lista de SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft SharePoint Online a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Introducir ID de sitio, unidad y carpeta</td> 
   <td> <p>Seleccione cómo desea identificar el sitio y la lista que contiene el elemento que desea mover.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne el <strong>[!UICONTROL Id. de sitio]</strong>, <strong>[!UICONTROL Id. de lista]</strong> y <strong>[!UICONTROL Id. de elemento]</strong> para el elemento que desea mover.</p> </li> 
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

#### [!UICONTROL Actualice un elemento]

Este módulo de acción actualiza un elemento existente en una lista de SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft SharePoint Online a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Update an Item]</td> 
   <td> <p>Seleccione cómo desea identificar el sitio y la lista que contiene el elemento que desea actualizar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne el <strong>[!UICONTROL Id. de sitio]</strong>, <strong>[!UICONTROL Id. de lista]</strong> y <strong>[!UICONTROL Id. de elemento]</strong> del elemento que desea actualizar.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el sitio que contiene el elemento que desea actualizar, seleccione la lista y, a continuación, seleccione el elemento. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td>Para cada campo que desee actualizar para el nuevo elemento, haga clic en <b>Agregar elemento</b> e introduzca la clave del campo (que identifica el campo) y el nuevo valor que desea que tenga el elemento para ese campo.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Ver artículos] (Programados)

Este módulo de activación inicia un escenario cuando se crea o modifica un elemento.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft SharePoint Online a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch Lists]</td> 
   <td>Seleccione si desea ver listas por hora de creación (elementos nuevos) o por hora de modificación (elementos actualizados).</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site and List ID]</td> 
   <td> <p>Seleccione cómo desea identificar el sitio y la lista que desea ver.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne el <strong>[!UICONTROL Id. de sitio]</strong> y <strong>[!UICONTROL Id. de lista]</strong> que desee ver.</p> </li> 
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

* [[!UICONTROL Crear una lista]](#create-a-list)
* [[!UICONTROL Obtener una lista]](#get-a-list)
* [[!UICONTROL Enumerar listas]](#list-lists)
* [[!UICONTROL Ver listas]](#watch-lists)

#### [!UICONTROL Crear una lista]

Este módulo de acción crea una nueva lista en SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft SharePoint Online a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a Site ID]</td> 
   <td> <p>Seleccione cómo desea identificar el sitio en el que desea crear una lista.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Introduzca o asigne el <strong>[!UICONTROL Site ID]</strong> donde desee crear una lista.</p> </li> 
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
   <td>Para cada columna que desee establecer para la nueva lista, haga clic en <b>Agregar elemento </b>, escriba un <strong>[!UICONTROL Nombre]</strong> para el campo y seleccione el <strong>[!UICONTROL Tipo]</strong> del valor que desea que tenga la nueva columna.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Obtener una lista]

Este módulo de acción devuelve los datos de una lista especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft SharePoint Online a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get a List]</td> 
   <td> <p>Seleccione cómo desea identificar el sitio y la lista que contiene el elemento que desea obtener.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne el <strong>[!UICONTROL Id. de sitio]</strong> y el <strong>Id. de lista</strong> que desee devolver.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el sitio que contiene la lista que desea recuperar y, a continuación, seleccione la lista. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Enumerar listas]

Este módulo de acción recupera una lista de todos los elementos de un sitio especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft SharePoint Online a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List Lists]</td> 
   <td> <p>Seleccione cómo desea identificar el sitio del que desea recuperar listas.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne el <strong>[!UICONTROL Id. de sitio]</strong> que contiene las listas que desea devolver.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el sitio que contiene las listas que desea recuperar. La lista desplegable recupera solo los sitios que sigue.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de listas que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Ver listas]

Este módulo de activación inicia un escenario cuando se crea o modifica una lista.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft SharePoint Online a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch Lists]</td> 
   <td>Seleccione si desea ver listas por hora de creación (elementos nuevos) o por hora de modificación (elementos actualizados).</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Introducir ID de sitio]</td> 
   <td> <p>Seleccione cómo desea identificar el sitio que desea ver en busca de listas.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne el <strong>[!UICONTROL Id. de sitio]</strong> donde desee ver las listas.</p> </li> 
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

#### [!UICONTROL Obtener una página]

Este módulo de acción devuelve los datos de una página especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft SharePoint Online a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get a Page]</td> 
   <td> <p>Seleccione cómo desea identificar la página que desea recuperar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Introduzca o asigne el <strong>[!UICONTROL Site ID]</strong>y <strong>[!UICONTROL Page ID]</strong>.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el sitio que contiene la página que desea recuperar y, a continuación, seleccione la página.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Sitio

* [[!UICONTROL Obtener un sitio]](#get-a-site)
* [[!UICONTROL Buscar sitios]](#search-sites)

#### [!UICONTROL Obtener un sitio]

Este módulo de acción devuelve los datos de un sitio especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft SharePoint Online a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get a Site]</td> 
   <td> <p>Seleccione cómo desea identificar la página que desea recuperar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Introduzca o asigne el <strong>[!UICONTROL Site ID]</strong>.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el sitio que desea recuperar.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Buscar sitios]

Este módulo de acción busca los sitios según el parámetro que especifique.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft SharePoint Online a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
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
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft SharePoint Online a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>Seleccione cómo desea identificar el sitio y la unidad que contiene el elemento que desea actualizar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Escriba o asigne el <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL Drive ID]</strong> y <strong>[!UICONTROL Folder ID]</strong> en los campos que aparecen.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Seleccione el sitio que contiene el elemento que desea actualizar, seleccione la unidad y, a continuación, seleccione la carpeta. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Token]</td> 
   <td> El token identifica desde qué punto el módulo debe comenzar a recuperar los cambios.  </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Realizar una llamada API]

Este módulo le permite realizar una llamada de API personalizada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Microsoft SharePoint Online a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Microsoft SharePoint Online a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>Introduzca una ruta relativa a <code>https://graph.microsoft.com</code>. Ejemplo:<code> /beta/sites</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td> 
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
   <td> <p>For instructions about connecting your Microsoft SharePoint Online account to [!DNL Workfront Fusion], see <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Connect Microsoft SharePoint Online to [!DNL Workfront Fusion]</a> in this article.</p> </td> 
  </tr> 
  -->
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>Seleccione un webhook existente o haga clic en Agregar e introduzca la conexión para crear un nuevo webhook.</p> 
   </td> 
  </tr> 
 </tbody> 
</table>
