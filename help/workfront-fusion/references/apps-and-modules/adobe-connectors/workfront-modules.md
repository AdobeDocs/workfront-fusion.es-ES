---
title: Módulos de Adobe Workfront
description: Puede utilizar el conector Adobe Workfront Fusion Adobe Workfront para automatizar sus procesos dentro de Workfront. Si dispone de una licencia de Workfront Fusion for Work Automation and Integration, también puede utilizarla para conectarse a aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion, Workfront Integrations and Apps
exl-id: 93c27cf6-38b0-466c-87bb-926c4817eae7
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '8067'
ht-degree: 56%

---

# Módulos de Adobe Workfront

Puede utilizar el conector Adobe Workfront Fusion Adobe Workfront para automatizar sus procesos dentro de Workfront. También puede conectar Workfront a otras aplicaciones y servicios.

Para obtener instrucciones sobre cómo crear un escenario, vea los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md). Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

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
   <p>Heredado: cualquiera </p>
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


>[!NOTE]
>
>* Si su organización utiliza el paquete de licencias heredado (basado en conectores), debe tener una licencia de integración y automatización del trabajo de Workfront Fusion para conectarse a aplicaciones y servicios de terceros. El conector de Workfront no se cuenta contra el número de aplicaciones activas disponibles para su organización. Todos los escenarios, incluso si solo utilizan la aplicación de Workfront, no se contabilizan en el recuento total de escenarios de su organización.

+++

## Conexión de Workfront a Workfront Fusion

El conector de Workfront utiliza OAuth 2.0 para conectarse a Workfront.

Puede crear una conexión a su cuenta de Workfront directamente desde un módulo de Workfront Fusion.

1. En cualquier módulo de Adobe Workfront, haga clic en **Añadir** junto al campo Conexión.
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
          <p>Introduzca un nombre para la nueva conexión.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>
          <p>Seleccione si se está conectando a un entorno de producción o de no producción.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Connection type]</td>
        <td>
          <p>Seleccione si desea conectarse a una cuenta de servicio o a una personal.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Introduzca su ID de cliente de Workfront. Esto se puede encontrar en el área Aplicaciones OAuth2 del área Configuración en Workfront. Abra la aplicación específica a la que se está conectando para ver el ID de cliente.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Escriba el secreto de cliente de Workfront. Esto se puede encontrar en el área Aplicaciones OAuth2 del área Configuración en Workfront. Si no dispone de un Secreto de cliente para la aplicación OAuth2 en Workfront, puede generar otro. Para obtener instrucciones, consulte la documentación de Workfront.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Authentication URL]</td>
        <td>Este puede seguir siendo el valor predeterminado, o bien puede introducir la dirección URL de su instancia de Workfront, seguida de <code>/integrations/oauth2</code>. <p>Ejemplo: <code>https://mydomain.my.workfront.com/integrations/oauth2</code></p></td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Host prefix]</td>
        <td>En la mayoría de los casos, este valor debe ser <code>origin</code>.
      </tr>
    </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.

   Si no ha iniciado sesión en Workfront, se le dirigirá a una pantalla de inicio de sesión. Después de iniciar sesión, puede permitir la conexión.

>[!NOTE]
>
>* Las conexiones de OAuth 2.0 a la API de Workfront ya no dependen de las claves de API.
>* Para crear una conexión con un entorno limitado de Workfront, debe crear una aplicación OAuth2 en ese entorno y, a continuación, utilizar el ID de cliente y el Secreto de cliente generados por esa aplicación en la conexión.

## Módulos Workfront y sus campos

Al configurar los módulos de Workfront, Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden mostrarse campos de Workfront adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).


![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

>[!NOTE]
>
>* Si no ve los campos más actualizados en un módulo de Workfront, puede deberse a problemas de almacenamiento en caché. Espere una hora e inténtelo de nuevo.
>* Los códigos de estado HTTP 429 de Adobe Workfront no deben provocar desactivaciones, sino activar una breve pausa en la ejecución en el escenario.

* [Activadores](#triggers)
* [Acciones](#actions)
* [Búsquedas](#searches)

### Activadores

<!--
* [Watch Events](#watch-events) 
* [Watch Record](#watch-record) 
* [Watch Field](#watch-field)
-->

+++ **[!UICONTROL Ver eventos]**

Este módulo de activación ejecuta un escenario en tiempo real cuando se añaden, actualizan o eliminan objetos de un tipo específico en Workfront

El módulo devuelve cualquier campo estándar asociado con el registro, junto con los campos y valores personalizados a los que accede la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

1. Haga clic en **[!UICONTROL Añadir]** a la derecha del cuadro **Webhook**.

1. Configure el webhook en el cuadro **[!UICONTROL Añadir un hook]** que se muestra.

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td>[!UICONTROL Webhook name]</td> 
      <td>Introducir un nombre para el webhook</td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL Connection]</td> 
      <td> <p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Conectar Workfront a Workfront Fusion</a> en este artículo.</p> </td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL Record Type]</td> 
      <td>Seleccione el tipo de registro de Workfront que desea que vea el módulo.</td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL State]</td> 
      <td>Seleccione si desea ver el estado antiguo o el nuevo.<ul><li><p><b>[!UICONTROL New state]</b></p><p>Active un escenario cuando el registro cambia <b>a </b> un valor determinado.</p><p>Por ejemplo, si el estado se establece en [!UICONTROL New State] y el filtro se establece en [!UICONTROL Status] [!UICONTROL Equals] [!UICONTROL In Progress], el webhook activa un escenario cuando el [!UICONTROL Status] cambia a [!UICONTROL In Progress], independientemente del estado anterior. </p></li><li><p><b>[!UICONTROL Old state]</b></p><p>Activa un escenario cuando el registro cambia <b>de </b> un valor determinado.</p><p>Por ejemplo, si el estado se establece en [!UICONTROL Old State] y el filtro se establece en [!UICONTROL Status] [!UICONTROL Equals] [!UICONTROL In Progress], el webhook activa un escenario cuando un [!UICONTROL Status] que está actualmente [!UICONTROL In Progress] cambia a otro estado. </p></li></ul></td> 
     </tr> 
     <tr data-mc-conditions=""> 
      <td> <p>[!UICONTROL Events filters]</p> </td> 
      <td> <p>Puede establecer filtros para ver solo los registros que cumplan los criterios seleccionados.</p> <p>Para cada filtro, introduzca el campo que desea que evalúe el filtro, el operador y el valor que desea que permita el filtro. Puede utilizar más de un filtro añadiendo reglas AND.</p> <p><b>NOTA</b>: no puede editar filtros en los webhooks de Workfront existentes. Para configurar diferentes filtros para las suscripciones a eventos de Workfront, elimine el webhook actual y cree uno nuevo.</p> <p>Para obtener más información sobre los filtros de eventos, consulte <a href="#event-subscription-filters-in-the-workfront--watch-events-modules" class="MCXref xref">Filtros de suscripción de eventos en los módulos Workfront &gt; [!UICONTROL Watch Events]</a> en este artículo.</p> </td> 
     </tr> 
     <tr data-mc-conditions=""> 
      <td>Excluir eventos realizados por esta conexión</td> 
      <td>Habilite esta opción para excluir los eventos creados o actualizados con el mismo conector que utiliza este módulo de activador. Así pueden evitarse situaciones en las que un escenario podría activarse a sí mismo y provocar su repetición en un bucle interminable.<p><b>NOTA</b>: El tipo de registro de asignación no incluye esta opción.</p></td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL Record Origin]</td> 
      <td>
       <p>Elija si desea que el escenario vea [!UICONTROL Solo registros nuevos], [!UICONTROL Solo registros actualizados], [!UICONTROL Registros nuevos y actualizados] o [!DNL Deleted Records Only].</p>
       <p><b>NOTA</b>: Si elige [!UICONTROL Registros nuevos y actualizados], la creación del webhook crea 2 suscripciones de eventos (para la misma dirección de webhook).</p>
       </td> 
     </tr> 
    </tbody> 
   </table>



   <!--Markdown 0032 placeholder-->

Una vez creado el webhook, podrá ver la dirección del punto final al que se envían los eventos.

Para obtener más información, consulte la sección [Ejemplos de cargas útiles de eventos](https://experienceleague.adobe.com/en/docs/workfront/using/adobe-workfront-api/event-subscriptions/event-subs-api#examples-of-event-payloads) en el artículo API de suscripción de eventos en la documentación de Workfront.

Vea una lista de los tipos de objetos Workfront para los que puede usar este módulo en [tipos de objetos Workfront disponibles para cada módulo Workfront](#workfront-object-types-available-for-each-workfront-module).

+++

+++ **[!UICONTROL Campo de observación]**

Este módulo de activador ejecuta un escenario cuando se actualiza un campo que se haya especificado. El módulo devuelve el valor antiguo y el nuevo del campo especificado. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Conectar Workfront a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro de Workfront que desea que vea el módulo.</p> <p>Por ejemplo, seleccione [!UICONTROL Task] si desea comenzar a ejecutar el escenario cada vez que se actualice un campo de registro en una tarea.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Field]</td> 
   <td>Seleccione el campo en el que desea que el módulo observe las actualizaciones. Estos campos reflejan los campos que el administrador de Workfront ha configurado para el seguimiento.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Outputs]</td> 
   <td>Seleccione los campos de objeto que desea incluir en el paquete de salida para este módulo.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

Vea una lista de los tipos de objetos Workfront para los que puede usar este módulo en [tipos de objetos Workfront disponibles para cada módulo Workfront](#workfront-object-types-available-for-each-workfront-module).

+++

+++ **[!UICONTROL Ver registro]**

Este módulo de activación ejecuta un escenario cuando se añaden, actualizan o ambos objetos de un tipo específico. El módulo devuelve todos los campos estándar asociados con el registro o registros, junto con cualquier campo personalizado y valor al que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

En la salida, el módulo indica si cada registro es nuevo o se ha actualizado.

Los registros que se agregaron y actualizaron desde la última vez que se ejecutó el escenario se devuelven como registros nuevos.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Conectar Workfront a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td> <p>Elija si desea que el escenario vea [!UICONTROL Solo registros nuevos], [!UICONTROL Solo registros actualizados] o [!UICONTROL Registros nuevos y actualizados].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro de Workfront que desea que vea el módulo.</p> <p>Por ejemplo, si desea iniciar el escenario cada vez que se cree un nuevo proyecto, seleccione [!UICONTROL Project]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Seleccione los campos que desea incluir en el paquete de salida para este módulo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Referencia]</td> 
   <td> <p>Seleccione los campos de referencia que desee incluir en el paquete de salida para este módulo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Seleccione los campos de recopilación que desea incluir en el paquete de salida para este módulo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Optional Filter]</td> 
   <td> <p>(Avanzado) Escriba una cadena de código de API para definir cualquier parámetro o código adicional que restrinja sus criterios. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

Vea una lista de los tipos de objetos Workfront para los que puede usar este módulo en [tipos de objetos Workfront disponibles para cada módulo Workfront](#workfront-object-types-available-for-each-workfront-module).

+++


### Acciones

<!--
* [Convert object](#convert-object) 
* [Create a record (attaching custom forms)](#create-a-record-attaching-custom-forms) 
* [Create a record](#create-a-record) 
* [Custom API Call](#custom-api-call) 
* [Delete Record](#delete-record) 
* [Download Document](#download-document) 
* [Misc Action](#misc-action) 
* [Read a Record](#read-a-record) 
* [Update Record](#update-record) 
* [Upload Document](#upload-document)
-->

+++ **[!UICONTROL Convertir objeto]**

Este módulo de acción realiza una de las siguientes conversiones:

* Convertir problema a proyecto
* Convertir problema a tarea
* Convertir tarea a proyecto

>[!NOTE]
>
>A partir de julio de 2024, los formularios personalizados se pueden incluir al convertir un objeto.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Conectar Workfront a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Object type]</td> 
   <td> <p>Seleccione el tipo de objeto que desea convertir. Es el tipo que tiene el objeto antes de la conversión.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Convert to]</td> 
   <td>Seleccione el objeto al que desea convertirlo. Es el tipo que tiene el objeto después de la conversión.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL &lt;Object&gt; ID]</td> 
   <td> <p>Introduzca el ID del objeto. </p> <p>Nota: Al introducir el ID de un objeto, puede empezar a escribir su nombre y, a continuación, seleccionarlo en la lista. A continuación, el módulo introducirá el ID adecuado en el campo.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Template ID]</td> 
   <td> <p>Si está realizando una conversión a un proyecto, seleccione el ID de plantilla que desee utilizar para el proyecto.</p> <p>Nota: Al introducir el ID de un objeto, puede empezar a escribir su nombre y, a continuación, seleccionarlo en la lista. A continuación, el módulo introducirá el ID adecuado en el campo.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Custom forms]</td> 
   <td>Seleccione los formularios personalizados que desee añadir al objeto recién convertido y, a continuación, introduzca los valores de los campos de formulario personalizado.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Options]</td> 
   <td> <p>Habilite las opciones que desee al convertir el objeto. Las opciones están disponibles en función del objeto al que se convierta o desde el que se convierta.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Copy native fields]</td> 
   <td> <p>Habilite esta opción para copiar cualquier campo nativo del objeto original al nuevo.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Copy custom forms]</td> 
   <td> <p>Habilite esta opción para copiar cualquier campo nativo del objeto original al nuevo.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Create a record]** 

Este módulo de acción crea un objeto, como un proyecto, una tarea o un problema en Workfront, y le permite agregar un formulario personalizado al nuevo objeto. El módulo le permite seleccionar qué campos del objeto están disponibles en el módulo.

Especifique el identificador del registro.

El módulo devuelve el identificador del registro y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Asegúrese de proporcionar el número mínimo de campos de entrada. Por ejemplo, si desea crear un problema, debe proporcionar un ID de proyecto principal válido en el campo ID de proyecto para indicar dónde debe residir el problema en Workfront. Puede utilizar el panel de asignación para asignar esta información desde otro módulo del escenario o puede introducirla manualmente escribiendo el nombre y seleccionándolo a continuación en la lista.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Conectar Workfront a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro de Workfront que desea que cree el módulo.</p> <p>Por ejemplo, si desea crear un proyecto, seleccione [!UICONTROL Proyecto] en la lista desplegable.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Select fields to map]</td> 
   <td> <p>Seleccione los campos que desea que estén disponibles para la entrada de datos. Esto le permite utilizar estos campos sin tener que desplazarse por los que no necesita. A continuación, puede introducir o asignar datos en estos campos.</p> <p>En el caso de los campos de los formularios personalizados, utilice el campo <b>[!UICONTROL Attach Custom Form]</b>.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Attach Custom Form]</td> 
   <td>Seleccione cualquier formulario personalizado que desee agregar al nuevo objeto y, a continuación, introduzca o asigne valores para esos campos.</td> 
  </tr> 
 </tbody> 
</table>

Vea una lista de los tipos de objetos Workfront para los que puede usar este módulo en [tipos de objetos Workfront disponibles para cada módulo Workfront](#workfront-object-types-available-for-each-workfront-module).

>[!NOTE]
>
>* Al introducir el ID de un objeto, puede empezar a escribir su nombre y, a continuación, seleccionarlo en la lista. A continuación, el módulo introducirá el ID adecuado en el campo.
>* Al introducir el texto de un campo personalizado o un objeto [!UICONTROL Nota] (comentario o respuesta), puede usar etiquetas de HTML en el campo [!UICONTROL Texto de nota] para crear texto enriquecido, como texto en negrita o en cursiva.
>



>[!NOTE]
>
>Los usuarios se crean en estado Desactivado y Pendiente de aprobación. Si su organización se ha migrado a Adobe Admin Console y el distintivo de Aprobación pendiente no se elimina en unos minutos, puede aprobar al usuario.
>
>* **Resolver usuarios individuales**
>
>      Puede resolver usuarios individuales en la lista Usuarios.
>
>      1. Seleccione el usuario o usuarios en la lista Usuarios.
>      1. Haga clic en el menú de tres puntos del encabezado de la lista.
>      1. Seleccione **Aprobar**.
>      1. Después de unos minutos, actualice la página.
>
>* **Resolver usuarios agregados en un lote grande**
>
>   Para resolver los usuarios que se agregaron en un lote grande, puede agregar el lote de usuarios directamente a Adobe Admin Console.
>
>   Para obtener instrucciones, consulte [Administrar varios usuarios | Carga masiva de CSV](https://helpx.adobe.com/enterprise/using/bulk-upload-users.html) en la documentación de Adobe.

+++

+++ **[!UICONTROL Crear registro (heredado)]**

>[!IMPORTANT]
>
>Este módulo se ha reemplazado por el módulo Crear un registro. Se recomienda utilizar ese módulo en nuevos escenarios.
>&#x200B;>Los escenarios existentes que utilicen este módulo seguirán funcionando según lo esperado. Este módulo se eliminará del selector de módulos en mayo de 2025.

Este módulo de acción crea un objeto en Workfront, como un proyecto, una tarea o un problema. El módulo le permite seleccionar qué campos del objeto están disponibles en el módulo.

Especifique el identificador del registro.

El módulo devuelve el identificador del registro y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Asegúrese de proporcionar el número mínimo de campos de entrada. Por ejemplo, si desea crear un problema, debe proporcionar un ID de proyecto principal válido en el campo ID de proyecto para indicar dónde debe residir el problema en Workfront. Puede utilizar el panel de asignación para asignar esta información desde otro módulo del escenario o puede introducirla manualmente escribiendo el nombre y seleccionándolo a continuación en la lista.

Este módulo no adjunta formularios personalizados al crear el objeto. Para adjuntar formularios personalizados al crear un objeto, use el módulo [!UICONTROL Crear un registro (adjuntar formularios personalizados)].

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Conectar Workfront a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro de Workfront que desea que cree el módulo.</p> <p>Por ejemplo, si desea crear un proyecto, seleccione [!UICONTROL Proyecto] en la lista desplegable.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Select fields to map]</td> 
   <td>Seleccione los campos que desea que estén disponibles para la entrada de datos. Así podrá utilizar estos campos sin tener que desplazarse por los que no necesita.</td> 
  </tr> 
 </tbody> 
</table>

Vea una lista de los tipos de objetos Workfront para los que puede usar este módulo en [tipos de objetos Workfront disponibles para cada módulo Workfront](#workfront-object-types-available-for-each-workfront-module).

>[!NOTE]
>
>* Al introducir el ID de un objeto, puede empezar a escribir su nombre y, a continuación, seleccionarlo en la lista. A continuación, el módulo introducirá el ID adecuado en el campo.
>* Al introducir el texto de un campo personalizado o un objeto [!UICONTROL Nota] (comentario o respuesta), puede usar etiquetas de HTML en el campo [!UICONTROL Texto de nota] para crear texto enriquecido, como texto en negrita o en cursiva.

+++

+++ **[!UICONTROL Llamada de API personalizada]**

Este módulo de acción le permite realizar una llamada autenticada personalizada a la API de Workfront. De este modo, puede crear una automatización del flujo de datos que no puedan realizar los demás módulos de Workfront.

El módulo devuelve la siguiente información:

* **[!UICONTROL Código de estado]** (número): indica si la petición HTTP se ha realizado correctamente o no. Se trata de códigos estándar que puede buscar en internet.
* **[!UICONTROL Encabezados]** (objeto): contexto más detallado para el código de respuesta/estado que no está relacionado con el cuerpo de salida. No todos los encabezados que aparecen en un encabezado de respuesta son de respuesta, por lo que algunos podrían no resultarle útiles.

  Los encabezados de respuesta dependen de la petición HTTP elegida al configurar el módulo.

* **[!UICONTROL Cuerpo]** (objeto): según la petición HTTP elegida al configurar el módulo, es posible que reciba de vuelta algunos datos. Esos datos, como los de una petición GET, están incluidos en este objeto.

Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Conectar Workfront a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td> <p>Introduzca una ruta relativa a <code> https://&lt;WORKFRONT_DOMAIN&gt;/attask/api/&lt;API_VERSION&gt;/</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL API Version]</td> 
   <td>Seleccione la versión de la API de Workfront que desea que utilice el módulo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, consulte <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP en Adobe Workfront Fusion</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar. Determina el tipo de contenido de la petición.</p> <p>Por ejemplo:<code> {"Content-type":"application/json"}</code></p> <p>Nota: Si se producen errores y es difícil determinar su origen, considere la posibilidad de modificar los encabezados según la documentación de Workfront. Si su llamada de API personalizada devuelve un error de petición HTTP 422, intente utilizar un encabezado <code>"Content-Type":"text/plain"</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Añada la consulta para la llamada de API en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"name":"something-urgent"}</code></p> <p>Sugerencia: Le recomendamos que envíe información a través del cuerpo de JSON en lugar de como parámetros de consulta.</p> </td> 
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

Vea una lista de los tipos de objetos Workfront para los que puede usar este módulo en [tipos de objetos Workfront disponibles para cada módulo Workfront](#workfront-object-types-available-for-each-workfront-module).

+++

+++ **[!UICONTROL Eliminación de registro]**

Este módulo de acción elimina un objeto, como un proyecto, una tarea o un problema en Workfront.

Especifique el identificador del registro.

El módulo devuelve el identificador del registro y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Conectar Workfront a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Force delete]</td> 
   <td>Habilite esta opción para asegurarse de que se elimina el registro, incluso si la interfaz de usuario de Workfront solicitara confirmación de la eliminación.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Eliminación asíncrona]</td> 
   <td>Active esta opción para permitir que el módulo elimine de forma asíncrona.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>Identificador</td> 
   <td> <p>Introduzca el ID único de Workfront del registro que desea que elimine el módulo.</p> <p>Para obtener el ID, abra el objeto Workfront en el explorador y copie el texto al final de la dirección URL después de "ID=". Por ejemplo: https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td>Seleccione el tipo de registro de Workfront que desea que elimine el módulo.</td> 
  </tr> 
 </tbody> 
</table>

Vea una lista de los tipos de objetos Workfront para los que puede usar este módulo en [tipos de objetos Workfront disponibles para cada módulo Workfront](#workfront-object-types-available-for-each-workfront-module).

>[!NOTE]
>
>Se recomienda la siguiente configuración de escenario para evitar la posibilidad de que no se eliminen registros debido a operaciones asíncronas.
>
>1. Elimine el registro de forma sincrónica.
>1. Añada la administración de errores al módulo Eliminar registro para ignorar el error causado por el tiempo de espera de 40 segundos.


+++

+++ **[!UICONTROL Descargar documento]**

Este módulo de acción descarga un documento de Workfront.

Especifique el identificador del registro.

El módulo devuelve el contenido, el nombre de archivo y la extensión y el tamaño de archivo del documento. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Conectar Workfront a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Document ID]</td> 
   <td> <p>Asigne o introduzca manualmente el ID único de Workfront del documento que desea que descargue el módulo.</p> <p>Para obtener el ID, abra el objeto Workfront en el explorador y copie el texto al final de la dirección URL después de "ID=". Por ejemplo: https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
 </tbody> 
</table>

Vea una lista de los tipos de objetos Workfront para los que puede usar este módulo en [tipos de objetos Workfront disponibles para cada módulo Workfront](#workfront-object-types-available-for-each-workfront-module).

+++

+++ **[!UICONTROL Acciones diversas]**

Este módulo de acción le permite realizar acciones en la API.

>[!NOTE]
>
>En julio de 2024, la acción `convertToProject` incluye el campo `copyCategories`. Cuando se establece en `TRUE`, todos los formularios personalizados se incluirán en el proyecto al que se convierte el problema.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Conectar Workfront a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro de Workfront con el que desea que interactúe el módulo.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Action]</td> 
   <td> <p>Seleccione la acción que desea que realice el módulo.</p> <p>Es posible que tenga que rellenar campos adicionales, según el [!UICONTROL Record Type] and [!UICONTROL Action] que elija. Algunas combinaciones de estas dos configuraciones pueden requerir solamente un identificador de registro, mientras que otras (como Proyecto para <strong>[!UICONTROL Record Type]</strong> y [!UICONTROL Attach Template] para la <strong>[!UICONTROL Action]</strong>) requieren información adicional (como un identificador de objeto y un identificador de plantilla).</p><p>Para ver las opciones disponibles para algunas acciones, consulte <a href="#misc-action-options" class="MCXref xref">Otras opciones de acción</a> en este artículo.</p> <p>Para obtener detalles sobre campos individuales, consulte la <a href="http://developer.workfront.com/">documentación para desarrolladores de Workfront</a>. <p><strong>Nota</strong>: El sitio de documentación para desarrolladores incluye información solamente a través de la versión 14 de la API, pero aún contiene información valiosa para las llamadas de la API. </p> 
    <ol> 
     <li value="1"> <p>Seleccione el tipo de registro en el panel de navegación izquierdo de la página Documentación para desarrolladores de Workfront. Los siguientes tipos tienen sus propias páginas:</p> 
      <ul> 
       <li> <p>[!UICONTROL Projects]</p> </li> 
       <li> <p>[!UICONTROL Tasks]</p> </li> 
       <li> <p>[!UICONTROL Issues]</p> </li> 
       <li> <p>[!UICONTROL Users]</p> </li> 
       <li> <p>[!UICONTROL Documents]</p> </li> 
      </ul> <p>Para todos los demás tipos de registro, seleccione <b>[!UICONTROL Other objects and endpoints]</b> y busque el tipo de registro en las páginas ordenadas alfabéticamente.</p> </li> 
     <li value="2"> <p>En la página del tipo de registro adecuado, busque (Ctrl-F o Cmd-F) la acción.</p> </li> 
     <li value="3"> <p>Vea las descripciones de los campos disponibles en la acción seleccionada.</p> </li> 
    </ol> <p>Nota:  <p>Al crear una revisión a través del módulo [!UICONTROL Misc Action] de Workfront, se recomienda crearla sin ninguna opción avanzada y, a continuación, actualizarla mediante la API de SOAP [!DNL Workfront Proof].</p><p>Para obtener más información sobre cómo crear una revisión con la API de Workfront (que usa este módulo), consulte <a href="https://experienceleague.adobe.com/en/docs/workfront/using/adobe-workfront-api/tips-troubleshooting-apis/api-create-proof-options-json" class="MCXref xref">Agregar opciones avanzadas de revisión al crear una revisión mediante la API de Adobe Workfront</a></p> </p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL ID]</td> 
   <td>Introduzca o asigne el ID de Workfront único del registro con el que desea que interactúe el módulo.<p>Para obtener el ID, abra el objeto Workfront en el explorador y copie el texto al final de la dirección URL después de "ID=". Por ejemplo: https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p></td> 
  </tr> 
 </tbody> 
</table>

Vea una lista de los tipos de objetos Workfront para los que puede usar este módulo en [tipos de objetos Workfront disponibles para cada módulo Workfront](#workfront-object-types-available-for-each-workfront-module).

#### Varias opciones de acción

##### Tarea

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <th>Acción</th> 
   <th>Opciones</th> 
  </tr> 
  <tr> 
   <td>Copiar</td> 
   <td>
   <ul>
   <li>clearApprovers</li>
   <li>clearAssignments</li>
   <li>clearConstraints</li>
   <li>clearCustomData</li>
   <li>clearDocuments</li>
   <li>clearExpenses</li>
   <li>clearFinancials<p>Borra los datos financieros</p></li>
   <li>clearPermissions</li>
   <li>clearPredecessors</li>
   <li>clearProgress</li>
   <li>clearTimedNotifications<p>Borra las notificaciones de recordatorio</p></li>
   </ul>
   </td> 
  </tr> 
  <tr> 
   <td>Mover</td> 
   <td>
   <ul>
   <li>clearApprovers</li>
   <li>clearAssignments</li>
   <li>clearDocuments</li>
   <li>clearConstraints</li>
   <li>clearExpenses</li>
   <li>clearFinancials<p>Borra los datos financieros</p></li>
   <li>clearPermissions</li>
   <li>clearPredecessors</li>
   <li>clearProgress</li>
   <li>clearTimedNotifications<p>Borra las notificaciones de recordatorio</p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>

##### Problema

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <th>Acción</th> 
   <th>Opciones</th> 
  </tr> 
  <tr> 
   <td>Copiar</td> 
   <td>
   <ul>
   <li>clearApprovers</li>
   <li>clearAssignments</li>
   <li>clearCustomData</li>
   <li>clearDocuments</li>
   <li>clearPermissions</li>
   <li>clearProgress</li>
   </ul>
   </td> 
  </tr> 
  <tr> 
   <td>Convertir a tarea</td> 
   <td>
   <ul>
   <li>preserveIssue<p>Mantener el problema original y enlazar su solución a esta tarea</p></li>
   <li>preservePrimaryContact<p>Permitir que el contacto principal de los problemas acceda a esta tarea</p></li>
   <li>preserveCompletionDate<p>Conservar la fecha planificada de finalización del problema</p></li>
   </ul>
   </td> 
  </tr> 
  <tr> 
   <td>Convertir en proyecto</td> 
   <td>
   <ul>
   <li>preserveIssue<p>Mantener el problema original y enlazar su solución a esta tarea</p></li>
   <li>preservePrimaryContact<p>Permitir que el contacto principal de los problemas acceda a esta tarea</p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>



##### Proyecto

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <th>Acción</th> 
   <th>Opciones</th> 
  </tr> 
  <tr> 
   <td>Copiar</td> 
   <td>
   <ul>
   <li>clearApprovers</li>
   <li>clearAssignments</li>
   <li>clearCustomData</li>
   <li>clearDocuments</li>
   <li>clearExpenses</li>
   <li>clearFinancials<p>Borra los datos financieros</p></li>
   <li>clearPermissions</li>
   <li>clearPredecessors</li>
   <li>clearProgress</li>
   <li>clearTimedNotifications<p>Borra las notificaciones de recordatorio</p></li>
   </ul>
   </td> 
  </tr> 
  <tr> 
   <td>Adjuntar plantilla / Guardar como plantilla</td> 
   <td>
   <ul>
   <li>clearApprovers</li>
   <li>clearAssignments</li>
   <li>clearBillingRates</li>
   <li>clearConstraints</li>
   <li>clearDeliverables<p>Borra metas</p></li>
   <li>clearDocuments</li>
   <li>clearExpenses</li>
   <li>clearFinancials<p>Borra los datos financieros</p></li>
   <li>clearHourTypes</li>
   <li>clearIssueSetup<p>Borra las propiedades de cola y la configuración de problemas</p></li>
   <li>clearPredecessors</li>
   <li>clearRisks</li>
   <li>clearSharingOptions</li>
   <li>clearTimedNotifications<p>Borra las notificaciones de recordatorio</p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>



+++

+++ **[!UICONTROL Leer un registro]**

Este módulo de acción recupera datos de un único registro.

Especifique el identificador del registro. También puede especificar qué registros relacionados desea que lea el módulo.

Por ejemplo, si el registro que está leyendo el módulo es un proyecto, puede especificar que desea que se lean las tareas del proyecto.

El módulo devuelve una matriz de datos de los campos de salida especificados.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
    <td> <p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Conectar Workfront a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Record Type]</td>

<td>Elija el tipo de objeto Workfront que desea que lea el módulo.</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Outputs]</td>

<td> <p>Seleccione la información que desea incluir en el paquete de salida para este módulo.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Formulario personalizado de salida]</td>
     <td> <p>Seleccione los formularios personalizados que desea incluir en el paquete de salida para este módulo y, a continuación, seleccione los campos específicos de los formularios personalizados que desea incluir en la salida.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL References]</td>
   <td>Seleccione cualquier campo de referencia que desee incluir en la salida.</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Collections]</td>
   <td>Seleccione cualquier campo de referencia que desee incluir en la salida.</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL ID]</td>
   <td> <p>Introduzca el ID único de Workfront del registro que desea que lea el módulo.</p> <p>Para obtener el ID, abra el objeto Workfront en el explorador y copie el texto al final de la dirección URL después de "ID=". Por ejemplo: https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
 </tbody> 
</table>

Vea una lista de los tipos de objetos Workfront para los que puede usar este módulo en [tipos de objetos Workfront disponibles para cada módulo Workfront](#workfront-object-types-available-for-each-workfront-module).

+++

+++ **[!UICONTROL Leer un registro (heredado)]**

>[!IMPORTANT]
>
>Este módulo se ha reemplazado por el módulo Leer un registro. Se recomienda utilizar ese módulo en nuevos escenarios.
>&#x200B;>Los escenarios existentes que utilicen este módulo seguirán funcionando según lo esperado. Este módulo se eliminará del selector de módulos en mayo de 2025.

Este módulo de acción recupera datos de un único registro.

Especifique el identificador del registro. También puede especificar qué registros relacionados desea que lea el módulo.

Por ejemplo, si el registro que está leyendo el módulo es un proyecto, puede especificar que desea que se lean las tareas del proyecto.

El módulo devuelve una matriz de datos de los campos de salida especificados.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
    <td> <p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Conectar Workfront a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Record Type]</td>

<td>Elija el tipo de objeto Workfront que desea que lea el módulo.</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Outputs]</td>

<td> <p>Seleccione la información que desea incluir en el paquete de salida para este módulo.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL References]</td>
   <td>Seleccione cualquier campo de referencia que desee incluir en la salida.</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Collections]</td>
   <td>Seleccione cualquier campo de referencia que desee incluir en la salida.</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL ID]</td>
   <td> <p>Introduzca el ID único de Workfront del registro que desea que lea el módulo.</p> <p>Para obtener el ID, abra el objeto Workfront en el explorador y copie el texto al final de la dirección URL después de "ID=". Por ejemplo: https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
 </tbody> 
</table>

Vea una lista de los tipos de objetos Workfront para los que puede usar este módulo en [tipos de objetos Workfront disponibles para cada módulo Workfront](#workfront-object-types-available-for-each-workfront-module).

+++

+++ **Actualizar la versión de carga de eventos**

Workfront acaba de lanzar una nueva versión de su servicio de suscripción a eventos. La nueva versión no es un cambio en la API de Workfront, sino un cambio en la funcionalidad de suscripción de evento. Este módulo de acción actualiza la versión de carga útil de evento utilizada para este escenario.

Para obtener más información sobre la nueva versión de suscripción de evento, consulte [Versiones de suscripción de evento](https://experienceleague.adobe.com/en/docs/workfront/using/adobe-workfront-api/event-subscriptions/event-subs-versioning) en la documentación de Workfront

Para obtener recursos sobre cómo preservar los escenarios de Workfront Fusion durante la actualización de la suscripción al evento, incluida una grabación del seminario web, consulte [Conservación de los escenarios de Fusion durante la actualización de las suscripciones a eventos V2](https://experienceleaguecommunities.adobe.com/t5/workfront-discussions/event-follow-up-preserving-your-fusion-scenarios-during-the/td-p/754182).

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Conectar Workfront a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Version]</td> 
   <td> Seleccione la versión de la suscripción de evento que desea utilizar para esta carga útil. </td> 
  </tr> 
 </tbody> 
</table>


+++

+++ **Actualizar un registro**


Este módulo de acción actualiza un objeto, como un proyecto, una tarea o un problema. El módulo le permite seleccionar qué campos del objeto están disponibles en el módulo.

Especifique el identificador del registro.

El módulo devuelve el ID del objeto y cualquier campo asociado, junto con cualquier campo personalizado y valor al que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Conectar Workfront a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL ID]</td> 
   <td> <p>Introduzca el ID único de Workfront del registro que desea que actualice el módulo.</p> <p>Para obtener el ID, abra el objeto Workfront en el explorador y copie el texto al final de la dirección URL después de "ID=". Por ejemplo: https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
  <tr> 
   <td>[!DNL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro de Workfront que desea que actualice el módulo.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!DNL Select fields to map]</td> 
   <td>Seleccione los campos que desea que estén disponibles para la entrada de datos. Esto le permite utilizar estos campos sin tener que desplazarse por los que no necesita. A continuación, puede introducir o asignar datos en estos campos.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!DNL Attach Custom Form]</td> 
   <td>Seleccione los formularios personalizados para los que desea proporcionar valores de campo en el nuevo registro. Después de seleccionar el formulario, escriba los datos de los campos de ese formulario.<p> Para proporcionar valores de campo para un formulario que adjunte en este módulo, incluya el ID de formulario personalizado en la sección Campos a asignar.</td> 
  </tr> 
 </tbody> 
</table>

Vea una lista de los tipos de objetos Workfront para los que puede usar este módulo en [tipos de objetos Workfront disponibles para cada módulo Workfront](#workfront-object-types-available-for-each-workfront-module).

>[!NOTE]
>
> Al introducir el texto de un campo personalizado o un objeto [!UICONTROL Nota] (comentario o respuesta), puede usar etiquetas de HTML en el campo [!UICONTROL Texto de nota] para crear texto enriquecido, como texto en negrita o en cursiva.


+++

+++ **[!UICONTROL Actualizar registro (heredado)]**

>[!IMPORTANT]
>
>Este módulo se ha reemplazado por el módulo Actualizar un registro. Se recomienda utilizar ese módulo en nuevos escenarios.
>&#x200B;>Los escenarios existentes que utilicen este módulo seguirán funcionando según lo esperado. Este módulo se eliminará del selector de módulos en mayo de 2025.

Este módulo de acción actualiza un objeto, como un proyecto, una tarea o un problema. El módulo le permite seleccionar qué campos del objeto están disponibles en el módulo.

Especifique el identificador del registro.

El módulo devuelve el ID del objeto y cualquier campo asociado, junto con cualquier campo personalizado y valor al que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Conectar Workfront a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL ID]</td> 
   <td> <p>Introduzca el ID único de Workfront del registro que desea que actualice el módulo.</p> <p>Para obtener el ID, abra el objeto Workfront en el explorador y copie el texto al final de la dirección URL después de "ID=". Por ejemplo: https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
  <tr> 
   <td>[!DNL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro de Workfront que desea que actualice el módulo.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!DNL Select fields to map]</td> 
   <td>Seleccione los campos que desea que estén disponibles para la entrada de datos. Esto le permite utilizar estos campos sin tener que desplazarse por los que no necesita. A continuación, puede introducir o asignar datos en estos campos.</td> 
  </tr> 
 </tbody> 
</table>

Vea una lista de los tipos de objetos Workfront para los que puede usar este módulo en [tipos de objetos Workfront disponibles para cada módulo Workfront](#workfront-object-types-available-for-each-workfront-module).

>[!NOTE]
>
>* Al introducir el ID de un objeto, puede empezar a escribir su nombre y, a continuación, seleccionarlo en la lista. A continuación, el módulo introducirá el ID adecuado en el campo.
>* Al introducir el texto de un campo personalizado o un objeto [!UICONTROL Nota] (comentario o respuesta), puede usar etiquetas de HTML en el campo [!UICONTROL Texto de nota] para crear texto enriquecido, como texto en negrita o en cursiva.

+++

+++ **[!UICONTROL Subir documento]**

Este módulo de acción carga un documento en un objeto de Workfront, como un proyecto, una tarea o un problema. Este módulo carga el documento en fragmentos, lo que facilita el proceso de carga para Workfront.

Este módulo puede gestionar archivos de mayor tamaño que el módulo heredado y forma parte de un despliegue gradual para organizaciones con un paquete de Ultimate Workfront.

Especifique la ubicación del documento, el archivo que desea cargar y un nuevo nombre opcional para el archivo.

El módulo devuelve el ID del documento y cualquier campo asociado, junto con cualquier campo personalizado y valor al que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Conectar Workfront a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Related Record ID]</td> 
   <td>Introduzca el ID único de Workfront del registro en el que desea cargar el documento.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Related Record Type]</td> 
   <td>Seleccione el tipo de registro de Workfront donde desea que el módulo cargue el documento.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder ID]</td> 
   <td>Según el tipo de registro relacionado, es posible que deba introducir o asignar un ID de carpeta.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
 </tbody> 
</table>

Vea una lista de los tipos de objetos Workfront para los que puede usar este módulo en [tipos de objetos Workfront disponibles para cada módulo Workfront](#workfront-object-types-available-for-each-workfront-module).

+++

+++ **[!UICONTROL Cargar documento (heredado)]**

Este módulo de acción carga un documento en un objeto de Workfront, como un proyecto, una tarea o un problema. Carga todo el documento a la vez.

Especifique la ubicación del documento, el archivo que desea cargar y un nuevo nombre opcional para el archivo.

El módulo devuelve el ID del documento y cualquier campo asociado, junto con cualquier campo personalizado y valor al que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Conectar Workfront a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Related Record ID]</td> 
   <td>Introduzca el ID único de Workfront del registro en el que desea cargar el documento.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Related Record Type]</td> 
   <td>Seleccione el tipo de registro de Workfront donde desea que el módulo cargue el documento.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder ID]</td> 
   <td>Según el tipo de registro relacionado, es posible que deba introducir o asignar un ID de carpeta.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
 </tbody> 
</table>

Vea una lista de los tipos de objetos Workfront para los que puede usar este módulo en [tipos de objetos Workfront disponibles para cada módulo Workfront](#workfront-object-types-available-for-each-workfront-module).

+++

### Búsquedas

<!--
* [Read Related Records](#read-related-records) 
* [Search](#search)
-->

+++ **[!UICONTROL Read Related Records]**

Este módulo de búsqueda lee registros que coinciden con la consulta de búsqueda especificada, en un objeto principal concreto.

Especifique qué campos desea incluir en la salida. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Conectar Workfront a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro principal (objeto Workfront) cuyos registros asociados desea leer.</p> <p>Vea una lista de los tipos de objetos de Workfront para los que puede usar este módulo en <a href="#object-types-available-for-each-workfront-search-module" class="MCXref xref">tipos de objetos de Workfront disponibles para cada módulo de Workfront</a> en este artículo.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Parent Record ID]</td> 
   <td> <p>Introduzca o asigne el ID del registro principal cuyos registros asociados desea leer.</p> <p>Para obtener el ID, abra el objeto Workfront en el explorador y copie el texto al final de la dirección URL después de "ID=". Por ejemplo: https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Collections]</td> 
   <td>Seleccione o asigne el tipo de registro secundario que desea que el módulo lea.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Outputs]</td> 
   <td> <p>Seleccione la información que desea incluir en el paquete de salida para este módulo.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Búsqueda]**

Este módulo de búsqueda busca registros en un objeto de Workfront que coincidan con la consulta de búsqueda especificada.

Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Conectar Workfront a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro de Workfront que desea que busque el módulo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Lista de formularios personalizados]</td> 
   <td> <p>Seleccione al menos un formulario personalizado. Los campos de estos formularios personalizados estarán disponibles para la consulta de búsqueda.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Result Set]</td> 
   <td>Seleccione una opción para especificar si desea que el módulo obtenga el primer resultado que coincida con sus criterios de búsqueda o todos los resultados que coincidan con estos.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximal]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search criteria fields]</td> 
   <td> <p>Seleccione los campos que desea utilizar para los criterios de búsqueda. Estos campos estarán disponibles en el menú desplegable Criterios de búsqueda.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search criteria]</td> 
   <td> <p>Introduzca el campo por el que desea buscar, el operador que desea utilizar en la consulta y el valor que está buscando en el campo.</p> <p>Nota: No use <code>username </code> en los criterios de búsqueda. Si se incluye <code>username </code> en una consulta de API en Workfront, el usuario inicia sesión en Workfront y la búsqueda no se realizará correctamente.</p> <p>Nota: <code>In</code> y <code>NotIn</code> funcionan con matrices. Las entradas deben estar en formato de matriz.</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Outputs]</td> 
   <td> <p>Seleccione los campos que desea incluir en la salida para este módulo.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL References]</td> 
   <td>Seleccione los campos de referencia que desea incluir en la búsqueda.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Collections]</td> 
   <td>Seleccione las colecciones que desea añadir a la búsqueda.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Buscar (Heredado)]**

>[!IMPORTANT]
>
>Este módulo se ha reemplazado por el módulo Buscar registros. Se recomienda utilizar ese módulo en nuevos escenarios.
>&#x200B;>Los escenarios existentes que utilicen este módulo seguirán funcionando según lo esperado. Este módulo se eliminará del selector de módulos en mayo de 2025.

Este módulo de búsqueda busca registros en un objeto de Workfront que coincidan con la consulta de búsqueda especificada.

Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Conectar Workfront a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro de Workfront que desea que busque el módulo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Result Set]</td> 
   <td>Seleccione una opción para especificar si desea que el módulo obtenga el primer resultado que coincida con sus criterios de búsqueda o todos los resultados que coincidan con estos.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximal]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search criteria fields]</td> 
   <td> <p>Seleccione los campos que desea utilizar para los criterios de búsqueda. Estos campos estarán disponibles en el menú desplegable Criterios de búsqueda.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search criteria]</td> 
   <td> <p>Introduzca el campo por el que desea buscar, el operador que desea utilizar en la consulta y el valor que está buscando en el campo.</p> <p>Nota: No use <code>username </code> en los criterios de búsqueda. Si se incluye <code>username </code> en una consulta de API en Workfront, el usuario inicia sesión en Workfront y la búsqueda no se realizará correctamente.</p> <p>Nota: <code>In</code> y <code>NotIn</code> funcionan con matrices. Las entradas deben estar en formato de matriz.</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Outputs]</td> 
   <td> <p>Seleccione los campos que desea incluir en la salida para este módulo.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL References]</td> 
   <td>Seleccione los campos de referencia que desea incluir en la búsqueda.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Collections]</td> 
   <td>Seleccione las colecciones que desea añadir a la búsqueda.</td> 
  </tr> 
 </tbody> 
</table>

+++

<!--not visible Jan 6, 2025

+++ **[!UICONTROL Search (Legacy)]**

This search module looks for records in an object in Workfront that match the search query you specify.

You can map this information in subsequent modules in the scenario.

When you are configuring this module, the following fields display.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your Workfront app to Workfront Fusion, see <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Connect Workfront to Workfront Fusion</a> in this article.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Select the type of Workfront record that you want the module to search for.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Result Set]</td> 
   <td>Select an option to specify whether you want the module to get the first result that matches your search criteria or all the results that match it.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximal]</td> 
   <td> <p>Enter or map the maximum number of records you want the module to return during each scenario execution cycle.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search criteria]</td> 
   <td> <p>Enter the field that you want to search by, the operator you want to use in your query, and the value that you are searching for in the field.</p> <p>Note: Do not use <code>username </code>in your search criteria. Including <code>username </code>in an API query to Workfront logs the user into Workfront, and the search will not be successful.</p> <p>Note: <code>In</code> and <code>NotIn</code>work with arrays. The inputs should be in array format.</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Outputs]</td> 
   <td> <p>Select the fields that you want to include in the output for this module.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL References]</td> 
   <td>Select any reference fields that you want to include in the search.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Collections]</td> 
   <td>Select any collections that you want to add to the search.</td> 
  </tr> 
 </tbody> 
</table>

See a list of the Workfront object types for which you can use this module in [Workfront object types available for each Workfront module](#workfront-object-types-available-for-each-workfront-module).

+++-->

## Tipos de objetos de Workfront disponibles para cada módulo de Workfront

<!-- [Object types available for each Workfront trigger module](#object-types-available-for-each-workfront-trigger-module) 
* [Object types available for each Workfront action module](#object-types-available-for-each-workfront-action-module) 
* [Object types available for each Workfront search module](#object-types-available-for-each-workfront-search-module)-->

+++**Tipos de objetos disponibles para cada módulo de déclencheur de Workfront**

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col>         
 <thead> 
  <tr> 
   <th> </th> 
   <th>[!UICONTROL Watch Record]</th> 
   <th>[!UICONTROL Watch Field]</th> 
   <th>[!UICONTROL Watch Events]</th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>Proceso de aprobación</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Asignación</td> 
   <td> </td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Línea base</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Registro de facturación </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Tarifa de facturación</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Compañía</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Panel de control</td> 
   <td> </td> 
   <td> </td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Documento</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Carpeta de documentos</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Solicitud de documento</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Versión de documento</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Gasto</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Tipo de gasto</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Grupo</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Hora</td> 
   <td> </td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Tipo de hora</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Problema</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Iteración</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Función</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Entrada de cuaderno</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Hito</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Ruta de hitos</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Nota</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Etiqueta de nota</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Portafolio</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Programa</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Proyecto</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Usuario de proyecto</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Aprobación de revisión</td> 
   <td> </td> 
   <td> </td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Tiempo reservado* </td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Informe</td> 
   <td> </td> 
   <td> </td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Riesgo</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Tipo de riesgo</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Aprobador de paso</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Tarea</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Equipo</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Plantilla</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Tarea de plantilla</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Plantilla de horas</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Usuario</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Actualizar</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**Tipos de objetos disponibles para cada módulo de acción de Workfront**

>[!NOTE]
>
>El módulo [!UICONTROL Descargar documento] no se incluye en esta tabla porque los tipos de objetos de Workfront no forman parte de su configuración.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <col> 
 <col> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th> </th> 
   <th>[!UICONTROL Create a record]</th> 
   <th>[!UICONTROL Update a record]</th> 
   <th>[!UICONTROL Delete a record]</th> 
   <th>[!UICONTROL Upload Document]</th> 
   <th>[!UICONTROL Read a record]</th> 
   <th>[!UICONTROL Custom API Call]</th> 
   <th>[!UICONTROL Misc Action]</th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>Proceso de aprobación</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Asignación</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Línea base</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
   <tr> 
   <td>Registro de facturación</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Tarifa de facturación</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Compañía</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Documento</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Carpeta de documentos</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Versión de documento</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Tipo de cambio</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Gasto</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Tipo de gasto</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Documento externo</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Grupo</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Hora</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Tipo de hora</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Problema</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Iteración</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Función</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Entrada de cuaderno</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Hito</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Ruta de hitos</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Nota</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Etiqueta de nota</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Portafolio</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Programa</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Proyecto</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Usuario de proyecto</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Tiempo reservado* </td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Riesgo</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Tipo de riesgo</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Aprobador de paso</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Tarea</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Equipo</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Plantilla</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Tarea de plantilla</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Plantilla de horas</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Usuario</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Actualizar</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**Tipos de objetos disponibles para cada módulo de búsqueda de Workfront**

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th> </th> 
   <th>[!UICONTROL Search]</th> 
   <th>[!UICONTROL Read Related Records]</th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>Proceso de aprobación</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Asignación</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Registro de facturación</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Tarifa de facturación</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Compañía</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Documento</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Carpeta de documentos</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Versión de documento</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Gasto</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Tipo de gasto</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Grupo</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Hora</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Tipo de hora</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Problema</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Iteración</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Función</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Entrada de cuaderno</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Hito</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Ruta de hitos</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Nota</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Etiqueta de nota</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Portafolio</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Programa</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Proyecto</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Usuario de proyecto</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Tiempo reservado* </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Riesgo</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Tipo de riesgo</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Aprobador de paso</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Tarea</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Equipo</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Plantilla</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Tarea de plantilla</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Plantilla de horas</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Usuario</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Delegación de usuario</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

Le recomendamos que lo verifique bien para asegurarse de que esto funciona de la manera prevista.

+++

## Filtros de suscripción a eventos en los módulos Workfront > [!UICONTROL Ver eventos]

>[!NOTE]
>
>* Recomendamos encarecidamente usar filtros de suscripción de eventos en sus módulos Ver eventos de .
>
>* Workfront acaba de lanzar una nueva versión de su servicio de suscripción a eventos. La nueva versión no es un cambio en la API de Workfront, sino un cambio en la funcionalidad de suscripción de evento. Este módulo de acción actualiza la versión de carga útil de evento utilizada para este escenario.
>
>   Para obtener más información sobre la nueva versión de suscripción de evento, consulte [Versiones de suscripción de evento](https://experienceleague.adobe.com/en/docs/workfront/using/adobe-workfront-api/event-subscriptions/event-subs-versioning) en la documentación de Workfront
>
>   Para obtener recursos sobre cómo preservar los escenarios de Workfront Fusion durante la actualización de la suscripción al evento, incluida una grabación del seminario web, consulte [Conservación de los escenarios de Fusion durante la actualización de la versión 2.0 de las suscripciones al evento(https://experienceleaguecommunities.adobe.com/t5/workfront-discussions/event-follow-up-preserving-your-fusion-scenarios-during-the/td-p/754182)].

El módulo [!UICONTROL Ver eventos] de Workfront déclencheur los escenarios en función de un enlace web que crea una suscripción de evento en la API de Workfront. La suscripción de eventos es un conjunto de datos que determina qué eventos se envían al webhook. Por ejemplo, si configura un módulo [!UICONTROL Ver eventos] que vigila problemas, la suscripción de eventos solo enviará eventos relacionados con los problemas.

Mediante filtros de suscripción de eventos, los usuarios de Fusion pueden crear suscripciones de eventos que se adapten mejor a sus casos de uso. Por ejemplo, puede configurar una suscripción de evento en la API de Workfront para enviar al webhook solo los problemas que estén en un proyecto específico, asegurándose de que el módulo [!UICONTROL Ver eventos] solo entrará en déclencheur para los problemas de ese proyecto. La capacidad de crear activadores más limitados mejora el diseño de escenarios al reducir el número de activadores irrelevantes.

Esto es diferente a la configuración de un filtro en el escenario de Workfront Fusion. Sin un filtro de suscripción de eventos, el webhook recibe todos los eventos relacionados con el tipo de objeto seleccionado. La mayoría de estos eventos serían irrelevantes para el escenario y deben filtrarse para que el escenario pueda continuar.

Los siguientes operadores están disponibles en el filtro Workfront > Ver eventos:

* Es igual a
* No es igual a
* Mayor que
* Menor que
* Mayor o igual que
* Menor o igual que
* Contiene
* Existe
   * Este operador no requiere un valor y el campo de valor está ausente.
* No existe
   * Este operador no requiere un valor y el campo de valor está ausente.
* Cambiado
   * Este operador no requiere un valor y el campo de valor está ausente.
   * Este operador ignora el campo Estado.
   * Cuando use `Changed`, seleccione **Solo eventos actualizados** en el campo **Origen del registro**.

>[!IMPORTANT]
>
>No puede editar filtros en webhooks de Workfront existentes. Para configurar diferentes filtros para las suscripciones a eventos de Workfront, elimine el webhook actual y cree uno nuevo.

>[!INFO]
>
>**Ejemplo:** considere un escenario que procese nuevos problemas asignados a una usuaria específica, Ana.
>
>### Filtrado de eventos mediante un filtro de suscripción de eventos (recomendado)
>
>Mediante el filtro de eventos, puede configurar el webhook para que active el escenario cuando se asigne un problema a Ana cuando se cree el problema. Ana tiene el userID b378489d8f7cd3cee0539260720a84b7.
>
>![Filtro de eventos](/help/workfront-fusion/references/apps-and-modules/assets/event-filter-watch-events-350x277.png)
>
>Si se crean 100 problemas en un día, pero solo dos de ellos se asignan a Ana, el escenario se ejecutaría dos veces.
>
>### Filtrar eventos dentro del escenario (no recomendado)
>
>Para filtrar eventos de modo que solo se procesen los problemas asignados a Ana, puede crear un filtro después del módulo [!UICONTROL Ver eventos].
>
>![Sin filtro de eventos](/help/workfront-fusion/references/apps-and-modules/assets/watch-events-non-event-filter-350x206.png)
>
>Si se crean 100 problemas en un día, pero solo dos de ellos se asignan a Ana, el escenario se ejecutaría 100 veces. 98 de las ejecuciones se detendrían en el filtro, pero el módulo de activador sigue consumiendo datos y realizando operaciones en todas las ejecuciones.

Para obtener más información sobre las suscripciones a eventos de Workfront, consulte [Preguntas más frecuentes - Suscripciones a eventos](https://experienceleague.adobe.com/en/docs/workfront/using/adobe-workfront-api/event-subscriptions/event-subs-faq).

Para obtener más información sobre los webhooks, consulte [déclencheur instantáneos (webhooks) en Adobe Workfront Fusion](/help/workfront-fusion/references/modules/webhooks-reference.md)

Para obtener más información sobre los filtros en los escenarios, vea [Agregar un filtro a un escenario](/help/workfront-fusion/create-scenarios/add-modules/add-a-filter-to-a-scenario.md).
