---
title: Resumen de asignación
description: La asignación es el proceso de asignar los resultados de un módulo, estructurados en elementos, a los campos de entrada de otro módulo.
author: Becky
feature: Workfront Fusion
exl-id: 9208ce20-0757-427a-9669-ce4274d05522
source-git-commit: 190bfe5992fb21b789a7246c4ae732a5dc7672fa
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 14%

---

# Resumen de asignación

La asignación es el proceso de asignar los resultados de un módulo a los campos de entrada de otro módulo.

La operación de un módulo produce cero, uno o más paquetes como salida. Un paquete consta de uno o más elementos.

Puede asignar estos elementos a campos en módulos posteriores.

Al hacer clic en un campo en el que puede insertar un valor generado desde un módulo anterior en un escenario, se muestra el panel Asignación. Aquí puede seleccionar el elemento que desea asignar. Una asignación puede incluir uno o más de los siguientes elementos:

* Un solo elemento
* Varios elementos
* Texto estático
* Funciones 

>[!BEGINSHADEBOX]

**Ejemplos**:

Elemento único

![](assets/map-single.png)

Varios elementos con texto

![](assets/map-multiple-with-text.png)

Función con varios elementos y texto

![](assets/map-formula-with-text.png)


>[!ENDSHADEBOX]


Para obtener instrucciones sobre la asignación, vea los artículos en [Asignar datos: índice de artículo](/help/workfront-fusion/create-scenarios/map-data/map-data-toc.md).

>[!NOTE]
>
>No se puede obtener acceso a las salidas de módulos ajustados entre [!UICONTROL Iterator] y [!UICONTROL Aggregator] más allá del módulo [!UICONTROL Aggregator].

## El panel de asignación

Cuando hace clic en un campo donde puede asignar datos, se abre el panel de asignación.

La primera pestaña ![](assets/toolbar-icon-functions-you-map-from-other-modules.png) muestra los elementos que puede asignar desde otros módulos.

Las otras fichas incluyen funciones, operadores y palabras clave que puede utilizar para crear fórmulas. Se ordenan en diferentes pestañas según el tipo de datos que administran.

![](assets/mapping-panel-blank.png)


Para obtener más información sobre las fichas de funciones, vea [Descripción general de las funciones](/help/workfront-fusion/get-started-with-fusion/understand-fusion/function-overview.md).

Para obtener más información sobre la asignación de elementos mediante funciones, vea [Asignar elementos mediante funciones](/help/workfront-fusion/create-scenarios/map-data/map-using-functions.md).

## Colecciones

Los elementos pueden contener varios valores de varios tipos. Son elementos de tipo colección.

Los paquetes de tipo colección muestran `(Collection)` junto a la etiqueta del paquete en la salida del módulo.

![](assets/collection.png)

En la mayoría de los casos, se asignan los elementos de la colección en lugar de asignar el elemento que representa la colección completa.

Para localizar el elemento de una colección en el panel de asignación, haga clic en la flecha situada junto a la colección.

![](assets/collection-dropdown.png)

Para obtener más información sobre las colecciones, vea [Tipos de datos de elementos](/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md).

Para obtener instrucciones sobre cómo asignar colecciones, vea [Asignar un elemento](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md#map-an-item) en el artículo Asignar información de un módulo a otro.

## Matrices

Los elementos pueden contener varios valores del mismo tipo. Son elementos de tipo matriz.

Los paquetes de tipo matriz muestran `(Array)` junto a la etiqueta del paquete en la salida del módulo.

En el panel de asignación, las matrices se muestran con corchetes. Puede identificar un elemento de tipo matriz por los corchetes al final de la etiqueta del elemento. Para localizar un elemento de matriz específico en el panel Asignación, haga clic en la flecha situada junto a la matriz.

![](assets/array.png)

Para obtener información e instrucciones sobre cómo asignar matrices y elementos de matriz, vea [Asignar matrices y elementos de matriz](/help/workfront-fusion/create-scenarios/map-data/map-an-array.md).
