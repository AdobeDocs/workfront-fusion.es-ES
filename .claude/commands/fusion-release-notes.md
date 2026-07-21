---
name: fusion-release-notes
description: 'Cree una nueva página de notas de la versión semanales de Workfront Fusion y conéctela a la página de información general de la actividad de la versión y a la tabla de contenido. Utilícelo cuando el usuario desee escribir, añadir o redactar una nueva nota de versión de Fusion o una página de versión semanal, o solicite documentar las nuevas funciones de Fusion para una versión. No utilice para las notas de la versión de Workfront (Quicksilver) en anuncios/versiones de productos: utilice el formateador de notas de la versión para esas notas.'
source-git-commit: 59a8d8ee83906bc16fc627bd348accc4e588cf9b
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 1%

---


# Notas de la versión de Fusion

Crea una nueva página semanal de notas de la versión de Adobe Workfront **Fusion** en `help/workfront-fusion/fusion-product-releases/` y la vincula desde los dos lugares en los que se puede detectar: la página de información general sobre la actividad de la versión y `help/workfront-fusion/TOC.md`.

Este es un sistema diferente de las notas de la versión de Quicksilver (core Workfront) gestionadas por la aptitud `release-notes-formatter`:

| | Notas de la versión de Fusion (esta aptitud) | Notas de la versión de Quicksilver (`release-notes-formatter`) |
|---|---|---|
| Cadencia | Semanal | Trimestralmente |
| Directorio | `help/workfront-fusion/fusion-product-releases/fusion-releases-{YYYY}/` | `help/quicksilver/product-announcements/product-releases/` |
| Llamada de fecha por función | No — el título de la página lleva la semana | Sí: `>[!NOTE]` bloque por característica |
| Página de índice | `fusion-release-activity.md` (por año/mes) | `{YY}-q{N}-release-overview.md` (por trimestre) |

## Paso 1: Recopilar las funciones

Pida al usuario (si no se ha proporcionado ya) la lista de funciones/cambios en el documento para la semana y para cada uno de ellos:

- Un título de función corto
- Una descripción sencilla de lo que ha cambiado y por qué importa
- Los artículos de ayuda a los que se vincula (compruebe que la ruta existe; no lo adivine)
- Si requiere una acción de usuario/administrador o está en desuso (necesita una llamada de `>[!IMPORTANT]`)

## Paso 2: Determinar el nombre y la fecha del archivo

- Busque el lunes (o la fecha de lanzamiento) de la semana que se está documentando y confírmelo con el usuario si es ambiguo.
- Ruta de archivo: `help/workfront-fusion/fusion-product-releases/fusion-releases-{YYYY}/fusion-{YYYY}-{M}-{D}.md`
  - `{M}` y `{D}` tienen **ceros iniciales**: `fusion-2026-7-20.md`, no `fusion-2026-07-20.md`.
  - Si la carpeta Año aún no existe, créela.
- Compruebe si ya existe una página para esa semana antes de crear una nueva.

## Paso 3: escribir la página

### Frontmatter

```yaml
---
title: Workfront Fusion release activity Week of {Month} {Day}, {Year}
description: Workfront Fusion release activity Week of {Month} {Day}, {Year}
author: {Author}
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
hidefromtoc: true
---
```

Reglas:
- `title` y `description` son idénticos.
- Incluya siempre la coma en la fecha (`July 20, 2026`), aunque algunas páginas antiguas la omitan; no copie esa incoherencia.
- **Use `hidefromtoc: true` para cada nueva página. No agregue un(a) `exl-id` o `TQID`.** Estos se asignan más adelante una vez publicada la página; inventar una es erróneo. (Todas las páginas a partir de mediados de 2026 siguen este patrón; consulte `_fusion-release-notes-reference.md` si necesita ver un ejemplo).

### Cuerpo

```markdown
# Workfront Fusion release activity: Week of {Month} {Day}, {Year}

This page describes all enhancements made in Adobe Workfront Fusion the week of {Month} {Day}, {Year}.

For a list of all recent changes, see [Adobe Workfront Fusion release activity](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md).

For a list of recent bug fixes in Workfront Fusion, see the [Workfront Maintenance Updates](https://experienceleague.adobe.com/en/docs/workfront-known-issues/releases/current-updates) page and check for any updates labeled Workfront Fusion Maintenance Update.

## {Feature title}

Feature description paragraph(s) — what changed, why, and how it affects existing scenarios/configurations if relevant.

For more information, see [{Help article title}](/help/workfront-fusion/{path-to-article}.md).

## {Next feature title}

...
```

Notas:
- Un H2 por función, en el orden que el usuario les dio (sin orden forzado de más reciente-primer dentro de la página — es una sola semana).
- No hay llamada de fecha `>[!NOTE]` por característica: el título de la página ya contiene la fecha.
- Si una característica requiere una acción o es un cambio importante o está en desuso, agregue una llamada `>[!IMPORTANT]` directamente debajo de H2, antes de la descripción:

  ```markdown
  ## {Feature title}
  
  >[!IMPORTANT]
  >
  >**Action Required: {short summary of what the user must do and by when}**
  >
  >{Details of the requirement.}
  
  {Regular description paragraph(s).}
  ```

- Cada característica debe finalizar con &quot;Para obtener más información, vea [...]&quot; vínculo al artículo de ayuda correspondiente. Compruebe que el destino del vínculo existe en el repositorio.

## Paso 4: Añadir la página al índice de información general

Editar `help/workfront-fusion/fusion-product-releases/fusion-release-activity.md`:

- Busque la sección `## Fusion releases in {current year}` (se trata de **no** envuelto en un bloque contraíble de `+++`; solo se contraen los años anteriores).
- Busque o cree el encabezado `### {Month} {Year}` para el mes de la versión, directamente debajo del encabezado del año.
  - Si el encabezado del mes aún no existe, agréguelo **por encima** del mes anterior (primero el mes más reciente).
- Agregue la nueva página como la viñeta **first** bajo el encabezado de ese mes (la semana más reciente primero):

  ```markdown
  * [Workfront Fusion release activity: Week of {Month} {Day}, {Year}](/help/workfront-fusion/fusion-product-releases/fusion-releases-{YYYY}/fusion-{YYYY}-{M}-{D}.md)
  ```

- Si esta es la primera versión de un nuevo año, agregue un nuevo encabezado `## Fusion releases in {YYYY}` sobre el encabezado del año anterior y ajuste la sección del año *anterior* en un bloque contraíble de `+++ **Click to open**` / `+++` si no lo está ya (solo el año actual permanece expandido).

## Paso 5: Agregar la página al índice

Editar `help/workfront-fusion/TOC.md`:

- Buscar `* Fusion releases - {YYYY} {#fusion-releases-{YYYY}}` para el año actual, anidado en `* Fusion release activity {#fusion-release-activity}`.
- Agregue la nueva página como la **primera** entrada bajo ese encabezado (la más reciente primero), que coincida con la sangría existente (8 espacios):

  ```markdown
        * [Workfront Fusion release activity: Week of {Month} {Day}, {Year}](/help/workfront-fusion/fusion-product-releases/fusion-releases-{YYYY}/fusion-{YYYY}-{M}-{D}.md)
  ```

- Si el encabezado del año actual aún no existe, agregue `* Fusion releases - {YYYY} {#fusion-releases-{YYYY}}` por encima del encabezado del año anterior.
- **No** agregue el prefijo `{hide-from-toc}` a las nuevas entradas, que solo se usa para las entradas antiguas cuando ya no se pueden navegar (consulte Incoherencias conocidas más abajo).

### Incoherencias conocidas que se deben tener en cuenta (no replicar)

- Varias entradas del índice de principios de 2026 están anidadas por error en el encabezado `Fusion releases - 2025`, aunque las páginas en sí son versiones de 2026. Al agregar una nueva entrada, siempre verifique que aparezca en el encabezado que coincida con **su propio año**, no donde se encuentre la entrada anterior.
- Algunos títulos/H1s de páginas anteriores omiten la coma anterior al año (`July 13 2026` en lugar de `July 13, 2026`). Utilice siempre la coma en las páginas nuevas.

## Paso 6: Lista de comprobación final

- [ ] Archivo creado en la ruta correcta sin ceros a la izquierda en la fecha
- [ ] usa `hidefromtoc: true`, no se ha inventado `exl-id`/`TQID`
- [ ] coincidencia de título/descripción, la fecha incluye una coma
- [ ] Cada característica tiene una descripción y un vínculo &quot;Para obtener más información&quot; verificado
- [ ] características de acción necesaria/obsolescencia tienen una llamada `>[!IMPORTANT]`
- [ ] Se agregó una nueva página como la entrada más reciente en `fusion-release-activity.md`, bajo el año/mes correcto
- [ ] Se agregó una nueva página como la entrada más reciente en `TOC.md`, bajo el encabezado de año correcto
- [ ] encabezados de año/mes nuevos creados si es necesario, con el año anterior contraído en `fusion-release-activity.md`

## Recursos adicionales

Para ver ejemplos completos (una semana sencilla de varias características y una con una llamada de acción requerida de `>[!IMPORTANT]`), vea `.claude/commands/_fusion-release-notes-reference.md`.
