---
title: Analizador de texto
description: Puede utilizar la herramienta Text parser para analizar el texto y utilizarlo en otros módulos de escenarios de Adobe Workfront Fusion. El analizador de texto no requiere una conexión.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 885d714e-fc09-41a2-89dc-ebe29a355e43
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1326'
ht-degree: 81%

---

# [!UICONTROL Analizador de texto]

Puede utilizar la [!UICONTROL herramienta de análisis de texto] para analizar texto y utilizarlo en otros módulos de escenarios de Adobe Workfront Fusion. El [!UICONTROL Text parser] no requiere una conexión.

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
   <p>No se requiere licencia de Workfront Fusion</p>
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

## Información de API del analizador de texto

El conector del analizador de texto utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 2</td> 
  </tr>
 </tbody> 
 </table>

## [!UICONTROL Text parser] módulos y sus campos

Al configurar los módulos de [!UICONTROL Text parser], Adobe Workfront Fusion muestra los campos que se indican a continuación. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Transformadores

* [[!UICONTROL Get Elements from HTML]](#get-elements-from-html)
* [[!UICONTROL Get Elements from text]](#get-elements-from-text)
* [[!UICONTROL HTML to Text]](#html-to-text)
* [[!UICONTROL Match Pattern]](#match-pattern)
* [[!UICONTROL Replace]](#replace)

#### [!UICONTROL Get Elements from HTML]

Recupera los elementos deseados del código del HTML.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Continue the execution of the route even if the module finds no matches]</td> 
   <td> <p>Active esta opción para asegurarse de que el módulo no detenga el escenario si no devuelve resultados.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Element type]</td> 
   <td> <p> Seleccione el tipo de elemento que desea recuperar del código del HTML. </p> 
    <ul> 
     <li>[!UICONTROL Image]</li> 
     <li>[!UICONTROL Link]</li> 
     <li>[!UICONTROL iFrame element(s)]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL HTML] </td> 
   <td> <p>Introduzca o asigne el código de HTML desde el que desea recuperar los tipos de elementos especificados.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Elements from text]

Analiza elementos de texto en función del patrón determinado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Input text]</td> 
   <td> <p>Introduzca o asigne el texto que desea analizar.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Pattern]</td> 
   <td> <p>Seleccione el patrón que refleje los elementos del texto que desee analizar.</p> <p>Para introducir una expresión regular personalizada, seleccione Personalizado en la lista y, a continuación, introduzca la expresión personalizada en el campo Regex personalizada.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Ignore Duplicate Occurrences]</td> 
   <td> <p>Marque esta casilla para ignorar las repeticiones de un elemento de texto.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL De HTML a texto]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL HTML] </td> 
   <td> <p>Introduzca el código de HTML que desea convertir en texto sin formato.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Line break] </td> 
   <td> <p>Seleccione el tipo de nueva línea (salto de línea).</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Uppercase headings]</p> </td> 
   <td> <p>Active esta opción para convertir el texto incluido en las etiquetas de encabezado (como &lt;h2&gt; &lt;/h2&gt;) en texto en mayúsculas.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Patrón de coincidencia]

El módulo [!UICONTROL Patrón de coincidencia] le permite buscar y extraer elementos de cadena que coincidan con un patrón de búsqueda de un texto determinado. Este módulo utiliza expresiones regulares (también conocidas como regex o regexp).

Una expresión regular es una secuencia de caracteres en la que cada carácter es un metacarácter, que tiene un significado especial, o un carácter regular que tiene un significado literal. Estos caracteres y metacaracteres identifican un patrón que se puede utilizar para buscar texto. Por ejemplo, si desea buscar nombres, puede configurar una expresión regular para buscar un patrón que consista en dos palabras consecutivas que comiencen con mayúsculas. Las expresiones regulares son una potente herramienta para buscar y manipular texto.

El análisis de las expresiones regulares excede el ámbito de este artículo. Recomendamos los siguientes recursos:

* Para obtener la lista completa de metacaracteres, consulte [Expresiones regulares](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) en los documentos web de MDN.
* Para ver un tutorial sobre cómo crear expresiones regulares, recomendamos [RegexOne](https://regexone.com/).
* Para experimentar con expresiones regulares, recomendamos el sitio web [Expresiones regulares 101](https://regex101.com/). Seleccione ECMAScript (JavaScript) FLAVOR en el panel izquierdo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Pattern] </td> 
   <td> <p>Introduzca el patrón de expresión regular. </p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Ejemplo: </b></span></span> <code>[+-]?(\d+(\.\d+)?|\.\d+)([eE][+-]?\d+)?</code> extrae todos los números del texto proporcionado.</p> <p>Nota:  <p>El patrón debe contener al menos un grupo de captura entre paréntesis <code>()</code>. Si el patrón no contiene ningún grupo de captura, el paquete de salida está vacío.</p> </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Global match]</td> 
   <td> <p>Active esta opción para recuperar todas las coincidencias del texto. Cada coincidencia se genera en un paquete independiente. Si esta opción está desactivada, el módulo recupera únicamente la primera entrada.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Case sensitive]</td> 
   <td> <p> Active esta opción para que este módulo distinga entre mayúsculas y minúsculas.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Multiline] </td> 
   <td> <p>Habilite esta opción para asegurarse de que los metacaracteres inicial y final (<code>^</code> y <code>$</code>) coinciden con el principio o final de cada línea, no sólo con el principio o el final de toda la cadena de entrada.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Singleline]</td> 
   <td>Habilite esta opción para asegurarse de que el punto (.) coincida con los caracteres de línea nueva (<code>\n</code>).</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Continue the execution of the route even if the module returns no results]</td> 
   <td> <p>Active esta opción para asegurarse de que el módulo no detenga el escenario si no devuelve resultados.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Text] </td> 
   <td> <p>Introduzca o asigne el texto que desea que coincida con el patrón.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Reemplazar]

Busca un valor o una expresión regular especificados en el texto introducido y reemplaza el resultado por el nuevo valor.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Pattern] </td> 
   <td> <p>Introduzca el término de búsqueda. También puede utilizar una expresión regular. Para obtener más información sobre la expresión regular, consulte el módulo <a href="#match-pattern" class="MCXref xref">[!UICONTROL Match Pattern]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL New value]</td> 
   <td> <p> Introduzca el valor que desea reemplazar con el término de búsqueda.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Global match]</td> 
   <td> <p>Active esta opción para recuperar todas las coincidencias del texto. Cada coincidencia se genera en un paquete independiente. Si esta opción está desactivada, el módulo recupera únicamente la primera entrada.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Case sensitive]</td> 
   <td> <p> Active esta opción para que este módulo distinga entre mayúsculas y minúsculas.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Multiline] </td> 
   <td> <p>Habilite esta opción para asegurarse de que los metacaracteres inicial y final (<code>^</code> y <code>$</code>) coinciden con el principio o final de cada línea, no sólo con el principio o el final de toda la cadena de entrada.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Singleline]</td> 
   <td>Habilite esta opción para asegurarse de que el punto (.) coincida con los caracteres de línea nueva (<code>\n</code>).</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Text] </td> 
   <td> <p>Introduzca el texto que desea buscar.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Extracción de datos

La extracción de datos, a veces denominada extracción web o recolección web, es el proceso de recopilar datos de sitios web y almacenarlos en la base de datos u hojas de cálculo locales. Si desea obtener datos de un sitio web y no está familiarizado con las expresiones regulares, puede utilizar una herramienta de extracción de datos.

Si la herramienta de extracción de datos proporciona una API REST, puede conectarse a ella a través de nuestros módulos [[!UICONTROL HTTP] universales](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#universal-connectors) y [Webhooks](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md).

## Solución de problemas del analizador de texto

Utilice esta información si no consigue que el analizador de texto genere ninguna salida.

>[!BEGINSHADEBOX]

Ejemplo:

El módulo debe analizar el tipo de archivo del documento de archivo &quot;filename.docx&quot; y la extensión del nombre de archivo varía de DOCX a PDF o CSV.

La expresión que puede elegir usar en este caso es [!DNL \..+]

Esta expresión regular normalmente daría como resultado una coincidencia completa.

Sin embargo, la implementación de esta expresión en el analizador de texto no da como resultado una coincidencia:

![No hay coincidencia](/help/workfront-fusion/references/apps-and-modules/assets/text-parser-you-dont-get-a-match-350x365.png)

La razón es que la “i” muestra solo el número de coincidencias por coincidencia, así que en este caso tenemos 2 coincidencias, por lo que después de la “i” hay un valor numérico 1 y 2. El caso de uso es que, si alguna vez necesita hacer coincidir o transferir datos a través de un filtro, solo el segundo valor coincidente puede especificar qué valor está representado mediante el valor numérico.

![Coincidencia](/help/workfront-fusion/references/apps-and-modules/assets/text-parser-matches-350x355.png)

Para poder obtener los valores de coincidencia necesarios para añadir corchetes a la parte que desea analizar (por ejemplo, para extraer de “filename.docx” solo “docx”), los corchetes deben aplicarse en \, de acuerdo con la expresión regex que se utiliza en este escenario de caso.(.+)

Esto captura el DOCX, lo coloca en un grupo y deja el “.” fuera.

![Obtener coincidencias](/help/workfront-fusion/references/apps-and-modules/assets/text-parser-get-matches-350x592.png)

En la salida que se muestra en la imagen siguiente, el grupo de captura coincidirá con cualquier carácter (excepto para los terminadores de línea).

![Salida](/help/workfront-fusion/references/apps-and-modules/assets/text-parser-output-350x389.png)

Otra solución que también incorpora regex es utilizar la función de reemplazo

`{{replace("abcdefghijklmno pqr stuvw xyz.docx"; "/.\./"; ".")}}`

A continuación, reemplace `abcdefghijklmno pqr stuvw xyz.docx` por la variable de nombre de archivo real.

>[!ENDSHADEBOX]
