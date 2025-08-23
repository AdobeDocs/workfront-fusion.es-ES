---
title: Información general de conexión
description: Para la mayoría de las aplicaciones, es necesario crear una conexión a través de la cual Adobe Workfront Fusion pueda comunicarse con el servicio de terceros proporcionado según la configuración del escenario específico.
author: Becky
feature: Workfront Fusion
exl-id: 01132df7-4cc0-4ff3-b4d7-607a06558735
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 22%

---

# Información general de conexión

Workfront Fusion requiere una conexión para la mayoría de las aplicaciones.  Utiliza esta conexión para comunicarse con el servicio de terceros proporcionado.

Por ejemplo, si desea crear un escenario que recupere información de Workfront, debe conceder permiso a Workfront Fusion para acceder a su cuenta de Workfront.

Una conexión representa la autorización y los permisos que Fusion utiliza para acceder a la aplicación. Puede crear una o más conexiones para cada aplicación utilizada en sus escenarios y puede utilizar la misma conexión en varios módulos o escenarios.

La mayoría de las conexiones se utilizan solo para una aplicación. Por ejemplo, no se puede usar una conexión Workfront en un módulo [!UICONTROL Salesforce]. Algunas aplicaciones de [!DNL Adobe] pueden compartir conexiones. Para obtener más información, vea los artículos de esas aplicaciones, que se enumeran en [Aplicaciones Fusion y sus referencias de módulos: índice de artículos](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).

Las conexiones son propiedad de los equipos. Todos los miembros de un equipo tienen acceso a las conexiones del equipo mientras que los usuarios que no pertenecen a un equipo no tienen acceso a las conexiones de este.

## Derechos de acceso

Para cada conexión, Workfront Fusion requiere únicamente los derechos de acceso necesarios para completar correctamente un escenario determinado. Por ejemplo, si crea un escenario para descargar un documento de Workfront, Workfront Fusion no solicita permiso para crear un nuevo proyecto. Posteriormente, si descubre que necesita crear un proyecto, puede actualizar la conexión o crear una nueva que pueda crear proyectos.

No todos los servicios permiten limitar el acceso a tareas específicas. En estos casos, Workfront Fusion debe exigir derechos de acceso completos. Para obtener más información sobre cómo restringir el acceso de Workfront Fusion a su cuenta registrada en esos servicios, consulte la documentación específica de la aplicación que se enumera en [Aplicaciones Fusion y sus referencias de módulos: índice de artículos](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).
