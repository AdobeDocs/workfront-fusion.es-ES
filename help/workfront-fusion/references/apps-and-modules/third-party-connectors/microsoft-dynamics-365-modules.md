---
title: Módulos de Microsoft Dynamics 365
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan Microsoft Dynamics 365, así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: 16ae173b-10ce-481d-8f6c-1df0e65f7c0e
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1860'
ht-degree: 75%

---

# [!DNL Microsoft Dynamics 365 modules]

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!DNL Microsoft Dynamics 365], así como conectarlo a varias aplicaciones y servicios de terceros.

>[!NOTE]
>
>El conector de [!DNL Microsoft Dynamics 365] no admite [!DNL Dynamics Finance and Operations].
>
>Para obtener información acerca del conector [!DNL Microsoft Dynamics 365 Finance and Operations], vea [[!DNL Microsoft Dynamics 365 Finance and Operations] módulos](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/dynamics-finance-operations-modules.md).

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

Para usar [!DNL Microsoft Dynamics] 365, debe tener una cuenta de [!DNL Microsoft Dynamics 365].

## Conectar Microsoft Dynamics 365 a Workfront Fusion

Puede crear una conexión con su cuenta de [!DNL Microsoft Dynamics 365] directamente desde un módulo de [!DNL Microsoft Dynamics 365].

>[!NOTE]
>
>Algunas aplicaciones de Microsoft utilizan la misma conexión, que está vinculada a permisos de usuario individuales. Por lo tanto, al crear una conexión, la pantalla de consentimiento de permisos muestra los permisos que se otorgaron previamente a la conexión de este usuario, además de cualquier nuevo permiso que sea necesario para la aplicación actual.
>
>Por ejemplo, si a un usuario se le han otorgado permisos de &quot;Leer tabla&quot; a través del conector de Excel y luego crea una conexión en el conector de Outlook para leer correos electrónicos, la pantalla de consentimiento de permisos mostrará tanto el permiso de &quot;Leer tabla&quot; ya otorgado como el nuevo permiso requerido de &quot;Escribir correo electrónico&quot;.

1. En cualquier módulo de [!DNL Microsoft Dynamics 365], haga clic en **[!UICONTROL Añadir]** junto al campo [!UICONTROL Conexión].


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
          <td>Seleccione si le importa conectarse a una cuenta de servicio o a una cuenta personal.</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client ID]<p>(Opcional)</p></td>
          <td>Escriba su [!UICONTROL Client ID] [!DNL Microsoft Dynamics].</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]<p>(Opcional)</p></td>
          <td>Introduzca su [!DNL Microsoft Dynamics] [!UICONTROL Client Secret].
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Authentication URL]</td>
          <td>Introduzca la dirección URL que utilizará su instancia de Workfront para autenticar esta conexión. <p>El valor predeterminado es <code>https://oauth.my.workfront.com/integrations/oauth2</code>.</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Resource]</td>
          <td>escriba la dirección de su cuenta de [!DNL Dynamics 365], sin <code>>https://</code>.</p>
        </tr>
      </tbody>
    </table>
1. Haga clic en **[!UICONTROL Continuar]** para crear la conexión y volver al módulo.

>[!NOTE]
>
>Al registrar Workfront Fusion en su portal [!DNL Microsoft Azure], utilice el siguiente URI de redirección:
>
>* `https://app.workfrontfusion.com/oauth/cb/workfront-microsoft-dynamics2`


## Módulos de [!DNL Microsoft Dynamics 365] y sus campos

Al configurar módulos de [!DNL Microsoft Dynamics 365], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL Microsoft Dynamics 365] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Activadores](#triggers)
* [Acciones](#actions)
* [Búsquedas](#searches)

### Activadores

* [[!UICONTROL Watch Records (Real Time)]](#watch-records-real-time)
* [[!UICONTROL Watch Records (Scheduled)]](#watch-records-scheduled)

#### [!UICONTROL Watch Records (Real Time)]

Este módulo activador instantáneo ejecuta un escenario cuando se crea o actualiza el registro (objeto) especificado en [!DNL Dynamics 365]. 

Se requiere un webhook en este módulo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>Seleccione el webhook que desee utilizar para este módulo. </p> <p>Para añadir un nuevo webhook:</p> 
    <ol> 
     <li value="1"> <p>Haga clic en <strong>[!UICONTROL Add]</strong> a la derecha del campo Webhook</p> </li> 
     <li value="2"> <p>En el campo de nombre <strong>[!UICONTROL Webhook]</strong>, escriba un nombre descriptivo para el webhook.</p> </li> 
     <li value="3"> <p>En el campo <strong>[!UICONTROL Conexión]</strong>, seleccione la Conexión que desea utilizar.</p> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Microsoft Dynamics 365] a Workfront Fusion, consulte <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Microsoft Dynamics 365] a Workfront Fusion</a> en este artículo. </p> </li> 
     <li value="4"> <p>Haga clic en <strong>[!UICONTROL Save]</strong> para guardar el webhook y volver al módulo.</p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Records (Scheduled)]

Este módulo de déclencheur programado ejecuta un escenario cuando se crea o actualiza un registro del objeto especificado después de la última ejecución programada de este escenario.

La salida del módulo indica si el registro que ha encontrado es nuevo o está actualizado. Si el registro se agregó y se actualizó a la vez en el período de tiempo, se devuelve como un registro nuevo.

Esto sucede en un intervalo programado de forma regular que usted especifica.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> "
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Microsoft Dynamics 365] a Workfront Fusion, consulte <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Microsoft Dynamics 365] a Workfront Fusion</a> en este artículo. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include]</td> 
   <td>Seleccione si desea que el módulo vea <strong>[!UICONTROL Solo registros nuevos]</strong>, <strong>[!UICONTROL Solo registros actualizados]</strong> o <strong>[!UICONTROL Registros nuevos y actualizados]</strong>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>Elija el tipo de registro de [!UICONTROL Microsoft Dynamics 365] que desea que vea el escenario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Seleccione la información que desea incluir en el paquete de salida para este módulo. Los campos están disponibles en función del tipo de entidad seleccionado.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Max Records]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Acciones

* [[!UICONTROL Create Record]](#create-record)
* [[!UICONTROL Make an API Call]](#make-an-api-call)
* [[!UICONTROL Delete Record]](#delete-record)
* [[!UICONTROL Read Records]](#read-records)
* [[!UICONTROL Actualizar registro]](#update-record)


#### [!UICONTROL Create Record]

Este módulo de acción crea una entidad, como una cita o una tarea.

Especifique la información sobre la entidad que desea crear.

El módulo devuelve el ID de la nueva entidad y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Microsoft Dynamics 365] a Workfront Fusion, consulte <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Microsoft Dynamics 365] a Workfront Fusion</a> en este artículo. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>Seleccione el tipo de entidad que desea que cree el módulo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select Fields to Map]</td> 
   <td>Seleccione los campos para los que desea incluir valores cuando se cree el registro. Los campos disponibles dependen del tipo de entidad.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Property fields]</td> 
   <td> Estos son los campos que ha seleccionado. Introduzca el valor que desea que tenga el registro para una propiedad determinada. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete Record]

Este módulo de acción elimina una entidad.

Especifique el ID de la entidad.

El módulo devuelve el ID de la entidad y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Microsoft Dynamics 365] a Workfront Fusion, consulte <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Microsoft Dynamics 365] a Workfront Fusion</a> en este artículo. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td> <p>Seleccione el tipo de entidad que desea que elimine el módulo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td> <p>Introduzca o asigne el identificador único de [!DNL Microsoft Dynamics 365] del registro que desea que elimine el módulo.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Realizar una llamada de API]

Este módulo de acción le permite realizar una llamada autenticada personalizada a la API de [!DNL Microsoft Dynamics 365]. De este modo, puede crear una automatización del flujo de datos que no puedan realizar los otros módulos de [!DNL Microsoft Dynamics 365].

El módulo devuelve información sobre el código de estado, los encabezados y el cuerpo. Puede asignar esta información en módulos subsiguientes en el escenario.

Para obtener más información, consulte la documentación de [!DNL Microsoft] acerca del uso de [!DNL Dynamics 365 Customer Engagement Web API].

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Microsoft Dynamics 365] a Workfront Fusion, consulte <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Microsoft Dynamics 365] a Workfront Fusion</a> en este artículo. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> <p>Escriba una ruta relativa a <code>&lt;Instance URL>/api/data/v9.1/</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> <p>Para obtener más </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion añade los encabezados de autorización para usted.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Añada la consulta para la llamada de API en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"name":"something-urgent"}</code></p> </td> 
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

#### [!UICONTROL Read Records]

Este módulo de acción lee datos de una sola entidad en [!DNL Microsoft Dynamics 365].

Especifique el ID de la entidad.

El módulo devuelve el ID de la entidad y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Microsoft Dynamics 365] a Workfront Fusion, consulte <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Microsoft Dynamics 365] a Workfront Fusion</a> en este artículo. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>Seleccione el tipo de entidad que desea que lea el módulo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Seleccione la información que desea incluir en el paquete de salida para este módulo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Introduzca o asigne el identificador único de [!DNL Microsoft Dynamics 365] del registro que desea que lea el módulo.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Actualizar registro]

Este módulo de acción actualiza una entidad.

Especifique el ID de la entidad.

El módulo devuelve el identificador del registro actualizado y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Microsoft Dynamics 365] a Workfront Fusion, consulte <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Microsoft Dynamics 365] a Workfront Fusion</a> en este artículo. </p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>Seleccione el tipo de entidad que desea que actualice el módulo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select Fields to Map]</td> 
   <td>Seleccione los campos para los que desea incluir valores cuando se cree el registro. Los campos disponibles dependen del tipo de entidad.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Property fields]</td> 
   <td>Estos son los campos que ha seleccionado. Introduzca el valor que desea que tenga el registro para una propiedad determinada.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Introduzca o asigne el identificador único de [!DNL Microsoft Dynamics] 365 del registro que desea que actualice el módulo.</td> 
  </tr> 
 </tbody> 
</table>

### Búsquedas

#### [!UICONTROL Search Records]

Este módulo de búsqueda busca registros en un objeto de [!DNL Microsoft Dynamics 365] que coincidan con la consulta de búsqueda especificada. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Microsoft Dynamics 365] a Workfront Fusion, consulte <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Microsoft Dynamics 365] a Workfront Fusion</a> en este artículo. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>Seleccione el tipo de entidad que desea que actualice el módulo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filters]</td> 
   <td> <p>Seleccione el filtro que desee utilizar para esta búsqueda.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Standard Filters]</strong> </p> <p>Configure el filtro seleccionando un campo y un operador e introduciendo o asignando el valor que desea buscar. Puede utilizar las reglas AND u OR en el filtro.</p> </li> 
     <li> <p><strong>[!UICONTROL Query Functions]</strong> </p> <p>Introduzca la función de consulta de API web de [!DNL Dynamics 365] que desee usar para la búsqueda. </p> <p>Para obtener más información sobre las funciones de consulta, consulte <a href="https://docs.microsoft.com/en-us/dynamics365/customer-engagement/web-api/queryfunctions?view=dynamics-ce-odata-9">Referencia de función de consulta de API web</a> en la documentación de [!DNL Microsoft].</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort]</td> 
   <td> <p>Especifique el orden en que se devuelven los elementos. Puede agregar varias ordenaciones.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Field]</strong> </p> <p>Especifique el campo por el que desea ordenar los resultados.</p> </li> 
     <li> <p><strong>[!UICONTROL Direction]</strong> </p> <p>Especifique la dirección de la ordenación (ascendente o descendente).</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Max Records]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Seleccione la información que desea incluir en el paquete de salida para este módulo.</p> </td> 
  </tr> 
 </tbody> 
</table>
