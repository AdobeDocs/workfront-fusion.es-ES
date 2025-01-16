---
title: Funciones matemáticas
description: Las siguientes funciones matemáticas están disponibles en el panel de asignaciones de Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 3d08b09d-b395-4226-b7e3-d5650c428a59
source-git-commit: 24a6c1558fd6349c022df8a1847a7f39fafddd67
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 97%

---

# Funciones matemáticas

## [!UICONTROL average ([array of values]) average(value1; [value2], ...)]

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

## [!UICONTROL max ([array of values]), max(value1;value2; ...)]

Devuelve el número mayor de una matriz especificada o el número mayor entre los números introducidos individualmente.

## [!UICONTROL min ([array of values]), min(value1; value2; ...)]

Devuelve el número menor dentro de una matriz especificada o el número menor entre los números introducidos individualmente.

## [!UICONTROL round (number)]

Redondea al valor numérico entero más cercano

>[!BEGINSHADEBOX]

**Ejemplos**

* `round(` `1.2` `)`

  Devuelve 1

* `round(` `1.5` `)`

  Devuelve 2

* `round(` `1.7` `)`

  Devuelve 2

* `round(` `2` `)`

  Devuelve 2

>[!ENDSHADEBOX]

## [!UICONTROL sum ([array of values]), sum(value1; value2; ...)]

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
