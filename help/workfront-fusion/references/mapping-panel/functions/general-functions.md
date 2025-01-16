---
title: Funciones generales
description: Las siguientes funciones generales están disponibles en el panel de asignación de Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 6d4b8801-aa7e-47d4-80b3-aceac10c073f
source-git-commit: 2c732659f3f3e81e13b7b12a5df5bde19c0e0928
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 8%

---

# Funciones generales

## [!UICONTROL get (object or array; path)]

Devuelve la ruta de valor de un objeto o matriz. Para acceder a objetos anidados, utilice la notación de puntos. El primer elemento de una matriz es el índice 1.

>[!BEGINSHADEBOX]

**Ejemplos:**

* `get( array ; 1 + 1 )`
* `get( array ; 5.raw_name )`
* `get( object ; raw_name )`
* `get( object ; raw_name.sub_raw_name )`

>[!ENDSHADEBOX]

## [!UICONTROL if (expression; value1; value2)]

Devuelve `value1` si la expresión se evalúa como verdadera; en caso contrario, devuelve `value2`.

Para crear una instrucción if que devuelva un valor sólo si dos o más expresiones se evalúan como true, utilice la palabra clave `and`.

Para combinar instrucciones `if`, use los operadores `and` y `or`.

![y operador](assets/and-in-if-statement.png)

>[!BEGINSHADEBOX]

**Ejemplos:**

* `if( 1 = 1 ; A ; B )`

  Devuelve un

* `if( 1 = 2 ; A ; B )`

  Devuelve B

* `if( 1 = 2 and 1 = 2 ; A ; B )`

  Devuelve B

>[!ENDSHADEBOX]

## [!UICONTROL ifempty (value1; value2)]

Devuelve `value1` si este valor no está vacío; en caso contrario, devuelve `value2`.

>[!BEGINSHADEBOX]

**Ejemplos:**

* `ifempty(` `A` `;` `B` )

  Devuelve un

* `ifempty(` `unknown` `;` `B` )

  Devuelve B

* `ifempty(` `""` `;` `B` )

  Devuelve B

>[!ENDSHADEBOX]

## [!UICONTROL switch (expression; value1; result1; [value2; result2; ...]; [else])]

Evalúa un valor (denominado expresión) frente a una lista de valores; devuelve el resultado correspondiente al primer valor coincidente. Para incluir un valor `else`, agréguelo después de la expresión o valor final.

>[!BEGINSHADEBOX]

**Ejemplos:**

* `switch( B ; A ; 1 ; B ; 2 ; C ; 3 )`

  Devuelve 2

* `switch( C ; A ; 1 ; B ; 2 ; C ; 3 )`

  Devuelve 3

* `switch( X ; A ; 1 ; B ; 2 ; C ; 3 ; 4 )`

  Devuelve 4

  En esta función, 4 es el valor que se devuelve si no se aplica ninguna expresión (el valor `else`).

>[!ENDSHADEBOX]

## [!UICONTROL omit(object; key1; [key2; ...])]

Omite las claves dadas del objeto y devuelve el resto.

>[!BEGINSHADEBOX]

**Ejemplo:**

`omit(` Usuario `;` contraseña `)`

Devuelve una colección de información del usuario, excluida la contraseña.

>[!ENDSHADEBOX]

## [!UICONTROL pick(object; key1; [key2; ...])]

Selecciona solo las claves dadas del objeto.

>[!BEGINSHADEBOX]

**Ejemplo:**

`pick(` Usuario `;` contraseña `;` correo electrónico `)`

Devuelve una colección que incluye únicamente la contraseña y la dirección de correo electrónico del usuario.

>[!ENDSHADEBOX]

## mergeCollections(colección1; colección2)

Combina dos colecciones combinando sus pares clave-valor. Si ambas colecciones contienen la misma clave, el valor de la segunda colección sobrescribe ese valor de la primera colección.
