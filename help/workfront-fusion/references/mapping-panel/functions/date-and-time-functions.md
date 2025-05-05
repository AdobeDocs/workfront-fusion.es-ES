---
title: Funciones de fecha y hora
description: Las siguientes funciones de fecha y hora están disponibles en el panel de asignación de Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 92813dac-4bf0-4681-9b71-7bd2e92a89a4
source-git-commit: 9249223c6fbe0360b11d41988fe8b9c35e45dbb8
workflow-type: tm+mt
source-wordcount: '1876'
ht-degree: 92%

---

# Funciones de fecha y hora

## Variables

### now

Obtiene la hora actual en formato AAAA-MM-DD-hh:mm:ss.

### timestamp

Obtiene la hora actual como una marca de tiempo Unix.

## Funciones 

### [!UICONTROL addSeconds (fecha; número)]

Devuelve una nueva fecha como resultado de añadir un número determinado de segundos a una fecha. Para restar segundos, introduzca un número negativo.

>[!BEGINSHADEBOX]

**Ejemplos:**

* `addSeconds(2016-12-08T15:55:57.536Z;2)`

  Devuelve 2016-12-08T15:55:59.536Z

* `addSeconds(2016-12-08T15:55:57.536Z;-2)`

  Devuelve 2016-12-08T15:55:55.536Z

>[!ENDSHADEBOX]

### [!UICONTROL addMinutes (fecha; número)] {#addminutes-date-number}

Devuelve una nueva fecha como resultado de añadir un número determinado de minutos a una fecha. Para restar minutos, introduzca un número negativo.

>[!BEGINSHADEBOX]

**Ejemplos:**

* `addMinutes(2016-12-08T15:55:57.536Z;2)`

  Devuelve 2016-12-08T15:57:57.536Z

* `addMinutes(2016-12-08T15:55:57.536Z;-2)`

  Devuelve 2016-12-08T15:53:57.536Z

>[!ENDSHADEBOX]

### [!UICONTROL addHours (fecha; número)] {#addhours-date-number}

Devuelve una nueva fecha como resultado de añadir un número determinado de horas a una fecha. Para restar horas, introduzca un número negativo.

>[!BEGINSHADEBOX]

**Ejemplos:**

* `addHours(2016-12-08T15:55:57.536Z; 2)`

  Devuelve 2016-12-08T17:55:57.536Z

* `addHours(2016-12-08T15:55:57.536Z;-2)`

  Devuelve 2016-12-08T13:55:57.536Z

>[!ENDSHADEBOX]

### [!UICONTROL addDays (fecha; número)] {#adddays-date-number}

Devuelve una nueva fecha como resultado de añadir un número determinado de días a una fecha. Para restar días, introduzca un número negativo.

>[!BEGINSHADEBOX]

**Ejemplos:**

* `addDays(2016-12-08T15:55:57.536Z;2)`

  Devuelve 2016-12-10T15:55:57.536Z

* `addDays(2016-12-08T15:55:57.536Z;-2)`

  Devuelve 2016-12-6T15:55:57.536Z

>[!ENDSHADEBOX]

### [!UICONTROL addMonths (fecha; número)]

Devuelve una nueva fecha como resultado de añadir un número determinado de meses a una fecha. Para restar meses, introduzca un número negativo.

>[!BEGINSHADEBOX]

**Ejemplos:**

* `addMonths(2016-08-08T15:55:57.536Z;2)`

  Devuelve 2016-10-08T15:55:57.536Z

* `addMonths(2016-08-08T15:55:57.536Z;-2)`

  Devuelve 2016-06-08T15:55:57.536Z

>[!ENDSHADEBOX]

### [!UICONTROL addYears (fecha; número)]

Devuelve una nueva fecha como resultado de añadir un número determinado de años a una fecha. Para restar años, introduzca un número negativo.

>[!BEGINSHADEBOX]

**Ejemplos:**

* `addYears(2016-08-08T15:55:57.536Z;2)`

  Devuelve 2018-08-08T15:55:57.536Z

* `addYears(2016-12-08T15:55:57.536Z; -2)`

  Devuelve 2014-08-08T15:55:57.536Z

>[!ENDSHADEBOX]

### [!UICONTROL setSecond (fecha; número)]

Esta función devuelve una nueva fecha con los segundos especificados en parámetros.

Especifique un número del 0 al 59. Si el número está fuera de ese intervalo, la función devuelve un segundo desde el minuto anterior (para un número negativo) o un minuto posterior (para un número positivo).

Si necesita especificar un número fuera del intervalo, le recomendamos que utilice [!UICONTROL &#x200B; addSeconds], tal como se ha descrito anteriormente en la sección [addSeconds (fecha; número)](#addseconds-date-number).

>[!BEGINSHADEBOX]

**Ejemplos:**

* `setSecond(2015-10-07T11:36:39.138Z;10)`

  Devuelve 2015-10-07T11:36:10.138Z

* `setSecond(2015-10-07T11:36:39.138Z; 61)`

  Devuelve 2015-10-07T11:37:01.138Z

>[!ENDSHADEBOX]

### [!UICONTROL setMinute (fecha; número)]

Esta función devuelve una nueva fecha con los minutos especificados en los parámetros.

Especifique un número del 0 al 59. Si el número está fuera de ese intervalo, la función devuelve un minuto desde la hora anterior (para un número negativo) o una hora posterior (para un número positivo).

Si necesita especificar un número fuera del intervalo, le recomendamos que utilice addMinutes, tal como se ha descrito anteriormente en [addMinutes (fecha; número)](#addminutes-date-number).

>[!BEGINSHADEBOX]

**Ejemplos:**

* `setMinute(2015-10-07T11:36:39.138Z;10)`

  Devuelve 2015-10-07T11:10:39.138Z

* `setMinute(2015-10-07T11:36:39.138Z;61)`

  Devuelve 2015-10-07T12:01:39.138Z

>[!ENDSHADEBOX]

### [!UICONTROL setHour (fecha; número)]

Esta función devuelve una nueva fecha con la hora especificada en parámetros.

Especifique un número del 0 al 23. Si el número está fuera de este intervalo, la función devuelve una hora desde el día anterior (para un número negativo) o un día posterior (para un número positivo).

Si necesita especificar un número fuera del intervalo, le recomendamos que utilice addHours, tal como se ha descrito anteriormente en [addHours (fecha; número)](#addhours-date-number).

>[!BEGINSHADEBOX]

**Ejemplos:**

* `setHour(2015-08-07T11:36:39.138Z;6)`

  Devuelve 2015-08-07T06:36:39.138Z

* `setHour(2015-08-07T11:36:39.138;-6)`

  Devuelve 2015-08-06T18:36:39.138Z

>[!ENDSHADEBOX]

### [!UICONTROL setDay (fecha; número/nombre del día en inglés)]

Esta función devuelve una nueva fecha con el día especificado en parámetros.

Puede utilizar esta función para establecer el día de la semana, con el domingo como 1 y el sábado como 7. Si especifica un número del 1 al 7, la fecha resultante se encuentra dentro de la semana actual (de domingo a sábado). Si el número está fuera de ese intervalo, la función devuelve un día de la semana anterior (para un número negativo) o de la semana siguiente (para un número positivo).

Si necesita especificar un número fuera del intervalo, le recomendamos que utilice addDays, tal como se ha descrito anteriormente en [addDays (fecha; número)](#adddays-date-number).

>[!BEGINSHADEBOX]

**Ejemplos:**

* `setDay(2018-06-27T11:36:39.138Z;Monday)`

  Devuelve 2018-06-25T11:36:39.138Z

* `setDay(2018-06-27T11:36:39.138Z;1)`

  Devuelve 2018-06-24T11:36:39.138Z

* `setDay(2018-06-27T11:36:39.138Z;7)`

  Devuelve 2018-06-30T11:36:39.138Z

>[!ENDSHADEBOX]

### [!UICONTROL setDate (fecha; número)]

Esta función devuelve una nueva fecha con el día del mes especificado en parámetros.

Especifique un número del 1 al 31. Si el número está fuera de este intervalo, la función devuelve un día del mes anterior (para un número negativo) o del mes siguiente (para un número positivo).

>[!BEGINSHADEBOX]

**Ejemplos:**

* `setDate(2015-08-07T11:36:39.138Z;5)`

  Devuelve 2015-08-05T11:36:39.138Z

* `setDate(2015-08-07T11:36:39.138Z;32)`

  Devuelve 2015-09-01T11:36:39.138Z

>[!ENDSHADEBOX]

### [!UICONTROL setMonth (date; number/name of the month in English)]

Esta función devuelve una nueva fecha con el mes especificado en parámetros.

Especifique un número del 1 al 12. Si el número está fuera de este intervalo, la función devuelve el mes del año anterior (para un número negativo) o del año siguiente (para un número positivo).

>[!BEGINSHADEBOX]

**Ejemplos:**

* `setMonth(2015-08-07T11:36:39.138Z;5)`

  Devuelve 2015-05-07T11:36:39.138Z

* `setMonth(2015-08-07T11:36:39.138Z;17)`

  Devuelve 2016-05-07T11:36:39.138Z

* `setMonth(2015-08-07T11:36:39.138Z;january)`

  Devuelve 2015-01-07T12:36:39.138Z

>[!ENDSHADEBOX]

### [!UICONTROL setYear (date; number)]

Devuelve una nueva fecha con el año especificado en parámetros.

>[!BEGINSHADEBOX]

**Ejemplo:**

* `setYear(2015-08-07T11:36:39.138Z;2017)`

  Devuelve 2017-08-07T11:36:39.138Z

>[!ENDSHADEBOX]

### [!UICONTROL formatDate (date; format; [timezone])]

Utilice esta función cuando tenga un valor Fecha, como `12-10-2021 20:30`, al que desee dar formato como valor Texto, como `Dec 10, 2021 8:30 PM`.

Esto resulta útil, por ejemplo, cuando se necesita cambiar el formato de fecha de una aplicación o servicio web al de una aplicación o servicio web conectado en el mismo escenario.

Para obtener más información, consulte Fecha y texto en el artículo [Tipos de datos de elementos](/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md).

#### Parámetros

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Parámetro</th> 
   <th>Tipo de datos esperado* </th> 
   <th>Qué hace</th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL date] </td> 
   <td>Fecha </td> 
   <td> <p>Convierte un valor Fecha en un valor Texto. </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL format] </td> 
   <td>Texto </td> 
   <td> <p>Permite especificar un formato mediante tokens de formato de fecha y hora. Para obtener más información, vea <a href="/help/workfront-fusion/references/mapping-panel/functions/tokens-for-date-and-time-formatting.md" class="MCXref xref">Tokens para el formato de fecha y hora</a>.</p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Ejemplo: </b></span></span><code>DD.MM.YYYY HH:mm</code> </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL timezone] </td> 
   <td>Texto </td> 
   <td> <p>(Opcional) Permite especificar la zona horaria utilizada para la conversión. </p> <p>Para obtener la lista de zonas horarias reconocidas, consulte la columna “Nombre de la base de datos TZ” en <a href="https://en.wikipedia.org/wiki/List_of_tz_database_time_zones">Lista de zonas horarias de la base de datos TZ</a> de la Wikipedia. La función solo reconoce como zonas horarias válidas los valores enumerados en esta columna. Se ignora cualquier otro valor y se utiliza la zona horaria de escenarios especificada en su perfil. </p> <p>Si omite este parámetro, se aplica la zona horaria de escenarios especificada en la configuración del perfil. </p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Ejemplo: </b></span></span><code>Europe/Prague</code>, <code>UTC</code></p> </td> 
  </tr> 
 </tbody> 
</table>

Si se proporciona un tipo diferente, se aplica la coerción de tipos. Para obtener más información, vea [Coerción de tipos](/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md).

#### Valor y tipo devueltos

La función `formatDate` devuelve una representación de texto del valor Fecha en cuestión, según el formato y la zona horaria especificados. El tipo de datos es Texto.

>[!BEGINSHADEBOX]

**Ejemplos:** El escenario y la zona horaria web se han establecido en `Europe/Prague` en estos ejemplos.

![Ejemplo de función de fecha y hora](assets/date&time-functions-examples-350x61.png)

* `formatDate(1. Date created;MM/DD/YYYY)`

  Devuelve 10/01/2018

* `formatDate(1. Date created; YYYY-MM-DD hh:mm A)`

  Devuelve 2018-10-01 09:32 AM

* `formatDate(1. Date created;DD.MM.YYYY HH:mm;UTC)`

  Devuelve 01.10.2018 07:32

* `formatDate(now;DD.MM.YYYY HH:mm)`

  Devuelve 19.03.2019 15:30

>[!ENDSHADEBOX]

### [!UICONTROL parseDate (texto; formato; [zona horaria])]

Utilice esta función cuando tenga un valor de texto que represente una fecha (como `12-10-2019 20:30` o `Aug 18, 2019 10:00 AM`) y desee convertirlo (analizarlo) en un valor de fecha (una representación binaria legible por máquina). Para obtener más información, consulte Fecha y texto en el artículo [Tipos de datos de elementos](/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md).

#### Parámetros

La segunda columna indica el tipo esperado. Si se proporciona un tipo diferente, se aplica la coerción de tipos. Para obtener más información, vea [Coerción de tipos](/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Parámetro</th> 
   <th>Tipo de datos esperado* </th> 
   <th>Qué hace</th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL text] </td> 
   <td>Texto </td> 
   <td> <p>Convierte un valor Fecha en un valor Texto. </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL format] </td> 
   <td>Texto </td> 
   <td> <p>Permite especificar un formato mediante tokens de formato de fecha y hora. Para obtener más información, vea <a href="/help/workfront-fusion/references/mapping-panel/functions/tokens-for-date-and-time-formatting.md" class="MCXref xref">Tokens para el formato de fecha y hora</a>.</p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Ejemplo: </b></span></span><code>DD.MM.YYYY HH:mm</code> </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL timezone] </td> 
   <td>Texto </td> 
   <td> <p>(Opcional) Permite especificar la zona horaria utilizada para la conversión. </p> <p>Para obtener la lista de zonas horarias reconocidas, consulte la columna “Nombre de la base de datos TZ” en <a href="https://en.wikipedia.org/wiki/List_of_tz_database_time_zones">Lista de zonas horarias de la base de datos TZ</a> de la Wikipedia. La función solo reconoce como zonas horarias válidas los valores enumerados en esta columna. Se ignora cualquier otro valor y se utiliza la zona horaria de escenarios especificada en su perfil. </p> <p>Si omite este parámetro, se aplica la zona horaria de escenarios especificada en la configuración del perfil.</p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Ejemplo: </b></span></span><code>Europe/Prague</code>, <code>UTC</code></p> </td> 
  </tr> 
 </tbody> 
</table>

Si se proporciona un tipo diferente, se aplica la coerción de tipos. Para obtener más información, vea [Coerción de tipos](/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md).

#### Valor y tipo devueltos

Esta función convierte una cadena de texto en una fecha, según el formato y la zona horaria que haya especificado. El tipo de datos del valor es Fecha.

>[!BEGINSHADEBOX]

**Ejemplos:** en los ejemplos siguientes, el valor Fecha devuelto se expresa según la norma ISO 8601, pero el tipo de datos del resultado es Fecha.

* `parseDate(2016-12-28;YYYY-MM-DD)`

  Devuelve 2016-12-28T00:00:00.000Z

* `parseDate(2016-12-28 16:03;YYYY-MM-DD HH:mm)`

  Devuelve 2016-12-28T16:03:00.000Z

* `parseDate(2016-12-28 04:03 pm; YYYY-MM-DD hh:mm a)`

  Devuelve 2016-12-28T16:03:06.000Z

* `parseDate(1482940986;X)`

  Devuelve 2016-12-28T16:03:06.000Z

>[!ENDSHADEBOX]

### [!UICONTROL dateDifference (Date1; Date2; Unidad)]

Devuelve un número que representa la diferencia entre las dos fechas, expresado en la unidad especificada.

Date2 se resta a Date1.

Utilice uno de los siguientes valores de tiempo para el parámetro `unit`:

* milisegundos
* segundos
* minutos
* horas
* días
* semanas
* meses

Si no se especifica ninguna unidad, la función devuelve la diferencia en milisegundos.

>[!BEGINSHADEBOX]

**Ejemplos:**

* `dateDifference(2021-05-11T18:10:00.000Z;2021-05-11T18:00:00.000Z)`

  Devuelve `600,000`

* `dateDifference(2021-05-11T18:10:00.000Z;2021-05-11T18:00:00.000Z;hours)`

  Devuelve `4`

* `dateDifference2021-06-11T18:10:00.000Z;2021-05-11T18:00:00.000Z;months)`

  Devuelve `1`

>[!ENDSHADEBOX]

### Ejemplos adicionales

#### Cómo calcular el enésimo día de la semana en un mes

Esta sección está adaptada para [!DNL Workfront Fusion] de la página web [!DNL Exceljet] que explica cómo obtener el enésimo día de la semana de un mes.

Si necesita calcular una fecha correspondiente al enésimo día de la semana del mes (por ejemplo, primer martes, tercer viernes, etc.), puede utilizar la siguiente fórmula:

![Calcular n.º día](assets/date&time-functions-calc-nth-day-350x31.png)

```
{{addDays(setDate(1.date; 1); 1.n * 7 - formatDate(addDays(setDate(1.date; 1); "-" + 1.dow); "E"))}}
```

La fórmula contiene los siguientes elementos:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td><code>1.n</code> </td> 
   <td> <p> Enésimo día:</p> 
    <ul> 
     <li><code>1</code> para el primer martes</li> 
     <li><code>2</code> para el segundo martes</li> 
     <li><code>3</code> para el tercer martes, y así sucesivamente</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><code>2.dow</code> </td> 
   <td> <p> día de la semana:</p> 
    <ul> 
     <li><code>1</code> para el lunes</li> 
     <li><code>2</code> para el martes</li> 
     <li><code>3</code> para el miércoles</li> 
     <li><code>4</code> para el jueves</li> 
     <li><code>5</code> para el viernes</li> 
     <li><code>6</code> para el sábado</li> 
     <li><code>7</code> para el domingo</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><code>1.date</code> </td> 
   <td> <p> La fecha determina el mes. Para calcular el enésimo día de la semana del mes actual, utilice la variable <code>now</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

Si desea calcular solamente un caso específico, por ejemplo, cada segundo miércoles, puede reemplazar los elementos `1.n` y `2.dow` de la fórmula con los números correspondientes. Para el segundo miércoles del mes actual, se utilizarían los siguientes valores:

* `1.n` = `2`
* `1.dow` = `3`
* `1.date` = `now`

![Valor de variable de noveno día](assets/nth-day-variable-value-350x33.png)

#### Explicación:

* `setDate(now;1)` devuelve el primer día del mes actual
* `formatDate(....;E)` devuelve el día de la semana (1, 2, ... 6)

### Cálculo de días entre fechas

Una posibilidad es utilizar la siguiente expresión:

![Calcular días entre fechas](assets/calculate-days-between-dates-350x68.png)

```
{{round((2.value - 1.value) / 1000 / 60 / 60 / 24)}}
```

>[!NOTE]
>
>* Los valores de `D1` y `D2` deben ser valores de tipo Fecha. Si son valores de tipo cadena (por ejemplo, 20.10.2018), utilice la función `parseDate()` para convertirlos en valores de tipo fecha.
>
>* La función `round()` se usa para casos en los que una de las fechas se encuentra dentro del período de horario de verano y la otra no. En estos casos, la diferencia de horas es de una hora menos o más. Puede dividirlo entre 24 para obtener un resultado que no sea entero. Pierde una hora de horario de verano. El redondeo lo iguala para que no tenga ningún porcentaje

#### Cómo calcular el último día/milisegundo del mes

Cuando se especifica un intervalo de fechas, por ejemplo, en un módulo de búsqueda, si el intervalo abarca todo el mes anterior como un intervalo cerrado (el intervalo que incluye ambos puntos límite), se debe calcular el último día del mes.

01-09-2019 ≤ D ≤ 30-09-2019

La fórmula siguiente muestra una forma de calcular el último día del mes anterior:

![Último día del mes anterior](assets/last-day-prev-month.png)

```
{{addDays(setDate(now; 1); -1)}}
```

En algunos casos, debe calcular no solo el último día del mes, sino literalmente su último milisegundo:

2019-09-01T00:00:00.000Z ≤ D ≤ 2019-09-30T23:59:59.999Z

Esta fórmula muestra una forma de calcular el último milisegundo del mes anterior:

![Último milisegundo del mes anterior](assets/last-millisecond-prev-month-350x45.png)

```
{{parseDate(parseDate(formatDate(now; "YYYYMM01"); "YYYYMMDD"; "UTC") - 1; "x")}}
```

Si necesita que el resultado utilice la configuración de zona horaria, omita el argumento UTC:

![Omitir UTC](assets/omit-utc-argument-350x45.png)

`{{parseDate(parseDate(formatDate(now; "YYYYMM01"); "YYYYMMDD") - 1; "x")}}`

Sin embargo, es preferible utilizar el intervalo de semiapertura en su lugar (el intervalo que excluye uno de sus puntos límite), especificando el primer día del mes siguiente en su lugar y sustituyendo el operador &quot;menor o igual que&quot; por &quot;menor que&quot; de la siguiente manera:

`2019-09-01 ≤ D < 2019-10-01`

`2019-09-01T00:00:00.000Z ≤ D < 2019-10-01T00:00:00.000Z`
