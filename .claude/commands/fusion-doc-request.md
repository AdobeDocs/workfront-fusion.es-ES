---
name: fusion-doc-request
description: Gestionar una solicitud de documentación de Fusion desde la plantilla de Slack
source-git-commit: ac9a22b254b591ccf55270df62a85d158bb03697
workflow-type: tm+mt
source-wordcount: '1326'
ht-degree: 0%

---


# Solicitud de documentación de Fusion

Administra el patrón recurrente &quot;Nueva solicitud de documentación de {person}&quot; publicado en el canal de Slack `#fusion-documentation`: lea la solicitud, actualice los documentos y, a continuación, cree una tarea de seguimiento en el mismo formulario personalizado de Workfront utilizado para cada solicitud anterior de este tipo.

Este es un flujo de trabajo diferente de la aptitud `fusion-release-notes`. Esta aptitud actualiza un artículo de referencia y crea una tarea de Workfront; no crea ni actualiza una página semanal de notas de versiones de Fusion en este repositorio, aunque la solicitud indique &quot;Necesita anuncio: Sí&quot;. Use `fusion-release-notes` únicamente si el usuario solicita por separado una nota de la versión semanal.

## Paso 1: Obtener los detalles de la solicitud

Si se le proporciona un vínculo de Slack, analice `channel_id` y `message_ts` fuera de la dirección URL y recupere el subproceso (`slack_get_thread_replies` o `slack_read_thread`, según la herramienta MCP de Slack que esté conectada (pruebe ambos si falla uno). Mantenga el enlace permanente/URL del hilo - es necesario en el paso 4.

Las conexiones de Slack en este entorno son irregulares (tokens caducados, desconexiones a mitad de la sesión). Si falla una recuperación:
- Vuelva a intentarlo una vez.
- Si sigue fallando, informe claramente al usuario de que la recuperación ha fallado y pídale que pegue directamente el contenido de la solicitud. No adivines el contenido, y no te rindas silenciosamente sin decirlo.

La plantilla de solicitud tiene estos campos: extraer cada uno:

* **Título de característica**
* **Descripción**
* **Puntos que se agregarán a la documentación** *(a veces presentes: secciones o detalles específicos que el solicitante desea cubrir; trátelos como necesarios, no como opcionales, si se proporcionan)*
* **Fecha de lanzamiento prevista**
* **Necesita anuncio** *(Sí/No - solo informativo; consulte la nota anterior. No actúe en este campo.)*

Si la solicitud se vincula a una página wiki de Confluence con la especificación completa, búsquela (`get_wiki_content`) antes de escribir la documentación. No confíe solo en el resumen de Slack para obtener detalles técnicos (nombres de campos exactos, pasos, etiquetas de interfaz de usuario): extraiga estos de la especificación de wiki cuando esté vinculado.

Si la solicitud, en su lugar, se vincula a una fuente secundaria que no es de confluencia (por ejemplo, una publicación de la comunidad de Experience League, un artículo de asistencia técnica o un resumen generado por IA), en lugar de una especificación autoritativa, puede utilizarla para completar los detalles técnicos que falta en el texto de Slack, pero puede tratarla como de menor confianza que la propia solicitud de Slack. Cuando entre en conflicto con el texto de Slack o lo agregue (un nombre diferente para el mismo botón o campo, un detalle no mencionado en Slack), no elija uno sin avisar: escriba el documento utilizando la redacción de la solicitud de Slack como fuente principal y marque la discrepancia en línea con un comentario de HTML (por ejemplo, `<!-- BECKY CHECK ME: Slack calls this "Activate," but the linked community post calls it "Reactivate" - confirm against the live UI. -->`) según las directrices del paso 3.

## Paso 2: Crear una rama para la solicitud

Antes de tocar cualquier archivo, cree una nueva rama de Git para esta solicitud y desprotéjala. Rama de la rama predeterminada actual (`main`), no de la rama que esté desprotegida.

Asigne un nombre a la rama `becky-{short-kebab-case-description}`, derivada del **Título de característica**; la primera palabra debe ser `becky`, que coincida con la convención de ramas existente de este repositorio (por ejemplo, `becky-webhook-update`, `becky-storage-beta-sos`). Sea breve: unas pocas palabras, no el título completo textualmente.

Si el árbol de trabajo no está limpio (cambios no confirmados del trabajo no relacionado), detenga e informe al usuario en lugar de ramificarlo.

## Paso 3: Actualizar la documentación

Encuentre los artículos existentes relevantes en este repositorio (grep para nombres de módulos relacionados, etiquetas de interfaz de usuario o nombres de configuración; no adivine el archivo). Actualícelas para reflejar el cambio, según la estructura, el nivel de encabezado y el estilo de casa existentes de ese artículo.

* No invente detalles técnicos (nombres de campo exactos, ámbitos de permisos, pasos de configuración) que no estén en la solicitud de Slack o en la especificación de wiki vinculada. Si algo no está confirmado, márquelo en línea como un comentario de HTML (por ejemplo, `<!-- BECKY CHECK ME: confirm the exact permission scope before publishing -->`) en lugar de adivinar, nunca como una llamada visible. No se debe representar en la página publicada.
* Si esto requiere un archivo de artículo completamente nuevo (no solo una edición en uno existente), siga las convenciones permanentes de este repositorio: no se fabrica `exl-id`/`TQID` en frontmatter y convierta el archivo a CRLF/no-BOM después de crearlo (la herramienta `Write` toma el valor predeterminado de LF).
* Escribir una nueva página en &quot;el índice&quot; significa AMBOS, no solo uno: una página se puede vincular desde un subíndice y seguir siendo invisible para los lectores:
  - El archivo de navegación principal para el área de producto (p. ej. `help/workfront-fusion/TOC.md`): esto es lo que realmente impulsa el árbol de navegación publicado.
  - Cualquier subíndice o página de aterrizaje de contenido que también vincule a artículos de este tipo (por ejemplo, `apps-and-modules-toc.md` para una nueva página de módulos de conector).
    Compruebe ambos explícitamente y confirme que la nueva entrada se encuentra en la misma lista, en el mismo nivel de anidación, como los artículos hermanos más cercanos en cada archivo; no suponga que agregarla a una cubre a la otra.

## Paso 4: Crear la tarea de Workfront

Proyecto: **Tareas de documentación del producto - para problemas de desarrollo que requieren mensajes**. Resuelva su ID con `insights_find_id_by_name` (entidad `project`) en lugar de codificarlo, en caso de que cambie alguna vez. Consulte Valores conocidos a continuación para ver el último ID resuelto.

Campos de tarea:

| Campo | Valor |
|---|---|
| `name` | `Becky - {Feature Title}` |
| `projectID` | de la búsqueda de proyectos anterior |
| `parentID` | el identificador de tarea principal (`parentID`, un campo del sistema - sin prefijo `DE:`): consulte Valores conocidos a continuación. Esto hace que la nueva tarea sea una subtarea, no una tarea de nivel superior del proyecto. |
| `assignedToID` | el usuario actual, de `insights_get_current_user` |
| `categoryID` | el ID del formulario personalizado de la documentación del producto; consulte Valores conocidos a continuación. Si alguna vez no está claro, consulte `task.task_categoryID` cualquier tarea del mismo nivel reciente en este proyecto para confirmar. |
| `description` | el **texto completo del mensaje de Slack** (todos los campos de la plantilla de solicitud, no una paráfrasis), seguido de un vínculo a la conversación de Slack |
| `DE:Release notes` | Para ver una nota de la versión con formato, consulte el formato siguiente |
| `DE:Preview Date Known` | `Yes`, de forma predeterminada |
| `DE:Preview Date` | la fecha citada en el mensaje original de Slack (la **fecha prevista de lanzamiento** de la solicitud), de forma predeterminada |
| `taskConstraint` + `constraintDate` | Establezca `taskConstraint` en `MFO` (debe finalizar el) con `constraintDate` = la fecha citada en el mensaje original de Slack (la **fecha de lanzamiento esperada** de la solicitud), por lo que la fecha planificada de finalización de la tarea coincide con ella también. |
| Producto/Área | seleccione `Fusion` (un campo de enumeración en el formulario Documentación del producto; confirme el nombre de campo exacto con `insights_search_fields` si alguna vez no está claro) |

Establezca los campos de fecha de vista previa y la fecha planificada de finalización como parte de esta misma llamada de creación: no los deje para más tarde o espere a que se le pregunte. Si el usuario indica una fecha diferente más tarde o indica que la fecha aún no se conoce, actualice en consecuencia, pero de forma predeterminada rellenarla cada vez.

Las nuevas tareas tienen de forma predeterminada una restricción Lo antes posible con una duración 0, en la que `plannedStartDate`/`plannedCompletionDate` se derivan del programador y se descarta silenciosamente una escritura directa en (sin errores, la fecha simplemente no cambia). Configurar `taskConstraint: "MFO"` con `constraintDate` es la manera confiable de fijar la fecha planificada de finalización en la fecha citada en el mensaje de Slack. Lea `workfront://knowledge/task/update` antes de escribir esto: es un campo de fecha/horario según las reglas del servidor MCP.

Formato de nota de versión para el campo `DE:Release notes`. Comience siempre con `***FUSION***` en su propia línea, luego una línea en blanco y el título: esto marca la nota como perteneciente a Fusion (a diferencia de Core Workfront) de un vistazo:

```markdown
***FUSION***

## {Feature Title}

{Description of what changed and why it matters, in second person. A sentence or two is enough for a simple change - use multiple paragraphs and/or a bulleted list for anything with several parts or steps, the same way a full weekly release note would.}

For more information, see [{Article title}](/help/workfront-fusion/{path-to-article}.md).
```

Antes de crear la llamada, llame a `read_workflow_docs` con `workfront://tools/create-any-object`. Esta llamada establece campos personalizados y un valor de enumeración (`DE:Preview Date Known`), que lo requiere según las reglas del servidor MCP.

## Paso 5: Confirmar de nuevo al usuario

Informe claramente:

* La rama que ha creado.
* Qué archivo(s) de documentación ha cambiado y qué ha añadido.
* El nombre y la dirección URL de la tarea.
* Los valores de campo exactos que haya establecido, incluidos los campos de fecha de vista previa.
* Cualquier cosa en la que no estuviera completamente seguro, por ejemplo, que Slack no estuviera disponible y trabajara solo con texto pegado, que el artículo del documento de destino fuera ambiguo o que un detalle técnico no estuviera en el material de origen y se marcara en lugar de adivinar.

## Valores conocidos (de ejecuciones anteriores)

Confirme que estos aún se resuelven en lugar de suponer que son permanentes:

* El proyecto &quot;Tareas de documentación del producto - para problemas de desarrollo que requieren mensajería&quot; se asigna al ID `5e69583f00236b9f767c3e3944100ee4`
* La tarea principal &quot;Becky - Tareas del canal Fusion-Documentation&quot; se asigna al ID `6a9b065100003a7554832780c2015e93` (en el mismo proyecto): se resuelve con `insights_find_id_by_name` (entidad `task`) en lugar de codificarse, en caso de que cambie alguna vez
* El formulario personalizado de documentación del producto (`categoryID`) es `5d7275b9000514604bd969d418725843`
* Campos personalizados usados: `DE:Release notes`, `DE:Preview Date Known`, `DE:Preview Date`
