---
name: add-mini-tocs
description: ""
source-git-commit: 4ec81401b5a76edd620b9779414ee578966b4315
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---


# Añadir mini índice

Analiza un archivo Markdown e inserta una mini tabla de contenido debajo de cada encabezado correspondiente que tenga subencabezados directos.

## Flujo de trabajo

1. Lea el archivo de destino.
2. Identifique todos los encabezados de `##` nivel o más profundo que tengan al menos un encabezado secundario directo (un nivel de `#` más profundo).
3. Para cada uno de estos encabezados principales, cree una lista con viñetas de vínculos únicamente a sus elementos secundarios directos.
4. Inserte la lista inmediatamente antes del primer encabezado secundario, después de cualquier texto introductorio que siga al encabezado principal.
5. Si ya existe una mini TDC en esa posición, compárela con los encabezados secundarios actuales de esa sección. Si la lista no está actualizada (faltan entradas, entradas adicionales o vínculos incorrectos), sustitúyala por la lista actualizada. Si ya coincide, omita.
6. Escriba el archivo actualizado.

## Ámbito

- **Nunca** cree un mini índice bajo el título de artículo de `#`. Los mini índices solo se agregan bajo `##` encabezados y más profundos.
- Un encabezado de `##` obtiene una lista de sus `###` elementos secundarios directos.
- Un encabezado de `###` obtiene una lista de sus `####` elementos secundarios directos.
- Y así sucesivamente para niveles más profundos.

## Formato de vínculo

Cada entrada de la lista utiliza este formato exacto:

```
* [Heading text](#anchor)
```

### Anclar reglas de generación

Convierta el texto del encabezado en un anclaje como se indica a continuación:

1. Poner todo el texto en minúsculas.
2. Elimine los caracteres que no sean letras, números, espacios o guiones.
3. Reemplace los espacios por guiones.
4. Elimine cualquier formato de código ajustado con acento grave (mantenga el texto dentro).

Ejemplo: `### Create or edit a function` → `#create-or-edit-a-function`

## Anidado de reglas

- Solo vincule **elementos secundarios directos** (un nivel más profundo que el elemento principal) en cada lista.
- No incluya nietos ni encabezados más profundos en la misma lista.
- Si esos encabezados secundarios tienen elementos secundarios, se inserta su propio mini TOC debajo de ellos.

**Estructura de ejemplo:**

```
## Manage a package          ← parent: gets a list of ### headings
### Functions                ← child of ##, parent of ####: gets a list of #### headings
#### Create a function       ← child of ###
#### Delete a function       ← child of ###
### Variables                ← child of ##
### History                  ← child of ##
```

Resultados en:

En `## Manage a package`:

```
* [Functions](#functions)
* [Variables](#variables)
* [History](#history)
```

En `### Functions`:

```
* [Create a function](#create-a-function)
* [Delete a function](#delete-a-function)
```

## Ubicación

Inserte la mini lista de índice inmediatamente antes del primer encabezado secundario. Si hay texto introductorio entre el encabezado principal y el primer encabezado secundario, la lista va después de ese texto, directamente encima del primer encabezado secundario. Incluya siempre una línea en blanco antes y después de la mini lista de índice.

## Qué omitir

- `#` encabezados (el título del artículo): no agregue nunca una mini TDC aquí.
- Encabezados principales con un solo elemento secundario directo: omitir: una lista de un solo elemento no agrega ningún valor de navegación.
- Secciones sin encabezados secundarios: omitir.
