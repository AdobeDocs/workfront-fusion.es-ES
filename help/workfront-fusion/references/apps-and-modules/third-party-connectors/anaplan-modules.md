---
description: En un  [!DNL Adobe Workfront Fusion] escenario, puede automatizar los flujos de trabajo que utilizan Anaplan, así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion, Workfront Integrations and Apps
exl-id: 81c9b141-4e40-430f-99f1-c44b7a833bcd
source-git-commit: 85cd8dbf70dff220f593fa669b447bf5df2a21a2
workflow-type: tm+mt
source-wordcount: '1859'
ht-degree: 27%

---

# Módulos de [!DNL Anaplan]

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!DNL Anaplan], así como conectarlo a varias aplicaciones y servicios de terceros.

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

Antes de poder usar el conector de [!DNL Anaplan], debe asegurarse de que se cumplen los siguientes requisitos previos:

* Debe tener una cuenta activa de [!UICONTROL Anaplan].
* Debe configurar espacios de trabajo, modelos y otros objetos [!DNL Anaplan] en su cuenta de [!UICONTROL Anaplan] para que [!DNL Workfront Fusion] pueda interactuar con ellos.

## Información de API de Anaplan

El conector Anaplan utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL básica</td> 
   <td>https://api.anaplan.com/2/0/
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> Versión 2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>v1.11.5/td&gt; 
 </tbody> 
</table>

## Conectar [!DNL Anaplan] a [!DNL Workfront Fusion] {#connect-anaplan-to-workfront-fusion}

Para crear una conexión para los módulos de [!DNL Anaplan]:

1. Haga clic en **[!UICONTROL Añadir]** junto al cuadro [!UICONTROL Conexión].
1. Seleccione el tipo de conexión.

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!DNL Anaplan] [!UICONTROL Básico]</td> 
      <td> <p>Una conexión [!DNL Anaplan] [!UICONTROL Basic] sólo requiere una dirección de correo electrónico y una contraseña para crear la conexión. </p> <p>Escriba un nombre para la conexión y luego ingrese su dirección de correo electrónico y la contraseña de su cuenta de [!DNL Anaplan].</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!DNL Anaplan] [!UICONTROL Certificado de CA]</td> 
      <td> <p>Una conexión [!DNL Anaplan] [!UICONTROL CA Certificate] requiere una clave de certificado [!UICONTROL], [!UICONTROL Encoded Data] y [!UICONTROL Encoded Signed Data]. Puede generarlas en su cuenta de [!DNL Anaplan]. Para obtener instrucciones, consulte la documentación de [!DNL Anaplan].</p> <p>Escriba un nombre para la conexión y, a continuación, escriba la clave de certificado [!UICONTROL], los datos codificados [!UICONTROL] y los datos firmados codificados [!UICONTROL] que generó en su cuenta de [!DNL Anaplan].</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.

## Módulos de [!DNL Anaplan] y sus campos

Al configurar módulos de [!DNL Anaplan], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Anaplan] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Activadores](#triggers)
* [Acciones](#actions)
* [Búsquedas](#searches)

### Activadores

#### [!DNL Watch records]

Este módulo de déclencheur inicia un escenario cuando se crea o actualiza un registro del tipo elegido.

>[!NOTE]
>
>Este módulo devuelve los datos de los registros nuevos. No devuelve los datos de los registros existentes modificados.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Anaplan], consulte <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">Conectar[!DNL Anaplan] a [!DNL Workfront Fusion]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de objeto a observar</td> 
   <td>Seleccione el tipo de elemento que desea ver. El escenario comienza cuando se crea o actualiza este tipo de registro.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Identificador de &lt;Object&gt;</td> 
   <td>Introduzca el ID del objeto en un plan, como un modelo o módulo, asociado a los objetos que desea inspeccionar</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Límite</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Acciones

* [[!UICONTROL Crear un elemento de lista]](#create-a-list-item)
* [[!UICONTROL Realizar una llamada de API personalizada]](#make-a-custom-api-call)
* [[!UICONTROL Leer un registro]](#read-a-record)
* [[!UICONTROL Ejecutar una acción]](#run-an-action)
* [[!UICONTROL Actualizar un registro]](#update-a-record)
* [[!UICONTROL Cargar un archivo]](#upload-a-file)

#### [!UICONTROL Crear un elemento de lista]

Este módulo de acción añade un nuevo elemento a una lista de Anaplan.

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Connection]</td>
        <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Anaplan], consulte <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">Conectar[!DNL Anaplan] a [!DNL Workfront Fusion]</a> en este artículo.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Workspace ID]</td>
        <td>Seleccione o asigne el ID de la Workspace de Anaplan que contiene la lista donde desea agregar un elemento.</td>
    </tr>
    <tr>
        <td>[!UICONTROL ID de modelo]</td>
        <td>Seleccione o asigne el ID del modelo que contiene la lista donde desea agregar un elemento.</td>
    </tr>
    <tr>
        <td>[!UICONTROL List ID]</td>
        <td>Seleccione o asigne el ID de la lista donde desea crear un elemento.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Name]</td>
        <td>Escriba un nombre para el nuevo elemento.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Código]</td>
        <td>Introduzca el código del nuevo artículo. Los códigos son códigos generados por el usuario que permiten distinguir entre elementos de línea con el mismo nombre.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Parent]</td>
        <td>Introduzca el nombre del elemento principal en el que desea crear el nuevo elemento.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Properties]</td>
        <td>Si la lista a la que desea agregar un elemento tiene propiedades personalizadas, seleccione las propiedades para las que desee agregar valores y, a continuación, agregue los valores.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Subconjuntos]</td>
        <td>Si la lista a la que desea agregar elementos tiene subconjuntos personalizados, seleccione los subconjuntos a los que desea agregar el elemento y, a continuación, seleccione <b>[!UICONTROL Sí]</b> para agregar el nuevo elemento a ese subconjunto.</td>
    </tr>
</table>

#### [!UICONTROL Realizar una llamada de API personalizada]

Este módulo le permite realizar una llamada de API personalizada a la API [!DNL Anaplan].

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Anaplan], consulte <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Anaplan] a [!DNL Workfront Fusion]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>Introduzca una ruta relativa a <code>https://api.anaplan.com/2/0/</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] añade encabezados de autorización automáticamente.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String] </td> 
   <td> <p>Introduzca la cadena de consulta de la solicitud.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la instrucción condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Eliminar un registro]

Este módulo de acción elimina un registro existente.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Anaplan], consulte <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">Conectar[!DNL Anaplan] a [!DNL Workfront Fusion]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Seleccione o asigne el ID de la Workspace de Anaplan que contiene el objeto que desea eliminar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de modelo]</td> 
   <td>Introduzca o asigne el ID del modelo que contiene el objeto que desea eliminar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Eliminar</td> 
   <td> <p>Seleccione el tipo de objeto que desea eliminar.</p> 
    <ul> 
     <li> <p><b>Acción</b> </p> <p>Seleccione o asigne la acción que desea eliminar.</p> </li> 
     <li> <p><b>Elemento de lista</b> </p> <p>Seleccione la lista de la que desea eliminar un elemento y, a continuación, introduzca o asigne el ID o el código del elemento que desea eliminar</p>  </li> 
     <li> <p><b>[!UICONTROL File]</b> </p> <p>Seleccione o asigne el archivo que desea eliminar.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Leer un registro]

Este módulo de acción lee un solo registro.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Anaplan], consulte <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">Conectar[!DNL Anaplan] a [!DNL Workfront Fusion]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>Seleccione el tipo de registro que desea leer.</p> 
    <ul> 
     <li> <p><b>Modelo</b> </p> <p>Seleccione o asigne el ID del modelo que desea leer</p> </li> 
     <li> <p><b>Lista de modelos</b> </p> <p>Seleccione o asigne los ID de Workspace y del modelo que contienen la lista que desea leer y, a continuación, seleccione la lista. En el campo [!UICONTROL Data type], seleccione si desea leer datos o metadatos.</p> </li> 
     <li> <p><b>Versión de modelo</b> </p> <p>Seleccione o asigne el ID del modelo que desea leer.</p> </li> 
     <li> <p><b>Usuario</b> </p> <p>Seleccione si desea devolver datos sobre el propietario de la cuenta en uso u otro usuario. Si selecciona otro usuario, seleccione el nombre del usuario.</p> </li> 
     <li> <p><b>Workspace</b> </p> <p>Seleccione o asigne el ID de la Workspace que desea leer.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Ejecutar una acción]

Este módulo de acción importa, exporta, elimina o procesa una acción.

<table style="table-layout:auto"> 
     <col/>
     <col/>
     <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL Connection]</td>
        <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Anaplan], consulte <a href="#Connect" class="MCXref xref" >[!UICONTROL Connect Anaplan to Workfront Fusion]</a> en este artículo.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Workspace ID]</td>
        <td>Seleccione o asigne el identificador de [!DNL Anaplan] Workspace donde desea realizar la acción</td>
      </tr>
      <tr >
        <td role="rowheader">[!UICONTROL ID de modelo]</td>
        <td>Seleccione o asigne el ID del modelo en el que desea realizar la acción.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Tipo de acción]</td>
        <td>
          <p>Seleccione la acción que desea realizar</p>
            <ul>
              <li>
                <p><b>[!UICONTROL Delete]</b>
                </p>
                <p>Introduzca o asigne el ID de la acción que desea eliminar.</p>
              </li>
              <li>
                <p><b>[!UICONTROL Export]</b>
                </p>
                <p>Introduzca o asigne el ID de la definición de exportación que desea utilizar. Puede exportar a los siguientes formatos de archivo:</p>
                  <ul>
                    <li>
                      <p>XLS</p>
                    </li>
                    <li>
                      <p>XLSX</p>
                    </li>
                    <li>
                      <p>CSV</p>
                    </li>
                  </ul>
                </li>
                <li>
                  <p><b>[!UICONTROL Importar] </b>
                  </p>
                  <p style="font-weight: normal;">Introduzca o asigne el ID de la definición de importación que desee utilizar.</p>
                </li>
                <li>
                 <p><b>[!UICONTROL Proceso]</b>
                 </p>
                  <p>Introduzca o asigne el ID del proceso que desea utilizar. </p>
                </li>
              </ul>
            </td>
          </tr>
        </tbody>
      </table>


#### [!UICONTROL Actualizar un registro]

Este módulo de acción actualiza un único registro en [!UICONTROL Anaplan].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Anaplan], consulte <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">Conectar[!DNL Anaplan] a [!DNL Workfront Fusion]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>Seleccione el tipo de registro que desea actualizar. </p> 
    <ul> 
     <li> <p><b>[!UICONTROL Elemento de lista]</b> </p> <p>Para ver los campos, consulte <a href="#create-a-list-item" class="MCXref xref">Crear un elemento de lista</a> en este artículo.</p> </li> 
     <li> <p><b>[!UICONTROL Module datos de celda]</b> </p> <p>Al actualizar los datos de la celda, también se actualizan todos los cálculos descendentes que utilizan esos datos.</p> <p>Rellene los campos siguientes:</p> 
      <ul> 
       <li> <p><b>[!UICONTROL ID de modelo]</b> </p> <p>Seleccione o asigne el modelo que contiene la celda que desea actualizar.</p> </li> 
       <li> <p><b>[!UICONTROL ID de módulo]</b> </p> <p>Seleccione o asigne el módulo que contiene la celda que desea actualizar</p> </li> 
       <li> <p><b>[!UICONTROL Nombre de elemento de línea]</b> </p> <p>Seleccione o asigne el elemento de línea de la celda que desea actualizar</p> </li> 
       <li> <p style="font-weight: bold;">[!UICONTROL Dimension ID]</p> <p>Seleccione o asigne la dimensión que está en el elemento de línea.</p> 
       <p><b>Nota: </b> 
       <ul>
       <li> La clave de Dimension (valor) debe ser <code>dimensionName</code> (siguiente) o <code>dimensionId</code> (ID).</li>
       <li>La clave de elemento (valor) debe ser <code>itemName</code> (texto), <code>itemCode</code> (texto) o <code>itemId</code> (identificador).</li>
       <li>Las claves de Dimension y de elemento deben ser del mismo tipo (texto o ID).
       </ul>
        </p> 
        <p>Para obtener información sobre las dimensiones, busque Dimensiones en [!DNL Anaplan Anapedia].</p> </li> 
       <li> <p><b>[!UICONTROL Value]</b> </p> <p>Introduzca o asigne el nuevo valor de la celda.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Modelo año fiscal actual]</b> </p> <p>Introduzca el ID de Workspace y el ID de modelo del modelo para el que desea actualizar el año fiscal y, a continuación, introduzca o asigne el nuevo año para el modelo.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Cargar un archivo]

Este módulo de acción carga un archivo en Anaplan. El archivo debe haberse cargado ya en Anaplan. Puede utilizar este módulo para cargarlo en ubicaciones adicionales dentro de Anaplan.
<table style="table-layout:auto">
<col>
<col>
<tbody>
<tr>
<td role="rowheader">[!UICONTROL Connection]</td>
<td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Anaplan], consulte <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">Conectar[!DNL Anaplan] a [!DNL Workfront Fusion]</a> en este artículo.</td>
</tr>
<tr>
<td role="rowheader">[!UICONTROL Workspace ID]</td>
<td>Seleccione o asigne el identificador de [!DNL Anaplan] Workspace donde desea cargar un archivo.</td>
</tr>
<tr>
<td role="rowheader">[!UICONTROL ID de modelo]</td>
<td>Seleccione o asigne el ID del modelo en el que desea cargar un archivo.</td>
</tr>
<tr>
<td role="rowheader">[!UICONTROL File ID]</td>
<td>Seleccione o asigne el ID del archivo que desea cargar.</td>
</tr>
</tbody>
</table>
</div>

### Búsquedas

#### [!UICONTROL Obtener registro]

Este módulo de búsqueda devuelve todos los registros accesibles del tipo seleccionado.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Anaplan], consulte <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">Conectar[!DNL Anaplan] a [!DNL Workfront Fusion]</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tipos de registro]</td> 
   <td> <p>Seleccione el tipo de registro que desea recuperar.</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Espacios de trabajo]</b> </p> </li> 
       <li> <p><b>[!UICONTROL Modelos]</b> </p> </li> 
       <li> <p><b>[!UICONTROL Elementos de línea]</b> </p> <p>Seleccione o asigne el ID del modelo que contiene los [!DNL line] elementos que desea recuperar.</p> </li> 
       <li> <p><b>[!UICONTROL Listas de modelos]</b> </p> <p>Seleccione o asigne el ID del Workspace y el ID del modelo que contienen las listas del modelo que desea recuperar.</p> </li> 
       <li> <p><b>[!UICONTROL Calendario de modelo]</b> </p> <p>Seleccione o asigne el ID del Workspace que contiene el calendario del modelo que desea recuperar.</p> </li> 
       <li> <p><b>[!UICONTROL Versiones de modelo]</b> </p> </li> 
       <li> <p>Seleccione o asigne el ID del modelo que contiene las versiones del modelo que desea recuperar.</p> </li> 
       <li> <p><b>[!UICONTROL Usuarios]</b> </p> </li> 
       <li> <p><b>[!UICONTROL Views]</b> </p> <p>Seleccione si desea elegir la vista por módulo o por modelo y, a continuación, seleccione o asigne el ID del módulo o modelo que contiene la vista que desea recuperar.</p> </li> 
      </ul> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Devolver tamaño del espacio de trabajo]</td> 
   <td>Active esta opción para devolver una estimación del tamaño actual del espacio de trabajo. Esta estimación se basa en los tamaños de todos los módulos incluidos en el espacio de trabajo.</td> 
  </tr> 
 </tbody> 
</table>
