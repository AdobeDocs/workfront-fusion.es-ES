---
title: Módulos de Adobe Content Tagger
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan Adobe Content Tagger, así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
source-git-commit: 801e8cb1a4c807aaa4275382c2d6211cf3cd6d1f
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 21%

---

# Módulos de Adobe Content Tagger

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan Adobe Content Tagger, así como conectarlo a varias aplicaciones y servicios de terceros.

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

## Crear una conexión con Adobe Content Tagger

Para crear una conexión para los módulos de Adobe Content Tagger:

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


## Módulos de Adobe Content Tagger y sus campos

Al configurar los módulos de Adobe Content Tagger, Workfront Fusion muestra los campos que se indican a continuación. Junto con estos, pueden mostrarse campos adicionales de Adobe Content Tagger, en función de factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, consulte [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Acciones

* [Colores de etiqueta](#tag-colors)
* [Palabras clave de etiqueta](#tag-keywords)
* [Etiquetar texto en una imagen](#tag-text-in-an-image)

#### Colores de etiqueta

Este módulo devuelve el porcentaje de una imagen cubierta por diferentes colores de píxel, ordenados en 40 categorías de color.


<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe Content Tagger, consulte <a href="#create-a-connection-to-adobe-content-tagger" class="MCXref xref" >Crear una conexión con Adobe Content Tagger</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre de archivo de imagen</td> 
   <td>Introduzca o asigne el nombre de archivo de la imagen para la que desea etiquetar los colores.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Datos de imagen</td> 
   <td>Introduzca o asigne los datos del archivo de la imagen para la que desea etiquetar los colores.</td> 
  </tr> 
  </tr> 
 <tr> 
   <td role="rowheader">Formato de imagen</td> 
    <td>Seleccione el tipo de imagen para la imagen para la que desea etiquetar los colores.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">Número de colores</td> 
    <td>Introduzca o asigne el número de colores que desea devolver. Para devolver todos los resultados, escriba 0.</p></td> 
  </tr> 
 <tr> 
   <td role="rowheader">Cobertura mínima</td> 
   <td>Introduzca o asigne la cobertura mínima para la que desea etiquetar los colores. Solo se devolverán los colores que cubran al menos esta cantidad de la imagen. Un valor de 1 es el 100 % de la imagen y un valor de 0,5 representa el 50 % de la imagen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Redimensionar imagen antes de la extracción.</td> 
   <td>Seleccione Sí para cambiar el tamaño de la imagen a 320 x 320 antes de extraer los colores. Seleccione No para extraer los colores de la imagen a tamaño completo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Habilitar máscara de primer plano/fondo</td> 
   <td>Seleccione Sí si desea incluir colores por separado para la imagen general, el primer plano y el fondo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Recuperar tonos</td> 
   <td>Seleccione Sí si desea recuperar datos sobre los tonos cálidos, neutros y fríos, además de los colores.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Número máximo de colores devueltos</td> 
   <td>Introduzca o asigne el número máximo de colores que devuelve el módulo para un ciclo de ejecución.</td> 
  </tr> 
 </tbody> 
</table>



#### Palabras clave de etiqueta

Este módulo extrae palabras clave o frases clave que describen mejor el asunto del documento.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe Content Tagger, consulte <a href="#create-a-connection-to-adobe-content-tagger" class="MCXref xref" >Crear una conexión con Adobe Content Tagger</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre de archivo de documento</td> 
   <td>Escriba o asigne el nombre de archivo del documento del que desea extraer palabras clave.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Datos de imagen</td> 
   <td>Introduzca o asigne los datos de archivo del documento del que desea extraer palabras clave.</td> 
  </tr> 
  </tr> 
 <tr> 
   <td role="rowheader">Formato de imagen</td> 
    <td>Seleccione el formato del documento del que desea extraer palabras clave.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de aplicación</td> 
   <td>Introduzca o asigne el ID de aplicación del documento.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Número de frases clave</td> 
   <td>Introduzca o asigne el número de frases clave que desea que devuelva el módulo. Para devolver todos los resultados, escriba 0.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Relevancia mínima</td> 
   <td>Introduzca o asigne el umbral de puntuación por debajo del cual no se devolverán los resultados.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Longitud mínima de la frase clave (palabras)</td> 
   <td>Introduzca o asigne el número mínimo de palabras requeridas en frases clave.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Longitud máxima de la frase clave (palabras)</td> 
   <td>Introduzca o asigne el número máximo de palabras requeridas en frases clave.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Profundidad de la unidad semántica</td> 
   <td>Seleccione la profundidad a la que desea que vayan las respuestas jerárquicas.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipos de entidad</td> 
   <td>Para cada tipo de entidad al que desee restringir frases clave, haga clic en <b>Agregar elemento</b> e introduzca la información del tipo de entidad.</td> 
  </tr> 
 </tbody> 
</table>

#### Etiquetar texto en una imagen

Este módulo indica si hay texto en una imagen y devuelve el texto, si lo hay.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Adobe Content Tagger, consulte <a href="#create-a-connection-to-adobe-content-tagger" class="MCXref xref" >Crear una conexión con Adobe Content Tagger</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre de archivo de imagen</td> 
   <td>Escriba o asigne el nombre de archivo del documento del que desea extraer texto.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Datos de imagen</td> 
   <td>Escriba o asigne los datos de archivo del documento del que desea extraer texto.</td> 
  </tr> 
  </tr> 
 <tr> 
   <td role="rowheader">Formato de imagen</td> 
    <td>Seleccione el formato del documento del que desea extraer el texto.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">Filtrar con diccionario</td> 
   <td>Seleccione si desea devolver solo las palabras que se encuentran en el diccionario de inglés.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Probabilidad mínima</td> 
   <td>Introduzca o asigne la probabilidad mínima, donde el módulo solo devolverá palabras reconocidas con al menos esta probabilidad. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Relevancia mínima</td> 
   <td>Introduzca el porcentaje mínimo de la imagen que debe cubrir el texto devuelto. La relevancia se calcula como la fracción del área del cuadro delimitador del texto extraído en comparación con la imagen completa. 0,01 se traduciría en un texto que ocupe al menos el 1 % de la imagen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Número máximo de resultados devueltos</td> 
   <td>Introduzca o asigne el número máximo de resultados que devolverá el módulo para un ciclo de ejecución.</td> 
  </tr> 
 </tbody> 
</table>
