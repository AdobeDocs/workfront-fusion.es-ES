---
title: Herramientas
description: La sección  [!DNL Adobe Workfront Fusion Tools] incluye varios módulos útiles que pueden mejorar su escenario.
author: Becky
feature: Workfront Fusion
exl-id: d9425f5b-4f4a-42da-9aca-1c1783be5fa7
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '2286'
ht-degree: 86%

---

# [!UICONTROL Herramientas]

La sección [!DNL Adobe Workfront Fusion Tools] incluye varios módulos útiles que pueden mejorar su escenario.

Los módulos de [!UICONTROL Tools] están disponibles en la lista de aplicaciones o en el icono de [!UICONTROL Tools] ![Tools icon](/help/workfront-fusion/references/apps-and-modules/assets/tools-icon-small.png) en la parte inferior de la pantalla.

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
   <p>Actual: Su organización debe adquirir Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de [!DNL Adobe Workfront Fusion], consulte Licencias de [[!DNL Adobe Workfront Fusion] ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## [!UICONTROL Herramientas] y sus campos

* [Activadores](#triggers)
* [Acciones](#actions)
* [Agregadores](#aggregators)
* [Transformadores](#transformers)

### Activadores

#### [!UICONTROL Activador básico]

Este módulo le permite crear un activador personalizado y definir sus paquetes de entrada.

Puede usar este módulo, por ejemplo, para contactos o cualquier otra lista programada para enviarse a una dirección de correo electrónico especificada (como los módulos [!UICONTROL Correo electrónico] >[!UICONTROL Enviar un correo electrónico] o [!DNL Gmail] >[!UICONTROL Enviar un correo electrónico]), o como un simple recordatorio que se activará cuando quiera.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bundle]</td> 
   <td> <p>Cree paquetes personalizados añadiendo elementos de matriz. Para cada elemento que desee agregar al paquete, haga clic en <b>Agregar elemento</b> e introduzca el nombre y el valor del elemento.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Acciones

* [[!UICONTROL Obtener múltiples variables]](#get-multiple-variables)
* [[!UICONTROL Obtener variable]](#get-variable)
* [[!UICONTROL Función de incremento]](#increment-function)
* [[!UICONTROL Establecer varias variables]](#set-multiple-variables)
* [[!UICONTROL Establecer variable]](#set-variable)
* [[!UICONTROL Suspensión]](#sleep)

#### [!UICONTROL Obtener múltiples variables]

Este módulo recupera valores creados anteriormente por el módulo [!UICONTROL Establecer variable] o [!UICONTROL Establecer múltiples variables].

Este módulo puede leer variables que se establecieron en cualquier parte del escenario, incluso si la variable se estableció en una ruta diferente a la ubicación del módulo [!UICONTROL Obtener múltiples variables]. El único requisito es que el módulo [!UICONTROL Herramientas] > [!UICONTROL Establecer variable] o [!UICONTROL Herramientas] > [!UICONTROL Establecer múltiples variables] se ejecute antes que el módulo [!UICONTROL Herramientas] > [!UICONTROL Obtener múltiples variables].  Para obtener más información sobre el orden en que se ejecutan los módulos, vea [Agregar un módulo de enrutador y configurar rutas](/help/workfront-fusion/create-scenarios/add-modules/router-module.md).

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Variables]</td>
        <td>Para cada variable que desee que obtenga el módulo, haga clic en <b>Agregar elemento</b> e introduzca el nombre de la variable.</td>
    </tr>
</table>

>[!BEGINSHADEBOX]

**Ejemplos:** los siguientes son posibles usos de los módulos [!UICONTROL Establecer]/[!UICONTROL Obtener (múltiples) variables]:

* Para almacenar un valor calculado para su uso posterior, incluso en una ruta diferente. Esto resulta útil en casos en los que el valor se utiliza en varios módulos y la fórmula para calcularlo es demasiado compleja.
* Para depurar una fórmula. Si una fórmula utilizada en un módulo no proporciona aparentemente un resultado correcto, copie la fórmula y péguela en un módulo [!UICONTROL Establecer variable] que inserte antes del módulo correspondiente. Desconecte los módulos después del módulo [!UICONTROL Establecer variable] y ejecute el escenario. Compruebe el resultado del módulo [!UICONTROL Establecer variable], ajuste o simplifique la fórmula, ejecute de nuevo el escenario y continúe haciéndolo hasta que se haya resuelto el problema.

>[!ENDSHADEBOX]


#### [!UICONTROL Obtener variable]

Este módulo recupera un valor creado anteriormente por el módulo [!UICONTROL Establecer variable] o [!UICONTROL Establecer múltiples variables].

Este módulo puede leer variables que se establecieron en cualquier parte del escenario, incluso si la variable se estableció en una ruta diferente a donde se encuentra el módulo [!UICONTROL Obtener variable]. El único requisito es que el módulo [!UICONTROL Herramientas] > [!UICONTROL Establecer variable] o [!UICONTROL Herramientas] > [!UICONTROL Establecer múltiples variables] se ejecute antes que el módulo [!UICONTROL Herramientas] > [!UICONTROL Obtener variable].  Para obtener más información sobre el orden en que se ejecutan los módulos, vea [Agregar un módulo de enrutador y configurar rutas](/help/workfront-fusion/create-scenarios/add-modules/router-module.md).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Variable name]</td> 
   <td> <p>Asigne el nombre de la variable que desea que obtenga el módulo.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Función de incremento]

Este módulo devuelve un valor incrementado en 1 después de cada ciclo o cada escenario ejecutado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reset a value]</td> 
   <td> <p>Seleccione cuando desee que el módulo restablezca el valor. Es entonces cuando desea que el valor comience de nuevo en el primer valor.</p> 
    <ul> 
     <li>[!UICONTROL After one cycle]</li> 
     <li>[!UICONTROL After one scenario run]</li> 
     <li>[!UICONTROL Never]</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**Ejemplo:**

Este módulo se puede utilizar para implementar una asignación &quot;round robin&quot; de tareas, posibles clientes, correos electrónicos, etc., a los usuarios de un grupo. El algoritmo elige a los usuarios asignados de un grupo en un orden racional, que generalmente va de la parte superior a la parte inferior de una lista. Cuando el algoritmo llega al final de la lista, le asigna la siguiente asignación al usuario en la parte superior de la lista y continúa realizando asignaciones en la lista.

El siguiente escenario envía un correo electrónico al primer destinatario después de ejecutar cada escenario impar y al segundo destinatario después de ejecutar cada escenario par.

![Ejemplo de correo electrónico](/help/workfront-fusion/references/apps-and-modules/assets/example-email.png)

Para crear este escenario, haga lo siguiente:

1. Establezca el campo **[!UICONTROL Restablecer un valor]** del módulo en Nunca.
1. Defina la ruta para los valores impares. Establezca el filtro para esta ruta mediante la función de coincidencia de módulo igual a `1`:

   ![Números impares](/help/workfront-fusion/references/apps-and-modules/assets/odd.png)

**Nota**: no olvide cambiar el operador [!UICONTROL Igual a] del operador [!UICONTROL Texto] predeterminado al operador [!UICONTROL Numérico].

1. Establezca la ruta para los valores pares utilizando la función de coincidencia de módulo igual a `0`:

La función de incremento añade uno cada vez que se ejecuta el escenario. Los filtros comprueban el incremento y actúan en su valor, lo que garantiza que los correos electrónicos se distribuyan de manera uniforme.

>[!ENDSHADEBOX]

#### [!UICONTROL Establecer múltiples variables]

Este módulo crea variables que otros módulos pueden asignar en la ruta. La variable también se puede asignar a los módulos [!UICONTROL Obtener variable] u [!UICONTROL Obtener varias variables] para cualquier ruta del escenario.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Variables]</td> 
   <td>Para cada variable que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca el nombre y el valor de la variable.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Variable lifetime] </td> 
   <td> <p>Seleccione el tiempo que desea que las variables sigan siendo válidas (mantengan el mismo valor).</p> 
    <ul> 
     <li><strong>[!UICONTROL One cycle]</strong>: la variable es válida durante un ciclo. Esto resulta útil cuando se reciben varios webhooks en una ejecución de escenario, porque más webhooks crean más ciclos. </li> 
     <li><strong>[!UICONTROL One execution]</strong>: la variable es válida para una ejecución de escenario. Una ejecución puede contener uno o más ciclos.</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Establecer variable]

Este módulo crea una variable que otros módulos pueden asignar en la ruta. La variable también se puede asignar a los módulos [!UICONTROL Obtener variable] u [!UICONTROL Obtener varias variables] para cualquier ruta del escenario.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Variable name] </td> 
   <td>Introduzca el nombre de la variable. Este nombre se muestra al asignar la variable en otros módulos. </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Variable lifetime] </td> 
   <td> <p>Seleccione el tiempo que desea que las variables sigan siendo válidas (mantengan el mismo valor).</p> 
    <ul> 
     <li><strong>[!UICONTROL One cycle]</strong>: la variable es válida durante un ciclo. Resulta útil cuando se reciben varios webhooks en una ejecución de escenario (más webhooks = más ciclos). </li> 
     <li><strong>[!UICONTROL One execution]</strong>: la variable es válida para una ejecución de escenario. Una ejecución puede contener uno o más ciclos.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Variable value] </td> 
   <td>Introduzca o asigne el valor de la variable. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Suspensión]

Este módulo le permite retrasar el flujo del escenario hasta 300 segundos (5 minutos).

Esta función puede resultar útil, por ejemplo, si desea reducir la carga del servidor de servicio de [!DNL target] o para imitar el comportamiento humano al enviar SMS o correos electrónicos masivos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Delay]</p> </td> 
   <td> <p>Introduzca el número de segundos durante los que se detendrá el escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!TIP]
>
>Si desea pausar el flujo durante períodos de tiempo más largos, le recomendamos que divida el escenario en dos escenarios:
>
>* El primer escenario contendría la parte antes de la pausa.
>* El segundo escenario contendría la parte posterior.
>
>El primer escenario acabaría almacenando toda la información necesaria en un almacén de datos junto con la marca de tiempo actual. El segundo escenario comprobaría periódicamente si hay registros con una marca de tiempo anterior al retraso previsto en el almacén de datos, recuperaría los registros, finalizaría el procesamiento de los datos y eliminaría los registros del almacén de datos.
>
><!--For more information on data stores, see [Data Stores in [!DNL Adobe Workfront Fusion]]().-->
>
>Para obtener más información sobre módulos de almacenes de datos específicos, consulte [[!UICONTROL Módulos de almacenes de datos]](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/data-store-modules.md).

### Agregadores

* [[!UICONTROL Agregador numérico]](#numeric-aggregator)
* [[!UICONTROL Agregador de tablas]](#table-aggregator)
* [[!UICONTROL Agregador de texto]](#text-aggregator)

#### [!UICONTROL Agregador numérico]

Este módulo le permite recuperar valores numéricos y, a continuación, aplicar una de las funciones seleccionadas (SUM, AVG, COUNT, MAX, MIN) y devolver el resultado en un paquete.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Source module]</p> </td> 
   <td> <p>Seleccione el módulo desde el que desea agregar los campos.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Aggregate function]</p> </td> 
   <td> <p>Seleccione la función que desee utilizar para agregar los valores.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Group by]</p> </td> 
   <td> <p>Defina una expresión por la cual desea agrupar la salida agregada. Esta expresión puede contener uno o varios elementos asignados. Los datos añadidos se separan en grupos utilizando el valor de esta expresión. Cada grupo genera como un paquete independiente con una clave (la expresión evaluada) y un valor (el valor agregado). Puede utilizar la clave como filtro en módulos posteriores.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Stop processing after an empty aggregation]</td> 
   <td>Active esta opción para detener el escenario cuando no haya resultados.</td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Value]</p> </td> 
   <td> <p>Introduzca o asigne el valor que desea agregar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Agregador de tablas]

Este módulo combina los valores de los campos seleccionados de los paquetes recibidos en un solo paquete utilizando un separador de columnas y filas especificado (que le permite crear una tabla).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Source module]</p> </td> 
   <td> <p>Seleccione el módulo desde el que desea agregar los campos.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Aggregated fields]</td> 
   <td> <p> Seleccione los campos del módulo seleccionado anteriormente que contienen los valores que desea agregar al paquete.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Column separator]</p> </td> 
   <td> <p>Seleccione o introduzca el tipo de separador que separará las columnas de valor de campo en el paquete resultante. Si selecciona [!UICONTROL Other], introduzca el carácter que desea utilizar para separar valores en el campo separador.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Row separator]</p> </td> 
   <td> <p>Seleccione o introduzca el tipo de separador que separará las filas de valor de campo en el paquete resultante. Si selecciona [!UICONTROL Other], introduzca el carácter que desea utilizar para separar valores en el campo separador.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Group by]</p> </td> 
   <td> <p>Defina una expresión por la cual desea agrupar la salida agregada. Esta expresión puede contener uno o varios elementos asignados. Los datos agregados se separarán entonces en grupos utilizando el valor de esta expresión. Cada grupo genera como un paquete independiente con una clave (la expresión evaluada) y un valor (el valor agregado). Puede utilizar la clave como filtro en módulos posteriores.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Stop processing after an empty aggregation]</td> 
   <td>Seleccione esta opción para detener el escenario cuando no haya resultados.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Agregador de texto]

Este módulo combina los valores de los campos seleccionados de los paquetes recibidos en un solo paquete.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Source module]</p> </td> 
   <td> <p>Seleccione el módulo desde el que desea agregar los campos.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Row separator]</p> </td> 
   <td> <p>Seleccione o introduzca el tipo de separador que separará las filas de valor de campo en el paquete resultante. Si selecciona [!UICONTROL Other], introduzca el carácter que desea utilizar para separar valores en el campo separador.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Group by]</p> </td> 
   <td> <p>Defina una expresión que contenga uno o varios elementos asignados. Los datos agregados se separan en Grupos con el mismo valor de expresión. Cada grupo genera como un paquete independiente que contiene una clave con la expresión evaluada y el texto agregado. Al hacerlo, puede utilizar la clave como filtro en módulos posteriores.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Stop processing after an empty aggregation]</td> 
   <td>Seleccione esta opción para detener el escenario cuando no haya resultados.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Text]</td> 
   <td> <p> Introduzca o asigne el texto que desea que agregue el módulo.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**Ejemplo:** puede usar el agregador de texto para insertar más valores (por ejemplo, nombres de clientes o notas) en un solo paquete y enviar un correo electrónico que contenga todos los valores del cuerpo del correo electrónico o del asunto del correo electrónico.

>[!ENDSHADEBOX]

### Transformadores

* [[!UICONTROL Escribir una cadena]](#compose-a-string)
* [[!UICONTROL Convertir la codificación del texto]](#convert-the-encoding-of-the-text)
* [[!UICONTROL Conmutador]](#switch)

#### [!UICONTROL Escribir una cadena]

Convierte cualquier valor en un tipo de datos de cadena (texto). Esto facilita la asignación al asignar, por ejemplo, datos binarios.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text]</td> 
   <td> <p>Introduzca o asigne los datos que desea convertir en texto.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Convertir la codificación del texto]

Convierte el texto de entrada (o los datos binarios) a la codificación seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Input data]</p> </td> 
   <td> <p>Introduzca o asigne el contenido que desea convertir.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Input data codepage]</td> 
   <td> <p>Seleccione el tipo de codificación de los datos de entrada. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Output data codepage]</p> </td> 
   <td> <p>Seleccione el tipo de codificación de los datos de destino (salida).</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Conmutador]

Comprueba si el valor de entrada coincide con la lista de valores proporcionada. Devuelve la salida en función del resultado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Input]</p> </td> 
   <td> <p>Introduzca la expresión que desea evaluar.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Use regular expressions to match]</td> 
   <td> <p>Active esta opción para utilizar expresiones regulares. El módulo determina los casos en función de la expresión regular, en lugar de una coincidencia exacta.</p> 
    <div> 
     <p>Una expresión regular es una secuencia de caracteres en la que cada carácter es un metacarácter, que tiene un significado especial, o un carácter regular que tiene un significado literal. Estos caracteres y metacaracteres identifican un patrón que se puede utilizar para buscar texto. Por ejemplo, si desea buscar nombres, puede configurar una expresión regular para buscar un patrón que consista en dos palabras consecutivas que comiencen con mayúsculas. Las expresiones regulares son una potente herramienta para buscar y manipular texto.</p> 
     <p>El análisis de las expresiones regulares excede el ámbito de este artículo. Recomendamos los siguientes recursos:</p> 
     <ul> 
      <li>Para obtener la lista completa de metacaracteres, consulte <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions">Expresiones regulares</a> en los documentos web de MDN.</li> 
      <li>Para ver un tutorial sobre cómo crear expresiones regulares, recomendamos <a href="https://regexone.com/">RegexOne</a>.</li> 
      <li>Para experimentar con expresiones regulares, recomendamos el sitio web <a href="https://regex101.com/">Expresiones regulares 101</a>. Seleccione ECMAScript (JavaScript) FLAVOR en el panel izquierdo.</li> 
     </ul> 
    </div> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Cases] </td> 
   <td> Para cada caso que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca el patrón y el resultado del elemento. <p>Si la entrada contiene un valor introducido en el campo [!UICONTROL Pattern], se devuelve el valor introducido en el campo [!UICONTROL Output].</p> <p>Si la entrada no coincide con ninguno de los valores establecidos en un campo de [!UICONTROL Pattern], se produce una de las siguientes situaciones:</p> 
    <ul> 
     <li>Se devuelve el valor del campo [!UICONTROL Else]</li> 
     <li>Si no hay ningún valor en el campo [!UICONTROL Else], no se devuelve ningún resultado.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Else]</p> </td> 
   <td> <p>Introduzca el valor que se devuelve cuando no se cumplen los criterios establecidos en el campo Casos. </p> </td> 
  </tr> 
 </tbody> 
</table>
