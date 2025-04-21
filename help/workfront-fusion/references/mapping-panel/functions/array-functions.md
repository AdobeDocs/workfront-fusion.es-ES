---
title: Funciones de matriz
description: Las siguientes funciones de matriz están disponibles en el panel de asignación de Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 16c3915c-add1-4aab-a0e1-75fc590c42a6
source-git-commit: d141738a7e013ed817cb657b883fc5e1061e2165
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 88%

---

# Funciones de matriz

## [!UICONTROL join (array; separator)]

Concatena todos los elementos de una matriz en una cadena, utilizando el separador especificado entre cada elemento.

## [!UICONTROL length (array)]

Devuelve el número de elementos de una matriz.

## [!UICONTROL keys (object)]

Devuelve una matriz de las propiedades de un objeto o matriz determinados.

## [!UICONTROL slice (array; start; [end])]

Devuelve una nueva matriz que contiene solo los elementos seleccionados.

## [!UICONTROL merge (array1; array2; ...)]

Combina una o más matrices en una matriz.

## [!UICONTROL contains (array; value)]

Comprueba si una matriz contiene el valor.

## [!UICONTROL remove (array; value1; value2; ...)]

Quita los valores especificados en los parámetros de una matriz. Esta función solo es efectiva en matrices primitivas de texto o números.

## [!UICONTROL add (array; value1; value2; ...)]

Añade los valores especificados en parámetros a una matriz y devuelve esa matriz.

## [!UICONTROL map (complex array; key;[key for filtering];[possible values for filtering])]

Devuelve una matriz primitiva que contiene los valores de una matriz compleja. Esta función permite filtrar valores. Utilice nombres de variables sin procesar para las claves.

>[!BEGINSHADEBOX]

**Ejemplos:**

* `map(Emails[];email)`

  Devuelve una matriz primitiva con correos electrónicos

* `map(Emails[];email;label;work;home)`

  Devuelve una matriz primitiva con correos electrónicos que tienen una etiqueta igual a trabajo o inicio

>[!ENDSHADEBOX]

Para obtener más información, vea [Asignar una matriz o elemento de matriz](/help/workfront-fusion/create-scenarios/map-data/map-an-array.md).

## shuffle

## [!UICONTROL sort (array; [order]; [key])]

Ordena los valores de una matriz. Los valores válidos del parámetro `order` son los siguientes:

* `asc`

  (predeterminado): orden ascendente: 1, 2, 3, ... para el tipo Número. A, B, C, a, b, c, ... para el tipo Texto

* `desc`

  orden descendente: ..., 3, 2, 1 para el tipo Número. ..., c, b, a, C, B, A para el tipo Texto.

* `asc ci`

  orden ascendente sin distinción de mayúsculas y minúsculas: A, a, B, b, C, c, ... para el tipo Texto.

* `desc ci`

  orden descendente sin distinción de mayúsculas y minúsculas: ..., C, c, B, b, A, a para el tipo Texto.

Utilice el parámetro `key` para tener acceso a las propiedades de objetos complejos.

Utilice nombres de variables sin procesar para las claves.

Para acceder a las propiedades anidadas, utilice la notación de puntos.

El primer elemento de una matriz es el índice 1.

>[!BEGINSHADEBOX]

**Ejemplos:**

* `sort(Contacts[];name)`

  Ordena una matriz de contactos por la propiedad &quot;name&quot; en orden ascendente predeterminado

* `sort(Contacts[];desc;name)`

  Ordena una matriz de contactos por la propiedad &quot;name&quot; en orden descendente

* `sort(Contacts[];asc ci;name)`

  Ordena una matriz de contactos por la propiedad “name” en orden ascendente sin distinción de mayúsculas y minúsculas

* `sort(Emails[];sender.name)`

  Ordena una matriz de correos electrónicos por la propiedad “sender.name”

>[!ENDSHADEBOX]

## [!UICONTROL reverse (array)]

El primer elemento de la matriz se convierte en el último elemento, el segundo en el último, etc.

## [!UICONTROL flatten (array)]

Crea una nueva matriz con todos los elementos de submatriz concatenados en ella, de forma recursiva, hasta la profundidad especificada.

## [!UICONTROL distinct (array; [key])]

Elimina los duplicados dentro de una matriz. Utilice el argumento &quot;[!UICONTROL key]&quot; para tener acceso a las propiedades de objetos complejos. Para acceder a las propiedades anidadas, utilice la notación de puntos. El primer elemento de una matriz es el índice 1.

>[!BEGINSHADEBOX]

**Ejemplo:**`distinct(Contacts[];name)`

Elimina los duplicados dentro de una matriz de contactos comparando la propiedad “name”

>[!ENDSHADEBOX]

## toCollection

* Esta función toma una matriz que contiene pares de clave-valor y la convierte en una colección. La función tiene tres argumentos:

* (matriz) que contiene pares de valor clave
* (cadena) el nombre del campo que se utilizará como clave
* (cadena) el nombre del campo que se utilizará como valor

>[!BEGINSHADEBOX]

Ejemplo:

Dada una matriz:

```
[{"name":"Bob", "age":22}, {"name":"Tim", "age":23}]
```

y argumentos

```
{{toCollection(6.array; "name"; "age")}}
```

la función devuelve

```
{
    "Bob": 22,
    "Tim": 23
}
```

>[!ENDSHADEBOX]

## toArray

Esta función convierte una colección en una matriz de pares clave-valor.

>[!BEGINSHADEBOX]

**Ejemplos:**

Dada la colección

`{ key1: "value1", key2: "value2:}`

La función

`toArray({ key1: "value1", key2: "value2:})`

Devuelve la matriz de pares clave-valor

`[{ key1: "value1"}, { key2: "value2"}]`

>[!ENDSHADEBOX]

## [!UICONTROL arrayDifference [array1, array2, mode]]

Devuelve la diferencia entre dos matrices.

Introduzca uno de los siguientes valores para el parámetro `mode`.

* `classic`: devuelve una nueva matriz que contiene todos los elementos de `array1` que no existen en `array2`.

* `symmetric`: devuelve una matriz de elementos que no son comunes a ambas matrices.

  En otras palabras, la función devuelve una matriz que contiene todos los elementos de `array1` que no existen en `array2` y todos los elementos de `array2` que no existen en `array1`.

>[!BEGINSHADEBOX]

**Ejemplos:**

Dadas las siguientes matrices:

```
myArray = [1,2,3,4,5]
```

```
yourArray = [3,4,5,6,7]
```

* `arrayDifference [myArray, yourArray, classic]`

  Devuelve `[1,2]`

* `arrayDifference [yourArray, myArray, classic]`

  Devuelve `[6,7]`

* `arrayDifference [myArray, yourArray, symmetric]`

  Devuelve `[1,2,6,7]`

>[!ENDSHADEBOX]

## deDuplicate

## Keywords

## emptyarray
