---
title: Módulos de Workfront Fusion
description: Con el conector de Workfront Fusion, puede administrar su propia organización de Fusion desde un escenario, incluidos registros, enlaces, escenarios y conexiones.
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 7606f1b15aac0f2baef1b4ef16e3bcaa39dad27c
workflow-type: tm+mt
source-wordcount: 1430
ht-degree: 24%

---

# Módulos de Workfront Fusion

Con el conector de Workfront Fusion, puede administrar su propia organización de Fusion desde un escenario concreto. A diferencia de otros conectores, que conectan Fusion a una aplicación o servicio de terceros, este conector permite que un escenario llame a la propia API de Fusion, de forma similar a como el conector de Adobe Workfront permite que un escenario administre Workfront.

Para obtener instrucciones sobre cómo crear un escenario, consulte los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, consulte los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

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

## Conexión de Workfront Fusion a Workfront Fusion

1. En cualquier módulo de Workfront Fusion, haga clic en **[!UICONTROL Agregar]** junto al campo Conexión.
1. Rellene los campos siguientes:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Connection type]</td> 
      <td>Seleccione el tipo de conexión que desea crear.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Connection name]</td> 
      <td>Introduzca un nombre para la conexión.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Client ID]</td> 
      <td>Introduzca su [!UICONTROL Client ID] [!DNL Adobe]. Esto se puede encontrar en la sección de detalles de [!UICONTROL Credentials] de [!DNL Adobe Developer Console].</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Client Secret]</td> 
      <td>Introduzca su [!DNL Adobe] [!UICONTROL Client Secret]. Esto se puede encontrar en la sección de detalles de [!UICONTROL Credentials] de [!DNL Adobe Developer Console].</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Organization ID]</td> 
      <td>Escriba su ID de organización de IMS [!DNL Adobe].</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Region]</td> 
      <td>Seleccione la región Fusión para esta conexión.</td> 
     </tr> 
    </tbody> 
   </table>

1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.

## Módulos de Workfront Fusion y sus campos

Al configurar los módulos de Workfront Fusion, Workfront Fusion muestra los campos que se indican a continuación. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, consulte [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Acciones](#actions)
* [Exportar](#export)
* [Varios](#misc)

### Acciones

* [Clonar un registro](#clone-a-record)
* [Crear un registro](#create-a-record)
* [Eliminación de un registro](#delete-a-record)
* [Enumerar registros](#list-records)
* [Leer un registro](#read-a-record)
* [Actualizar un registro](#update-a-record)

#### Clonar un registro

Este módulo realiza una copia del registro especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar Workfront Fusion a Workfront Fusion, consulte <a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Conectar Workfront Fusion a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de registro</td> 
   <td> Seleccione el tipo de registro que desea clonar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de escenario</td> 
   <td> Introduzca o asigne el ID del escenario que desea clonar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre</td> 
   <td> Introduzca o asigne un nombre para el nuevo escenario.</td> 
  </tr> 
 </tbody> 
</table>

#### Crear un registro

Este módulo crea un registro con los datos especificados.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar Workfront Fusion a Workfront Fusion, consulte <a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Conectar Workfront Fusion a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de registro</td> 
   <td> Seleccione el tipo de registro que desea crear. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de equipo</td> 
   <td> Introduzca o asigne el ID del equipo propietario de este registro. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre</td> 
   <td> Introduzca o asigne un nombre para el nuevo registro.</td> 
  </tr> 
 </tbody> 
</table>

#### Eliminación de un registro

Este módulo elimina un registro especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar Workfront Fusion a Workfront Fusion, consulte <a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Conectar Workfront Fusion a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de registro</td> 
   <td> Seleccione el tipo de registro que desea eliminar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Otros campos</td> 
   <td>Introduzca valores para cualquier otro campo. Los campos disponibles dependen del tipo de registro seleccionado. </td> 
  </tr> 
 </tbody> 
</table>

#### Enumerar registros

Este módulo devuelve una lista paginada de registros utilizando la paginación basada en cursor y filtros de propiedad.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar Workfront Fusion a Workfront Fusion, consulte <a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Conectar Workfront Fusion a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de registro</td> 
   <td>Seleccione el tipo de registro del que desea obtener una lista.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Propiedad</td> 
   <td>Para cada filtro de propiedad para el que desee devolver resultados, haga clic en <b>Agregar elemento</b> e introduzca el campo, el operador y el valor que desee filtrar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Start</td> 
   <td>Introduzca la ubicación donde desea iniciar los resultados devueltos. Se utiliza para la paginación.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Número máximo de resultados devueltos</td> 
   <td>Introduzca o asigne el número máximo de registros que desea que devuelva el módulo para cada ciclo de ejecución.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Ordenar por</td> 
   <td>Seleccione el campo por el que desea ordenar los resultados.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Dirección</td> 
   <td>Seleccione si desea ordenar los resultados en orden ascendente o descendente.</td> 
  </tr> 
 </tbody> 
</table>

#### Leer un registro

Este módulo recupera el registro especificado

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar Workfront Fusion a Workfront Fusion, consulte <a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Conectar Workfront Fusion a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de registro</td> 
   <td> Seleccione el tipo de registro que desea eliminar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Otros campos</td> 
   <td>Introduzca valores para cualquier otro campo. Los campos disponibles dependen del tipo de registro seleccionado. </td> 
  </tr> 
 </tbody> 
</table>

#### Actualizar un registro

Actualiza un registro especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar Workfront Fusion a Workfront Fusion, consulte <a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Conectar Workfront Fusion a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de registro</td> 
   <td> Seleccione el tipo de registro que desee actualizar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre</td> 
   <td> Introduzca o asigne un nombre nuevo para el registro.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID</td> 
   <td> Introduzca o asigne el ID del registro que desea actualizar. </td> 
  </tr> 
 </tbody> 
</table>

### Exportar

* [Exportar registros de actividad](#export-activity-logs)
* [Exportar escenarios](#export-scenarios)

#### Exportar registros de actividad

Este módulo exporta los registros de actividad.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar Workfront Fusion a Workfront Fusion, consulte <a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Conectar Workfront Fusion a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de archivo</td> 
   <td>Seleccione el formato de archivo en el que desea exportar los registros.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Propiedad</td> 
   <td>Para cada filtro de propiedad para el que desee devolver resultados, haga clic en <b>Agregar elemento</b> e introduzca el campo, el operador y el valor que desee filtrar. También puede filtrar por si el campo existe o no.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Start</td> 
   <td>Introduzca la ubicación donde desea iniciar los resultados devueltos. Se utiliza para la paginación.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Número máximo de resultados devueltos</td> 
   <td>Introduzca o asigne el número máximo de registros que desea que devuelva el módulo para cada ciclo de ejecución.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Ordenar por</td> 
   <td>Seleccione el campo por el que desea ordenar los resultados.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Dirección</td> 
   <td>Seleccione si desea ordenar los resultados en orden ascendente o descendente.</td> 
  </tr> 
 </tbody> 
</table>

#### Exportar escenarios

Este módulo exporta los modelos de Fusion para uno o más escenarios.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar Workfront Fusion a Workfront Fusion, consulte <a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Conectar Workfront Fusion a Workfront Fusion</a> en este artículo.</p> </td> 
  <tr> 
   <td role="rowheader">ID de escenario</td> 
   <td>Para cada escenario que desee exportar, haga clic en <b>Agregar elemento</b> e introduzca el identificador de escenario.</td> 
  </tr> 
  </tr> 
 </tbody> 
</table>

### Varios

* [Obtener estadísticas de cola de un vínculo](#get-queue-statistics-for-a-hook)
* [Obtener dependencias de registro](#get-record-dependencies)
* [Enumerar escenarios para una conexión](#list-scenarios-for-a-connection)
* [Enumeración de las regiones y organizaciones de Fusion](#list-the-fusion-regions-and-organizations)

#### Obtener estadísticas de cola de un vínculo

Este módulo devuelve las estadísticas de cola del vínculo especificado: el número de eventos en cola actualmente, el límite de cola y si el vínculo está habilitado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar Workfront Fusion a Workfront Fusion, consulte <a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Conectar Workfront Fusion a Workfront Fusion</a> en este artículo.</p> </td> 
  <tr> 
   <td role="rowheader">ID de enlace</td> 
   <td> Introduzca o asigne el ID del vínculo para el que desea obtener detalles.</td> 
  </tr> 
 </tbody> 
</table>

#### Obtener dependencias de registro

Este módulo obtiene las dependencias del registro.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar Workfront Fusion a Workfront Fusion, consulte <a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Conectar Workfront Fusion a Workfront Fusion</a> en este artículo.</p> </td> 
  <tr> 
   <td role="rowheader">Tipo de registro</td> 
   <td> Seleccione el tipo de registro para el que desea recuperar las dependencias. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de escenario</td> 
   <td> Introduzca o asigne el ID del registro para el que desea recuperar las dependencias. </td> 
  </tr> 
  </tr> 
 </tbody> 
</table>

#### Enumerar escenarios para una conexión

Este módulo devuelve una lista paginada de escenarios que hacen referencia a la conexión dada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar Workfront Fusion a Workfront Fusion, consulte <a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Conectar Workfront Fusion a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de conexión</td> 
   <td>Introduzca o asigne el ID de la conexión para la que desea devolver escenarios.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Propiedad</td> 
   <td>Para cada filtro de propiedad para el que desee devolver resultados, haga clic en <b>Agregar elemento</b> e introduzca el campo, el operador y el valor que desee filtrar. También puede filtrar por si el campo existe o no.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Start</td> 
   <td>Introduzca la ubicación donde desea iniciar los resultados devueltos. Se utiliza para la paginación.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Número máximo de resultados devueltos</td> 
   <td>Introduzca o asigne el número máximo de registros que desea que devuelva el módulo para cada ciclo de ejecución.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Ordenar por</td> 
   <td>Seleccione el campo por el que desea ordenar los resultados.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Dirección</td> 
   <td>Seleccione si desea ordenar los resultados en orden ascendente o descendente.</td> 
  </tr> 
 </tbody> 
</table>

#### Enumeración de las regiones y organizaciones de Fusion

Este módulo devuelve el ID de región y organización de cada organización de Fusion a la que puede acceder la conexión, en función de las credenciales y el acceso en el perfil de usuario de IMS de las credenciales utilizadas en la conexión.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar Workfront Fusion a Workfront Fusion, consulte <a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Conectar Workfront Fusion a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
 </tbody> 
</table>





