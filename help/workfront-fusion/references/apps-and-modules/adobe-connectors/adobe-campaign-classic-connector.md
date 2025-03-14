---
title: Módulos de Adobe Campaign v7/v8
description: Con los módulos de  [!DNL Adobe Campaign] , puede iniciar un escenario de  [!DNL Adobe Workfront Fusion]  basado en eventos en su cuenta de  [!DNL Adobe Campaign]  y crear, leer o actualizar acuerdos y otros registros, buscar registros usando los criterios que haya establecido y subir documentos.
author: Becky
feature: Workfront Fusion
exl-id: 9fdff26c-c7c0-4eb8-a36f-4aeaf432b333
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 90%

---

# Módulos de [!DNL Adobe Campaign]

Con los módulos de [!DNL Adobe Campaign], puede iniciar un escenario de [!DNL Adobe Workfront Fusion] basado en los eventos de su cuenta de [!DNL Adobe Campaign v7/v8], crear, leer o actualizar registros, buscar registros con los criterios establecidos y realizar llamadas de API personalizadas.

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

Debe añadir las direcciones IP de Fusion a [!DNL Adobe Campaign].

* Para obtener instrucciones sobre cómo añadir direcciones IP a la lista de permitidos de Campaign, consulte [Adición de direcciones IP a la lista de permitidos](https://experienceleague.adobe.com/es/docs/control-panel/using/sftp-management/ip-range-allow-listing#adding-ip-addresses-allow-list) en la documentación de Adobe Campaign.
* Para obtener una lista de direcciones IP que agregar a la lista de permitidos, consulte [Configuración de direcciones IP para Fusion en la lista de permitidos de su organización](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/set-up-ip-addresses-for-fusion.md).

## Información de API de Adobe Campaign

El conector de Adobe Campaign utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.7.22</td> 
  </tr>
 </tbody> 
 </table>

## Conectar [!DNL Adobe Campaign] a [!DNL Adobe Workfront Fusion]

>[!IMPORTANT]
>
>Se recomienda encarecidamente crear una conexión servidor a servidor. Adobe Campaign ha actualizado su API para aceptar solo conexiones de servidor a servidor. Si se está conectando a la versión 8 o superior de Campaign, **debe** crear una conexión servidor a servidor.
>
>Para obtener más información sobre los nuevos requisitos de conexión de Campaign, consulte [Migración de operadores técnicos de Campaign a Adobe Developer Console](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/ims-migration.html?lang=es) en la documentación de Campaign.

1. En cualquier módulo de [!DNL Adobe Campaign], haga clic en **[!UICONTROL Añadir]** junto al campo [!UICONTROL Conexión].
1. Rellene los campos siguientes:
   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
          <td role="rowheader">[!UICONTROL Connection type]</td>
          <td>
            <p>Seleccione si va a crear una conexión básica o una conexión servidor a servidor.</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Connection name]</td>
          <td>
            <p>Introduzca un nombre para esta conexión.</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Base URL]</td>
          <td>Escriba la dirección URL base que utiliza para conectarse a la instancia de [!DNL Adobe Campaign].</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Username]</td>
          <td>Si está creando una conexión básica, introduzca su nombre de usuario de Adobe Campaign.</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Password]</td>
          <td>Si está creando una conexión básica, introduzca su contraseña de Adobe Campaign.</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client ID]</td>
          <td>Si está creando una conexión servidor a servidor, introduzca su [!DNL Adobe] [!UICONTROL Client ID]. Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]</td>
          <td>Si va a crear una conexión servidor a servidor, escriba [!DNL Adobe] [!UICONTROL Client Secret]. Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].
        </tr>
     </tbody>
    </table>
1. Haga clic en **[!UICONTROL Continuar]** para crear la conexión y volver al módulo.

## Módulos de [!DNL Adobe Campaign] y sus campos

Al configurar módulos de [!DNL Adobe Campaign], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Adobe Campaign] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

<!--* [Triggers](#triggers)-->
* [Acciones](#actions)
* [Búsquedas](#searches)

<!--### Triggers

#### [!UICONTROL Watch records]

This scheduled trigger module starts a scenario when a record changes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>For instructions on creating a connection to [!DNL Adobe Campaign], see <a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >Create a connection to [!DNL Adobe Campaign]</a> in this article.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td>Select whether you want to watch for new records, updated records, or both.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource]</td> 
   <td>Select the resource that you want to watch for.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields to include in output]</td> 
   <td>Select the fields that you want to include in the module's output.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Custom fields to include in output]</td> 
   <td>For each custom field that you want to include in output, click <b>[!UICONTROL Add]</b> and enter the name of the custom field.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned results]</td> 
   <td>Enter or map the maximum number of records you want the module to return during each scenario execution cycle.</td> 
  </tr> 
 </tbody> 
</table>-->


### Acciones

* [[!UICONTROL Create a record]](#create-a-record)
* [[!UICONTROL Eliminar un registro]](#delete-record)
* [[!UICONTROL Realizar una llamada de API personalizada]](#make-a-custom-api-call)
* [[!UICONTROL Realizar una acción]](#perform-an-action)
* [[!UICONTROL Leer un registro]](#read-a-record)
* [[!UICONTROL Suscribirse o cancelar la suscripción]](#subscribe-or-unsubscribe)
* [[!UICONTROL Actualizar un registro]](#update-record)

#### [!UICONTROL Crear un registro]

Este módulo de acción crea un nuevo registro en [!DNL Adobe Campaign].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Campaign], consulte <a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >Crear una conexión con [!DNL Adobe Campaign]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource]</td> 
   <td>Seleccione el tipo de registro de [!DNL Adobe Campaign] que desea crear. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields] </td> 
   <td>Seleccione los campos para los que desea establecer valores cuando se cree el registro y, a continuación, rellene los valores de esos campos. Los campos varían según el tipo de registro seleccionado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Custom fields]</td> 
   <td> Para cada campo personalizado que desee agregar al nuevo registro, haga clic en <b>[!UICONTROL Add item]</b> y escriba o asigne el nombre y valor del campo. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete Record]

Este módulo de acción elimina un único registro de [!DNL Adobe Campaign].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Campaign], consulte <a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >Crear una conexión con [!DNL Adobe Campaign]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource]</td> 
   <td>Seleccione el tipo de recurso que desea eliminar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Introduzca o asigne el ID del recurso que desea eliminar.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Realizar una llamada de API personalizada]

Este módulo realiza una llamada de API personalizada a la API de [!DNL Adobe Campaign]

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe Campaign], consulte <a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >Crear una conexión a [!DNL Adobe Campaign]</a> en este artículo.</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Action]</td>
      <td><p>Seleccione la acción que desea que realice la llamada de API.</p>
      <p>[!UICONTROL Execute query]</p>
      <p>[!UICONTROL Write]</p>
      <p>[!UICONTROL Get entity if more recent]</p>
      <p>[!UICONTROL Select all]</p>
      <p>[!UICONTROL Push event]</p>
    </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p>
        <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p>
        <p>[!DNL Workfront Fusion] añade el encabezado de token de [!UICONTROL x-security] automáticamente.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL XML Body]</td>
   <td> <p>Añada el contenido del cuerpo para la llamada de API en XML, sin el elemento de sesión. </td>     </tr>
  </tbody>
</table>


#### [!UICONTROL Perform an action]

Este módulo de acción realiza una acción seleccionada en un objeto de la API de [!DNL Adobe Campaign].

Para obtener información sobre acciones y campos específicos, consulte [[!DNL Adobe Campaign] : documentación de API](https://experienceleague.adobe.com/developer/campaign-api/api/p-14.html?lang=es).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Para obtener instrucciones sobre cómo crear una conexión a [!DNL Adobe Campaign], consulte <a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >Crear una conexión a [!DNL Adobe Campaign]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Action]</td> 
   <td><p>Seleccione la acción que se realizará en el objeto.</p>
   <ul>
   <li><p><b>[!DNL List]</b></p><p> Para obtener información sobre los campos disponibles, consulte <a href="#search" class="MCXref xref" >[!UICONTROL Search]</a> en este artículo. </p></li>
     <li><p><b>[!UICONTROL Get]</b></p><p> Para obtener información sobre los campos disponibles, consulte <a href="#search" class="MCXref xref" >[!UICONTROL Search]</a> en este artículo. </p></li> 
   <li><p><b>[!UICONTROL Create]</b></p><p> Para obtener información sobre los campos disponibles, consulte <a href="#create-a-record" class="MCXref xref" >[!UICONTROL Create a record]</a> en este artículo. </p></li>
   <li><p><b>[!UICONTROL Update]</b></p><p> Para obtener información sobre los campos disponibles, consulte <a href="#update-record" class="MCXref xref" >[!UICONTROL Update a record]</a> en este artículo. </p></li>
   <li><p><b>[!UICONTROL Delete]</b></p><p> Para obtener información sobre los campos disponibles, consulte <a href="#delete-record" class="MCXref xref" >[!UICONTROL Delete a record]</a> en este artículo. </p></li>
   </ul>
   </td>
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Leer un registro]

Este módulo de acción lee un registro de [!DNL Adobe Campaign].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Campaign], consulte <a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >Crear una conexión con [!DNL Adobe Campaign]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource]</td> 
   <td>Seleccione el tipo de registro de [!DNL Adobe Campaign] que desea leer.</td> 
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL ID] </td> 
   <td>Introduzca o asigne el ID del registro que desea leer.</td> 
  </tr> 
 <tr> 
   <td role="rowheader">[!UICONTROL Fields to include in output] </td> 
   <td>Seleccione los campos que desea incluir en la salida del módulo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Custom fields to include in output]</td> 
   <td>Para cada campo personalizado que desee incluir en la salida, haga clic en <b>[!UICONTROL Add]</b> e introduzca el nombre del campo personalizado.</td> 
  </tr> 
 </tbody> 
</table>


#### [!UICONTROL Suscribirse o cancelar la suscripción]

Este módulo de acción suscribe o cancela la suscripción de un usuario a un servicio de información.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Campaign], consulte <a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >Crear una conexión con [!DNL Adobe Campaign]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subscribe or unsubscribe]</td> 
   <td>Seleccione si desea suscribirse o cancelar la suscripción del servicio informativo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Service name]</td> 
   <td>Seleccione el servicio al que desea suscribirse o cancelar la suscripción.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Recipient email address] </td> 
   <td>Introduzca o asigne la dirección de correo electrónico del usuario al que desea suscribir o cancelar la suscripción al servicio informativo.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Actualizar registro]

Este módulo de acción actualiza un único registro en [!DNL Adobe Campaign].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Campaign], consulte <a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >Crear una conexión con [!DNL Adobe Campaign]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource]</td> 
   <td>Seleccione el tipo de registro de [!DNL Adobe Campaign] que desea crear.</td> 
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL ID] </td> 
   <td>Introduzca o asigne el ID del registro que desea actualizar.</td> 
  </tr> 
<tr> 
   <td role="rowheader">[!UICONTROL Fields] </td> 
   <td>Seleccione los campos para los que desea actualizar los valores y rellene los valores de esos campos. Los campos varían según el tipo de registro seleccionado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Custom fields]</td> 
   <td> Para cada campo personalizado que desee actualizar, haga clic en <b>[!UICONTROL Add item]</b> y escriba o asigne el nombre y valor del campo. </td> 
  </tr> 
 </tbody> 
</table>

### Búsquedas

#### [!UICONTROL Búsqueda]

Este módulo de búsqueda devuelve registros basados en los criterios especificados.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Campaign], consulte <a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >Crear una conexión con [!DNL Adobe Campaign]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource]</td> 
   <td>Seleccione el tipo de registro de [!DNL Adobe Campaign] que desea crear. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search criteria]</td> 
   <td>Introduzca los campos y valores que desea que utilice la búsqueda. Los campos dependen del recurso seleccionado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td> 
  </tr> 
 </tbody> 
</table>
