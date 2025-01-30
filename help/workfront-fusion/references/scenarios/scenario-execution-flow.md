---
content-type: overview
title: Flujo de ejecución de escenario
description: Este artículo explica cómo se ejecuta un escenario y cómo fluyen los datos a través de él. También explica dónde puede encontrar información sobre los datos procesados y cómo leerlos.
author: Becky
feature: Workfront Fusion
exl-id: bd4f05e2-df3c-4848-9a70-3df18ca4461b
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 0%

---

# Flujo de ejecución de escenario

Este artículo explica cómo se ejecuta un escenario y cómo fluyen los datos a través de él, y cómo ver los datos procesados por cada módulo.

## Flujo de ejecución de escenario

Una vez que un escenario se configura correctamente y se activa, se ejecuta según su programación definida.

Cuando comienza el escenario, el primer módulo responde a un evento que se ha configurado para inspeccionar. Cuando devuelve datos, estos se empaquetan en paquetes. El escenario devuelve un paquete para cada evento. Por ejemplo, si un módulo está configurado para inspeccionar problemas, devolverá un paquete de datos para cada problema que encuentre.

Si el módulo de déclencheur devuelve paquetes de datos, estos pasan al siguiente módulo y el escenario continúa, pasando los paquetes a través de cada módulo sucesivo, uno a la vez.

Si los paquetes se procesan correctamente en todos los módulos, el escenario se marca como un éxito en la página de detalles del escenario.

### Ejemplo: [!UICONTROL [!DNL Workfront Fusion] for Work Automation]

>[!BEGINSHADEBOX]

**Ejemplo:** En este escenario que observa las solicitudes entrantes en [!DNL Workfront] y luego las convierte en [!DNL Workfront] proyectos, los datos fluirían de la siguiente manera:

El primer paso del escenario, realizado por el primer módulo, es inspeccionar las solicitudes. Cada solicitud que encuentra se considera un paquete. Si el módulo se ejecuta sin encontrar ningún paquete, el escenario finaliza después del primer módulo.

Si el primer módulo devuelve un paquete, este pasará por el resto del escenario. En este ejemplo, el paquete iría al segundo módulo, que convierte la solicitud en un proyecto.

![Flujo de ejecución del escenario de Workfront](assets/example-execution-flow-wf-only.png)

>[!ENDSHADEBOX]

### Ejemplo: [!UICONTROL [!DNL Workfront Fusion] for Work Automation and Integration]

>[!BEGINSHADEBOX]

**Ejemplo:** En este escenario que descarga documentos de [!DNL Adobe Workfront] y los envía a una carpeta de [!DNL Dropbox], los datos fluirían de la siguiente manera:

El primer paso del escenario, realizado por el primer módulo, es inspeccionar los documentos en Workfront. Cada documento que encuentra se considera un paquete. Si el módulo se ejecuta sin encontrar ningún paquete, el escenario finaliza después del primer módulo.

Si se devuelve un paquete, este pasa por el resto del escenario. En este ejemplo, el resto del escenario consiste en el segundo módulo, que carga el paquete en la carpeta [!DNL Dropbox].

![Flujo de ejecución del escenario de integración](assets/example-execution-flow-wf-dropbox.png)

Si el primer módulo devuelve varios paquetes, el primer paquete se cargará en [!DNL Dropbox] antes de que se cargue el segundo paquete. Luego se carga el segundo paquete, luego el tercero, etc.

>[!ENDSHADEBOX]

## Información sobre paquetes procesados

Para cada módulo, el paquete pasa por un proceso de 4 pasos antes de pasar al siguiente módulo o llegar a su destino final.

* Inicialización
* Operación
* Confirmar/revertir
* Finalización

>[!NOTE]
>
>El escenario más amplio también pasa por este proceso. Para obtener información acerca de este proceso en el nivel de escenario, vea [Ejecución de escenarios, ciclos y fases](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md).

Una vez finalizada la ejecución de un escenario, cada módulo muestra un icono con el número de operaciones realizadas. Puede hacer clic en este icono para mostrar la información detallada sobre los paquetes procesados para cada paso del proceso. Puede ver qué configuración de módulo se utilizó y qué paquetes devolvió cada módulo.

![Paquetes procesados](assets/Info-processed-bundles.png)

En este ejemplo, el módulo recibió información de entrada como:

* El ID del problema que encontró
* El objeto al que se convertirá el problema (Proyecto)
* El ID de la plantilla que utilizará para crear el proyecto
* El tipo de registro del objeto que ha encontrado (OPTASK, que es un problema)

Después del procesamiento, el módulo devolvió esta información de salida:

* ID del proyecto recién creado.

Si el módulo ha encontrado más de un problema, la información se captura para cada paquete por separado. Habría un área de Operación 2 con secciones de entrada y salida que describan el segundo paquete, y así sucesivamente.

## Errores al ejecutar un escenario

Se puede producir un error durante la ejecución del escenario. Por ejemplo, si ha eliminado la plantilla que el módulo utilizará para crear el nuevo proyecto, el escenario termina con un mensaje de error. Para obtener más información sobre cómo controlar los errores, consulte [Tipos de error](/help/workfront-fusion/references/errors/error-processing.md).

## Recursos

* Para obtener más información sobre la configuración de un escenario, consulte [Editor de escenarios](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md).
* Para obtener más información sobre la página de detalles del escenario, consulte [Detalles del escenario](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-details.md).
* Para obtener más información sobre cómo activar un escenario, vea [Activar o desactivar un escenario](/help/workfront-fusion/manage-scenarios/activate-deactivate-scenarios.md).
* Para obtener más información sobre cómo programar un escenario, vea [Programar un escenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md).
* Para obtener más información sobre los módulos, consulte [Información general sobre módulos](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md).
