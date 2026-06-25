---
name: writing-quality
description: 'Revise y mejore la calidad de la escritura técnica para artículos de procedimientos y documentación general de Workfront. Aplica la Guía de estilo de la documentación de Workfront y los principios de Desarrollo de información técnica de calidad. Se utiliza para editar, revisar o escribir artículos de procedimientos, artículos de información general, artículos de referencia o documentación general. No utilizar para notas de la versión: utilice en su lugar la habilidad de formateo de notas de la versión.'
source-git-commit: 4d32e8aab5b3b8a12dbc23e61f517fc4fd6dc9e5
workflow-type: tm+mt
source-wordcount: '1128'
ht-degree: 1%

---


# Calidad de escritura

Revisa y mejora la documentación de Workfront mediante la Guía de estilo de documentación de Workfront y los principios de DQTI.

## Flujo de trabajo

Al revisar o editar contenido:

1. Leer el archivo de destino
2. Aplicar las reglas siguientes: solucione problemas directamente o márquelos
3. Conservar la intención y la precisión técnica del autor
4. Para obtener información detallada sobre terminología, puntuación y reglas de procedimiento, consulte .claude/commands/_writing-quality-reference.md

## Voz y punto de vista

- Usar **segunda persona** (&quot;Puedes...&quot;) al dirigirse al lector
- Usa contracciones para un tono conversacional (no lo hagas, no puedes, es, son)
- Utilice &quot;Recomendamos&quot; para prácticas recomendadas, no &quot;Se recomienda&quot; ni &quot;Debería&quot;
- Al escribir para un grupo de usuarios, haga referencia a otros roles en tercera persona (&quot;Puede ver... Sin embargo, el administrador de Workfront puede restringir...&quot;)
- Nunca use pronombres de género — reestructura la oración o use &quot;ellos&quot;
- Sin barra para las opciones: use &quot;o&quot; (&quot;él o ella&quot; no &quot;él/ella&quot;)

## Claridad (DQTI)

- Una idea por frase
- Mantener frases por debajo de ~25 palabras siempre que sea posible
- El posible cliente con la acción o el resultado, no con el contexto de fondo
- Utilice la palabra más simple que transmita el significado (&quot;usar&quot; no &quot;utilizar&quot;, &quot;iniciar&quot; no &quot;iniciar&quot;, &quot;sobre&quot; no &quot;con respecto&quot;)
- Evite las nominalizaciones (&quot;crear&quot; no &quot;crear&quot;, &quot;configurar&quot; no &quot;la configuración de&quot;)
- Utilice un lenguaje específico y concreto: evite términos vagos (&quot;varios&quot;, &quot;varios&quot;, &quot;algunos&quot;)
- Evite los negativos dobles
- Utilice pronombres opcionales (&quot;eso&quot;, &quot;quién&quot;) para aclarar la estructura de la oración

## Concreción (DQTI)

- Utilice ejemplos específicos en lugar de descripciones abstractas
- Incluir valores realistas en ejemplos
- Asigne un nombre a los elementos, campos y áreas de la interfaz de usuario exactos

## Orientación de tareas (DQTI)

- Céntrese en lo que el usuario *puede hacer*, no en lo que el sistema *es*
- Procedimientos principales con verbos imperativos (&quot;Crear una tarea&quot;, &quot;Configurar notificaciones&quot;)
- Proporcionar contexto suficiente para que el usuario actúe, pero no más
- Incluya un vínculo a la ayuda detallada (&quot;Para obtener más información, consulte [artículo]&quot;).

## Uso de mayúsculas

- **Encabezados**: Siempre utilice mayúsculas y minúsculas en las frases (&quot;Crear una tarea&quot; en lugar de &quot;Crear una tarea&quot;)
- **Términos de Workfront**: utilice mayúsculas únicamente cuando haga referencia directamente a un elemento de la interfaz de usuario
   - Referencia directa: &quot;Complete el campo Fecha planificada de finalización&quot;.
   - Referencia indirecta: &quot;Cada tarea debe tener una fecha planificada de finalización&quot;.
   - Sugerencia: si puede poner &quot;the&quot; o &quot;a&quot; delante del término, normalmente debería escribirse en minúsculas
- **Botones**: seguir el uso de mayúsculas en la interfaz de usuario, excepto los botones en mayúsculas → mayúsculas
- **Roles**: &quot;Administrador del sistema&quot; para el rol en la interfaz de usuario; &quot;Administrador de Workfront&quot; para la persona

## Encabezados

- Utilice el comando obligatorio en el caso de la oración (&quot;Crear una tarea&quot;, &quot;Configurar los niveles de acceso&quot;)
- Los encabezados deben estar basados en tareas; describa lo que el usuario va a lograr
- Los artículos de información general terminan con &quot;información general&quot; (&quot;Información general de proyectos&quot;)
- Dividir secciones largas en varios encabezados con subobjetivos claros

## Referencias cruzadas y vínculos

Utilice estos patrones exactos:

| Situación | Formato |
|-----------|--------|
| Vínculo después de proporcionar información | &quot;Para obtener más información, consulte [Nombre del artículo].&quot; |
| Vínculo sin información previa | &quot;Para obtener más información, consulte [Nombre del artículo].&quot; |
| Vínculo a una sección de otro artículo | &quot;Para obtener más información, consulte [Nombre de sección] en [Nombre de artículo].&quot; |
| Vínculo a una sección del mismo artículo | &quot;Para obtener más información, consulte [Nombre de sección] en este artículo&quot;. |

- En un párrafo: en línea con el texto.
- En un paso de procedimiento: en una nueva línea después del paso
- Varios vínculos: utilizar una lista con viñetas
- Utilice &quot;esquina superior derecha&quot; / &quot;esquina superior izquierda&quot; para las posiciones de la pantalla

## Negrita y cursiva

- **Negrita** solo acciones en las que se puede hacer clic y elementos de interfaz de usuario dentro de pasos de procedimiento
- No aplique negrita a los elementos de la interfaz de usuario fuera de los pasos del procedimiento
- No ponga en negrita nombres de cuadros de diálogo, nombres de páginas, nombres de iconos o nombres de menús fuera de los pasos
- Utilice *cursiva* para el texto que el usuario debe escribir (&quot;Escriba *my.workfront.com* en el cuadro Dirección URL&quot;)
- Nunca use cursiva para dar énfasis: reestructura la oración

## Notas, sugerencias y advertencias

Usar con moderación: el uso excesivo los hace invisibles para los lectores.

- Máximo de una nota/sugerencia/advertencia por sección
- Nunca apilar varias notas
- Combinar notas relacionadas en una nota con una lista con viñetas
- No use las notas para anunciar nuevas funciones: vuelva a redactar el texto del artículo en su lugar

| Tipo | Objetivo |
|------|---------|
| `>[!NOTE]` | Información que no se ajusta al párrafo; evitar frustraciones; versiones/compatibilidad |
| `>[!TIP]` | Sugerencias agradables de tener que facilitan la vida del usuario |
| `>[!IMPORTANT]` | Información vital para el paso o procedimiento |
| `>[!WARNING]` | Alertar al usuario sobre la posible pérdida de datos |

## Procedimientos

- Usar encabezados de comando imperativos (&quot;Crear una tarea&quot;)
- Introducción sólo cuando sea necesario: el encabezamiento debería ser suficiente
- Formato de introducción preferido: frase infinita + dos puntos (&quot;Para crear una contraseña temporal:&quot;)
- Los procedimientos de un solo paso siguen utilizando una lista numerada
- Usar &quot;type&quot; o &quot;select&quot; — evita palabras vagas como &quot;set&quot; o &quot;specified&quot;
- Pasos condicionales: (Condicional) Si es miembro de más de un equipo, seleccione...
- Pasos opcionales: &quot;(Opcional) Para añadir un emoji, haga clic en...&quot;
- Describa la respuesta del sistema antes de que se produzca o inmediatamente después
- Varios métodos: primero documente la forma más directa y luego utilice &quot;Or&quot;

### Corchetes angulares derechos en procedimientos

- Use `>` para mostrar la navegación entre menús y pestañas: &quot;Haga clic en **Correo electrónico** > **Notificaciones**&quot;
- Poner en negrita los nombres de los botones, no los corchetes
- Incluir espacios entre corchetes
- No utilizar corchetes para la navegación del menú principal: utilizar el fragmento de menú principal

## Referencia rápida de puntuación

| Regla | Ejemplo |
|------|---------|
| Coma de Oxford siempre | &quot;motivo, medios y oportunidad&quot; |
| Coma antes de &quot;then&quot; en los procedimientos | &quot;Haga clic en Configuración y luego en Interfaz.&quot; |
| Coma tras año en una fecha a mitad de la frase | &quot;La edición del 2 de enero de 2016 de...&quot; |
| Sin comas solo mes-año | &quot;Enero de 2016&quot; |
| Dos puntos antes de una lista, en minúsculas después de | &quot;Seleccione una de las siguientes opciones: opción A&quot; |
| No hay dos puntos después de encabezados de procedimiento | &quot;Crear una tarea&quot; (no &quot;Crear una tarea&quot;) |
| Guiones elásticos con moderación | Reestructurar la oración si es posible |
| Períodos en las extensiones de archivo | &quot;Cargar un archivo .pdf&quot; |

Para ver las reglas terminológicas y de puntuación completas, consulte .claude/commands/_writing-quality-reference.md.

## Integridad (DQTI)

- Incluya toda la información que el usuario necesita para comprender y actuar
- No incluya información que el usuario no necesite
- Proporcione siempre un vínculo &quot;Para obtener más información&quot; a la documentación detallada
- Valores predeterminados del sistema de documentos: &quot;(Predeterminado)&quot; en listas o describa en la frase

## Organización (DQTI)

- Estructura lógica con revelación progresiva (descripción general → detalles → referencia)
- Primero, el contenido más reciente para páginas ordenadas por tiempo (por ejemplo, notas de la versión)
- Un tema por sección
- Usar listas para más de 3 elementos paralelos
- Usar tablas para comparaciones estructuradas o descripciones de campos
- Evitar párrafos de pared de texto: dividir en fragmentos digeribles

## Tipos de artículos

| Tipo | Objetivo | Convención de título |
|------|---------|-----------------|
| Información general | Contexto, diagramas, cómo funcionan las cosas, sin procedimientos | Finaliza con &quot;información general&quot; |
| Instrucciones | Tarea específica con pasos claros | Verbo imperativo |
| Introducción | Información de configuración + vínculos para nuevos usuarios | &quot;Empiece con...&quot; |
| Referencia | Descripciones de los campos en tablas | Frase de sustantivo descriptiva |

## Lista de comprobación de validación

Después de editar, compruebe lo siguiente:

- [ ] Segunda persona en todo (&quot;usted&quot;), contracciones utilizadas
- [ ] caso de oración en todos los encabezados
- [ ] términos de Workfront se capitalizaron correctamente (referencia directa e indirecta)
- [ ] Solo en negrita en acciones en las que se puede hacer clic dentro de los pasos del procedimiento
- [ ]: las referencias cruzadas utilizan un formato estándar (&quot;Para obtener más información, consulte...&quot;)
- [ ] notas/sugerencias/advertencias no apiladas, máximo de una por sección
- [ ] coma de Oxford usada de manera consistente
- [ ] Los pasos del procedimiento utilizan verbos específicos (escriba, seleccione, haga clic, no &quot;establezca&quot; ni &quot;especifique&quot;)
- [ ] pasos condicionales/opcionales etiquetados correctamente
- [ ] Sin pronombres de género
- [ ] frases son claras, concretas y orientadas a tareas
