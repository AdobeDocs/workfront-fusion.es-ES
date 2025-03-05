---
title: Módulos de Google Sheets
description: Para usar [!DNL Google Sheets] con la extensión de [!DNL Adobe Workfront Fusion],you need the [!UICONTROL Workfront Fusion Google Sheets]  (opcional, pero necesaria para las activaciones instantáneas).
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 80965570-2937-4ac8-97c0-54f7a813ec50
source-git-commit: 85cd8dbf70dff220f593fa669b447bf5df2a21a2
workflow-type: tm+mt
source-wordcount: '3957'
ht-degree: 71%

---

# Módulos de [!DNL Google Sheets]

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!DNL Google Sheets], así como conectarlo a varias aplicaciones y servicios de terceros.

Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Google Sheets] a [!DNL Workfront Fusion], consulte [Crear una conexión con [!DNL Adobe Workfront Fusion] : instrucciones básicas](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

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

Para usar los módulos de [!UICONTROL Google Sheets], debe tener una cuenta de [!UICONTROL Google].

## Información de API de hojas de Google

El conector de Google Sheets utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL básica</td> 
   <td> https://sheets.googleapis.com/v4</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> v4 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 2.5.7</td> 
  </tr>
 </tbody> 
 </table>

## Módulos de hojas de Google y sus campos

Al configurar módulos de [!DNL Google Forms], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Google Sheets] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Activadores

#### [!UICONTROL Watch Rows]

Recupera valores de filas recién agregadas en la hoja de cálculo.

El módulo solo recupera las filas nuevas que no se hayan rellenado anteriormente. El déclencheur no procesa una fila sobrescrita.

>[!IMPORTANT]
>
>Si la hoja de cálculo contiene una fila en blanco, no se procesará ninguna fila después de la fila en blanco.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Sheets] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Spreadsheet] </td> 
   <td> <p>Seleccione la hoja de cálculo que contiene la hoja que desea ver.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sheet] </td> 
   <td> <p>Seleccione la hoja en la que desee buscar una fila nueva.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Table contains headers]</td> 
   <td> <p> Seleccione si la hoja de cálculo contiene una fila de encabezado.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Yes]</strong> </p> <p>El módulo no recupera la fila de encabezado como datos de salida. </p> <p>Los encabezados designan los nombres de variables en la salida.</p> </li> 
     <li> <p><strong>[!UICONTROL No]</strong> </p> <p>El módulo también recupera la primera fila de la tabla</p> <p>Los nombres de variables en la salida son A, B, C, D, etc.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Row with headers] </td> 
   <td> <p>Introduzca el rango de la fila de encabezado. Por ejemplo, <code>A1:F1</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL First table row]</td> 
   <td> <p>Introduzca el rango de la primera fila de la tabla. Por ejemplo, <code>A1:F1</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Value render option]</p> </td> 
   <td> <ul><li><p style="font-weight: bold;">[!UICONTROL Formatted value]</p> <p>Los valores se calculan y se les aplica formato en la respuesta según el formato de la celda. El formato se basa en la configuración regional de la hoja de cálculo, no en la configuración regional del usuario solicitante. Por ejemplo, si <code>A1</code> es <code>1.23</code> y <code>A2</code> es <code>=A1</code> y tiene formato de moneda, <code>A2</code> devolvería <code>"$1.23"</code>.</p></li><li> <p style="font-weight: bold;">[!UICONTROL Unformatted value]</p> <p>Los valores se calculan, pero no se les aplica formato en la respuesta. Por ejemplo, si <code>A1</code> es <code>1.23</code> y <code>A2</code> es <code>=A1</code> y tiene formato de moneda, <code>A2</code> devolvería el número <code>"1.23"</code>.</p></li><li> <p style="font-weight: bold;">[!UICONTROL Formula]</p> <p>Los valores no se calculan. La respuesta incluye las fórmulas. Por ejemplo, si <code>A1</code> es <code>1.23</code> y <code>A2</code> es <code>=A1</code> y tiene formato de moneda, <code>A2</code> devolvería <code>"=A1"</code>.</p> </li><ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Date and time render option]</p> </td> 
   <td> <ul><li><p style="font-weight: bold;">[!UICONTROL Serial number]</p> <p>Los campos de fecha, hora, fecha y hora y duración se presentan como valores dobles en formato de "número de serie", tal como lo populariza Lotus 1-2-3. La parte del número entero del valor (a la izquierda del decimal) cuenta los días transcurridos desde el 30 de diciembre de 1899. La parte fraccionaria (a la derecha del decimal) cuenta la hora como una fracción del día. Por ejemplo, el 1 de enero de 1900 al mediodía sería 2,5, 2 porque son 2 días después del 30 de diciembre de 1899 y 0,5 porque el mediodía es medio día. El 1 de febrero de 1900 a las 3 de la tarde sería 33,625. Esto trata correctamente el año 1900 como un año no bisiesto.</p> </li><li><p style="font-weight: bold;">[!UICONTROL Formatted string]</p> <p>Los campos de fecha, hora, fecha y hora se presentan como cadenas en un formato numérico determinado (que depende de la configuración regional de la hoja de cálculo).</p></li><ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Establezca el número máximo de resultados con los que trabajará [!DNL Workfront Fusion] durante un ciclo de ejecución.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Acciones

* [[!UICONTROL Añadir una fila]](#add-a-row)
* [[!UICONTROL Añadir una hoja]](#add-a-sheet)
* [[!UICONTROL Borrar una celda]](#clear-a-cell)
* [[!UICONTROL Borrar una fila]](#clear-a-row)
* [[!UICONTROL Crear una hoja de cálculo]](#create-a-spreadsheet)
* [[!UICONTROL Eliminar una fila]](#delete-a-row)
* [[!UICONTROL Eliminar una hoja]](#delete-a-sheet)
* [[!UICONTROL Obtener una celda]](#get-a-cell)
* [[!UICONTROL Realización de una llamada de API]](#make-an-api-call)
* [[!UICONTROL Actualizar una celda]](#update-a-cell)
* [[!UICONTROL Actualizar una fila]](#update-a-row)

#### [!UICONTROL Añadir una fila]

Este módulo añade una fila a una hoja.

Al configurar [!DNL Google Sheets] módulos, [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Google Sheets] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Sheets] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Mode]</td> 
   <td> <p>Seleccione si desea seleccionar la hoja de cálculo y la hoja manualmente o mediante asignación.</p> <p>Nota: la asignación manual resulta útil, por ejemplo, cuando se crea una hoja de cálculo nueva en un escenario de [!DNL Workfront Fusion] y desea añadir datos a la hoja de cálculo recién creada directamente en el escenario.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Seleccione la hoja de cálculo de [!DNL Google].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheet] </td> 
   <td> <p>Seleccione la hoja a la que desea añadir una fila.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Column Range]</td> 
   <td>Seleccione el rango de columnas con el que desea trabajar.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Table contains headers]</td> 
   <td> <p> Seleccione si la hoja de cálculo contiene la fila de encabezado.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Yes]</strong> </p> <p>El módulo no recupera la fila de encabezado como datos de salida. </p> <p>Los encabezados designan los nombres de variables en la salida.</p> </li> 
     <li> <p><strong>[!UICONTROL No]</strong> </p> <p>El módulo también recupera la primera fila de la tabla</p> <p>Los nombres de variables en la salida son A, B, C, D, etc.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Values] </td> 
   <td> <p>Introduzca o asigne las celdas deseadas de la fila que desea añadir.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Value input option]</td> 
   <td> 
    <ul> 
     <li> <p><strong>[!UICONTROL User entered]</strong></p> <p>Los valores se analizan como si el usuario los hubiera escrito en la IU. Los números se mantienen, pero las cadenas se pueden convertir en números, fechas u otros formatos siguiendo las mismas reglas que se aplican al escribir texto en una celda a través de la IU de [!DNL Google Sheets].</p> </li> 
     <li> <p><strong>[!UICONTROL Raw]</strong> </p> <p> Los valores que introduce el usuario no se analizan y se almacenan tal y como se introdujeron. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Insert data option]</td> 
   <td> <p>Especifique cómo se cambian los datos existentes al introducir nuevos datos. </p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Insert rows]</strong></p> <p>Las filas se insertan para los nuevos datos.</p> </li> 
     <li> <p><strong>[!UICONTROL Overwrite]</strong> </p> <p>Los nuevos datos sobrescriben los datos existentes en las áreas donde se escriben. Al añadir datos al final de la hoja, se insertan nuevas filas o columnas para poder escribir los datos.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Add a Sheet]

Crea una hoja nueva en una hoja de cálculo seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Sheets] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Seleccione la hoja de cálculo de Google en la que desea añadir una hoja.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Properties]</td> 
   <td> 
    <ul> 
     <li> <p style="font-weight: bold;">[!UICONTROL Title]</p> <p>Introduzca el nombre de la nueva hoja.</p> </li> 
     <li> <p style="font-weight: bold;">[!UICONTROL Index]</p> <p>Introduzca la posición de la hoja. El valor predeterminado es 0 (lo que coloca la hoja en primer lugar).</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Clear a Cell]

Elimina un valor de una celda especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Sheets] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Seleccione la hoja de cálculo de Google que contiene la hoja en la que desea borrar una celda.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheet] </td> 
   <td> <p>Seleccione la hoja en la que desea borrar una celda.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Cell] </td> 
   <td> <p>Introduzca o asigne el ID de la celda que desea borrar. Ejemplo: <code>A5</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Clear a Row]

Elimina valores de una fila especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Sheets] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Seleccione la hoja de cálculo de [!DNL Google] que contiene la hoja de cálculo de la que desea borrar una fila.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheet] </td> 
   <td> <p> Seleccione la hoja de la que desea borrar los datos.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Row number]</td> 
   <td> <p>Introduzca el número de la fila desde la que desea borrar los datos. Ejemplo: <code> 23</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Spreadsheet]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Sheets] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Title] </td> 
   <td> <p>Introduzca el nombre de la nueva hoja de cálculo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Locale]</td> 
   <td> <p>Introduzca la configuración regional de la hoja de cálculo en uno de los siguientes formatos:</p> 
    <ul> 
     <li>un código de idioma ISO 639-1 como <code>en</code></li> 
     <li>un código de idioma ISO 639-2 como <code>haw</code>, si no existe ningún código 639-1</li> 
     <li>una combinación del código de idioma ISO y el código de país, como <code>en_US</code></li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Recalculation interval]</td> 
   <td> <p>La cantidad de tiempo de espera antes de volver a calcular las funciones volátiles:</p> <ul><li><p style="font-weight: bold;">[!UICONTROL On change]</p> <p>Las funciones volátiles se actualizan con cada cambio.</p></li><li> <p style="font-weight: bold;">[!UICONTROL On change and every minute]</p> <p>Las funciones volátiles se actualizan con cada cambio y cada minuto.</p></li> <li><p style="font-weight: bold;">[!UICONTROL On change and hourly]</p> <p>Las funciones volátiles se actualizan con cada cambio y cada hora.</p></li></ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Time zone]</td> 
   <td> <p> Seleccione la zona horaria de la hoja de cálculo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Number format]</td> 
   <td> <p>Seleccione el formato predeterminado de todas las celdas de la hoja de cálculo.</p> <p><strong>[!UICONTROL Text]</strong>: formato de texto. Ejemplo: <code>1000. 12</code></p> <p><strong>[!UICONTROL Number]</strong>: formato de número. Ejemplo: <code>1,000.12</code></p> <p><strong>[!UICONTROL Percent]</strong>: formato de porcentaje. Ejemplo: <code>10. 12%</code></p> <p><strong>[!UICONTROL Currency]</strong>: formato de moneda. Ejemplo: <code>$1,000.12</code></p> <p><strong>[!UICONTROL Date]</strong>: formato de fecha. Ejemplo: <code>9/26/2008</code></p> <p><strong>[!UICONTROL Time]</strong>: formato de hora. Ejemplo: <code>3:59:00 PM</code></p> <p><strong>[!UICONTROL Date time]</strong>: formato de fecha y hora. Ejemplo: <code>9/26/08 15:59:00</code> </p> <p><strong>[!UICONTROL Scientific]</strong>: Formato de número científico. Ejemplo: <code>1. 01E+03</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheets] </td> 
   <td> <p>Para cada hoja que desee agregar a la hoja de cálculo, haga clic en <strong>[!UICONTROL Agregar elemento]</strong> y escriba o asigne un título para la hoja y su índice. Un índice 0 representa la primera hoja.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Eliminar una fila]

Elimina una fila especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Sheets] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Seleccione la hoja de cálculo de Google que contiene la hoja en la que desea eliminar una fila.</p> </td> 
  </tr> 
  <tr> 
   <td>Hoja </td> 
   <td> <p>Seleccione la hoja de la que desea eliminar una fila.</p> </td> 
  </tr> 
  <tr> 
   <td>Número de fila</td> 
   <td> <p>Introduzca el número de la fila que desea eliminar. Ejemplo: <code>23</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Eliminar una hoja]

Elimina una hoja específica.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Sheets] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Seleccione la hoja de cálculo de [!DNL Google].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheet] </td> 
   <td> <p>Seleccione la hoja que desee eliminar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Obtener una celda]

Recupera un valor de una celda seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Sheets] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Seleccione la hoja de cálculo de [!DNL Google].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheet] </td> 
   <td> <p>Seleccione la hoja que contiene la celda de la que desea recuperar los datos.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Cell] </td> 
   <td> <p>Introduzca el ID de la celda desde la que desea recuperar los datos. Ejemplo: <code>A6</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Value render option]</td> 
   <td> <ul><li><p style="font-weight: bold;">[!UICONTROL Formatted value]</p> <p>Los valores se calculan y se les aplica formato en la respuesta según el formato de la celda. El formato se basa en la configuración regional de la hoja de cálculo, no en la configuración regional del usuario solicitante. Por ejemplo, si <code>A1</code> es <code>1.23</code> y <code>A2</code> es <code>=A1</code> y tiene formato de moneda, <code>A2</code> devolvería <code>"$1.23"</code>.</p></li><li> <p style="font-weight: bold;">[!UICONTROL Unformatted value]</p> <p>Los valores se calculan, pero no se les aplica formato en la respuesta. Por ejemplo, si <code>A1</code> es <code>1.23</code> y <code>A2</code> es <code>=A1</code> y tiene formato de moneda, <code>A2</code> devolvería el número <code>"1.23"</code>.</p></li><li> <p style="font-weight: bold;">[!UICONTROL Formula]</p> <p>Los valores no se calculan. La respuesta incluye las fórmulas. Por ejemplo, si <code>A1</code> es <code>1.23</code> y <code>A2</code> es <code>=A1</code> y tiene formato de moneda, <code>A2</code> devolvería <code>"=A1"</code>.</p> </li><ul></td> 
  </tr> 
  <tr> 
   <td>[!DNL Date and time render option]</td> 
   <td> <ul><li><p style="font-weight: bold;">[!DNL Serial number]</p> <p>Los campos de fecha, hora, fecha y hora y duración se presentan como valores dobles en formato de "número de serie", tal como lo populariza Lotus 1-2-3. La parte del número entero del valor (a la izquierda del decimal) cuenta los días transcurridos desde el 30 de diciembre de 1899. La parte fraccionaria (a la derecha del decimal) cuenta la hora como una fracción del día. Por ejemplo, el 1 de enero de 1900 al mediodía sería 2,5, 2 porque son 2 días después del 30 de diciembre de 1899 y 0,5 porque el mediodía es medio día. El 1 de febrero de 1900 a las 3 de la tarde sería 33,625. Esto trata correctamente el año 1900 como un año no bisiesto.</p></li><li> <p style="font-weight: bold;">[!DNL Formatted string]</p> <p>Los campos de fecha, hora, fecha y hora se presentan como cadenas en un formato numérico determinado (que depende de la configuración regional de la hoja de cálculo).</p> </li><ul></td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Realización de una llamada de API]

Este módulo de acción le permite realizar una llamada de API personalizada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de Google Sheets a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión a [!DNL Adobe Workfront Fusion] - Instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td>Escriba una ruta relativa a <code>https://sheets.googleapis.com/v4/</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar. Por ejemplo, <code>{"Content-type":"application/json"}</code>. [!DNL Workfront Fusion] añade los encabezados de autorización en su lugar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> Añada la consulta para la llamada de API en forma de objeto JSON estándar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:   <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>">  
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Actualizar una celda]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Sheets] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Seleccione la hoja de cálculo de [!DNL Google].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheet] </td> 
   <td> <p>Seleccione la hoja en la que desea actualizar una celda.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Cell] </td> 
   <td> <p>Introduzca el ID de la celda que desea actualizar. Ejemplo: <code>A5</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Value]</td> 
   <td> <p>Introduzca el nuevo valor para la celda.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Value input option]</td> 
   <td> 
    <ul> 
     <li> <p><strong>[!UICONTROL User entered]</strong></p> <p>Los valores se analizan como si el usuario los hubiera escrito en la IU. Los números se mantienen, pero las cadenas se pueden convertir en números, fechas u otros formatos siguiendo las mismas reglas que se aplican al escribir texto en una celda a través de la IU de [!DNL Google Sheets].</p> </li> 
     <li> <p><strong>[!UICONTROL Raw]</strong> </p> <p> Los valores que introduce el usuario no se analizan y se almacenan tal y como se introdujeron. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Actualizar una fila]

Este módulo permite cambiar el contenido de la celda en una fila seleccionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Sheets] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Mode]</td> 
   <td> <p>Seleccione si desea seleccionar la hoja de cálculo y la hoja manualmente o mediante asignación.</p> <p>Nota: La asignación manual resulta útil, por ejemplo, cuando se crea una nueva hoja de cálculo en el escenario [!UICONTROL Workfront Fusion] y se desea añadir datos a la hoja de cálculo recién creada directamente en el escenario.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Seleccione la hoja de cálculo de [!DNL Google].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheet] </td> 
   <td> <p>Seleccione la hoja en la que desea actualizar una fila.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Row number]</td> 
   <td> <p> Introduzca el número de la fila que desea actualizar.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Table contains headers]</td> 
   <td> <p> Seleccione si la hoja de cálculo contiene la fila de encabezado.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Yes]</strong> </p> <p>El módulo no recupera la fila de encabezado como datos de salida. </p> <p>Los encabezados designan los nombres de variables en la salida.</p> </li> 
     <li> <p><strong>[!UICONTROL No]</strong> </p> <p>El módulo también recupera la primera fila de la tabla</p> <p>Los nombres de variables en la salida son A, B, C, D, etc.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Values] </td> 
   <td> <p>Introduzca o asigne los valores a las celdas deseadas de la fila que desea cambiar (actualizar).</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Value input option]</td> 
   <td> 
    <ul> 
     <li> <p><strong>[!UICONTROL User entered]</strong></p> <p>Los valores se analizan como si el usuario los hubiera escrito en la IU. Los números se mantienen, pero las cadenas se pueden convertir en números, fechas u otros formatos siguiendo las mismas reglas que se aplican al escribir texto en una celda a través de la IU de [!DNL Google Sheets].</p> </li> 
     <li> <p><strong>[!UICONTROL Raw]</strong> </p> <p> Los valores que introduce el usuario no se analizan y se almacenan tal y como se introdujeron. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Búsquedas

* [[!UICONTROL Obtener valores de rango]](#get-range-values)
* [[!UICONTROL Hojas de lista]](#list-sheets)
* [[!UICONTROL Buscar filas]](#search-rows)
* [[!UICONTROL Buscar filas (avanzado)]](#search-rows-advanced)

#### [!UICONTROL Obtener valores de rango]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Sheets] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Seleccione la hoja de cálculo de [!DNL Google].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheet] </td> 
   <td> <p>Seleccione la hoja de la que desea obtener el contenido del rango.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Range] </td> 
   <td> <p>Introduzca el rango que desea obtener. Ejemplo: <code>A1:D25</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Table contains headers]</td> 
   <td> <p>Marque esta casilla si la hoja tiene una fila de encabezado</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Row with headers]</td> 
   <td>Introduzca el rango de los encabezados de tabla. Ejemplo <code>A1:F1</code>. Si deja el campo vacío, [!DNL Workfront Fusion] trata la primera fila del rango especificado como encabezado.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Value render option]</td> 
   <td> <ul><li><p style="font-weight: bold;">[!UICONTROL Formatted value]</p> <p>Los valores se calculan y se les aplica formato en la respuesta según el formato de la celda. El formato se basa en la configuración regional de la hoja de cálculo, no en la configuración regional del usuario solicitante. Por ejemplo, si <code>A1</code> es <code>1.23</code> y <code>A2</code> es <code>=A1</code> y tiene formato de moneda, <code>A2</code> devolvería <code>"$1.23"</code>.</p></li><li> <p style="font-weight: bold;">[!UICONTROL Unformatted value]</p> <p>Los valores se calculan, pero no se les aplica formato en la respuesta. Por ejemplo, si <code>A1</code> es <code>1.23</code> y <code>A2</code> es <code>=A1</code> y tiene formato de moneda, <code>A2</code> devolvería el número <code>"1.23"</code>.</p></li><li> <p style="font-weight: bold;">[!UICONTROL Formula]</p> <p>Los valores no se calculan. La respuesta incluye las fórmulas. Por ejemplo, si <code>A1</code> es <code>1.23</code> y <code>A2</code> es <code>=A1</code> y tiene formato de moneda, <code>A2</code> devolvería <code>"=A1"</code>.</p> </li><ul></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Date and time render option]</td> 
   <td> <ul><li><p style="font-weight: bold;">[!UICONTROL Serial number]</p> <p>Los campos de fecha, hora, fecha y hora y duración se presentan como valores dobles en formato de "número de serie", tal como lo populariza Lotus 1-2-3. La parte del número entero del valor (a la izquierda del decimal) cuenta los días transcurridos desde el 30 de diciembre de 1899. La parte fraccionaria (a la derecha del decimal) cuenta la hora como una fracción del día. Por ejemplo, el 1 de enero de 1900 al mediodía sería 2,5, 2 porque son 2 días después del 30 de diciembre de 1899 y 0,5 porque el mediodía es medio día. El 1 de febrero de 1900 a las 3 de la tarde sería 33,625. Esto trata correctamente el año 1900 como un año no bisiesto.</p> </li><li><p style="font-weight: bold;">[!UICONTROL Formatted string]</p> <p>Los campos de fecha, hora, fecha y hora se presentan como cadenas en un formato numérico determinado (que depende de la configuración regional de la hoja de cálculo).</p></li><ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Sheets]

Este módulo devuelve una lista de todas las hojas de una hoja de cálculo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Sheets] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Seleccione la hoja de cálculo de [!DNL Google] que contiene las hojas que desea enumerar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Buscar filas]

Busca filas utilizando las opciones de filtro.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de Google Sheets a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión a [!DNL Adobe Workfront Fusion] - Instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Seleccione la hoja de cálculo de [!DNL Google].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheet] </td> 
   <td> <p>Seleccione la hoja en la que desea buscar las filas.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Table contains headers]</td> 
   <td> <p> Seleccione si la hoja de cálculo contiene la fila de encabezado. Si se selecciona la opción [!UICONTROL Yes], el módulo no recupera la fila de encabezado, ya que los encabezados designan los datos de salida y los nombres de variables en la salida. Si se selecciona la opción [!UICONTROL No], el módulo también recupera la primera fila de tabla y los nombres de variables en la salida son A, B, C, D, etc.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Column range]</td> 
   <td>Seleccione el rango de columnas con el que desea trabajar. Ejemplo: <code>A-F</code></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Filter]</td> 
   <td> <p>Establezca el filtro que desea utilizar para buscar filas.</p> <!--<p>For more information about filters, see <a href="/help/workfront-fusion/create-scenarios/add-modules/" class="MCXref xref">Add a filter to a scenario in [!UICONTROL Adobe Workfront Fusion]</a>.</p>--> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sort order]</td> 
   <td>Seleccione si desea ordenar de forma ascendente o descendente.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Order by]</td> 
   <td>Elija la columna por la que desea ordenar.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Value render option]</td> 
   <td> <ul><li><p style="font-weight: bold;">[!UICONTROL Formatted value]</p> <p>Los valores se calculan y se les aplica formato en la respuesta según el formato de la celda. El formato se basa en la configuración regional de la hoja de cálculo, no en la configuración regional del usuario solicitante. Por ejemplo, si <code>A1</code> es <code>1.23</code> y <code>A2</code> es <code>=A1</code> y tiene formato de moneda, <code>A2</code> devolvería <code>"$1.23"</code>.</p></li><li> <p style="font-weight: bold;">[!UICONTROL Unformatted value]</p> <p>Los valores se calculan, pero no se les aplica formato en la respuesta. Por ejemplo, si <code>A1</code> es <code>1.23</code> y <code>A2</code> es <code>=A1</code> y tiene formato de moneda, <code>A2</code> devolvería el número <code>"1.23"</code>.</p></li><li> <p style="font-weight: bold;">[!UICONTROL Formula]</p> <p>Los valores no se calculan. La respuesta incluye las fórmulas. Por ejemplo, si <code>A1</code> es <code>1.23</code> y <code>A2</code> es <code>=A1</code> y tiene formato de moneda, <code>A2</code> devolvería <code>"=A1"</code>.</p> </li><ul></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Date and time render option]</td> 
   <td> <ul><li><p style="font-weight: bold;">[!UICONTROL Serial number]</p> <p>Los campos de fecha, hora, fecha y hora y duración se presentan como valores dobles en formato de "número de serie", tal como lo populariza Lotus 1-2-3. La parte del número entero del valor (a la izquierda del decimal) cuenta los días transcurridos desde el 30 de diciembre de 1899. La parte fraccionaria (a la derecha del decimal) cuenta la hora como una fracción del día. Por ejemplo, el 1 de enero de 1900 al mediodía sería 2,5, 2 porque son 2 días después del 30 de diciembre de 1899 y 0,5 porque el mediodía es medio día. El 1 de febrero de 1900 a las 3 de la tarde sería 33,625. Esto trata correctamente el año 1900 como un año no bisiesto.</p> </li><li><p style="font-weight: bold;">[!UICONTROL Formatted string]</p> <p>Los campos de fecha, hora, fecha y hora se presentan como cadenas en un formato numérico determinado (que depende de la configuración regional de la hoja de cálculo).</p></li><ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned rows]</td> 
   <td>Establezca el número máximo de filas que [!DNL Workfront Fusion] devolverá durante un ciclo de ejecución.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Buscar filas (avanzado)]

Devuelve los resultados que coinciden con los criterios especificados.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Sheets] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Crear una conexión: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Seleccione la hoja de cálculo de Google que contiene la hoja que desea buscar.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheet] </td> 
   <td> <p>Seleccione la hoja que contiene las filas que desea buscar.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query]</td> 
   <td> <p>Utilice [!DNL Google Charts Query Language]. Ejemplo: <code>select * where B = "John"</code></p> <p>Para obtener más información sobre [!DNL Google Charts Query Language], consulte <a href="https://developers.google.com/chart/interactive/docs/querylanguage">Referencia del lenguaje de consulta</a> en la documentación de [!DNL Google].</p> </td> 
  </tr> 
 </tbody> 
</table>

## Límites de uso

Si se produce el error `429: RESOURCE_EXHAUSTED`, ha excedido el límite de la API.

La API de [!DNL Google Sheets] tiene un límite de 500 solicitudes por 100 segundos por proyecto, y de 100 solicitudes por 100 segundos por usuario. Los límites para lecturas y escrituras se contabilizan por separado. No hay límite de uso diario.

Puede encontrar información más detallada en [https://developers.google.com/sheets/api/limits?hl=es-419](https://developers.google.com/sheets/api/limits?hl=es-419).

## Sugerencias y trucos

* [Obtener celdas vacías de una  [!DNL Google] hoja](#get-empty-cells-from-a-google-sheet)
* [Añadir un botón a una hoja para ejecutar un escenario](#add-a-button-in-a-sheet-to-run-a-scenario)

### Obtener celdas vacías de [!DNL Google Sheet]

Para obtener celdas vacías, puede usar el módulo [!UICONTROL Buscar filas (avanzadas)]. Utilice esta fórmula para obtener las columnas vacías.

```
select * where E is null
```

Aquí, &quot;E&quot; es la columna y &quot;es nulo&quot; es la condición. Puede crear una consulta más avanzada utilizando el lenguaje de consulta Google. Para obtener más información, consulte [Google Query Lang](https://developers.google.com/chart/interactive/docs/querylanguage) en la documentación de Google.

### Añadir un botón a una hoja para ejecutar un escenario

1. En [!DNL Workfront Fusion], inserte el módulo **[!UICONTROL Webhook]** > **[!UICONTROL Webhooks personalizados]** en el escenario y configúrelo. Para obtener instrucciones, consulte [Webhooks](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md).

1. Copie la URL del webhook.
1. Ejecute el escenario.
1. En Google Sheets, elija **[!UICONTROL Insertar]** > **[!UICONTROL Dibujo]**... en la barra de menús principal.

1. En la ventana [!UICONTROL Dibujo], haga clic en el icono **[!UICONTROL Cuadro de texto]** ![Cuadro de texto](/help/workfront-fusion/references/apps-and-modules/assets/text-box.png) cerca de la parte superior de la ventana.
1. Diseñe un botón y haga clic en el botón **[!UICONTROL Guardar y cerrar]** en la esquina superior derecha:
1. El botón se coloca en la hoja de cálculo. Haga clic en los tres puntos verticales de la esquina superior derecha del botón:
1. Elija **[!UICONTROL Asignar script...]** en el menú.
1. Escriba el nombre del script (función), por ejemplo `runScenario` y haga clic en **[!UICONTROL Aceptar]**:
1. Elija **[!UICONTROL Herramientas]** > **[!UICONTROL Editor de scripts]** en la barra de menús principal.

1. Inserte el siguiente código:

   * El nombre de la función debe corresponder al nombre especificado en el paso 9.
   * Reemplace la URL con la URL del webhook que copió en el paso 2.

     ```
     function runScenario() {
     UrlFetchApp.fetch("&lt;webhook you copied>");
     }
     ```

1. Presione **[!UICONTROL Ctrl+S]** para guardar el archivo de script, ingrese un nombre de proyecto y haga clic en **[!UICONTROL Aceptar]**.

1. Vuelva a [!DNL Google Sheets] y haga clic en el nuevo botón.
1. Conceda la autorización necesaria al script:
1. En [!DNL Workfront Fusion], compruebe que el escenario se haya ejecutado correctamente.

## Almacenamiento de fechas en una hoja de cálculo

Si almacena un valor Date en una hoja de cálculo sin ningún formato, aparecerá en la hoja de cálculo como texto en formato ISO 8601. Sin embargo, [!DNL Google Sheets] fórmulas o funciones que funcionan con fechas que no comprenden este texto (Ejemplo: fórmula `=A1+10`) muestran el siguiente error:

![Error](/help/workfront-fusion/references/apps-and-modules/assets/mceclip6-350x87.png)

Para permitir que [!DNL Google Sheets] entienda la fecha, debe aplicarle formato con la función `formatDate`. El formato correcto pasado a la función como segundo argumento depende de la configuración regional de la hoja de cálculo.

Para obtener más información sobre esta función, consulte [[!UICONTROL formatDate] (date; format; [timezone])](/help/workfront-fusion/references/mapping-panel/functions/date-and-time-functions.md#formatdate-date-format-timezone) en el artículo Funciones de fecha y hora.

Para determinar el formato correcto:

1. En Hojas de cálculo de Google, elija la configuración de **[!UICONTROL Archivo]** > **[!UICONTROL Hoja de cálculo]** en el menú principal para comprobar y establecer la configuración regional.

1. Después de comprobar o establecer la configuración regional adecuada, determine el formato de fecha y hora correspondiente eligiendo **[!UICONTROL Formato]** > **[!UICONTROL Número]** en el menú principal. El formato se muestra junto al elemento de menú Fecha y hora:

1. Para componer el formato correcto que se debe pasar a la función [!UICONTROL formatDate()], consulte la lista de [tokens para el formato de fecha y hora](/help/workfront-fusion/references/mapping-panel/functions/tokens-for-date-and-time-formatting.md).

>[!BEGINSHADEBOX]

**Ejemplo:**

Para el formato `MM/DD/YYYY HH:mm:ss` (para la configuración regional de Estados Unidos):

![Fórmula de hora local](/help/workfront-fusion/references/apps-and-modules/assets/locale-time-350x83.png)

>[!ENDSHADEBOX]

## Aprovechar las funciones de [!DNL Google Sheets]

Para utilizar una función integrada desde Hojas de cálculo de Google, puede aprovecharla. Para obtener más información, vea [Usar [!DNL Google Sheets] funciones](/help/workfront-fusion/create-scenarios/map-data/map-using-functions.md#use-google-sheets-functions) en el artículo Asignar un elemento mediante funciones.

## Impedir que [!DNL Google Sheets] cambie números en fechas

Si una cadena de números que está utilizando como texto se interpreta como una fecha en una hoja de cálculo [!DNL Google], puede aplicar formato previo al número como texto sin formato para evitarlo. Por ejemplo, si escribe 1-2019 con la intención de que sea texto, Google puede interpretarlo como una fecha.

1. En [!DNL Google Sheets], resalte la columna o celda que contenga el número o los números.
1. Haga clic en **[!UICONTROL Formato]** > **[!UICONTROL Número]** > **[!UICONTROL Texto sin formato]**.

Otra solución en [!DNL Workfront Fusion] es escribir un apóstrofo (&#39;) antes de un número, por ejemplo, &#39;1-2019 o &#39;1/47. El apóstrofo no se muestra en la celda después de enviar los datos desde [!DNL Workfront Fusion].
