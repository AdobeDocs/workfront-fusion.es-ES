---
title: Módulos de Microsoft Dynamics 365
description: En un escenario de  [!DNL Adobe Workfront Fusion] , puede automatizar los flujos de trabajo que utilizan Microsoft Dynamics 365 y conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: 16ae173b-10ce-481d-8f6c-1df0e65f7c0e
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1549'
ht-degree: 89%

---

# [!DNL Microsoft Dynamics 365 modules]

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!DNL Microsoft Dynamics 365], así como conectarlo a varias aplicaciones y servicios de terceros.

>[!NOTE]
>
>El conector de [!DNL Microsoft Dynamics 365] no admite [!DNL Dynamics Finance and Operations].

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

Para usar [!DNL Microsoft Dynamics] 365, debe tener una cuenta de [!DNL Microsoft Dynamics 365].

## Conectar Microsoft Dynamics 365 a Workfront Fusion

Puede crear una conexión con su cuenta de [!DNL Microsoft Dynamics 365] directamente desde un módulo de [!DNL Microsoft Dynamics 365].

>[!NOTE]
>
>Algunas aplicaciones de Microsoft utilizan la misma conexión, que está vinculada a permisos de usuario individuales. Por lo tanto, al crear una conexión, la pantalla de consentimiento de permisos muestra los permisos que se otorgaron previamente a la conexión de este usuario, además de cualquier nuevo permiso que sea necesario para la aplicación actual.
>
>Por ejemplo, si a un usuario se le han otorgado permisos de &quot;Leer tabla&quot; a través del conector de Excel y luego crea una conexión en el conector de Outlook para leer correos electrónicos, la pantalla de consentimiento de permisos mostrará tanto el permiso de &quot;Leer tabla&quot; ya otorgado como el nuevo permiso requerido de &quot;Escribir correo electrónico&quot;.

1. En cualquier módulo de [!DNL Microsoft Dynamics 365], haga clic en **[!UICONTROL Add]** junto al campo [!UICONTROL Connection].
1. Introduzca un nombre para la conexión. 
1. En el campo **[!UICONTROL Resource]**, escriba la dirección de su cuenta de [!DNL Dynamics 365], sin `https://`.
1. Haga clic en **[!UICONTROL Continue]** para crear la conexión y volver al módulo.

>[!NOTE]
>
>Al registrar [!DNL Workfront Fusion] en el portal de [!DNL Microsoft Azure], use el siguiente URI de redireccionamiento:
>
>* `https://app.workfrontfusion.com/oauth/cb/workfront-microsoft-dynamics2`


## Módulos de [!DNL Microsoft Dynamics 365] y sus campos

Al configurar módulos de [!DNL Microsoft Dynamics 365], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Microsoft Dynamics 365] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [[!UICONTROL Watch Records (Scheduled)]](#watch-records-scheduled)
* [[!UICONTROL Watch Records (Real Time)]](#watch-records-real-time)
* [[!UICONTROL Create Record]](#create-record)
* [[!UICONTROL Make an API Call]](#make-an-api-call)
* [[!UICONTROL Delete Record]](#delete-record)
* [[!UICONTROL Read Records]](#read-records)
* [[!UICONTROL Update Record]](#update-record)
* [[!UICONTROL Search Records]](#search-records)

### [!UICONTROL Watch Records (Scheduled)]

Este módulo activador programado ejecuta un escenario cuando se crea o actualiza un registro del objeto especificado después de la última ejecución programada en [!DNL Dynamics 365].

La salida del módulo indica si el registro que ha encontrado es nuevo o actualizado (si se añadió y actualizó en el período de tiempo, se marca como nuevo). Puede asignar esta información en módulos subsiguientes en el escenario.

Esto sucede en un intervalo programado de forma regular que usted especifica.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Microsoft Dynamics 365] a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Microsoft Dynamics 365] a [!DNL Workfront Fusion]</a> en este artículo. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include]</td> 
   <td>Seleccione si desea que el módulo vea <strong>[!UICONTROL Only new records]</strong>, <strong>[!UICONTROL Updated records only]</strong> o <strong>[!UICONTROL New records and all changes]</strong>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>Elija el tipo de registro [!UICONTROL Microsoft Dynamics 365] que desea que vea el escenario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Seleccione la información que desea incluir en el paquete de salida para este módulo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Max Records]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Watch Records (Real Time)]

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
     <li value="2"> <p>En el campo Nombre de <strong>[!UICONTROL Webhook]</strong>, escriba un nombre descriptivo para el webhook.</p> </li> 
     <li value="3"> <p>En el campo <strong>[!UICONTROL Connection]</strong>, seleccione la Conexión que desea utilizar seleccionada</p> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Microsoft Dynamics 365] a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Microsoft Dynamics 365] a [!DNL Workfront Fusion]</a> en este artículo. </p> </li> 
     <li value="4"> <p>Haga clic en <strong>[!UICONTROL Save]</strong> para guardar el webhook y volver al módulo.</p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Create Record]

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
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Microsoft Dynamics 365] a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Microsoft Dynamics 365] a [!DNL Workfront Fusion]</a> en este artículo. </p> </td> 
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

### [!UICONTROL Make an API Call]

Este módulo de acción le permite realizar una llamada autenticada personalizada a la API [!DNL Microsoft Dynamics 365]. De este modo, puede crear una automatización del flujo de datos que no puedan realizar los otros módulos de [!DNL Microsoft Dynamics 365].

El módulo devuelve información sobre el código de estado, los encabezados y el cuerpo. Puede asignar esta información en módulos subsiguientes en el escenario.

Para obtener más información, consulte la documentación de [!DNL Microsoft] acerca del uso de [!DNL Dynamics 365 Customer Engagement Web API].

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Microsoft Dynamics 365] a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Microsoft Dynamics 365] a [!DNL Workfront Fusion]</a> en este artículo. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> <p>Escriba una ruta relativa a <code>&lt;Instance URL>/api/data/v9.1/</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, consulte <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de petición HTTP en [!DNL Adobe Workfront Fusion]</a>.</p> <p>Para obtener más </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] añade los encabezados de autorización automáticamente.</p> </td> 
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

### [!UICONTROL Delete Record]

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
  <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Microsoft Dynamics 365] a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Microsoft Dynamics 365] a [!DNL Workfront Fusion]</a> en este artículo. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td> <p>Seleccione el tipo de entidad que desea que elimine el módulo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td> <p>Escriba o asigne el identificador único de [!DNL Microsoft Dynamics 365] del registro que desea que elimine el módulo.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Read Records]

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
  <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Microsoft Dynamics 365] a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Microsoft Dynamics 365] a [!DNL Workfront Fusion]</a> en este artículo. </p> </td> 
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
   <td>Escriba o asigne el identificador único [!DNL Microsoft Dynamics 365] del registro que desea que lea el módulo.</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Update Record]

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
  <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Microsoft Dynamics 365] a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Microsoft Dynamics 365] a [!DNL Workfront Fusion]</a> en este artículo. </p> </td> 
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

### [!UICONTROL Search Records]

Este módulo de búsqueda busca registros en un objeto de [!DNL Microsoft Dynamics 365] que coincidan con la consulta de búsqueda especificada. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Microsoft Dynamics 365] a [!DNL Workfront Fusion], consulte <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Microsoft Dynamics 365] a [!DNL Workfront Fusion]</a> en este artículo. </p> </td> 
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
