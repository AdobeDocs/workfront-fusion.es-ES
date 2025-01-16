---
title: Módulos de Adobe Target
description: En un escenario de  [!DNL Adobe Workfront Fusion]  puede automatizar los flujos de trabajo que utilizan módulos de  [!DNL Adobe Target], as well as connect it to multiple third-party applications and services. [!DNL Adobe Target]  que le permiten crear, leer, actualizar o eliminar registros, enumerar todos los registros de un tipo determinado, buscar registros según los criterios especificados o realizar una llamada de API personalizada a la API de  [!DNL Adobe Target] .
author: Becky
feature: Workfront Fusion
exl-id: f3c1ed7b-b69b-478a-8240-1a2ab89e11e5
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1923'
ht-degree: 80%

---

# Módulos de [!DNL Adobe Target]

En un escenario de [!DNL Adobe Workfront Fusion], puede automatizar los flujos de trabajo que utilizan [!DNL Adobe Target], así como conectarlo a varias aplicaciones y servicios de terceros. Los módulos de [!DNL Adobe Target] le permiten crear, leer, actualizar o eliminar registros, enumerar todos los registros de un tipo determinado, buscar registros basados en los criterios especificados o realizar una llamada de API personalizada a la API de [!DNL Adobe Target].


Si necesita instrucciones sobre cómo crear un escenario, vea los artículos en [Crear un escenario: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

## Requisitos de acceso

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto"> 
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
    </tr>
  </tbody>
</table>


Para saber qué plan, tipo de licencia o acceso tiene, póngase en contacto con el administrador de [!DNL Workfront].

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## Requisitos previos

Antes de poder usar el conector de [!DNL Adobe Target], debe asegurarse de que se cumplen los siguientes requisitos previos:

* Debe tener una cuenta de [!DNL Adobe Target] activa.

## Información de API de Adobe Target

El conector de Adobe Target utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.7.33</td> 
  </tr>
 </tbody> 
 </table>

## Crear una conexión a [!DNL Adobe Target]

>[!IMPORTANT]
>
>Las conexiones creadas después del 3 de junio de 2024 requieren una conexión de servidor a servidor de Adobe Target.
>
>* Las conexiones de cuenta de servicio existentes seguirán funcionando hasta enero de 2025. Debe reemplazar las conexiones de su cuenta de servicio con las conexiones de servidor a servidor de Adobe Target antes de enero de 2024.
>* Debe ser un desarrollador de su organización para crear una conexión de servidor a servidor de Adobe Target. La función de desarrollador se establece en Adobe Admin Console.

Para crear una conexión para los módulos de [!DNL Adobe Target]:

1. Haga clic en **[!UICONTROL Add]** junto al cuadro Conexión.

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
        <td role="rowheader">[!UICONTROL Connection type]</td>
        <td>Seleccione si va a crear una conexión de cuenta de servicio o una conexión de servidor a servidor de Adobe Target.<p><b>IMPORTANTE</b>: Las conexiones creadas después del 3 de junio de 2024 requieren una conexión de servidor a servidor de Adobe Target. Las conexiones de cuenta de servicio existentes seguirán funcionando hasta enero de 2025. Debe reemplazar las conexiones de su cuenta de servicio con las conexiones de servidor a servidor de Adobe Target antes de enero de 2024.
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>Seleccione si desea conectarse a un entorno de producción o de no producción.
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>Seleccione si desea conectarse a una cuenta de servicio o a una personal.
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Escriba su ID de cliente de [!DNL Adobe]. Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Escriba su secreto de cliente de [!DNL Adobe]. Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Technical account ID]</td>
        <td>Escriba su ID de cuenta técnica de [!DNL Adobe]. Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Organization ID]</td>
        <td>Introduzca el ID de organización de [!DNL Adobe]. Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Tenant]</td>
        <td>
          <p> Para localizar a su inquilino, inicie sesión en [!DNL Adobe Experience Cloud], abra [!DNL Target] y haga clic en la tarjeta [!DNL Target]. Utilice el valor ID de inquilino como se indica en el subdominio URL.</p>
          <p>Por ejemplo, si la URL al iniciar sesión en [!DNL Adobe Target] es <code>&lt;https://mycompany.experiencecloud.adobe.com/...></code>, el identificador de inquilino es “mycompany”.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Meta Scopes]</td>
        <td>Introduzca <code>ent_marketing_sdk</code>       </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Private key]</td>
        <td>
          <p>Introduzca la clave privada que se generó cuando se crearon sus credenciales en [!DNL Adobe Developer Console]. </p>
          <p>Para extraer la clave privada o el certificado:</p>
          <ol>
            <li value="1">
              <p>Haga clic en <b>[!UICONTROL Extract]</b>.</p>
            </li>
            <li value="2">
              <p>Seleccione el tipo de archivo que va a extraer.</p>
            </li>
            <li value="3">
              <p>Seleccione el archivo que contiene la clave privada o el certificado.</p>
            </li>
            <li value="4">
              <p>Introduzca la contraseña del archivo.</p>
            </li>
            <li value="5">
              <p>Haga clic en <b>[!UICONTROL Save]</b> para extraer el archivo y volver a la configuración de conexión.</p>
            </li>
          </ol>
        </td>
      </tr>
    </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continue]** para guardar la conexión y volver al módulo.

## Módulos de [!DNL Adobe Target] y sus campos

Al configurar módulos de [!DNL Adobe Target], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Adobe Target] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Acciones](#actions)

* [Búsquedas](#searches)


### Acciones

* [[!UICONTROL Create a record]](#create-a-record)

* [[!UICONTROL Make a custom API call]](#make-a-custom-api-call)

* [[!UICONTROL Delete a record]](#delete-a-record)

* [[!UICONTROL Read a record]](#read-a-record)

* [[!UICONTROL Update a record]](#update-a-record)


#### [!UICONTROL Create a record]

Este módulo de acción crea una actividad, una oferta o un público AB o XT.

<table style="table-layout:auto"> 
<col/>
<col/>
<tbody>
  <tr>
    <td role="rowheader">[!UICONTROL Connection]</td>
    <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Target], consulte <a href="#create-a-connection-to-adobe-target" class="MCXref xref" >Crear una conexión con [!DNL Adobe Target]</a> en este artículo.</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Record type]</td>
    <td>
      <p>Seleccione el tipo de registro que desea crear.</p>
      <ul>
        <li>
        <b>Propiedad</b><p>Para información detallada sobre los campos, consulte <a href="https://developer.adobe.com/target/administer/admin-api/#tag/Properties/operation/createProperty">Crear una propiedad</a> en la documentación de la API de Adobe Target.</p>
        </li>
        <li>
        <b>Oferta de recomendación</b><p>Para obtener información detallada sobre los campos, consulte <a href="https://developer.adobe.com/target/administer/admin-api/#tag/Offers/operation/createOffer">Crear una nueva oferta de recomendación</a> en la documentación de la API de Adobe Target.</p>
        </li>
        <li>
          <b>[!UICONTROL Offer JSON]</b>
          <p>Continúe hasta <a href="#offer-fields" class="MCXref xref" >Campos de oferta</a>.</p>
        </li>
        <li>
          <b>[!UICONTROL Offer Content]</b>
          <p>Continúe hasta <a href="#offer-fields" class="MCXref xref" >Campos de oferta</a>.</p>
        </li>
        <li>
        <b>Entorno</b><p>Para obtener información más detallada sobre los campos, consulte <a href="https://developer.adobe.com/target/administer/admin-api/#tag/Environments/operation/createEnvironment">Crear entorno</a> en la documentación de la API de Adobe Target.</p>
        </li>
        <li>
          <b>[!UICONTROL Audience]</b>
          <p>Para obtener información detallada sobre los campos, consulte <a href="https://developer.adobe.com/target/administer/admin-api/#tag/Audiences/operation/createAudience_1_1">Crear audiencia</a> en la documentación de la API de Adobe Target.</p>
        </li>
        <li>
          <b>[!UICONTROL AB Activity]</b>
          <p>Para obtener información detallada sobre los campos, consulte <a href="https://developer.adobe.com/target/administer/admin-api/#tag/Activities/operation/createActivity_4_1">Crear actividad AB</a> en la documentación de la API de Adobe Target.</p>
        </li>
        <li>
          <b>[!UICONTROL XT Activity]</b>
          <p>Continúe hasta <a href="#xt-activity-fields" class="MCXref xref" >Campos de actividad XT</a>.</p>
        </li>
        <li>
          <b>[!UICONTROL AP Activity]</b>
          <p>Para obtener información detallada sobre los campos, consulte <a href="https://developer.adobe.com/target/administer/admin-api/#tag/Activities/operation/createActivity_2">Crear actividad AP</a> en la documentación de la API de Adobe Target.</p>
        </li>
        <li>
          <b>[!UICONTROL Response Token]</b>
          <p>Para obtener información detallada sobre los campos, consulte <a href="https://developer.adobe.com/target/administer/admin-api/#tag/Response-tokens/operation/createResponseToken">Crear token de respuesta</a> en la documentación de la API de Adobe Target.</p>
        </li>
      </ul>
    </td>
  </tr>
</tbody>
</table>

<!--

##### AB Activity fields

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Name]</td>
      <td>Enter or map a name for this activity. The name can be no more than 250 characters.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Options]</td>
      <td>
        <p>For each option that you want to add to the activity, click <b>[!UICONTROL Add item]</b> and fill in the following fields:</p>
        <ul>
          <li>
            <p><b>[!UICONTROL Option local ID]</b>
            </p>
            <p>Enter or map a string to be used to track the option across API requests.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Name]</b>
            </p>
            <p>Enter or map a name for the option. The name must be no more than 250 characters.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Offer ID]</b>
            </p>
          </li>
          <li>
            <p>Select or map the Offer associated with the option.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Mboxes]</td>
      <td>
        <p>For each Mbox that you want to add to the activity, click <b>[!UICONTROL Add item]</b> and fill in the following fields:</p>
        <ul>
          <li>
            <p>[!UICONTROL Audience IDs]</p>
            <p>For each audience that you want to add to the Mbox, click <b>[!UICONTROL Add item]</b> and select the Audience ID.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Location local ID]</b>
            </p>
            <p>Enter or map a string to be used to track the location across API requests.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Name]</b>
            </p>
            <p>Enter or map a name for the Location. The name must be no more than 250 characters.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Selectors]</td>
      <td>
        <p>For each selector that you want to add to the activity, click <b>[!UICONTROL Add item]</b> and fill in the following fields:</p>
        <ul>
          <li>
            <p>[!UICONTROL Audience IDs]</p>
            <p>For each audience that you want to add to the Mbox, click <b>[!UICONTROL Add item]</b> and select the Audience ID.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Location local ID]</b>
            </p>
            <p>Enter or map a string to be used to track the location across API requests.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Selector]</b>
            </p>
            <p>Enter or map a string to be used to track the location across API requests.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Name]</b>
            </p>
            <p>Enter or map a name for the Location. The name must be no more than 250 characters.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Experiences]</td>
      <td>
        <p>A list of locations on the page where the content offer is served. A location contains the following:
</p>
        <ul>
          <li>
            <p><b>[!UICONTROL Experience local ID]</b>
            </p>
            <p>Enter or map the ID of the experience</p>
          </li>
          <li>
            <p><b>[!UICONTROL Name]</b>
            </p>
            <p>Enter or map the name of the experience
</p>
          </li>
          <li>
            <p><b>[!DNL Audience IDs]</b>
            </p>
            <p>For each audience that you want to see the experience, click <b>[!UICONTROL Add item]</b> and enter the Audience ID.
</p>
          </li>
          <li>
            <p><b>[!UICONTROL Visitor Percentage]</b>
            </p>
            <p>Enter or map the percentage of visitors that is allocated to the experience</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Metrics]</td>
      <td><p>For details on metrics, see <a href="https://developer.adobe.com/target/administer/admin-api/#tag/Activities/operation/createActivity_4_1">Create AB activity</a> in the Adobe Target API documentation.</p> </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Third Party ID]</td>
      <td>Enter or map an ID to identify this activity. You can choose this ID. This ID must not be the same as another activity, and can be no more than 250 characters.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Starts at]</td>
      <td>Enter or map the date and time to start the activity in the format <code>YYYY-MM-DD hh:mm:ss.z</code>.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Ends at]</td>
      <td>Enter or map the date and time to end the activity in the format <code>YYYY-MM-DD hh:mm:ss.z</code>.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL State]</td>
      <td>
        <p>Enter or map the state of the activity.</p>
        <ul>
          <li>
            <p>[!UICONTROL Approved]</p>
          </li>
          <li>
            <p>[!UICONTROL Deactivated]</p>
          </li>
          <li>
            <p>[!UICONTROL Paused]</p>
          </li>
          <li>
            <p>[!UICONTROL Saved] </p>
          </li>
          <li>
            <p>[!UICONTROL Deleted]</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Priority]</td>
      <td>Enter a number that defines the priority of the activity. Higher numbers have higher priority. This value must be between 0 and 999. The default value is 5.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Auto-allocate traffic]</td>
      <td>
        <p>Enable this option to auto-allocate traffic. Auto-allocating sends more traffic to the more successful experience.</p>
        <p>Select or map the evaluation criteria by which to judge which experience is more successful.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>Enter or map the workspace that the activity is associated with</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Property IDs] </td>
      <td>For each property that you want to add to the activity, click <b>[!UICONTROL Add item]</b> and select or map the property's ID.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Reporting audiences]</td>
      <td>
        <p>For each reporting audience that you want to add to the activity, click [!UICONTROL Add item] and enter the following information:</p>
        <ul>
          <li>
            <p><b>[!UICONTROL Reporting Audience local ID]</b>
            </p>
            <p>Enter or map a string to be used to track the Reporting Audience across API requests.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Audience ID]</b>
            </p>
            <p>Enter or map the Segment to be used in reporting</p>
          </li>
          <li>
            <p><b>[!UICONTROL Metric local ID]</b>
            </p>
            <p>Enter or map a string to be used to track the metric across API requests.</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

-->

##### Campos de actividad XT

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Name]</td>
      <td>Introduzca o asigne un nombre para esta actividad. El nombre no puede tener más de 250 caracteres.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Options]</td>
      <td>
        <p>Para cada opción que desee agregar a la actividad, haga clic en <b>[!UICONTROL Add item]</b> y rellene los campos siguientes:</p>
        <ul>
          <li>
            <p><b>[!UICONTROL Option local ID]</b>
            </p>
            <p>Introduzca o asigne una cadena para utilizar en el seguimiento de la opción entre las solicitudes de API.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Name]</b>
            </p>
            <p>Introduzca o asigne un nombre para la opción. El nombre no debe tener más de 250 caracteres.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Offer ID]</b>
            </p>
          </li>
          <li>
            <p>Seleccione o asigne la oferta asociada a la opción. </p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Locations]</td>
      <td>
        <p>Para cada Mbox que desee agregar a la actividad, haga clic en <b>[!UICONTROL Add item]</b> y rellene los campos siguientes:</p>
        <ul>
          <li>
            <p>[!UICONTROL Audience IDs]</p>
            <p>Para cada audiencia que desee agregar al mbox, haga clic en <b>[!UICONTROL Add item]</b> y seleccione el ID de audiencia.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Location local ID]</b>
            </p>
            <p>Introduzca o asigne una cadena para utilizarla para rastrear la ubicación entre las solicitudes de API.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Name]</b>
            </p>
            <p>Introduzca o asigne un nombre para la ubicación. El nombre no debe tener más de 250 caracteres.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Experiences]</td>
      <td>
        <p>Una lista de ubicaciones en la página donde se sirve la oferta de contenido. Una ubicación contiene lo siguiente:
</p>
        <ul>
          <li>
            <p><b>[!UICONTROL Experience local ID]</b>
            </p>
            <p>Introduzca o asigne el ID de la experiencia</p>
          </li>
          <li>
            <p><b>[!UICONTROL Name]</b>
            </p>
            <p>Introduzca o asigne el nombre de la experiencia

</p>
          </li>
          <li>
            <p><b>[!DNL Audience IDs]</b>
            </p>
            <p>Para cada audiencia para la que quiera ver la experiencia, haga clic en <b>[!UICONTROL Add item]</b> e introduzca el ID de audiencia.

</p>
          </li>
          <li>
            <p><b>[!UICONTROL Visitor Percentage]</b>
            </p>
            <p>Introduzca o asigne el porcentaje de visitantes asignado a la experiencia</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Metrics]</td>
      <td> </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Third Party ID]</td>
      <td>Introduzca o asigne un ID para identificar esta actividad. Puede elegir este ID. Este ID no debe ser el mismo que otra actividad y no puede tener más de 250 caracteres.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Starts at]</td>
      <td>Escriba o asigne la fecha y la hora de inicio de la actividad en el formato <code>YYYY-MM-DD hh:mm:ss.z</code>.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Ends at]</td>
      <td>Introduzca o asigne la fecha y la hora de finalización de la actividad en el formato <code>YYYY-MM-DD hh:mm:ss.z</code>.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL State]</td>
      <td>
        <p>Introduzca o asigne el estado de la actividad.</p>
        <ul>
          <li>
            <p>[!UICONTROL Approved]</p>
          </li>
          <li>
            <p>[!UICONTROL Deactivated]</p>
          </li>
          <li>
            <p>[!UICONTROL Paused]</p>
          </li>
          <li>
            <p>[!UICONTROL Saved] </p>
          </li>
          <li>
            <p>[!UICONTROL Deleted]</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Priority]</td>
      <td>Introduzca un número que defina la prioridad de la actividad. Los números más altos tienen mayor prioridad. Este valor debe estar comprendido entre 0 y 999. El valor predeterminado es 5.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Auto-allocate traffic]</td>
      <td>
        <p>Habilite esta opción para asignar automáticamente el tráfico. La asignación automática envía más tráfico a una experiencia con más éxito.</p>
        <p>Seleccione o asigne los criterios de evaluación con los que juzgar qué experiencia tiene más éxito.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>Introduzca o asigne el espacio de trabajo con el que está asociada la actividad</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Property IDs] </td>
      <td>Para cada propiedad que desee agregar a la actividad, haga clic en <b>[!UICONTROL Add item]</b> y seleccione o asigne el ID de la propiedad.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Reporting audiences]</td>
      <td>
        <p>Para cada audiencia de informes que desee agregar a la actividad, haga clic en [!UICONTROL Add item] e introduzca la siguiente información:</p>
        <ul>
          <li>
            <p><b>[!UICONTROL Reporting Audience local ID]</b>
            </p>
            <p>Introduzca o asigne una cadena que se utilizará para realizar un seguimiento del público de informes a través de las solicitudes de API.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Audience ID]</b>
            </p>
            <p>Introduzca o asigne el segmento que se utilizará en los informes</p>
          </li>
          <li>
            <p><b>[!UICONTROL Metric local ID]</b>
            </p>
            <p>Introduzca o asigne una cadena que se utilizará para realizar un seguimiento de la métrica a través de las solicitudes de API.</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

##### Campos de oferta

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Name]</td>
      <td>Introduzca o asigne un nombre para esta actividad. El nombre no puede tener más de 250 caracteres.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Content]</td>
      <td>
        <p>Introduzca o asigne el contenido de la oferta que se mostrará al usuario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>
        <p>Introduzca o asigne el ID del espacio de trabajo asociado a la oferta. Si se deja en blanco, la oferta se asocia al espacio de trabajo predeterminado de la cuenta. Esta funcionalidad se aplica solamente a cuentas Premium de [!DNL Target].</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>
        <p>Introduzca o asigne la fecha y la hora de modificación de esta oferta.</p>
      </td>
    </tr>
  </tbody>
</table>

<!--

##### Audience fields

>[!NOTE]
>
>Audiences created through Workfront Fusion can only be edit in Fusion or through the API. They cannot be edited from within Target.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Name]</td>
      <td>Enter or map a name for this audience. The name can be no more than 250 characters.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Description]</td>
      <td>
        <p>Enter or map a description of this audience.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Origin]</td>
      <td>
        <p>Select whether this audience's origin is from Target or from the cloud.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Target Rule]</td>
      <td>
        <p>Enable the toggle to make rules AND, that is, all rules must be applied.</p>
        <p>For each rule that you want to apply to the audience, click <b>[!UICONTROL Add item]</b> and enter the JSON of the rule you want to apply. </p>
        <div class="example"><span class="autonumber"><span><b>Example: </b></span></span>
          <p>Example 1:</p>
          <p ><code>&lbrace;</code></p>
                    <p ><code>                "page": "url",</code>
                    </p>
                    <p><code>                "equals":&lbrack;</code>
                    </p>
                    <p ><code>                    "http://www.myhomepage.com/"</code>
                    </p>
                    <p><code>                &rbrack;</code>
                    </p>
                    <p ><code>            &rbrace;,</code>
                    </p>
                    <p>Example 2</p>
                    <p ><code>            &lbrace;</code>
                    </p>
                    <p><code>                "geo": "region",</code>
                    </p>
                    <p><code>                "matches": &lbrack;</code>
                    </p>
                    <p ><code>                    "california"</code>
                    </p>
                    <p ><code>                &rbrack;</code>
                    </p>
                    <p ><code>            &rbrace;</code>
                    </p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>
        <p>Enter or map the ID of the workspace associated with the audience. If left blank, the offer is associated with the default workspace of the account. This functionality applies only to [!DNL Target Premium] accounts.</p>
      </td>
    </tr>
  </tbody>
</table>

-->

#### [!UICONTROL Make a custom API call]

Este módulo realiza una llamada de API personalizada a la API de [!DNL Adobe Target].

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Target], consulte <a href="#create-a-connection-to-adobe-target" class="MCXref xref" >Crear una conexión con [!DNL Adobe Target]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL [!DNL Target] URL base]</td>
      <td>Escriba o asigne la dirección URL base de [!DNL Target].</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Path]</p>
      </td>
      <td>
        <p>Introduzca una ruta relativa a {baseURL}/</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
      </td>
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de petición HTTP en [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p>
        <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p>
        <p>[!DNL Workfront Fusion] añade automáticamente encabezados de autorización y encabezados x-api-key.</p>
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
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>

#### [!UICONTROL Delete a record]

Este módulo de acción elimina una sola actividad AB, actividad XT, oferta o audiencia.

<table style="table-layout:auto"> 
<col/>
<col/>
<tbody>
  <tr>
    <td role="rowheader">[!UICONTROL Connection]</td>
    <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Target], consulte <a href="#create-a-connection-to-adobe-target" class="MCXref xref" >Crear una conexión con [!DNL Adobe Target]</a> en este artículo.</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Record type]</td>
    <td>Seleccione el tipo de registro que desea eliminar.</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Record ID]</td>
    <td>Introduzca o asigne el ID del registro que desea eliminar.</td>
  </tr>
</tbody>
</table>

#### [!UICONTROL Read a record]

Este módulo de acción recupera datos de una sola actividad, oferta, audiencia, propiedad o informe.

<table style="table-layout:auto"> 
<col/>
<col/>
<tbody>
  <tr>
    <td role="rowheader">[!UICONTROL Connection]</td>
    <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Target], consulte <a href="#create-a-connection-to-adobe-target" class="MCXref xref" >Crear una conexión con [!DNL Adobe Target]</a> en este artículo.</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Record type]</td>
    <td>Seleccione el tipo de registro que desea leer.</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Record ID]</td>
    <td>Introduzca o asigne el ID del registro que desea leer.</td>
  </tr>
</tbody>
</table>

#### [!UICONTROL Update a record]

Este módulo de acción actualiza un registro en Target.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Target], consulte <a href="#create-a-connection-to-adobe-target" class="MCXref xref" >Crear una conexión con [!DNL Adobe Target]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Record type]</td>
      <td>
        <p>Seleccione el tipo de registro que desee actualizar.</p>
       </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Field names]</td>
      <td>Seleccione los campos que desee actualizar. Los campos aparecen a continuación.
          <p>Para obtener información detallada sobre los campos, consulte la <a href="https://developer.adobe.com/target/administer/admin-api/">documentación de la API de Adobe Target</a>.</p>
      </td>
    </tr>
  </tbody>
</table>

### Búsquedas

* [[!UICONTROL Get records]](#get-records)

* [[!UICONTROL Search]](#search)


#### [!UICONTROL Get records]

Este módulo de búsqueda recupera una lista de los registros del tipo seleccionado.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Target], consulte <a href="#create-a-connection-to-adobe-target" class="MCXref xref" >Crear una conexión con [!DNL Adobe Target]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Record type]</td>
      <td>Seleccione el tipo de registro que desee actualizar.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Sort by]</td>
      <td>Para cada campo por el que desee ordenar, haga clic en <b>[!UICONTROL Add item]</b> y seleccione el campo y si los resultados devueltos deben ser ascendentes o descendentes.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Starts At]</td>
      <td>
        <p>Introduzca la fecha más antigua cuyos registros desea recuperar. </p>
        <p>Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos en [!DNL Adobe Workfront Fusion]</a>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Ends At]</td>
      <td>
        <p>Introduzca la fecha más reciente cuyos registros desea recuperar. </p>
        <p>Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos en [!DNL Adobe Workfront Fusion]</a>.</p>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Search]

Este módulo de búsqueda busca Actividades, Ofertas o Públicos basándose en los criterios especificados.

<table style="table-layout:auto"> 
<col/>
<col/>
<tbody>
  <tr>
    <td role="rowheader">[!UICONTROL Connection]</td>
    <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Target], consulte <a href="#create-a-connection-to-adobe-target" class="MCXref xref" >Crear una conexión con [!DNL Adobe Target]</a> en este artículo.</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Record type]</td>
    <td>Seleccione el tipo de registro que desee actualizar.</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Sort by]</td>
    <td>Para cada campo por el que desee ordenar, haga clic en <b>[!UICONTROL Add item]</b> y seleccione el campo y si los resultados devueltos deben ser ascendentes o descendentes.</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Search criteria]</td>
    <td>Para cada regla que desee configurar, seleccione el campo, el operador y el valor. Haga clic en <b>[!UICONTROL Add AND rule]</b> para crear reglas adicionales.</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Offset]</td>
    <td>
      <p>Introduzca el número de la primera respuesta que desea que devuelva el módulo. La primera respuesta devuelta tiene un desplazamiento de <code>0</code>. Utilice este campo en combinación con el campo [!UICONTROL Maximum number of returned results] para paginar las respuestas.</p>
      <p>Por ejemplo, para ver la tercera página de respuestas, cuando cada página tenga diez respuestas, establezca [!UICONTROL Offset] en 20 y [!UICONTROL Maximum number of returned] resultados en 10.</p>
    </td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Limit]</td>
    <td>
      <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario. Utilice este campo en combinación con el campo [!UICONTROL Offset] para paginar las respuestas.</p>
      <p>Por ejemplo, para ver la tercera página de respuestas, cuando cada página tenga diez respuestas, establezca [!UICONTROL Offset] en 20 y [!UICONTROL Maximum number of returned] resultados en 10.</p>
    </td>
  </tr>
</tbody>
</table>
