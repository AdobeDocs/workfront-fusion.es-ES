---
title: Encadenar varios escenarios juntos
description: Puede encadenar escenarios juntos, permitiendo que un escenario almacene en déclencheur otro y devolviendo la salida de datos por el segundo escenario al primero.
author: Becky
feature: Workfront Fusion
exl-id: def8d4c1-fc20-4b93-b1fd-be2f60300464
source-git-commit: 7f73007e219714c38dd0cf29d2a1e3a4c8f6f3cc
workflow-type: tm+mt
source-wordcount: '1247'
ht-degree: 0%

---

# Encadenar varios escenarios juntos

>[!NOTE]
>
>Esta función se encuentra actualmente en Beta.

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

* **Ampliación del tiempo**: puede utilizar el encadenamiento para operaciones por lotes grandes con acciones de ejecución prolongada, como cuando desea exportar e importar archivos. Esta operación tarda algún tiempo si hay muchos archivos. Dado que los escenarios secundarios no cuentan con el tiempo de espera del escenario principal, puede superar el tiempo de ejecución al utilizar varios escenarios secundarios para exportar o importar los archivos.

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

La recursión se produce cuando un escenario déclencheur déclencheur una nueva ejecución de sí mismo, lo que provoca una nueva ejecución, y así sucesivamente en un bucle infinito.

La recursión puede causar problemas de rendimiento tanto para la organización propietaria del escenario recursivo como para otras organizaciones.

Al encadenar escenarios, siga estas prácticas para evitar la recursión:

* Asegúrese de que **los escenarios secundarios no puedan almacenar en déclencheur el escenario principal**. Por ejemplo, si se activa un escenario principal cuando se crea una solicitud, asegúrese de que los escenarios secundarios no creen solicitudes.
* Asegúrese de que **los escenarios secundarios no se llamen entre sí**. Por ejemplo, si el escenario secundario A llama al escenario secundario B, asegúrese de que el escenario secundario B no llame al escenario secundario A.
* Asegúrese de que **un escenario no se puede llamar a sí mismo**. Por ejemplo, se activa un escenario cuando se crea una tarea y ese escenario crea dos tareas. Las tareas recién creadas vuelven a almacenar en déclencheur el escenario, lo que crea cuatro tareas nuevas. Cada vez que se crea una tarea, se activa el escenario y, cada vez que se ejecuta, se duplica el número de tareas. El número de tareas aumenta exponencialmente.

>[!IMPORTANT]
>
>* **Cuando un escenario está causando recursión, el equipo de ingeniería de Fusion lo desactiva para evitar nuevos problemas de rendimiento.**
>* Dado que la recursividad es el resultado del diseño de escenarios, debe diseñarlos de manera que se garantice que el escenario no incluya acciones que lo déclencheur.

### Utilice la gestión de errores para garantizar una respuesta

Dado que el escenario principal está esperando una respuesta del escenario secundario antes de poder continuar, debe asegurarse de que el escenario secundario esté creado para proporcionar una respuesta aunque encuentre un error.
