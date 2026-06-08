---
title: Encadenar varios escenarios juntos
description: Puede encadenar escenarios juntos, permitiendo que un escenario almacene en déclencheur otro y devolviendo la salida de datos por el segundo escenario al primero.
author: Becky
feature: Workfront Fusion
exl-id: def8d4c1-fc20-4b93-b1fd-be2f60300464
TQID: https://experienceleague.adobe.com/ypbKUSaT72N2r75oYX9tZsJaj6H39cUCumApjMw69j0
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 81d1dfcdb5c15f6a93e2793f9a0e41821b65c7e3
workflow-type: tm+mt
source-wordcount: 1705
ht-degree: 9%

---

# Encadenar varios escenarios juntos

>[!IMPORTANT]
>
>Esta función se encuentra en Beta y no se recomienda para flujos de trabajo de producción esenciales. Como función de Beta, el comportamiento puede cambiar y es posible que los casos extremos no se gestionen completamente.
>
>Para integraciones estables, considere la posibilidad de activar un segundo escenario a través de un gancho web utilizando un módulo de solicitud HTTP: este patrón utiliza primitivas totalmente compatibles y proporciona a cada escenario un control de ejecución independiente.
>
>Si decide utilizar escenarios encadenados, revise atentamente las instrucciones de diseño y las restricciones de este artículo, especialmente la sección [Prácticas recomendadas](#best-practices).

Puede encadenar escenarios juntos, permitiendo que un escenario almacene en déclencheur otro y devolviendo la salida de datos por el segundo escenario al primero. Esto permite crear escenarios más modulares, donde no tiene que duplicar secciones de escenarios en varios escenarios.

Puede llamar a varios escenarios secundarios desde un escenario principal y a un escenario secundario desde varios escenarios principales. También puede anidar escenarios secundarios y llamar a uno desde otro.

Cuando un escenario principal está esperando que un escenario secundario devuelva datos, ese tiempo no se cuenta para el tiempo de espera del escenario principal. Por ejemplo, un escenario principal llama a 5 escenarios secundarios, cada uno de los cuales tarda 10 minutos en ejecutarse, para un total de 50 minutos. Los módulos del propio escenario principal tardan 15 minutos en ejecutarse. El escenario principal no agota el tiempo de espera, aunque haya transcurrido un total de 65 minutos, lo que supera el límite de tiempo de espera de 40 minutos.

Para obtener más información sobre las protecciones de rendimiento de Fusion, incluidos los tiempos de espera, consulte [protecciones de rendimiento de Fusion](/help/workfront-fusion/references/scenarios/fusion-performance-guardrails.md).

Para obtener instrucciones sobre la configuración de módulos de cadena, consulte [Módulos de cadena](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/chain-modules.md).

## Escenarios principales y secundarios

* El escenario **parent** llama a otro escenario mediante el módulo **Chain** > **Call a child scenario**. Recibe el resultado del escenario secundario, que puede procesar en módulos de escenario posteriores.
* El escenario **child** es invocado por el escenario primario. Su módulo de déclencheur recibe datos del escenario principal y devuelve el resultado al escenario principal.

El escenario principal requiere una respuesta del escenario secundario. Actualmente no se admiten escenarios secundarios que no devuelvan datos.

## Estructuras de datos en escenarios encadenados

Workfront Fusion utiliza estructuras de datos para transferir información del escenario principal al escenario secundario. La estructura de datos se configura en el escenario secundario. Cuando se selecciona el escenario secundario del escenario principal, los campos de la estructura de datos utilizada como entrada del escenario secundario aparecen en el escenario principal. Puede asignar valores a estos campos, que se pasan al escenario secundario cuando se activa.

Para obtener información sobre los módulos que se van a configurar en los escenarios principal y secundario, vea [Módulos de cadena](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/chain-modules.md).

Para obtener información sobre las estructuras de datos, vea [Estructuras de datos](/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md).

## Flujo de datos

1. Los datos fluyen a través del escenario principal.
1. Los datos llegan al módulo Invocar a un escenario secundario. Los datos se asignan a los campos del módulo Invocar a un escenario secundario, que coinciden con los campos de la estructura de datos utilizada en el módulo de déclencheur del escenario secundario.
1. Los datos del escenario Llamar a un elemento secundario se pasan al escenario secundario.
1. El escenario secundario procesa los datos y realiza acciones.
1. El escenario secundario finaliza con la respuesta Devolver al módulo principal.
1. El resultado de la respuesta Devolver al módulo principal se pasa al escenario principal.
1. El resultado del escenario Llamar a un escenario secundario es el resultado del escenario secundario. Este resultado se puede procesar más adelante en el escenario principal.

## Casos de uso

Consideremos los siguientes ejemplos de casos de uso para encadenar escenarios:

* **Lógica reutilizable**: puede encadenar escenarios para acciones repetidas utilizadas en varios escenarios. Por ejemplo, si tiene varios escenarios que archivan contenido, puede crear un único escenario secundario denominado &quot;Archivar contenido&quot; que puede utilizar como escenario secundario para cualquier flujo de trabajo que archive contenido.

* **Control de errores**: Es común que las organizaciones tengan las mismas acciones de control de errores en varios escenarios, como una ruta de control de errores que envía un registro de errores a un almacén de datos y crea una notificación de demora. Puede crear un escenario secundario con estas acciones y encadenarlo en rutas de gestión de errores en varios escenarios.

* **Tiempo de ampliación**: puede usar el encadenamiento para operaciones por lotes grandes en las que el tiempo total de procesamiento excedería el límite de ejecución de 40 minutos de un solo escenario. Sin embargo, trate este patrón con precaución: un escenario principal que se encadena a varios escenarios secundarios de larga duración no tiene un límite de tiempo de espera general. Si se bloquea cualquier escenario secundario o se produce un problema de plataforma, el padre espera indefinidamente sin mostrar un error.

  Antes de utilizar el encadenamiento para ampliar el tiempo de ejecución, considere si el tamaño del lote puede reducirse, si la frecuencia puede aumentar o si el diseño puede reestructurarse para evitar largas cadenas secuenciales. Consulte [Prácticas recomendadas](#best-practices) a continuación.

* **Reemplazar iteradores**: reemplazar iteradores con escenarios secundarios puede reducir el uso de memoria, como en operaciones complejas en una iteración que provocan un error de Memoria insuficiente. Puede crear un escenario independiente para la operación compleja y reemplazar el iterador con el módulo Invocar a un escenario secundario

* **Busque y cree un registro**: Por ejemplo, podría crear un escenario que busque un usuario. Si existen, el escenario los añade como aprobadores con el acceso que necesitan para revisar y aprobar. Si no existen, el escenario crea una solicitud para que el administrador incorpore un nuevo usuario.

## Visualización del historial de ejecución para escenarios encadenados

Puede ver el historial de ejecución de los escenarios encadenados consultando el historial de cada escenario incluido en la cadena. Por ejemplo, el historial de ejecución del escenario principal incluiría información sobre los módulos y los datos procesados directamente en el escenario principal. Para ver el historial de ejecución de los módulos y datos procesados en un escenario secundario, abra el escenario secundario y vea allí el historial de ejecución.

Se recomienda usar el botón **Ir al escenario secundario** en el módulo Llamar a un escenario secundario para ir rápidamente al escenario secundario, donde puede ver su historial de ejecución. El escenario secundario se abre en otra ventana del explorador, lo que le permite ver los escenarios principal y secundario al mismo tiempo.

![Botón Ir al escenario secundario](assets/go-to-the-child-button.png)

## Errores y ejecuciones incompletas

### Gestión de errores

Si se produce un error en el escenario secundario, esto puede afectar a la devolución de datos a su principal.

Se recomienda configurar el control de errores en el escenario secundario para garantizar que, si algo sale mal en el escenario secundario, el escenario principal no se quede atascado esperando la respuesta del escenario secundario.

## Prácticas recomendadas

Tenga en cuenta las siguientes prácticas recomendadas al encadenar un escenario.

### Evite la recursión al encadenar escenarios

La recursividad se produce cuando un escenario activa una nueva ejecución de sí mismo, lo que activa una nueva ejecución, y así sucesivamente en un bucle infinito.

La recursividad puede causar problemas de rendimiento tanto para la organización propietaria del escenario recursivo como para otras organizaciones.

Al encadenar escenarios, siga estas prácticas para evitar la recursión:

* Asegúrese de que **los escenarios secundarios no puedan almacenar en déclencheur el escenario principal**. Por ejemplo, si se activa un escenario principal cuando se crea una solicitud, asegúrese de que los escenarios secundarios no creen solicitudes.
* Asegúrese de que **los escenarios secundarios no se llamen entre sí**. Por ejemplo, si el escenario secundario A llama al escenario secundario B, asegúrese de que el escenario secundario B no llame al escenario secundario A.
* Asegúrese de que **un escenario no se puede llamar a sí mismo**. Por ejemplo, se activa un escenario cuando se crea una tarea y ese escenario crea dos tareas. Las tareas recién creadas vuelven a activar el escenario, lo que crea cuatro tareas nuevas. Cada vez que se crea una tarea, se activa el escenario y, cada vez que se ejecuta el escenario, se duplica el número de tareas. El número de tareas aumenta exponencialmente.

>[!IMPORTANT]
>
>* **Cuando un escenario está produciendo recursividad, el equipo de ingeniería de Fusion lo desactiva para evitar nuevos problemas de rendimiento.**
>* Dado que la recursividad es el resultado del diseño de escenarios, debe diseñarlos de manera que se garantice que el escenario no incluya acciones que lo activen.
>* Puede ver un diagrama de las relaciones entre los escenarios principal y secundario.
>   Para obtener instrucciones, consulte [Ver relaciones de escenarios encadenados](/help/workfront-fusion/manage-scenarios/view-chained-scenario-relationships.md).

### Utilice la gestión de errores para garantizar una respuesta

Dado que el escenario principal está esperando una respuesta del escenario secundario antes de poder continuar, debe asegurarse de que el escenario secundario esté creado para proporcionar una respuesta aunque encuentre un error.

### No utilice la configuración &quot;Comprometer último Déclencheur (CTL)&quot;

No se recomienda utilizar la configuración de escenario &quot;Confirmar último Déclencheur (CTL)&quot; con escenarios encadenados. Si necesita volver a intentar el comportamiento en un escenario que utiliza el encadenamiento, impleméntelo explícitamente utilizando una ruta de control de errores con un recuento máximo de reintentos definido.

### Limitar profundidad de anidación

Limite las redes de escenarios encadenados a dos niveles de profundidad (principal → secundario). Los escenarios anidados a tres o más niveles de profundidad (padre → hijo → nieto) aumentan significativamente la complejidad, reducen la observabilidad y dificultan el diagnóstico de errores sin soporte técnico.

Si su diseño requiere un anidado más profundo, documente el mapa de cadena completo y asegúrese de que la monitorización esté implementada antes de implementarla en producción.

### Use Fuego y Olvídese con cuidado

Cuando **Activar y olvidar** está habilitado en el módulo Llamar a un escenario secundario, el escenario principal envía el escenario secundario y continúa inmediatamente sin esperar una respuesta. El padre no tiene visibilidad de si el escenario secundario se ejecutó, tuvo éxito o falló.

Usar Fuego y Olvidar solo cuando:

* El escenario secundario realiza registros, notificaciones o escrituras de auditoría que no afectan a la lógica del escenario principal
* Dispone de supervisión independiente para detectar errores secundarios silenciosos

No utilice Fuego y Olvidar cuando:

* El escenario secundario realiza escrituras de las que depende el principal
* Debe saber si el escenario secundario se realizó correctamente antes de que el principal continúe
* El flujo de trabajo es transaccional o requiere garantías de procesamiento de exactamente una vez

### Evite llamar a escenarios secundarios dentro de iteradores de gran volumen

Al colocar un módulo de escenario Llamar a un escenario secundario dentro de un BasicFeeder u otro iterador, se distribuye un escenario secundario para cada elemento procesado. Al contar un número elevado de artículos (cientos o más por ejecución), esto crea una carga de envío significativa y aumenta la exposición a los problemas de fiabilidad de la plataforma.

Antes de usar este patrón:

* Considere si la lógica del escenario secundario se puede integrar directamente en el escenario principal como módulos
* Precalcule las búsquedas que devuelvan el mismo valor para cada iteración fuera del iterador, en lugar de enviar una llamada en cadena por elemento
* Confirme el recuento máximo realista de elementos y revíselo al administrador antes de implementarlo en la producción

