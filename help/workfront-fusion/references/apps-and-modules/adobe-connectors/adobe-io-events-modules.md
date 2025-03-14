---
title: Módulos de Adobe I/O Events
description: Con los módulos de Adobe I/O Events, puede iniciar un escenario de Adobe Workfront Fusion basado en los eventos de sus aplicaciones de Adobe.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: b2229f3e-a2a7-4b07-8ead-a37d193c2ec7
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 36%

---

# Módulos de Adobe I/O Events

Con los módulos de Adobe I/O Events, puede iniciar un escenario de Adobe Workfront Fusion basado en eventos en cuentas y servicios de Adobe que no tengan un conector de Workfront Fusion dedicado.

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

Antes de poder utilizar el conector de Adobe I/O Events, debe asegurarse de que se cumplen los siguientes requisitos previos:

* Debe tener una cuenta de Adobe activa.

## Información de API de Adobe I/O Events

El conector de Adobe I/O Events utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL básica</td> 
   <td>https://api.adobe.io/events</td> 
  </tr>
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.6.7</td> 
  </tr>
 </tbody> 
 </table>

## Creación de una conexión con Adobe I/O Events

Para crear una conexión para los módulos de Adobe I/O Events:

1. Haga clic en Agregar junto al cuadro Conexión.

1. Rellene los campos siguientes:

   <table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">Nombre de conexión</td>
        <td>
          <p>Introduzca un nombre para esta conexión.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">Tipo</td>
        <td>
          <p>Seleccione si desea conectarse a una cuenta de servicio o a una cuenta personal.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">Ámbitos adicionales</td>
        <td>Para agregar ámbitos adicionales, haga clic en <b>Agregar elemento</b> e introduzca el ámbito.</td>
      </tr>
      <tr>
        <td role="rowheader">Id. de cliente</td>
        <td>Introduzca su ID de cliente de Adobe. Esto se puede encontrar en la sección de detalles de credenciales de Adobe Developer Console</td>
      </tr>
      <tr>
        <td role="rowheader">Secreto de cliente</td>
        <td>Escriba el Secreto de cliente de Adobe. Esto se puede encontrar en la sección de detalles de credenciales de Adobe Developer Console</td>
      </tr>
      </tr>
        <tr>
        <td role="rowheader">ID de organización de consumidores</td>
        <td>Introduzca su ID de organización de consumidores. Esto se puede encontrar en la dirección URL de credencial del proyecto: <code>https://developer.adobe.com/console/projects/{consumer org ID}/ {project ID}/credentials/{credential ID}/details</code></td>
      </tr>
      <tr>
        <td role="rowheader">ID de credencial</td>
        <td>Introduzca su ID de credencial. Esto se puede encontrar en la dirección URL de credencial del proyecto: <code>https://developer.adobe.com/console/projects/{consumer org ID}/ {project ID}/credentials/{credential ID}/details</code></td>
      </tr>
      <tr>
        <td role="rowheader">ID de organización IMS</td>
        <td>Introduzca su ID de organización de Adobe. Esto se puede encontrar en la sección de detalles de credenciales de Adobe Developer Console</td>
      </tr>
        <tr>
        <td role="rowheader">Identificador de proyecto</td>
        <td>Introduzca su ID de proyecto. Esto se puede encontrar en la dirección URL de credencial del proyecto: <code>https://developer.adobe.com/console/projects/{consumer org ID}/ {project ID}/credentials/{credential ID}/details</code></td>
      </tr>
      <tr>
        <td role="rowheader">WORKSPACE ID</td>
        <td>Para ver el Workspace ID del proyecto, descargue los detalles del proyecto desde la página de información general del proyecto en Adobe Developer Console. </td>
      </tr>
    </tbody>
    </table>

1. Haga clic en **Continuar** para guardar la conexión y volver al módulo.

## Módulos Adobe I/O Events y sus campos

Al configurar módulos de [!DNL Adobe I/O Events], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Adobe I/O Events] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Activadores](#triggers)
* [Acciones](#actions)
* [Búsquedas](#searches)

### Activadores

#### Crear un registro de eventos

Este módulo de acción utiliza un webhook para crear una descripción de evento. Puede configurar un webhook aquí. Si utiliza un webhook existente, los campos de este módulo son de solo lectura.

Para crear un webhook:

1. Haga clic en **Agregar** junto al campo Webhook.
1. Rellene los campos siguientes:

   <table>
     <col/>
     <col/>
     <tbody>
       <tr>
         <td role="rowheader">[!UICONTROL Webhook name]</td>
        <td>Escriba un nombre para este webhook.</td>
       </tr>
       <tr>
         <td role="rowheader">[!UICONTROL Connection]</td>
        <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe I/O Events], consulte <a href="#create-a-connection-to-adobe-io-events" class="MCXref xref" >Crear una conexión con [!DNL Adobe I/O Events]</a> en este artículo.</td>
       </tr>
       <tr>
         <td role="rowheader">
           Descripción del webhook de [!UICONTROL]
         </td>
         <td>
           Escriba una descripción para este webhook.
        </td>
       </tr>
       <tr>
         <td role="rowheader">
           [!UICONTROL Proveedor de eventos]
         </td>
         <td>
           Seleccione el producto o la cuenta desde los que desea crear eventos.
         </td>
       </tr>
       <tr>
         <td role="rowheader">
           [!UICONTROL Event type]
         </td>
         <td>
           Seleccione los eventos que desea que vea el webhook. El escenario entrará en déclencheur cuando se produzcan estos eventos.
         </td>
       </tr>
     </tbody>
   </table>

1. Haga clic en Guardar para guardar el webhook y volver al módulo.

### Acciones

#### Obtener todos los eventos de un diario

Este módulo de búsqueda recupera todos los eventos para un registro desde un historial.

<table>
     <col/>
     <col/>
     <tbody>
       <tr>
         <td role="rowheader">[!UICONTROL Connection]</td>
        <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe I/O Events], consulte <a href="#create-a-connection-to-adobe-io-events" class="MCXref xref" >Crear una conexión con [!DNL Adobe I/O Events]</a> en este artículo.</td>
       </tr>
       <tr>
         <td role="rowheader">
           [!UICONTROL ID de registro]
         </td>
         <td>
           Seleccione el registro para el que desea recuperar eventos.
        </td>
       </tr>
       <tr>
         <td role="rowheader">
           [!UICONTROL Maximum number of returned records]
         </td>
         <td>
              Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario. 
         </td>
       </tr>
       <tr>
         <td role="rowheader">
           [!UICONTROL Devolver eventos que se producen después de]
         </td>
         <td>
         </td>
       </tr>
       <tr>
         <td role="rowheader">
           [!UICONTROL Seek]
         </td>
         <td>
         </td>
       </tr>
       <tr>
         <td role="rowheader">
           [!UICONTROL Última versión]
         </td>
         <td>
         Active esta opción para devolver el evento más reciente.
         </td>
       </tr>
     </tbody>
   </table>

#### Realizar una llamada de API personalizada

Este módulo de acción realiza una llamada de API personalizada a la API [!DNL Adobe I/O Events]

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
     <td role="rowheader">[!UICONTROL Connection]</td>
        <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe I/O Events], consulte <a href="#create-a-connection-to-adobe-io-events" class="MCXref xref" >Crear una conexión con [!DNL Adobe I/O Events]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Path]</p>
      </td>
      <td>
        <p>Introduzca una ruta relativa a <code>https://api.adobe.io/events</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
      </td>
      <td>
  <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p>  
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p>
        <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion añade automáticamente encabezados de autorización y encabezados x-api-key.</p>
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
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la instrucción condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>

### Búsquedas

#### Obtención de ID de proveedor y evento

Este módulo de búsqueda obtiene los Adobe I/O Events ID del proveedor y los eventos especificados.

<table>
     <col/>
     <col/>
     <tbody>
       <tr>
         <td role="rowheader">[!UICONTROL Connection]</td>
        <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe I/O Events], consulte <a href="#create-a-connection-to-adobe-io-events" class="MCXref xref" >Crear una conexión con [!DNL Adobe I/O Events]</a> en este artículo.</td>
       </tr>
       <tr>
         <td role="rowheader">
           [!UICONTROL Proveedor de eventos]
         </td>
         <td>
           Seleccione el proveedor para el que desea recuperar el ID.
        </td>
       </tr>
       <tr>
         <td role="rowheader">
           [!UICONTROL Event type]
         </td>
         <td>
              Seleccione los eventos para los que desea proporcionar ID. Los eventos están disponibles en función del proveedor de eventos. 
         </td>
       </tr>
     </tbody>
   </table>

<!--

Watch Events

This trigger module starts a scenario when an event occurs in the chosen Adobe product or service.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">Webhook</td> 
   <td><p>Select the webhook that you want to use for this trigger, or add a new webhook. </p><p>To add a new webhook, <ol><li>Click <b>Add</b> next to the webhook field.</li><li>Enter the following: <ul><li>A name for the webhook</li><li>The connection that you want to use for this webhook</li><li>The source of the events you want to watch</li></ul></li><li>Click <b>Save</b> to save the webhook and return to the module. </td> 
   </tr> 
   </tbody> 
</table>

-->
