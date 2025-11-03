---
title: Módulos de Adobe Workfront Planning
description: 'Con los módulos  [!DNL Adobe Workfront Planning] , puede iniciar un escenario de Adobe Workfront Fusion basado en los eventos de su cuenta de Workfront Planning, crear, leer o actualizar acuerdos y otros registros, buscar registros con los criterios que haya establecido y cargar documentos. [!DNL Adobe] '
author: Becky
feature: Workfront Fusion
exl-id: d1bc9e39-da49-4090-a106-14b52855bc8f
source-git-commit: 1929bf897e9263ec551e93df776b96f419436715
workflow-type: tm+mt
source-wordcount: '1582'
ht-degree: 38%

---

# Módulos de [!DNL Adobe Workfront Planning]

Con los módulos [!DNL Adobe Workfront Planning], puede almacenar en déclencheur un escenario cuando se produzcan eventos en Workfront Planning. También puede crear, leer, actualizar y eliminar registros, o realizar una llamada de API personalizada a su cuenta de [!DNL Adobe Workfront Planning].

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
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete Select o Prime Workfront que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++## Requisitos previos

Debe tener lo siguiente para acceder a Workfront Planning:

* Un nuevo paquete y licencia de Workfront. Workfront Planning no está disponible para paquetes o licencias de Workfront heredados.
* Un paquete de Workfront Planning.
* La instancia de Workfront de su organización debe incorporarse a la experiencia unificada de Adobe.

## Información de API de Adobe Workfront Planning

El conector de Adobe Workfront Planning utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Dirección URL base</td> 
   <td>https://{{connection.host}}/maestro/api/{{common.maestroApiVersion}}/</td> 
  </tr>
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.13.7</td> 
  </tr>
 </tbody> 
 </table>

## Crear una conexión a [!DNL Adobe Workfront Planning] {#create-a-connection-to-adobe-workfront-planning}

Puede crear una conexión con su cuenta de [!DNL Workfront Planning] directamente desde un módulo de Workfront Fusion.

1. En cualquier módulo de [!DNL Adobe Workfront Planning], haga clic en **[!UICONTROL Añadir]** junto al cuadro Conexión.

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
          <td>Introduzca su [!UICONTROL Client ID] [!DNL Adobe]. Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]<p>(Opcional)</p></td>
          <td>Introduzca su [!DNL Adobe] [!UICONTROL Client Secret].  Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Authentication URL]</td>
          <td>Introduzca la dirección URL que utilizará su instancia de Workfront para autenticar esta conexión. <p>El valor predeterminado es <code>https://oauth.my.workfront.com/integrations/oauth2</code>.</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Host prefix]</td>
          <td>Introduzca el prefijo de host.<p>El valor predeterminado es <code>origin-</code>.</p>
        </tr>
      </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.

## Módulos de [!DNL Adobe Workfront Planning] y sus campos

Al configurar los módulos de Workfront, Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden mostrarse campos de Workfront adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).


![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Activadores](#triggers)
* [Acciones](#actions)
* [Búsquedas](#searches)
* [Sin categoría](#uncategorized)

### Activadores

#### Ver eventos

Este módulo de déclencheur inicia un escenario cuando se crea, actualiza o elimina un registro, tipo de registro o espacio de trabajo en Workfront Planning.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Webhook]</td>
      <td>Seleccione el webhook que desee utilizar o haga clic en Agregar para crear uno nuevo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Object type]</td>
      <td>Seleccione si desea ver registros, tipos de registros o espacios de trabajo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL State]</td>
      <td>Seleccione si desea ver el estado antiguo o el nuevo.<ul><li><p><b>[!UICONTROL New state]</b></p><p>Active un escenario cuando el registro cambia <b>a </b> un valor determinado.</p></li><li><p><b>[!UICONTROL Old state]</b></p><p>Activa un escenario cuando el registro cambia <b>de </b> un valor determinado.</p></li></ul></td> 
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>Si observa registros, seleccione el Workspace que desee ver para ver los registros.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Record type]</td>
      <td>Si inspecciona registros, seleccione el tipo de registro que desee inspeccionar.</td>
    </tr>
    </tr>
     <tr data-mc-conditions=""> 
      <td> <p>[!UICONTROL Events filters]</p> </td> 
      <td> <p>Puede establecer filtros para ver solo los registros que cumplan los criterios seleccionados.</p> <p>Para cada filtro, introduzca el campo que desea que evalúe el filtro, el operador y el valor que desea que permita el filtro. Puede utilizar más de un filtro añadiendo reglas AND.</p> <p>Nota: Los filtros no se pueden editar en los webhooks de Workfront existentes. Para configurar diferentes filtros para las suscripciones a eventos de Workfront, elimine el webhook actual y cree uno nuevo.</p> <p>Para obtener más información sobre los filtros de eventos, consulte <a href="/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#event-subscription-filters-in-the-workfront--watch-events-modules" class="MCXref xref">Filtros de suscripción de eventos en Workfront &gt; Módulos de [!UICONTROL Watch Events]</a> en el artículo Módulos de Workfront.</p> </td> 
     </tr> 
    <tr>
      <td role="rowheader">[!UICONTROL Objetos que ver]</td>
      <td>Seleccione si desea ver las nuevas. registros actualizados, nuevos y actualizados o eliminados.</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Excluir actualizaciones realizadas por esta conexión]</p>
      </td>
      <td>Habilite esta opción para evitar que el escenario se active cuando la conexión utilizada por este módulo realice un cambio. Esto evita que se active otra instancia del escenario si este realiza una acción de activación.</td> 
      </tr>
  </tbody>
</table>

### Acciones

* [Eliminación de un tipo de registro](#delete-a-record-type)
* [Realizar una llamada de IA personalizada](#make-a-custom-api-call)

#### Eliminación de un tipo de registro

Este módulo de acción elimina un solo tipo de registro en Workfront Planning por su ID.

>[!WARNING]
>
>Al eliminar un tipo de registro en Workfront Planning también se eliminan todos los registros de la tabla de tipo de registro.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL ID de tipo de registro]</p>
      </td>
      <td>Introduzca o asigne el ID del tipo de registro que desea eliminar.</td> 
      </tr>
  </tbody>
</table>

#### Realizar una llamada de API personalizada

Este módulo realiza una llamada de API personalizada a la API de [!DNL Adobe Workfront Planning].

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre la creación de una conexión a [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión a [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL URL]</p>
      </td>
      <td>
        <p>Introduzca una ruta relativa a <code>https://(YOUR_WORKFRONT_DOMAIN)/maestro/api/</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
      </td>
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p>
        <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion añade encabezados de autorización automáticamente.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Query String]  </td>
      <td>
        <p>Para cada par clave/valor que desee agregar a la cadena de consulta, haga clic en <b>Agregar elemento</b> e introduzca la clave y el valor.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Body]</td>
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la instrucción condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>


### Búsquedas

#### Búsqueda de registros

Este módulo de acción recupera una lista de registros en función de los criterios especificados.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>Introduzca o asigne el Workspace que contiene los registros que desea buscar.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>Seleccione el tipo de registro que desea buscar.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record Fields]</p>
      </td>
      <td>Para cada campo que desee utilizar en la búsqueda, busque ese campo, seleccione el operador e introduzca o asigne el valor que desee buscar. Los campos están disponibles en función del tipo de registro seleccionado.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Condición para filtros]</p>
      </td>
      <td>Seleccione la condición de los filtros:<ul><li><b>Y</b><p>El módulo devuelve registros que cumplen <b>todos</b> los valores de campo que seleccionó.</p></li><li><b>O</b><p>El módulo devuelve registros que cumplen <b>cualquier</b> de los valores de campo que seleccionó.</p></li></ul></td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Limit]</p>
      </td>
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
      </tr>
  </tbody>
</table>


### Sin categoría


#### Crear un registro

Esta acción crea un único registro en Workfront Planning.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL ID de tipo de registro]</p>
      </td>
      <td>Introduzca o asigne el tipo de registro que desea crear. Los tipos de registro disponibles se basan en su cuenta de Workfront Planning.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>Otros campos</p>
      </td>
      <td>Introduzca los valores que desea que tenga el nuevo registro. Estos campos se basan en el tipo de registro seleccionado.</td> 
      </tr>
     <tr>
  </tbody>
</table>

### Eliminación de un registro

Este módulo de acción elimina el registro especificado en Workfront Planning.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record ID]</p>
      </td>
      <td>Introduzca o asigne el ID del registro que desea eliminar.</td> 
      </tr>
  </tbody>
</table>

### Obtener un registro

Este módulo de acción recupera un único registro de [!DNL Adobe Workfront Planning], especificado por su identificador.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Record ID]</td>
      <td>Introduzca o asigne el ID del registro que desea recuperar.</td>
    </tr>
  </tbody>
</table>

### Obtener registros por tipo de registro

Este módulo de acción recupera todos los registros del tipo especificado.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>Seleccione o asigne el espacio de trabajo que contiene los registros que desea recuperar.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Record type]</td>
      <td>Seleccione el tipo de registro que desea recuperar.</td>
    </tr>
     <!--<tr>
      <td role="rowheader">
        <p>[!UICONTROL Maximum number of returned records]</p>
      </td>
      <td>Enter or map the maximum number of records you want the module to return during each scenario execution cycle.</td> -->
  </tbody>
</table>

### Obtener tipos de registros

Este módulo de acción recupera una lista de tipos de registro en una cuenta de [!DNL Adobe Workfront Planning].

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>Seleccione o asigne el espacio de trabajo que contiene los tipos de registro que desea recuperar.</td>
    </tr>
  </tbody>
</table>

### Actualizar registro

Esta acción actualiza un único registro en Workfront Planning.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record ID]</p>
      </td>
      <td>Introduzca o asigne el tipo de registro que desea actualizar Los tipos de registro disponibles se basan en su cuenta de Workfront Planning.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>Otros campos</p>
      </td>
      <td>Introduzca los nuevos valores que desea que tenga el registro. Estos campos se basan en el tipo de registro seleccionado.</td> 
      </tr>
     <tr>
  </tbody>
</table>


## Usar JSONata para el desglose legible `record-types`

La siguiente expresión JSONata crea un resultado legible en lenguaje natural de la consulta de Planning que le proporciona el desglose de tipos de registros. Esto hace que el nombre del tipo de registro, los nombres de campo y los nombres de opciones de campo (cuando corresponda) sean legibles por un nombre y mantiene el resto de la estructura intacta.

```
(
    $s0 := ({"data":$ ~> | fields | {"options":(options){name:$}} |});
    $s1 := ({"data":$s0.data ~> | **.fields | {"options_name":(options.*){displayName:$}} | });
    $s2 := $s1 ~> | data | {"fields":(fields){displayName:$}} |; 
    $s2.data{displayName:$}
)
```

Para obtener información sobre el uso de módulos JSONata, consulte [módulos JSONata](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/jsonata-module.md).

