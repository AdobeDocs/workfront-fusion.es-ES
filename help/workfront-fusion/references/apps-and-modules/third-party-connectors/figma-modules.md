---
title: Módulos Figma
description: Con los módulos Adobe Workfront Fusion Figma, puede recuperar listas de comentarios, archivos, versiones de archivos o proyectos. También puede publicar un comentario o hacer una llamada a la API de Figma.
author: Becky
feature: Workfront Fusion
exl-id: 1220460b-1957-4dfc-b7c1-4c97b36ea061
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '2600'
ht-degree: 16%

---

# Módulos de [!DNL Figma]

Con los módulos de Adobe Workfront Fusion [!DNL Figma], puede recuperar listas de comentarios, archivos, versiones de archivos o proyectos. También puede publicar un comentario o llamar a la API [!DNL Figma].

Si necesita instrucciones sobre cómo crear un escenario, vea los artículos en [Crear un escenario: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

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

Para usar módulos [!DNL Figma], debe tener una cuenta de [!DNL Figma].

## Información de API de Figma

El conector Figma utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Dirección URL base</td> 
   <td> https://api.figma.com/v1</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> Versión 1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.8.25</td> 
  </tr>
 </tbody> 
 </table>

## Crear una conexión con Figma

Para crear una conexión para los módulos Figma:

1. En cualquier módulo Figma, haga clic en **[!UICONTROL Agregar]** junto al cuadro Conexión.

1. Rellene los campos siguientes:

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">[!UICONTROL Connection type]</td>
        <td>
          <p> Para nuevas conexiones, seleccione <code>Figma</code> sin la etiqueta Heredado. </p><p>Figma cambió sus requisitos de autenticación en enero de 2025. El tipo de conexión <code>Figma</code> cumple los nuevos requisitos. El tipo de conexión <code>Figma (Legacy)</code> se eliminará en el futuro.</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>Introduzca un nombre para esta conexión.</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Escriba su [!UICONTROL Archivo] [!UICONTROL ID de cliente].</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Escriba el Secreto de cliente de Figma .</td>
        </tr>
        <tr>
        <td role="rowheader">Ámbitos personalizados</td>
        <td>Escriba los ámbitos personalizados necesarios para esta conexión.</td>
        </tr>
        <tr>
        <td role="rowheader">URL de verificación de conexión personalizada</td>
        <td>El extremo predeterminado para comprobar que la conexión se creó correctamente es: <code>https://api.figma.com/v1/me</code>. Si esta dirección URL no es compatible con el ámbito personalizado, proporcione una dirección URL de verificación personalizada.</td>
        </tr>
      </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.



## Módulos de [!DNL Figma] y sus campos

Al configurar módulos de [!DNL Figma], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL Figma] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Comentarios](#comments)

* [Proyectos y archivos](#projects-and-files)

* [Componentes y estilos](#components-and-styles)

* [Otro](#other)


### Comentarios

* [Eliminar un comentario](#delete-a-comment)

* [Enumerar comentarios](#list-comments)

* [Publicar un comentario](#post-a-comment)


#### [!UICONTROL Eliminar un comentario]

Este módulo de acción elimina un solo comentario de un archivo.

<table style="table-layout:auto"> 
  <col/>
  <col />
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>Para obtener instrucciones sobre cómo conectar tu cuenta de [!DNL Figma] a Workfront Fusion, consulta <a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">Crear una conexión con Figma</a> en este artículo.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL File ID]</td>
      <td>Introduzca o asigne el ID de archivo del archivo desde el que desea agregar o eliminar un comentario. </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Comment ID]</td>
      <td>Escriba el texto del comentario que desea eliminar.</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Enumerar comentarios]

Este módulo de búsqueda enumera todos los comentarios adjuntos a un solo archivo en [!DNL Figma].

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>Para obtener instrucciones sobre cómo conectar tu cuenta de [!DNL Figma] a Workfront Fusion, consulta <a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">Crear una conexión con Figma</a> en este artículo.</p>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL File ID]</td>
      <td>
        <p>Introduzca o asigne el ID de archivo del archivo para el que desea recuperar los comentarios. </p>
        <ul>
          <li>
            <p>Si no conoce el identificador, haga clic en <b>[!UICONTROL Buscar archivos]</b> y escriba o asigne el identificador del proyecto al que está asociado el archivo. A continuación, seleccione el archivo.</p>
          </li>
          <li>
            <p>Si no conoce el identificador del proyecto, haga clic en <b>[!UICONTROL Buscar proyectos]</b> y escriba o asigne el identificador del equipo propietario del proyecto al que está asociado el archivo. A continuación, seleccione el proyecto y, a continuación, seleccione el archivo.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Maximum number of returned comments]</td>
      <td>Introduzca o asigne el número máximo de comentarios que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</td>
    </tr>
  </tbody>
</table>


#### [!UICONTROL Publicar un comentario]

Este módulo de acción publica un comentario en un archivo Figma.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>Para obtener instrucciones sobre cómo conectar tu cuenta de [!DNL Figma] a Workfront Fusion, consulta <a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">Crear una conexión con Figma</a> en este artículo.</p>
    </tr>
    <tr>
      <td  role="rowheader">[!UICONTROL File ID]</td>
      <td>
        <p>Introduzca o asigne el ID de archivo del archivo en el que desea publicar un comentario. </p>
        <ul>
          <li>
            <p>Si no conoce el identificador del archivo, haga clic en <b>[!UICONTROL Buscar archivos]</b> y escriba o asigne el identificador del proyecto al que está asociado el archivo. A continuación, seleccione el archivo.</p>
          </li>
          <li>
            <p>Si intenta encontrar el identificador del archivo y no conoce el identificador del proyecto, haga clic en <b>[!UICONTROL Buscar proyectos]</b> y escriba o asigne el identificador del equipo propietario del proyecto con el que está asociado el archivo. Seleccione el proyecto y, a continuación, seleccione el archivo.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Comment]</td>
      <td>Introduzca el texto del comentario.</td>
    </tr>
  </tbody>
</table>


### Proyectos y archivos

* [Obtener un archivo o una imagen](#get-a-file-or-image)

* [Historial de versiones del archivo de lista](#list-file-version-history)

* [Lista de archivos de proyecto](#list-project-files)

* [Enumerar proyectos](#list-projects)


#### [!UICONTROL Obtener un archivo o imagen]

Este módulo de acción recupera un solo archivo o imagen de una biblioteca Figma

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>Para obtener instrucciones sobre cómo conectar tu cuenta de [!DNL Figma] a Workfront Fusion, consulta <a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">Crear una conexión con Figma</a> en este artículo.</p>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Object type]</td>
      <td>
        <p>Seleccione el tipo de objeto que desea recuperar.</p>
        <ul>
          <li>
            <p><b>[!UICONTROL File]</b>
            </p>
            <p>El módulo devuelve el documento al que hace referencia [!UICONTROL Key] como objeto JSON. La clave del archivo se puede analizar desde cualquier URL del archivo Figma.</p>
            <p>Para ver los campos, consulte <a href="#get-a-file-or-image-file" class="MCXref xref" >[!UICONTROL Obtener un archivo o imagen: Archivo]</a>.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Nodos de archivo]</b>
            </p>
            <p>Devuelve los nodos a los que hacen referencia los identificadores como un objeto JSON. Los nodos se recuperan del archivo [!DNL Figma] al que hace referencia [!UICONTROL Key].</p>
            <p>Para ver los campos, consulte <a href="#get-a-file-or-image-file-nodes" class="MCXref xref" >[!UICONTROL Obtener un archivo o imagen: nodos de archivo]</a>.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Imagen]</b>
            </p>
            <p>El módulo procesa imágenes de un archivo.</p>
            <p>Para ver los campos, consulte <a href="#get-a-file-or-image-image" class="MCXref xref" >[!UICONTROL Obtener un archivo o imagen: Imagen]</a>.</p>
          </li>
          <li>
            <p><b>[!UICONTROL rellenos de imagen]</b>
            </p>
            <p>El módulo devuelve vínculos de descarga para todas las imágenes presentes en los rellenos de imagen de un documento. Los rellenos de imagen muestran [!DNL Figma] las imágenes que proporcionó el usuario. Cuando arrastra una imagen a [!DNL Figma], [!DNL Figma] crea un rectángulo con un solo relleno que representa la imagen y el usuario puede transformar el rectángulo (y las propiedades del relleno).</p>
            <p>Para ver los campos, consulte <a href="#get-a-file-or-image-image-fills" class="MCXref xref" >[!UICONTROL Obtener un archivo o imagen: Rellenos de imagen]</a>.</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>


##### Obtener un archivo o imagen: Archivo

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Tecla de archivo]</td>
      <td>Seleccione el archivo desde el que desea devolver JSON.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL ID de versión]</td>
      <td>Introduzca o asigne la versión del archivo que desea que devuelva el módulo. Para el módulo actual, deje este campo en blanco.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL ID de nodo]</td>
      <td>
        <p>Para devolver sólo un subconjunto del documento, escriba los nodos que desea que devuelva el módulo. El módulo devuelve los nodos enumerados, sus nodos secundarios y cualquier elemento entre el nodo raíz y los nodos enumerados.</p>
        <p>Para cada nodo que desee devolver, haga clic en <b>[!UICONTROL Add]</b> e introduzca el texto del nodo.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Profundidad]</td>
      <td>
        <p>Introduzca o asigne un entero que represente la profundidad en el árbol de documentos para la que desea devolver resultados. </p>
        <div class="example"><span class="autonumber"><span><b>Ejemplo:</b></span></span>
          <ul>
            <li>
              <p>Para devolver solo las páginas, escriba <code>1</code>.</p>
            </li>
            <li>
              <p>Para devolver páginas y objetos de nivel superior, escriba <code>2</code>.</p>
            </li>
          </ul>
        </div>
        <p>Para devolver todos los nodos, deje este campo en blanco.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Geometría]</td>
      <td>Para devolver datos vectoriales, escriba <code>paths</code>.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Plugin data]</td>
      <td>Una lista separada por comas de los ID de complemento o la cadena "[!UICONTROL shared]". Cualquier dato presente en el documento escrito por esos complementos se incluirá en el resultado en las propiedades <code>pluginData</code> y <code>sharedPluginData</code>.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Datos de rama]</td>
      <td>Active esta opción para devolver los metadatos de la rama del archivo solicitado. Si el archivo es una rama, la clave del archivo principal se incluye en la respuesta devuelta. Si el archivo tiene ramas, sus metadatos se incluyen en la respuesta devuelta. Predeterminado: <code>false</code>.</td>
    </tr>
  </tbody>
</table>

##### Obtener un archivo o imagen: nodos de archivo

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Tecla de archivo]</td>
      <td>Seleccione el archivo desde el que desea devolver JSON.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL ID de nodo]</td>
      <td>
        <p>Introduzca los nodos que desea que devuelva y convierta el módulo</p>
        <p>Para cada nodo que desee devolver, haga clic en <b>[!UICONTROL Add]</b> e introduzca el texto del nodo.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL ID de versión]</td>
      <td>Introduzca o asigne la versión del archivo que desea que devuelva el módulo. Para el módulo actual, deje este campo en blanco.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Profundidad]</td>
      <td>
        <p>Introduzca o asigne un entero que represente la profundidad en el árbol de documentos para la que desea devolver resultados. </p>
        <div class="example"><span class="autonumber"><span><b>Ejemplo:</b></span></span>
          <ul>
            <li>
              <p>Para devolver solo las páginas, escriba <code>1</code>.</p>
            </li>
            <li>
              <p>Para devolver páginas y objetos de nivel superior, escriba <code>2</code>.</p>
            </li>
          </ul>
        </div>
        <p>Para devolver todos los nodos, deje este campo en blanco.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Geometría]</td>
      <td>Para devolver datos vectoriales, escriba <code>paths</code>.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Plugin data]</td>
      <td>Una lista separada por comas de los ID de complemento o la cadena "compartida". Los datos presentes en el documento escrito por esos complementos se incluirán en el resultado de las propiedades pluginData y sharedPluginData.</td>
    </tr>
  </tbody>
</table>


##### Obtener un archivo o imagen: Imagen

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Tecla de archivo]</td>
      <td>Seleccione el archivo desde el que desea devolver JSON.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL ID de nodo]</td>
      <td>
        <p>Introduzca los nodos que desea que procese el módulo.</p>
        <p>Para cada nodo que desee procesar, haga clic en <b>[!UICONTROL Add]</b> e introduzca el texto del nodo.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Escala]</td>
      <td>Para escalar la imagen, introduzca o asigne el factor de escala. Este número debe estar entre 0,01 y 4.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Formato]</td>
      <td>
        <p>Seleccione el formato para la salida de imagen.</p>
        <ul>
          <li>
            <p>JPG</p>
          </li>
          <li>
            <p>PNG</p>
          </li>
          <li>
            <p>SVG</p>
          </li>
          <li>
            <p>PDF</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL SVG - Incluir ID]</td>
      <td>Active esta opción para incluir los atributos de ID de todos los elementos de SVG. Valor predeterminado: [!UICONTROL false].</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL SVG - Simplificar trazo]</td>
      <td>Active esta opción para simplificar los trazos interiores/exteriores y utilice el atributo de trazo si es posible en lugar de &lt;máscara&gt;. Valor predeterminado: [!UICONTROL true].</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Utilizar límites absolutos]</td>
      <td>Active esta opción para utilizar las dimensiones completas del nodo independientemente de si se recorta o no o el espacio alrededor está vacío. Utilice esta opción para exportar nodos de texto sin recortarlos. Valor predeterminado: [!UICONTROL false].</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Version]</td>
      <td>Introduzca o asigne la versión del archivo que desea que devuelva el módulo. Para el módulo actual, deje este campo en blanco.</td>
    </tr>
  </tbody>
</table>

##### Obtener un archivo o imagen: rellenos de imagen

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Tecla de archivo]</td>
      <td>Seleccione el archivo desde el que desea devolver JSON.</td>
    </tr>
  </tbody>
</table>

### [!UICONTROL Historial de versiones de archivos de lista]

Este módulo de búsqueda devuelve el historial de versiones de un solo archivo en [!UICONTROL Figma].
<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>Para obtener instrucciones sobre cómo conectar tu cuenta de [!DNL Figma] a Workfront Fusion, consulta <a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">Crear una conexión con Figma</a> en este artículo.</p>
    <tr>
      <td role="rowheader">[!UICONTROL File ID]</td>
      <td>
        <p>Introduzca o asigne el ID de archivo del archivo para el que desea recuperar el historial de versiones. </p>
        <ul>
          <li>
            <p>Si no conoce el identificador del archivo, haga clic en <b>[!UICONTROL Buscar archivos]</b> y escriba o asigne el identificador del proyecto al que está asociado el archivo. A continuación, seleccione el archivo.</p>
          </li>
          <li>
            <p>Si intenta encontrar el identificador del archivo y no conoce el identificador del proyecto, haga clic en <b>[!UICONTROL Buscar proyectos]</b> y escriba o asigne el identificador del equipo propietario del proyecto con el que está asociado el archivo. Seleccione el proyecto y, a continuación, seleccione el archivo.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Maximum number of returned files]</td>
      <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Enumerar archivos de proyecto]

Este módulo de búsqueda devuelve una lista de todos los archivos del proyecto especificado.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>Para obtener instrucciones sobre cómo conectar tu cuenta de [!DNL Figma] a Workfront Fusion, consulta <a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">Crear una conexión con Figma</a> en este artículo.</p>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL File ID]</td>
      <td>
        <p>Escriba o asigne el Id. del proyecto para el que desea recuperar los archivos. </p>
        <ul>
          <li>
            <p>Si no conoce el id. del proyecto, haga clic en <b>[!UICONTROL Buscar proyectos]</b> y escriba o asigne el id. del equipo con el que está asociado el proyecto. A continuación, seleccione el proyecto.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Maximum number of returned files]</td>
      <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Lista de proyectos]

Este módulo de búsqueda devuelve una lista de todos los proyectos dentro del equipo especificado.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>Para obtener instrucciones sobre cómo conectar tu cuenta de [!DNL Figma] a Workfront Fusion, consulta <a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">Crear una conexión con Figma</a> en este artículo.</p>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Team ID]</td>
      <td>Escriba o asigne el Id. del proyecto para el que desea recuperar los archivos. El ID del equipo se puede encontrar en la dirección URL de la página del equipo en Figma</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Número máximo de proyectos devueltos]</td>
      <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td>
    </tr>
  </tbody>
</table>


### Componentes y estilos

#### [!UICONTROL Obtener un estilo o componente]

Este módulo de acción recupera un solo estilo o componente, o un conjunto de estilos o componentes.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>Para obtener instrucciones sobre cómo conectar tu cuenta de [!DNL Figma] a Workfront Fusion, consulta <a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">Crear una conexión con Figma</a> en este artículo.</p>
    </tr>
    <tr>
      <td role="rowheader">Object&gt; type</td>
      <td>Seleccione el tipo de objeto que desea recuperar.</td>
    </tr>
    <tr>
      <td role="rowheader">&lt;[!UICONTROL Objeto&gt; clave]</td>
      <td>Introduzca la clave (identificador único) del objeto que desea recuperar.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Team ID]</td>
      <td>Si recupera un componente del equipo o un conjunto de componentes del equipo, introduzca o asigne el ID del equipo al que están asociados el registro o registros.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Tamaño de página]</td>
      <td>Si recupera un componente del equipo o un conjunto de componentes del equipo, introduzca o asigne el número o los resultados que se devolverán por página. Predeterminado: 30.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Después]</td>
      <td>
        <p>Si recupera un componente del equipo o un conjunto de componentes del equipo, introduzca o asigne el número del resultado después del cual se comenzará a recuperar los resultados. Esto se puede combinar con el campo [!UICONTROL Page Size] para paginar los resultados.</p>
        <p>Este valor no se corresponde con los ID de objeto.</p>
        <p>Este campo no se puede usar en combinación con el campo [!UICONTROL Before].</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Before]</td>
      <td>
        <p>Si recupera un componente del equipo o un conjunto de componentes del equipo, introduzca o asigne el número del resultado antes del cual se debe iniciar la recuperación de resultados. Esto se puede combinar con el campo [!UICONTROL Page Size] para paginar los resultados.</p>
        <p>Este valor no se corresponde con los ID de objeto.</p>
        <p>Este campo no se puede usar en combinación con el campo [!UICONTROL After].</p>
      </td>
    </tr>
  </tbody>
</table>


### Otro

* [Realizar una llamada de API](#make-an-api-call)

* [Ver eventos](#watch-events)


#### [!UICONTROL Realizar una llamada API]

Este módulo de acción le permite realizar una llamada autenticada personalizada a la API de Figma sin tener que pensar en la autenticación. De este modo, puede crear una automatización del flujo de datos que no se puede lograr con los otros módulos Figma.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>Para obtener instrucciones sobre cómo conectar tu cuenta de [!DNL Figma] a Workfront Fusion, consulta <a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">Crear una conexión con Figma</a> en este artículo.</p>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p>Escriba una ruta relativa a <code>https://api.figma.com/v1/</code>.</p>
        <p>Por ejemplo: <code>[!DNL files/7179110/comments]</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Method]</td>
      <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td>
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
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>

#### [!UICONTROL Ver eventos]

Este módulo de déclencheur inicia un escenario cuando se produce uno de los siguientes eventos para un equipo específico en el espacio de equipo [!DNL Figma]:

* Actualización de archivo

* Actualización de versión de archivo

* Eliminar archivo

* Publicación de biblioteca

* Comentario de archivo

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Webhook]</td>
      <td>
        <p>Seleccione el webhook que ve el módulo.</p>
        <p>Para añadir un nuevo webhook:</p>
        <ol>
          <li>
            <p>Haga clic en <b>[!UICONTROL Agregar]</b> junto al campo [!UICONTROL Webhook].</p>
          </li>
          <li>
            <p>Introduzca un nombre para el webhook. </p>
          </li>
          <li>
            <p>Seleccione la conexión que desea utilizar para este webhook. Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Figma] a [!UICONTROL Workfront Fusion], consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a [!UICONTROL Adobe Workfront Fusion]: instrucciones básicas.</a></p>
          </li>
          <li>
            <p>Seleccione el tipo de evento que desea que vea el módulo.</p>
          </li>
          <li>
            <p>Introduzca el ID del equipo cuyos eventos desea que vea el webhook.</p>
          </li>
          <li>
            <p>Seleccione si desea que el webhook esté activo o en pausa.</p>
          </li>
          <li>
            <p>Escriba una descripción para el webhook.</p>
          </li>
          <li>
            <p>Haga clic en <b>[!UICONTROL Save]</b> para guardar el webhook y volver al módulo.</p>
          </li>
        </ol>
      </td>
    </tr>
  </tbody>
</table>
