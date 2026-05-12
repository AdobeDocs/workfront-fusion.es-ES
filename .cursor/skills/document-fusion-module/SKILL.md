---
name: document-fusion-module
description: Documente un nuevo módulo de conector de Adobe Workfront Fusion agregándolo al artículo del conector correspondiente en help/workfront-fusion/references/apps-and-modules/. Se utiliza cuando el usuario pide añadir, documentar o describir un nuevo módulo de Fusion, o cuando el usuario proporciona capturas de pantalla de un panel de configuración del módulo Fusion y desea que se actualice el artículo correspondiente.
source-git-commit: 976db79104d226a16a35dc04e8c8cb111eb745db
workflow-type: tm+mt
source-wordcount: '1609'
ht-degree: 0%

---


# Documento de un módulo de conector de Fusion

Utilice esta aptitud para agregar uno o más módulos nuevos a un artículo del conector de Workfront Fusion (por ejemplo, `adobe-firefly-modules.md`, `adobe-photoshop-modules.md`, `azure-dev-ops.md`).

## Entradas requeridas (por módulo)

Antes de rellenar los campos de cualquier módulo, el usuario **debe** proporcionar todo lo siguiente. Si falta alguno, deténgase y pídalo antes de continuar.

1. **El nombre del módulo**, exactamente como aparece en la interfaz de usuario de Fusion (por ejemplo, `Generate adaptive composite`).
2. **Ruta del artículo del conector**: el agente localiza esto y lo confirma con el usuario (consulte Fase 1).
3. **Dirección URL de la API** para la operación de la API subyacente. Esto es necesario para que se pueda hacer referencia al propósito de cada campo en relación con las especificaciones de la API.
4. **Captura de pantalla del panel de configuración del módulo en la vista estándar** (`Show advanced settings` **sin marcar**).
5. **Captura de pantalla del panel de configuración del módulo en la vista avanzada** (`Show advanced settings` **comprobado**) o una instrucción explícita de que el módulo no tiene campos avanzados.

## Flujo de trabajo

Este es un proceso de varias fases. El ritmo es importante: trabaje *con* el usuario, no por delante de ellos. Confirme el progreso en cada límite de fase y manténgase abierto a correcciones en cualquier momento.

### Fase 1 - Ámbito de trabajo

1. **Pregunte si se trata de un módulo o de varios**: *&quot;¿Va a agregar uno o varios módulos a un artículo del conector?&quot;*

2. **Reúna todos los nombres de módulo por adelantado**, según la respuesta:
   - **Módulo único**: pida su nombre exacto tal como aparece en la interfaz de usuario de Fusion.
   - **Múltiples módulos**: pida todos los nombres a la vez, O bien pida una captura de pantalla del conector que los enumera (por ejemplo, la pantalla de información general del conector en Fusion que muestra etiquetas de mosaico para cada módulo). En cualquier caso, finalice este paso con una lista confirmada de todos los módulos nuevos que se van a agregar.

3. **Busque usted mismo el artículo del conector** buscando `help/workfront-fusion/references/apps-and-modules/` en función del nombre del conector que implican los módulos. Usar las herramientas `Glob` o `Grep`.

4. **Confirmar la ruta de acceso del artículo con el usuario**: *&quot;Según los nombres de los módulos, debería ir en `help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-firefly-modules.md`. ¿Es correcto?&quot;*

5. **Lea el artículo del conector** para conocer su estructura y convenciones existentes. Preste atención a:
   - Estilo de encabezado (normalmente `### Module name` en el caso de las frases)
   - Ordenación de módulos existente (normalmente alfabético)
   - La redacción de `Connection` filas
   - Cómo se escriben los campos anidados (por ejemplo, `Image > Source`)
   - Cualquier nota al pie o convención de anotaciones existente

### Fase 2: coloque los marcadores de posición de cada módulo en la parte delantera

Incluso si solo hay un módulo nuevo, esto le ofrece al usuario una hoja de ruta visual clara. Si hay varios módulos nuevos, colóquelos todos ahora.

Para cada módulo nuevo, inserte una sección de marcador de posición en la posición alfabética:

```markdown
### Module name

<!-- PLACEHOLDER: Add description of the Module name module here. -->

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>For instructions on creating a connection to [!DNL Connector Name], see <a href="#create-a-connection-to-connector-name" class="MCXref xref" >Create a connection to [!DNL Connector Name]</a> in this article.</td> 
  </tr> 
  <!-- PLACEHOLDER: Add field rows for the Module name module here. -->
 </tbody> 
</table>
```

Muestre al usuario la lista de marcadores de posición que se añadieron (por ejemplo, &quot;Marcadores de posición añadidos para: Generar compuesto adaptable, Generar imágenes con Image5, Generar compuesto preciso, Generar vídeo&quot;). A continuación, pregunte cuál comenzar con: *&quot;¿Con cuál desea comenzar?&quot;*

### Fase 3: bucle de documentación por módulo

Para cada módulo, complete este bucle completamente antes de pasar al siguiente:

#### 3 bis. Obtener la URL de API

Pida al usuario la URL de la API: *&quot;Comparta la URL de la API para la operación de la API subyacente de `<module name>`.&quot;*

Cuando lo tenga:
- Pruebe `WebFetch` en la dirección URL.
- Si la página está vacía/representada mediante JS (algo común en los documentos de Adobe Developer), busque una página de guía de funciones relacionada (normalmente en una URL de `.../guides/how-tos/...`) y búsquela.
- Si no hay suerte, vuelva a `WebSearch` para el nombre de la operación.

Utilice lo que aprenda como contexto de fondo para las descripciones de los campos más adelante. No se lo vuelque al usuario; sólo reconozca brevemente: *&quot;Se obtuvo el contexto de la API: listo para la captura de pantalla de la vista estándar.&quot;*

#### 3 ter. Obtenga la captura de pantalla de vista estándar

Preguntar: *&quot;Comparta una captura de pantalla del panel de configuración del módulo con `Show advanced settings`**sin marcar**. Después de revisar los campos estándar, pediré la vista avanzada, pero aún no la envíe.&quot;*

#### 3 quater. Documente los campos estándar

Trabajando desde la captura de pantalla de la vista estándar, capture cada campo visible de arriba a abajo. Para cada campo:

1. Utilice la etiqueta de interfaz de usuario exacta del campo como encabezado de fila. Para campos agrupados, únase con ` > `:

   ```
   [!UICONTROL Background > Image > Source]
   ```
2. Lea el texto de ayuda debajo del campo en la captura de pantalla (el pie de ilustración gris/amarillo). Utilícelo como base para la descripción.
3. Haga referencias cruzadas del contexto de la API del paso 3a para identificar lo que representa el campo (por ejemplo, `background.fillAreaMask` es &quot;el área del fondo donde se colocará el objeto&quot;).
4. Escriba la descripción combinando **lo que es el campo** (de la API) con **cómo proporcionarlo** (del texto de ayuda de la interfaz de usuario y el tipo de campo).

Omita cualquier campo que no esté visible en la captura de pantalla, aunque la API lo admita. No inventes campos.

Una vez establecidos los campos estándar, revíselos brevemente al usuario (por ejemplo, &quot;Campos estándar añadidos: Conexión, Preguntar, Relación de aspecto, ...&quot;) y, a continuación, avance al paso 3d.

#### 3d. Obtenga la captura de pantalla de vista avanzada

Preguntar: *&quot;Ahora comparta una captura de pantalla del panel de configuración del módulo con `Show advanced settings`**comprobado**. Si el módulo no tiene campos avanzados, dilo y nos adelantaremos.&quot;*

#### 3e. Documente los campos avanzados

Trabajar desde la captura de pantalla de vista avanzada:

1. Identifique los campos que *no están* en la vista estándar; son los campos avanzados.
2. Para cada campo avanzado, siga el mismo proceso de descripción del paso 3c.
3. Anexar `*` al nombre de campo dentro de `<td role="rowheader">`:

   ```html
   <td role="rowheader">[!UICONTROL Seeds]*</td>
   ```
4. Después de cerrar `</table>`, agregue esta nota al pie en su propia línea:

   ```markdown
   * These fields are advanced fields, and do not display unless you select **[!UICONTROL Show advanced settings]**.
   ```

Si el usuario dice que el módulo no tiene campos avanzados, omita los pasos 3d y 3e por completo.

#### 3 septies. Borrador de la descripción del módulo

Ahora (no antes), reemplace el marcador de posición de descripción en la parte superior de la sección con un borrador de una frase basado en el contexto de la API y en lo que implican los campos. Ofrezca siempre como borrador para la revisión del usuario:

> *&quot;Redacté esta descripción: &#39;...&#39;. ¿Desea usar eso, editarlo o reemplazarlo?&quot;*

#### 3g. Resumen por módulo

Proporcione al usuario un resumen final de los campos documentados del módulo (estándar + avanzado) y formule cualquier pregunta abierta:

- ¿Hubo campos cortados en las capturas de pantalla?
- ¿Es aceptable la descripción del módulo?
- ¿Se debe marcar algo como obsoleto o digno de mención?

Espere a que se confirme antes de decir que el módulo ha finalizado. Entonces pregunte: *&quot;¿Listo para pasar al siguiente módulo?&quot;* (o &quot;Hemos terminado con este artículo del conector&quot;).

### Fase 4 - Verificación final

Una vez documentados todos los módulos, revise esta lista de comprobación para cada uno de ellos:

- [ ] El encabezado del módulo es `### ` (H3) y usa mayúsculas y minúsculas.
- [ El módulo ] aparece en orden alfabético en relación con los módulos relacionados.
- [ ] La primera fila es `Connection` y usa la redacción estándar de vínculo de conexión.
- [ ]: todos los campos documentados son visibles en las capturas de pantalla del usuario.
- [ ] Los campos avanzados están marcados con `*` y existe una sola nota al pie debajo de la tabla.
- [ ] No se han inventado campos solo desde la API.
- [ ]: las descripciones desplegables de Source utilizan las etiquetas de opciones exactas de la interfaz de usuario (consulte la &quot;Convención de campos de Source&quot; a continuación).
- [ ] La descripción del módulo es un resumen de una oración que describe lo que hace el módulo.

## Convención de campo de Source

Los campos de fuente de imagen en los conectores de Fusion suelen presentar una lista desplegable con dos opciones. **Use las etiquetas exactas que se muestran en la captura de pantalla del usuario**; diferentes generaciones de módulos usan palabras diferentes:

| Si se muestra la lista desplegable... | Usar este formato |
|---|---|
| **Cargar imagen** y **URL de imagen** (módulos más recientes) | `<ul><li><b>Upload Image</b><p>Upload the image, or map the image file from a previous module.</p></li><li><b>Image URL</b><p>Enter or map the URL of the image.</p></li></ul>` |
| **Archivo** y **URL prefirmada** (módulos anteriores) | `<ul><li><b>File</b><p>Select a source file from a previous module, or map the source file's reference image file name and reference image file.</p></li><li><b>Presigned URL</b><p>Enter or map the URL of the source image.</p></li></ul>` |

Si la captura de pantalla no muestra las opciones desplegables abiertas, pida al usuario que las comparta.

## Estilo de descripción de campo

- Hacer coincidir la voz y la estructura de las entradas de módulo existentes en el mismo artículo.
- Escriba descripciones breves: normalmente basta con una o dos frases por campo.
- Use el marcado `[!UICONTROL ...]` para cualquier nombre de campo de interfaz de usuario al que se haga referencia desde otro campo.
- Use `<code>...</code>` para valores literales (`<code>en-US</code>`, `<code>0.0</code>`).
- Para los campos de intervalo numérico, indique el intervalo permitido explícitamente: *&quot;Escriba un número entre 0 y 1...&quot;*.
- Para los desplegables con opciones discretas, enumérelos como un(a) `<ul>` con `<b>Option</b>` seguido(a) por una descripción de `<p>`.

## Campos comunes y descripciones recomendadas

Vuelva a utilizarlos para mantener la coherencia entre los módulos:

**Semillas** (cuando el campo permite varios valores de semilla a través de Agregar elemento):
> Haga clic en **Agregar elemento** para agregar un valor semilla y, a continuación, escriba o asigne un entero. Utilice una semilla por variación. El recuento de valores semilla debe coincidir con el valor **Number of Variations** si se proporcionan ambos.

**Número de variaciones** (reemplace el intervalo con el intervalo real de la captura de pantalla):
> Escriba un número entre [min] y [max]. El módulo genera este número de [variaciones de tipo de salida].

**Límite** (el límite estándar del ciclo de ejecución de Fusion; incluir solo si está visible en la captura de pantalla):
> Introduzca o asigne el número máximo de resultados con los que desea que funcione el módulo durante un ciclo de ejecución.

**Configuración regional**:
> Introduzca o asigne un código de idioma y región para adaptar el contenido generado a un país e idioma específicos. La configuración regional debe proporcionarse en el código de idioma ISO 639-1 y en la región ISO 3166-1. Ejemplo: `en-US`

## Estar abierto a correcciones en cualquier momento

El usuario puede corregir el trabajo anterior a mitad del flujo: semillas, texto, etiquetas desplegables, colocación en el campo, división avanzada/estándar, etc. Tratar cualquier corrección como autoritaria y actualizar sin retroceso. Después de la corrección, resuma brevemente lo que se ha cambiado.

Si el usuario introduce una nueva convención a mitad de flujo (por ejemplo, &quot;marcemos los campos avanzados con `*` y añadamos una nota al pie&quot;), adoptarla para el resto de la sesión y aplicarla retroactivamente a cualquier módulo ya documentado.

## Qué hacer si la información es contradictoria

Cuando la especificación de la API y la interfaz de usuario no coinciden (esto sucede a menudo):

1. **Confía en la interfaz de usuario**, porque eso es lo que el usuario ve realmente en Fusion.
2. **Observe la discrepancia** en su respuesta al usuario para que pueda decidir si desea investigar más a fondo.
3. **No inventes una explicación** en el cuerpo del artículo, mantén la idea de lo que hay en la interfaz de usuario.

Si dos capturas de pantalla del usuario se contradicen entre sí (por ejemplo, una muestra `Blend` y otra muestra `Harmonization` para el mismo módulo), deténgase y pregunte cuál es la correcta antes de escribir. Identifique qué captura de pantalla probablemente pertenezca a un módulo diferente haciendo referencia cruzada a la especificación de la API.
