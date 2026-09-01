---
title: Crear escenarios desde Almacenamiento
description: El almacenamiento se integra con el generador de escenarios de Fusion, de modo que puede crear escenarios preconfigurados directamente desde la página Almacenamiento para descargar o cargar archivos.
author: Becky
feature: Workfront Fusion
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: aef1685cb25c0cdcb0dcdf9b0c73fb482d392e5f
workflow-type: tm+mt
source-wordcount: 272
ht-degree: 0%

---

# Crear escenarios desde Almacenamiento

Para obtener información general sobre el almacenamiento, consulte [Información general sobre el almacenamiento](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/storage-overview.md).

El almacenamiento se integra con el generador de escenarios de Fusion. Desde la página Almacenamiento, los usuarios pueden crear un escenario que descargue el archivo seleccionado.

## Descargar en escenario

1. En Workfront Fusion, haga clic en **Almacenamiento** en el panel de navegación izquierdo.
1. Vaya al repositorio que contiene el archivo que desea descargar en un escenario concreto.
1. Seleccione un archivo y, a continuación, haga clic en **&quot;Descargar en escenario&quot;** en la barra de acciones.

A continuación, Fusion crea un nuevo escenario denominado **&quot;Descargar {fileName}&quot;**. Este escenario se abre en una pestaña independiente del explorador.

El escenario está preconfigurado con:

* La conexión activa.
* El repositorio, la carpeta y el archivo preseleccionados.
* Un módulo para generar una URL de descarga firmada previamente.
* Un módulo HTTP para recuperar el archivo de esa dirección URL.
* Un intervalo de programación predeterminado de 15 minutos.

## Cargar archivo en un escenario

1. En Workfront Fusion, haga clic en **Almacenamiento** en el panel de navegación izquierdo.
1. Vaya al repositorio y la carpeta que contiene el archivo que desea descargar en un escenario concreto.
1. Mientras explora dentro de una carpeta, haga clic en el menú desplegable **&quot;Cargar archivo&quot;**.
1. Seleccione **&quot;Cargar archivo en el escenario&quot;**.

A continuación, Fusion crea un nuevo escenario denominado **&quot;Cargar en {folderName}&quot;**. Este escenario se abre en una nueva pestaña del explorador. Debe agregar módulos para proporcionar el archivo que desea cargar, como el módulo de documento Workfront > Descargar.

El escenario está preconfigurado con:

* La conexión activa.
* El repositorio y la carpeta preseleccionados.
* Un módulo para generar una URL de carga prefirmada con un nombre de archivo de marcador de posición.
* Un intervalo de programación predeterminado de 15 minutos.

