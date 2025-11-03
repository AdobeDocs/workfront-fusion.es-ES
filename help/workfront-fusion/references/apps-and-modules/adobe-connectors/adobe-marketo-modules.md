---
title: Módulos Marketo
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan  [!DNL Marketo], así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: da417ac7-e532-45f7-86d9-3643b5f9f203
source-git-commit: 1929bf897e9263ec551e93df776b96f419436715
workflow-type: tm+mt
source-wordcount: '2237'
ht-degree: 64%

---

# Módulos de [!DNL Marketo]

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!DNL Marketo], así como conectarlo a varias aplicaciones y servicios de terceros.

Para ver un vídeo introductorio del conector de Marketo, consulte:

* [Marketo](https://video.tv.adobe.com/v/3427026/){target=_blank}

Para obtener instrucciones sobre cómo crear un escenario, vea los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront</td> 
   <td> <p>Cualquier paquete de flujo de trabajo de Adobe Workfront y cualquier paquete de integración y automatización de Adobe Workfront</p><p>Workfront Ultimate</p><p>Paquetes Workfront Prime y Select, con una compra adicional de Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencias de Adobe Workfront</td> 
   <td> <p>Estándar</p><p>Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion</td> 
   <td>
   <p>Basado en operaciones: no se requiere licencia de Workfront Fusion</p>
   <p>Basado en conectores (heredado): Workfront Fusion para la automatización e integración del trabajo </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete Select o Prime Workfront que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Para usar módulos [!DNL Marketo], debe tener una cuenta de [!DNL Marketo].

## Información de API de Marketo

El conector de Marketo utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> Versión 1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.14.19</td> 
  </tr>
 </tbody> 
 </table>

## Conexión de [!DNL Marketo] a Workfront Fusion {#connect-marketo-to-workfront-fusion}

Puede crear una conexión con su cuenta de [!DNL Marketo] directamente desde cualquier módulo de [!DNL Marketo].

1. En cualquier módulo de Marketo, haga clic en **Agregar** junto al campo Conexión.
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
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>
          <p>Seleccione si desea conectarse a una cuenta de servicio o a una personal.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Cuenta / Munchkin ID]</td>
        <td>
          <p>Escriba su cuenta de [!DNL Marketo] o [!DNL Marketo] ID de [!UICONTROL Munchkin]. Esta es la única parte de la dirección URL base o extremo asignado a su cuenta que usa para acceder a [!DNL Marketo] a través de su API de [!UICONTROL REST]. Para obtener instrucciones sobre cómo encontrar esto, consulte [URL básica](https://developers.marketo.com/rest-api/base-url/) en la documentación de [!DNL Marketo].</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Introduzca su ID de cliente de Marketo. Para obtener instrucciones sobre cómo encontrar esto, consulte [Authentication](https://developers.marketo.com/rest-api/authentication/) en la documentación de [!DNL Marketo].</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Escriba el Secreto de cliente de Marketo. Para obtener instrucciones sobre cómo localizarlos, consulte [Authentication](https://developers.marketo.com/rest-api/authentication/) en la documentación de [!DNL Marketo].</td>
      </tr>
     </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continuar]** para crear la conexión y volver al módulo.

## Módulos de [!DNL Marketo] y sus campos

Al configurar módulos de [!DNL Marketo], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL Marketo] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Activadores](#triggers)
* [Acciones](#actions)
* [Búsquedas](#searches)

### Activadores

* [[!UICONTROL Ver eventos (instantáneo)]](#watch-events-instant)
* [[!UICONTROL Ver registros]](#watch-records)

#### [!UICONTROL Ver eventos (instantáneo)]

Este módulo de activador inicia un escenario cuando se crea o se actualiza un registro.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Webhook]</p> </td> 
   <td> <p>Introduzca el webhook que desea que utilice el módulo.</p> <p>Para obtener más información sobre los webhooks, consulte <a href="/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md" class="MCXref xref">Webhooks</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Ver registros]

Este módulo de activador inicia un escenario cuando se crea o se actualiza un registro.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Marketo] a Workfront Fusion, consulte <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Marketo] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro que desea crear.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Activity]</strong> </p> <p>Seleccione el tipo de actividad que desea ver. </p> <p>El módulo solo ve las nuevas actividades.<br></p> </li> 
     <li> <p><strong>[!UICONTROL Lead]</strong> </p> <p>En el campo <b>Tipo de evento</b>, seleccione si desea buscar registros nuevos, registros actualizados, registros nuevos y actualizados o actualizaciones de campos específicas. Si selecciona ver actualizaciones de campos específicos, seleccione el campo que desea que el módulo vea.</p> </li> 
     <li> <p><strong>[!UICONTROL Programa]</strong> </p> <p>En el campo <b>Tipo de evento</b>, seleccione si desea inspeccionar registros nuevos, registros actualizados o registros nuevos y actualizados.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Seleccione los campos que desee incluir en el paquete de salida para este módulo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Acciones

* [[!UICONTROL Añadir posibles clientes a una lista]](#add-leads-to-a-list)
* [[!UICONTROL Clonar un programa]](#clone-a-program)
* [[!UICONTROL Create a record]](#create-a-record)
* [[!UICONTROL Llamada de API personalizada]](#custom-api-call)
* [[!UICONTROL Descargar un archivo]](#download-a-file)
* [[!UICONTROL Leer un registro]](#read-a-record)
* [[!UICONTROL Quitar posibles clientes de una lista]](#remove-leads-from-a-list)
* [[!UICONTROL Programar una campaña]](#schedule-a-campaign)
* [[!UICONTROL Actualizar un registro]](#update-a-record)
* [[!UICONTROL Subir un archivo]](#upload-a-file)

#### [!UICONTROL Añadir posibles clientes a una lista]

Este módulo de acción agrega uno o más posibles clientes a una lista mediante el uso del ID de posible cliente. Puede añadir hasta 300 posibles clientes a la vez.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Marketo] a Workfront Fusion, consulte <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Marketo] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List ID]</td> 
   <td>Introduzca o asigne el ID de la lista a la que desea añadir posibles clientes.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Lead IDs]</td> 
   <td> <p>Para cada posible cliente que desee añadir a la lista, haga clic en <b>[!UICONTROL Añadir]</b> y, a continuación, escriba o asigne el identificador del posible cliente que desee añadir. Puede añadir hasta 300 posibles clientes para que el módulo los añada a la lista.</p> <p>Haga clic en el botón de alternancia Asignar para asignar una colección existente de posibles clientes que desee añadir a la lista.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Clonar un programa]

Este módulo de acción realiza una copia de un programa utilizando el ID del programa existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Marketo] a Workfront Fusion, consulte <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Marketo] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de programa existente]</td> 
   <td>Introduzca o asigne el ID del programa que desea copiar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Nuevo nombre de programa]</p> </td> 
   <td> <p>Introduzca o asigne un nombre para el nuevo programa</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID]</td> 
   <td>Introduzca o asigne el ID de la carpeta en la que desea ubicar el nuevo programa.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Crear un registro]

Este módulo de acción crea un nuevo registro en [!DNL Marketo]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Marketo] a Workfront Fusion, consulte <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Marketo] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro que desea crear.</p> 
    <ul> 
     <li> <p>[!UICONTROL Company]</p> </li> 
     <li> <p>[!UICONTROL Folder]</p> </li> 
     <li> <p>[!UICONTROL Lead]</p> </li> 
     <li> <p>[!UICONTROL Program]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select fields to map]</td> 
   <td>Si está creando una compañía o un posible cliente, seleccione los campos para los que desea establecer valores cuando se cree el nuevo registro y, a continuación, introduzca los valores de estos campos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tipo de programa]</td> 
   <td>Si está creando un programa, seleccione el tipo de programa que desea crear.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Canal de programa] </td> 
   <td>Si está creando un programa, seleccione el canal de programa en el que desea crear el programa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Carpeta] / [!UICONTROL Nombre del programa]</td> 
   <td>Si está creando una carpeta o programa, escriba o asigne un nombre para el nuevo registro.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td> <p>Si está creando una carpeta o un programa, introduzca o asigne una descripción para el nuevo registro.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Parent Folder ID]</td> 
   <td>Si va a crear una carpeta o un programa, escriba o asigne el identificador de la carpeta principal en la que desea crear el nuevo registro.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Costs]</td> 
   <td>Si está creando un programa, añada los costes.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tags]</td> 
   <td>Si está creando un programa, añada las etiquetas</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Llamada de API personalizada]

Este módulo de acción le permite realizar una llamada autenticada personalizada a la API de [!DNL Marketo]. De este modo, puede crear una automatización del flujo de datos que no puedan realizar los otros módulos de [!DNL Marketo].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Marketo] a Workfront Fusion, consulte <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Marketo] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Escriba una ruta relativa a <code>https://{your-base-url}.mktorest.com/</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>[!UICONTROL Workfront Fusion] añade los encabezados de autorización automáticamente.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Añada la consulta para la llamada de API en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td> <p>Para cada campo que desee agregar a su llamada de API, haga clic en <b>Agregar elemento</b> e introduzca la clave y el valor del campo.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Descargar un archivo]

Este módulo de acción descarga un archivo mediante el ID de archivo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Marketo] a Workfront Fusion, consulte <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Marketo] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>Introduzca o asigne el ID del archivo que desea descargar.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Leer un registro]

Este módulo de acción lee información sobre un registro mediante su ID.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Marketo] a Workfront Fusion, consulte <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Marketo] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro que desea crear.</p> 
    <ul> 
     <li> <p>[!UICONTROL Campaign]</p> </li> 
     <li> <p>[!UICONTROL Company]</p> </li> 
     <li> <p>[!UICONTROL Lead]</p> </li> 
     <li> <p>[!UICONTROL List]</p> </li> 
     <li> <p>[!UICONTROL Program]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Seleccione la información que desea incluir en el paquete de salida para este módulo. Los campos están disponibles en función del [!UICONTROL Record Type] seleccionado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL &lt;Object&gt; ID]</td> 
   <td>Introduzca o asigne el ID del objeto sobre el que desea recuperar información.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Quitar posibles clientes de una lista]

Este módulo de acción elimina uno o más posibles clientes de una lista mediante el uso del ID de posible cliente. Puede eliminar hasta 300 posibles clientes a la vez.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Marketo] a Workfront Fusion, consulte <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Marketo] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List ID]</td> 
   <td>Introduzca o asigne el ID de la lista donde desea quitar los posibles clientes.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Lead IDs]</td> 
   <td> <p>Para cada posible cliente que desee eliminar de la lista, haga clic en <b>[!UICONTROL Agregar elemento]</b> y, a continuación, escriba o asigne el identificador del posible cliente que desee eliminar. Puede añadir hasta 300 posibles clientes para que el módulo los quite de la lista. </p> <p>Haga clic en el botón de alternancia Asignar para asignar una colección existente de posibles clientes que desee eliminar de la lista.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Programar una campaña]

Este módulo de acción programa una campaña existente para una fecha determinada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Marketo] a Workfront Fusion, consulte <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Marketo] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Campaign ID]</td> 
   <td>Introduzca o asigne el ID de la campaña que desea programar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Programación para la fecha]</p> </td> 
   <td>Seleccione la fecha en la que desea ejecutar la campaña. Si este campo se deja en blanco, la campaña se ejecuta cinco minutos después de que comience el escenario.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Actualizar un registro]

Este módulo de acción actualiza un registro existente mediante su identificador.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Marketo] a Workfront Fusion, consulte <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Marketo] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro que desea crear.</p> 
    <ul> 
     <li> <p>[!UICONTROL Company]</p> </li> 
     <li> <p>[!UICONTROL Lead]</p> </li> 
     <li> <p>[!UICONTROL Program]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Compañía] / [!UICONTROL Posible cliente] / [!UICONTROL Programa ID]</td> 
   <td>Introduzca o asigne el ID del registro que desea actualizar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select fields to map]</td> 
   <td>Si está actualizando una compañía o un posible cliente, seleccione los campos para los que desee actualizar los valores e introduzca los valores de dichos campos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Nombre de programa]</td> 
   <td>Si va a actualizar un programa, escriba o asigne un nombre nuevo para el programa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td> <p>Si va a actualizar un programa, escriba o asigne una nueva descripción para el programa.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start Date]</td> 
   <td>Si va a actualizar un programa, introduzca o asigne una nueva fecha de inicio para el programa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL End Date]</td> 
   <td>Si va a actualizar un programa, introduzca o asigne una nueva fecha de finalización para el programa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Costs]</td> 
   <td>Si va a actualizar un programa, añada los costes.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tags]</td> 
   <td>Si va a actualizar un programa, añada las etiquetas </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Subir un archivo]

Este módulo de acción sube un nuevo archivo a [!UICONTROL Marketo].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Marketo] a Workfront Fusion, consulte <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Marketo] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID]</td> 
   <td>Introduzca o asigne el ID de la carpeta en la que desea ubicar el nuevo archivo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Escriba una descripción para el archivo que ha subido.</td> 
  </tr> 
 </tbody> 
</table>

### Búsquedas

* [[!UICONTROL Enumerar registros]](#list-records)
* [[!UICONTROL Buscar registros]](#update-a-record)

#### [!UICONTROL Enumerar registros]

Este módulo de acción recupera todos los registros de un tipo específico.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Marketo] a Workfront Fusion, consulte <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Marketo] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro que desea enumerar.</p> 
    <ul> 
     <li> <p>[!UICONTROL Leer todas las campañas]</p> </li> 
     <li> <p>[!UICONTROL Leer todos los programas]</p> </li> 
     <li> <p>[!UICONTROL Leer todos los posibles clientes] </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Field]</td> 
   <td>Si ha seleccionado recuperar posibles clientes, seleccione si desea recuperar posibles clientes de una lista o de un programa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Seleccione la información que desea incluir en el paquete de salida para este módulo. Los campos están disponibles en función del [!UICONTROL Record Type] seleccionado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Buscar registros]

Este módulo de búsqueda recupera una lista de registros que coinciden con criterios de búsqueda específicos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Marketo] a Workfront Fusion, consulte <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Marketo] a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>Seleccione el tipo de registro que desea buscar.</p> 
    <ul> 
     <li> <p>[!UICONTROL Campañas]</p> </li> 
     <li> <p>[!UICONTROL Posibles clientes]</p> </li> 
     <li> <p>[!UICONTROL Programs]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Field]</p> </td> 
   <td> <p>Seleccione el campo por el que desea buscar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Valor / valores]</td> 
   <td>Introduzca el valor del campo que desea buscar. Si el campo le permite buscar varios valores, para cada valor que desee buscar, haga clic en <b>[!UICONTROL Agregar elemento]</b> e introduzca el valor.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Salida]</td> 
   <td> <p>Seleccione la información que desea incluir en el paquete de salida para este módulo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>
