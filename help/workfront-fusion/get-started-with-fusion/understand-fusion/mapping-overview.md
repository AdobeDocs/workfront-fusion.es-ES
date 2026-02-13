---
title: Información general sobre la asignación
description: La asignación es el proceso de asignar los resultados de un módulo, estructurados en elementos, a los campos de entrada de otro módulo.
author: Becky
feature: Workfront Fusion
exl-id: 9208ce20-0757-427a-9669-ce4274d05522
source-git-commit: 88147d0305595e1d0d388f510ed43fc5beaa4b64
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 96%

---

# Información general sobre la asignación

La asignación es el proceso de asignar los resultados de un módulo a los campos de entrada de otro módulo.

La operación de un módulo produce cero, uno o más paquetes como salida. Un paquete consta de uno o más elementos.

Puede asignar estos elementos a campos en módulos posteriores.

El panel de asignación se muestra al hacer clic en un campo en el que puede insertar un valor generado desde un módulo anterior en un escenario. Aquí puede seleccionar el elemento que desea asignar. Una asignación puede incluir uno o más de los siguientes elementos:

* Un solo elemento
* Varios elementos
* Texto estático
* Funciones 

>[!BEGINSHADEBOX]

**Ejemplos**:

Elemento único

![Asignar un solo elemento](assets/map-single.png)

Varios elementos con texto

![Asignar varios elementos](assets/map-multiple-with-text.png)

Función con varios elementos y texto

![Asignar fórmula con texto](assets/map-formula-with-text.png)


>[!ENDSHADEBOX]


Para obtener instrucciones sobre la asignación, consulte los artículos en [Asignar datos: índice de artículos](/help/workfront-fusion/create-scenarios/map-data/map-data-toc.md).

>[!NOTE]
>
>No se puede acceder a las salidas de módulos agrupados entre un [!UICONTROL Iterador] y [!UICONTROL Agregador] más allá del módulo [!UICONTROL Agregador].

## El panel de asignación

Cuando hace clic en un campo donde puede asignar datos, se abre el panel de asignación.

La primera pestaña ![Asignar desde otros módulos](assets/toolbar-icon-functions-you-map-from-other-modules.png) muestra los elementos que puede asignar desde otros módulos.

Las otras pestañas incluyen funciones, operadores y palabras clave que puede utilizar para crear fórmulas. Se ordenan en diferentes pestañas según el tipo de datos que gestionan.

![Panel de asignación](assets/mapping-panel-blank.png)


Para obtener más información sobre las pestañas de función, consulte [Información general sobre la función](/help/workfront-fusion/get-started-with-fusion/understand-fusion/function-overview.md).

Para obtener más información sobre la asignación de elementos mediante funciones, vea [Asignar elementos mediante funciones integradas](/help/workfront-fusion/create-scenarios/map-data/map-using-functions.md).

## Colecciones

Algunos elementos pueden contener múltiples valores de diversos tipos. Son elementos de tipo colección.

Los paquetes de tipo colección muestran `(Collection)` junto a la etiqueta del paquete en la salida del módulo.

![Colección](assets/collection.png)

En la mayoría de los casos, se asignan elementos de la colección en lugar de asignar el elemento que representa la colección completa.

Para localizar el elemento de una colección en el panel de asignación, haga clic en la flecha situada junto a la colección.

![Lista desplegable de colecciones](assets/collection-dropdown.png)

Para obtener más información sobre las colecciones, consulte [Tipos de datos de elementos](/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md).

Para obtener instrucciones sobre cómo asignar colecciones, consulte [Asignar un elemento](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md#map-an-item) en el artículo Asignar información de un módulo a otro.

## Matrices

Algunos elementos pueden contener varios elementos del mismo tipo. Son elementos de tipo matriz.

Los paquetes de tipo matriz muestran `(Array)` junto a la etiqueta del paquete en la salida del módulo.

En el panel de asignación, las matrices se muestran con corchetes. Puede identificar un elemento de tipo matriz por los corchetes al final de la etiqueta del elemento. Para localizar un elemento de matriz específico en el panel de asignación, haga clic en la flecha situada junto a la matriz.

![Matriz](assets/array.png)

Para obtener información e instrucciones sobre cómo asignar matrices y elementos de matriz, consulte [Asignar matrices y elementos de matriz](/help/workfront-fusion/create-scenarios/map-data/map-an-array.md).
