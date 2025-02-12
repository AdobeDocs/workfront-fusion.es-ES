---
filename: workday-modules
title: Módulos de Workday
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan  [!DNL Workday], así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: 77237a1b-2acd-4350-9cc0-ec43b8b08137
source-git-commit: fedf8f3f4031faaad9f81ed38fbc77e40e3a85b6
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 46%

---

# Módulos de [!DNL Workday]

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!DNL Workday], así como conectarlo a varias aplicaciones y servicios de terceros.

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
   <p>Actual: no se requiere licencia de Workfront Fusion.</p>
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

Para usar los módulos [!DNL Workday], debe:

* Tener una cuenta de [!DNL Workday].

* Crear una aplicación OAuth en [!DNL Workday]. Para obtener instrucciones, consulte la documentación de [!DNL Workday].

## Información de API de Workday

El conector de Workday utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL básica</td> 
   <td>https://{{connection.servicesUrl}}/api</td> 
  </tr>
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.6.4</td> 
  </tr>
 </tbody> 
 </table>

## Conectar [!DNL Workday] a [!DNL Workfront Fusion]

1. En cualquier módulo de [!DNL Workfront Fusion], haga clic en [!UICONTROL Add] junto al campo [!UICONTROL Connection]

2. Rellene los campos siguientes:

   <table style="table-layout:auto"> 
        <col/>
        <col/>
        <tbody>
            <tr>
                <td role="rowheader">
                    <p role="rowheader">[!UICONTROL Connection name]</p>
                </td>
                <td>Introduzca un nombre para la conexión</td>
            </tr>
            <tr>
                <td  role="rowheader">[!UICONTROL Workday host]</td>
                <td>Escriba la dirección de su host [!DNL Workday] sin <code>https://</code>. Por ejemplo, <code>mycompany.workday.com</code></td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL Services URL]</td>
                <td>Escriba la dirección de los servicios web de [!DNL Workday] sin <code>https://</code>. Por ejemplo, <code>mycompany-services.workday.com</code></td>
            </tr>
            <tr>
                <td  role="rowheader">[!UICONTROL Tenant name]</td>
                <td>Escriba el inquilino de esta cuenta de [!DNL Workday]. El inquilino es el identificador de su organización y se puede ver en la dirección URL que utiliza para iniciar sesión en Workday. Ejemplo: en la dirección <code>https://www.myworkday.com/mycompany</code>, el usuario es <code>mycompany</code>.</td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL Client ID]</td>
                <td>Escriba el Id. de cliente para la aplicación [!DNL Workday] que utiliza esta conexión. Esto se obtiene al crear la aplicación en [!DNL Workday].</td>
            </tr>
            <tr>
                <td  role="rowheader">[!UICONTROL Client Secret]</td>
                <td>Escriba el Secreto de cliente para la aplicación [!DNL Workday] que utiliza esta conexión. Esto se obtiene al crear la aplicación en [!DNL Workday].</td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL Session timeout (min)]</td>
                <td >Introduzca el número de minutos tras los cuales caduca el token de autorización.</td>
            </tr>
        </tbody>
    </table>


3. Haga clic en [!UICONTROL Continue] para guardar la conexión y volver al módulo

## Módulos de [!DNL Workday] y sus campos

Al configurar módulos de [!DNL Workday], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Workday] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Acción](#action)

* [Buscar](#search)


### Acción

* [[!UICONTROL Create a record]](#create-a-record)

* [[!UICONTROL Delete a record]](#delete-a-record)

* [[!UICONTROL Make a custom API call]](#make-a-custom-api-call)

* [[!UICONTROL Update a record]](#update-a-record)


#### [!UICONTROL Create a record]

Este módulo de acción crea un único registro en [!DNL Workday].

<table style="table-layout:auto"> 
    <col/>
    <col/>
    <tbody>
        <tr>
            <td role="rowheader">[!UICONTROL Connection]</td>
            <td>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Workday] a Workfront Fusion, consulte <a href="#Connect" class="MCXref xref" >Conectar [!DNL Workday] a [!DNL Workfront Fusion]</a>.</td>
        </tr>
        <tr>
            <td  role="rowheader">[!UICONTROL Record Type]</td>
            <td>Seleccione el tipo de registro que desea crear.</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL ID] </td>
            <td>Introduzca o asigne el ID del registro que desea crear.</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL Subresource ID]</td>
            <td >Introduzca o asigne el ID del subrecurso que desea crear.</td>
        </tr>
    </tbody>
</table>

#### [!UICONTROL Delete a record]

Este módulo de acción elimina un único registro de [!DNL Workday].

<table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
        <tr>
            <td role="rowheader">[!UICONTROL Connection]</td>
            <td>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Workday] a [!DNL Workfront Fusion], vea <a href="#Connect" class="MCXref xref" >Conectar [!DNL Workday] a [!DNL Workfront Fusion]</a>.</td>
        </tr>
        <tr>
            <td  role="rowheader">[!UICONTROL Record type]</td>
            <td>Seleccione el tipo de registro que desea eliminar.</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL Specific record type]</td>
            <td>Seleccione el tipo de registro específico que desea eliminar. Se basan en el tipo de registro elegido.</td>
        </tr>
        <tr>
            <td  role="rowheader">[!UICONTROL Subresource ID]</td>
            <td>Introduzca o asigne el ID del subrecurso que desea eliminar.</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL ID] </td>
            <td >Introduzca o asigne el ID del registro que desea eliminar.</td>
        </tr>
    </tbody>
</table>


### [!UICONTROL Make a custom API call]

Este módulo de acción le permite realizar una llamada autenticada personalizada a la API [!DNL Workday]. De este modo, puede crear una automatización del flujo de datos imposibles de realizar por los otros [!DNL Workday] módulos.

Al configurar este módulo, se muestran los campos siguientes.

El módulo devuelve el código de estado, junto con los encabezados y el cuerpo de la llamada de API.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!DNL Connection]</p> </td> 
            <td>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Workday] a [!DNL Workfront Fusion], vea <a href="#Connect" class="MCXref xref" >Conectar [!DNL Workday] a [!DNL Workfront Fusion]</a>.</td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Escriba una ruta relativa a <code style="color: #ff1493;">https://&lt;tenantHostname>/api/&lt;serviceName>/&lt;version>/&lt;tenant></code>.</td> 
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
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a record]

Este módulo de acción actualiza un único registro en [!DNL Workday].

<table style="table-layout:auto"> 
    <col/>
    <col/>
    <tbody>
        <tr>
            <td role="rowheader">[!UICONTROL Connection]</td>
            <td>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Workday] a Workfront Fusion, consulte <a href="#Connect" class="MCXref xref" >[!UICONTROL Connect [!DNL Workday] a Workfront Fusion]</a></td>
        </tr>
        <tr>
            <td  role="rowheader">[!UICONTROL Record Type]</td>
            <td>Seleccione el tipo de registro que desee actualizar.</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL ID] </td>
            <td>Introduzca o asigne el ID del registro que desea actualizar.</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL Subresource ID]</td>
            <td >Introduzca o asigne el ID del subrecurso que desea actualizar.</td>
        </tr>
    </tbody>
</table>

### Buscar

* [[!UICONTROL Read a record]](#read-a-record)

* [[!UICONTROL List records]](#list-records)


#### [!UICONTROL Read a record]

Este módulo de acción lee un solo registro.

<table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
        <tr>
            <td role="rowheader">[!UICONTROL Connection]</td>
            <td>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Workday] a Workfront Fusion, consulte <a href="#Connect" class="MCXref xref" >[!UICONTROL Connect [!DNL Workday] a Workfront Fusion]</a></td>
        </tr>
        <tr>
            <td  role="rowheader">[!UICONTROL Record type]</td>
            <td>Seleccione el tipo de registro que desea eliminar.</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL Specific record type]</td>
            <td>Seleccione el tipo de registro específico que desea leer. Se basan en el tipo de registro elegido.</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL ID] </td>
            <td >Introduzca o asigne el ID del registro que desea eliminar.</td>
        </tr>
    </tbody>
</table>

#### [!UICONTROL List records]

Este módulo de búsqueda recupera una lista de registros del tipo especificado.

<table style="table-layout:auto"> 
      <col/>
      <col/>
      <tbody>
          <tr>
              <td role="rowheader">[!UICONTROL Connection]</td>
              <td>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Workday] a [!DNL Workfront Fusion], vea <a href="#Connect" class="MCXref xref" >Conectar [!DNL Workday] a [!DNL Workfront Fusion]</a></td>
          </tr>
          <tr>
              <td  role="rowheader">[!UICONTROL Record Type]</td>
              <td>Seleccione el tipo de registro que desea recuperar.</td>
          </tr>
          <tr>
              <td role="rowheader">[!UICONTROL Limit]</td>
              <td >
                  <p>Introduzca o asigne el número máximo de registros que desea que el módulo recupere durante cada ciclo de ejecución de escenario.</p>
              </td>
          </tr>
      </tbody>
  </table>
