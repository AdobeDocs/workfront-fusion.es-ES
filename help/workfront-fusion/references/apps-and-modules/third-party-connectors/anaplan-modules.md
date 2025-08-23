---
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan Anaplan, así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion, Workfront Integrations and Apps
exl-id: 81c9b141-4e40-430f-99f1-c44b7a833bcd
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '2023'
ht-degree: 21%

---

# Módulos de [!DNL Anaplan]

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!DNL Anaplan], así como conectarlo a varias aplicaciones y servicios de terceros.

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

Antes de poder usar el conector de [!DNL Anaplan], debe asegurarse de que se cumplen los siguientes requisitos previos:

* Debe tener una cuenta activa de [!UICONTROL Anaplan].
* Debe configurar espacios de trabajo, modelos y otros objetos [!DNL Anaplan] en su cuenta de [!UICONTROL Anaplan] para que Workfront Fusion pueda interactuar con ellos.

## Información de API de Anaplan

El conector Anaplan utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Dirección URL base</td> 
   <td>https://api.anaplan.com/2/0/
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> Versión 2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.11.5</td> 
 </tbody> 
</table>

## Conexión de [!DNL Anaplan] a Workfront Fusion {#connect-anaplan-to-workfront-fusion}

Para crear una conexión para los módulos de [!DNL Anaplan]:

1. Haga clic en **[!UICONTROL Añadir]** junto al cuadro [!UICONTROL Conexión].
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
        <td role="rowheader">[!UICONTROL correo electrónico]</td>
        <td>
          <p>Introduzca la dirección de correo electrónico de esta cuenta de Anaplan.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Password]</td>
        <td>Introduzca la contraseña de esta cuenta de Anaplan.</td>
      </tr>
     </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.

<!--1. Click **[!UICONTROL Add]** next to the [!UICONTROL Connection] box.
1. Select the connection type.

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!DNL Anaplan] [!UICONTROL Basic]</td> 
      <td> <p>An [!DNL Anaplan] [!UICONTROL Basic] connection requires only an email address and password to create the connection. </p> <p>Enter a name for the connection, then enter your email address and the password of your [!DNL Anaplan] account.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!DNL Anaplan] [!UICONTROL CA Certificate]</td> 
      <td> <p>An [!DNL Anaplan] [!UICONTROL CA Certificate] connection requires a [!UICONTROL Certificate Key], [!UICONTROL Encoded Data], and [!UICONTROL Encoded Signed Data]. You can generate these in your [!DNL Anaplan] account. For instructions, see the [!DNL Anaplan] documentation.</p> <p>Enter a name for the connection, then enter the [!UICONTROL Certificate Key], [!UICONTROL Encoded Data], and [!UICONTROL Encoded Signed Data] that you generated in your [!DNL Anaplan] account.</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. Click **[!UICONTROL Continue]** to save the connection and return to the module.-->

## Módulos de [!DNL Anaplan] y sus campos

Al configurar módulos de [!DNL Anaplan], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL Anaplan] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

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
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Anaplan], consulte <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Anaplan] a Workfront Fusion</a> en este artículo.</td> 
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
* [Eliminación de un registro](#delete-a-record)
* [Exportación de datos](#export-data)
* [Importar datos](#import-data)
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
        <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Anaplan], consulte <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Anaplan] a Workfront Fusion</a> en este artículo.</td>
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
        <td>Si la lista a la que desea agregar elementos tiene subconjuntos personalizados, seleccione los subconjuntos a los que desee agregar el elemento.</td>
    </tr>
</table>

#### [!UICONTROL Eliminar un registro]

Este módulo de acción elimina un registro existente.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Anaplan], consulte <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Anaplan] a Workfront Fusion</a> en este artículo.</td> 
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
   <td role="rowheader">Tipo de registro</td> 
   <td> <p>Seleccione el tipo de objeto que desea eliminar.</p> 
    <ul> 
     <li> <p><b>Acción</b> </p> <p>Seleccione o asigne la acción que desea eliminar.</p> </li> 
     <li> <p><b>Elemento de lista</b> </p> <p>Seleccione la lista de la que desea eliminar un elemento y, a continuación, introduzca o asigne el ID o el código del elemento que desea eliminar</p>  </li> 
     <li> <p><b>[!UICONTROL File]</b> </p> <p>Seleccione o asigne el archivo que desea eliminar.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>



#### [!UICONTROL Exportar datos]

Este módulo de acción recupera datos de Anaplan mediante Export Definitions

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Anaplan], consulte <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Anaplan] a Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Seleccione o asigne el ID de la Workspace de Anaplan que contiene los datos que desea exportar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de modelo]</td> 
   <td>Introduzca o asigne el ID del modelo que contiene los datos que desea exportar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de definición de exportación</td> 
   <td> <p>Introduzca o asigne el ID de la definición de exportación de Anaplan que desee utilizar.</p> 
   </td> 
  </tr> 
 </tbody> 
</table>

#### Importar datos

Este módulo de acción importa datos en Anaplan.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Anaplan], consulte <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Anaplan] a Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Seleccione o asigne el ID de la Workspace de Anaplan donde desea importar los datos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID de modelo]</td> 
   <td>Introduzca o asigne el ID del modelo donde desea importar los datos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de definición de exportación</td> 
   <td> <p>Introduzca o asigne el ID de la definición de importación de Anaplan que desee utilizar.</p> 
   </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Realizar una llamada de API personalizada]

Este módulo le permite realizar una llamada de API personalizada a la API [!DNL Anaplan].

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Anaplan], consulte <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Anaplan] a Workfront Fusion</a> en este artículo.</td> 
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
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion añade encabezados de autorización automáticamente.</p> </td> 
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

#### [!UICONTROL Leer un registro]

Este módulo de acción lee un solo registro.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Anaplan], consulte <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Anaplan] a Workfront Fusion</a> en este artículo.</td> 
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
     <li> <p><b>Vista</b> </p> <p>Seleccione o asigne el ID del modelo que contiene la vista que desea leer.</p> </li> 
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
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Anaplan], consulte <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Anaplan] a Workfront Fusion</a> en este artículo.</td> 
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

#### [!UICONTROL Cargar archivo para la acción]

Este módulo de acción carga un archivo existente en Anaplan a ubicaciones adicionales dentro de Anaplan.
<table style="table-layout:auto">
<col>
<col>
<tbody>
<tr>
<td role="rowheader">[!UICONTROL Connection]</td>
<td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Anaplan], consulte <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Anaplan] a Workfront Fusion</a> en este artículo.</td>
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
   <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Anaplan], consulte <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Anaplan] a Workfront Fusion</a> en este artículo.</td> 
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
