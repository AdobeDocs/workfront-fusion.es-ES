---
product-previous: workfront-fusion
content-type: release-notes
product-area: workfront-integrations
navigation-topic: fusion-release-activity
title: 'Actividad en la versión de Workfront Fusion: semana del martes, 16 de noviembre de 2020'
description: En esta página se describen todas las mejoras realizadas en Adobe Workfront Fusion durante la semana del martes, 16 de noviembre de 2020.
author: Luke
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
hidefromtoc: true
exl-id: 69e4a458-fd32-4dcd-be43-19a9467cf678
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 21%

---

# Actividad de la versión de Workfront Fusion: semana del martes, 16 de noviembre de 2020

En esta página se describen todas las mejoras realizadas en Adobe Workfront Fusion durante la semana del martes, 16 de noviembre de 2020.

Para obtener una lista de todos los cambios recientes, consulte [Actividad de la versión de Adobe Workfront Fusion](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md).

Para obtener una lista de las correcciones de errores recientes en Workfront Fusion, consulte la página [Actualizaciones de mantenimiento de Workfront](https://experienceleague.adobe.com/docs/workfront-known-issues/releases/current-updates.html?lang=es) y busque cualquier actualización etiquetada como Actualización de mantenimiento de Workfront Fusion.

## Actualizaciones en el conector de Jira Cloud

Para ampliar las formas de utilizar el conector Jira Cloud, hemos añadido tres módulos nuevos:

* Añadir problema al sprint
* Enumerar registros
* Buscar registros

También hemos actualizado los módulos existentes para admitir el tipo de objeto &quot;Sprint&quot;. Anteriormente, solo se podía acceder al objeto &quot;Sprint&quot; a través del módulo Llamada de API personalizada.

## El ID de ejecución ya está disponible para la asignación en escenarios

El ID de ejecución de un escenario ya está disponible en el panel Asignación. Este ID representa una ejecución específica del escenario y se puede utilizar como metadatos. Por ejemplo, el ID de ejecución se puede guardar con un registro que Fusion cree, para que pueda determinar más adelante qué ejecución de Fusion creó el registro. Puede encontrar el ID de ejecución en el panel de asignación, en Funciones generales.

## Métodos abreviados de teclado para escenarios de Workfront Fusion 2.0

Para que la creación de escenarios sea más conveniente, hemos agregado algunos métodos abreviados de teclado:

* Ctrl/Cmd+Mayús+Entrar: Ejecutar un escenario una vez
* Ctrl/Cmd + Mayús + S: guardar un escenario

## Actualizaciones del conector de Office 365 Excel

Para ampliar las formas de utilizar el conector de Excel de Office 365, hemos añadido algunos módulos nuevos. Ahora puede hacer lo siguiente:

* Almacenar en déclencheur un módulo de cambios en libros
* Buscar o descargar libros
* Mostrar una lista de hojas de cálculo, filas de hoja de cálculo, tablas o filas de tabla
* Actualizar una tabla o fila de hoja de cálculo
* Eliminar una tabla o una fila de la hoja de cálculo
* Recuperación de metadatos de una tabla
* Realizar una llamada de API personalizada

Los módulos disponibles anteriormente siguen presentes en la aplicación.


## Uso de OAuth 2.0 en las conexiones de aplicaciones de Workfront

Hemos actualizado el conector de Workfront para que utilice OAuth 2.0. Esta actualización significa que es más fácil realizar cambios en las conexiones de la aplicación de Workfront. Por ejemplo, si algo sobre su conexión cambia (como una contraseña), ya no necesita actualizar cada conexión individual en sus escenarios. Además, OAuth2 ofrece otras ventajas, como una seguridad mejorada y la capacidad de usar el inicio de sesión único (SSO).

Las conexiones existentes no requieren ningún cambio en este momento. Sin embargo, puede volver a autorizar las conexiones existentes si desea aprovechar las ventajas de OAuth 2.0.
