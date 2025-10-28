---
title: Módulos Veeva Vault
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan Veeva Vault, así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
source-git-commit: 4f5a4cf8691e5bb47eec6f6b2842369c5c6fbad8
workflow-type: tm+mt
source-wordcount: '1516'
ht-degree: 16%

---

# Módulos Veeva Vault

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan Veeva Vault, así como conectarlo a varias aplicaciones y servicios de terceros.

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

Para utilizar los módulos Veeva Vault, debe tener una cuenta Veeva Vault.

## Módulos Veeva Vault y sus campos

Al configurar los módulos de Veeva Vault, Workfront Fusion muestra los campos que se indican a continuación. Junto con estos, pueden mostrarse campos adicionales de Veeva Vault, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Documento

* [Crear un solo documento](#create-a-single-document)
* [Crear varios documentos](#create-multiple-documents)
* [Eliminar un solo documento](#delete-a-single-document)
* [Exportar documentos](#export-documents)
* [Obtener un solo documento](#get-a-single-document)
* [Iniciar acción de usuario](#initiate-user-action)
* [Enumerar documentos](#list-documents)
* [Recuperar resultados de exportación del documento](#retrieve-document-export-results)
* [Actualizar varios documentos](#update-multiple-documents)
* [Actualizar un solo documento](#update-a-single-document)

#### Crear un solo documento

Este módulo crea un solo documento, enlace o plantilla.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Veeva Vault a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Tipo</p> </td> 
   <td> <p>Seleccione si desea crear un documento, un enlace o una plantilla.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">  <p>Seleccionar campos</p> </td> 
   <td> <p>Seleccione los campos para los que desea introducir datos y, a continuación, introduzca los datos en esos campos.</td> 
  </tr> 
 </tbody> 
</table>

#### Crear varios documentos

Este módulo crea varios documentos o plantillas utilizando un archivo CSV.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Veeva Vault a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Tipo</p> </td> 
   <td> <p>Seleccione si desea crear plantillas o documentos</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">  <p>Datos de archivo</p> </td> 
   <td> <p>Asigne el archivo CSV que se utilizará para crear los documentos.</td> 
  </tr> 
 </tbody> 
</table>

#### Eliminar un solo documento

Este módulo elimina un solo documento, enlace o plantilla.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Veeva Vault a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Tipo</p> </td> 
   <td> <p>Seleccione si desea eliminar un documento, un enlace o una plantilla.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>ID de documento/ID de cuaderno/nombre de plantilla</p> </td> 
   <td> <p>Seleccione los campos que desea eliminar.</td> 
  </tr> 
 </tbody> 
</table>

#### Exportar documentos

Este módulo exporta los documentos especificados, incluidos los orígenes, las representaciones y el texto.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Veeva Vault a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Tipo</p> </td> 
   <td> <p>Seleccione si desea eliminar un documento, un enlace o una plantilla.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Fuente</p> </td> 
   <td> <p>Active esta opción para incluir archivos de origen en la exportación.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Representaciones</p> </td> 
   <td> <p>Active esta opción para incluir archivos de representaciones en la exportación.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Todas las versiones</p> </td> 
   <td> <p>Active esta opción para incluir todas las versiones de los archivos de documento en la exportación.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Texto</p> </td> 
   <td> <p>Active esta opción para incluir el texto del documento de origen en la exportación.</p></td> 
  </tr> 
 </tbody> 
</table>

#### Obtener un solo documento

Este módulo recupera los metadatos de un solo documento, enlace o plantilla.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Veeva Vault a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Tipo</p> </td> 
   <td> <p>Seleccione si desea recuperar los datos de un documento, un enlace o una plantilla.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>ID de documento/ID de cuaderno/nombre de plantilla</p> </td> 
   <td> <p>Seleccione los campos para los que desea recuperar datos.</td> 
  </tr> 
 </tbody> 
</table>

#### Iniciar acción de usuario

Este módulo inicia acciones en documentos y carpetas, como enviar un documento para su revisión o cambiar su estado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Veeva Vault a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Tipo</p> </td> 
   <td> <p>Seleccione si desea realizar una acción en un documento o en un enlace.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Documento / Cuaderno</p> </td> 
   <td> <p>Seleccione el documento o el enlace en el que desea realizar la acción.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Versión del documento/ Versión del cuaderno</p> </td> 
   <td> <p>Seleccione el documento o el enlace en el que desea realizar la acción.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Acción</p> </td> 
   <td> <p>Seleccione la acción que se va a realizar en el documento o en el enlace.</td> 
  </tr> 
 </tbody> 
</table>

#### Enumerar documentos

Este módulo enumera todos los documentos del tipo seleccionado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Veeva Vault a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Tipo</p> </td> 
   <td> <p>Seleccione si desea enumerar documentos, carpetas o plantillas.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Número máximo de resultados devueltos</td> 
   <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td> 
  </tr> 
 </tbody> 
</table>

#### Recuperar resultados de exportación del documento

Este módulo devuelve los resultados de una exportación de documento solicitada anteriormente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Veeva Vault a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ID de trabajo</p> </td> 
   <td> <p>Introduzca o asigne el ID del trabajo para el que desea obtener resultados. </p> </td> 
  </tr> 
  </tbody> 
</table>

#### Actualizar varios documentos

Este módulo actualiza varios documentos o plantillas mediante un archivo CSV.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Veeva Vault a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Tipo</p> </td> 
   <td> <p>Seleccione si desea crear plantillas o documentos</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">  <p>Datos de archivo</p> </td> 
   <td> <p>Asigne el archivo CSV que se utilizará para crear los documentos.</td> 
  </tr> 
 </tbody> 
</table>

#### Actualizar un solo documento

Este módulo actualiza un solo documento, enlace o plantilla.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Veeva Vault a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Tipo</p> </td> 
   <td> <p>Seleccione si desea crear un documento, versión de documento, enlace o plantilla.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ID/nombre</p> </td> 
   <td> <p>Si va a actualizar una plantilla, escriba un nombre nuevo para ella.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Nuevo nombre de plantilla</p> </td> 
   <td> <p>Introduzca o asigne el ID o el nombre del objeto que desea actualizar.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">  <p>Seleccionar campos</p> </td> 
   <td> <p>Seleccione los campos para los que desea introducir datos y, a continuación, introduzca los datos en esos campos.</td> 
  </tr> 
 </tbody> 
</table>

### Objeto



#### Enumerar objetos

Este módulo recupera todos los objetos Vault en el Vault autenticado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Veeva Vault a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Recuperación de etiquetas localizadas</p> </td> 
   <td> <p>Seleccione Yes para recuperar cadenas localizadas (traducidas) para los campos de objeto label y label_plural.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Número máximo de resultados devueltos</td> 
   <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td> 
  </tr> 
 </tbody> 
</table>

### Otro

* [Realizar una llamada de API personalizada](#make-a-custom-api-call)
* [Realización de una consulta VQL](#make-a-vql-query)
* [Leer registros](#read-logs)

#### Realizar una llamada de API personalizada

Este módulo de acción realiza una llamada personalizada a la API de Veeva Vault.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Veeva Vault a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>Escriba una ruta relativa a <code>baseurl/api/v</code>.  Por ejemplo: <code>/objects/documents</code>. No incluya <code>baseurl/api/v/</code>, ya que ya está incluido.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Método</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Encabezados</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion añade los encabezados de autorización para usted.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Cadena de consulta</td> 
   <td> <p>Añada la consulta para la llamada de API en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Cuerpo</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### Realización de una consulta VQL

Este módulo realiza una consulta utilizando el lenguaje de consulta Vault (VQL).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Veeva Vault a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Tipo</p> </td> 
   <td> <p>Seleccione si desea crear plantillas o documentos</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">  <p>Datos de archivo</p> </td> 
   <td> <p>Asigne el archivo CSV que se utilizará para crear los documentos.</td> 
  </tr> 
 </tbody> 
</table>

#### Leer registros

Este módulo devuelve datos de las pistas de auditoría

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Veeva Vault a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Tipo de auditoría</p> </td> 
   <td> <p>Seleccione el tipo de auditoría para el que desea recuperar datos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Fecha de inicio</p> </td> 
   <td> <p>Introduzca o asigne la fecha de inicio de las auditorías que desee recuperar.</p><p>Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Fecha de finalización</p> </td> 
   <td> <p>Introduzca o asigne la fecha de finalización de las auditorías que desee recuperar.</p><p>Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>URL de resultado </p> </td> 
   <td> <p>Seleccione CSV si desea obtener la URL para descargar un CSV con el resultado.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Número máximo de resultados devueltos</td> 
   <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td> 
  </tr> 
 </tbody> 
</table>


