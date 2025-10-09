---
title: El editor de escenarios
description: El editor de escenarios permite crear y editar escenarios en una interfaz visual.
author: Becky
feature: Workfront Fusion
exl-id: 47ccecf0-751c-4026-96a9-329c33cb6801
source-git-commit: ce2a41a9708bb0e611ab4056aac733d58d27d7a9
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 32%

---

# El editor de escenarios

El editor de escenarios permite crear y editar escenarios en una interfaz visual.

![Editor de escenarios](assets/scenario-editor.jpg)

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront</td> 
   <td> <p>Cualquiera</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencia de Adobe Workfront</td> 
   <td> <p>Nuevo: estándar</p><p>O</p><p>Actual: [!UICONTROL Work] o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion**</td> 
   <td>
   <p>Actual: no se requiere licencia de Workfront Fusion.</p>
   <p>O</p>
   <p>Heredado: cualquiera </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Plan de Workfront de [!UICONTROL Select] o [!UICONTROL Prime]: su organización debe adquirir Adobe Workfront Fusion.</li><li>Plan de Workfront de [!UICONTROL Ultimate]: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe comprar Adobe Workfront Fusion.</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">Configuraciones de nivel de acceso*</td> 
   <td> 
     <p>Debe ser administrador de Workfront Fusion para su organización.</p>
     <p>Debe ser administrador de Workfront Fusion para su equipo.</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Abra el editor de escenarios y agregue un módulo:

1. Haga clic en **[!UICONTROL Icono de escenarios]** ![escenarios](assets/scenarios-icon.png) en el panel izquierdo.
1. Haga clic en el icono de signo de interrogación ![icono de pregunta](assets/question-mark-full-size.png) y, a continuación, busque y haga clic en la aplicación o el servicio con el que desee comenzar. Para obtener información detallada sobre la configuración de un módulo, consulte [Configurar un módulo](/help/workfront-fusion/create-scenarios/add-modules/configure-a-modules-settings.md).

## Acciones del editor de escenarios disponibles

### Ejecute su escenario

| Acción | Detalles |
|----------|----------|
| Realizar una ejecución de prueba del escenario | Compruebe que el escenario se ejecuta tal como espera antes de activarlo. Una vez activado, el escenario se ejecutará según su programación. Si todo no funciona según lo esperado, consulte [Agregar control de errores](/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md) para obtener información sobre cómo manejar los errores. |

![botón de escenario de ejecución](assets/run-your-scenario.png)

### Programación

| Acción | Detalles |
|----------|----------|
| Programar el escenario | De forma predeterminada, un escenario se ejecuta cada 15 minutos. Puede cambiar esto definiendo cuándo y con qué frecuencia se ejecuta un escenario activado. Los escenarios de Fusion se pueden programar para que se ejecuten con tanta frecuencia como cada 5 minutos. Para obtener más información, consulte [Programar un escenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md). |

![panel de programación](assets/scheduling-scenario-editor.png)

### Controles

| Acción | Detalles |
|----------|----------|
| Guarde. | Después de guardar el escenario, dispondrá de una nueva versión en el menú de tres puntos en caso de que necesite acceder a ella en el futuro. Las versiones de escenarios guardadas anteriormente solo están disponibles durante 60 días. |
| Configuración de escenarios | El panel de configuración de escenario contiene la configuración avanzada del escenario. Para obtener más información acerca de la configuración disponible, vea [Configurar opciones de escenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md). |
| Notas | Tome notas sobre el escenario. Otros usuarios pueden ver estas notas cuando se encuentren en el escenario. |
| Alineación automática | Alinee automáticamente los módulos en su escenario. |
| Explicar flujo | Vea una animación en la que los puntos móviles muestran cómo fluyen los datos por el escenario. |
| Herramientas de desarrollo | Con la herramienta de desarrollo, puede comprobar todas las ejecuciones manuales de su escenario, revisar todas las operaciones realizadas y ver los detalles de cada llamada de API realizada. Puede ver qué módulo, operación o respuesta única causó el error y utilizar ese conocimiento para refinar el escenario. Para obtener más información, vea [Depurar un escenario](/help/workfront-fusion/manage-scenarios/debug-a-scenario.md). |
| Más | En el menú Más, puede importar o exportar modelos y restaurar el escenario a versiones anteriores. |

![panel de controles](assets/controls-editor-scenario.png)

### Herramientas

| Acción | Detalles |
|----------|----------|
| Control de flujo | Configure las opciones para controlar el modo en que los datos fluyen por él. Para obtener más información, [vea el vínculo necesario]. |
| Herramientas | La sección de herramientas contiene varios módulos útiles que pueden mejorar los escenarios. Para obtener más información, [vea el vínculo necesario]. |
| Analizador de texto | Utilice la herramienta Analizador de texto para analizar el texto y utilizarlo en otros módulos de escenarios. El analizador de texto no requiere una conexión. Para obtener más información, [vea el vínculo necesario]. |

![panel de herramientas](assets/tools-scenario-editor.png)

### Favoritos

Puede usar el icono Favoritos para añadir módulos que utilice con frecuencia.

![Panel de favoritos](assets/favorites-scenario-editor.png)
