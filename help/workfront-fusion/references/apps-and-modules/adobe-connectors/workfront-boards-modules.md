---
title: Módulos de placas Adobe Workfront
description: Puede utilizar el conector de tableros de Adobe Workfront para automatizar los procesos en los tableros de Workfront y conectarlo a aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion, Workfront Integrations and Apps
exl-id: dcc5044d-8fdf-4a74-b664-e965e714ce92
source-git-commit: 1929bf897e9263ec551e93df776b96f419436715
workflow-type: tm+mt
source-wordcount: '2904'
ht-degree: 16%

---

# Módulos de placas Adobe Workfront

>[!NOTE]
>
>El conector Board Fusion está en estado beta. Como resultado, la compatibilidad con este conector es limitada y puede cambiar debido al desarrollo futuro de los paneles. Además, puede haber cambios en la API de GraphQL sin previo aviso que podrían afectar al proceso del conector Fusion.

Los tableros de Adobe Workfront son herramientas flexibles que permiten la colaboración en equipo al proporcionar acceso a un tablero compartido que contiene columnas y tarjetas.

Puede utilizar los módulos de Tableros de Adobe Workfront para leer o actualizar registros, realizar una llamada de API a la API de Tableros de Workfront o almacenar en déclencheur un escenario cuando se produzca una acción en un tablero.

<!--For general information on Workfront Boards, see [Boards overview](/help/quicksilver/agile/boards-overview.md).-->

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
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete Select o Prime Workfront que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++## Requisitos previos

Debe tener configurado un tablero en Adobe Workfront para poder conectarse a él.

## Información de API de Adobe Workfront Boards

El conector de los paneles de Adobe Workfront utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.23.6</td> 
  </tr>
 </tbody> 
 </table>

## Creación de una conexión a los paneles de Workfront

>[!NOTE]
>
>Puede utilizar una conexión de Workfront para conectarse a los tableros de Workfront o puede crear una conexión de tableros de Workfront independiente.

Para crear una conexión de Workfront Boards:

1. En cualquier módulo de [!DNL Adobe Workfront Boards], haga clic en **[!UICONTROL Añadir]** junto al cuadro Conexión.

1. Rellene los campos siguientes:

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
          <td role="rowheader">[!UICONTROL Connection name]</td>
          <td>
            <p>Introduzca un nombre para esta conexión.</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Environment]</td>
          <td>Seleccione si desea conectarse a un entorno de producción o de no producción.</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Type]</td>
          <td>Seleccione si le importa conectarse a una cuenta de servicio o a una cuenta personal.</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client ID]<p>(Opcional)</p></td>
          <td>Introduzca su [!UICONTROL Client ID] [!DNL Adobe]. Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]<p>(Opcional)</p></td>
          <td>Introduzca su [!DNL Adobe] [!UICONTROL Client Secret].  Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Authentication URL]<p>(Opcional)</p></td>
          <td>Introduzca la dirección URL que utilizará su instancia de Workfront para autenticar esta conexión. <p>El valor predeterminado es <code>https://oauth.my.workfront.com/integrations/oauth2</code>.</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Host prefix]</td>
          <td>Introduzca el prefijo de host.<p>El valor predeterminado es <code>origin-</code>.</p>
        </tr>
      </tbody>
    </table>
1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.

## Módulos de tableros de Adobe Workfront y sus campos

Al configurar los módulos de Workfront Boards, Workfront Fusion muestra los campos que se indican a continuación. Junto con estos, pueden mostrarse campos adicionales de Tableros de Workfront, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Tarjetas](#cards)
* [Tableros](#boards)
* [Columnas](#columns)
* [Etiquetas](#tags)
* [Comentarios](#comments)
* [Otro](#other)

### Tarjetas

* [Añadir elemento de lista de comprobación](#add-checklist-item)
* [Agregar subtarea](#add-subtask)
* [Crear una tarjeta](#create-a-card)
* [Mover una tarjeta](#move-a-card)
* [Leer una tarjeta](#read-a-card)
* [Actualizar una tarjeta](#update-a-card)

#### Añadir elemento de lista de comprobación

Este módulo de acción agrega un elemento de lista de comprobación a la tarjeta especificada.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Puede utilizar una conexión existente de Workfront para conectarse a los tableros de Workfront o puede utilizar una conexión específica de los tableros de Workfront. </p><p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Crear una conexión a los tableros de Workfront</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>Introduzca o asigne el ID de la tarjeta a la que desea agregar un elemento de lista de comprobación.<p>Puede encontrar el ID de la tarjeta en la dirección URL cuando la visualice en Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Elementos de lista de comprobación]</td> 
   <td>Para cada elemento de la lista de comprobación que desee agregar, haga clic en Agregar elemento, escriba el nombre del elemento de la lista de comprobación y seleccione si el elemento se ha completado.</p></td> 
  </tr> 
 </tbody> 
</table>

#### Agregar subtarea

Este módulo de acción agrega una subtarea a una tarjeta en los paneles. La tarjeta debe ser una tarjeta conectada. La subtarea también se agrega a la tarea de Workfront que representa la tarjeta.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Puede utilizar una conexión existente de Workfront para conectarse a los tableros de Workfront o puede utilizar una conexión específica de los tableros de Workfront. </p><p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Crear una conexión a los tableros de Workfront</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Id. de tarjeta principal]</td> 
   <td>Introduzca o asigne el ID de la tarjeta a la que desea agregar una subtarea.<p>Puede encontrar el ID de la tarjeta en la dirección URL cuando la visualice en Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>Introduzca o asigne el ID del tablero que contiene la tarjeta a la que desea agregar una subtarea.<p>Puede encontrar el ID del tablero en la URL cuando visualice el tablero en Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Name]</td> 
   <td>Escriba o asigne un nombre para la nueva subtarea.</p></td> 
  </tr> 
 </tbody> 
</table>

#### Crear una tarjeta

Este módulo de acción crea una nueva tarjeta en un tablero de Workfront.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Puede utilizar una conexión existente de Workfront para conectarse a los tableros de Workfront o puede utilizar una conexión específica de los tableros de Workfront. </p><p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Crear una conexión a los tableros de Workfront</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>Introduzca o asigne el ID del tablero al que desea agregar una tarjeta.<p>Puede encontrar el ID del tablero en la URL cuando visualice el tablero en Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Id. de columna]</td> 
   <td>Introduzca o asigne el ID de la columna a la que desea agregar una subtarea.<p>Puede encontrar el ID de columna en la información que devuelve el módulo Leer un tablero.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Name]</td> 
   <td>Escriba o asigne un nombre para la nueva tarjeta.</p></td> 
  </tr> 
 </tbody> 
</table>

#### Mover una tarjeta

Este módulo de acción mueve una tarjeta a una columna diferente en el mismo tablero.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Puede utilizar una conexión existente de Workfront para conectarse a los tableros de Workfront o puede utilizar una conexión específica de los tableros de Workfront. </p><p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Crear una conexión a los tableros de Workfront</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>Introduzca o asigne el ID de la tarjeta que desea mover.<p>Puede encontrar el ID de la tarjeta en la dirección URL cuando la visualice en Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>Introduzca o asigne el ID del tablero que contiene la tarjeta que desea mover.<p>Puede encontrar el ID del tablero en la URL cuando visualice el tablero en Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL ID de columna de destino]</td> 
   <td>Introduzca o asigne el ID de la columna a la que desea mover la tarjeta.<p>Puede encontrar el ID de columna en la información que devuelve el módulo Leer un tablero.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL To index]</td> 
   <td>Introduzca o asigne la posición que desea que tenga la tarjeta en la nueva columna.<p>Posición superior de la columna en el índice 0.</p></td> 
  </tr> 
 </tbody> 
</table>

#### Leer una tarjeta

Este módulo de acción recupera información sobre una tarjeta específica.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Puede utilizar una conexión existente de Workfront para conectarse a los tableros de Workfront o puede utilizar una conexión específica de los tableros de Workfront. </p><p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Crear una conexión a los tableros de Workfront</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>Introduzca o asigne el ID de la tarjeta que desea leer.<p>Puede encontrar el ID de la tarjeta en la dirección URL cuando la visualice en Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>Introduzca o asigne el ID del tablero que contiene la tarjeta que desea leer.<p>Puede encontrar el ID del tablero en la URL cuando visualice el tablero en Workfront.</p></td> 
  </tr> 
 </tbody> 
</table>

#### Actualizar una tarjeta

Este módulo de acción actualiza la información de una tarjeta especificada.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Puede utilizar una conexión existente de Workfront para conectarse a los tableros de Workfront o puede utilizar una conexión específica de los tableros de Workfront. </p><p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Crear una conexión a los tableros de Workfront</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>Introduzca o asigne el ID de la tarjeta que desea actualizar.<p>Puede encontrar el ID de la tarjeta en la dirección URL cuando la visualice en Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>Introduzca o asigne el ID del tablero que contiene la tarjeta que desea actualizar.<p>Puede encontrar el ID del tablero en la URL cuando visualice el tablero en Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Name]</td> 
   <td>Escriba o asigne un nombre nuevo para la tarjeta.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Description]</td> 
   <td>Escriba o asigne una nueva descripción para la tarjeta.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Estimation]</td> 
   <td>Escriba o asigne una estimación del tiempo necesario para completar esta tarjeta.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Due date]</td> 
   <td>Escriba o asigne la fecha límite de esta tarjeta.</p>
   <p>Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos</a>.</p>
   </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Status]</td> 
   <td>Seleccione un nuevo estado para la tarjeta.</p></td> 
  </tr> 
 </tbody> 
</table>

### Tableros

* [Crear un tablero](#create-a-board)
* [Leer un tablero](#read-a-board)

#### Crear un tablero

Este módulo de acción crea un tablero en Workfront. Puede especificar el tipo de tablero que desea crear.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Puede utilizar una conexión existente de Workfront para conectarse a los tableros de Workfront o puede utilizar una conexión específica de los tableros de Workfront. </p><p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Crear una conexión a los tableros de Workfront</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Nombre de tablero]</td> 
   <td>Introduzca o asigne un nombre para el nuevo tablero.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Template]</td> 
   <td>Seleccione la plantilla para el tipo de tablero que desea crear.</td> 
  </tr> 
 </tbody> 
</table>

#### Leer un tablero

Este módulo de acción devuelve información sobre un único tablero, como las tarjetas, columnas, etiquetas y miembros del tablero.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Puede utilizar una conexión existente de Workfront para conectarse a los tableros de Workfront o puede utilizar una conexión específica de los tableros de Workfront. </p><p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Crear una conexión a los tableros de Workfront</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>Introduzca o asigne el ID del tablero para el que desea recuperar información.<p>Puede encontrar el ID del tablero en la URL cuando visualice el tablero en Workfront.</p></td> 
  </tr> 
 </tbody> 
</table>

### Columnas

* [Creación de una columna](#create-a-column)
* [Buscar una columna](#search-for-a-column)
* [Actualizar una columna](#update-a-column)

#### Creación de una columna

Este módulo de acción crea una nueva columna en el tablero especificado.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Puede utilizar una conexión existente de Workfront para conectarse a los tableros de Workfront o puede utilizar una conexión específica de los tableros de Workfront. </p><p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Crear una conexión a los tableros de Workfront</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>Introduzca o asigne el ID del tablero al que desea agregar una columna.<p>Puede encontrar el ID del tablero en la URL cuando visualice el tablero en Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Id. de columna]</td> 
   <td>Introduzca o asigne el ID de la columna que desea actualizar.<p>Puede encontrar el ID de columna en la información que devuelve el módulo Leer un tablero.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Nombre de columna]</td> 
   <td>Introduzca o asigne un nombre nuevo para la columna.</td> 
  </tr> 
 </tbody> 
</table>

#### Buscar una columna

Este módulo de búsqueda devuelve información sobre la columna con el nombre especificado.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Puede utilizar una conexión existente de Workfront para conectarse a los tableros de Workfront o puede utilizar una conexión específica de los tableros de Workfront. </p><p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Crear una conexión a los tableros de Workfront</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>Introduzca o asigne el ID del tablero que contiene la columna que desea recuperar.<p>Puede encontrar el ID del tablero en la URL cuando visualice el tablero en Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Nombre de columna]</td> 
   <td>Introduzca o asigne el nombre de la columna que desea recuperar.</td> 
  </tr> 
 </tbody> 
</table>

#### Actualizar una columna

Este módulo de acción actualiza el nombre o el límite de trabajo en curso de la columna especificada.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Puede utilizar una conexión existente de Workfront para conectarse a los tableros de Workfront o puede utilizar una conexión específica de los tableros de Workfront. </p><p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Crear una conexión a los tableros de Workfront</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>Introduzca o asigne el ID del tablero que contiene la columna que desea recuperar.<p>Puede encontrar el ID del tablero en la URL cuando visualice el tablero en Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Nombre de columna]</td> 
   <td>Introduzca o asigne el nombre de la columna que desea recuperar.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Límite WIP]</td> 
   <td>Introduzca o asigne un nuevo límite de WIP para la columna.</td> 
  </tr> 
 </tbody> 
</table>

### Etiquetas

* [Añadir una etiqueta a una tarjeta](#add-a-tag-to-a-card)
* [Crear una etiqueta](#create-a-tag)

#### Añadir una etiqueta a una tarjeta

Este módulo de acción agrega una etiqueta a una tarjeta.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Puede utilizar una conexión existente de Workfront para conectarse a los tableros de Workfront o puede utilizar una conexión específica de los tableros de Workfront. </p><p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Crear una conexión a los tableros de Workfront</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>Introduzca o asigne el ID de la tarjeta a la que desee agregar una etiqueta.<p>Puede encontrar el ID de la tarjeta en la dirección URL cuando la visualice en Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>Introduzca o asigne el ID del tablero que contiene la tarjeta a la que desea agregar una etiqueta.<p>Puede encontrar el ID del tablero en la URL cuando visualice el tablero en Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Tag ID]</td> 
   <td>Introduzca o asigne el ID de la etiqueta que desee añadir.<p>Puede encontrar el ID de la etiqueta en la información que devuelve el módulo Leer un tablero.</p></td> 
  </tr> 
 </tbody> 
</table>

#### Crear una etiqueta

Este módulo de acción crea una etiqueta nueva y le asigna un color.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Puede utilizar una conexión existente de Workfront para conectarse a los tableros de Workfront o puede utilizar una conexión específica de los tableros de Workfront. </p><p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Crear una conexión a los tableros de Workfront</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>Introduzca o asigne el ID del tablero para el que desea crear una etiqueta.<p>Puede encontrar el ID del tablero en la URL cuando visualice el tablero en Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Nombre de etiqueta]</td> 
   <td>Introduzca o asigne un nombre para la nueva etiqueta.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Color de etiqueta]</td> 
   <td>Seleccione el color de esta etiqueta.</td> 
  </tr> 
 </tbody> 
</table>

### Comentarios

* [Crear un comentario](#create-a-comment)
* [Leer comentarios de tarjeta](#read-card-comments)

#### Crear un comentario

Este módulo de acción creó un comentario en la tarjeta especificada.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Puede utilizar una conexión existente de Workfront para conectarse a los tableros de Workfront o puede utilizar una conexión específica de los tableros de Workfront. </p><p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Crear una conexión a los tableros de Workfront</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>Introduzca o asigne el ID de la tarjeta a la que desea agregar un comentario.<p>Puede encontrar el ID de la tarjeta en la dirección URL cuando la visualice en Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Comment]</td> 
   <td>Escriba o asigne el texto del comentario que desea agregar.</p></td> 
  </tr> 
 </tbody> 
</table>

#### Leer comentarios de tarjeta

Este módulo de acción recupera los comentarios de la tarjeta especificada.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Puede utilizar una conexión existente de Workfront para conectarse a los tableros de Workfront o puede utilizar una conexión específica de los tableros de Workfront. </p><p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Crear una conexión a los tableros de Workfront</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>Introduzca o asigne el ID de la tarjeta para la que desea recuperar los comentarios.<p>Puede encontrar el ID de la tarjeta en la dirección URL cuando la visualice en Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td>Introduzca el número máximo de comentarios que desea que devuelva el módulo en un ciclo de ejecución.</p></td> 
  </tr> 
 </tbody> 
</table>

### Otro

#### Realizar una llamada de API personalizada

Este módulo de acción realiza una llamada personalizada a la API de Workfront Boards.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
      <td> <p>Puede utilizar una conexión existente de Workfront para conectarse a los tableros de Workfront o puede utilizar una conexión específica de los tableros de Workfront. </p><p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Crear una conexión a los tableros de Workfront</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td> <p>Introduzca una ruta relativa a <code> https://&lt;WORKFRONT_DOMAIN&gt;/boards-service/graphql?</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p><p>Para la mayoría de las llamadas de tableros, el método es POST. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar. Determina el tipo de contenido de la petición.</p> <p>Por ejemplo:<code> { "Content-type":"application/json-stringify()"}</code></p>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Añada la consulta para la llamada de API en forma de objeto JSON estándar.</p> <p>En los paneles de Workfront, esta sección suele dejarse vacía.</p>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de Graphql incrustado de JSON </p> <p>Ejemplo:</p><p>En este ejemplo se actualiza un nombre de columna. Puede incluir <code>boardId</code> y <code>columnId</code> como GUID codificados o asignados desde un módulo anterior.<p><pre>{<br> "query": "mutation { updateColumn(boardId: \"\", columnId: \"\", updateColumnInput: { name: \"\" }) { id name }}"<br>}</pre><p>Nota:  <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>


#### Realizar una llamada de API de GraphQL personalizada

Este módulo de acción realiza una solicitud personalizada de GraphQL a la API de Workfront Boards.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
      <td> <p>Puede utilizar una conexión existente de Workfront para conectarse a los tableros de Workfront o puede utilizar una conexión específica de los tableros de Workfront. </p><p>Para obtener instrucciones sobre cómo conectar la aplicación de Workfront a Workfront Fusion, consulte <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Crear una conexión a los tableros de Workfront</a> en este artículo.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método para esta llamada. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td> <p>Añada la consulta para la llamada de API en forma de objeto JSON estándar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Nombre de operación]</td> 
   <td> <p>Introduzca un nombre para esta operación. Esto puede facilitar el seguimiento y la depuración de la llamada.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Origen de datos de variables]</td> 
   <td> <p>Seleccione si las variables procederán de un formulario o de una colección.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Variables]</td> 
   <td> <p>Para cada variable que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca la clave y el valor de la variable.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td> 
   </tr> 
 </tbody> 
</table>
