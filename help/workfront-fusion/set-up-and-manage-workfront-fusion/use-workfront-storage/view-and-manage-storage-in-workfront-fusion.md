---
title: Visualización y administración del almacenamiento en Workfront Fusion
description: El área de almacenamiento enumera los repositorios disponibles y le permite examinar carpetas y archivos.
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: a2632cb3184cd555555136288e78ab1e05e4ea9d
workflow-type: tm+mt
source-wordcount: 330
ht-degree: 1%

---

# Visualización y administración del almacenamiento en Workfront Fusion

El área de almacenamiento de Workfront Fusion le permite ver e interactuar con repositorios en su almacenamiento de Adobe Cloud.

Para obtener información general sobre el almacenamiento, consulte [Información general sobre el almacenamiento](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/storage-overview.md).

>[!TIP]
>
>Se debe inicializar el almacenamiento para poder ver los repositorios. Para obtener instrucciones, vea [Inicializar almacenamiento](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/initialize-storage.md).

## Ver repositorios, carpetas y archivos

1. En Workfront Fusion, haga clic en **Almacenamiento** en el panel de navegación izquierdo.
Se abre una lista de repositorios.

   Si solo hay un repositorio disponible, el repositorio se abre directamente.

1. Haga clic en **Abrir** en cualquier repositorio para examinar su contenido.

   Al abrir un repositorio, se muestran las Carpetas dentro del repositorio.
1. Haga clic en una carpeta para abrirla y mostrar sus Archivos.
1. Para volver a navegar hacia arriba por la estructura de carpetas, haga clic en las rutas de exploración.


>[!NOTE]
>
>Una carpeta vacía muestra el mensaje: *&quot;Esta carpeta está vacía&quot;*

## Administrar varias conexiones de almacenamiento

Un equipo puede tener varias conexiones de almacenamiento de Adobe.

1. En Workfront Fusion, haga clic en **Almacenamiento** en el panel de navegación izquierdo.
Cuando existen varias conexiones, las pestañas aparecen en la parte superior de la página Almacenamiento, etiquetadas con el nombre de cada conexión.
1. Para cambiar a los repositorios de una conexión diferente, haga clic en la pestaña correspondiente a esa conexión.

Si una conexión deja de ser válida, por ejemplo, si su token caducó y no se pudo actualizar, se filtra automáticamente y no aparece como una pestaña. La actualización programada de tokens de Fusion mantiene las conexiones válidas automáticamente.

## Información de archivo

Cada archivo de la tabla muestra lo siguiente:

| Columna | Descripción |
| -------- | ------------- |
| **Nombre** | Nombre de archivo con un icono de documento. |
| **Tipo** | Distintivo de extensión de archivo, como PNG, PDF o JPG. |
| **Tamaño** | Tamaño de archivo. Muestra *&quot;Procesando...&quot;* si el archivo se cargó recientemente y el backend aún lo está procesando. |
| **Creado** | Fecha de creación. |

Los archivos también muestran un **distintivo de versión** (por ejemplo, `v2`, `v3`) cuando existen varias versiones.

## Controles de tabla

* **Buscar/filtrar**: filtre los archivos por nombre mediante la barra de búsqueda global.
* **Ordenando**: haga clic en los encabezados de columna para ordenarlos.
* **Paginación**: elige 10, 25, 50 o 100 elementos por página. El valor predeterminado es 25.
