---
title: Módulos de Microsoft OneDrive para empresas
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan  [!DNL Microsoft OneDrive for Business], así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: 657bea46-064e-4333-8e86-81678bb1c3bd
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1144'
ht-degree: 70%

---

# Módulos de [!DNL Microsoft OneDrive for Business]

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!DNL Microsoft OneDrive for Business], así como conectarlo a varias aplicaciones y servicios de terceros.

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
   <p>Actual: Su organización debe comprar Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Para usar [!DNL Microsoft OneDrive for Business] con Adobe Workfront Fusion, necesitará una cuenta de [!DNL Microsoft].

## Conectando el servicio [!DNL Microsoft OneDrive for Business] a Workfront Fusion

Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Microsoft OneDrive for Business] a [!UICONTROL Workfront Fusion], consulte [Crear una conexión a [!UICONTROL Adobe Workfront Fusion]: instrucciones básicas](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

>[!NOTE]
>
>Algunas aplicaciones de Microsoft utilizan la misma conexión, que está vinculada a permisos de usuario individuales. Por lo tanto, al crear una conexión, la pantalla de consentimiento de permisos muestra los permisos que se otorgaron previamente a la conexión de este usuario, además de cualquier nuevo permiso que sea necesario para la aplicación actual.
>
>Por ejemplo, si a un usuario se le han otorgado permisos de &quot;Leer tabla&quot; a través del conector de Excel y luego crea una conexión en el conector de Outlook para leer correos electrónicos, la pantalla de consentimiento de permisos mostrará tanto el permiso de &quot;Leer tabla&quot; ya otorgado como el nuevo permiso requerido de &quot;Escribir correo electrónico&quot;.

## Módulos de [!DNL Microsoft OneDrive for Business] y sus campos

Al configurar módulos de [!DNL Microsoft OneDrive for Business], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL Microsoft OneDrive for Business] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Activadores](#triggers)
* [Acciones](#actions)

### Activadores

* [[!UICONTROL Ver archivos]](#watch-files)
* [[!UICONTROL Ver carpetas]](#watch-folders)

#### [!UICONTROL Ver archivos]

Este módulo de activación se activa cuando se añade o actualiza un nuevo archivo en una carpeta que se está viendo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p> [!UICONTROL Drive ID]</p> </td> 
   <td> <p>Seleccione la unidad que desea ver.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td> <p> Seleccione la carpeta que desea ver. Dentro de un escenario, solo puede monitorizar una carpeta.</p> <p>Sugerencia: Para ver varias carpetas, cree un escenario independiente para cada una de ellas.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL I want to watch]</p> </td> 
   <td> <p>Seleccione si desea inspeccionar los nuevos archivos y todos los cambios o sólo los nuevos archivos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned rows]</td> 
   <td> <p> Defina el número máximo de resultados que desea que devuelva el módulo durante un ciclo.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Ver carpetas]

Este módulo de activación se activa cuando se añade una nueva carpeta a la carpeta que se está viendo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p> [!UICONTROL Drive ID]</p> </td> 
   <td> <p>Seleccione la unidad que desea ver.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td> <p> Seleccione la carpeta que desea ver. Dentro de un escenario, solo puede monitorizar una carpeta.</p> <p>Sugerencia: para realizar un seguimiento de varias carpetas, cree un escenario independiente para cada una de ellas.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL I want to watch]</p> </td> 
   <td> <p>Seleccione si desea ver las carpetas nuevas y todos los cambios o solo las carpetas nuevas.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned rows]</td> 
   <td> <p> Defina el número máximo de resultados que desea que devuelva el módulo durante un ciclo.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Acciones

* [[!UICONTROL Crear una carpeta]](#create-a-folder)
* [[!UICONTROL Eliminar un archivo]](#delete-a-file)
* [[!UICONTROL Eliminar una carpeta]](#delete-a-folder)
* [[!UICONTROL Obtener un archivo]](#get-a-file)
* [[!UICONTROL Obtener un vínculo para compartir]](#get-a-sharing-link)
* [[!UICONTROL Subir un archivo]](#upload-a-file)

#### [!UICONTROL Crear una carpeta]

Crea una carpeta dentro de la carpeta principal especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td><strong>[!UICONTROL Connection]</strong> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td><strong>[!UICONTROL Drive ID]</strong> </td> 
   <td> <p>Seleccione la unidad en la que desea crear una carpeta nueva.</p> </td> 
  </tr> 
  <tr> 
   <td><strong>[!UICONTROL Folder]</strong> </td> 
   <td> <p>Seleccione la carpeta en la que desea crear una nueva carpeta.</p> </td> 
  </tr> 
  <tr> 
   <td><strong>[!UICONTROL Folder name]</strong> </td> 
   <td>Introduzca o asigne un nombre para la nueva carpeta.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Eliminar un archivo]

Este módulo de acción mueve el archivo especificado a la papelera de reciclaje.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> [!UICONTROL Drive ID]</td> 
   <td> <p>Seleccione la unidad desde la que desea eliminar un archivo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td> <p>Introduzca el ID del archivo que desea eliminar. </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Eliminar una carpeta]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> [!UICONTROL Drive ID]</td> 
   <td> <p>Seleccione la unidad desde la que desea eliminar un archivo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder ID]</td> 
   <td> <p>Introduzca o asigne el ID de la carpeta que desea eliminar. </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Obtener un archivo]

Este módulo de acción recupera el archivo mediante el ID proporcionado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> [!UICONTROL Drive ID]</td> 
   <td> <p>Seleccione la unidad desde la que desea recuperar un archivo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td> <p>Introduzca el ID del archivo que desea recuperar. </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Obtener un vínculo de uso compartido]

Este módulo recupera un vínculo que puede compartir para dar acceso al archivo especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> [!UICONTROL Drive ID]</td> 
   <td> <p>Seleccione la unidad en la que desea cargar un archivo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Enter]</td> 
   <td> <p>Seleccione si desea elegir un archivo utilizando el ID de archivo o la ruta de acceso del archivo. Introduzca el ID de archivo o la ruta en el campo que aparece.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Permission type]</p> </td> 
   <td> <p>Seleccione si desea que los usuarios que reciban el vínculo tengan permisos de lectura y escritura o de solo lectura.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Scope]</td> 
   <td> <p> Seleccione si desea que el archivo sea accesible para cualquier usuario que tenga el vínculo o accesible solo para los miembros de su organización.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Subir un archivo]

Este módulo de acción carga un archivo binario o de texto en una carpeta especificada

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Office 365] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> [!UICONTROL Drive ID]</td> 
   <td> <p>Seleccione la unidad en la que desea cargar un archivo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Seleccione la carpeta dentro de la unidad.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Source File]</p> </td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL If the file with the same name exists]</td> 
   <td> <p> Seleccione lo que desea hacer si ya existe un archivo con el mismo nombre que el archivo que está intentando cargar.</p> 
    <ul> 
     <li>[!UICONTROL Replace the existing file]</li> 
     <li>[!UICONTROL Rename the new file]</li> 
     <li>[!UICONTROL End with an error]</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
