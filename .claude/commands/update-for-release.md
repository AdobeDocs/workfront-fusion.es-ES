---
name: update-for-release
description: ""
source-git-commit: 4d32e8aab5b3b8a12dbc23e61f517fc4fd6dc9e5
workflow-type: tm+mt
source-wordcount: '1443'
ht-degree: 0%

---


# Actualización de la versión (Workfront)

Esta aptitud se explica actualizando los artículos de ayuda de Workfront para una próxima versión de la funcionalidad. El flujo de trabajo es el contrario de `remove-preview-highlighting`: se está agregando un nuevo comportamiento a los artículos, se está marcando como Vista previa y (posteriormente, en GA) se está limpiando con esa otra aptitud.

## Ámbito

Aplicar cuando **todos** sean verdaderos:

1. El usuario está actualizando los artículos de ayuda de Workfront para una función que se está enviando (generalmente Vista previa primero).
2. El cambio introduce un nuevo comportamiento para la interfaz de usuario, no una limpieza de GA. Para la limpieza de GA, use **remove-preview-highlight** en su lugar.
3. El archivo es **no** una nota de la versión. Para las notas de la versión, use **release-notes-formatter** en su lugar.
4. El usuario ha dado contexto a la funcionalidad: como mínimo una breve descripción y una captura de pantalla; idealmente, una URL de PRD (Adobe Wiki).

Si el ámbito no es claro, confirme antes de empezar.

## Flujo de trabajo requerido (humano en bucle)

**no** edita el repositorio de forma masiva. Mover un artículo a la vez. Después de cada artículo, pregunte si desea continuar con el siguiente.

### &#x200B;1. Recopilar contexto de función

Confirme con el usuario:

- **Lo que cambió** (resumen de 1 a 2 frases del nuevo comportamiento o interfaz de usuario).
- **Capturas de pantalla** de la nueva interfaz de usuario. Si se proporciona, guarde bajo la carpeta `assets/` del artículo de destino con un nombre de archivo descriptivo en mayúsculas y minúsculas (p. ej. `add-custom-message.png`). Si no se proporciona, pregunte si desea esperar uno o continuar con una referencia de marcador de posición.
- **URL de PRD** (wiki de Adobe), si está disponible. Recuperarla con la herramienta `user-Adobe Wiki Confluence` MCP `get_wiki_content`. Léalo para encontrar el comportamiento que el usuario no puede ver en la interfaz de usuario: efectos secundarios de notificación, qué sucede cuando se edita o se agrega algo más tarde, límites de caracteres no mostrados, permisos, etc.
- **Disponibilidad**: Solo vista previa, Vista previa + versión rápida o ya GA. Esto controla la elección del fragmento de código en el paso 3.
- **Exclusiones explícitas**: cualquier artículo que el usuario desee omitir (por ejemplo, &quot;esta característica no está en las plantillas&quot;).

### &#x200B;2. Artículos afectados por inventario

Busque el repositorio con las palabras clave del área de características (p. ej. `approval workflow`, `document approval`, la etiqueta de campo específica). Crear una lista de candidatos:

- Artículos explicativos en el árbol `help/quicksilver/.../` correspondiente.
- Artículos de información general y preguntas frecuentes sobre el área de funciones.
- **Excluir** `product-announcements/` (las notas de la versión utilizan una aptitud diferente).
- **Excluir** páginas de índice/índice donde la única mención es el texto de vínculo a otro artículo.
- **Excluir** artículos que el usuario dijo omitir en el paso 1.

Presentar la lista de candidatos al usuario. Pregunte qué actualizar y qué omitir. Referencia cruzada `help/quicksilver/TOC.md` si parece que falta un artículo relacionado.

### &#x200B;3. Seleccionar el fragmento de vista previa

Lea `help/_includes/snippets.md` y elija según disponibilidad:

| Disponibilidad | Fragmento |
| --- | --- |
| Solo vista previa: el contenido resaltado es nuevo en un artículo de, de lo contrario, GA | `{{highlighted-preview}}` |
| Solo vista previa: todo el artículo es nuevo. | `{{highlighted-preview-article-level}}` |
| Vista previa + clientes de versión rápida, general | `{{preview-fast-release-general}}` |

Si ya existe un fragmento de código específico para la versión para el trimestre actual, prefiera el genérico. Confirme la elección con el usuario antes de aplicar.

### &#x200B;4. Por artículo: mostrar primero, editar después de Aceptar

Para cada artículo de la lista confirmada por el usuario:

1. **Leer el archivo.**

2. **Determine el patrón de resaltado.** Pregunte al usuario cuál se ajusta a este artículo (la respuesta puede diferir según el artículo):

   - **Duplicación por sección**: anexe `in Production` al encabezado de sección existente. Agregue una nueva sección con `in Preview` anexado, dentro de `<div class="preview"> ... </div>`. Utilícelo cuando el nuevo comportamiento cambie el procedimiento de forma significativa: pasos adicionales, una nueva imagen, nuevas filas de tabla o una redacción diferente. Típico para procedimientos prácticos.
   - **Ajuste por línea**: agregue las nuevas oraciones en línea dentro de la sección existente, dentro de `<span class="preview"> ... </span>`. Utilícelo cuando la adición sea una o dos frases que se ajusten de forma natural a un párrafo, celda de tabla o respuesta a preguntas frecuentes existente.
   - **Mixto**: Algunas secciones del mismo artículo utilizan la duplicación por sección, mientras que otras utilizan el ajuste por línea. Aparezca esta opción cuando el artículo tenga secciones de procedimiento y secciones de estilo de preguntas frecuentes.

3. **Coloque el fragmento** en su propia línea inmediatamente después del encabezado H1, con una línea en blanco por encima y por debajo. El fragmento se sitúa **antes de** el párrafo de introducción.

4. **Agregue nuevos detalles en &quot;incluir siempre&quot; frente a &quot;listo para revisión&quot;.** Este es el paso más importante.

   - **Incluir siempre** (aplicar automáticamente, sin preguntar): comportamientos invisibles que el usuario no puede observar al interactuar con la interfaz de usuario. Ejemplos:
      - Efectos adversos (por ejemplo, &quot;editar esto reenvía el correo electrónico a todos los participantes&quot;)
      - Comportamiento entre otros objetos o eventos posteriores
      - Requisitos previos y permisos
      - Límites no mostrados en la IU de
      - Cualquier cosa que el usuario solo pueda aprender del PRD, los documentos o el equipo del producto
   - **Preparado para revisión** (presentado al usuario con `AskQuestion` como selección múltiple): hechos que el usuario puede ver en la pantalla mientras usa la característica. Ejemplos:
      - Ya se muestra un contador de caracteres en la interfaz de usuario (por ejemplo: `0 / 500`)
      - Estado expandido/contraído predeterminado de un campo
      - Estado seleccionado predeterminado de una casilla de verificación visible
      - Etiquetas de botón junto al campo
      - Mensajes de validación que aparecen en línea

   Proporcione una justificación de una frase para cada elemento &quot;listo para revisión&quot; (&quot;Ayuda a los principiantes a planificar un mensaje más largo&quot;, &quot;Ayuda a los usuarios que no lo ven en etapas posteriores a ampliarlo&quot;). Incluya solo los elementos que elija el usuario. El principio predeterminado es &quot;si el usuario puede verlo en pantalla mientras realiza la tarea, no lo repita&quot;, pero el usuario recibe la llamada final.

5. **Proponer ediciones.** Muestre fragmentos antes o después (o una descripción de estilo de comparación enfocada) del artículo que cubren: ubicación de fragmentos, cambios de nombre de encabezados, nuevo contenido de vista previa en la vista previa y ubicación, referencia de captura de pantalla y cualquier ajuste de `class="preview"` en línea.

6. **Espere una aprobación explícita** (&quot;está bien&quot;, &quot;aplicar&quot;, &quot;sí&quot;) antes de escribir el archivo.

7. **Validar.** Después de escribir, ejecute `ReadLints` en el archivo e informe de cualquier problema. Vuelva a leer la sección modificada para confirmar la estructura.

8. **Diferir las ediciones en el nivel de prosa** a la habilidad **calidad de escritura**. No rehaga aquí la voz, el uso de mayúsculas y minúsculas, las reglas en negrita ni los patrones de vínculos: lea `~/.cursor/skills/writing-quality/SKILL.md` si se solicita un pase en prosa.

### &#x200B;5. Después de cada artículo

Pregunte si desea pasar al siguiente artículo, detener, omitir o volver a visitar el actual.

### &#x200B;6. Fin de la sesión: copiar/pegar la nota de la versión

Cuando el usuario finalice la sesión (diga &quot;listo&quot;, &quot;ya está&quot;, &quot;detener&quot; o rechace continuar con el siguiente artículo), pregunte:

> &quot;¿Desea copiar/pegar una entrada de nota de versión para la página de mejora?&quot;

Si es así, genere una entrada de borrador utilizando el contexto de función del paso 1 y el artículo de ayuda principal actualizado en esta sesión. **No lo escriba en ningún archivo**; proporciónelo como texto de copiar/pegar solamente.

Dé formato a la entrada para que coincida con la estructura de página del área de producto de la aptitud de **formateador de notas de la versión**:

```markdown
## {Feature name}

>[!NOTE]
>
>Preview: {date or TBD}
>Production fast release: {date or TBD}
>Production for everyone: {date or TBD}

{1–3 sentences describing what changed and why it helps users. Lead with the benefit, not the UI action.}

For more information, see [{Primary article title}](/help/quicksilver/{path-to-article}.md).
```

Reglas:

- Use `TBD` para cualquier fecha aún no conocida; pregunte al usuario si tiene las fechas.
- El nombre de la función es mayúsculas y minúsculas (ponga en mayúsculas solo la primera palabra y los sustantivos propios).
- La descripción debe centrarse en lo que los usuarios ahora pueden hacer, no en los detalles de la implementación.
- Vínculo al artículo de procedimientos más específico actualizado, no a una página de información general.
- No incluya un bloque de fecha `>[!NOTE]` si todas las fechas son desconocidas y el usuario no desea marcadores de posición; omita este bloque y tenga en cuenta que debe agregarse más adelante.

## Reglas de contenido

### Encabezados

- Anexe exactamente **`in Production`** a los encabezados de sección existentes que permanezcan como referencia en el lado de producción.
- Anexe exactamente **`in Preview`** a los nuevos encabezados de sección.
- Mantenga el resto del encabezado en mayúsculas o minúsculas (por `writing-quality`).

### Previsualizar contenedores

- **Nivel de sección**: ajuste en `<div class="preview"> ... </div>`. Coloque las etiquetas de apertura y cierre en sus propias líneas, con una línea en blanco encima y debajo de cada etiqueta, para que se sigan representando los encabezados y las listas dentro.
- **En línea (nivel de oración)**: ajuste `<span class="preview"> ... </span>` dentro del párrafo, celda de tabla o respuesta a preguntas frecuentes existente.
- Nunca anide un(a) `<span class="preview">` dentro de un(a) `<div class="preview">`.

### Ubicación del fragmento

- La línea de fragmento va inmediatamente después de H1, con una línea en blanco por encima y por debajo.
- El fragmento se sitúa **antes de** el párrafo de introducción, la llamada de `>[!IMPORTANT]` y cualquier bloque de requisitos de acceso.
- Un fragmento por artículo.

### Capturas de pantalla

- Guarde las nuevas capturas de pantalla en la carpeta `assets/` del artículo con un nombre de archivo descriptivo en mayúsculas y minúsculas.
- Haga referencia a la nueva captura de pantalla desde la nueva sección Vista previa. Si la captura de pantalla de una sección en producción ya no refleja la función con precisión, déjela en su lugar; sigue representando el comportamiento de producción hasta GA.
- No fabrique nombres de archivo de captura de pantalla; si aún no se ha proporcionado ninguna captura de pantalla, pregunte al usuario.

### Notas y sugerencias

- Máximo de uno `>[!NOTE]` (o `>[!TIP]`, `>[!IMPORTANT]`, `>[!WARNING]`) por sección. Si la sección existente ya tiene una nota, combine el nuevo contenido relacionado en la misma nota como una lista con viñetas en lugar de apilarlo.

### Qué no hacer

- No edite artículos bajo `product-announcements/`.
- No edite de forma masiva; un artículo a la vez, con aprobación explícita cada vez.
- No incluya hechos observables de la interfaz de usuario sin mostrarlos primero al usuario.
- No modifique el contenido de `<!-- ... -->` comentarios de HTML a menos que el usuario lo indique explícitamente.
- No cambie `author:` ni campos de frontmatter no relacionados.

## Comprobación de la calidad antes de presentar las ediciones

- Fragmento de código aparece una vez, en su propia línea, después de H1, con líneas en blanco por encima y por debajo.
- Los encabezados de sección existentes finalizan con `in Production`.
- Los nuevos encabezados de sección finalizan con `in Preview` y la sección se encuentra dentro de `<div class="preview">`.
- Las adiciones en línea están dentro de `<span class="preview">`.
- `ReadLints` está limpio en el archivo editado.
- El artículo se lee correctamente en ambos estados (con el contenido de vista previa mostrado y oculto).

## Referencias

- Estilo de documentación de Workfront: vea la aptitud de **calidad de escritura** en `~/.cursor/skills/writing-quality/SKILL.md`.
- Catálogo de fragmentos: `help/_includes/snippets.md` en el repositorio de docs.
- Limpieza de GA (flujo de trabajo inverso): consulte la aptitud de **eliminar resaltado de vista previa** en `.cursor/skills/remove-preview-highlighting/SKILL.md`.
- Adobe Wiki MCP para PRD: servidor `user-Adobe Wiki Confluence`, herramienta `get_wiki_content`.
