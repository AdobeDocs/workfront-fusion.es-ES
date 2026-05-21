---
title: Funciones matemáticas
description: Las siguientes funciones matemáticas están disponibles en el panel de asignaciones de Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 3d08b09d-b395-4226-b7e3-d5650c428a59
TQID: https://experienceleague.adobe.com/a0WYFvPFBnXOvKS9ndQ-TD5xSvJz2bCbUbDY5VnXW0w
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 404
ht-degree: 62%

---

# Funciones matemáticas

## [!UICONTROL average ([matriz de valores]) average(value1; [value2], ...)]

Devuelve el valor promedio de los valores numéricos en una matriz específica o el valor promedio de los valores numéricos introducidos individualmente.

## [!UICONTROL ceil (number)]

Devuelve el valor entero menor que sea mayor o igual que un número especificado.

>[!BEGINSHADEBOX]

**Ejemplos:**

* `ceil(` `1.2` `)`

  Devuelve 2

* `ceil(` `4` `)`

  Devuelve 4

>[!ENDSHADEBOX]

## [!UICONTROL floor (number)]

Devuelve el valor entero más alto que sea menor o igual que un número especificado.

>[!BEGINSHADEBOX]

**Ejemplos:**

* `floor(` `1.2` `)`

  Devuelve 1

* `floor(` `1.9` `)`

  Devuelve 1

* `floor(` `4` `)`

  Devuelve 4

>[!ENDSHADEBOX]

## [!UICONTROL max ([matriz de valores]), max(value1;value2; ...)]

Devuelve el número mayor de una matriz especificada o el número mayor entre los números introducidos individualmente.

## [!UICONTROL min ([matriz de valores]), min(value1; value2; ...)]

Devuelve el número menor dentro de una matriz especificada o el número menor entre los números introducidos individualmente.

## [!UICONTROL round (number)]

Redondea al valor numérico entero más cercano

>[!BEGINSHADEBOX]

**Ejemplos:**

* `round(` `1.2` `)`

  Devuelve 1

* `round(` `1.5` `)`

  Devuelve 2

* `round(` `1.7` `)`

  Devuelve 2

* `round(` `2` `)`

  Devuelve 2

>[!ENDSHADEBOX]

## [!UICONTROL sum ([matriz de valores]), sum(value1; value2; ...)]

Devuelve la suma de los valores en una matriz especificada o la suma de los números introducidos individualmente.

## [!UICONTROL parseNumber (number; decimal separator)]

Analiza una cadena con un número y devuelve el número. Por ejemplo, parseNumber(1 756,456;,)

## [!UICONTROL formatNumber (number; decimalPOINTS; [decimalSeparator]; [thousandsSeparator])]

Devuelve un número en el formato solicitado. De forma predeterminada, el punto decimal es una coma (,) y el separador de miles es un punto (.).

>[!BEGINSHADEBOX]

**Ejemplo:**

`formatNumber( 123456789 ; 3 ; , ; . )`

Devuelve 123 456 789 000

>[!ENDSHADEBOX]

### [!UICONTROL abs(número)]

[!BADGE Nuevo!]{type=Informative}

Devuelve el valor absoluto de un número.

>[!BEGINSHADEBOX]

**Ejemplo:**

* `abs(-3.14)`

  Devuelve 3.14
* `abs(3.14)`

  Devuelve 3.14


### [!UICONTROL div(número1; número2; ...)]

[!BADGE Nuevo!]{type=Informative}

Divide todos los números en el orden proporcionado.

>[!BEGINSHADEBOX]

**Ejemplo:**

* `div(10; 2)`

  Devuelve 5
* `div(100; 5; 4)`

  Devuelve 5


### [!UICONTROL ln(número)]

[!BADGE Nuevo!]{type=Informative}

Devuelve el logaritmo natural del número.


>[!BEGINSHADEBOX]

**Ejemplo:**

* `ln(1)`

  Devuelve 0
* `ln(2.718281828)`

  Devuelve 1


### [!UICONTROL log(número1; número2)]

[!BADGE Nuevo!]{type=Informative}

Devuelve el logaritmo de `number2` en la base `number1`.

>[!BEGINSHADEBOX]

**Ejemplo:**

* `log(10; 100)`

  Devuelve 2
* `log(2; 8)`

  Devuelve 3


### [!UICONTROL número(cadena)]

[!BADGE Nuevo!]{type=Informative}

Convierte una cadena en un número.

>[!BEGINSHADEBOX]

**Ejemplo:**

* `number("3.14")`

  Devuelve 3.14
* `number("42")`

  Devuelve 42


### [!UICONTROL power(number; power)]

[!BADGE Nuevo!]{type=Informative}

Devuelve un número elevado a la potencia especificada.

>[!BEGINSHADEBOX]

**Ejemplo:**

* `power(2; 3)`

  Devuelve 8
* `power(4; 0.5)`

  Devuelve 2


### [!UICONTROL prod(número1; número2; ...)]

[!BADGE Nuevo!]{type=Informative}

Multiplica todos los números proporcionados juntos.

>[!BEGINSHADEBOX]

**Ejemplo:**

* `prod(2; 3; 4)`

  Devuelve 24
* `prod(5; 5)`

  Devuelve 25


### [!UICONTROL sortAscNum(número1; número2; ...)]

[!BADGE Nuevo!]{type=Informative}

Devuelve los números proporcionados ordenados en orden ascendente.

>[!BEGINSHADEBOX]

**Ejemplo:**

* `sortAscNum(3; 1; 2)`

  Devuelve \[1, 2, 3]
* `sortAscNum(5; 3; 4)`

  Devuelve \[3, 4, 5]


### [!UICONTROL sortDescNum(número1; número2; ...)]

[!BADGE Nuevo!]{type=Informative}

Devuelve los números proporcionados ordenados en orden descendente.

>[!BEGINSHADEBOX]

**Ejemplo:**

* `sortDescNum(3; 1; 2)`

  Devuelve \[3, 2, 1]
* `sortDescNum(5; 3; 4)`

  Devuelve \[5, 4, 3]


### [!UICONTROL sqrt(número)]

[!BADGE Nuevo!]{type=Informative}

Devuelve la raíz cuadrada de un número.

>[!BEGINSHADEBOX]

**Ejemplo:**

* `sqrt(9)`

  Devuelve 3
* `sqrt(4)`

  Devuelve 2


### [!UICONTROL sub(número1; número2; ...)]

[!BADGE Nuevo!]{type=Informative}

Resta todos los números en el orden proporcionado.

>[!BEGINSHADEBOX]

**Ejemplo:**

* `sub(10; 3; 2)`

  Devuelve 5
* `sub(20; 5)`

  Devuelve 15
