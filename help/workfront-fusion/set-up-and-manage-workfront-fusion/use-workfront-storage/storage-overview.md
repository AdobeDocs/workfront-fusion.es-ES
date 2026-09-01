---
title: Resumen de almacenamiento
description: Storage es una página de Workfront Fusion que proporciona a los equipos acceso directo a sus repositorios de Adobe Enterprise Storage Management (ESM), lo que permite a los usuarios examinar carpetas, cargar y descargar archivos, ver el historial de versiones y crear escenarios de automatización.
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: d5568479d43bd5518adae5b66b132b4075e7f356
workflow-type: tm+mt
source-wordcount: 279
ht-degree: 2%

---

# Resumen de almacenamiento

<!--Add to navigation articles once this goes to production-->

El área de almacenamiento de Workfront Fusion proporciona a los equipos acceso directo a sus repositorios de Adobe Enterprise Storage Management (ESM). Los usuarios pueden examinar carpetas, cargar y descargar archivos, ver el historial de versiones y crear escenarios de automatización, todo sin salir de Fusion.

El almacenamiento es propiedad de los equipos y requiere que la organización se incorpore a Adobe Identity Management System (IMS) con acceso al almacenamiento de Adobe.

Los archivos de Fusion Storage se reflejan en Adobe Files (adobe.com/files), por lo que se puede acceder a cualquier archivo al que se pueda acceder en Adobe Files desde Fusion Storage.

Para obtener instrucciones sobre el uso de Storage, consulte:

* [Inicializar almacenamiento](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/initialize-storage.md)
* [Visualización y administración del almacenamiento en Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/view-and-manage-storage-in-workfront-fusion.md)
* [Cargar archivos al almacenamiento](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/upload-files-to-storage.md)
* [Descargar archivos de almacenamiento](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/download-files-from-storage.md)
* [Eliminar archivos del almacenamiento](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/delete-files-from-storage.md)
* [Ver el historial de versiones de archivos en Almacenamiento](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/view-storage-file-version-history.md)
* [Crear escenarios desde Almacenamiento](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/create-scenarios-from-storage.md)

## Requisitos previos de almacenamiento

Para utilizar el área de almacenamiento de Workfront Fusion, debe cumplirse lo siguiente:

* La organización está integrada en **Adobe Identity Management System (IMS)**
* La organización tiene **Almacenamiento de Adobe** disponible
* El usuario ha iniciado sesión en la **organización Adobe IMS correcta** (la que coincide con la organización Fusion seleccionada)
* La cuenta del usuario tiene **acceso al almacenamiento de Adobe**

## Glosario

Al utilizar

| Término | Definición |
| ------ | ----------- |
| **Repositorio** | Un contenedor de almacenamiento de nivel superior en Adobe ESM, normalmente asignado a un proyecto o espacio de trabajo |
| **Conexión** | Un vínculo seguro entre Fusion y Adobe Storage, creado automáticamente durante la inicialización. Utiliza la autenticación IMS de Adobe con actualización automática de tokens |
| **ESM** | Enterprise Storage Management, el servicio de almacenamiento de archivos en la nube de Adobe |
| **IMS** | Adobe Identity Management System, la plataforma de autenticación e identidad de Adobe |

<!--

## UI Reference — Key Screens

### 1. Initialization Screen

* Cloud icon with **"Adobe Storage"** heading
* Description text explaining the feature
* **"Initialize Storage"** button (primary action)
* Error variants for access restriction, org mismatch, access denied, no storage found

### 2. Repository List

* Table with **Name** and **Region** columns
* **"Open"** action button per row

### 3. File Browser

* Breadcrumb navigation bar
* **"Upload File"** dropdown button (with "Upload File" and "Upload File in Scenario" options)
* File/folder table with **Name**, **Type**, **Size**, **Created** columns
* Floating action bar on file selection with: **Download**, **Download in Scenario**, **Versions**, **Delete**
* Upload/download progress banners (top-right corner)

### 4. Version History Panel

* Right-side slide-out panel
* Version list with date, version badge, and download button per entry
* **"current"** label on the latest version

-->
