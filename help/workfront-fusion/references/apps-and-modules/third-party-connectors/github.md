---
title: Módulos GitHub
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan GitHub, así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: d9e6c26c-8770-40bc-a83a-8c05f86e4a3f
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '1959'
ht-degree: 65%

---

# Módulos de [!DNL GitHub]

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!UICONTROL GitHub], así como conectarlo a varias aplicaciones y servicios de terceros.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront</td> 
   <td> <p>Cualquier paquete de flujo de trabajo de Adobe Workfront y cualquier paquete de integración y automatización de Adobe Workfront</p><p>Workfront Ultimate</p><p>Paquetes Workfront Prime y Select, con una compra adicional de Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencias de Adobe Workfront</td> 
   <td> <p>Estándar</p><p>Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion</td> 
   <td>
   <p>Basado en operaciones: no se requiere licencia de Workfront Fusion</p>
   <p>Basado en conectores (heredado): Workfront Fusion para la automatización e integración del trabajo </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete Select o Prime Workfront que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Para usar los módulos [!DNL GitHub], debe tener una cuenta de [!DNL GitHub].

## Conexión de [!DNL GitHub] a Workfront Fusion

Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL GitHub] a [!UICONTROL Workfront Fusion], consulte [Crear una conexión a [!UICONTROL Adobe Workfront Fusion]: Instrucciones básicas](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

## Módulos [!DNL GitHub] y sus campos.

Al configurar módulos de [!DNL GitHub], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL GitHub] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Activadores](#triggers)
* [Acciones](#actions)

### Activadores

* [[!UICONTROL Ver comentarios]](#watch-comments)
* [[!UICONTROL Ver horquillas]](#watch-forks)
* [[!UICONTROL Ver problemas]](#watch-issues)
* [[!UICONTROL Ver solicitudes de cambio]](#watch-pull-requests)
* [[!UICONTROL Ver repositorios]](#watch-repositories)

#### [!UICONTROL Ver comentarios]

Este módulo de déclencheur inicia un escenario cuando se agrega un comentario nuevo o se modifica uno existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL GitHub] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Seleccione el repositorio que desea inspeccionar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Issue number]</td> 
   <td>Si desea restringir la búsqueda buscando únicamente nuevos comentarios realizados sobre un problema específico, introduzca el número de problema.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned issues]</td> 
   <td> <p> Defina el número máximo de comentarios que Workfront Fusion devolverá durante un ciclo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch]</td> 
   <td>Seleccione si desea inspeccionar solo comentarios nuevos o los comentarios y todos los cambios.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Ver horquillas]

Este módulo de déclencheur inicia un escenario cuando se crea una nueva ramificación.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL GitHub] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Seleccione el repositorio que desea inspeccionar en busca de ramificaciones.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned forks]</td> 
    <td>Introduzca o asigne el número máximo de ramificaciones que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</td>
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Ver problemas]

Este módulo de déclencheur inicia un escenario cuando se agrega un problema nuevo o se modifica uno existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL GitHub] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL I want to watch]</td> 
   <td>Seleccione si desea ver todos los repositorios asociados a esta cuenta o sólo un repositorio.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Si ha elegido ver los problemas de un solo repositorio, seleccione el repositorio que desee ver.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned issues]</td> 
   <td> <p> Establezca el número máximo de problemas que Workfront Fusion devuelve durante un ciclo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch]</td> 
   <td>Seleccione si desea inspeccionar solo problemas nuevos o problemas nuevos y todos los cambios.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td> <p>Puede filtrar los problemas que desea tener en cuenta según la forma en que esté asociados a ellos.</p> 
    <ul> 
     <li>[!UICONTROL All issues]</li> 
     <li>[!UICONTROL Only issues assigned to me]</li> 
     <li>[!UICONTROL Only issues created by me]</li> 
     <li>[!UICONTROL Only issues mentioning me]</li> 
     <li>[!UICONTROL Only issues I'm subscribed to updates for]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL State]</td> 
   <td>Seleccione si solo desea inspeccionar los problemas abiertos o solo los problemas cerrados. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Labels]</td> 
   <td>Para cada etiqueta que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca la etiqueta. El módulo observa los problemas con estas etiquetas.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Solicitudes de extracción de observación]

Este módulo se activa cuando se añade una nueva solicitud de extracción o se modifica una existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL GitHub] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Seleccione el repositorio que desea inspeccionar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned pull requests]</td> 
   <td> <p> Establezca el número máximo de solicitudes de extracción que Workfront Fusion devuelve durante un ciclo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL State]</td> 
   <td>Seleccione si desea ver solicitudes [!UICONTROL only open pull], solicitudes [!UICONTROL only closed ones] o todas las solicitudes de extracción. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch]</td> 
   <td>Seleccione si desea inspeccionar solo nuevas solicitudes de extracción, o nuevas solicitudes de extracción y todos los cambios.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Ver repositorios]

Este módulo de déclencheur inicia un escenario cuando se crea o modifica un repositorio.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL GitHub] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned repositories]</td> 
   <td> <p> Establezca el número máximo de repositorios que Workfront Fusion devuelve durante un ciclo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch]</td> 
   <td>Seleccione si desea inspeccionar nuevos repositorios y todos los cambios o solo nuevos repositorios.</td> 
  </tr> 
 </tbody> 
</table>

### Acciones

* [[!UICONTROL Añadir asignados]](#add-assignees)
* [[!UICONTROL Añadir etiquetas a un problema]](#add-labels-to-an-issue)
* [[!UICONTROL Crear un comentario]](#create-a-comment)
* [[!UICONTROL Crear un problema]](#create-an-issue)
* [[!UICONTROL Obtener un problema]](#get-an-issue)
* [[!UICONTROL Enumerar comentarios]](#list-comments)
* [[!UICONTROL Quitar una etiqueta de un problema]](#remove-a-label-from-an-issue)
* [[!UICONTROL Quitar asignados]](#remove-assignees)
* [[!UICONTROL Buscar un problema]](#search-for-an-issue)
* [[!UICONTROL Actualizar un problema]](#update-an-issue)

#### [!UICONTROL Añadir asignados]

Este módulo añade asignados al problema especificado

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL GitHub] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Seleccione el repositorio que contiene el problema al que desea añadir asignados.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assignee]</td> 
   <td>Seleccione las personas que desea asignar al problema. Entre los asignados disponibles se encuentran todos los que tienen permisos de escritura en el repositorio y los miembros de la organización con permisos de lectura en el repositorio. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>Introduzca o asigne el número de problema del problema al que desea añadir asignados. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Añadir etiquetas a un problema]

Este módulo añade etiquetas a un problema. Las etiquetas se definen en el nivel de repositorio y solo las puede crear alguien con acceso de escritura al repositorio.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL GitHub] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Seleccione el repositorio que contiene el problema al que desea añadir etiquetas.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Labels]</td> 
   <td>Seleccione las etiquetas que desea añadir al problema.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>Introduzca o asigne el número del problema al que desea añadir etiquetas.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Crear un comentario]

Este módulo crea un comentario sobre el problema especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL GitHub] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Seleccione el repositorio que contiene el problema en el que desea crear un comentario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>Introduzca o asigne el número de problemas sobre el que desea crear un comentario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td>Introduzca o asigne el contenido del comentario.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Crear un problema]

Este módulo crea un nuevo problema en el repositorio seleccionado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL GitHub] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Seleccione el repositorio en el que desea crear un problema.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assignee]</td> 
   <td>Seleccione las personas que desea asignar al problema. Entre los usuarios asignados disponibles se encuentran los que tienen permisos de escritura en el repositorio y los miembros de la organización con permisos de lectura en el repositorio. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Milestone]</td> 
   <td>Seleccione el hito que desea asociar con el nuevo problema. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Labels]</td> 
   <td>Seleccione las etiquetas que desee aplicar al nuevo problema. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Title]</td> 
   <td>Escriba o asigne un título para el nuevo problema.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td>Introduzca o asigne el cuerpo del problema como descripción o información adicional</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Obtener un problema]

Este módulo recupera detalles sobre el problema especificado

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL GitHub] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Seleccione el repositorio que contiene el problema cuyos detalles desea recuperar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>Introduzca o asigne el número de problema del problema cuyos detalles desee recuperar. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Enumerar comentarios]

Este módulo enumera todos los comentarios sobre el problema especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL GitHub] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Seleccione el repositorio que contiene el problema del que desea enumerar comentarios.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>Introduzca o asigne el número de problemas del que desea enumerar comentarios.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Since]</td> 
   <td>El módulo devolverá los comentarios creados después de esta fecha. Para obtener una lista de los formatos de fecha admitidos, vea <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos</a>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned comments]</td> 
   <td> <p> Defina el número máximo de comentarios que Workfront Fusion devolverá durante un ciclo.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Quitar una etiqueta de un problema]

Este módulo quita una sola etiqueta de un problema.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL GitHub] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Seleccione el repositorio que contiene el problema del que desea quitar una etiqueta.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Labels]</td> 
   <td>Seleccione la etiqueta que desea quitar del problema.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>Introduzca o asigne el número de problemas del que desea quitar una etiqueta.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Quitar asignados]

Este módulo quita los asignados del problema especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL GitHub] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Seleccione el repositorio que contiene el problema del que desea quitar asignados.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assignee]</td> 
   <td>Seleccione las personas que desee quitar del problema. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>Introduzca o asigne el número de problema del que desea eliminar las personas asignadas. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Buscar un problema]

Este módulo busca los problemas que coinciden con los criterios de búsqueda.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL GitHub] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned issues]</td> 
   <td> <p> Establezca el número máximo de problemas que Workfront Fusion devuelve durante un ciclo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort by]</td> 
   <td> <p>Seleccione cómo desea ordenar los resultados de la búsqueda.</p> 
    <ul> 
     <li> <p>[!UICONTROL Best match] </p> </li> 
     <li>[!UICONTROL Date created]</li> 
     <li>[!UICONTROL Date updated]</li> 
     <li>[!UICONTROL Number of comments]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort direction]</td> 
   <td> <p>Seleccione de subida o de bajada. </p> <p>Para las fechas, al seleccionar <strong>[!UICONTROL descending]</strong> se obtendrá primero la fecha más reciente. </p> <p>Para [!UICONTROL number of comments], al seleccionar <strong>[!UICONTROL descending]</strong> se obtendrá el problema con el número más alto de comentarios primero.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td>Escriba o asigne la consulta de búsqueda. Para obtener una descripción detallada de las opciones de búsqueda, consulte <a href="https://docs.github.com/es/github/searching-for-information-on-github/searching-issues-and-pull-requests">Búsqueda de problemas y solicitudes de extracción</a> en el sitio de ayuda de [!DNL GitHub].</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Actualizar un problema]

Este módulo actualiza un problema de [!DNL GitHub] existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL GitHub] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Seleccione el repositorio en el que desea actualizar un problema.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assignee]</td> 
   <td>Seleccione las personas que desea asignar al problema. Entre los asignados disponibles se encuentran todos los que tienen permisos de escritura en el repositorio y los miembros de la organización con permisos de lectura en el repositorio. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Milestone]</td> 
   <td>Seleccione el hito que desea asociar con el problema. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Labels]</td> 
   <td>Seleccione las etiquetas que desee aplicar al problema. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>Introduzca o asigne el número del problema que desee actualizar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL State]</td> 
   <td>Seleccione el estado con el que desea actualizar el problema. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Title]</td> 
   <td>Escriba o asigne un título nuevo para el problema.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td>Introduzca o asigne un nuevo cuerpo para el problema, como una descripción o información adicional</td> 
  </tr> 
 </tbody> 
</table>
