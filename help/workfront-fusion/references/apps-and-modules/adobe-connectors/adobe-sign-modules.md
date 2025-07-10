---
title: Módulos de Adobe Acrobat Sign
description: Con los módulos de [!DNL Adobe Acrobat Sign] , puede iniciar un escenario de [!DNL Adobe Workfront Fusion] basado en eventos de su cuenta de [!DNL Adobe] Acrobat Sign, crear, leer o actualizar acuerdos y otros registros, buscar registros usando los criterios que haya establecido y cargar documentos.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 0ef9d40e-8ad6-434e-8fa0-076920ff29ea
source-git-commit: 899fc717f5107433d6f1aea31c4d079243a85822
workflow-type: tm+mt
source-wordcount: '6664'
ht-degree: 96%

---

# Módulos de [!DNL Adobe Acrobat Sign]

Con los módulos de [!DNL Adobe Acrobat Sign], puede iniciar un escenario de [!DNL Adobe Workfront Fusion] basado en eventos de su cuenta de [!DNL Adobe Acrobat Sign], crear, leer o actualizar acuerdos y otros registros, buscar registros usando los criterios que haya establecido y cargar documentos.

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

## Información de la API [!DNL Adobe Acrobat Sign]

El conector de Adobe Acrobat Sign utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> v6 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.35.1</td> 
  </tr>
 </tbody> 
</table>


## Recomendaciones de uso del conector de [!DNL Adobe Acrobat Sign]

La aplicación [!DNL Adobe Sign] hace que la automatización de los procesos empresariales de firma electrónica en [!DNL Fusion] sea mucho más fácil y eficaz.

Los nuevos usuarios de [!DNL Adobe Sign] deben prestar mucha atención a algunas de las restricciones relacionadas con la actualización de acuerdos. Los acuerdos no suelen cambiarse una vez iniciados. Recomendamos que los nuevos usuarios de [!DNL Adobe Sign] se centren en la creación de nuevos acuerdos mediante el módulo de creación de acuerdos. Esto hará que las automatizaciones de [!DNL Fusion] sean más sencillas y funcionen mejor con [!DNL Adobe Sign].

Los acuerdos de [!DNL Adobe Sign] necesitan un campo con el que trabajar. Hay algunas opciones para hacerlo, pero lo más fácil y habitual es cargar un documento transitorio y luego asignar ese documento a su acuerdo.

![Recomendaciones de Adobe Sign](/help/workfront-fusion/references/apps-and-modules/assets/adobe-sign-recommendations-350x168.png)

## Módulos de [!DNL Adobe Acrobat Sign] y sus campos

Al configurar módulos de [!DNL Adobe Acrobat Sign], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Adobe Acrobat Sign] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Activadores](#triggers)
* [Acciones](#actions)
* [Búsquedas](#searches)

### Activadores

<!--
* [Watch for agreements](#watch-for-agreements) 
* [Watch for events](#watch-for-events)
-->

+++ **[!UICONTROL Watch for agreements]**

Este módulo activador inicia un escenario cuando se crea o actualiza un acuerdo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
<td>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Adobe Acrobat Sign] a [!DNL Workfront Fusion], consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión a [!DNL Adobe Workfront Fusion]: instrucciones básicas</a></td>  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td>Seleccione si desea buscar registros nuevos, registros actualizados o ambos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type] </td> 
   <td>Seleccione el tipo de registro que desea ver.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Find text]</td> 
   <td> <p>Introduzca los términos que desea buscar. El módulo devuelve registros que incluyen estos términos como valores de campo.</p> <p>Para obtener más información sobre la búsqueda de campos en [!DNL Adobe Acrobat Sign], consulte “Cómo funciona la búsqueda de texto” en <a href="https://helpx.adobe.com/es/sign/using/adobesign-search-users-agreements.html#HowSearchWorks">Búsqueda de Adobe Sign: cómo funciona</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned agreements]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Observar eventos]**

Este módulo de activador inicia un escenario cuando se produce un evento que selecciona.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td>Seleccione el webhook que desee utilizar o haga clic en <b>[!UICONTROL Add]</b> y llene los campos siguientes.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name]</td> 
   <td> <p>Introducir un nombre para el webhook</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Adobe Acrobat Sign] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scopes]</td> 
   <td> 
    <ul> 
     <li> <p>[!UICONTROL Account]</p> </li> 
     <li> <p>[!UICONTROL Group]</p> </li> 
     <li> <p>[!UICONTROL User]</p> </li> 
     <li> <p>[!UICONTROL Resource]</p> <p>Si selecciona [!UICONTROL Resource], introduzca el identificador de recurso y el tipo de recurso.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource level]</td> 
   <td> <p>Seleccione el tipo de recurso que desea observar.</p> 
    <ul> 
     <li> <p>[!UICONTROL Agreements]</p> </li> 
     <li> <p>[!UICONTROL Widgets]</p> </li> 
     <li> <p>[!UICONTROL Megasigns]</p> </li> 
     <li> <p>[!UICONTROL Library Documents]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook subscription events]</td> 
   <td>Seleccione los eventos de [!DNL Adobe Sign] que desea que el módulo observe.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Application display name]</td> 
   <td>El nombre para mostrar de la aplicación a través de la cual se crea el webhook.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Application name]</td> 
   <td>El nombre para mostrar de la aplicación a través de la cual se crea el webhook.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Problem notification emails]</td> 
   <td> <p>Esta configuración solo funciona para cuentas del administrador</p> <p>Para cada dirección de correo electrónico a la que desea enviar correos electrónicos de notificación de problemas, haga clic en <b>[!UICONTROL Add]</b> e introduzca la dirección de correo electrónico.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Agreement conditional parameters]</td> 
   <td>Si desea añadir parámetros condicionales, seleccione <b>[!UICONTROL Yes]</b> en el tipo de registro al que desea añadir parámetros y, a continuación, seleccione <b>[!UICONTROL Yes]</b> en cualquier parámetro que desee habilitar.</td> 
  </tr> 
 </tbody> 
</table>

+++

### Acciones

<!--
* [Create a record](#create-a-record) 
* [Create an agreement](#create-an-agreement) 
* [Create related records](#create-related-records) 
* [Custom API Call](#custom-api-call) 
* [List records](#list-records) 
* [Read a record](#read-a-record) 
* [Read related records](#read-related-records) 
* [Update a record](#update-a-record) 
* [Update related record](#update-related-record) 
* [Upload document](#upload-document)
-->

+++ **[!UICONTROL Crear un registro]**

Este módulo de acción crea un nuevo registro del tipo seleccionado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Adobe Acrobat Sign] a [!DNL Workfront Fusion], consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td>Añada los encabezados de la solicitud en forma de objeto JSON estándar. Por ejemplo: <code>{"Content-type":"application/json"}</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>Seleccione el tipo de registro que desea crear.</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Group]</b> </p> </li> 
     <li> <p><b>[!UICONTROL Library document]</b> </p> </li> 
     <li> <p><b>[!UICONTROL User]</b> </p> </li> 
     <li> <p><b>[!UICONTROL Web form] ([!UICONTROL Widget])</b> </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Group info]</td> 
   <td> <p>Introduzca o asigne el [!UICONTROL Name] y el [!UICONTROL ID] del grupo e indique si este grupo es el predeterminado para la cuenta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Library document info]</td> 
   <td> <p>Rellene los campos siguientes:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Files to send]</b> </p> <p>Para cada archivo que desee añadir, haga clic en <b>[!UICONTROL Add item]</b> y rellene los campos.</p> 
      <ul> 
       <li><b>[!UICONTROL Transient document ID]</b> <p>Introduzca el ID del documento transitorio</p> </li> 
       <li> <p><b>[!UICONTROL URL file transfer]</b> </p> <p>Rellene los campos siguientes:</p> 
        <ul> 
         <li> <p><b>[!UICONTROL Mime-Type]</b> </p> <p>Introduzca el tipo MIME del archivo original. Los tipos MIME (Multipurpose Internet Extension) son etiquetas que permiten al software identificar diferentes tipos de datos compartidos en Internet. Los servidores y exploradores web utilizan el tipo MIME para determinar qué se debe hacer con un archivo. Por ejemplo, un archivo con el tipo MIME <code>text/html</code> se procesará en un explorador de forma distinta que un archivo con el tipo MIME <code>image/jpeg</code>.</p> </li> 
         <li> <p><b>[!UICONTROL Name]</b> </p> <p>Introduzca un nombre para el archivo.</p> </li> 
         <li> <p><b>[!UICONTROL URL]</b> </p> <p>Escriba la dirección URL del archivo que desea enviar.</p> </li> 
        </ul> </li> 
       <li> <p><b>[!UICONTROL Notarize]</b> </p> <p>Seleccione si este documento debe estar registrado por un notario.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Library template name]</b> </p> <p>Introduzca o asigne el nombre de plantilla de la biblioteca</p> </li> 
     <li> <p><b>[!UICONTROL Sharing mode]</b> </p> <p>Especifique quién debe tener acceso al documento de la biblioteca.</p> </li> 
     <li> <p><b>[!UICONTROL Library document state]</b> </p> <p>Seleccione si el documento está en estado de creación o activo.</p> </li> 
     <li> <p><b>[!UICONTROL Library template type]</b> </p> <p>Para cada tipo de plantilla de biblioteca que desee utilizar, haga clic en <b>[!UICONTROL Add item]</b> y seleccione el tipo de plantilla.</p> </li> 
     <li> <p><b>[!UICONTROL Last event date]</b> </p> <p>Introduzca la última fecha en la que se produjo un evento en el documento de la biblioteca.</p> <p>Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos</a>.</p> </li> 
     <li> <p><b>[!UICONTROL Library document status]</b> </p> <p>Seleccione el estado del documento de la biblioteca.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL User info]</td> 
   <td> <p>Rellene los campos siguientes:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Email]</b> </p> <p>Introduzca la dirección de correo electrónico del usuario.</p> </li> 
     <li> <p><b>[!UICONTROL Is account admin]</b> </p> <p>Marque esta opción si el usuario creado es administrador de cuentas.</p> </li> 
     <li> <p><b>[!UICONTROL User ID]</b> </p> <p>Introduzca el ID único del usuario</p> </li> 
     <li> <p><b>[!UICONTROL Account ID]</b> </p> <p>Escriba el ID único de la cuenta de [!DNL Adobe Acrobat Sign] asociada a este usuario.</p> </li> 
     <li> <p><b>[!UICONTROL First name]</b> </p> <p>Introduzca el nombre del usuario.</p> </li> 
     <li> <p><b>[!UICONTROL Last name]</b> </p> <p>Introduzca el apellido del usuario</p> </li> 
     <li> <p><b>[!UICONTROL Company]</b> </p> <p>Introduzca el nombre de la compañía del usuario.</p> </li> 
     <li> <p><b>[!UICONTROL Initials]</b> </p> <p>Introduzca las iniciales del usuario.</p> </li> 
     <li> <p><b>[!UICONTROL Locale]</b> </p> <p>Introduzca la configuración regional del usuario. Determina el idioma de la interfaz de usuario. </p> </li> 
     <li> <p><b>[!UICONTROL Phone]</b> </p> <p>Introduzca el número de teléfono del usuario</p> </li> 
     <li> <p><b>Identificador del grupo primario</b> </p> <p>Introduzca el grupo al que se añade el nuevo usuario. Si no se escribe nada, el usuario se añadirá al grupo predeterminado de la cuenta.</p> </li> 
     <li> <p><b>[!UICONTROL Job title]</b> </p> <p>Introduzca el cargo del usuario.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Web form info]</td> 
   <td> <p>Rellene los campos siguientes</p> 
    <ul> 
     <li> <p><b>[!UICONTROL File info]</b> </p> <p>Para cada archivo que desee añadir al formulario web, haga clic en Añadir y rellene los campos siguientes:</p> 
      <ul> 
       <li> <p>[!UICONTROL File type]</p> <p>[!UICONTROL Document]</p> </li> 
       <li> <p>[!UICONTROL Transient document]</p> </li> 
       <li> <p>[!UICONTROL URL file info]</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Web form name]</b> </p> <p>Introduzca un nombre para el formulario web. Este nombre se utiliza para identificar el formulario web en lugares como correos electrónicos y sitios web.</p> </li> 
     <li> <p><b>[!UICONTROL Web form state]</b> </p> <p>Seleccione el estado en el que se debe crear el nuevo formulario web.</p> </li> 
     <li> <p><b>[!UICONTROL Web form participant set info]</b> </p> 
      <ul> 
       <li> <p><b>[!UICONTROL Member info]</b> </p> <p>Para cada miembro que desee añadir al conjunto de participantes, haga clic en <b>[!UICONTROL Add item]</b>. </p> 
        <ul> 
         <li> <p><b>[!UICONTROL Email]</b> </p> <p>Deje esta opción en blanco.</p> </li> 
         <li> <p><b>[!UICONTROL Security option]</b> </p> <p>Si desea añadir una opción de seguridad para autenticar a este usuario, seleccione <b>[!UICONTROL Yes]</b>, luego seleccione la opción de seguridad y rellene los campos que requiera.</p> </li> 
        </ul> </li> 
       <li> <p><b>[!UICONTROL Role]</b> </p> <p>Seleccione la función. Todos los miembros de este conjunto de participantes comparten la función.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Web form additional participant sets info]</b> </p> 
      <ul> 
       <li> <p><b>[!UICONTROL Member info]</b> </p> <p>Para cada miembro que desee añadir al conjunto de participantes, haga clic en <b>[!UICONTROL Add item]</b>.</p> 
        <ul> 
         <li> <p><b>[!UICONTROL Email]</b> </p> <p>Deje esta opción en blanco.</p> </li> 
         <li> <p><b>[!UICONTROL Security option]</b> </p> <p>Si desea añadir una opción de seguridad para autenticar a este usuario, seleccione <b>[!UICONTROL Yes]</b>, luego seleccione la opción de seguridad y rellene los campos que requiera.</p> </li> 
        </ul> </li> 
       <li> <p><b>[!UICONTROL Role]</b> </p> </li> 
       <li> <p><b>[!UICONTROL Web form participant ID] </b> </p> <p>Introduzca el ID del participante del formulario web.</p> </li> 
       <li> <p><b>[!UICONTROL Order]</b> </p> <p>Especifique el orden en que este conjunto de participantes debe interactuar con el formulario web. Por ejemplo, el grupo de participantes que tiene un valor de pedido de 1 debe ir primero, 2 debe ir después, y así sucesivamente. Los números de pedido deben comenzar por uno y no deben haber espacios en la serie. </p> </li> 
       <li> <p><b>[!UICONTROL Provider participant set info]</b> </p> <p>Si se desconoce el participante, introduzca si el proveedor debe proporcionar los detalles del participante e introduzca un mensaje con los detalles necesarios para el participante desconocido.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Authentication failure info]</b> </p> <p>Si desea proporcionar una página de fallo o error para los usuarios, seleccione <b>[!UICONTROL Yes]</b> y rellene los campos siguientes:</p> 
      <ul> 
       <li> <p><b>[!UICONTROL URL]</b> </p> <p>Introducir la dirección URL de la página de error</p> </li> 
       <li> <p><b>[!UICONTROL Deframe]</b> </p> <p>Habilite esta opción si desea que la página de error aparezca dentro del formulario web</p> </li> 
       <li> <p><b>[!UICONTROL Delay]</b> </p> <p>Introduzca el retardo, en segundos, que debe producirse antes de redirigir al usuario a la página de error.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL CC info]</b> </p> <p>Para cada dirección de correo electrónico que desee que reciba un correo electrónico cuando se firme el acuerdo final en el formulario web, haga clic en <b>[!UICONTROL Add item]</b> e introduzca la dirección de correo electrónico.</p> </li> 
     <li> <p><b>[!UICONTROL Completion info]</b> </p> <p style="font-style: normal;">Si desea proporcionar una página de finalización satisfactoria para los usuarios, seleccione <b>[!UICONTROL Yes]</b> y rellene los campos siguientes:</p> 
      <ul> 
       <li> <p><b>[!UICONTROL URL]</b> </p> <p>Introducir la dirección URL de la página de finalización satisfactoria</p> </li> 
       <li> <p><b>[!UICONTROL Deframe]</b> </p> <p>Habilite esta opción si desea que la página de finalización satisfactoria aparezca dentro del formulario web</p> </li> 
       <li> <p><b>[!UICONTROL Delay]</b> </p> <p>Introduzca el retardo, en segundos, que debe producirse antes de redirigir al usuario a la página de finalización satisfactoria.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Group ID]</b> </p> <p>Introduzca el ID del grupo al que pertenece el formulario web. Si no se introduce nada, el formulario web pertenecerá al grupo principal del usuario de la cuenta.</p> </li> 
     <li> <p><b>[!UICONTROL Last event date]</b> </p> <p>Introduzca la fecha en la que se ha producido el último evento en el formulario web. Use el formato <code>yyyy-MM-dd'T'HH:mm:ssZ</code>.</p> </li> 
     <li> <p><b>[!UICONTROL Locale]</b> </p> <p>Introduzca la configuración regional del usuario. Determina el idioma de la interfaz de usuario. </p> </li> 
     <li> <p><b>[!UICONTROL Security optio]n</b> </p> <p>Introduzca la contraseña utilizada para proteger el documento. Debe comunicar esta contraseña por separado a las partes relevantes.</p> </li> 
     <li> <p><b>[!UICONTROL Vaulting info]</b> </p> <p>Si la cuenta está configurada para el almacenamiento de documentos y está establecida en la opción de habilitar por acuerdo, puede habilitar esta opción para almacenar este acuerdo.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Create an agreement]**

Este módulo de acción crea un acuerdo, lo envía para su firma y devuelve el ID del acuerdo.

>[!NOTE]
>
>Se recomienda cargar el documento para firmar como documento transitorio y, a continuación, asignarlo al campo [!UICONTROL File to send] del módulo [!UICONTROL Create an agreement]. Por ejemplo, consulte “Cargar documento” en este artículo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
<td>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Adobe Acrobat Sign] a [!DNL Workfront Fusion], consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a></td>  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td>Añada los encabezados de la solicitud en forma de objeto JSON estándar. Por ejemplo: <code>{"Content-type":"application/json"}</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Files to send]</td> 
   <td> <p>Para cada elemento que desee incluir en el acuerdo, haga clic en <b>[!UICONTROL Add Item]</b> y rellene los campos siguientes:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL File Type]</b> </p> 
      <ul> 
       <li> <p><b>[!UICONTROL Document]</b> </p> <p>Rellene los campos siguientes:</p> 
        <ul> 
         <li> <p><b>[!UICONTROL Created date]</b> </p> <p>Introduzca o asigne la fecha de creación del documento en el formato <code>yyyy-MM-dd'T'HH:mm:ssZ</code>. Por ejemplo, <code>2016-02-25T18:46:19Z</code> representa la hora UTC.</p> </li> 
         <li> <p><b>[!UICONTROL ID]</b> </p> <p>Introduzca o asigne el ID del documento.</p> </li> 
         <li> <p><b>[!UICONTROL Label]</b> </p> <p>Introduzca o asigne una etiqueta única para el archivo. En el caso de un flujo de trabajo personalizado, se asignará un archivo al elemento de archivo correspondiente en la definición del flujo de trabajo. Esto debe especificarse en caso de solicitud de creación del acuerdo de flujo de trabajo personalizado.</p> </li> 
         <li> <p><b>[!UICONTROL Number of pages]</b> </p> <p>Introduzca o asigne el número de páginas en el documento.</p> </li> 
         <li> <p><b>[!UICONTROL Mime-Type]</b> </p> <p>Introduzca o asigne el tipo MIME del archivo original. Los tipos MIME (Multipurpose Internet Extension) son etiquetas que permiten al software identificar diferentes tipos de datos compartidos en Internet. Los servidores y exploradores web utilizan el tipo MIME para determinar qué se debe hacer con un archivo. Por ejemplo, un archivo con el tipo MIME <code>text/html</code> se procesará en un explorador de forma distinta que un archivo con el tipo MIME <code>image/jpeg</code>.</p> </li> 
         <li> <p><b>[!UICONTROL Name]</b> </p> <p>Escriba o asigne un nombre para el documento.<br></p> </li> 
        </ul> </li> 
       <li> <p><b>[!UICONTROL Library document ID]</b> </p> <p>Introduzca el ID del documento de la biblioteca</p> </li> 
       <li> <p><b>[!UICONTROL Transient document ID]</b> </p> <p>Introduzca el ID del documento transitorio</p> </li> 
       <li> <p><b>[!UICONTROL URL file transfer]</b> </p> <p>Rellene los campos siguientes:</p> 
        <ul> 
         <li> <p><b>[!UICONTROL Mime-Type]</b> </p> <p>Introduzca el tipo MIME del archivo original. Los tipos MIME (Multipurpose Internet Extension) son etiquetas que permiten al software identificar diferentes tipos de datos compartidos en Internet. Los servidores y exploradores web utilizan el tipo MIME para determinar qué se debe hacer con un archivo. Por ejemplo, un archivo con el tipo MIME <code>text/html</code> se procesará en un explorador de forma distinta que un archivo con el tipo MIME <code>image/jpeg</code>.</p> </li> 
         <li> <p><b>[!UICONTROL Name]</b> </p> <p>Introduzca un nombre para el archivo.</p> </li> 
         <li> <p><b>[!UICONTROL URL]</b> </p> <p>Escriba la dirección URL del archivo que desea enviar.</p> </li> 
        </ul> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Label]</b> </p> <p>Introduzca una etiqueta para el archivo.</p> </li> 
     <li> <p><b>[!UICONTROL Notarize]</b> </p> <p>Active esta opción para indicar que el archivo debe estar certificado por un notario.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Agreement name]</td> 
   <td>Introduzca un nombre para el nuevo acuerdo. Este nombre se utiliza para identificar el acuerdo en lugares como correos electrónicos y sitios web.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Participant sets info]</td> 
   <td> <p>Para cada conjunto de participantes que desee añadir, haga clic en <b>[!UICONTROL Add item]</b> y rellene los campos siguientes.</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Members]</b> </p> <p>Para cada persona que desee añadir al conjunto de participantes, haga clic en <b>[!UICONTROL Add item]</b> e introduzca la dirección de correo electrónico de la persona.</p> </li> 
     <li> <p><b>[!UICONTROL Order]</b> </p> <p>Especifique el orden en que este conjunto de participantes debe firmar el acuerdo. Por ejemplo, el grupo de participantes que tiene un valor de orden de 1 debe firmar primero, el 2 debe firmar después, y así sucesivamente. Los números de pedido deben comenzar por uno y no deben haber espacios en la serie. </p> </li> 
     <li> <p><b>[!UICONTROL Role]</b> </p> <p>Seleccione una función para este conjunto de participantes. Todos los participantes en el conjunto reciben esta función.</p> </li> 
     <li> <p><b>[!UICONTROL ID]</b> </p> <p>Introduzca o asigne el ID de este conjunto de participantes.</p> </li> 
     <li> <p><b>[!UICONTROL Label]</b> </p> <p>Introduzca o asigne una etiqueta única para el juego de participantes. Para los flujos de trabajo personalizados, la etiqueta especificada en el conjunto de participación debe asignarla al paso de participación en el flujo de trabajo personalizado.</p> </li> 
     <li> <p><b>[!UICONTROL Name]</b> </p> <p>Introduzca un nombre para el conjunto de participantes. Este nombre debe ser único dentro del acuerdo.</p> </li> 
     <li> <p><b>[!UICONTROL Private message]</b> </p> <p>Introduzca o asigne un mensaje para este conjunto de participantes. Todos los participantes en el conjunto reciben este mensaje.</p> </li> 
     <li> <p><b>[!UICONTROL Visible pages]</b> </p> <p>Si la visibilidad limitada del documento está habilitada para este contrato, especifique qué archivos son visibles para este conjunto de participantes. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Signature type]</td> 
   <td> <p>Seleccione el tipo de firma que requiere el acuerdo.</p> 
    <ul> 
     <li> <p><b>[!UICONTROL E-sign]</b> </p> <p>El acuerdo debe firmarse electrónicamente.</p> </li> 
     <li> <p><b>[!UICONTROL Written]</b> </p> <p>El acuerdo debe firmarse a mano y el acuerdo firmado debe analizarse y cargarse.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL State]</td> 
   <td> <p>Seleccione un estado para este acuerdo.</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Authoring]</b> </p> <p>Aún puede editar o añadir campos a este acuerdo.</p> </li> 
     <li> <p><b>[!UICONTROL Draft]</b> </p> <p>Puede generar gradualmente este acuerdo antes de enviarlo.</p> </li> 
     <li> <p><b>[!UICONTROL In Process]</b> </p> <p>Este acuerdo se enviará inmediatamente.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL CCs]</td> 
   <td> <p>Puede enviar este acuerdo a las partes interesadas que no necesiten firmarlo, como las partes interesadas. Reciben un correo electrónico al principio del proceso de firma y otro cuando se recibe la firma final. También reciben una copia del acuerdo en PDF. </p> <p>Para cada persona que desee incluir en la copia de seguridad de este contrato, haga clic en <b>[!UICONTROL Add item]</b> y rellene los campos siguientes:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Email]</b> </p> <p>Introduzca o asigne la dirección de correo electrónico que desea que aparezca en el contrato.</p> </li> 
     <li> <p><b>[!UICONTROL Label]</b> </p> <p>Introduzca o asigne una etiqueta para esta dirección de correo electrónico, tal como se ve en la descripción del flujo de trabajo</p> </li> 
     <li> <p><b>[!UICONTROL Visible pages]</b> </p> </li> 
     <li> <p>Si la visibilidad limitada del documento está habilitada para este contrato, especifique qué archivos son visibles para este conjunto de participantes. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Email option]</td> 
   <td> <p>Para cada tipo de correo electrónico, seleccione si ese tipo de correo se envía a todos los participantes o a ninguno.</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Completion emails]</b> </p> <p>Enviar un correo electrónico cuando se complete, cancele, caduque o rechace este acuerdo.</p> </li> 
     <li> <p><b>[!UICONTROL In-Flight emails]</b> </p> <p>Se envía un correo electrónico cuando se delega o reemplaza este acuerdo.</p> </li> 
     <li> <p><b>[!UICONTROL Agreement initiation emails]</b> </p> <p>Enviar un correo electrónico cuando se cree este acuerdo o cuando se solicite una acción.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL External ID]</td> 
   <td> <p>Introduzca o asigne un ID para este acuerdo. Puede especificarlo cuando se cree el acuerdo y utilizarlo para ubicarlo en módulos o consultas posteriores.</p> <p>Nota: El valor ID externo es visible para todos los participantes a través de la API, por lo que no debe utilizarse para contener un token confidencial.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Merge field info]</td> 
   <td> <p>Para cada campo del acuerdo para el que desee colocar un valor predeterminado, haga clic en <b>[!UICONTROL Add item]</b> e introduzca el valor predeterminado y el nombre del campo.</p> <p>Los valores se presentarán a los firmantes para los campos editables. Para los campos de solo lectura, los valores proporcionados no se podrán editar durante el proceso de firma.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Notary info]</td> 
   <td> <p>Rellene los campos siguientes:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Appointment]</b> </p> <p>Introduzca o asigne una fecha y hora propuestas para la cita en la que se notarizará este acuerdo.</p> </li> 
     <li> <p><b>[!UICONTROL Note]</b> </p> <p>Introduzca o asigne las notas que desee incluir sobre la sesión de notaría.</p> </li> 
     <li> <p><b>[!UICONTROL Payment]</b> </p> <p>Seleccione si será el firmante o el remitente del acuerdo quien pagará al notario.</p> </li> 
     <li> <p><b>[!UICONTROL Notary Type]</b> </p> <p>Seleccionar el tipo de notario</p> 
      <ul> 
       <li> <p>[!UICONTROL Provider notary]</p> <p>El notario es proporcionado por el notario proveedor.</p> </li> 
       <li> <p>[!UICONTROL BYON notary]</p> <p>El notario es proporcionado por el cliente.</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Post sign option]</td> 
   <td> <p>Seleccione si desea que los firmantes sean dirigidos a una página de finalización satisfactoria tras firmar el acuerdo. Si selecciona <b>[!UICONTROL Yes]</b>, rellene los campos siguientes:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Redirect delay]</b> </p> <p>Introduzca o asigne un número que represente el número de segundos antes de que el firmante se redirija a la página de finalización satisfactoria. Si este valor es mayor que 0, el usuario verá primero el mensaje de éxito estándar de [!DNL Adobe Sign] y, tras un tiempo de espera, se le redirigirá a la página de finalización satisfactoria.</p> </li> 
     <li> <p><b>[!UICONTROL Redirect URL]</b> </p> <p>Introduzca o asigne una URL de acceso público a la que se enviará al usuario después de completar correctamente el proceso de firma.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Security option]</td> 
   <td> <p>Introduzca o asigne la contraseña secundaria que se utilizará para proteger el documento PDF. </p> <p>Importante: [!DNL Adobe Sign] nunca compartirá esta contraseña, por lo que debe comunicarla por separado a las partes relevantes.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Vaulting info]</td> 
   <td>Si la cuenta está configurada para el almacenamiento de documentos y está establecida en la opción de habilitar por acuerdo, puede habilitar esta opción para almacenar este acuerdo.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Crear registros relacionados]**

Este módulo de acción crea registros vinculados a un módulo seleccionado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Adobe Acrobat Sign] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] añade encabezados de autorización automáticamente.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>Seleccione el tipo de registro del registro original con el que desea asociar los registros creados.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Agreement]/[!UICONTROL Library document]/[!UICONTROL User]/[!UICONTROL Widget ID]</td> 
   <td>Introduzca o asigne el ID del objeto con el que desea asociar el registro creado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Agreement related field]</td> 
   <td> <p>Seleccione el tipo de campo relacionado que desea crear</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Form fields]</b> </p> <p>Introduzca el ID de plantilla de la plantilla que contiene los campos que desea crear</p> </li> 
     <li> <p><b>[!UICONTROL Reminders]</b> </p> <p>Rellene los campos siguientes:</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Recipient participant ID]</b> </p> <p>Para cada participante al que desee enviar un recordatorio, haga clic en [!UICONTROL Add item] e introduzca el ID del participante.</p> </li> 
       <li> <p><b>[!UICONTROL Status]</b> </p> <p>Para los nuevos registros, el estado debe ser [!UICONTROL Active].</p> </li> 
       <li> <p><b>[!UICONTROL First reminder delay]</b> </p> <p>Introduzca el retraso en horas antes de enviar el primer recordatorio. El valor mínimo permitido es una hora y el valor máximo no puede ser mayor que la diferencia entre la creación del acuerdo y la hora de caducidad del acuerdo en horas. Si no se ha establecido este retraso, el primer recordatorio se basará en la frecuencia.</p> </li> 
       <li> <p><b>[!UICONTROL Reminder frequency]</b> </p> <p>Establezca la frecuencia con la que desea que se envíe el recordatorio. Si no se ha indicado la frecuencia, el recordatorio se enviará una vez.</p> </li> 
       <li> <p><b>[!UICONTROL Last sent date]</b> </p> <p>Este campo lo establece el sistema.</p> </li> 
       <li> <p><b>[!UICONTROL Next sent date]</b> </p> <p>Este campo debe estar en blanco o establecido como [!UICONTROL ONCE].</p> </li> 
       <li> <p><b>[!UICONTROL Note]</b> </p> <p>Introduzca una nota para incluirla en el recordatorio. Esto resulta útil para indicar al participante por qué se requiere su participación.</p> </li> 
       <li> <p><b>[!UICONTROL Start reminder counter from]</b> </p> <p>Seleccione si el recordatorio se enviará en función del momento en el que se crea el acuerdo o cuando esté disponible.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Signer identity report]</b> </p> <p>Introduzca la contraseña utilizada para proteger el documento PDF.</p> </li> 
     <li> <p><b>[!UICONTROL Views]</b> </p> <p>Introduzca los campos siguientes</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Name]</b> </p> <p>Seleccione el nombre de la vista que desea crear.</p> </li> 
       <li> <p><b>[!UICONTROL Auto login user]</b> </p> <p>Seleccione <b>[!UICONTROL Yes]</b> para iniciar automáticamente la sesión del usuario en la dirección URL devuelta.</p> </li> 
       <li> <p><b>[!UICONTROL Frame Parent]</b> </p> <p>Introduzca o asigne una lista separada por comas de direcciones URL de dominio principal donde las direcciones URL devueltas se pueden incorporar en Iframes. Si se dejan vacías, las páginas de [!DNL Adobe Acrobat Sign] no se podrán ver en el iframe.</p> </li> 
       <li> <p><b>[!UICONTROL Locale]</b> </p> <p>Introduzca el idioma en el que desea crear la vista. </p> </li> 
       <li> <p><b>[!UICONTROL No chrome flag]</b> </p> <p>Seleccione <b>[!UICONTROL Yes]</b> para mostrar la página incrustada sin un encabezado o pie de página de navegación.</p> </li> 
       <li> <p><b>[!UICONTROL Can edit files]</b> </p> <p>Seleccione <b>[!UICONTROL Yes]</b> si desea que la sección de carga de archivos se edite añadiendo o quitando archivos. Este no es un mecanismo de control de acceso. El valor predeterminado es [!UICONTROL Yes].</p> </li> 
       <li> <p><b>[!UICONTROL Library document]</b> </p> <p>Seleccione <b>[!UICONTROL Yes]</b> si desea que los enlaces de los documentos de la biblioteca estén visibles. El valor predeterminado es [!UICONTROL Yes].</p> </li> 
       <li> <p><b>[!UICONTROL Local file]</b> </p> <p>Seleccione <b>[!UICONTROL Yes]</b> si desea que aparezca el botón de carga de archivos locales. El valor predeterminado es [!UICONTROL Yes].</p> </li> 
       <li> <p><b>[!UICONTROL Web connectors]</b> </p> <p>Seleccione <b>[!UICONTROL Yes]</b> si desea que aparezcan los enlaces para adjuntar documentos desde orígenes web. El valor predeterminado es Sí.</p> </li> 
       <li> <p><b>[!UICONTROL Is preview selected]</b> </p> <p>Seleccione <b>[!UICONTROL Yes]</b> para establecer la página de composición en modo de creación.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Member share]</b> </p> <p>Para cada miembro con el que desee compartir el acuerdo, haga clic en <b>[!UICONTROL Add item]</b> e introduzca la dirección de correo electrónico del abonado y un mensaje para ese abonado.</p> </li> 
     <li> <p>[!UICONTROL Delegate participant set]</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Participant set ID]</b> </p> <p>Introduzca el ID del conjunto de participantes</p> </li> 
       <li> <p><b>[!UICONTROL Member info]</b> </p> <p>Para cada miembro que desee añadir, haga clic en [!UICONTROL Add item] e introduzca la dirección de correo electrónico y la información de teléfono del miembro.</p> </li> 
       <li> <p><b>[!UICONTROL Private message]</b> </p> <p>Introduzca un mensaje. Todos los miembros del conjunto de participantes reciben este mensaje.</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Library view info]</td> 
   <td> <p>Rellene los campos siguientes:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Name]</b> </p> <p>Introduzca un nombre para la plantilla de biblioteca. Este nombre se utiliza en correos electrónicos y sitios web.</p> </li> 
     <li> <p><b>[!UICONTROL Auto login user]</b> </p> <p>Seleccione <b>[!UICONTROL Yes]</b> para iniciar sesión automáticamente en la dirección URL devuelta.</p> </li> 
     <li> <p><b>[!UICONTROL Frame parent]</b> </p> <p>Introduzca o asigne una lista separada por comas de direcciones URL de dominio principal donde las direcciones URL devueltas se pueden incorporar en Iframes. Si se dejan vacías, las páginas de [!DNL Adobe Acrobat Sign] no se podrán ver en el iframe.</p> </li> 
     <li> <p><b>[!UICONTROL Locale]</b> </p> <p>Introduzca el idioma en el que desea crear la vista. </p> </li> 
     <li> <p><b>[!UICONTROL No chrome flag]</b> </p> <p>Seleccione <b>[!UICONTROL Yes]</b> para mostrar la página incrustada sin un encabezado o pie de página de navegación.</p> </li> 
     <li> <p><b>[!UICONTROL Send view configuration]</b> </p> <p>Seleccione <b>[!UICONTROL Yes]</b> si desea configurar la vista de [!UICONTROL Send] y, a continuación, rellene los campos siguientes.</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Agreement name]</b> </p> <p>Introduzca o asigne el nombre del acuerdo para el documento de biblioteca en la página de redacción.</p> </li> 
       <li> <p><b>[!UICONTROL Can edit files]</b> </p> <p>Seleccione <b>[!UICONTROL Yes]</b> si desea que la sección de carga de archivos se edite añadiendo o quitando archivos. Este no es un mecanismo de control de acceso. El valor predeterminado es [!UICONTROL Yes].</p> </li> 
       <li> <p><b>[!UICONTROL Local file]</b> </p> <p>Seleccione <b>[!UICONTROL Yes]</b> si desea que los vínculos de documentos de biblioteca estén visibles. El valor predeterminado es [!UICONTROL Yes].</p> </li> 
       <li> <p><b>[!UICONTROL Web connectors]</b> </p> <p>Seleccione <b>[!UICONTROL Yes]</b> si desea que aparezcan los vínculos para adjuntar documentos de orígenes web. El valor predeterminado es [!UICONTROL Yes].</p> </li> 
       <li> <p><b>Es la vista previa seleccionada</b> </p> <p>Seleccione <b>[!UICONTROL Yes]</b> para establecer la página de composición en modo de creación.</p> </li> 
      </ul> <p> </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL User view info]</td> 
   <td> <p>Rellene los campos siguientes</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Name]</b> </p> <p>Seleccione el nombre de la vista de usuario solicitada.</p> </li> 
     <li> <p><b>[!UICONTROL Auto login user]</b> </p> <p>Seleccione <b>[!UICONTROL Yes]</b> para iniciar sesión automáticamente con el usuario. Seleccione <b>[!UICONTROL No]</b> para requerir credenciales. El valor predeterminado es [!UICONTROL No].</p> </li> 
     <li> <p><b>[!UICONTROL Frame parent]</b> </p> <p>Introduzca o asigne una lista separada por comas de direcciones URL de dominio principal donde las direcciones URL devueltas se pueden incorporar en Iframes. Si se deja vacío, las páginas de [!DNL Adobe Acrobat Sign] no se podrán ver en el iframe.</p> </li> 
     <li> <p><b>Sin indicador de Chrome</b> </p> <p>Seleccione <b>[!UICONTROL Yes]</b> para mostrar la página incrustada sin un encabezado o pie de página de exploración.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Widget related fields]</td> 
   <td> <p>Seleccione el registro relacionado que desea crear.</p> 
    <ul> 
     <li> <p>[!UICONTROL Views]</p> <p>Cumplimente los campos siguientes.</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Name]</b> </p> <p>Seleccione el nombre de la vista del formulario web solicitado</p> </li> 
       <li> <p><b>[!UICONTROL Auto login user]</b> </p> <p>Seleccione <b>[!UICONTROL Yes]</b> para iniciar sesión automáticamente con el usuario. Seleccione <b>[!UICONTROL No]</b> para requerir credenciales. El valor predeterminado es [!UICONTROL No].</p> </li> 
       <li> <p><b>[!UICONTROL Frame parent]</b> </p> <p>Introduzca o asigne una lista separada por comas de direcciones URL de dominio principal donde las direcciones URL devueltas se pueden incorporar en Iframes. Si se dejan vacías, las páginas de [!DNL Adobe Acrobat Sign] no se podrán ver en el iframe.</p> </li> 
       <li> <p><b>[!UICONTROL Locale]</b> </p> <p>Introduzca el idioma en el que desea crear la vista. </p> </li> 
       <li> <p><b>[!UICONTROL No chrome flag]</b> </p> <p>Seleccione <b>[!UICONTROL Yes]</b> para mostrar la página incrustada sin un encabezado o pie de página de navegación.</p> </li> 
       <li> <p>[!UICONTROL Personalized signing view configuration]</p> <p>Si desea configurar una vista de firma personalizada, seleccione <b>[!UICONTROL Yes]</b> y cumplimente los campos siguientes:</p> 
        <ul> 
         <li> <p><b>[!UICONTROL Email]</b> </p> <p>Introduzca la dirección de correo electrónico de la persona que recibe el formulario web recién creado</p> </li> 
         <li> <p><b>[!UICONTROL Comment]</b> </p> <p>Escriba un comentario que describa cómo el que llama a la API estableció la identidad del firmante. Esta información aparece en la pista de auditoría de [!DNL Adobe Acrobat Sign].</p> </li> 
         <li> <p><b>[!UICONTROL Expiration]</b> </p> <p>Introduzca una fecha de caducidad para la personalización de este formulario web. </p> <p>Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">Coerción de tipos</a>.</p> </li> 
         <li> <p><b>[!UICONTROL Reusable]</b> </p> <p>Seleccione <b>[!UICONTROL Yes]</b> si desea que el firmante deseado pueda firmar el formulario más de una vez.</p> </li> 
        </ul> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Member share]</b> </p> <p>Para cada miembro con el que desee compartir el acuerdo, haga clic en <b>[!UICONTROL Add item]</b> e introduzca la dirección de correo electrónico del miembro y un mensaje para ese miembro.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Llamada de API personalizada]**
Este módulo le permite realizar una llamada de API personalizada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Adobe Acrobat Sign] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>Introduzca una ruta relativa a <code>https://api.[region].adobesign.com/api/rest/v6/</code></p> <p>Nota: Para obtener la lista de los puntos finales disponibles, consulte la Referencia de la API de [!DNL Adobe Sign].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] añade encabezados de autorización automáticamente.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String] </td> 
   <td> <p>Introduzca la cadena de consulta de la solicitud.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la instrucción condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Upload a transient document]</td> 
   <td> <p>Si desea cargar un documento transitorio, introduzca el archivo de origen del documento que desea cargar.</p> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL List records]**

Este módulo de acción enumera todos los registros del tipo seleccionado a los que la cuenta tiene acceso.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Adobe Acrobat Sign] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] añade encabezados de autorización automáticamente.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>Seleccione el tipo de registro del que desea recuperar registros relacionados.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Locale]</td> 
   <td> <p>Introduzca la configuración regional del usuario. Determina el idioma de la interfaz de usuario. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL External ID]</td> 
   <td>Introduzca o asigne el ID externo (un ID asignado fuera de [!DNL Adobe Acrobat Sign]) para los acuerdos que desea devolver.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Group ID]</td> 
   <td>Introduzca el ID del grupo asociado a los registros que desea enumerar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show hidden (records)]</td> 
   <td>Habilite esta opción si desea incluir registros ocultos en los resultados.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Cursor] / [!UICONTROL Start index]</td> 
   <td> <p>Introduzca el número del primer registro que debe devolver el módulo. </p> <p>Nota: Este campo se combina con el campo [!UICONTROL Maximum number of returned records] para la paginación. Por ejemplo, si el [!UICONTROL Maximum number of returned events] es 100 y el [!UICONTROL Start index] es 101, el módulo devuelve los registros 101-200 o la segunda página de resultados.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned records]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> <p>Nota: Este campo se combina con el campo [!UICONTROL Cursor] o [!UICONTROL Start Index] para la paginación. Por ejemplo, si el [!UICONTROL Maximum number of returned events] es 100 y el [!UICONTROL Start index] es 101, el módulo devuelve los registros 101-200 o la segunda página de resultados.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Parent domain URLs]</td> 
   <td> <p>Introduzca o asigne una lista separada por comas de direcciones URL de dominio principal donde las direcciones URL devueltas se pueden incorporar en Iframes. Si se deja vacío, las páginas de [!DNL Adobe Acrobat Sign] no se podrán ver en el iframe.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Leer un registro]**

Este módulo de acción recupera información de un único registro.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Adobe Acrobat Sign] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] añade encabezados de autorización automáticamente.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>Seleccione el tipo de registro del que desea recuperar registros relacionados.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record ID]</td> 
   <td>Introduzca o asigne el ID del registro que desea recuperar.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Read related records]**

Lea información adicional relacionada con un único registro.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Adobe Acrobat Sign] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] añade encabezados de autorización automáticamente.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>Seleccione el tipo de registro del que desea recuperar registros relacionados.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record ID] (Ejemplo: [!UICONTROL Account ID])</td> 
   <td>Introduzca o asigne el ID del registro del que desea recuperar registros relacionados.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Other fields]</td> 
   <td>Introduzca información en campos específicos basados en el tipo de registro y campos relacionados.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Actualizar un registro]**

Este módulo de acción actualiza un único registro en [!DNL Adobe Acrobat Sign].

>[!IMPORTANT]
>
>* Como práctica recomendada, si prevé realizar cambios sustanciales en un acuerdo, le recomendamos que cree un nuevo acuerdo en lugar de actualizar el existente.
>* Algunas actualizaciones incluyen campos obligatorios. A medida que configure la actualización, asegúrese de completar todos los campos obligatorios. Los campos obligatorios están en negrita en los módulos de [!DNL Workfront Fusion].
>



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Adobe Acrobat Sign] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] añade encabezados de autorización automáticamente.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record ID] </td> 
   <td>Introduzca o asigne el ID del registro que desea actualizar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>Seleccione el tipo de registro que desee actualizar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Other fields]</td> 
   <td> <p>Introduzca información en campos específicos basados en el tipo de registro y campos relacionados.</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Agreement]</b> </p> <p>Como práctica recomendada, si prevé realizar cambios sustanciales en un acuerdo, le recomendamos que cree un nuevo acuerdo en lugar de actualizar el existente.</p> </li> 
     <li> <p><b>[!UICONTROL Library document]</b> </p> <p> Seleccione los campos que desea actualizar y rellene los campos seleccionados:</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Status]</b> </p> <p>Seleccione el nuevo estado del documento de biblioteca.</p> </li> 
       <li> <p><b>[!UICONTROL Name]</b> </p> <p>Introduzca o asigne el nombre de plantilla de la biblioteca</p> </li> 
       <li> <p><b>[!UICONTROL Sharing mode]</b> </p> <p>Especifique quién debe tener acceso al documento de la biblioteca.</p> </li> 
       <li> <p><b>[!UICONTROL Library template type]</b> </p> <p>Para cada tipo de plantilla de biblioteca que desee utilizar, haga clic en <b>[!UICONTROL Add item]</b> y seleccione el tipo de plantilla.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL User]</b> </p> <p> Seleccione los campos que desea actualizar y rellene los campos seleccionados:</p> 
      <ul> 
       <li> <p><b>[!UICONTROL First name]</b> </p> <p>Introduzca el nombre del usuario.</p> </li> 
       <li> <p><b>[!UICONTROL Last name]</b> </p> <p>Introduzca el apellido del usuario</p> </li> 
       <li> <p><b>[!UICONTROL Company]</b> </p> <p>Introduzca el nombre de la compañía del usuario.</p> </li> 
       <li> <p><b>[!UICONTROL Phone]</b> </p> <p>Introduzca el número de teléfono del usuario</p> </li> 
       <li> <p><b>[!UICONTROL Primary group ID]</b> </p> <p>Introduzca el grupo al que se añade el nuevo usuario. Si no se escribe nada, el usuario se añadirá al grupo predeterminado de la cuenta.</p> </li> 
       <li> <p><b>[!UICONTROL Job title]</b> </p> <p>Introduzca el cargo del usuario.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Web form] ([!UICONTROL widget])</b> </p> <p>Introduzca información en campos específicos basados en el tipo de registro y campos relacionados.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Actualizar registro relacionado]**

Este módulo de acción actualiza los registros relacionados con un objeto específico.

>[!IMPORTANT]
>
>* Como práctica recomendada, si prevé realizar cambios sustanciales en un acuerdo, le recomendamos que cree un nuevo acuerdo en lugar de actualizar el existente.
>* Algunas actualizaciones incluyen campos obligatorios. A medida que configure la actualización, asegúrese de completar todos los campos obligatorios. Los campos obligatorios están en negrita en los módulos de [!DNL Workfront Fusion].
>



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Adobe Acrobat Sign] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] añade encabezados de autorización automáticamente.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>Seleccione el tipo de registro del registro al que están asociados los campos relacionados.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Agreement]/[!UICONTROL Library document]/[!UICONTROL User]/[!UICONTROL Widget ID]</td> 
   <td>Introduzca o asigne el ID del objeto con el que desea asociar el registro creado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Other fields]</td> 
   <td> <p>Introduzca información en campos específicos basados en el tipo de registro y campos relacionados.</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Agreement]</b> </p> <p>Como práctica recomendada, si prevé realizar cambios sustanciales en un acuerdo, le recomendamos que cree un nuevo acuerdo en lugar de actualizar el existente.</p> </li> 
     <li> <p><b>[!UICONTROL Library document]</b> </p> <p> Seleccione los campos que desea actualizar y rellene los campos seleccionados:</p> 
      <ul> 
       <li> <p><b>[!UICONTROL State]</b> </p> <p>Seleccione el nuevo estado del documento de biblioteca.</p> </li> 
       <li> <p><b>[!UICONTROL Note]</b> </p> <p>Escriba o asigne el texto de la nota.</p> </li> 
       <li> <p><b>[!UICONTROL Visibility]</b> </p> <p>Seleccione si el documento de biblioteca se muestra o se guía.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL User]</b> </p> <p> Seleccione los campos que desea actualizar y rellene los campos seleccionados:</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Group info list]</b> </p> <p>Rellene los campos siguientes</p> 
        <ul> 
         <li> <p><b>[!UICONTROL Status]</b> </p> <p>Seleccione el nuevo estado del usuario.</p> </li> 
         <li> <p><b>[!UICONTROL ID]</b> </p> <p>Introduzca el ID único del grupo</p> </li> 
         <li> <p><b>[!UICONTROL Is group admin]</b> </p> <p>Seleccione <b>[!UICONTROL Yes]</b> para convertir al usuario en administrador de un grupo.</p> </li> 
         <li> <p><b>Es el grupo principal</b> </p> <p>Seleccione <b>[!UICONTROL Yes]</b> para actualizar este grupo al grupo principal del usuario.</p> </li> 
         <li> <p><b>[!UICONTROL Created date]</b> </p> <p>Introduzca la fecha de creación del grupo.</p> <p>Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">Coerción de tipos en [!UICONTROL Adobe Workfront Fusion]</a>.</p> </li> 
         <li> <p><b>[!UICONTROL Name]</b> </p> <p>Introduzca o asigne el nombre del grupo.</p> </li> 
         <li> <p><b>[!UICONTROL Library document creation visible]</b> </p> <p>Esta configuración determina si el usuario puede crear documentos de la biblioteca</p> 
          <ul> 
           <li> <p>[!UICONTROL Value]</p> <p>Permitir</p> </li> 
           <li> <p>[!UICONTROL Inherited]</p> <p>Heredar la configuración de grupo del grupo o de la cuenta</p> </li> 
          </ul> </li> 
         <li> <p><b>[!UICONTROL Send restricted to workflows]</b> </p> <p>Esta configuración determina si el usuario puede crear acuerdos solo mediante flujos de trabajo.</p> 
          <ul> 
           <li> <p>[!UICONTROL Value]</p> <p>Permitir</p> </li> 
           <li> <p>[!UICONTROL Inherited]</p> <p>Heredar la configuración de grupo del grupo o de la cuenta</p> </li> 
          </ul> </li> 
         <li> <p><b>[!UICONTROL User can send]</b> </p> 
          <ul> 
           <li> <p>[!UICONTROL Value]</p> <p>Permitir</p> </li> 
           <li> <p>[!UICONTROL Inherited]</p> <p>Heredar la configuración de grupo del grupo o de la cuenta</p> </li> 
          </ul> </li> 
        </ul> </li> 
      </ul> 
      <ul> 
       <li> <p><b>[!UICONTROL State]</b> </p> <p>Seleccione el nuevo estado del usuario e introduzca un comentario sobre el motivo por el que desea activarlo o desactivarlo.</p> </li> 
       <li> <p><b>[!UICONTROL Locale]</b> </p> <p>Introduzca la configuración regional del usuario. Determina el idioma de la interfaz de usuario. </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Web form] ([!UICONTROL widget])</b> </p> <p>Introduzca información en campos específicos basados en el tipo de registro y campos relacionados.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Subir documento]**

Suba un documento transitorio. Un documento transitorio está disponible durante 7 días después de subirse.

>[!NOTE]
>
>Recomendamos subir el documento para firmarlo como documento transitorio y, a continuación, asignarlo al campo Archivo a enviar en el módulo Crear un acuerdo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Adobe Acrobat Sign] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] añade encabezados de autorización automáticamente.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record ID]</td> 
   <td>Introduzca o asigne el ID del registro que desea actualizar</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL MIME type]</td> 
   <td>Introduzca el tipo MIME del archivo original. Los tipos MIME (Multipurpose Internet Extension) son etiquetas que permiten al software identificar diferentes tipos de datos compartidos en Internet. Los servidores y exploradores web utilizan el tipo MIME para determinar qué se debe hacer con un archivo. Por ejemplo, un archivo con el tipo MIME <code>text/html</code> se procesará en un explorador de forma distinta que un archivo con el tipo MIME <code>image/jpeg</code>.</td> 
  </tr> 
 </tbody> 
</table>

**Ejemplo:** En este flujo de trabajo, el documento que se va a firmar (descargado previamente desde Workfront) se carga como un documento transitorio.

(/help/workfront-fusion/references/apps-and-modules/assets/sign-example-1-350x308.png)

El módulo [!UICONTROL Subir documento] proporciona al documento un ID [!DNL Adobe Acrobat Sign] al que se puede hacer referencia en módulos posteriores. Cuando se crea el acuerdo, el ID del documento cargado se incluye en el campo [!UICONTROL Archivos a enviar].

![Firmar ejemplo](/help/workfront-fusion/references/apps-and-modules/assets/sign-example-2-350x356.png)

+++

### Búsquedas

+++ **[!UICONTROL Buscar acuerdos]**

Este módulo de búsqueda busca los acuerdos basándose en los criterios proporcionados.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Adobe Acrobat Sign] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text filter]</td> 
   <td> <p>Buscar texto en los metadatos del acuerdo. </p> 
    <ul> 
     <li> <p><b>[!UICONTROL Find text]</b> </p> <p>Escriba el texto que desea buscar en los metadatos del acuerdo. Cada palabra es tratada como un elemento de texto independiente. </p> </li> 
     <li> <p><b>[!UICONTROL Find text in]</b> </p> <p>Seleccione los campos de metadatos en los que desea buscar texto. Si no selecciona nada, los módulos buscan todos los metadatos.</p> </li> 
    </ul> <p>El módulo devuelve cualquier acuerdo que contenga alguno de los textos introducidos en cualquiera de los campos seleccionados. Ejemplo: si introducimos “campaña de primavera” y seleccionamos las opciones Título y Nota, devuelve cualquier acuerdo con las palabras “primavera” o “campaña” en Título o Nota.</p> <p>Para obtener más información sobre la búsqueda de campos en [!DNL Adobe Acrobat Sign], consulte "Cómo funciona la búsqueda de texto" en <a href="https://helpx.adobe.com/es/sign/using/adobesign-search-users-agreements.html#HowSearchWorks">[!DNL Adobe Sign] Búsqueda: cómo funciona</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Created date]</td> 
   <td>Seleccionar fechas. El módulo devuelve solo los registros en los que la fecha de creación coincida con este criterio.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expiration date]</td> 
   <td>Seleccionar fechas. El módulo solo devuelve registros en los que la fecha de caducidad coincide con este criterio.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p role="rowheader">[!UICONTROL Modified date]</p> </td> 
   <td>Seleccionar fechas. El módulo devuelve solo los registros en los que la fecha de modificación coincide con este criterio.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL External ID]</td> 
   <td> <p> El ID externo es un ID asignado por el remitente al acuerdo que puede presentarse bajo cualquier forma, aunque esta suele ser "&lt;groupID&gt;:&lt;ID&gt;".</p> <p>Para cada ID externo que desee añadir, haga clic en <b>[!UICONTROL Add]</b> e introduzca o asigne el ID externo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Group ID]</td> 
   <td> <p>El ID de grupo es un identificador asignado cuando se creó el grupo.</p> <p>Para cada ID externo que desee añadir, haga clic en <b>[!UICONTROL Add]</b> e introduzca o asigne el ID externo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td> <p>Este es el ID asignado al acuerdo específico. </p> <p>Para cada ID externo que desee añadir, haga clic en <b>[!UICONTROL Add]</b> e introduzca o asigne el ID externo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Parent ID]</td> 
   <td> <p>Este es el ID asignado al objeto principal del acuerdo. </p> <p>Para cada ID externo que desee añadir, haga clic en <b>[!UICONTROL Add]</b> e introduzca o asigne el ID externo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Participant email]</td> 
   <td> <p>La dirección de correo electrónico de un participante. </p> <p>Para cada ID externo que desee añadir, haga clic en <b>[!UICONTROL Add]</b> e introduzca o asigne el ID externo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Role]</td> 
   <td>Seleccione las funciones que desea que incluyan los resultados devueltos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort by]</td> 
   <td>Si desea que el módulo ordene los resultados, seleccione el campo por el que desea ordenar los resultados.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort order]</td> 
   <td>Si desea que el módulo ordene los resultados, seleccione si desea ordenar de forma ascendente o descendente.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Status]</td> 
   <td>Seleccione los estados que desea que incluyan los resultados devueltos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>Seleccione los tipos de acuerdo que desea que incluyan los resultados devueltos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subtypes]</td> 
   <td>Seleccione los subtipos de acuerdo que desea que incluyan los resultados devueltos. Solo los acuerdos de plantilla de biblioteca incluyen subtipos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL User ID]</td> 
   <td> <p>El ID del usuario con el que se comparte el acuerdo.</p> <p>Para cada ID de usuario que desee añadir, haga clic en <b>[!UICONTROL Add]</b> y escriba o asigne el ID de usuario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Visibility]</td> 
   <td>Seleccione el nivel de visibilidad que desea que incluyan los resultados devueltos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start index]</td> 
   <td> <p>Introduzca la posición del primer resultado que desea devolver. Combine esto con los [!UICONTROL maximum returned results] para paginar resultados</p> <p>Ejemplo: si devuelve 100 resultados a la vez, introduzca 100 para que se devuelvan los resultados 100-200.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned results]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++
