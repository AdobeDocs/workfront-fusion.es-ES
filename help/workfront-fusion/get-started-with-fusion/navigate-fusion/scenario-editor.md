---
title: El editor de escenarios
description: El editor de escenarios permite crear y editar escenarios en una interfaz visual.
author: Becky
feature: Workfront Fusion
exl-id: 47ccecf0-751c-4026-96a9-329c33cb6801
source-git-commit: f968b9141173725160cea36575ad4e02a09a5e3f
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 33%

---

# El editor de escenarios

El editor de escenarios permite crear y editar escenarios en una interfaz visual.

![Editor de escenarios](assets/scenario-editor.jpg)

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Paquete de Adobe Workfront</td> 
   <td> <p>Cualquier paquete de flujo de trabajo de Adobe Workfront y cualquier paquete de integración y automatización de Adobe Workfront</p><p>Workfront Ultimate</p><p>Paquetes Workfront Prime y Select, con una compra adicional de Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencias de Adobe Workfront</td> 
   <td> <p>Estándar</p><p>Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete Select o Prime Workfront que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

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

Es posible que tenga que hacer clic en el icono de tres puntos del área Controles para ver algunos de estos controles.

| Acción | Detalles |
|----------|----------|
| Guarde. <p>![Icono de guardar](assets/save-icon.png)</p> | Después de guardar el escenario, dispondrá de una nueva versión en el menú de tres puntos en caso de que necesite acceder a ella en el futuro. Las versiones de escenarios guardadas anteriormente solo están disponibles durante 60 días. |
| Configuración de escenarios <p>![Icono de configuración de escenario](assets/scenario-settings-icon.png)</p> | El panel de configuración de escenario contiene la configuración avanzada del escenario. Para obtener más información acerca de la configuración disponible, vea [Configurar opciones de escenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md). |
| Notas  <p>![Icono de notas](assets/notes-icon.png)</p> | Tome notas sobre el escenario. Otros usuarios pueden ver estas notas cuando se encuentren en el escenario. |
| Alineación automática <p>![Icono de alineación automática](assets/auto-align-icon.png)</p> | Alinee automáticamente los módulos en su escenario. |
| Buscar módulos ![Buscar módulos](assets/search-modules-icon.png)  </p> | Introduzca un término de búsqueda para localizar un módulo y, a continuación, haga clic en los resultados de búsqueda que se llevarán a ese módulo. Puede buscar por nombre de módulo, ID, tipo o aplicación. |
| Explicar flujo  <p>![Explicar icono de flujo](assets/explain-flow-icon.png) </p> | Vea una animación en la que los puntos móviles muestran cómo fluyen los datos por el escenario. |
| DevTool <p>![Icono de DevTool](assets/devtool-icon.png)</p> | Con DevTool, puede comprobar todas las ejecuciones manuales de su escenario, revisar todas las operaciones realizadas y ver los detalles de cada llamada a la API realizada. Puede ver qué módulo, operación o respuesta única causó el error y utilizar ese conocimiento para refinar el escenario. Para obtener más información, vea [Depurar un escenario](/help/workfront-fusion/manage-scenarios/debug-a-scenario.md). |
| Exportar modelo  <p>![Icono de exportar Blueprint](assets/export-blueprint-icon.png) </p> | Exporte un modelo del escenario actual. |
| Importar modelo  <p>![Icono Importar modelo](assets/import-blueprint-icon.png) </p> | Importe un modelo de escenario exportado anteriormente. |
| Versión anterior  <p>![Icono de la versión anterior](assets//previous-version-icon.png) </p> | Vea las versiones anteriores de este escenario. |

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
