---
title: Módulos de Adobe Express
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan Adobe Express.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
source-git-commit: 801e8cb1a4c807aaa4275382c2d6211cf3cd6d1f
workflow-type: tm+mt
source-wordcount: '1374'
ht-degree: 18%

---

# Módulos de Adobe Express

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan Adobe Express, así como conectarlos a varias aplicaciones y servicios de terceros.

Si necesita instrucciones sobre cómo crear un escenario, vea los artículos en [Crear un escenario: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, consulte los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Paquete de Adobe Workfront</td> 
   <td> <p>Cualquier paquete del flujo de trabajo de Adobe Workfront y cualquier paquete de integración y automatización de Adobe Workfront</p><p>Workfront Ultimate</p><p>Paquetes Workfront Prime y Select, con una compra adicional de Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencias de Adobe Workfront</td> 
   <td> <p>Estándar</p><p>Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion</td> 
   <td>
   <p>Basado en operaciones: disponible para organizaciones con licencias basadas en operaciones</p>
   <p>Basado en conector (heredado): Workfront Fusion for Work Automation and Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Antes de poder utilizar el conector de Adobe Express, debe asegurarse de que se cumplen los siguientes requisitos previos:

* Debe tener una cuenta de Adobe Express activa.

## Creación de una conexión con Adobe Express

Para crear una conexión para los módulos de Adobe Express:

1. En cualquier módulo, haga clic en **[!UICONTROL Agregar]** junto al cuadro Conexión.

1. Rellene los campos siguientes:

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">Nombre de la conexión</td>
        <td>
          <p>Introduzca un nombre para esta conexión.</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">Entorno</td>
        <td>Seleccione si desea conectarse a un entorno de producción o de no producción.</td>
        </tr>
        <tr>
        <td role="rowheader">Tipo</td>
        <td>Seleccione si desea conectarse a una cuenta de servicio o a una personal.</td>
        </tr>
        <tr>
        <td role="rowheader">ID de cliente</td>
        <td>Introduzca su ID de cliente de Adobe. Esto se puede encontrar en la sección Detalles de credenciales de Adobe Developer Console.</td>
        </tr>
        <tr>
        <td role="rowheader">Secreto de cliente</td>
        <td>Escriba el Secreto de cliente de Adobe. Esto se puede encontrar en la sección Detalles de credenciales de Adobe Developer Console.</td>
        </tr>
      </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.


## Módulos Adobe Express y sus campos

Al configurar los módulos de Adobe Express, Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden mostrarse campos de Adobe Express adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, consulte [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Acciones

#### Exportar una representación

Este módulo exporta un documento al formato JPG o PNG. Puede proporcionar direcciones URL prefirmadas para las representaciones de página, que son válidas durante cuatro horas.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe Express, consulte <a href="#create-a-connection-to-adobe-express" class="MCXref xref" >Crear una conexión con Adobe Express</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Documento</td> 
   <td>Seleccione el documento para el que desea exportar una representación.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Números de página</td> 
   <td>Introduzca o asigne los números de página que desee incluir en la representación. Cadena separada por comas de los números de página para los que se realiza la solicitud de representación. Por ejemplo, "1,2,3". También se pueden especificar intervalos de páginas. Por ejemplo, 1-3 incluye las páginas 1, 2 y 3. Otro ejemplo es 1,3-5, que incluye las páginas 1, 3, 4 y 5. "1-" se puede usar para especificar todas las páginas, mientras que "5-" indica de la página 5 a la última página. Si no se proporciona, la primera página se considera de forma predeterminada. Los números de página comienzan desde 1.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Tipo de representación</td> 
   <td>Seleccione el tipo de representación que desea exportar: imagen, vídeo o PDF</td> 
  </tr>
  <tr> 
   <td role="rowheader">Formato</td> 
   <td>Seleccione el formato de archivo de la representación.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Tipo de PDF</td> 
   <td>Si va a exportar una PDF, seleccione si desea exportar una PDF estándar o de impresión.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Tamaño</td> 
   <td>Si va a exportar una imagen o un vídeo, introduzca o asigne el tamaño, en píxeles, del lado más largo. La relación de aspecto se mantiene. Para la imagen, el tamaño mínimo admitido es de 1 px y el tamaño máximo admitido es de 8192 px. Si no se proporciona, se tiene en cuenta el tamaño predeterminado de la página.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Descarga de archivos de PDF individuales</td> 
   <td>Si va a exportar un PDF, seleccione si las páginas se descargan como archivos de PDF independientes. Si el valor es True, cada página se descarga como su propio archivo PDF. Si es false, todas las páginas se combinan en un solo archivo PDF.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Configuración</td> 
   <td>Si va a exportar un PDF, seleccione si desea que el PDF tenga la configuración estándar o de impresión.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Fase de accesibilidad</td> 
   <td>Si va a exportar un PDF estándar, seleccione si desea incluir las etiquetas de accesibilidad en el PDF.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Sangrado</td> 
   <td>Si va a exportar un PDF de impresión, seleccione si desea incluir la configuración de impresión a sangre en la exportación</td> 
  </tr>
  <tr> 
   <td role="rowheader">Configuración de sangrado &gt; Cantidad</td> 
   <td>Introduzca la cantidad de margen de sangrado.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Ajustes de sangrado &gt; Unidades</td> 
   <td>Seleccione si la cantidad se refiere a pulgadas o milímetros.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Recortar</td> 
   <td>Si va a exportar un PDF de impresión, seleccione si desea incluir la configuración de recorte en la exportación</td> 
  </tr>
  <tr> 
   <td role="rowheader">Ajustes de recorte &gt; Importe</td> 
   <td>Introduzca la cantidad de margen de recorte.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Ajustes de recorte &gt; Unidades</td> 
   <td>Seleccione si la cantidad se refiere a pulgadas o milímetros.</td> 
  </tr>
 </tbody> 
</table>

#### Generar variaciones

Este módulo crea una variación del documento basada en los parámetros de entrada proporcionados. Después del procesamiento, almacena temporalmente el documento generado y lo pone a disposición del usuario en una carpeta designada. El documento permanece accesible durante 30 días, después de lo cual el sistema lo elimina automáticamente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe Express, consulte <a href="#create-a-connection-to-adobe-express" class="MCXref xref" >Crear una conexión con Adobe Express</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Documento</td> 
   <td>Seleccione el documento para el que desea generar variaciones.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Números de página</td> 
   <td>Introduzca o asigne los números de página que desee incluir en la representación. Cadena separada por comas de los números de página para los que se realiza la solicitud de variación. Por ejemplo, "1,2,3". También se pueden especificar intervalos de páginas. Por ejemplo, 1-3 incluye las páginas 1, 2 y 3. Otro ejemplo es 1,3-5, que incluye las páginas 1, 3, 4 y 5. "1-" se puede usar para especificar todas las páginas, mientras que "5-" indica de la página 5 a la última página. Si no se proporciona, la primera página se considera de forma predeterminada. Los números de página comienzan desde 1.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Nombre de documento preferido.</td> 
   <td>Escriba o asigne un nombre para el nuevo documento. Si no proporciona un nombre o el nombre ya está en uso, el sistema generará un nombre único.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Identificador de proyecto</td> 
   <td>Introduzca el ID del proyecto donde se almacenarán las variaciones.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Otros campos</td> 
   <td>Introduzca valores para otros campos. Los campos disponibles dependen del documento seleccionado.</td> 
  </tr>
 </tbody> 
</table>


### Búsquedas

#### Recuperar documentos etiquetados

Este módulo recupera una lista de documentos etiquetados, junto con metadatos relevantes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe Express, consulte <a href="#create-a-connection-to-adobe-express" class="MCXref xref" >Crear una conexión con Adobe Express</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Índice de inicio</td> 
   <td>Introduzca o asigne el índice de inicio de la paginación. Utilícelo cuando haya recuperado otra lista de resultados y desee continuar con esa lista. El índice predeterminado es 0.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Número máximo de resultados devueltos</td> 
   <td>Introduzca o asigne el número máximo de resultados que desea que devuelva el módulo para cada ciclo de ejecución.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Ordenar por</td> 
   <td>Seleccione el atributo por el que desea ordenar los resultados.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Dirección</td> 
   <td>Seleccione si desea ordenar los resultados de forma ascendente o descendente.</td> 
  </tr>
 </tbody> 
</table>

#### Recuperar detalles del documento

Este módulo recupera detalles de las páginas y los elementos etiquetados dentro de un documento especificado. Devuelve una lista paginada de las páginas del documento y los metadatos de cada página. Si el documento tiene elementos etiquetados, la API incluye sus respectivos detalles, como tamaño y posición. Si el documento no tiene elementos etiquetados, devuelve una matriz vacía. La respuesta incluye información de paginación para ayudar a los usuarios a navegar por las páginas del documento. Se puede devolver un máximo de 10 páginas en 1 ciclo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe Express, consulte <a href="#create-a-connection-to-adobe-express" class="MCXref xref" >Crear una conexión con Adobe Express</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Documento</td> 
   <td>Seleccione el documento para el que desea devolver páginas y detalles.</td> 
  </tr>
  <tr> 
   <td role="rowheader">Página de inicio</td> 
   <td>Introduzca o asigne el número de página de la primera página desde la que se recuperarán los detalles.</td>

#### Recuperación del estado de un trabajo

Este módulo recupera el estado de un trabajo mediante su ID de trabajo. Según el tipo de trabajo, la respuesta puede incluir detalles específicos del trabajo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe Express, consulte <a href="#create-a-connection-to-adobe-express" class="MCXref xref" >Crear una conexión con Adobe Express</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de trabajo</td> 
   <td>Introduzca o asigne el ID del trabajo para el que desea recuperar detalles.</td> 
  </tr>

