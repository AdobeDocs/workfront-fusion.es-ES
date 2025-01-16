---
title: CSV
description: Los módulos CSV de Adobe Workfront Fusion le permiten crear archivos CSV y analizar texto CSV a partir de un valor de texto o un archivo recibidos.
author: Becky
feature: Workfront Fusion
exl-id: bc6d5ddc-93c3-437b-8537-5bece1351c1d
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 69%

---

# CSV

Los módulos [!DNL Adobe Workfront Fusion] [!UICONTROL CSV] le permiten crear archivos CSV y analizar texto CSV a partir de un valor de texto recibido o un archivo.

## Requisitos de acceso

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] plan*</td>
  <td> <p>[!UICONTROL Pro] o superior</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licencia*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licencia**</td> 
   <td>
   <p>Requisito de licencia actual: no se requiere ninguna licencia de [!DNL Workfront Fusion].</p>
   <p>O</p>
   <p>Requisito de licencia heredado: [!UICONTROL [!DNL Workfront Fusion] para automatización e integración de trabajo, [!UICONTROL [!DNL Workfront Fusion] para automatización de trabajo</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Requisito de producto actual: si tiene el plan [!UICONTROL Select] o [!UICONTROL Prime] [!DNL Adobe Workfront], su organización debe adquirir [!DNL Adobe Workfront Fusion] así como [!DNL Adobe Workfront] para utilizar la funcionalidad descrita en este artículo. [!DNL Workfront Fusion] está incluido en el plan [!UICONTROL Ultimate] [!DNL Workfront].</p>
   <p>O</p>
   <p>Requisito de productos heredados: su organización debe comprar [!DNL Adobe Workfront Fusion] y [!DNL Adobe Workfront] para utilizar la funcionalidad descrita en este artículo.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Para saber qué plan, tipo de licencia o acceso tiene, póngase en contacto con el administrador de [!DNL Workfront].

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## [!UICONTROL Create CSV]

El Agregador [!UICONTROL Create CSV] le permite crear un texto csv a partir de valores de texto recibidos.

Para obtener más información sobre los agregadores, consulte [Módulo de agregador](/help/workfront-fusion/references/modules/aggregator-module.md).

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Source Module]</td>
        <td>Seleccione el módulo que utiliza para agregar los campos que necesita.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Aggregated Fields]</td>
        <td>Seleccione los campos que desee agregar de la lista de campos disponibles.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Include headers in the first row]</td>
        <td>Seleccione esta opción para incluir los encabezados en el resultado.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Group by]</td>
        <td>Introduzca el filtro para agrupar los resultados. Por ejemplo, introduzca una fecha.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Stop processing after an empty aggregation]</td>
        <td>Seleccione esta opción para detener el escenario cuando no haya resultados.</td>
    </tr>
</table>

## [!UICONTROL Create CSV (advanced)]

El acumulador [!UICONTROL Create CSV (advanced)] le permite crear un texto CSV a partir de valores de texto recibidos. Emplea una estructura de datos que define las columnas CSV en el archivo CSV resultante. Una vez definidas, las columnas aparecen como campos en la configuración del módulo CSV y se pueden asignar a módulos posteriores en el escenario.

Para obtener más información sobre los agregadores, consulte [Módulo de agregador en [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/references/modules/aggregator-module.md).

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Module]</td> 
   <td>Seleccione el módulo de la aplicación que utiliza para añadir los campos que necesita.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data Structure]</td> 
   <td> <p>Seleccione la estructura de datos para agregar los campos de la forma que desee. Después de definir la estructura de datos, puede asignar los elementos a los campos correspondientes.</p> <p>Para obtener más información, vea <a href="/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md" class="MCXref xref">Estructuras de datos en [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include headers in the first row] </td> 
   <td>Seleccione esta opción para incluir los encabezados en el resultado. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Group by] </td> 
   <td>Introduzca el filtro para agrupar los resultados. Por ejemplo, introduzca una fecha. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Stop processing after an empty aggregation] </td> 
   <td>Seleccione esta opción para detener el escenario cuando no haya resultados. </td> 
  </tr> 
 </tbody> 
</table>


<p>Supongamos que desea exportar sus contactos de Google a un archivo CSV con dos columnas “Nombre completo” y “Correo electrónico”. El paquete de salida del módulo [!UICONTROL Google Contacts] &gt;[!UICONTROL Get contacts from a group] tiene la siguiente estructura. Las direcciones de correo electrónico se almacenan dentro del elemento <code>[!UICONTROL Emails[]]</code>, que es una matriz de colecciones, y cada colección contiene dos elementos: <code>Label</code> y <code>Email</code>.</p>
<p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/transforming-350x546.png" style="width: 350;height: 546;"> </p>
<p>Si usa el módulo [!DNL Create CSV] simple, se le ofrecerá una lista de casillas de verificación correspondientes a los elementos de nivel superior de un paquete. Si intenta marcar <code>Full name</code> y <code>Emails</code> elementos, el módulo [!UICONTROL Create CSV] genera el siguiente resultado, que probablemente no sea el que desea:</p>
<p>"emails","fullName"</p>
<p>"[object Object]","Shon Winer"</p>
<p>"[object Object]","Lizeth Fulmore"</p>
<p>"[object Object]","Hilario Gullatt"</p>
<p>"[object Object]","Abby Eisenbarth"</p>
<p>Dado que el elemento <code>Full Name</code> es de tipo texto simple, se exporta bien. Sin embargo, el elemento <code>Emails</code>, que es de un tipo complejo de matriz de colecciones, se exporta como [object Object], que es la forma en que Colecciones y Matrices se transforman en texto de forma predeterminada. Para obtener más información, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md" class="MCXref xref">Tipos de datos de elementos en Adobe Workfront Fusion</a>.</p>
<p>Para exportar el contenido del elemento <code>Email </code> de la primera colección de la matriz <code>Emails[]</code>, es necesario emplear el módulo [!UICONTROL Create CSV (advanced)]. El módulo le permite definir columnas individuales del archivo CSV y asignarles elementos, incluidos los anidados.</p>
<ol>
<li value="1">Inserte el módulo [!UICONTROL Create CSV (advanced)] en un escenario y abra su configuración.</li>
<li value="2">Haga clic en el botón <strong>[!UICONTROL Add]</strong> junto al campo [!UICONTROL Data structure] para crear una nueva estructura de datos.</li>
<li value="3"> <p>Escriba un nombre para la estructura de datos y haga clic en el botón <strong>[!UICONTROL Add item]</strong> para agregar las columnas individuales. Si desea exportar dos columnas (“Nombre completo” y “Correo electrónico”), la estructura de datos resultante tendría este aspecto:</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/google-contacts-350x524.png" style="width: 350;height: 524;"> </p> </li>
<li value="4"> <p>Una vez que haya definido correctamente la estructura de datos, los campos correspondientes a cada columna individual deben aparecer en la configuración del módulo [!UICONTROL Create CSV (advanced)] para que pueda asignar los elementos. Tome el primer elemento de la matriz <code>[!UICONTROL Emails[]]</code> y asigne su elemento <code>Email </code> al campo/columna Correo electrónico:</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/create-csv-advanced-350x308.png" style="width: 350;height: 308;"> </p> </li>
<li value="5"> <p>Ejecute el escenario. Dado que el elemento <code>Emails[1]: Email</code> asignado a la columna “Correo electrónico” es de tipo texto simple, ahora se exporta de forma correcta:</p> <p>"Nombre completo","Correo electrónico"</p> <p>"Shon Winer","Shon@Winer.com"</p> <p>"Lizeth Fulmore","Lizeth@Fulmore.com"</p> <p>"Hilario Gullatt","Hilario@Gullatt.com"</p> <p>"Abby Eisenbarth","Abby@Eisenbarth.com"</p> </li>
</ol>
</div>

## [!UICONTROL Parse CSV]

El transformador [!UICONTROL Parse CSV] le permite analizar texto CSV desde un valor de texto recibido o un archivo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number of columns]</td> 
   <td>Especifique el número de columnas en el archivo CSV.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL CSV contains headers]</td> 
   <td> <p>Seleccione esta opción si la primera fila del texto CSV contiene encabezados.</p> <p>Nota: El módulo no utiliza estos encabezados para etiquetar las columnas de la salida. En su lugar, este campo garantiza que los encabezados no se incluyan en los datos de salida.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL delimiterType]</td> 
   <td> <p>Seleccione el delimitador para el archivo CSV. El delimitador es el carácter de texto que indica el límite entre valores o campos independientes.</p> 
    <ul> 
     <li>[!UICONTROL Comma]</li> 
     <li>[!UICONTROL Tab]</li> 
     <li> <p>[!UICONTROL Other]</p> <p>Si selecciona [!UICONTROL Other], introduzca el carácter delimitador que utiliza el archivo CSV para separar valores. Debe introducir exactamente un carácter.<br></p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Preserve quotes inside unquoted field]</td> 
   <td>Habilite esta opción para conservar las comillas.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL CSV]</td> 
   <td>Introduzca o asigne el archivo CSV que desea analizar.<p>Nota: <p>Si los datos vienen en formato binario (normalmente de un archivo), debe utilizar la función "toString()" para convertir los datos binarios a [!UICONTROL String]:</p><p><img src="/help/workfront-fusion/references/apps-and-modules/assets/parse-csv-350x123.png" style="width: 350;height: 123;"></p></p></td> 
  </tr> 
 </tbody> 
</table>
