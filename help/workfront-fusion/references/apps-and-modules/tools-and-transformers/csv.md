---
title: CSV
description: Los módulos CSV de Adobe Workfront Fusion le permiten crear archivos CSV y analizar texto CSV a partir de un valor de texto o un archivo recibidos.
author: Becky
feature: Workfront Fusion
exl-id: bc6d5ddc-93c3-437b-8537-5bece1351c1d
source-git-commit: 4697ea1449f77ddb8648658990098b3b4bc58ad2
workflow-type: tm+mt
source-wordcount: '942'
ht-degree: 48%

---

# CSV

Los módulos de Adobe Workfront Fusion [!UICONTROL CSV] le permiten crear archivos CSV y analizar texto CSV a partir de un valor de texto recibido o un archivo.

Como se trata de un transformador, estos módulos no requieren una conexión.

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
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete Select o Prime Workfront que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++



## [!UICONTROL Crear CSV]

El agregador [!UICONTROL Crear CSV] le permite crear un texto CSV a partir de valores de texto recibidos.

Para obtener más información sobre los agregadores, consulte [Módulo de agregador](/help/workfront-fusion/references/modules/aggregator-module.md).

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Source Module]</td>
        <td>Seleccione el módulo que genera los campos que desea utilizar para crear el CSV.</td>
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

## [!UICONTROL Crear CSV (avanzado)]

El acumulador [!UICONTROL Crear CSV (avanzado)] le permite crear un texto CSV a partir de valores de texto recibidos. Emplea una estructura de datos que define las columnas CSV en el archivo CSV resultante. Una vez definidas, las columnas aparecen como campos en la configuración del módulo CSV y se pueden asignar a módulos posteriores en el escenario.

Para obtener más información sobre los agregadores, consulte [Módulo de agregador](/help/workfront-fusion/references/modules/aggregator-module.md).

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Module]</td> 
        <td>Seleccione el módulo que genera los campos que desea utilizar para crear el CSV.</td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data Structure]</td> 
   <td> <p>Seleccione la estructura de datos para agregar los campos de la forma que desee. Después de definir la estructura de datos, puede asignar los elementos a los campos correspondientes.</p> <p>Para obtener más información, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md" class="MCXref xref">Estructuras de datos</a>.</p> </td> 
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


>[!BEGINSHADEBOX]

**Ejemplo**:

Este ejemplo muestra cómo exportar contactos de Google a un archivo CSV con dos columnas denominadas &quot;Full Name&quot; y &quot;Email&quot;. El paquete de salida del módulo [!UICONTROL Contactos de Google] > [!UICONTROL Obtener contactos de un grupo] tiene la siguiente estructura. Las direcciones de correo electrónico se almacenan dentro de <code>[!UICONTROL Correos electrónicos[]]</code> elemento, que es una matriz de colecciones, cada colección contiene dos elementos: <code>Label</code> y <code>correo electrónico</code>.
![Transformando](/help/workfront-fusion/references/apps-and-modules/assets/transforming-350x546.png)

El módulo [!DNL Create CSV] simple ofrece una lista de casillas de verificación correspondientes a los elementos de nivel superior de un paquete. Si intenta seleccionar <code>Nombre completo</code> y <code>correos electrónicos</code> elementos, el módulo [!UICONTROL Crear CSV] produce el siguiente resultado, que puede no ser el que desea:

```
"emails","fullName"
"[object Object]","Shon Winer"
"[object Object]","Lizeth Fulmore"
"[object Object]","Hilario Gullatt"
"[object Object]","Abby Eisenbarth"
```

Debido a que el elemento <code>Nombre completo</code> es de tipo texto simple, se exporta según lo esperado. El elemento <code>Correos electrónicos</code>, que es de un tipo complejo Array of Collections, se exporta como [objeto Object], que es la forma en que Collections y Arrays se transforman en texto de forma predeterminada.

Para obtener más información, vea [Tipos de datos de elementos](/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md).


Para exportar el contenido de <code>correo electrónico </code>elemento de la primera colección de <code>correos electrónicos[]</code> en su lugar, debe usar el módulo [!UICONTROL Crear CSV (avanzado)]. Este módulo le permite definir columnas individuales del archivo CSV y asignarles elementos, incluidos los anidados.

1. Inserte el módulo [!UICONTROL Crear CSV (avanzado)] en un escenario.
1. Haga clic en el botón <strong>[!UICONTROL Agregar]</strong> junto al campo [!UICONTROL Estructura de datos] para crear una nueva estructura de datos.
1. Escriba un nombre para la estructura de datos y haga clic en <strong>[!UICONTROL Agregar elemento]</strong> para agregar las columnas individuales. Para exportar dos columnas: &quot;Nombre completo&quot; y &quot;Correo electrónico&quot;, la estructura de datos resultante tendría este aspecto:

   ![Salida de contactos de Google](/help/workfront-fusion/references/apps-and-modules/assets/google-contacts-350x524.png)

1. Después de definir la estructura de datos, los campos correspondientes a cada columna individual aparecen en la configuración del módulo [!UICONTROL Crear CSV (avanzado)] para que pueda asignar los elementos. Tomar el primer elemento de los <code>[!UICONTROL correos electrónicos[]]</code> matriz y asignar su elemento <code>Correo electrónico </code>Vaya al campo/columna Correo electrónico:

   ![Crear módulo avanzado de CSV](/help/workfront-fusion/references/apps-and-modules/assets/create-csv-advanced-350x308.png)

1. Ejecute el escenario. Debido al elemento <code>Correos electrónicos[1]: Correo electrónico</code> asignado a la columna &quot;Correo electrónico&quot; es de tipo texto simple, se exporta correctamente.

```
"Full Name","Email"
"Shon Winer","Shon@Winer.com"
"Lizeth Fulmore","Lizeth@Fulmore.com"
"Hilario Gullatt","Hilario@Gullatt.com"
"Abby Eisenbarth","Abby@Eisenbarth.com"
```

>[!ENDSHADEBOX]

## [!UICONTROL Analizar CSV]

El transformador [!UICONTROL Analizar CSV] permite analizar texto CSV a partir de un valor de texto o un archivo recibidos.

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
   <td>Introduzca o asigne el archivo CSV que desea analizar.<p>Nota: <p>Si los datos vienen en formato binario (normalmente de un archivo), debe utilizar la función “toString()” para convertir los datos binarios a [!UICONTROL String]:</p><p><img src="/help/workfront-fusion/references/apps-and-modules/assets/parse-csv-350x123.png"></p></p></td> 
  </tr> 
 </tbody> 
</table>
