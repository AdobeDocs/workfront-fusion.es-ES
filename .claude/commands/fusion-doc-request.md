---
name: fusion-doc-request
description: Gestionar una solicitud de documentación de Fusion desde la plantilla de Slack
source-git-commit: e354c51f13bd4f15172de068cac9720bd097eb8d
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 0%

---


# Solicitud de documentación de Fusion

Administra el patrón recurrente &quot;Nueva solicitud de documentación de {person}&quot; publicado en el canal de Slack `#fusion-documentation`: lea la solicitud, actualice los documentos y, a continuación, cree una tarea de seguimiento en el mismo formulario personalizado de Workfront utilizado para cada solicitud anterior de este tipo.

Este es un flujo de trabajo diferente de la aptitud `fusion-release-notes`. Esta aptitud actualiza un artículo de referencia y crea una tarea de Workfront; no crea ni actualiza una página semanal de notas de versiones de Fusion en este repositorio, aunque la solicitud indique &quot;Necesita anuncio: Sí&quot;. Use `fusion-release-notes` únicamente si el usuario solicita por separado una nota de la versión semanal.

## Paso 1: Obtener los detalles de la solicitud

Si se le proporciona un vínculo de Slack, analice `channel_id` y `message_ts` fuera de la dirección URL y recupere el subproceso (`slack_get_thread_replies` o `slack_read_thread`, según la herramienta MCP de Slack que esté conectada (pruebe ambos si falla uno). Mantenga el enlace permanente/URL del hilo - es necesario en el paso 3.

Las conexiones de Slack en este entorno son irregulares (tokens caducados, desconexiones a mitad de la sesión). Si falla una recuperación:
- Vuelva a intentarlo una vez.
- Si sigue fallando, informe claramente al usuario de que la recuperación ha fallado y pídale que pegue directamente el contenido de la solicitud. No adivines el contenido, y no te rindas silenciosamente sin decirlo.

La plantilla de solicitud tiene estos campos: extraer cada uno:

&#x200B;* **Título de característica**
&#x200B;* **Descripción**
&#x200B;* **Puntos que se agregarán a la documentación** *(a veces presentes: secciones o detalles específicos que el solicitante desea cubrir; trátelos como necesarios, no como opcionales, si se proporcionan)*
&#x200B;* **Fecha de lanzamiento prevista**
&#x200B;* **Necesita anuncio** *(Sí/No - solo informativo; consulte la nota anterior. No actúe en este campo.)*

Si la solicitud se vincula a una página wiki de Confluence con la especificación completa, búsquela (`get_wiki_content`) antes de escribir la documentación. No confíe solo en el resumen de Slack para obtener detalles técnicos (nombres de campos exactos, pasos, etiquetas de interfaz de usuario): extraiga estos de la especificación de wiki cuando esté vinculado.

## Paso 2: Actualizar la documentación

Encuentre los artículos existentes relevantes en este repositorio (grep para nombres de módulos relacionados, etiquetas de interfaz de usuario o nombres de configuración; no adivine el archivo). Actualícelas para reflejar el cambio, según la estructura, el nivel de encabezado y el estilo de casa existentes de ese artículo.

&#x200B;* No invente detalles técnicos (nombres de campo exactos, ámbitos de permisos, pasos de configuración) que no estén en la solicitud de Slack o en la especificación de wiki vinculada. Si algo no está confirmado, márquelo en línea como un comentario de HTML (por ejemplo, `<!-- BECKY CHECK ME: confirm the exact permission scope before publishing -->`) en lugar de adivinar, nunca como una llamada visible. No se debe representar en la página publicada.
&#x200B;* Si esto requiere un archivo de artículo completamente nuevo (no solo una edición en uno existente), siga las convenciones permanentes de este repositorio: no se ha fabricado `exl-id`/`TQID` en frontmatter, conecte la nueva página al índice relevante y convierta el archivo a CRLF/no-BOM después de crearlo (la herramienta `Write` toma el valor predeterminado de LF).

## Paso 3: Crear la tarea de Workfront

Proyecto: **Tareas de documentación del producto - para problemas de desarrollo que requieren mensajes**. Resuelva su ID con `insights_find_id_by_name` (entidad `project`) en lugar de codificarlo, en caso de que cambie alguna vez. Consulte Valores conocidos a continuación para ver el último ID resuelto.

Campos de tarea:

| Campo | Valor |
|---|---|
| `name` | `Becky - {Feature Title}` |
| `projectID` | de la búsqueda de proyectos anterior |
| `assignedToID` | el usuario actual, de `insights_get_current_user` |
| `categoryID` | el ID del formulario personalizado de la documentación del producto; consulte Valores conocidos a continuación. Si alguna vez no está claro, consulte `task.task_categoryID` cualquier tarea del mismo nivel reciente en este proyecto para confirmar. |
| `description` | el **texto completo del mensaje de Slack** (todos los campos de la plantilla de solicitud, no una paráfrasis), seguido de un vínculo a la conversación de Slack |
| `DE:Release notes` | Para ver una nota de la versión con formato, consulte el formato siguiente |
| `DE:Preview Date Known` | `Yes`, de forma predeterminada |
| `DE:Preview Date` | **Fecha de lanzamiento prevista** de la solicitud de forma predeterminada |
| Producto/Área | seleccione `Fusion` (un campo de enumeración en el formulario Documentación del producto; confirme el nombre de campo exacto con `insights_search_fields` si alguna vez no está claro) |

Establecer los campos de fecha de vista previa como parte de esta misma llamada de creación: no los deje para más tarde ni espere a que se los soliciten. Si el usuario indica una fecha diferente más tarde o indica que la fecha aún no se conoce, actualice en consecuencia, pero de forma predeterminada rellenarla cada vez.

Formato de nota de versión para el campo `DE:Release notes`. Comience siempre con `***FUSION***` en su propia línea, luego una línea en blanco y el título: esto marca la nota como perteneciente a Fusion (a diferencia de Core Workfront) de un vistazo:

```markdown
***FUSION***

## {Feature Title}

{Description of what changed and why it matters, in second person. A sentence or two is enough for a simple change - use multiple paragraphs and/or a bulleted list for anything with several parts or steps, the same way a full weekly release note would.}

For more information, see [{Article title}](/help/workfront-fusion/{path-to-article}.md).
```

Antes de crear la llamada, llame a `read_workflow_docs` con `workfront://tools/create-any-object`. Esta llamada establece campos personalizados y un valor de enumeración (`DE:Preview Date Known`), que lo requiere según las reglas del servidor MCP.

## Paso 4: volver a confirmar con el usuario

Informe claramente:

&#x200B;* Qué archivo(s) de documentación ha cambiado y qué ha añadido.
&#x200B;* El nombre y la dirección URL de la tarea.
&#x200B;* Los valores de campo exactos que haya establecido, incluidos los campos de fecha de vista previa.
&#x200B;* Cualquier cosa en la que no estuviera completamente seguro, por ejemplo, que Slack no estuviera disponible y trabajara solo con texto pegado, que el artículo del documento de destino fuera ambiguo o que un detalle técnico no estuviera en el material de origen y se marcara en lugar de adivinar.

## Valores conocidos (de ejecuciones anteriores)

Confirme que estos aún se resuelven en lugar de suponer que son permanentes:

&#x200B;* El proyecto &quot;Tareas de documentación del producto - para problemas de desarrollo que requieren mensajería&quot; se asigna al ID `5e69583f00236b9f767c3e3944100ee4`
&#x200B;* El formulario personalizado de documentación del producto (`categoryID`) es `5d7275b9000514604bd969d418725843`
&#x200B;* Campos personalizados usados: `DE:Release notes`, `DE:Preview Date Known`, `DE:Preview Date`
