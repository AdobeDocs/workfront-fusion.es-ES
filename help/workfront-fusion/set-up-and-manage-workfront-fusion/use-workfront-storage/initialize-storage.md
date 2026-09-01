---
title: Inicializar almacenamiento
description: Cuando un usuario navega a Almacenamiento por primera vez, ve una pantalla de inicialización que crea una conexión segura a Adobe Storage en nombre del equipo.
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: a2632cb3184cd555555136288e78ab1e05e4ea9d
workflow-type: tm+mt
source-wordcount: 216
ht-degree: 0%

---

# Inicialización del almacenamiento en Workfront Fusion

El área de almacenamiento de Fusion debe inicializarse para poder ver repositorios, carpetas y archivos en el almacenamiento en la nube de Adobe.

Para obtener información general sobre el almacenamiento, consulte [Información general sobre el almacenamiento](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/storage-overview.md).

## Inicializar almacenamiento

1. En Workfront Fusion, haga clic en **Almacenamiento** en el panel de navegación izquierdo.
1. Haga clic en **Inicializar almacenamiento**.

Fusion crea automáticamente una conexión segura a Adobe Storage en nombre del equipo.

Una vez establecida la conexión, Fusion carga los repositorios de almacenamiento del equipo.

## Inicialización de resolución de problemas

| Mensaje | Motivo | Qué debe hacer el usuario |
| -------- | -------- | ------------------------ |
| **Acceso restringido** | La organización no está integrada en Adobe IMS. | Póngase en contacto con el administrador de la organización para completar la incorporación a IMS. |
| **No Coincide La Organización** | El usuario ha iniciado sesión en una organización de Adobe diferente a la seleccionada en Fusion. | Cierre sesión y vuelva a iniciarla con la organización Adobe IMS correcta. |
| **Acceso denegado** | La cuenta del usuario no tiene los permisos necesarios o el almacenamiento de Adobe no está disponible para la organización. | Compruebe los permisos de la cuenta con el administrador de la organización. Después de resolver, haga clic en **Reintentar**. |
| **No se encontró almacenamiento** | Se ha establecido la conexión, pero no se ha encontrado ningún repositorio. | Compruebe que el almacenamiento de Adobe esté aprovisionado para la organización. Después de verificarlo, haga clic en **Cargar almacenamiento** para volver a intentarlo. |
