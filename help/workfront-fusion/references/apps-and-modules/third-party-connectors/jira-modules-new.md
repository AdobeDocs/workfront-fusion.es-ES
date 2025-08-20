---
title: Módulos Jira
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan el software Jira, así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: b74a3618-c4a1-4965-a88d-1643bfab12db
source-git-commit: 9865101fe57c2668ecb5ad743b3d6963833feb4a
workflow-type: tm+mt
source-wordcount: '1608'
ht-degree: 33%

---

# Módulos Jira

>[!NOTE]
>
>Estas instrucciones se aplican a la nueva versión del conector Jira, que simplemente se denomina Jira. Para obtener instrucciones sobre los conectores heredados de Jira Cloud y Jira Server, consulte [Módulos de software de Jira](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/jira-software-modules.md).

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan Jira, así como conectarlo a varias aplicaciones y servicios de terceros.

El conector Jira se puede utilizar tanto para Jira Cloud como para Jira Data Server.

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

Para utilizar módulos Jira, debe tener una cuenta Jira.

## Conexión de Jira a Workfront Fusion

### Crear las credenciales necesarias

Para crear conexiones a Jira, necesitará lo siguiente:

| Tipo de conexión | Tipo de cuenta | Credenciales necesarias |
|---|---|---|
| OAuth 2 | Cualquiera | ID de cliente y secreto de cliente |
| Básico | Jira Cloud | Token de API de Jira |
| Básico | Centro de datos de Jira | Token de acceso personal de Jira (PAT) |

Para obtener instrucciones sobre cómo crear cualquiera de estos, consulte la documentación de Jira.

Al crear estas credenciales, necesitará la siguiente información:

* Para OAuth 2:

  | Centro de datos Fusion | Dirección URL de redireccionamiento |
  |---|---|
  | US | `https://app.workfrontfusion.com/oauth/cb/workfront-jira2` |
  | UE | `https://app-eu.workfrontfusion.com/oauth/cb/workfront-jira2` |
  | Azure | `https://app-az.workfrontfusion.com/oauth/cb/workfront-jira2` |



* Para tokens de acceso personal (PAT):

  | Centro de datos Fusion | Dirección URL de redireccionamiento |
  |---|---|
  | US | `https://app.workfrontfusion.com/oauth/cb/workfront-jira` |
  | UE | `https://app-eu.workfrontfusion.com/oauth/cb/workfront-jira` |
  | Azure | `https://app-az.workfrontfusion.com/oauth/cb/workfront-jira` |

  >[!IMPORTANT]
  >
  >Para utilizar una ruta de acceso, debe habilitar lo siguiente en los archivos `jira/bin/WEB-INF/classes`, en el archivo `jira-config.properties`:
  >
  >* `jira.rest.auth.allow.basic = true`
  >* `jira.rest.csrf.disabled = true`
  >
  >Si este archivo no existe, debe crearlo.

### Creación de la conexión con Jira en Workfront Fusion

Para crear la conexión en Workfront Fusion:

1. En cualquier módulo Jira, haga clic en **Agregar** junto al campo Conexión.
1. Configure los campos siguientes:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>Tipo de conexión</p> </td> 
      <td> <p>Seleccione si va a crear una conexión básica o una conexión OAuth 2.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>Nombre de conexión</p> </td> 
      <td> <p>Introduzca un nombre para la nueva conexión.</p> </td> 
     </tr> 
     <tr>
      <td role="rowheader">URL de servicio</td>
      <td>Introduzca la URL de instancia de Jira. Esta es la URL que usa para acceder a Jira.</td>
     </tr>
     <tr>
      <td role="rowheader">Tipo de cuenta de Jira</td>
       <td>Seleccione si desea conectarse a Jira Cloud o al centro de datos de Jira.</td>
     </tr>
     <tr> 
      <td role="rowheader">Id. de cliente</td> 
      <td> <p>Si está creando una conexión OAuth 2, introduzca su ID de cliente de Jira</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">Secreto de cliente</td> 
      <td> <p>Si está creando una conexión OAuth 2, introduzca el Secreto del cliente Jira</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">Correo electrónico</td> 
      <td>Si está creando una conexión básica con Jira Cloud, escriba su dirección de correo electrónico.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">Token de API</td> 
      <td>Si está creando una conexión básica con Jira Cloud, introduzca su token de API.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">Token de acceso personal</td> 
      <td>Si está creando una conexión básica con el centro de datos de Jira, introduzca su token de acceso personal.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">Versión de API</td> 
      <td>Seleccione la versión de la API de Jira a la que desea conectarse esta conexión.</td> 
     </tr> 
    </tbody> 
   </table>

1. Haga clic en **[!UICONTROL Continuar]** para crear la conexión y volver al módulo.


## Módulos Jira y sus campos

Al configurar los módulos Jira, Workfront Fusion muestra los campos que se indican a continuación. Junto con estos, pueden mostrarse campos Jira adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Activadores](#triggers)
* [Acciones](#actions)
* [Búsquedas](#searches)

### Activadores

#### Buscar registros

Este módulo de activación inicia un escenario cuando se añade, actualiza o elimina un registro.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Webhook</td> 
   <td> <p>Seleccione el webhook que desee utilizar para buscar registros o cree uno nuevo. </p> <p>Para crear un nuevo webhook:</p> 
    <ol> 
     <li>Haga clic en <strong>Agregar</strong></li> 
     <li>Introduzca un nombre para el webhook. </li> 
     <li> Seleccione la conexión que desea utilizar para su webhook. <p>Para obtener instrucciones sobre cómo conectar tu cuenta de Jira a Workfront Fusion, consulta <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Jira a Workfront Fusion</a> en este artículo.</p> </li> 
     <li> <p>Seleccione el tipo de registro que desea que vea el software:</p> 
      <ul> 
       <li>Problema</li> 
       <li>Comentario </li> 
       <li>Registro de trabajo </li> 
       <li>Proyecto </li> 
       <li>Sprint</li> 
       <li>Archivos adjuntos </li> 
      </ul> </li> 
     <li>Seleccione uno o varios tipos de eventos que almacenarán este escenario en déclencheur.</li> 
     <li>Introduzca un filtro de idioma de consulta Jira para este módulo.<p>Para obtener más información sobre JQL, consulte <a href="https://www.atlassian.com/blog/jira-software/jql-the-most-flexible-way-to-search-jira-14#:~:text=JQLstandsforJiraQuery,projectmanagers%2Candbusinessusers.">JQL</a> en el sitio de ayuda de Atlassian. </p></li>
     <li>Haga clic en <b>Guardar</b> para guardar el webhook. 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### Acciones

* [Añadir problema al sprint](#add-issue-to-sprint)
* [Crear un registro](#create-a-record)
* [Llamada de API personalizada](#custom-api-call)
* [Eliminación de un registro](#delete-a-record)
* [Descargar un archivo adjunto](#download-an-attachment)
* [Leer un registro](#read-a-record)
* [Actualizar un registro](#update-a-record)

#### Añadir problema al sprint

Este módulo de acción añade uno o más problemas a un sprint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar tu cuenta de Jira a Workfront Fusion, consulta <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Jira a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de Sprint</td> 
   <td>Introduzca o asigne el ID de sprint del sprint al que desea añadir un problema.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de problema o claves</td> 
   <td>Para cada problema o clave que desee agregar al sprint, haga clic en <b>Agregar elemento</b> e introduzca el identificador o la clave del problema. Puede introducir hasta 50 en un módulo.</td> 
  </tr> 
 </tbody> 
</table>

#### Crear un registro

Este módulo de acción crea un nuevo registro en Jira.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar tu cuenta de Jira a Workfront Fusion, consulta <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Jira a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de registro</td> 
   <td> <p>Seleccione el tipo de registro que desea que cree el módulo.</p> 
    <ul> 
     <li>Archivos adjuntos</li> 
     <li>Comentario</li> 
     <li>Problema</li> 
     <li>Proyecto</li> 
     <li>Sprint </li> 
     <li>Registro de trabajo</li> 
     <li>Usuario</li> 
     <li>Tablero</li> 
     <li>Categoría</li> 
     <li>Filtro</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Otros campos</td> 
   <td> Rellene los demás campos. Los campos están disponibles en función del tipo de registro seleccionado. </td> 
  </tr> 
 </tbody> 
</table>

#### Llamada de API personalizada

Este módulo de acción le permite realizar una llamada autenticada personalizada a la API de Jira.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar tu cuenta de Jira a Workfront Fusion, consulta <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Jira a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>Introduzca una ruta relativa a<code>&lt;Instance URL>/rest/api/2/ </code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">Método</td> 
   td&gt; <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Encabezados</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p> Workfront Fusion añade los encabezados de autorización para usted.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Cadena de consulta</td> 
   <td> <p>Añada la consulta para la llamada de API en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Cuerpo</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png">  </td> 
  </tr> 
 </tbody> 
</table>

#### Eliminación de un registro

Este módulo de acción elimina el registro especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar tu cuenta de Jira a Workfront Fusion, consulta <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Jira a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de registro</td> 
   <td> <p>Seleccione el tipo de registro que desea que elimine el módulo. </p> 
    <ul> 
     <li>Comentario</li> 
     <li>Problema</li> 
     <li>Proyecto</li> 
     <li>Sprint </li> 
     <li>Registro de trabajo</li> 
     <li>Archivos adjuntos</li> 
     <li>Tablero</li> 
     <li>Categoría</li> 
     <li>Filtro</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">(Tipo de registro)ID</td> 
   <td>Introduzca o asigne el ID o la clave del registro que desea eliminar.</td> 
  </tr> 
 </tbody> 
</table>

#### Descargar un archivo adjunto

Este módulo de acción descarga el archivo adjunto especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar tu cuenta de Jira a Workfront Fusion, consulta <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Jira a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Identificador</td> 
   <td>Introduzca o asigne el ID del archivo adjunto que desea descargar.</td> 
  </tr> 
 </tbody> 
</table>

#### Leer un registro

Este módulo de acción lee datos del registro especificado en Jira.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar tu cuenta de Jira a Workfront Fusion, consulta <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Jira a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de registro</td> 
   <td> <p>Seleccione el tipo de registro Jira que desea que lea el módulo.</p> 
    <ul> 
     <li>Archivos adjuntos</li> 
     <li>Comentario</li> 
     <li>Problema</li> 
     <li>Proyecto</li> 
     <li>Sprint </li> 
     <li>Registro de trabajo</li> 
     <li>Usuario</li> 
     <li>Tablero</li> 
     <li>Categoría</li> 
     <li>Filtro</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Salidas</td> 
   <td>Seleccione las salidas que desea recibir. Las opciones de salida están disponibles en función del tipo de registro seleccionado en el campo "Tipo de registro".</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID (Tipo de registro)</td> 
   <td> <p>Introduzca o asigne el ID de Jira único del registro que desea que lea el módulo.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Actualizar un registro

Este módulo de acción actualiza un registro existente, como un problema o un proyecto.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar tu cuenta de Jira a Workfront Fusion, consulta <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Jira a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de registro</td> 
   <td> <p>Seleccione el tipo de registro que desea que actualice el módulo. Al seleccionar un tipo de registro, en el módulo aparecerán otros campos específicos de dicho tipo de registro.</p> 
    <ul> 
     <li>Comentario</li> 
     <li>Problema</li> 
     <li>Proyecto</li> 
     <li>Sprint </li> 
     <li>Problema de transición</li> 
     <li>Categoría </li> 
     <li>Filtro </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID o clave</td> 
   <td>Introduzca o asigne el ID o la clave del registro que desea actualizar.</td> 
  <tr> 
   <td role="rowheader">Otros campos</td> 
   <td> Rellene los demás campos. Los campos están disponibles en función del tipo de registro seleccionado. </td> 
  </tr> 
 </tbody> 
</table>

### Búsquedas

#### Búsqueda de registros

Este módulo de búsqueda busca registros en un objeto de Jira que coincidan con la consulta de búsqueda especificada.

Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar tu cuenta de Jira a Workfront Fusion, consulta <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Conectar Jira a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de registro</td> 
   <td> <p>Seleccione el tipo de registro que desea que busque el módulo. Al seleccionar un tipo de registro, en el módulo aparecerán otros campos específicos de dicho tipo de registro.</p> 
    <ul> 
     <li>Problema</li> 
     <li>Proyecto</li> 
     <li>Usuario</li> 
     <li>Sprint</li> 
     <li>Tablero</li> 
     <li>Registro de trabajo</li> 
     <li>Comentario</li> 
     <li>Problema de transición</li> 
     <li>Categoría</li> 
    </ul> </td> 
  <tr> 
   <td role="rowheader"> <p>Resultados máximos</p> </td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo recupere durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
   <tr> 
    <td role="rowheader">Desplazamiento</td> 
    <td> Introduzca o asigne el ID del primer elemento para el que desea recuperar detalles. Esta es una forma de paginar los registros. Si introduce el elemento 5000 como desplazamiento, el módulo devolverá los elementos 5000-9999.</td> 
   </tr>
  <tr> 
   <td role="rowheader">Otros campos</td> 
   <td> Rellene los demás campos. Los campos están disponibles en función del tipo de registro seleccionado. </td> 
  </tr> 
 </tbody> 
</table>
