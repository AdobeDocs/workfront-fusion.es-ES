---
source-git-commit: 4d32e8aab5b3b8a12dbc23e61f517fc4fd6dc9e5
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---
# Plantillas de referencia de notas de versión

Plantillas detalladas para cada tipo de página de nota de versión. Se basan en las plantillas de
`help/quicksilver/product-announcements/product-releases/release-note-templates/` y
el formato real utilizado en las últimas versiones trimestrales.

&#x200B;---

## Plantilla de página de área de producto

```markdown
---
title: {Written Quarter} {Year} {Area} enhancements
description: {Written Quarter} {Year} {Area} enhancements
author: {Author}
feature: Product Announcements
recommendations: noDisplay, noCatalog
exl-id: {existing UUID}
---
# {Written Quarter} {Year} {Area} enhancements

This page describes {Area} enhancements made with the {Written Quarter} {Year} release to the Preview environment. These enhancements will be made available in the Production environment as noted.

For a list of all changes available at this point in the {Written Quarter} {Year} release cycle, see [{Written Quarter} {Year} release overview](/help/quicksilver/product-announcements/product-releases/{YY}-q{N}-release-activity/{YY}-q{N}-release-overview.md).

## Feature Title Here

>[!NOTE]
>
>Preview: {Month Day, Year}
>Production fast release: {Month Day, Year}
>Production for everyone: {Month Day, Year}

Feature description paragraph.

For more information, see [Help article title](/help/quicksilver/path/to/article.md).
```

### Reglas para páginas de área de producto

- Utilice Markdown (no HTML) para el contenido del cuerpo
- Cada función recibe un encabezado H2
- La llamada `>[!NOTE]` debe tener una línea en blanco antes de ella
- El formato `>[!NOTE]` es exactamente:

  ```
  >[!NOTE]
  >
  >Preview: {date}
  >Production fast release: {date}
  >Production for everyone: {date}
  ```

- Si una función se ha eliminado temporalmente, añada una línea después de la fecha:

  ```
  >
  >This feature has been temporarily removed from the Production environment on {date}.
  ```

- Los vínculos de ayuda utilizan rutas absolutas que comienzan por `/help/quicksilver/`

&#x200B;---

## Plantilla de página de información general

```markdown
---
title: {Written Quarter} {Year} release overview
description: This page provides information about functionality that is included in the {Written Quarter} {Year} release. These enhancements are planned to become available in the Production environment throughout the quarter.
author: {Author}
feature: Product Announcements
recommendations: noDisplay, noCatalog
exl-id: {existing UUID}
---
# {Written Quarter} {Year} release overview

This page provides information about functionality that is included in the {Written Quarter} {Year} release scheduled for {Release Month} {Year}.

The enhancements on this page are available in the Preview environment. This page will be updated with additional enhancements as the {Written Quarter} {Year} release nears its planned Production release.

>[!IMPORTANT]
>
>
>Monthly and quarterly releases are planned to be available on the Thursday of the second full week of the month, unless otherwise specified.
>
>|Monthly release|Quarterly release|
>|----|----|
>|<ul><li>{VV}.{M} ({Month Day, Year})</li><li>{VV}.{M} ({Month Day, Year})</li><li>{VV}.{M} ({Month Day, Year})</li></ul>|<ul><li>{VV}.{M} ({Month Day, Year})</li></ul>|
>
>Note that for the final release of each quarter ({VV}.{M} this quarter), users on the fast release schedule will receive the release one day early ({Month Day, Year}).
>
>For more information on the fast release process, see [Enable or disable the fast release process](/help/quicksilver/administration-and-setup/set-up-workfront/configure-system-defaults/enable-fast-release-process.md).

## Adobe Workfront enhancements

* [Administrator enhancements](#administrator-enhancements)
* [Document enhancements](#document-enhancements)
* [Project enhancements](#project-enhancements)
* [Reporting enhancements](#reporting-enhancements)
* [Requesting enhancements](#requesting-enhancements)
* [Other enhancements](#other-enhancements)
```

### Tabla de funciones generales

Cada sección del área de producto H3 contiene una tabla de HTML. Utilice esta estructura exacta:

```html
### {Area} enhancements

<table>
            <col style="width: 50%;" />
            <col style="width: 25%;" />
            <tbody>
              <tr>
        <td><strong>Feature</strong>
        </td>
        <td><strong>Preview</strong></td>
        <td><strong>Fast release</strong></td>
        <td><strong>Quarterly</strong></td>
        </tr>
    <tr>
        <td>
            <a href="/help/quicksilver/product-announcements/product-releases/{YY}-q{N}-release-activity/{YY}-q{N}-{area}.md" class="MCXref xref" xrefformat="{para}">Feature Title</a><p>Short description of the feature.</p>
        </td>
        <td><p>{Month Day, Year}</p></td>
        <td><p>{Month Day, Year}</p></td>
        <td><p>{Month Day, Year}</p></td>
    </tr>
            </tbody>
        </table>
```

#### Reglas de tabla

- Celda de característica: etiqueta `<a>` con `class="MCXref xref" xrefformat="{para}"` seguida de descripción `<p>`
- Los vínculos `href` a la página de área de producto (no es un anclaje específico)
- Celdas de fecha: agrupadas en `<p>` etiquetas
- Para los elementos no programados, agregue `<p>[!BADGE Off schedule]{type=Neutral}</p>` después del vínculo
- Se acepta `<p></p>` vacío después del vínculo cuando no se necesita un distintivo
- Mantener la sangría de HTML coherente con los archivos existentes

### Información general Secciones finales

Después de todas las tablas de área de producto:

```markdown
## Release notes for other areas

### Workfront Fusion enhancements

New features in Workfront Fusion are available in Production at a cadence outside of the standard release schedule. For more information about the latest features, see [Adobe Workfront Fusion release activity](https://experienceleague.adobe.com/es/docs/workfront-fusion/using/fusion-release-activity/fusion-release-activity).

### Workfront Planning enhancements

New features in Workfront Planning are available in Production. For more information about the latest features, see [{Written Quarter} {Year} release activity for Adobe Workfront Planning](/help/quicksilver/product-announcements/product-releases/planning-release-activity/planning-release-activity-{YY}-q{N}.md).

There are no updates for the following at this point in the release:

* Scenario Planner
* Proof
* Goals

## Desktop proofing viewer updates

{Version info if available, otherwise omit section}

## Announcements

{Announcement content}

### API version {NN}

{API version info}

### Workfront Maintenance Updates

For information about the maintenance updates made during the {Written Quarter} {Year} release, see [Workfront Maintenance Updates](https://experienceleague.adobe.com/docs/workfront-known-issues/releases/current-updates.html?lang=es).

### Training updates

Explore the latest updates made to learning programs, learning paths, videos, and guides for each Adobe Workfront product release. For more information, see the "What's New" section of the [Workfront Tutorials page](https://experienceleague.adobe.com/docs/workfront-learn/tutorials-workfront/home.html?lang=es).
```

&#x200B;---

## Plantilla de página de aspecto

```markdown
---
title: Look-and-feel updates during the {Written Quarter} {Year} release time frame
description: Look-and-feel updates during the {Written Quarter} {Year} release time frame
author: {Author}
feature: Product Announcements
recommendations: noDisplay, noCatalog
exl-id: {existing UUID}
---

# Look-and-feel updates during the {Written Quarter} {Year} release time frame

This page describes minor updates to the look and feel of various areas of the Adobe Workfront application that were made within the {Written Quarter} {Year} release timeframe. These enhancements will be made available in the Production environment a minimum of 2 weeks after releasing to Preview.

For a list of all changes available with the {Written Quarter} {Year} release, see [{Written Quarter} {Year} Release overview](/help/quicksilver/product-announcements/product-releases/{YY}-q{N}-release-activity/{YY}-q{N}-release-overview.md).

## Feature Title

>[!NOTE]
>
>Preview release: {Month Day, Year}; Planned Production release: {Month Day, Year}

Description of the look-and-feel change.
```

&#x200B;---

## Formatos de llamada de fecha

### Páginas de área de producto (multilínea)

```markdown
>[!NOTE]
>
>Preview: March 5, 2026
>Production fast release: April 15, 2026
>Production for everyone: April 16, 2026
```

### Páginas de aspecto (una sola línea)

```markdown
>[!NOTE]
>
>Preview release: March 5, 2026; Planned Production release: March 19, 2026
```

### Páginas semanales (una línea)

```markdown
>[!NOTE]
>
>Preview release: February 9, 2023; Planned Production release: February 23, 2023
```

&#x200B;---

## Incoherencias conocidas a tener en cuenta

1. **Vínculo de información general incorrecto trimestre**: las páginas de área de producto a veces se vinculan a la información general del trimestre anterior (por ejemplo, `26-q1` en lugar de `26-q2`)
2. **Vista previa de fechas que muestran el año incorrecto** — Las tablas de información general a veces muestran el año anterior en la columna Vista previa (por ejemplo, &quot;2025&quot; en lugar de &quot;2026&quot;)
3. **Faltan `</tr>` etiquetas de cierre** — Algunas filas de la tabla de HTML no tienen las etiquetas de cierre adecuadas
4. **`content-type: release-notes`** — Presente en archivos antiguos, omitido en las páginas más recientes del área de producto 26-q2. Seguir el patrón del trimestre actual.
5. **Error ortográfico en la plantilla** — La plantilla de presentación tiene `relesae` en lugar de `release`; use siempre la ortografía correcta
6. **Falta `<p></p>` después del vínculo de característica** — Algunas filas de la tabla de información general omiten la etiqueta `<p>` vacía después de la etiqueta `<a>`
