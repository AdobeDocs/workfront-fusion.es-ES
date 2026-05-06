---
title: Variables matemáticas
description: Las siguientes variables matemáticas están disponibles en el panel de [!DNL Adobe Workfront Fusion mapping] .
author: Becky
feature: Workfront Fusion
exl-id: b309f035-4d46-473b-b915-6938587b0bcf
source-git-commit: e11e581c092ebba343a0f2d6943ecbe4d0fe4c87
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 100%

---

# Variables matemáticas

## pi

Representa el símbolo matemático $\pi$.

## [!UICONTROL random]

Devuelve un número pseudoaleatorio de coma flotante en el rango [`0`,`1`] (que incluye `0`, pero no `1`).

Utilice la siguiente fórmula para generar un número pseudoaleatorio entero en el rango [`min`,`max`] (que incluye `min` y `max`):

![Random](assets/math-variable-random-350x61.png)

```
floor(random * (1.max - 1.min + 1)) + 1.min
```
