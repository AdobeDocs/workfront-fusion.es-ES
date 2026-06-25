---
name: release-notes-formatter
description: Dé formato y valide a las notas de la versión de Workfront para mantener la coherencia, una estructura correcta y una vinculación adecuada. Se utiliza solo para archivos de notas de versiones en directorios de versiones de productos o cuando el usuario menciona notas de versiones, versiones de productos o versiones trimestrales. No lo aplique a artículos de procedimientos o documentación general.
source-git-commit: 4d32e8aab5b3b8a12dbc23e61f517fc4fd6dc9e5
workflow-type: tm+mt
source-wordcount: '861'
ht-degree: 2%

---


# Formato de notas de versión

Aplica formato y valida las notas de la versión de Adobe Workfront en el directorio `help/quicksilver/product-announcements/product-releases/`.

## Tipos de página

Identifique el tipo de página a partir de la ruta y el contenido del archivo:

| Tipo de página | Patrón de archivos | Plantilla |
|-----------|-------------|----------|
| **Información general** | `{YY}-q{N}-release-overview.md` | Consulte .claude/commands/_release-notes-formatter-reference.md#overview-page-template |
| **Área de producto** | `{YY}-q{N}-{area}.md` | Consulte .claude/commands/_release-notes-formatter-reference.md#product-area-page-template |
| **Planificación** | `planning-release-activity-{YY}-q{N}.md` | Similar al área de producto |
| **Aspecto** | `look-and-feel-updates-{YY}-q{N}.md` | Consulte .claude/commands/_release-notes-formatter-reference.md#look-and-feel-page-template |

## Flujo de trabajo de formato

### Paso 1: Validar Frontmatter

Campos obligatorios para todas las páginas de notas de la versión:

```yaml
---
title: <descriptive title>
description: <matches or summarizes the title>
author: <author name>
feature: Product Announcements
recommendations: noDisplay, noCatalog
exl-id: <existing UUID — never generate or change>
---
```

Reglas:
- `feature` debe ser exactamente `Product Announcements`
- `recommendations` debe ser exactamente `noDisplay, noCatalog`
- No inventar nunca un(a) `exl-id`: incluir solo si ya existe uno
- No agregue `draft: Probably` a páginas reales (solo plantillas)

### Paso 2: Validar la estructura por tipo de página

#### Páginas de área de producto

1. **H1**: `{Written Quarter} {Area} enhancements`
   - Ejemplo: `# Second Quarter 2026 Administrator enhancements`
   - El trimestre debe escribirse: &quot;Primer trimestre&quot;, &quot;Segundo trimestre&quot;, &quot;Tercer trimestre&quot;, &quot;Cuarto trimestre&quot;

2. **Párrafo introductorio**: Describe el área y los vínculos a la descripción general
   - Debe vincularse al archivo de información general **del trimestre correcto**
   - Error común: se está vinculando con el trimestre anterior (por ejemplo, `26-q1` en lugar de `26-q2`)

3. **H2 por característica**: título de característica como encabezado
   - **Las características más recientes primero**: la nota de la versión más reciente debe aparecer como el primer H2 después del párrafo de introducción
   - Las funciones antiguas se siguen en orden cronológico inverso

4. **Bloque de llamada de fecha** después de cada H2:

```markdown
>[!NOTE]
>
>Preview: {Month Day, Year}
>Production fast release: {Month Day, Year}
>Production for everyone: {Month Day, Year}
```

5. **Cuerpo**: Descripción de la función y después vínculo a la documentación de ayuda

#### Páginas de información general

1. **H1**: `{Written Quarter} release overview`

2. **Párrafo de introducción** con mes de lanzamiento programado

3. **`>[!IMPORTANT]`bloque** con tabla de programación de versiones

4. **H2`Adobe Workfront enhancements`** con lista con viñetas de vínculos de anclaje:

```markdown
* [Administrator enhancements](#administrator-enhancements)
* [Document enhancements](#document-enhancements)
```

5. **H3 por área de producto** con tabla de características de HTML (consulte .claude/commands/_release-notes-formatter-reference.md#overview-feature-table)
   - Dentro de cada tabla, **las características más recientes primero**, la fila más reciente aparece en la parte superior de la tabla (después de la fila de encabezado)

6. **Secciones finales** (H2): Notas de la versión para otras áreas, Actualizaciones del visor de revisión de escritorio, Anuncios, Versión de API, Actualizaciones de mantenimiento, Actualizaciones de formación

### Paso 3: Validación de vínculos

- **Vínculo de información general en las páginas de área de productos**: Debe señalar al mismo trimestre
   - Correcto: `26-q2-release-activity/26-q2-release-overview.md`
   - Incorrecto: `26-q1-release-activity/26-q1-release-overview.md`
- **Vínculos de anclaje en la descripción general**: Debe coincidir con los ID de H3 (en minúsculas, guiones)
- **Vínculos de características en tablas de información general**: Debe usar `class="MCXref xref" xrefformat="{para}"`
- **Vínculos del documento de ayuda**: Debe comenzar con `/help/quicksilver/`

### Paso 4: Validar las fechas

- Formato: `{Month} {Day}, {Year}` (por ejemplo, &quot;12 de marzo de 2026&quot;)
- Usar `TBD` para fechas desconocidas
- Las fechas del bloque de la página `>[!NOTE]` del área de productos deben coincidir con la fila de la tabla de resumen correspondiente
- Las fechas de vista previa deben preceder a las de producción

### Paso 5: Correcciones comunes

Aplique estas correcciones al dar formato:

| Problema | Corregir |
|-------|-----|
| Trimestre de vínculo de información general incorrecto | Actualizar para que coincida con el trimestre del propio archivo |
| Falta el bloque de fecha `>[!NOTE]` | Añadir bloque después del encabezado de la función H2 |
| Formato de fecha incoherente | Estandarizar a `Month Day, Year` |
| Falta una línea en blanco antes de `>[!NOTE]` | Añadir línea en blanco |
| Espacios adicionales en las líneas de llamada | Recortar espacio final |
| HTML en páginas de área de producto | Mantener como marcador (HTML solo sirve para tablas de información general) |
| Falta `exl-id` | Déjelo fuera, no genere uno |

### Paso 6: Actualizar el índice

Siempre que cree una **nueva** página de nota de versión (información general o área de producto), agréguela a `help/quicksilver/TOC.md` con el mismo cambio. Las páginas que no estén en el índice no aparecerán en la navegación publicada, aunque los vínculos de la tabla de resumen apunten a ellas.

Dónde se agrega:

- La TDC tiene una sección por trimestre bajo un encabezado como `* 2026 Q3 Release {#release-26-q3}`. Si el encabezado del trimestre aún no existe (primera página de un nuevo trimestre), agréguelo por encima del trimestre anterior para que el trimestre más reciente aparezca en la parte superior.
- Bajo ese encabezado de trimestre, enumere las páginas en este orden:
   1. **Información general** primero (`Third Quarter 2026 release overview`).
   2. **Páginas de área de producto** alfabéticamente por nombre de área (Administrador, Documentos, Operaciones de empresa, Proyectos, Informes, Solicitud).
   3. **Otras mejoras** duran (siempre después de las áreas de producto alfabéticas).

Cada entrada del índice es un vínculo de markdown que utiliza el título de página y la ruta absoluta del repositorio:

```markdown
      * [Third Quarter 2026 Documents enhancements](/help/quicksilver/product-announcements/product-releases/26-q3-release-activity/26-q3-documents.md)
```

Hacer coincidir la sangría (seis espacios) con las entradas adyacentes. Use la página H1 literalmente como texto del vínculo, por ejemplo `Documents enhancements`, `Requesting enhancements` (no `Requests`), de modo que las etiquetas de tabla de contenido coincidan con trimestres anteriores.

Errores comunes que se deben evitar:

- Creación de una página de área de producto sin agregarla al índice.
- Vínculo a una descripción general de trimestre diferente desde la nueva página de área de producto (paso 3).
- Inserción de páginas de un nuevo trimestre bajo el encabezado del trimestre anterior.

## Convenciones de nomenclatura de archivos

| Tipo | Patrón | Ejemplo |
|------|---------|---------|
| Información general | `{YY}-q{N}-release-overview.md` | `26-q2-release-overview.md` |
| Área de producto | `{YY}-q{N}-{area-slug}.md` | `26-q2-admin-and-setup.md` |
| Directorio | `{YY}-q{N}-release-activity/` | `26-q2-release-activity/` |

slugs de área estándar: `admin-and-setup`, `documents`, `projects`, `reports`, `requests`, `other`

## Asignación de trimestre

| Trimestre | Formulario escrito | Meses |
|---------|-------------|--------|
| Primer trimestre | Primer trimestre | Ene-Mar |
| Segundo trimestre | Segundo trimestre | Abr-Jun |
| Tercer trimestre | Tercer trimestre | Jul-Sep |
| Cuarto trimestre | Cuarto trimestre | Oct-Dic |

La versión de producción trimestral aterriza generalmente el jueves de la segunda semana completa del último mes del trimestre.

## Lista de comprobación de validación

Cuando revise un archivo de notas de la versión, compruebe:

- [ ] Frontmatter tiene todos los campos obligatorios con los valores correctos
- [ ] H1 coincide con el formato de tipo de página
- [ ] El vínculo de información general apunta al trimestre correcto
- [ ] Cada característica tiene un bloque de fecha `>[!NOTE]` (páginas de área de producto)
- [ ] El formato de fecha es coherente (`Month Day, Year`)
- [ ] Las filas de la tabla de características de la descripción general coinciden con el contenido de página del área de producto
- [ ] No hay vínculos internos rotos
- [ ] vínculos de anclaje en la descripción general coinciden con los ID de sección H3
- [ Las características de ] se ordenan más recientes (tanto páginas de área de productos como tablas de información general)
- [ ] Las nuevas páginas de notas de la versión se enumeran en `help/quicksilver/TOC.md` en el trimestre correcto, con la descripción general en primer lugar y las áreas de producto en orden alfabético (el otro en último lugar)

## Recursos adicionales

- Para ver plantillas y ejemplos completos de HTML, consulte .claude/commands/_release-notes-formatter-reference.md
