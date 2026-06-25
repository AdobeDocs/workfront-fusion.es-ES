---
name: remove-preview-highlighting
description: ""
source-git-commit: 4d32e8aab5b3b8a12dbc23e61f517fc4fd6dc9e5
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 0%

---


# Quitar resaltado de vista previa (Workfront)

## Ámbito

Se aplican solo cuando **all** son verdaderos:

1. El usuario invocó este flujo de trabajo (por ejemplo, dice **&quot;quitar resaltado de vista previa&quot;** o claramente la misma intención).
2. La ruta del archivo Markdown **no contiene** **`product-announcements`** (excluya todo el árbol de carpetas, por ejemplo, notas de la versión, beta y anuncios en `help/quicksilver/product-announcements/`).
3. El archivo Markdown **no es** enumerado en **[Rutas excluidas](#excluded-paths)** a continuación.
4. El archivo Markdown aparece en `git log` como con contenido de vista previa **agregado o modificado** por el usuario de Git actual dentro del intervalo de fechas especificado por el usuario (consulte el paso Inventario).
5. El artículo tiene **al menos uno** de:
   - Vista previa del entorno **idioma en los párrafos del fragmento de cuerpo o en prosa real** (patrones típicos: &quot;información resaltada&quot;, &quot;entorno de vista previa&quot;, &quot;aún no disponible de forma general&quot;, notas de versión rápida)—**no** una coincidencia de **solo texto de vínculo** en una página de índice/índice (ver a continuación); o
   - Cualquier elemento de HTML con **`class="preview"`** (por ejemplo, `<span class="preview">`, `<div class="preview">`); o
   - Un fragmento de vista previa **variable** como **`{{highlighted-preview}}`** o **`{{highlighted-preview-article-level}}`**.

Si el ámbito no es claro, confirme antes de editar.

**Páginas de índice/índice de tabla de contenido: omitir siempre este caso:** **Nunca** puso un archivo en el inventario cuando el texto relacionado con la vista previa de **solamente** está **dentro** del texto para mostrar de un vínculo de marcado que señala a **otro** artículo (p. ej. *Enviar un informe en el entorno de vista previa de espacio aislado*) **y** el archivo tiene **no** `class="preview"`, **no** fragmento y **no** previsualizar repeticiones en **prose fuera de los vínculos**. No se trata del resaltado de vista previa de esa página; es solo una mención de la tabla de contenido. Se aplica a cualquier índice/índice, no solo a un archivo.

### Rutas excluidas

Nunca agregue estos elementos al inventario ni los edite en este flujo de trabajo a menos que el usuario anule explícitamente:

- `help/quicksilver/documents/adobe-workfront-for-experience-manager-assets-essentials/send-to-aem.md`: los límites de Previsualización paralela frente a Producción necesitan una decisión editorial deliberada fuera de la automatización.
- `help/quicksilver/reports-and-dashboards/reports/creating-and-managing-reports/create-manage-reports.md` — informa de TDC; la única señal de &quot;previsualización&quot; es el vínculo al artículo Previsualizar entrega de zona protegida.

## Flujo de trabajo requerido (humano en bucle)

**no** edita el repositorio de forma masiva sin aprobación.

1. **Inventario**\
   a. **Pregunte al usuario para qué versión trimestral** está eliminando el resaltado de vista previa (por ejemplo, &quot;T3 2026&quot; o &quot;2026.07&quot;).\
   b. **Recupere el calendario de versiones** de `https://wiki.corp.adobe.com/spaces/AWF/pages/3631617814/2026+Monthly+Release+Calendar` mediante la herramienta MCP de adobe-wiki. Buscar:
   - La **fecha de lanzamiento de producción** de la **versión trimestral anterior** → `--since`.
   - La **fecha de lanzamiento de producción** del **destino** → trimestral `--until`.
   - Las versiones trimestrales se identifican con la columna &quot;Nombre de versión trimestral&quot; (por ejemplo, 2026.01, 2026.04, 2026.07, 2026.10).
   - **Si la fecha actual se encuentra en el cuarto trimestre (octubre a diciembre):** después de recuperar el calendario del año actual, pídale al usuario que proporcione la dirección URL para el calendario de versiones del año próximo y, a continuación, recupere también esa dirección para que todas las fechas de producción trimestrales necesarias estén disponibles.
c. Determine el usuario de Git actual y, a continuación, ejecute lo siguiente utilizando las fechas de lanzamiento de producción del paso b:

   ```bash
   GIT_USER=$(git config user.name)
   git log --since="YYYY-MM-DD" --until="YYYY-MM-DD" \
     --author="$GIT_USER" --name-only --pretty=format: \
     -- "help/quicksilver/**/*.md" | sort -u | grep -v '^$'
   ```

   d. De esos resultados, **filtre a los archivos donde las confirmaciones del usuario actual en el intervalo de fechas agregaron o modificaron realmente el contenido de vista previa**. Para cada archivo candidato, compruebe si las confirmaciones del usuario introdujeron los marcadores de previsualización:

   ```bash
   git log --since="YYYY-MM-DD" --until="YYYY-MM-DD" \
     --author="$GIT_USER" -p -- "<file>" | \
   grep -q '^\+.*class="preview"\|^\+.*{{highlighted-preview\|^\+.*highlighted information\|^\+.*not yet generally available'
   ```

   Incluya el archivo solo si este grep coincide (código de salida 0). Esto evita los falsos positivos cuando un usuario realiza una edición no relacionada con un archivo cuyo resaltado de vista previa ha sido agregado por otra persona.

   e. **Omitir** cualquier ruta de acceso en **`product-announcements`**, cualquier **[ruta de acceso excluida](#excluded-paths)** y cualquier página de **índice/índice** según la regla de índice anterior.\
   f. Presente la lista ordenada resultante. Si el usuario dice que un archivo de la lista no tiene resaltado de previsualización, elimínelo de la ejecución y apriete los criterios en lugar de forzar las ediciones.

2. **Start**\
   Pregunte si desea comenzar con el artículo **first** de la lista (o una ruta en los nombres de usuario).

3. **Por artículo: mostrar primero, editar después de Aceptar**
   - Lea el archivo.
   - Proponga ediciones claramente: **antes o después de los extractos** o una descripción enfocada en el estilo de diferencia de lo que va a cambiar.
   - **Espere** para obtener una aprobación explícita (por ejemplo, &quot;está bien&quot;, &quot;aplicar&quot;, &quot;sí&quot;) antes de escribir el archivo.

4. **Después de cada archivo**\
   Pregunte si desea pasar al artículo **next** (o detener/omitir).

## Reglas de contenido (GA: la previsualización de contenido se convierte en el documento)

Al eliminar el resaltado de vista previa de la **disponibilidad general**, el objetivo es: **mantener el comportamiento documentado para la vista previa**, eliminar **ramas obsoletas &quot;en producción&quot; o de proceso antiguo** y, a continuación, **eliminar las etiquetas y los contenedores de solo vista previa** para que el tema se lea como actual para todos los clientes.

### Pasos paralelos

- Si el artículo tiene un paso (o elemento numerado) **enmarcado como &quot;en producción&quot;** (o equivalente: producción actual/comportamiento de producción existente) **y** un paso **paralelo** enmarcado como **&quot;en vista previa&quot;** (o entorno de vista previa):
   - **Quitar** el paso en producción (la ruta anterior).
   - **Conservar** la **sustancia** del paso de vista previa, pero **volver a redactar**, por lo que **no es** específica de la vista previa (quitar &quot;en vista previa&quot;, &quot;Entorno de vista previa&quot;, etc.). Ajuste la numeración para que la lista sea coherente.

Si la estructura es ambigua (sin paralelo claro), **stop** y mostrar ambos candidatos; pregunte al usuario qué bloque mantener.

### Secciones paralelas

- Si una **sección** (encabezado + cuerpo) es **aproximadamente &quot;en el entorno de producción&quot;** y hay una **sección paralela** **aproximadamente &quot;en el entorno de vista previa&quot;**:
   - **Quitar** la sección del entorno de producción (el contenido reemplazado).
   - **Reemplazar** por el contenido de la sección de vista previa, luego **quitar** la redacción del entorno de vista previa y cualquier contenedor **`class="preview"`** para que la sección sea neutra (lista para GA).

### Fragmentos de código y avisos de la parte superior del artículo

- Elimine **plantillas de solo vista previa** bloques (se expande/divide o párrafos que solo explican que el contenido resaltado es de solo vista previa, de liberación rápida, de espacio aislado, etc.) una vez que la función sea GA.
- Elimine vínculos u oraciones cuyo propósito **only** sea la disponibilidad de la vista previa, a menos que el usuario indique que se mantenga un aviso diferente.

### HTML `class="preview"`

- Quite las **etiquetas de apertura y cierre** de los elementos que usan **`class="preview"`**, **conservando el contenido interno** (markdown/HTML dentro de la etiqueta).
- Controle **`<span class="preview">`** y **`<div class="preview">`**, y el mismo patrón en otras etiquetas (p. ej. **`<p class="preview">`**, **`<li class="preview">`**) cuando aparecen en el contenido del cuerpo **visible** (no comentado).
- Conservar la estructura de listas/tablas; corregir listas rotas o espacios en blanco perdidos después de desajustarlas.

### Secciones comentadas (comentarios de HTML)

- **No** elimine, desajuste ni **modifique** ningún contenido dentro de **`<!-- … -->`** comentarios de HTML **a menos que el usuario indique explícitamente** qué hacer (por ejemplo, eliminar todo el comentario, eliminar clases de vista previa dentro del comentario solamente, descomentar para GA).
- Si el contenido relacionado con la vista previa o **`class="preview"`** aparece **solamente** dentro de los comentarios, **llame a eso** al revisar el artículo: diga lo que hay en el comentario y **pregunte** qué hacer. **Predeterminado: dejar las secciones comentadas sin cambiar.**

### Qué no hacer

- No ejecute este flujo de trabajo en rutas de acceso en **`product-announcements`** (notas de la versión y relacionadas); el inventario debe excluirlas.
- No realice el inventario ni edite las rutas enumeradas en **[Rutas excluidas](#excluded-paths)** a menos que el usuario pida explícitamente que se incluya una.
- **No** quite o edite automáticamente los bloques **comentados** (`<!-- … -->`); siga las **secciones comentadas** anteriores.
- No quite la opción &quot;Vista previa&quot; cuando se trate de **not** acerca de este patrón de disponibilidad de características (p. ej. [Vista previa del entorno de espacio aislado](·) como **nombre de producto** en un contexto no relacionado), juzgue y pregunte si no está seguro.
- No cambie `author:` ni el frontmatter no relacionado a menos que el usuario se lo pida.
- No omita el paso **mostrar → aprobar**.

## Comprobación de la calidad antes de presentar las ediciones

- No quedan **`class="preview"`** en el ámbito de cambio acordado.
- No hay encabezados duplicados huérfanos ni números de paso rotos.
- La introducción se lee correctamente **sin** contradiciendo a GA (no &quot;solo en vista previa&quot; para las funciones enviadas).

## Referencias

- Hacer coincidir **[estilo de documentación de Workfront](https://experienceleague.adobe.com/?lang=es)** y convenciones de repositorios (reglas de compromiso/PR si el usuario se compromete).
