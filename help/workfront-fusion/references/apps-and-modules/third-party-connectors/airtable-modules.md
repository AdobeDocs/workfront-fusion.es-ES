---
title: Módulos de Airtable
description: Adobe Workfront Fusion requiere una licencia Adobe Workfront Fusion y de Adobe Workfront.
author: Becky
feature: Workfront Fusion
exl-id: 3b445b50-5812-4ded-9788-f467991e0b52
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1890'
ht-degree: 93%

---

# Módulos de Airtable


Con el conector [!DNL Airtable] para Adobe Workfront Fusion, puede iniciar un escenario basado en eventos en su cuenta de [!DNL Airtable], crear, cargar y actualizar registros, buscar registros y realizar llamadas de API personalizadas a la API de Airtable.

## Requisitos de acceso

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Plan de Adobe Workfront*</td>
  <td> <p>[!UICONTROL Pro] o superior</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencia de Adobe Workfront*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion**</td> 
   <td> <p>[!UICONTROL Workfront Fusion for Work Automation and Integration] </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>Su organización debe comprar Adobe Workfront Fusion y Adobe Workfront para utilizar la funcionalidad que se describe en este artículo.</td> 
  </tr> 
 </tbody> 
</table>

Para saber qué plan, tipo de licencia o acceso tiene, póngase en contacto con el administrador de Workfront.

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## Requisitos previos

Debe tener una cuenta de Airtable para utilizar la funcionalidad de este artículo.

<!--
<p>For more information, see the tutorial .</p>
-->

## Información de API de Airtable

El conector Airtable utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Dirección URL base</td> 
   <td>https://api.airtable.com/v0</td> 
  </tr>
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 3.3.28</td> 
  </tr>
 </tbody> 
 </table>

## Conectar Airtable a Workfront Fusion {#connect-airtable-to-workfront-fusion}

<!--

1. Log in to your Airtable account.
1. Open your account overview and generate the API key.
-->
1. Abra Workfront Fusion y el cuadro de diálogo **Crear una conexión** del módulo deseado.
1. Introduzca un nombre para la conexión. 
1. (Opcional) Haga clic en Mostrar configuración avanzada e introduzca su ID de cliente de Airtable y Secreto de cliente.
1. Haga clic en el botón **Continuar** para crear la conexión y volver al módulo.

## Módulos de Airtable y sus campos

### Registros

* [Crear un registro](#create-a-record)
* [Eliminar un registro](#delete-a-record)
* [Obtener un registro](#get-a-record)
* [Buscar registros](#search-records)
* [Actualizar un registro](#update-a-record)
* [Actualizar un registro](#upsert-a-record)
* [Ver registros](#watch-records)
* [Ver respuestas](#watch-responses)
* [Realizar una llamada de API](#make-an-api-call)

#### Crear un registro {#create-a-record}

Este módulo de acción crea un nuevo registro.

Especifique los datos que desea en el registro y dónde desea que se almacenen.

El módulo devuelve cualquier campo estándar asociado con el registro, junto con los campos y valores personalizados a los que accede la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Airtable a Workfront Fusion, consulte <a href="#connect-airtable-to-workfront-fusion" class="MCXref xref">Conectar Airtable a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>Base </td> 
   <td> <p>Seleccione la base a la que pertenecerá el nuevo registro.</p> </td> 
  </tr> 
  <tr> 
   <td>Tabla </td> 
   <td> <p>Seleccione la tabla a la que pertenecerá el nuevo registro.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Registro</p> </td> 
   <td> <p>Introduzca los valores del nuevo registro. Los campos disponibles se basan en la tabla seleccionada.</p> <!--<p>For more information on field types, search for "Supported field types" in the Airtable documentation.</p> 
    <ul> 
     <li> <p><strong>Text</strong>: string</p> <p>A single line of text.</p> </li> 
     <li> <p><strong>Long text</strong>: string</p> <p>Multiple lines of text, which may contain "mention tokens", for example:</p><pre>&lt;airtable:mention id="menE1i9oBaGX3DseR"&gt;@Alex&lt;/airtable:mention&gt;</pre> </li> 
     <li><strong>Attachment</strong> : Add the attachment. Airtable will download the file from the provided <code>url</code> and keep its own copy of it. If the File name field is left empty, Airtable generates the name automatically.</li> 
     <li><strong>Checkbox</strong>: Select one of the options.</li> 
     <li><strong>Multiple select</strong>: Select multiple options in the checklist.</li> 
     <li><strong>Single select</strong>: Select one option from the drop-down menu.</li> 
     <li><strong>Collaborator</strong>: Enter the email that uniquely identifies a user in Airtable who this base is shared with.</li> 
     <li><strong>Date</strong>: UTC date, for example, 2019-09-05 (ISO 8601 formatted date)</li> 
     <li>Phone number:</li> 
     <li><strong>Emails</strong>: A valid email address.</li> 
     <li><strong>URL</strong>: A valid URL (for example, airtable.com or https://airtable.com/universe).</li> 
     <li><strong>Number</strong>: Enter a number.</li> 
     <li><strong>Currency</strong>: Currency value.</li> 
     <li><strong>Percent</strong>: A percentage value. Must be higher than or equal to 0.</li> 
     <li><strong>Duration</strong>: Enter the duration time. If you need help, see the information about the duration field type in the Airtable support documentation. </li> 
     <li><strong>Rating</strong>: Enter the number. For example, "3 stars" is 3. A rating cannot be 0.</li> 
     <li><strong>Link</strong>: Enter the linked records IDs from the table. The order of record IDs will be reversed compared to what you see in the app.</li> 
     <li><strong>Rollup</strong>: Computed value: COUNT(values)</li> 
     <li><strong>Lookup</strong>: Array of long text fields</li> 
     <li><strong>Autonumber</strong>: Automatically incremented unique counter for each record.</li> 
     <li> <p><strong>Barcode</strong>: The barcode object may contain the following two properties, both of which are optional.</p> <p>Barcode data (text)</p> <p>Barcode symbology, for example, "upce" or "code39" (type)</p> </li> 
    </ul> --></td> 
  </tr> 
  <tr> 
   <td>Vínculos inteligentes</td> 
   <td> <p>Active esta opción para introducir nombres en lugar de ID de registro en campos que se vinculan a otra tabla. El registro se crea automáticamente en la tabla vinculada si no hay ninguna coincidencia.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Eliminación de un registro {#delete-a-record}

Este módulo de acción elimina un registro en particular.

Especifique el ID y las ubicaciones del registro.

El módulo devuelve el identificador del registro y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Airtable a Workfront Fusion, consulte <a href="#connect-airtable-to-workfront-fusion" class="MCXref xref">Conectar Airtable a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>Base </td> 
   <td> <p>Seleccione la base que contiene el registro que desea eliminar.</p> </td> 
  </tr> 
  <tr> 
   <td>Tabla </td> 
   <td> <p>Seleccione la tabla que contiene el registro que desea eliminar.</p> </td> 
  </tr> 
  <tr> 
   <td>ID de registro</td> 
   <td> <p>Introduzca o asigne el ID único de Airtable del registro que desea que el módulo elimine. Puede recuperar el ID, por ejemplo, mediante el módulo Buscar registros.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Obtener un registro {#get-a-record}

Este módulo de acción recupera detalles de registro.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Airtable a Workfront Fusion, consulte <a href="#connect-airtable-to-workfront-fusion" class="MCXref xref">Conectar Airtable a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>Base </td> 
   <td> <p>Seleccione la base que contiene la tabla con el registro que desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td>Tabla</td> 
   <td> <p> Seleccione la tabla que contiene el registro cuyos detalles desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td>ID de registro</td> 
   <td> <p> Introduzca o asigne el ID del registro cuyos detalles desea recuperar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Búsqueda de registros {#search-records}

Este módulo de búsqueda busca registros en un objeto de Airtable que coincidan con la consulta de búsqueda especificada.

Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Airtable a Workfront Fusion, consulte <a href="#connect-airtable-to-workfront-fusion" class="MCXref xref">Conectar Airtable a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>Base </td> 
   <td> <p>Seleccione la base en la que desea buscar registros.</p> </td> 
  </tr> 
  <tr> 
   <td>Tabla </td> 
   <td> <p>Seleccione la tabla en la que desea buscar registros.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Fórmula</p> </td> 
   <td> <p>Fórmula utilizada para filtrar registros. La fórmula se evalúa para cada registro y, si el resultado no es <code>0</code>, <code>false</code>, <code>""</code>, <code>NaN</code>, <code>[]</code> o <code>#Error!</code>, el registro se incluye en la respuesta.</p> <p>Si se combina con <code>view</code>, solo se devuelven los registros de esa vista que cumplen la fórmula.</p> <p>Por ejemplo, para incluir solo registros en los que Nombre no esté vacío, introduzca:<code> NOT({Name} = '')</code></p> <p>Para obtener más información, busque información sobre las referencias de los campos de fórmula en la documentación de soporte de Airtable.</p> </td> 
  </tr> 
  <tr> 
   <td>Ordenar </td> 
   <td> <p>Seleccione la dirección de clasificación y el campo por el que desea ordenar los resultados.</p> </td> 
  </tr> 
  <tr> 
   <td>Ver </td> 
   <td> <p>Seleccione la vista en la que desee buscar registros.</p> </td> 
  </tr> 
  <tr> 
   <td>Límite</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Actualizar un registro {#update-a-record}

Este módulo de acción actualiza un registro determinado.

Especifique el ID del registro y los nuevos datos que desea que contenga.

El módulo devuelve cualquier campo estándar asociado con el registro, junto con los campos y valores personalizados a los que accede la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Airtable a Workfront Fusion, consulte <a href="#connect-airtable-to-workfront-fusion" class="MCXref xref">Conectar Airtable a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>Base </td> 
   <td> <p>Seleccione la base que contiene el registro que desea actualizar.</p> </td> 
  </tr> 
  <tr> 
   <td>Tabla </td> 
   <td> <p>Seleccione la tabla que contiene el registro que desea actualizar.</p> </td> 
  </tr> 
  <tr> 
   <td>ID de registro </td> 
   <td> <p>Introduzca o asigne el ID único de Airtable del registro que desea que el módulo actualice. Puede recuperar el ID, por ejemplo, mediante el módulo Buscar registros.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Registro</p> </td> 
   <td> <p>Introduzca los valores del nuevo registro. Los campos disponibles dependen de la tabla seleccionada.</p> <!--<p>In order to delete the content of the field, use the erase function. </p>  <p>Field types (via airtable.com/api):</p> 
    <ul> 
     <li> <p><strong>Text</strong>: string</p> <p>A single line of text.</p> </li> 
     <li> <p><strong>Long text</strong>: string</p> <p>The string can contain multiple lines of text with "mention tokens." For example:</p><pre>&lt;airtable:mention id="menE1i9oBaGX3DseR"&gt;@Alex&lt;/airtable:mention&gt;</pre> </li> 
     <li><strong>Attachment</strong>: Add the attachment. Airtable will download the file from the provided url and keep its own copy of it. If the File name field is left empty, Airtable will generate the name automatically.</li> 
     <li><strong>Checkbox</strong>: Select one of the options.</li> 
     <li><strong>Multiple select</strong>: Select multiple options in the checklist.</li> 
     <li><strong>Single select</strong>: Select one option from the drop-down menu.</li> 
     <li><strong>Collaborator</strong>: Enter the email that uniquely identifies a user in Airtable who this base is shared with.</li> 
     <li><strong>Date</strong>: UTC date, for example, 2019-09-05. (ISO 8601 formatted date)</li> 
     <li><strong>Phone number</strong>: A telephone number, for example, (415) 555-9876.</li> 
     <li><strong>Email</strong>valid email address.</li> 
     <li><strong>URL</strong>: lid URL such as airtable.com or https://airtable.coiverse.</li> 
     <li><strong>Number</strongnter a number.</li> 
     <li><strong>Currency</stro Currency value.</li> 
     <li><strong>Percent</stronA percentage value; must be equal to or more than 0i> 
     <li><strong>Duration</strong>: Enter the duration time. If you need help, see the information about the duration field type in the Airtable support documentation.</li> 
     <li><strong>Rating</strong>: Enter the number. For example, "3 stars" is 3. A rating cannot be 0.</li> 
     <li><strong>Link</strong>: Enter the linked records IDs from the table. The order of record IDs is reversed compared to what you see in the app.</li> 
     <li><strong>Rollup</strong>: Computed value: COUNT(values)</li> 
     <li><strong>Lookup</strong>: Array of long text fields</li> 
     <li><strong>Autonumber</strong>: Automatically incremented unique counter for each record.</li> 
     <li> <p><strong>Barcode</strong>: The barcode object may contain the following two properties, both of which are optional.</p> <p>Barcode data (text)</p> <p>Barcode symbology, for example, "upce" or "code39" (type)</p> </li> 
    </ul> --></td> 
  </tr> 
  <tr> 
   <td>Vínculos inteligentes</td> 
   <td> <p>Introduzca nombres en lugar de identificadores de registro en campos que se vinculen a otra tabla. El registro se crea automáticamente en la tabla vinculada si no hay ninguna coincidencia.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Actualizar un registro

Este módulo de acción actualiza o inserta un registro determinado.

Especifique el ID del registro y los nuevos datos que desea que contenga.

El módulo devuelve cualquier campo estándar asociado con el registro, junto con los campos y valores personalizados a los que accede la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Airtable a Workfront Fusion, consulte <a href="#connect-airtable-to-workfront-fusion" class="MCXref xref">Conectar Airtable a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>Base </td> 
   <td> <p>Seleccione la base que contiene el registro que desea actualizar.</p> </td> 
  </tr> 
  <tr> 
   <td>Tabla </td> 
   <td> <p>Seleccione la tabla que contiene el registro que desea actualizar.</p> </td> 
  </tr> 
  <tr> 
   <td>ID de registro </td> 
   <td> <p>Si está actualizando un registro, introduzca o asigne el ID único de Airtable del registro que desea que actualice el módulo. Puede recuperar el ID, por ejemplo, mediante el módulo Buscar registros.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Registro</p> </td> 
   <td> <p>Introduzca los valores del nuevo registro. Los campos disponibles dependen de la tabla seleccionada.</p> <!-- <p>In order to delete the content of the field, use the erase function. </p>  <p>Field types (via airtable.com/api):</p> 
    <ul> 
     <li> <p><strong>Text</strong>: string</p> <p>A single line of text.</p> </li> 
     <li> <p><strong>Long text</strong>: string</p> <p>The string can contain multiple lines of text with "mention tokens." For example:</p><pre>&lt;airtable:mention id="menE1i9oBaGX3DseR"&gt;@Alex&lt;/airtable:mention&gt;</pre> </li> 
     <li><strong>Attachment</strong>: Add the attachment. Airtable will download the file from the provided url and keep its own copy of it. If the File name field is left empty, Airtable will generate the name automatically.</li> 
     <li><strong>Checkbox</strong>: Select one of the options.</li> 
     <li><strong>Multiple select</strong>: Select multiple options in the checklist.</li> 
     <li><strong>Single select</strong>: Select one option from the drop-down menu.</li> 
     <li><strong>Collaborator</strong>: Enter the email that uniquely identifies a user in Airtable who this base is shared with.</li> 
     <li><strong>Date</strong>: UTC date, for example, 2019-09-05. (ISO 8601 formatted date)</li> 
     <li><strong>Phone number</strong>: A telephone number, for example, (415) 555-9876.</li> 
     <li><strong>Email</strong>valid email address.</li> 
     <li><strong>URL</strong>: lid URL such as airtable.com or https://airtable.coiverse.</li> 
     <li><strong>Number</strongnter a number.</li> 
     <li><strong>Currency</stro Currency value.</li> 
     <li><strong>Percent</stronA percentage value; must be equal to or more than 0i> 
     <li><strong>Duration</strong>: Enter the duration time. If you need help, see the information about the duration field type in the Airtable support documentation.</li> 
     <li><strong>Rating</strong>: Enter the number. For example, "3 stars" is 3. A rating cannot be 0.</li> 
     <li><strong>Link</strong>: Enter the linked records IDs from the table. The order of record IDs is reversed compared to what you see in the app.</li> 
     <li><strong>Rollup</strong>: Computed value: COUNT(values)</li> 
     <li><strong>Lookup</strong>: Array of long text fields</li> 
     <li><strong>Autonumber</strong>: Automatically incremented unique counter for each record.</li> 
     <li> <p><strong>Barcode</strong>: The barcode object may contain the following two properties, both of which are optional.</p> <p>Barcode data (text)</p> <p>Barcode symbology, for example, "upce" or "code39" (type)</p> </li> 
    </ul> --></td> 
  </tr> 
  <tr> 
   <td>Vínculos inteligentes</td> 
   <td> <p>Introduzca nombres en lugar de identificadores de registro en campos que se vinculen a otra tabla. El registro se crea automáticamente en la tabla vinculada si no hay ninguna coincidencia.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Ver registros {#watch-records}

Este módulo de activación inicia un escenario cuando se crea o actualiza un registro en la tabla especificada.

>[!NOTE]
>
>Para utilizar este módulo, se debe crear en la tabla el campo Hora de creación o Hora de la última modificación.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>Conexión </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Airtable a Workfront Fusion, consulte <a href="#connect-airtable-to-workfront-fusion" class="MCXref xref">Conectar Airtable a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>Base </td> 
   <td> <p>Seleccione la base que desee inspeccionar para buscar nuevos registros.</p> </td> 
  </tr> 
  <tr> 
   <td>Tabla </td> 
   <td> <p>Seleccione la tabla en la que desea buscar nuevos registros.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Configuración del activador</p> </td> 
   <td> <p>Campo del activador</p> <p>Un campo <code>Created Time</code> o <code>Last Modified Time</code> que se usa para ordenar registros. Si no tiene un campo <code>Created Time</code> o <code>Last Modified Time</code> en el esquema, debe crear uno. </p> <p>Campo de etiqueta</p> <p>Campo que se utiliza como etiqueta para un registro, por ejemplo, en el cuadro de diálogo Elegir por dónde empezar.</p> </td> 
  </tr> 
  <tr> 
   <td>Límite</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo vea durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
  <tr> 
   <td>Ver</td> 
   <td> <p>Seleccione la vista que desee utilizar.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Fórmula</p> </td> 
   <td> <p>Fórmula utilizada para filtrar registros. La fórmula se evalúa para cada registro y, si el resultado no es <code>0</code>, <code>false</code>, <code>""</code>, <code>NaN</code>, <code>[]</code> o <code>#Error!</code>, el registro se incluye en la respuesta.</p> <p>Si se combina con <code>view</code>, solo se devuelven los registros de esa vista que cumplen la fórmula.</p> <p>Por ejemplo, para incluir solo registros en los que Nombre no esté vacío, introduzca:<code> NOT({Name} = '')</code></p> <p>Para obtener más información, consulte la información sobre las referencias de los campos de fórmula en la documentación de soporte de Airtable.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Ver respuestas

Este módulo de activador inicia un escenario cuando se envía un formulario.

>[!NOTE]
>
>Esta funcionalidad solo está disponible para el plan Airtable Pro de pago.

La URL del webhook debe generarse en Workfront Fusion y luego añadirse a la configuración del formulario en Airtable.

1. Añada el módulo Ver nuevas respuestas a su escenario de Workfront Fusion.
1. Genere y copie la URL del webhook.

   <!--For instructions, see [ (webhooks) in Adobe Workfront Fusion](/help/workfront-fusion/).-->

1. Inicie sesión en su cuenta de Airtable.
1. Abra Base y la tabla que desee utilizar para el formulario y cree una vista de formulario.
1. Configure el formulario según sea necesario, desplácese hacia abajo por el formulario y habilite la opción Redirigir a URL después de enviar el formulario.
1. Introduzca la URL del webhook generada en el paso 2 al cuadro de diálogo mostrado y añada el ?record_id={record_id} justo después de la URL del webhook para incluir el ID de registro en la salida del módulo. A continuación, haga clic en Guardar. La dirección URL resultante, por ejemplo, tendrá este aspecto:
1. Vuelva al escenario de Workfront Fusion y ejecute el módulo Observar respuestas solo para cargar campos de Airtable y poder asignar esos campos a los demás módulos.
1. Envíe el formulario en Airtable donde la opción Redirigir a URL después de enviar el formulario está habilitada y se añadió la URL de webhook (paso 6 anterior).

   El módulo Ver respuestas se activa y se cargan los datos deseados.

1. Añada el módulo Airtable > Obtener un registro justo después del módulo Airtable > Observar respuestas y asigne el record_id al campo ID del registro.

Ahora, cada vez que se envía el formulario, se activa el módulo Ver respuestas en el escenario de Workfront Fusion y el módulo Obtener un registro devuelve los detalles del formulario enviado.

#### Realizar una llamada de API

#### Llamada de API personalizada

Este módulo de acción le permite realizar una llamada autenticada personalizada a la API de [!DNL Airtable]. De este modo, puede crear una automatización del flujo de datos que no puedan realizar los otros módulos de [!DNL Airtable].

La acción se basa en el tipo de entidad (tipo de objeto de Allocadia) especificado.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>Conexión</p> </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Airtable a Workfront Fusion, consulte <a href="#connect-airtable-to-workfront-fusion" class="MCXref xref">Conectar Airtable a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>Escriba una ruta relativa a <code>https://api.airtable.com/</code>. Ejemplo: <code>v0/{base}/{table}</code> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Método</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Encabezados</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion añade los encabezados de autorización para usted.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Cadena de consulta</td> 
   <td> <p>Añada la consulta para la llamada de API en forma de clave y valor</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Cuerpo</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la instrucción condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>
