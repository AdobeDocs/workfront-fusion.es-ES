---
title: El editor de escenarios
description: El editor de escenarios permite crear y editar escenarios en una interfaz visual.
author: Becky
feature: Workfront Fusion
exl-id: 47ccecf0-751c-4026-96a9-329c33cb6801
TQID: 'https://experienceleague.adobe.com/0NhWgeBcqYtVJ7XKqZ30O1lg3fKSs7YijEhhYBQ-jfg'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: cc160f0e8c2465b4f102b6d1755088335b2a9fe5
workflow-type: tm+mt
source-wordcount: '2357'
ht-degree: 14%
---
# El editor de escenarios

El editor de escenarios permite crear y editar escenarios en una interfaz visual.

La nueva experiencia del editor de escenarios:

![Nuevo editor de escenarios](assets/scenario-editor-new.png)

La experiencia clásica del editor de escenarios

![Editor de escenarios](assets/scenario-editor.jpg)

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Paquete de Adobe Workfront</td> 
   <td> <p>Cualquier paquete del flujo de trabajo de Adobe Workfront y cualquier paquete de integración y automatización de Adobe Workfront</p><p>Workfront Ultimate</p><p>Paquetes Workfront Prime y Select, con una compra adicional de Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencias de Adobe Workfront</td> 
   <td> <p>Estándar</p><p>Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Experiencias nuevas y clásicos

Workfront Fusion está cambiando el editor de escenarios a una nueva experiencia. Durante esta transición, tanto las experiencias clásicas como las nuevas están disponibles y puede cambiar entre ellas en cualquier momento. Recomendamos utilizar la nueva experiencia.

La nueva experiencia incluye lo siguiente:

* Un lienzo rediseñado, con módulos de estilo tarjeta, un minimapa y controles de zoom.
* Nuevos controles del editor de escenarios, incluidos Buscar y reemplazar, Fragmentos y Deshacer/Rehacer.
* Un botón Preguntar IA.
* Un selector de conectores actualizado con navegación por categorías y la capacidad de marcar favoritos en línea.
* Un modo oscuro que sigue a su configuración de apariencia.
* La capacidad de plegar un enrutador para ocultar sus rutas.
* [Seguimiento en directo](/help/workfront-fusion/manage-scenarios/live-trail.md), un panel que muestra un escenario que se ejecuta mientras sucede.
* Hay varias herramientas para desarrolladores integradas en el editor de escenarios.
* Registros de depuración temporales, que se pueden activar en la configuración del escenario.

Para cambiar entre las experiencias clásica y nueva:

1. En el editor de escenarios, ubique la opción **[!UICONTROL Probar el nuevo diseño]** en la esquina superior derecha.
1. Haga clic en el botón de alternancia para cambiar a la nueva experiencia.
1. Para volver a la experiencia clásica, haga clic de nuevo en el botón de alternancia.

El escenario se vuelve a cargar al cambiar. Su elección se guarda para el usuario, por lo que no cambia la experiencia que ven sus compañeros de equipo. El cambio no cambia el escenario en sí.

Si no ve la opción, es posible que la nueva experiencia aún no esté disponible para su organización. Póngase en contacto con su administrador de Workfront Fusion.

## Utilizar el editor de escenarios en la nueva experiencia (recomendado)

* [Abra el editor de escenarios y agregue un módulo:](#open-the-scenario-editor-and-add-a-module)
* [Acciones del editor de escenarios disponibles](#available-scenario-editor-actions)

### Abra el editor de escenarios y agregue un módulo:

1. Haga clic en **[!UICONTROL Icono de escenarios]** ![escenarios](assets/scenarios-icon.png) en el panel izquierdo.
1. Haga clic en el módulo de marcador de posición para abrir la lista de aplicaciones y servicios.
1. Seleccione la aplicación o el servicio con el que desea comenzar:

   * Examine por categoría utilizando el panel de la izquierda ([!UICONTROL Favoritos], [!UICONTROL Todas las aplicaciones], [!UICONTROL Adobe Workfront], [!UICONTROL Adobe Firefly Services], [!UICONTROL Adobe Creative &amp; Content], [!UICONTROL Adobe Cloud Services], [!UICONTROL IA generativa] o [!UICONTROL Integrada]).
   * Introduzca un término en el cuadro de búsqueda para filtrar la lista.
   * Para añadir un conector a sus favoritos, pase el ratón sobre el conector y, a continuación, haga clic en el icono de estrella situado junto al conector.

   Para obtener información detallada sobre la configuración de un módulo, consulte [Configurar un módulo](/help/workfront-fusion/create-scenarios/add-modules/configure-a-modules-settings.md).

### Acciones del editor de escenarios disponibles

* [Edición de acciones](#editing-actions)
* [Programación](#scheduling)
* [Controles](#controls)
* [Herramientas](#tools)
* [Favoritos](#favorites)
* [Preguntar al AI](#ask-ai)
* [Navegación por lienzo](#canvas-navigation)
* [Visualización en lienzo](#canvas-display)

#### Edición de acciones

Estas acciones están disponibles en la parte superior de la pantalla, en lugar de en la barra de herramientas inferior.

![Parte superior de la pantalla](assets/top-bar-new.png)

| Acción | Detalles |
| ---------- | ---------- |
| Nombre del escenario | El nombre del escenario se muestra en la parte superior izquierda de la pantalla. Para cambiar el nombre del escenario, haga clic en el nombre e introduzca uno nuevo. |
| Vista compacta | Cambie a una vista en la que los módulos del lienzo se encojan a mosaicos pequeños, la cuadrícula se apriete y los nombres de módulo largos se ajusten en lugar de cortarse. Cambiar de vista no vuelve a cargar el escenario. |
| Comentarios | Envíe comentarios sobre la nueva experiencia. Este botón se encuentra en la esquina superior derecha del editor de escenarios, junto a la opción Vista compacta. |
| Deshacer </br>![Icono Deshacer](assets/undo-icon.png) | Deshacer las acciones más recientes, más recientes primero. Solo puede deshacer las acciones de la sesión actual. |
| Rehacer </br>![icono Rehacer](assets/redo-icon.png) | Rehacer acciones recientes. Solo puede rehacer acciones desde la sesión actual. |
| Historial </br>![Editar icono de historial](assets/edit-history-icon.png) | Ver un historial de los cambios realizados en esta sesión. También puede deshacer todos los cambios de sesión. |

#### Programación

![panel de programación](assets/new-scheduling-area.png)

| Acción | Detalles |
| ---------- | ---------- |
| Ejecutar una vez | Ejecutar una vez solo es un icono en el nuevo diseño. Pase el ratón sobre el icono para ver la información sobre herramientas **[!UICONTROL Ejecutar una vez]**. Aquí puede probar la ejecución del escenario y comprobar que se ejecuta como espera antes de activarlo |
| Conmutador de activación | Active o desactive su escenario. Después de activarlo, el escenario se ejecutará según su programación. |
| Programar el escenario | De forma predeterminada, un escenario con un déclencheur de sondeo se ejecuta cada 15 minutos. Puede cambiar esto definiendo cuándo y con qué frecuencia se ejecuta un escenario activado. Los escenarios de fusión sondeados se pueden programar para que se ejecuten con tanta frecuencia como cada 5 minutos. Para obtener más información, consulte [Programar un escenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md). |

#### Controles

Es posible que tenga que hacer clic en el icono de tres puntos del área Controles para ver algunos de estos controles.

![panel de controles](assets/controls-new.png)

| Acción | Detalles |
| ---------- | ---------- |
| Guarde. <p>![Icono de guardar](assets/save-icon-new.png)</p> | <p>Después de guardar el escenario, dispondrá de una nueva versión en el menú de tres puntos en caso de que necesite acceder a ella en el futuro. Las versiones de escenarios guardadas anteriormente están disponibles durante 60 días después de crearse la siguiente versión de escenario. </p><p>Para conservar el historial de versiones de los escenarios más allá de los 60 días para fines de auditoría, se recomienda guardar y archivar un modelo del escenario en otra ubicación.</p> |
| Configuración de escenarios <p>![Icono de configuración de escenario](assets/scenario-settings-icon-new.png)</p> | El panel de configuración de escenario contiene la configuración avanzada del escenario. Para obtener más información acerca de la configuración disponible, vea [Configurar opciones de escenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md). Los detalles de solicitud y respuesta no se conservan en cada ejecución. Para recopilarlos para las ejecuciones regulares del escenario, active los registros de depuración temporales. Para obtener más información, vea [Registros de depuración temporales](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#temporary-debug-logs). |
| Notas <p>![Icono de notas](assets/notes-icon-new.png)</p> | Tome notas sobre el escenario. Otros usuarios pueden ver estas notas cuando se encuentren en el escenario. Para obtener más información, vea [Agregar notas a un escenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/add-notes-to-scenario.md). |
| Alineación automática <p>![Icono de alineación automática](assets/auto-align-icon-new.png)</p> | Alinee automáticamente los módulos en su escenario. |
| Módulos de búsqueda <p>![Icono de módulos de búsqueda](assets/search-modules-icon-new.png)</p> | Seleccione un módulo de la lista para ir a ese módulo en el escenario de o introduzca un término de búsqueda para localizar un módulo y, a continuación, haga clic en los resultados de búsqueda que se llevarán a ese módulo. Puede buscar por nombre de módulo, ID, tipo o aplicación. |
| Buscar y reemplazar <p>![Icono de buscar y reemplazar](assets/find-and-replace-icon-new.png)</p> | <p>Busque y reemplace variables, fuentes de valores asignadas o conexiones en los módulos del escenario. Utilice las pestañas para:</p><ul><li>Reemplace una variable asignada en todo el escenario o en un módulo.</li><li>Reasignar referencias de un módulo de origen a otro.</li><li>Copie una conexión a uno o todos los módulos compatibles de la misma aplicación.</li></ul><p>El panel obtiene una vista previa de los módulos que se verán afectados antes de realizar el cambio. Seleccione una fila en la vista previa para ir a ese módulo en el lienzo.</p> <p>Para obtener más información, vea [Buscar y reemplazar variables, orígenes y conexiones en un escenario](/help/workfront-fusion/manage-scenarios/find-and-replace.md).</p> |
| Fragmentos <p>![Icono de fragmentos](assets/snippets-icon-new.png)</p> | <p>Los fragmentos de código son secciones de escenario que se guardan como una unidad. Para crear uno, seleccione los módulos y guárdelos como un fragmento. En el panel Fragmentos de código, puede buscar, etiquetar, obtener una vista previa, fijar, ordenar y arrastrar y soltar fragmentos de código, así como importarlos y exportarlos. Puede compartir fragmentos de código con equipos u organizaciones, o enviar una copia directamente a otro usuario. Los fragmentos compartidos se muestran en su propia pestaña.</p> <p>Para obtener más información, consulte [Guardar y reutilizar secciones de escenarios con fragmentos](/help/workfront-fusion/create-scenarios/add-modules/use-snippets.md).</p> |
| Explicar flujo <p>![Explicar icono de flujo](assets/explain-flow-icon-new.png)</p> | Vea una animación en la que los puntos móviles muestran cómo fluyen los datos por el escenario. |
| Exportar modelo <p>![Icono de exportar modelo](assets/export-blueprint-icon-new.png)</p> | Exporte un modelo del escenario actual. Para obtener más información, consulte [Copiar módulos o escenarios](/help/workfront-fusion/create-scenarios/add-modules/copy-modules-or-scenarios.md). |
| Exportar como plantilla sin encabezado <p>![Exportar como icono de plantilla sin encabezado](assets/export-as-headless-template-icon-new.png)</p> | Exporte el escenario como una plantilla sin encabezado. |
| Importar modelo <p>![Icono Importar modelo](assets/import-blueprint-icon-new.png)</p> | Importe un modelo de escenario exportado anteriormente. Para obtener más información, consulte [Copiar módulos o escenarios](/help/workfront-fusion/create-scenarios/add-modules/copy-modules-or-scenarios.md). |
| DevTool <p>![Icono de DevTool](assets/devtool-icon-new.png)</p> | Con DevTool, puede comprobar todas las ejecuciones manuales de su escenario, revisar todas las operaciones realizadas y ver los detalles de cada llamada a la API realizada. Puede ver qué módulo, operación o respuesta única causó el error y utilizar ese conocimiento para perfeccionar el escenario. Para obtener más información, vea [Depurar un escenario](/help/workfront-fusion/manage-scenarios/debug-a-scenario.md). |
| Versiones anteriores <p>![Icono de la versión anterior](assets/previous-version-icon-new.png)</p> | Vea las versiones anteriores de este escenario. Para obtener más información, vea [Ver y administrar versiones de escenarios](/help/workfront-fusion/manage-scenarios/restore-a-scenario-version.md). |

#### Herramientas

![panel de herramientas](assets/tools-new.png)

| Acción | Detalles |
| ---------- | ---------- |
| Control de flujo | Configure las opciones para controlar la forma en que los datos fluyen por el escenario. Para obtener más información, consulte [Control de flujo](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/flow-control.md). |
| Herramientas | La sección de herramientas contiene varios módulos útiles que pueden mejorar los escenarios. Para obtener más información, consulte [Herramientas](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/tools-modules.md). |
| Analizador de texto | Utilice la herramienta Analizador de texto para analizar el texto y utilizarlo en otros módulos de escenarios. Para obtener más información, consulte [Analizador de texto](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/text-parser.md). |

#### Favoritos

![Panel de favoritos](assets/favorites-new.png)

Puede usar el icono Favoritos para añadir módulos que utilice con frecuencia.

| Acción | Detalles |
| ---------- | ---------- |
| Sus conectores favoritos | Aquí se muestran los conectores que ha marcado como favoritos. |
| Añadir icono favorito | Haga clic en este icono para seleccionar otro conector para añadirlo a la sección de favoritos. |
| Icono Desbordamiento | Si tiene más favoritos de los que caben en la barra de herramientas, se muestra un icono de desbordamiento (tres puntos) para que pueda acceder al resto. |

#### Preguntar al AI

![Botón Preguntar IA](assets/ask-ai-new.png)

Haga clic en **Preguntar a AI** para abrir el Asistente de IA de Adobe. Esta opción puede no estar disponible según la configuración de IA de su organización.

#### Navegación por lienzo

![Controles de navegación en lienzo](assets/canvas-navigation-new.png)

| Acción | Detalles |
| ---------- | ---------- |
| Acercar/alejar | Acercar o alejar la vista de lienzo. |
| Focus | Vuelva a una vista que se ajuste a todo el escenario en la pantalla. |
| Minimap | Ver una vista en miniatura de todo el escenario. El mapa mínimo muestra su ventanilla actual. Haga clic dentro de él o haga clic y arrastre para desplazarse por el lienzo. |

#### Visualización en lienzo

El nuevo lienzo también cambia el aspecto de los escenarios mientras trabaja.

| Función | Detalles |
| ---------- | ---------- |
| Tarjetas de módulo | Cada módulo es una tarjeta horizontal que muestra el icono de la aplicación, el nombre del módulo, la descripción y el ID del módulo. Los enrutadores se muestran como un mosaico de rama compacta y las directivas como tarjetas de énfasis pequeñas. |
| Vínculos | Los enlaces entre módulos son curvos y terminan en puntas de flecha que muestran la dirección. Los vínculos del controlador de error están discontinuos. |
| Estado del módulo | Los indicadores verdes, amarillos y rojos muestran el estado de cada módulo. |
| Detalle de zoom | Los detalles de la tarjeta se muestran al acercar. Cuando aleja el zoom, los módulos simplifican el acceso a los iconos para que pueda seguir viendo todo el escenario. |
| Pliegue un enrutador | En el modo de edición, puede plegar un enrutador para ocultar sus rutas. Para obtener más información, consulte [Plegar un enrutador](/help/workfront-fusion/create-scenarios/add-modules/router-module.md#fold-a-router). |
| Modo oscuro | El lienzo sigue la configuración de aspecto oscuro de las preferencias de Adobe, incluidas las tarjetas de módulo, los vínculos, los paneles, los controles y la información de estado. |
| Panel derecho | La configuración del módulo, la inspección del módulo, el navegador del módulo, Buscar y reemplazar, los fragmentos de código, [Live Trail](/help/workfront-fusion/manage-scenarios/live-trail.md) y los detalles de solicitud y respuesta se abren en el mismo panel, a la derecha del lienzo. |

## Uso del editor de escenarios en la experiencia clásica

* [Abra el editor de escenarios y agregue un módulo: (Clásico)](#open-the-scenario-editor-and-add-a-module-classic)
* [Acciones del editor de escenarios disponibles (clásico)](#available-scenario-editor-actions-classic)

### Abra el editor de escenarios y agregue un módulo: (Clásico)

1. Haga clic en **[!UICONTROL Icono de escenarios]** ![escenarios](assets/scenarios-icon.png) en el panel izquierdo.
1. Haga clic en el icono de signo de interrogación ![icono de pregunta](assets/question-mark-full-size.png) y, a continuación, busque y haga clic en la aplicación o el servicio con el que desee comenzar. Para obtener información detallada sobre la configuración de un módulo, consulte [Configurar un módulo](/help/workfront-fusion/create-scenarios/add-modules/configure-a-modules-settings.md).

### Acciones del editor de escenarios disponibles (clásico)

* [Ejecutar su escenario (clásico)](#run-your-scenario-classic)
* [Programación (clásica)](#scheduling-classic)
* [Controles (clásicos)](#controls-classic)
* [Herramientas (Classic)](#tools-classic)
* [Favoritos (clásico)](#favorites-classic)

#### Ejecutar su escenario (clásico)

![botón de escenario de ejecución](assets/run-your-scenario.png)

| Acción | Detalles |
|----------|----------|
| Realizar una ejecución de prueba del escenario | Compruebe que el escenario se ejecuta tal como espera antes de activarlo. Una vez activado, el escenario se ejecutará según su programación. Si todo no funciona según lo esperado, consulte [Agregar control de errores](/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md) para obtener información sobre cómo manejar los errores. |

#### Programación (clásica)

![panel de programación](assets/scheduling-scenario-editor.png)

| Acción | Detalles |
| ---------- | ---------- |
| Programar el escenario | De forma predeterminada, un escenario se ejecuta cada 15 minutos. Puede cambiar esto definiendo cuándo y con qué frecuencia se ejecuta un escenario activado. Los escenarios de fusión pueden programarse para que se ejecuten incluso cada 5 minutos. Para obtener más información, consulte [Programar un escenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md). |

#### Controles (clásicos)

Es posible que tenga que hacer clic en el icono de tres puntos del área Controles para ver algunos de estos controles.

![panel de controles](assets/controls-editor-scenario.png)

| Acción | Detalles |
| ---------- | ---------- |
| Guarde. <p>![Icono de guardar](assets/save-icon.png)</p> | <p>Después de guardar el escenario, dispondrá de una nueva versión en el menú de tres puntos en caso de que necesite acceder a ella en el futuro. Las versiones de escenarios guardadas anteriormente están disponibles durante 60 días después de crearse la siguiente versión de escenario. </p><p>Para conservar el historial de versiones de los escenarios más allá de los 60 días para fines de auditoría, se recomienda guardar y archivar un modelo del escenario en otra ubicación.</p> |
| Configuración de escenarios <p>![Icono de configuración de escenario](assets/scenario-settings-icon.png)</p> | El panel de configuración de escenario contiene la configuración avanzada del escenario. Para obtener más información acerca de la configuración disponible, vea [Configurar opciones de escenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md). |
| Notas  <p>![Icono de notas](assets/notes-icon.png)</p> | Tome notas sobre el escenario. Otros usuarios pueden ver estas notas cuando se encuentren en el escenario. |
| Alineación automática <p>![Icono de alineación automática](assets/auto-align-icon.png)</p> | Alinee automáticamente los módulos en su escenario. |
| Módulos de búsqueda <p>![Módulos de búsqueda](assets/search-modules-icon.png)  </p> | Introduzca un término de búsqueda para localizar un módulo y, a continuación, haga clic en los resultados de búsqueda que se llevarán a ese módulo. Puede buscar por nombre de módulo, ID, tipo o aplicación. |
| Explicar flujo  <p>![Explicar icono de flujo](assets/explain-flow-icon.png) </p> | Vea una animación en la que los puntos móviles muestran cómo fluyen los datos por el escenario. |
| DevTool <p>![Icono de DevTool](assets/devtool-icon.png)</p> | Con DevTool, puede comprobar todas las ejecuciones manuales de su escenario, revisar todas las operaciones realizadas y ver los detalles de cada llamada a la API realizada. Puede ver qué módulo, operación o respuesta única causó el error y utilizar ese conocimiento para perfeccionar el escenario. Para obtener más información, vea [Depurar un escenario](/help/workfront-fusion/manage-scenarios/debug-a-scenario.md). |
| Exportar modelo  <p>![Icono de exportar modelo](assets/export-blueprint-icon.png) </p> | Exporte un modelo del escenario actual. |
| Exportar como plantilla sin encabezado  <p>![Exportar como icono de plantilla sin encabezado](assets/export-as-headless-template-icon.png) </p> | Exporte el escenario como una plantilla sin encabezado. |
| Importar modelo  <p>![Icono Importar modelo](assets/import-blueprint-icon.png) </p> | Importe un modelo de escenario exportado anteriormente. |
| Versión anterior  <p>![Icono de la versión anterior](assets//previous-version-icon.png) </p> | Vea las versiones anteriores de este escenario. |

#### Herramientas (Classic)

![panel de herramientas](assets/tools-scenario-editor.png)

| Acción | Detalles |
| ---------- | ---------- |
| Control de flujo | Configure las opciones para controlar el modo en que los datos fluyen por él. Para obtener más información, consulte [Control de flujo](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/flow-control.md). |
| Herramientas | La sección de herramientas contiene varios módulos útiles que pueden mejorar los escenarios. Para obtener más información, consulte [Herramientas](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/tools-modules.md). |
| Analizador de texto | Utilice la herramienta Analizador de texto para analizar el texto y utilizarlo en otros módulos de escenarios. El analizador de texto no requiere una conexión. Para obtener más información, consulte [Analizador de texto](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/text-parser.md). |

#### Favoritos (clásico)

![Panel de favoritos](assets/favorites-scenario-editor.png)

Puede usar el icono Favoritos para añadir módulos que utilice con frecuencia.

