---
title: Módulos de Bibliotecas de Adobe Creative Cloud
description: Con los módulos de Bibliotecas de  [!DNL Adobe Workfront Fusion Adobe Creative Cloud] , puede iniciar un escenario cuando se cree o actualice un elemento o biblioteca. También puede cargar, recuperar, archivar o enumerar elementos, o bien realizar una llamada a la API  [!DNL Adobe Creative Cloud Libraries] .
author: Becky
feature: Workfront Fusion
exl-id: 85607e4e-538a-427f-8a99-a0ab65a75ac2
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '1393'
ht-degree: 82%

---

# Módulos de Bibliotecas de Adobe Creative Cloud

Con los módulos [!DNL Adobe Workfront Fusion] [!DNL Adobe Creative Cloud Libraries], puede iniciar un escenario cuando se cree o actualice un elemento o biblioteca. También puede cargar, recuperar, archivar o enumerar elementos, o bien realizar una llamada a la API [!DNL Adobe Creative Cloud Libraries].

Si necesita instrucciones sobre cómo crear un escenario, vea los artículos en [Crear un escenario: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

>[!IMPORTANT]
>
>Actualmente, la creación de conexiones no está disponible en el conector de Bibliotecas de Creative Cloud. Las conexiones existentes funcionan según lo esperado.

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

Para usar módulos de [!DNL Adobe Creative Cloud Libraries], debe tener una cuenta de [!UICONTROL Adobe Creative Cloud].

## Información de API de bibliotecas Adobe Creative Cloud

El conector Bibliotecas Adobe Creative Cloud utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL básica</td> 
   <td>https://cc-libraries.adobe.io/api/v1</td> 
  </tr>
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.1.7</td> 
  </tr>
 </tbody> 
 </table>

## Módulos de las [!UICONTROL Bibliotecas de Adobe Creative Cloud] y sus campos

Al configurar los módulos de [!UICONTROL Bibliotecas de Adobe Creative Cloud], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse campos de [!DNL Adobe Creative Cloud Libraries] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)


* [Elementos](#elements)

* [Bibliotecas](#libraries)

* [Otro](#other)


### Elementos

* [[!UICONTROL Archivar un elemento]](#archive-an-element)

* [[!UICONTROL Obtener un elemento]](#get-an-element)

* [[!UICONTROL Enumerar elementos]](#list-elements)

* [[!UICONTROL Cargar un elemento]](#upload-an-element)

* [!UICONTROL [Watch New Element in Library]](#watch-new-element-in-library)

* [[!UICONTROL Ver elementos actualizados]](#watch-updated-elements)


#### [!UICONTROL Archivar un elemento]

Este módulo de acción archiva un elemento de una biblioteca.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Seleccionar una conexión de Bibliotecas de Creative Cloud existente. Actualmente, la creación de conexiones no está disponible en el conector de Bibliotecas de Creative Cloud. Las conexiones existentes funcionan según lo esperado.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >Seleccione o asigne la biblioteca que contiene el elemento que desea archivar.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Element ID]</td>
      <td>Seleccione o asigne el elemento que desea archivar.</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Obtener un elemento]

Este módulo de acción devuelve un solo elemento de una biblioteca.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Seleccionar una conexión de Bibliotecas de Creative Cloud existente. Actualmente, la creación de conexiones no está disponible en el conector de Bibliotecas de Creative Cloud. Las conexiones existentes funcionan según lo esperado.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td>Seleccione o asigne la biblioteca que contiene el elemento que desea recuperar.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Element ID]</td>
      <td>Introduzca o asigne el ID del elemento que desea recuperar.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Selector]</td>
      <td>
        <p>Seleccione el tipo de información que devuelve el módulo. </p>
        <ul>
          <li>
            <p><b>[!UICONTROL Default]</b>
            </p>
            <p>Datos base</p>
          </li>
          <li>
            <p><b>[!UICONTROL Details]</b>
            </p>
            <p>Todos los datos disponibles</p>
          </li>
          <li>
            <p><b>[!UICONTROL Representations]</b>
            </p>
            <p>Una lista aplanada de recursos asociados al elemento de biblioteca</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Enumerar elementos]

Este módulo de acción recupera una lista de elementos de una biblioteca.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Seleccionar una conexión de Bibliotecas de Creative Cloud existente. Actualmente, la creación de conexiones no está disponible en el conector de Bibliotecas de Creative Cloud. Las conexiones existentes funcionan según lo esperado.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >Seleccione o asigne la biblioteca de la que desee enumerar los elementos.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Order by]</td>
      <td>Seleccione si desea ordenar los resultados por nombre o por la última fecha de modificación del elemento.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Type]</td>
      <td >Introduzca o asigne un tipo MIME para limitar los resultados a los elementos identificados con el tipo MIME especificado. Ejemplo: <code>string</code>.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Selector]</td>
      <td>
        <p>Seleccione el tipo de información que devuelve el módulo. </p>
        <ul>
          <li>
            <p><b>[!UICONTROL Default]</b>
            </p>
            <p>Datos base</p>
          </li>
          <li>
            <p><b>[!UICONTROL Details]</b>
            </p>
            <p>Todos los datos disponibles</p>
          </li>
          <li>
            <p><b>[!UICONTROL Representations]</b>
            </p>
            <p>Una lista aplanada de recursos asociados al elemento de biblioteca</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]</td>
      <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Ver nuevo elemento en la biblioteca]

Este módulo de activador inicia un escenario cuando se añade un elemento a una biblioteca.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Seleccionar una conexión de Bibliotecas de Creative Cloud existente. Actualmente, la creación de conexiones no está disponible en el conector de Bibliotecas de Creative Cloud. Las conexiones existentes funcionan según lo esperado.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >Seleccione la biblioteca en la que desea ver los elementos actualizados.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]</td>
      <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td>
    </tr>
  </tbody>
</table>


#### [!UICONTROL Ver elementos actualizados]

Este módulo de activador inicia un escenario cuando se actualiza un elemento de una biblioteca.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Seleccionar una conexión de Bibliotecas de Creative Cloud existente. Actualmente, la creación de conexiones no está disponible en el conector de Bibliotecas de Creative Cloud. Las conexiones existentes funcionan según lo esperado.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >Seleccione la biblioteca en la que desea ver los nuevos elementos.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]</td>
      <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td>
    </tr>
  </tbody>
</table>

### Bibliotecas

* [[!UICONTROL Ver bibliotecas nuevas]](#watch-new-libraries)

* [[!UICONTROL Ver bibliotecas actualizadas]](#watch-updated-libraries)


#### [!UICONTROL Ver bibliotecas nuevas]

Este módulo de activador inicia un escenario cuando se crea una biblioteca nueva.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Seleccionar una conexión de Bibliotecas de Creative Cloud existente. Actualmente, la creación de conexiones no está disponible en el conector de Bibliotecas de Creative Cloud. Las conexiones existentes funcionan según lo esperado.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]</td>
      <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Ver bibliotecas actualizadas]

Este módulo de activador inicia un escenario cuando se actualiza una biblioteca existente.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Seleccionar una conexión de Bibliotecas de Creative Cloud existente. Actualmente, la creación de conexiones no está disponible en el conector de Bibliotecas de Creative Cloud. Las conexiones existentes funcionan según lo esperado.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]</td>
      <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td>
    </tr>
  </tbody>
</table>

### Otro

* [Realizar una llamada de API](#make-an-api-call)
* [Cargar un recurso](#upload-an-asset)

#### [!UICONTROL Realizar una llamada de API]

Este módulo realiza una llamada de API personalizada a la API de [!DNL Adobe Creative Cloud Libraries].

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Creative Cloud a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con Adobe Workfront Fusion: instrucciones básicas.</a></p>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p>Escriba una ruta relativa a <code>https://cc-libraries.adobe.io/api</code>.</p>
    <p>Por ejemplo, <code>/v1/libraries</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL API version]</td>
      <td>
        <p>Seleccione la versión de la API [!DNL Adobe Analytics] a la que desea conectarse.</p>
      </td>
    </tr>    <tr>
      <td role="rowheader">[!UICONTROL Method]</td>
      <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Métodos de solicitud HTTP</a>.</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p>
        <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion añade los encabezados de autorización para usted.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Query String]</td>
      <td>
        <p>Añada la consulta para la llamada de API en forma de objeto JSON estándar.</p>
        <p>Por ejemplo: <code>{"name":"something-urgent"}</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Body]</td>
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la instrucción condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
       <tr>
      <td role="rowheader">[!UICONTROL Upload a transient document]</td>
      <td>
      <p>Si desea cargar un documento transitorio, introduzca el archivo de origen del documento que desea cargar.</p>
      <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p>
    </td>
    </tr>
</tbody>
</table>


#### [!UICONTROL Cargar un recurso]

Este módulo de acción carga un recurso de archivo pequeño en una biblioteca existente. El tamaño máximo de archivo es de 1 GB.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Seleccionar una conexión de Bibliotecas de Creative Cloud existente. Actualmente, la creación de conexiones no está disponible en el conector de Bibliotecas de Creative Cloud. Las conexiones existentes funcionan según lo esperado.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >Seleccione la biblioteca en la que desea cargar un recurso.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Invocation Mode]</td>
      <td>
        <p>Seleccione el modo de procesamiento con el que invocar este proceso de solicitud.</p>
        <ul>
          <li>
            <p><b>[!UICONTROL sync]</b>
            </p>
            <p>La llamada de la API se procesa de forma síncrona. La respuesta se envía cuando se completa el procesamiento (salvo que se agote el tiempo de espera de la llamada).</p>
          </li>
          <li>
            <p><b>[!UICONTROL async]</b>
            </p>
            <p>La respuesta asíncrona del monitor se devuelve inmediatamente y el procesamiento de la solicitud se produce de forma asíncrona. La llamada es responsable del sondeo del punto final hasta la finalización.</p>
          </li>
          <li>
            <p><b>[!UICONTROL sync,async]</b> (predeterminado)</p>
            <p>Se intenta el procesamiento síncrono de la solicitud. Cuando el procesamiento se extiende más allá de 5000 ms, se devuelve la respuesta asíncrona del monitor. Se debe sondear la URL del monitor hasta que se complete la solicitud.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Tipo de elemento]</td>
      <td >Seleccione el tipo de elemento que desea cargar</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Tipo de archivo]</td>
      <td >Introduzca o asigne el tipo MIME del archivo cargado.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Source File]</td>
      <td>
        <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p>
      </td>
    </tr>
  </tbody>
</table>





