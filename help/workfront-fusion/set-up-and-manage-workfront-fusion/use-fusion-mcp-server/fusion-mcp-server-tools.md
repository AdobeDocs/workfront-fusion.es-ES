---
title: Herramientas del servidor MCP de Adobe Workfront Fusion
description: Lista de referencia de las herramientas que expone el servidor de Adobe Workfront Fusion MCP a las plataformas agénticas de IA y a los colaboradores.
source-git-commit: 322a34df48a5218bc045e6cac6a5a8b3837e8c2e
workflow-type: tm+mt
source-wordcount: '1183'
ht-degree: 7%
---

# Herramientas del servidor MCP de Adobe Workfront Fusion


Este artículo enumera las herramientas que el servidor MCP de Adobe Workfront Fusion expone a un agente de IA conectado. El agente llama a estas herramientas en su nombre cuando le solicita que busque, inspeccione, cree, ejecute, actualice o elimine elementos de Fusion.

Las mismas herramientas están disponibles en todas las superficies compatibles: conexiones MCP personalizadas en Claude, ChatGPT, Copilot o su propio agente; y Coworker, tanto independientes como en el carril derecho de Fusion. Para obtener información de configuración, consulte [Configuración del servidor MCP de Adobe Workfront Fusion](configure-fusion-mcp-server.md).

El agente actúa en Fusion utilizando su Adobe ID, su función de organización de Fusion y las funciones de su equipo. Una herramienta solo funciona si tiene el permiso correspondiente en Fusion. Adobe no se responsabiliza de los cambios que el agente realice en sus datos de Fusion.

## Leer y escribir acciones

Cada herramienta se clasifica como:

* **Lectura**: recupera información sin cambiar nada, como enumerar escenarios u obtener una ejecución.
* **Write**: Crea, cambia, ejecuta o elimina datos de Fusion, como clonar un escenario o borrar una cola de ganchos web.

## Herramientas de organización

La organización activa se aplica a todas las demás herramientas de la sesión actual.

| Herramienta | Nombre | Acción | Descripción |
| --- | --- | --- | --- |
| Enumeración de organizaciones | `fusion_orgs_list` | Leer | Enumera las organizaciones de Fusion a las que puede acceder, con ID, región (zona) y etiqueta. |
| Establecer organización activa | `fusion_orgs_set` | Session | Cambia la organización activa para la sesión actual. No cambia ningún dato de Fusion. |

## Herramientas de escenario

### Escenarios

| Herramienta | Nombre | Acción | Descripción |
| --- | --- | --- | --- |
| Enumerar escenarios | `fusion_scenarios_list` | Leer | Muestra los escenarios de la organización. |
| Obtener escenario | `fusion_scenarios_get` | Leer | Devuelve un escenario, incluido su modelo completo. |
| Obtener dependencias del escenario | `fusion_scenarios_getDependencies` | Leer | Devuelve las conexiones, claves, almacenes de datos, estructuras de datos y enlaces web a los que hace referencia el modelo del escenario. |
| Buscar escenarios dependientes | `fusion_scenarios_dependents` | Leer | Busca escenarios que hagan referencia a un gancho web, almacén de datos, estructura de datos, conexión, clave o escenario determinados. Útil para el análisis de impacto antes de cambiar o eliminar un recurso. |
| Validar modelo | `fusion_scenarios_validate_blueprint` | Leer | Valida estructuralmente un modelo con un equipo (referencias de módulo, conexiones, campos obligatorios) sin guardar nada. |
| Crear escenario | `fusion_scenarios_create` | Escritura | Crea un escenario en un equipo a partir de un modelo, con nombre, descripción, carpeta, programación y procesamiento secuencial opcionales. |
| Clonar escenario | `fusion_scenarios_clone` | Escritura | Clona un escenario en el mismo equipo o en uno diferente. Al clonar entre equipos, se asigna cada conexión, gancho web, almacén de datos, estructura de datos y clave a un recurso de destino. Si lo desea, continúa desde el último registro procesado. |
| Actualizar escenario | `fusion_scenarios_update` | Escritura | Cambia el nombre, la descripción, la carpeta, la programación o el estado activo (activar/desactivar). También puede restaurar un escenario eliminado. |
| Ejecutar escenario una vez | `fusion_scenarios_execute` | Escritura | Ejecuta un escenario una vez y espera (hasta un tiempo de espera) el resultado, devolviendo el estado y cualquier mensaje de error. No compatible con escenarios instantáneos (activados por ganchos web). |
| Eliminar escenario | `fusion_scenarios_delete` | Escritura | Elimina un escenario. Los escenarios eliminados se pueden restaurar con **Actualizar escenario**. |

Ejemplos de peticiones de datos:

* _¿Qué escenarios activos del equipo de marketing no se han editado en 6 meses?_
* _¿Qué conexiones usa el escenario &quot;Salesforce → Workfront sync&quot;?_
* _Clonar &quot;Ingesta de posibles clientes&quot; en el equipo de ventas e intercambiar en la conexión de Sales Salesforce._
* _Valide este modelo antes de importarlo._
* _Ejecute &quot;Informe por la noche&quot; una vez y dígame si lo consigue._

### Versiones de escenarios

| Herramienta | Nombre | Acción | Descripción |
| --- | --- | --- | --- |
| Enumerar versiones de escenarios | `fusion_scenario_versions_list` | Leer | Enumera las versiones guardadas de un escenario. Filtrar por `version`, `createdAt`, `comment`. |
| Obtener versión del escenario | `fusion_scenario_versions_get` | Leer | Devuelve el modelo y los metadatos de una versión específica. |

Ejemplos de peticiones de datos:

* _¿Qué cambió entre la versión 12 y la versión 14 de este escenario?_

### Carpetas

| Herramienta | Nombre | Acción | Descripción |
| --- | --- | --- | --- |
| Listar carpetas | `fusion_folders_list` | Leer | Enumera carpetas de escenarios, con recuentos de escenarios. |
| Crear carpeta | `fusion_folders_create` | Escritura | Crea una carpeta en un equipo. |
| Cambiar nombre de carpeta | `fusion_folders_update` | Escritura | Cambia el nombre de una carpeta. |
| Eliminar carpeta | `fusion_folders_delete` | Escritura | Elimina una carpeta. |

## Herramientas de ejecución

| Herramienta | Nombre | Acción | Descripción |
| --- | --- | --- | --- |
| Enumerar ejecuciones | `fusion_executions_list` | Leer | Enumera las ejecuciones de un escenario o de una ejecución incompleta. Filtrar por `status` (por ejemplo `status==3` para errores, `status==2` para advertencias), `timestamp`, `duration`, `bundles`, `operations`, `transfer`. Opcionalmente incluye ejecuciones de comprobación. |
| Obtener ejecución | `fusion_executions_get` | Leer | Devuelve una sola ejecución y metadatos sobre su escenario o ejecución incompleta. |

Ejemplos de peticiones de datos:

* _Mostrarme las ejecuciones con errores de &quot;Sincronización de facturas&quot; de ayer y resumir los errores._
* _¿Qué ejecución de este escenario utilizó la mayor cantidad de operaciones esta semana?_

## Herramientas de operaciones (uso)

| Herramienta | Nombre | Acción | Descripción |
| --- | --- | --- | --- |
| Obtener operaciones | `fusion_operations_get` | Leer | Devuelve una serie temporal de operaciones (por día o mes) para un intervalo de fechas de hasta 1 año. Filtre por equipo, escenario o paquete; agrupe por módulo, paquete, escenario o equipo. |
| Obtener resumen de operaciones | `fusion_operations_summary_by_org` | Leer | Devuelve el total de operaciones por escenario y equipo para un intervalo de fechas, más el total general. |

Ejemplos de peticiones de datos:

* _Los 10 escenarios principales por operaciones el mes pasado._
* _¿Cuántas operaciones usó la aplicación de Salesforce en el tercer trimestre?_

## Herramientas de conexión y clave

Estas herramientas solo devuelven metadatos. No devuelven credenciales, tokens o valores secretos.

| Herramienta | Nombre | Acción | Descripción |
| --- | --- | --- | --- |
| Buscar conexiones | `fusion_connections_search` | Leer | Muestra las conexiones. Filtrar por `name`, `accountName`, `accountType`, `expire`, `teamId`, `scopesCount`, `editable`, `environmentType`, `authenticationType`. |
| Obtener conexión | `fusion_connections_get` | Leer | Devuelve los detalles de una sola conexión. |
| Claves de búsqueda | `fusion_keys_search` | Leer | Claves de lista. Filtrar por `name`, `typeName`, `teamId`. |
| Obtener clave | `fusion_keys_get` | Leer | Devuelve los detalles de una sola clave. |

Ejemplos de peticiones de datos:

* _¿Qué conexiones caducan en los próximos 30 días y qué escenarios las utilizan?_

## Herramientas de webhook

### Webhooks

| Herramienta | Nombre | Acción | Descripción |
| --- | --- | --- | --- |
| Enumerar webhooks | `fusion_hooks_list` | Leer | Muestra los ganchos web (ganchos). Filtrar por `name`, `teamId`, `type`, `enabled`, `gone`, `typeName`, `scenarioId`, `priority`, `detached` y más. |
| Obtener webhook | `fusion_hooks_get` | Leer | Devuelve la configuración de un webhook, los enlaces de propietario y las referencias externas. |
| Buscar webhooks dependientes | `fusion_hooks_dependents` | Leer | Busca los enlaces web que hacen referencia a una conexión determinada. |

### Cola de webhook

| Herramienta | Nombre | Acción | Descripción |
| --- | --- | -------- | --- |
| Obtener estadísticas de cola | `fusion_queue_stats` | Leer | Devuelve el número de eventos en cola, el límite de cola y si el webhook está habilitado. |
| Enumerar cola | `fusion_queue_list` | Leer | Enumera los eventos de gancho web recibidos que esperan procesarse. |
| Obtener elemento de cola | `fusion_queue_get` | Leer | Devuelve un solo evento en cola, incluida su carga útil descodificada. |
| Eliminar elementos en cola | `fusion_queue_delete` | Escritura | Elimina eventos en cola específicos (hasta 50) o borra la cola, excluyendo opcionalmente algunos eventos. Los eventos que se están procesando actualmente no se pueden eliminar. |

Ejemplos de peticiones de datos:

* _¿Se está realizando una copia de seguridad del webhook &quot;Envíos de formularios&quot;?_
* _Mostrarme la carga del evento en cola más antiguo._

## Herramientas de almacén de datos y estructura de datos

| Herramienta | Nombre | Acción | Descripción |
| --- | --- | --- | --- |
| Enumerar almacenes de datos | `fusion_datastores_list` | Leer | Enumera los almacenes de datos con el recuento, el tamaño y el tamaño máximo de los registros. |
| Obtener almacén de datos | `fusion_datastores_get` | Leer | Devuelve los metadatos y el uso de un almacén de datos, la estructura de datos vinculada y la configuración de validación estricta. |
| Enumerar registros de almacén de datos | `fusion_data_list` | Leer | Lee registros (clave + datos JSON) de un almacén de datos, con paginación de desplazamiento. |
| Buscar almacenes de datos dependientes | `fusion_datastores_dependents` | Leer | Busca almacenes de datos que utilizan una estructura de datos determinada. |
| Buscar estructuras de datos | `fusion_data_structures_search` | Leer | Enumera estructuras de datos. Filtrar por `name`, `strict`, `teamId`. |
| Obtener estructura de datos | `fusion_data_structures_get` | Leer | Devuelve una estructura de datos, incluida su especificación de campo completo. |

Ejemplos de peticiones de datos:

* _¿Qué almacenes de datos están llenos en más del 80 %?_
* _Mostrarme los primeros 20 registros del almacén de datos &quot;Asignación de cliente&quot;._

## Herramientas de registro de actividades

| Herramienta | Nombre | Acción | Descripción |
| --- | --- | --- | --- |
| Enumerar registros de actividad | `fusion_activity_logs_list` | Leer | Enumera los eventos de auditoría de la organización (quién realizó qué, a qué entidad, cuándo). Filtrar por `entity` (por ejemplo `scenario`, `connection`, `webhook`, `data store`, `user`), `action` (por ejemplo `created`, `deleted`, `updated`, `transferred ownership`), usuario, equipo y marca de tiempo. |
| Exportar registros de actividad | `fusion_activity_logs_export` | Leer | Exporta registros de actividad como CSV o XLSX, utilizando los mismos filtros. |

Ejemplos de peticiones de datos:

* _¿Quién eliminó escenarios en los últimos 7 días?_
* _Exportar todos los cambios de conexión de este trimestre a Excel._

## Compañero

Todas las herramientas de este artículo están disponibles en Coworker, tanto de forma independiente como en el carril derecho de Fusion, y están sujetas a la misma configuración de lectura y escritura y a sus permisos.

## Actualización de las herramientas

Cuando Adobe lanza una nueva versión del servidor Fusion MCP, los agentes conectados recogen automáticamente el conjunto de herramientas actualizado. No es necesario que vuelva a conectarse.

