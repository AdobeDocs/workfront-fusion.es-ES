---
title: Módulos de HubSpot CRM
description: Los módulos de HubSpot CRM de  [!DNL Adobe Workfront Fusion]  le permiten supervisar eventos, registros, contactos, participaciones, envíos de archivos y formularios, o crear, recuperar, actualizar y eliminar registros, contactos, participaciones, eventos o archivos de su cuenta de  [!DNL HubSpot CRM] .
author: Becky
feature: Workfront Fusion
exl-id: b8a1bbcd-337e-4c92-a1a6-d6d4bab1f440
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '5655'
ht-degree: 33%

---

# Módulos de [!DNL HubSpot CRM]

Los módulos de [!DNL Adobe Workfront Fusion] [!DNL HubSpot CRM] le permiten supervisar eventos, registros, contactos, participaciones, envíos de archivos y formularios, o crear, recuperar, actualizar y eliminar registros, contactos, participaciones, eventos o archivos en su cuenta de [!DNL HubSpot CRM].

## Requisitos de acceso

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] plan*</td>
  <td> <p>[!UICONTROL Pro] o superior</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licencia*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licencia**</td> 
   <td>
   <p>Requisito de licencia actual: no se requiere ninguna licencia de [!DNL Workfront Fusion].</p>
   <p>O</p>
   <p>Requisito de licencia heredado: [!UICONTROL [!DNL Workfront Fusion] para automatización e integración de trabajo </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Requisito de producto actual: si tiene el plan [!UICONTROL Select] o [!UICONTROL Prime] [!DNL Adobe Workfront], su organización debe adquirir [!DNL Adobe Workfront Fusion] así como [!DNL Adobe Workfront] para utilizar la funcionalidad descrita en este artículo. [!DNL Workfront Fusion] está incluido en el plan [!UICONTROL Ultimate] [!DNL Workfront].</p>
   <p>O</p>
   <p>Requisito de productos heredados: su organización debe comprar [!DNL Adobe Workfront Fusion] y [!DNL Adobe Workfront] para utilizar la funcionalidad descrita en este artículo.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Para saber qué plan, tipo de licencia o acceso tiene, póngase en contacto con el administrador de [!DNL Workfront].

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## Requisitos previos

Para usar módulos [!DNL HubSpot CRM], debe tener una cuenta de [!DNL HubSpot CRM].

## Información de API de CRM de HubSpot

El conector CRM de HubSpot utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL básica</td> 
   <td>https://api.hubapi.com</td> 
  </tr>
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 2.0.14</td> 
  </tr>
 </tbody> 
 </table>

## Conectar [!DNL Adobe Workfront Fusion] a [!DNL HubSpot CRM]

Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], consulte [Crear una conexión a  [!DNL Adobe Workfront Fusion] : instrucciones básicas](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

>[!NOTE]
>
>Al configurar una conexión, seleccione el tipo de conexión **HubSpot CRM**. El tipo HubSpot CRM (obsoleto) admite conexiones existentes, pero no recomendamos utilizarlo para crear nuevas conexiones.

## Módulos de [!DNL HubSpot CRM] y sus campos

Al configurar módulos de [!DNL Hubspot CRM], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Hubspot CRM] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Objetos de CRM](#crm-objects)
* [Registros (acuerdos, contactos y compañías)](#records-deals-contacts-and-companies)
* [Contactos](#contacts)
* [Acuerdos](#deals)
* [Compañías](#companies)
* [Participaciones](#engagements)
* [Eventos y notificaciones](#events-and-notifications)
* [Archivos](#files)
* [Tareas](#tasks)
* [Usuarios](#users)
* [Entradas](#tickets)
* [Formularios](#forms)
* [Medios sociales (difusión)](#social-media-broadcast)
* [Publicaciones de blog](#blog-posts)
  <!--* [Workflows]-->
* [Suscripciones](#subscriptions)
  <!--* [Associations](#associations)-->
* [Otro](#other)

+++**objetos CRM**

### Objetos de CRM

* [Buscar objetos CRM](#search-for-crm-objects)
* [Observar objetos CRM](#watch-crm-objects)

#### [!UICONTROL Search for CRM Objects]

Este módulo de búsqueda busca objetos de CRM por propiedades personalizadas o por consulta. Para buscar productos o elementos de línea, utilice una conexión especial con un ámbito personalizado requerido.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Introduzca o asigne el número máximo de elementos que devolverá el módulo en un ciclo de ejecución.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object Type to Search]</td> 
   <td>Seleccione el tipo de objeto de Hubspot CRM que desea buscar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output properties]</td> 
   <td>Seleccione las propiedades que desea que aparezcan en la salida del módulo. Los campos disponibles dependen del objeto que ha seleccionado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter by] </td> 
   <td> <p>Seleccione cómo desea filtrar la búsqueda</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Query]</strong> </p> <p>Introduzca o asigne la consulta</p> </li> 
     <li> <p><strong>[!UICONTROL Properties]</strong> </p> <p>Introduzca los grupos o filtros para la búsqueda.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort by]</td> 
   <td> <p>Haga clic si desea ordenar los resultados. Si decide ordenar los resultados, aparecen los siguientes campos. </p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Property name]</strong> </p> <p>Seleccione la propiedad por la que desea ordenar los resultados</p> </li> 
     <li> <p><strong>[!UICONTROL Direction]</strong> </p> <p>Elija si desea ordenar los resultados en dirección ascendente o descendente.</p> </li> 
    </ul> </td> 
  </tr> 
   <tr> 
    <td role="rowheader">Desplazamiento de inicio</td> 
    <td>Introduzca o asigne el ID del primer elemento para el que desea recuperar detalles. Este módulo solo devuelve hasta 5000 resultados a la vez. La configuración de un desplazamiento inicial permite recuperar elementos que no sean los primeros 5000. Si la desviación de inicio es 5000, el módulo devolverá los elementos 5000-9999.</td> 
   </tr>
 </tbody> 
</table>

#### Observar objetos CRM

Este módulo de déclencheur inicia un escenario cuando se crea o actualiza un objeto CRM.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Introduzca o asigne el número máximo de elementos que devolverá el módulo en un ciclo de ejecución.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object type to search]</td> 
   <td> <p>Seleccione el tipo de objeto que desea buscar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Properties]</td> 
   <td>Seleccione las propiedades que desee incluir en la salida para este módulo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Created/Updated]</td> 
   <td>Seleccione si desea inspeccionar los objetos creados (nuevos) o actualizados (modificados).</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter by]</td> 
   <td>Puede añadir un filtro para asegurarse de que el escenario se inicia solo cuando se cumplen determinadas condiciones.<ul><li><b>Consulta</b><p>Introduzca la consulta por la que desea filtrar.</li><li><b>Propiedades</b><p>Para cada propiedad que desee usar con el fin de filtrar los resultados, haga clic en <b>Agregar elemento</b> e introduzca el nombre de propiedad, el operador y el valor de propiedad.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++**Registros (ofertas, contactos y compañías)**

### Registros (acuerdos, contactos y compañías)

* [Crear un registro](#create-a-record)
* [[!UICONTROL Create a Record (Legacy)]](#create-a-record-legacy)
* [[!UICONTROL Delete a Record]](#delete-a-record)
* [[!UICONTROL Get a Record]](#get-a-record)
* [[!UICONTROL Get a Record Property]](#get-a-record-property)
* [Enumerar registros](#list-records)
* [[!UICONTROL Update a Record]](#update-a-record)
* [[!UICONTROL Watch Records]](#watch-records)

#### Crear un registro

Este módulo de acción crea un contacto, una compañía o una oferta.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro que desea crear.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Property groups]</td> 
   <td>Para cada propiedad que desee agregar al crear el registro, seleccione el grupo donde se encuentra la propiedad. Se abrirá el grupo de propiedades, donde podrá rellenar el valor de las propiedades. Los grupos de propiedades y las propiedades disponibles dependen del tipo de registro que desee crear.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Record (Legacy)]

Este módulo de acción crea un contacto, una compañía o un acuerdo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro que desea crear.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Properties]</td> 
   <td>Rellene las propiedades que desee establecer para el registro. Los campos disponibles dependen del tipo de registro que desee crear.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Record]

Este módulo de acción elimina un contacto, una compañía o un acuerdo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td>Seleccione el tipo de registro que desea eliminar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Introduzca el ID del contacto, la compañía o el acuerdo que desea eliminar. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Record]

Este módulo de acción obtiene detalles de un contacto, una compañía o un acuerdo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Seleccione el tipo de registro.</p> 
    <ul> 
     <li>[!UICONTROL Contact]</li> 
     <li>[!UICONTROL Company] </li> 
     <li>[!UICONTROL Deal]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search Type]</td> 
   <td>Si va a recibir un contacto, seleccione si desea identificarlo por el ID o por la dirección de correo electrónico.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Introduzca el ID del contacto, compañía o acuerdo que desea recuperar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Email]</td> 
   <td>Introduzca la dirección de correo electrónico del contacto cuyos detalles desea recuperar. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Record Property]

Este módulo de acción obtiene metadatos para una propiedad de registro específica por su nombre (interno).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td>Seleccione el tipo de registro que tiene la propiedad para la que desea recuperar metadatos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Property Name]</td> 
   <td>Seleccione la propiedad para la que desea recuperar metadatos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Option ID]</td> 
   <td> <p> Algunas propiedades tienen un conjunto de opciones disponibles que un usuario puede seleccionar como valor de propiedad. Introduzca el ID de la opción que representa el valor de propiedad que desea recuperar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Enumerar registros

Este módulo de búsqueda devuelve una lista de contactos, empresas u ofertas. La producción está limitada a 5.000 contactos, 12.500 empresas o 12.500 acuerdos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td> <p>Seleccione el tipo de registro que desea devolver.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Properties]</td> 
   <td>Seleccione las propiedades que desee incluir en la salida para este módulo.</td> 
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr>

</tbody> 
</table>

#### [!UICONTROL Update a Record]

Este módulo de acción actualiza un contacto, una compañía o un acuerdo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td>Seleccione el tipo de registro que desea actualizar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search Type]</td> 
   <td> <p>Si va a obtener un contacto, seleccione cómo desea identificar el registro:</p> 
    <ul> 
     <li> <p>[!UICONTROL ID]</p> </li> 
     <li> <p>[!UICONTROL Email]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Introduzca el ID del contacto, la compañía o el acuerdo que desea actualizar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Email]</td> 
   <td>Introduzca la dirección de correo electrónico del contacto cuyos detalles desea actualizar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Properties]</td> 
   <td>Rellene las propiedades que desee establecer para el registro. Los campos disponibles dependen del tipo de registro que desee crear.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Records]

Este módulo de activación inicia un escenario en el que se ha modificado o creado un contacto, una compañía o un acuerdo en los últimos 30 días. La salida está limitada a 10 000 registros.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td>Seleccione el tipo de registro que tiene la propiedad que desea ver.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search]</td> 
   <td>Seleccione si desea ver registros modificados recientemente o creados recientemente.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Properties]</td> 
   <td>Seleccione las propiedades que desea incluir en la salida del módulo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**Contactos**

### Contactos

* [[!UICONTROL Add Contacts to a List]](#add-contacts-to-a-list)
* [Crear/actualizar un contacto](#createupdate-a-contact)
* [[!UICONTROL Create/Update a Contact (Legacy)]](#createupdate-a-contact-legacy)
* [[!UICONTROL Create/Update a Group of Contacts]](#createupdate-a-group-of-contacts)
* [[!UICONTROL List Contacts]](#list-contacts)
* [[!UICONTROL List Contacts of a Company]](#list-contacts-of-a-company)
* [[!UICONTROL Merge contacts]](#merge-contacts)
* [[!UICONTROL Remove a Contact from a List]](#remove-a-contact-from-a-list)
* [[!UICONTROL Search for Contacts]](#search-for-contacts)
* [Observar contactos agregados a una lista](#watch-contacts-added-to-a-list)

#### [!UICONTROL Add Contacts to a List]

Este módulo añade los registros de contacto que ya se han creado en el sistema a una lista de contactos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List ID] </td> 
   <td>Seleccione el ID de la lista a la que desea añadir el contacto. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL IDs/Emails] </td> 
   <td> <p>Seleccione cómo desea identificar los contactos que desea añadir a la lista:</p> 
    <ul> 
     <li> <p>[!UICONTROL IDs]</p> <p>Añada los identificadores de los contactos que desea añadir a la lista.</p> </li> 
     <li> <p>[!UICONTROL Emails]</p> <p>Añada las direcciones de correo electrónico de los contactos que desee añadir a la lista.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### Crear/actualizar un contacto

Este módulo de acción crea un contacto si no existe en un portal. Si el contacto no existe en el portal, este módulo lo actualiza con los valores proporcionados.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Property groups]</td> 
   <td>Para cada propiedad que desee agregar al crear el contacto, seleccione el grupo donde se encuentra la propiedad. Se abrirá el grupo de propiedades, donde podrá rellenar los valores de las propiedades.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create/Update a Contact (Legacy)]

Crea un contacto si aún no existe en un portal o lo actualiza con los últimos valores de propiedad si ya existe en un portal.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Properties]</td> 
   <td>Rellene las propiedades que desee establecer o actualizar para el contacto. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create/Update a Group of Contacts]

Crea un grupo de contactos o los actualiza si ya existen. El rendimiento es mejor cuando el tamaño del lote se limita a 100 contactos o menos. Los cambios realizados a través de este punto final se procesan asincrónicamente, por lo que los cambios pueden tardar varios minutos en aplicarse a los registros de contactos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Batch of Contacts to Create/Update] </td> 
   <td> <p>Añada el lote de contactos.</p> <p>Haga clic en <strong>[!UICONTROL Add item]</strong> para agregar un nuevo contacto. En la ventana que aparece, introduzca o asigne la siguiente información:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Search Type]</strong> </p> <p>Seleccione cómo desea identificar al contacto:</p> 
      <ul> 
       <li> <p>[!UICONTROL ID]</p> <p>Introduzca el ID del contacto que desea crear o actualizar. </p> </li> 
       <li> <p>[!UICONTROL Email]</p> <p>Introduzca la dirección de correo electrónico del contacto que desea crear o actualizar. </p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL Properties]</strong> </p> <p>Rellene las propiedades que desee establecer o actualizar para el contacto.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Contacts]

Devuelve todos los contactos que se han creado en el portal. La salida está limitada a 5000 contactos. Para enumerar contactos anteriores o siguientes, puede usar el parámetro [!UICONTROL advanced] para desplazar la lista.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>El número máximo de contactos [!DNL Workfront Fusion] debe devolver durante un ciclo de ejecución de escenario. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output properties]</td> 
   <td>Seleccione las propiedades que desea que aparezcan en la salida del módulo. </td> 
  </tr> 
   <tr> 
    <td role="rowheader">ID de contacto [inicio de desplazamiento] </td> 
    <td>Introduzca o asigne el ID del usuario que desea que comience la lista. Por ejemplo, configurar el ID de contacto como el ID del contacto 101 permitirá al módulo enumerar los contactos 101-5100 en lugar de 1-5000. </td> 
   </tr>
 </tbody> 
</table>

#### [!UICONTROL List Contacts of a Company]

Recupera una lista de contactos de la compañía. La salida está limitada a 5000 contactos. Para enumerar contactos anteriores o siguientes, puede usar el parámetro [!UICONTROL advanced] para desplazar la lista.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Introduzca el ID de la compañía cuyos contactos desea enumerar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>El número máximo de contactos [!DNL Workfront Fusion] debe devolver durante un ciclo de ejecución de escenario. </td> 
  </tr> 
   <tr> 
    <td role="rowheader">ID de contacto [inicio de desplazamiento] </td> 
    <td>Introduzca o asigne el ID del usuario que desea que comience la lista. Por ejemplo, configurar el ID de contacto como el ID del contacto 101 permitirá al módulo enumerar los contactos 101-5100 en lugar de 1-5000. </td> 
   </tr>
 </tbody> 
</table>

#### [!UICONTROL Merge contacts]

Este módulo de acción combina contactos

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID 1] </td> 
   <td>Escriba el ID de uno de los contactos que desea combinar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID 2] </td> 
   <td>Escriba el ID del otro contacto que desea combinar.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Remove a Contact from a List]

Quita un contacto de una lista.

>[!NOTE]
>
>No se pueden quitar contactos manualmente de una lista dinámica.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List ID] </td> 
   <td>Seleccione el ID de la lista de la que desea quitar el contacto. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Contact ID] </td> 
   <td>Introduzca el ID del contacto que desea quitar de la lista. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search for Contacts]

Recupera una lista de contactos mediante la consulta de búsqueda.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td>Introduzca la consulta de búsqueda.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td>Escriba o asigne el número máximo de contactos que [!DNL Workfront Fusion] debe devolver durante un ciclo de ejecución de escenario. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch contacts added to a list]

Este módulo de activador inicia un escenario cuando se añade un nuevo contacto a una lista. Solo están disponibles para usuarios con una cuenta de marketing de pago.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List ID]</td> 
   <td>Escriba o asigne el ID de la lista que contiene los contactos que desea ver.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Properties]</td> 
   <td>Seleccione las propiedades que desea incluir en la salida del módulo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**Ofertas**

### Acuerdos

* [[!UICONTROL Get a Deal's CRM Pipeline]](#get-a-deals-crm-pipeline)
* [[!UICONTROL List Deal/Ticket Pipelines]](#list-dealticket-pipelines)

#### [!UICONTROL Get a Deal's CRM Pipeline]

Devuelve una canalización de acuerdo específica.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Pipeline ID] </td> 
   <td>Introduzca o asigne el ID de la canalización para la que desea recuperar detalles. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Stage ID] </td> 
   <td>Introduzca o asigne el ID de la fase para la que desea recuperar detalles. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Deal/Ticket Pipelines]

Devuelve todas las canalizaciones de acuerdos y tickets de un portal determinado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object Type] </td> 
   <td>Seleccione si quiere enumerar acuerdos o tickets.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++**Compañías**

### Compañías

#### [!UICONTROL Search for Companies by domain]

Recupera una lista de compañías en función de una coincidencia exacta con la propiedad del dominio.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Domain] </td> 
   <td>Escriba el dominio de las compañías que desea buscar, como <code>[!DNL hubspot].com</code>. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>El número máximo de compañías [!DNL Workfront Fusion] debe devolver durante un ciclo de ejecución de escenario. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output properties]</td> 
   <td>Seleccione las propiedades que desea que aparezcan en la salida del módulo. </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**Participaciones**

### Participaciones

* [Asociar una participación a un objeto CRM](#associate-an-engagement-with-a-crm-object)
* [Crear una participación](#create-an-engagement)
* [Eliminar una participación](#delete-an-engagement)
* [Ver participaciones](#watch-engagements)

#### Asociar una participación a un objeto CRM

Este módulo de acción asocia una participación con un contacto, una compañía o un acuerdo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>Seleccione el tipo de registro de CRM al que desea asociar una participación. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Engagement ID]</td> 
  <td>Introduzca o asigne el ID de la participación que desea asociar al objeto.</td> 
   </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record ID]</td> 
  <td>Introduzca o asigne el ID del registro al que desea asociar la participación.</td> 
   </tr> 
 </tbody> 
</table>

#### Crear una participación

Este módulo de acción crea una participación (como una nota, tarea o actividad) con un objeto CRM en HubSpot. Las participaciones son cualquier interacción con un contacto que debe registrarse en CRM.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Is Active?]</td> 
   <td>Active esta opción si la nueva participación va a estar activa cuando se cree. Una participación debe estar activa para que aparezca en la cronología.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
  <td>Seleccione el tipo de participación que desea crear.
  <ul>
  <li><b>Correo electrónico</b><p></p>Continuar a <a href="#email-metadata" class="MCXref xref" >Metadatos de correo electrónico</a>.</p></li>
  <li><b>Llamada</b><p>Continuar a <a href="#call-metadata" class="MCXref xref" >Llamar metadatos</a>.</p></li>
  <li><b>Reunión</b><p>Continuar a <a href="#meeting-fields" class="MCXref xref" >Campos de reunión</a>.</p></li>
  <li><b>Tarea</b><p>Continuar a <a href="#task-fields" class="MCXref xref" >Campos de tarea</a>.</p></li>
  <li><b>Nota</b><p>En el campo Body, introduzca el texto de la nota.</p></li>
  </ul>
  </td> 
   </tr> 
  <tr> 
   <td role="rowheader">Marca de tiempo</td> 
   <td>Introduzca o asigne una marca de tiempo para la participación.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Identificador de propietario</td> 
   <td>Introduzca o asigne el ID de propietario de la persona a la que se asignará el compromiso.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">UID</td> 
   <td>Introduzca o asigne un ID para la participación, que se puede utilizar en todos los tipos de objetos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de portal</td> 
   <td>Escriba o asigne el ID del portal. Esto resulta útil si su organización tiene varios portales.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Contactos asociados</td> 
   <td>Para cada contacto con el que desee asociar este compromiso, haga clic en <b>Agregar elemento</b> e introduzca el ID de contacto.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Compañías asociadas</td> 
   <td>Para cada compañía con la que desee asociar este compromiso, haga clic en <b>Agregar elemento</b> e introduzca el ID de compañía.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Ofertas asociadas</td> 
   <td>Para cada acuerdo con el que desee asociar este compromiso, haga clic en <b>Agregar elemento</b> e introduzca el ID de acuerdo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tickets asociados</td> 
   <td>Para cada ticket con el que desee asociar este compromiso, haga clic en <b>Agregar elemento</b> e introduzca el ID de ticket.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Archivos adjuntos</td> 
   <td>Para cada archivo adjunto con el que desee asociar este compromiso, haga clic en <b>Agregar elemento</b> e introduzca el identificador de archivo del archivo que desea adjuntar.</td> 
  </tr> 
 </tbody> 
</table>

##### Metadatos de correo electrónico

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL From > Email]</p> </td> 
   <td> <p>Introduzca o asigne la dirección de correo electrónico desde la que se enviará el correo electrónico.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL First Name]</td> 
   <td>Introduzca o asigne el nombre de la persona desde la que se enviará el correo electrónico.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Last Name]</td> 
  <td>Introduzca o asigne los apellidos de la persona desde la que se enviará el correo electrónico.
  </td> 
   </tr> 
  <tr> 
   <td role="rowheader">Hasta</td> 
   <td>Para cada dirección de correo electrónico a la que desee enviar el correo electrónico, haga clic en <b>Agregar elemento</b> y escriba o asigne la dirección de correo electrónico.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Cc</td> 
   <td>Para cada dirección de correo electrónico a la que desee agregar el correo electrónico, haga clic en <b>Agregar elemento</b> y escriba o asigne la dirección de correo electrónico.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Cco</td> 
   <td>Para cada dirección de correo electrónico a la que desee aplicar la copia CCO al correo electrónico, haga clic en <b>Agregar elemento</b> e introduzca o asigne la dirección de correo electrónico.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Asunto</td> 
   <td>Introduzca o asigne el texto del asunto del correo electrónico</td> 
  </tr> 
  <tr> 
   <td role="rowheader">HTML</td> 
   <td>Para enviar un correo electrónico con formato de HTML, introduzca o asigne el cuerpo del correo electrónico, incluidas las etiquetas de HTML.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Texto</td> 
   <td>Para enviar un correo electrónico de solo texto, introduzca o asigne el texto del cuerpo del correo electrónico.</td> 
  </tr> 
 </tbody> 
</table>

##### Metadatos de llamada

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL To Number]</p> </td> 
   <td> <p>Escriba o asigne el número de teléfono al que se realizará la llamada.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From Number]</td> 
   <td>Escriba o asigne el número de teléfono desde el que se realizará la llamada.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Status]</td> 
  <td>Seleccione el estado de la llamada.
  </td> 
   </tr> 
  <tr> 
   <td role="rowheader">Cuerpo</td> 
   <td>Introduzca o asigne los detalles o las notas de la llamada.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID externo</td> 
   <td>Este campo representa el ID interno de una llamada realizada en HubSpot. No requiere ninguna acción.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Duración</td> 
   <td>Introduzca o asigne la duración de la llamada en milisegundos</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de cuenta externa</td> 
   <td>Este campo representa el ID de cuenta interna de una llamada realizada en HubSpot. No requiere ninguna acción.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL de grabación</td> 
   <td>Introduzca o asigne la dirección URL del archivo de grabación.</td> 
  </tr> 
 </tbody> 
</table>

##### Campos de reunión

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Title]</p> </td> 
   <td> <p>Escriba o asigne el título o el asunto de la reunión.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td>Escriba o asigne el texto de la descripción o los detalles de la reunión.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start Time]</td> 
  <td>Escriba o asigne la hora de inicio de la reunión como una marca de tiempo UNIX.
  </td> 
   </tr> 
  <tr> 
   <td role="rowheader">Hora de finalización</td> 
   <td>Escriba o asigne la hora de finalización de la reunión como una marca de tiempo UNIX.</td> 
  </tr> 
 </tbody> 
</table>

##### Campos de tarea

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Subject]</p> </td> 
   <td> <p>Escriba o asigne el título o el asunto de la tarea.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td>Escriba o asigne el texto de la descripción o los detalles de la tarea.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Estado</td> 
   <td>Seleccione el estado de la tarea.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL For Object Type]</td> 
  <td>Escriba <code>CONTACT</code> o <code>COMPANY</code>.
  </td> 
   </tr> 
 </tbody> 
</table>

#### Eliminar una participación

Este módulo de acción elimina una participación por su ID.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>Introduzca o asigne el ID de la participación que desea eliminar.</td> 
  </tr> 
 </tbody> 
</table>

#### Ver participaciones

Este módulo de déclencheur inicia un escenario cuando se crea una nueva participación en un portal. Este módulo solo devuelve los registros creados en los últimos 30 días o los 10 000 registros creados más recientemente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>El número máximo de compañías [!DNL Workfront Fusion] debe devolver durante un ciclo de ejecución de escenario. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Since]</td> 
   <td>Introduzca o asigne la fecha más temprana en la que desea ver los eventos. Use el formato <code>MM/DD/YYYY h:mm</code>.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++**Eventos y notificaciones**

### Eventos y notificaciones

* [Crear/actualizar un evento de cronología](#create--update-a-timeline-event)
* [Enumerar tipos de eventos de cronología](#list-timeline-event-types)
* [Ver eventos de calendario](#watch-calendar-events)
* [Notificaciones de inspección](#watch-notifications)

#### Crear/actualizar un evento de cronología

Este módulo de acción crea o actualiza un evento de cronología. Este módulo solo se puede utilizar con una conexión de desarrollador que incluya su identificador de usuario, su clave de API de HubSpot, el ID de cliente y el secreto de cliente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Application ID]</td> 
   <td>Introduzca o asigne el ID de la aplicación a la que pertenece este evento.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event ID]</td> 
   <td>Introduzca o asigne un ID para este evento. El sistema no genera los ID de evento.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event Type ID]</td> 
   <td>Introduzca o asigne el ID del tipo de evento de este evento.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Email]</td> 
   <td>Escriba o asigne la dirección de correo electrónico del contacto para el que está creando el evento.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object ID]</td> 
   <td>Introduzca o asigne el ID del contacto para el que está creando el evento.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Timestamp]</td> 
   <td>Introduzca o asigne la marca de tiempo de este evento.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Custom data]</td> 
   <td>Para cada elemento de datos personalizados que desee agregar a este evento, haga clic en <b>Agregar elemento</b> e introduzca el nombre y el valor del elemento.</td> 
  </tr> 
 </tbody> 
</table>

#### Enumerar tipos de eventos de cronología

Este módulo de búsqueda devuelve una lista de todos los eventos de cronología de una aplicación específica. Este módulo solo se puede utilizar con una conexión de desarrollador que incluya su identificador de usuario, su clave de API de HubSpot, el ID de cliente y el secreto de cliente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Application ID]</td> 
   <td>Introduzca o asigne el ID de la aplicación a la que pertenecen estos eventos. </td> 
  </tr> 
 </tbody> 
</table>

#### Ver eventos de calendario

Este módulo de déclencheur inicia un escenario cuando se agrega un nuevo evento a un calendario. Incluye hasta 500 tareas en el intervalo entre la fecha de inicio y la de finalización. Este módulo solo se puede utilizar con una conexión de desarrollador que incluya su identificador de usuario, su clave de API de HubSpot, el ID de cliente y el secreto de cliente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Events Type]</td> 
   <td>Seleccione si desea ver eventos sociales, eventos de contenido o todos los eventos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de archivos que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start Date]</td> 
   <td>Introduzca o asigne la fecha de inicio.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL End Date]</td> 
   <td>Introduzca o asigne la fecha de finalización.</td> 
  </tr> 
 </tbody> 
</table>

#### Notificaciones de inspección

Este módulo de déclencheur inicia un escenario cuando se envía una nueva notificación sobre los cambios.  Incluye hasta 500 tareas en el intervalo entre la fecha de inicio y la de finalización. Este módulo solo se puede utilizar con una conexión de desarrollador que incluya su identificador de usuario, su clave de API de HubSpot, el ID de cliente y el secreto de cliente. Solo puede tener una URL de webhook por aplicación de desarrollador en HubSpot.

Para crear un webhook para este módulo, haz clic en **Agregar** junto al campo de webhook y rellena los campos siguientes:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Application ID]</td> 
   <td>Introduzca el ID de aplicación que desea utilizar para este webhook. Puede encontrar el ID en su portal para desarrolladores de HubSpot.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subscriptions]</td> 
   <td> <p>Para cada tipo de notificación que desee ver, haga clic en <b>Agregar elemento</b> y seleccione el tipo de suscripción.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Force to Remove Old Subscriptions]</td> 
   <td>Active esta opción para desasociar o eliminar las suscripciones antiguas adjuntas a este webhook.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++**Archivos**

### Archivos

* [[!UICONTROL Create a Folder]](#create-a-folder)
* [Eliminar un archivo](#delete-a-file)
* [[!UICONTROL Delete a Folder]](#delete-a-folder)
* [Archivos de lista](#list-files)
* [[!UICONTROL Move a File]](#move-a-file)
* [Cargar un archivo](#upload-a-file)
* [Ver archivos](#watch-files)

#### [!UICONTROL Create a Folder]

Este módulo crea una carpeta.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder Name] </td> 
   <td>Introduzca o asigne un nombre para la nueva carpeta.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Parent Folder ID] </td> 
   <td>Seleccione el ID de la carpeta principal de la carpeta que está creando. </td> 
  </tr> 
 </tbody> 
</table>

#### Eliminar un archivo

Este módulo de acción elimina permanentemente un archivo y todos los datos y miniaturas relacionados del administrador de archivos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>Introduzca o asigne el ID del archivo que desea eliminar.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Folder]

Marca una carpeta como eliminada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Introduzca o asigne el ID de la carpeta que desea eliminar.</td> 
  </tr> 
 </tbody> 
</table>

#### Archivos de lista

Este módulo de búsqueda devuelve una lista de archivos almacenados en el administrador de archivos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de archivos que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID]</td> 
   <td>Introduzca o asigne el ID de la carpeta que contiene los archivos que desea enumerar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td>Para incluir sólo archivos que contengan caracteres específicos en el nombre de archivo, escriba o asigne los caracteres que desea que el nombre de archivo incluya.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move a File]

Mueve un archivo a otra carpeta.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID] </td> 
   <td>Introduzca o asigne el ID del archivo que desea mover. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td>Seleccione el ID de la carpeta a la que desea mover el archivo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>Introduzca un nombre para el archivo que ha movido. </td> 
  </tr> 
 </tbody> 
</table>

#### Cargar un archivo

Este módulo de acción carga un archivo en el administrador de archivos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Access type] </td> 
   <td>Seleccione si desea que el archivo sea privado, público pero no indexable o público e indexable. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td>Seleccione el ID de la carpeta en la que desea cargar el archivo. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Overwrite]</td> 
   <td>Active esta opción para sobrescribir el archivo si ya existe en la carpeta.</td> 
  </tr> 
 </tbody> 
</table>

### Observar archivos

Este módulo de déclencheur inicia un escenario cuando se guarda un nuevo archivo en el administrador de archivos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de archivos que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID]</td> 
   <td>Introduzca o asigne el ID de la carpeta que contiene los archivos que desea inspeccionar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td>Para incluir sólo archivos que contengan caracteres específicos en el nombre de archivo, escriba o asigne los caracteres que desea que el nombre de archivo incluya.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++**Tareas**

### Tareas

* [Crear una tarea de calendario](#create-a-calendar-task)
* [Eliminar una tarea del calendario](#create-a-calendar-task)
* [Ver eventos de tarea](#watch-task-events)

#### Crear una tarea de calendario

Este módulo de acción crea una nueva tarea para un calendario. La conexión utilizada en este módulo debe utilizar las credenciales de un usuario con una cuenta de marketing de pago.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>Escriba o asigne un nombre para la nueva tarea de calendario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Escriba o asigne una descripción para la nueva tarea de calendario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Owner ID]</td> 
   <td>Introduzca o asigne el ID de propietario del usuario asignado a esta tarea.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event Date]</td> 
   <td>Escriba o asigne la fecha de esta tarea.<p>Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos en [!DNL Adobe Workfront Fusion]</a>.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Category]</td> 
   <td>Seleccione el tipo de evento.<ul><li><b>Publicación de blog</b><p>Introduzca el ID del grupo de contenido. Este es el ID de la página del blog.</p></li><li><b>Correo electrónico</b><p>Introduzca o asigne la ruta a la plantilla de correo electrónico que desee utilizar.</li><li><b>Página de aterrizaje</b><p>Introduzca o asigne la ruta a la plantilla de página de aterrizaje que desee utilizar.</li><li><b>Personalizado</b></li><ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL State]</td> 
   <td>Introduzca si el evento está en estado "pendiente" o "listo".</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Campaign GUID]</td> 
   <td>Introduzca o asigne el ID de HubSpot interno de la campaña de la que forma parte este evento.</td> 
  </tr> 
 </tbody> 
</table>

#### Eliminar una tarea del calendario

Este módulo de acción elimina una tarea del calendario. La conexión utilizada en este módulo debe utilizar las credenciales de un usuario con una cuenta de marketing de pago.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Introduzca o asigne el ID de la tarea que desea eliminar.</td> 
  </tr> 
 </tbody> 
</table>

#### Ver eventos de tarea

Este módulo de déclencheur inicia un escenario cuando hay un nuevo evento de tarea en un calendario. La conexión utilizada en este módulo debe utilizar las credenciales de un usuario con una cuenta de marketing de pago. El módulo devuelve hasta 500 eventos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de archivos que desea que devuelva el módulo durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start Date]</td> 
   <td>Introduzca o asigne la fecha más temprana en la que desea ver los eventos. Use el formato <code>MM/DD/YYYY h:mm</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL End Date]</td> 
   <td>Escriba o asigne la última fecha para la que desea ver eventos. Use el formato <code>MM/DD/YYYY h:mm</code>.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++**Usuarios**

### Usuarios

* [Obtener un propietario](#get-an-owner)
* [Enumerar propietarios](#list-owners)

#### Obtener un propietario

Este módulo de acción devuelve los detalles de un propietario.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Owner ID]</td> 
   <td> <p>Introduzca o asigne el ID del propietario para el que desea obtener detalles.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Enumerar propietarios

Este módulo de búsqueda devuelve una lista de todos los propietarios de una cuenta de HubSpot.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**Entradas**

### Entradas

<!--* [Create a Ticket]-->
* [Eliminar un ticket](#delete-a-ticket)
  <!--* [Create a Ticket]-->
  <!--* [Create a Ticket]-->
  <!--* [Create a Ticket]-->
  <!--* [Create a Ticket]-->

<!-- Create a Ticket Need to find a working connection-->

#### [!UICONTROL Delete a Ticket]

Elimina un ticket existente por su ID.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Introduzca el ID del ticket que desea eliminar. </td> 
  </tr> 
 </tbody> 
</table>

<!-- Get a Ticket  Need to find a working connection-->

<!-- List Tickets  Need to find a working connection-->

&lt;!— Actualizar un vale Necesita encontrar una conexión que funcione—>

<!-- Watch Tickets Need to find a working connection-->

+++

+++**Forms**

### Formularios

* [Obtener un archivo cargado mediante formulario](#get-a-file-uploaded-via-form)
* [Lista de Forms](#list-forms)
  <!--* [Submit Data to a Form]-->
  <!--* [Watch Submissions for a Form]-->

#### Obtener un archivo cargado mediante formulario

Este módulo de acción devuelve un archivo que se ha cargado a través de un formulario.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File URL]</td> 
   <td>Introduzca o asigne la dirección URL del archivo que desea recuperar. Esto se puede encontrar en los metadatos del formulario.</td> 
  </tr> 
 </tbody> 
</table>

#### Enumerar Forms

Este módulo de acción devuelve todos los formularios que se han creado en la cuenta asociada con la conexión utilizada para este módulo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Introduzca o asigne el número máximo de formularios que devolverá el módulo en un ciclo de ejecución.</td> 
  </tr> 
 </tbody> 
</table>

<!--#### Submit Data to a Form Need to find a working connection-->



&lt;!—#### Ver los envíos de un formulario—Necesita encontrar una conexión que funcione>—>

+++

+++**Medios sociales (difusión)**

### Medios sociales (difusión)

* [Cancelar un mensaje de difusión](#cancel-a-broadcast-message)
* [Crear un mensaje de difusión](#create-a-broadcast-message)
* [Ver mensajes transmitidos](#watch-broadcast-messages)

#### Cancelar un mensaje de difusión

Este módulo de acción cancela una difusión programada, como un tweet o una publicación de Facebook.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Broadcast ID]</td> 
   <td>Introduzca o asigne el ID de la emisión que desea cancelar.</td> 
  </tr> 
 </tbody> 
</table>

#### Crear un mensaje de difusión

Este módulo de acción crea y publica inmediatamente un mensaje en el canal de medios sociales especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel ID]</td> 
   <td>Introduzca o asigne el ID del canal que desea utilizar para esta difusión.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Title]</td> 
   <td>Escriba o asigne un título para esta difusión.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td>Introduzca o asigne el texto de la emisión.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Photo URL]</td> 
   <td>Escriba o asigne la dirección URL de una fotografía que desee incluir en la difusión.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Thumbnail URL]</td> 
   <td>Escriba o asigne la dirección URL de una miniatura que desee usar para esta difusión.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Trigger at]</td> 
   <td>Escriba o asigne la fecha y la hora en que desea que se envíe la difusión. Si se deja en blanco, la emisión se envía inmediatamente.<p>Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos en [!DNL Adobe Workfront Fusion]</a>.</p></td> 
  </tr> 
 </tbody> 
</table>

#### Ver mensajes transmitidos

Este módulo de déclencheur inicia un escenario cuando se publica un mensaje desde HubSpot al canal de medios sociales especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Introduzca o asigne el número máximo de elementos que devolverá el módulo en un ciclo de ejecución.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter by Status]</td> 
   <td>Para iniciar el escenario solo cuando el mensaje esté en un estado específico, seleccione el estado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter by Channel]</td> 
   <td>Para iniciar el escenario solo cuando el mensaje esté en un canal específico, seleccione el canal.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Broadcast ID]</td> 
   <td>Para iniciar el escenario solo cuando el mensaje esté en una fecha específica o posterior, escriba o asigne la fecha en el formato <code>MM/DD/YYYY</code>.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++**Publicaciones de blog**

### Publicaciones de blog

<!--* [Create a Blog Post]-->
* [Eliminar una publicación de blog](#delete-a-blog-post)
  <!--* [List Blog Posts]-->
* [Publish/Cancelar publicación de una publicación de blog](#publish--unpublish-a-blog-post)
  <!--* [Watch Blog Posts]-->

<!--
#### Create a Blog Post May need connection
-->


#### Eliminar una publicación de blog

Este módulo de acción elimina una sola publicación de blog.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Escriba o asigne el identificador de la publicación de blog que desea eliminar.</td> 
  </tr> 
 </tbody> 
</table>

<!--#### List Blog Posts May need connection

This search module retrieves posts from a HubSpot blog.-->

#### Publish / Cancelar la publicación de un blog

Este módulo de acción programa o cancela la publicación de una publicación de blog.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Introduzca o asigne el ID de la publicación de blog que desea programar o cancelar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Action]</td> 
   <td>Seleccione si desea programar la publicación de blog o cancelar una publicación de blog programada anteriormente.</td> 
  </tr> 
 </tbody> 
</table>

<!--#### Watch Blog PostsMay need connection-->

+++

<!--+++**Workflows**>

<!--### Workflows May need connection

#### Add a Contact to a Workflow


#### Remove a Contact from a Workflow

-->

<!--+++-->

+++**Suscripciones**

### Suscripciones

* [Actualizar suscripción de correo electrónico](#update-email-subscription)
* [Ver la cronología de suscripciones de un portal](#watch-subscriptions-timeline-for-a-portal)

#### Actualizar suscripción de correo electrónico

Este módulo de acción actualiza una suscripción de correo electrónico en HubSpot.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Email]</td> 
   <td>Introduzca o asigne la dirección de correo electrónico de la suscripción que desea actualizar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Statuses]</td> 
   <td>Para cada estado para el que desee actualizar la suscripción, haga clic en <b>Agregar elemento</b> e introduzca el ID del estado, y si la dirección de correo electrónico se suscribirá a ese estado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Portal Subscription Legal Status]</td> 
   <td>Para registrar la base legal de esta suscripción para el RGPD, seleccione el estado legal de esta suscripción.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Portal Subscription Legal Basis Explanation]</td> 
   <td>Para añadir una nota sobre la base legal de esta suscripción para el RGPD, introduzca o asigne el texto de la nota.</td> 
  </tr> 
 </tbody> 
</table>

#### Ver la cronología de suscripciones de un portal

Este módulo de déclencheur inicia un escenario cuando se agrega una nueva suscripción de cronología de correo electrónico al portal.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Introduzca o asigne el número máximo de elementos que devolverá el módulo en un ciclo de ejecución.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start Timestamp]</td> 
   <td>Para devolver resultados a partir de una fecha específica, introduzca la fecha en el formato <code>MM/DD/YYYY.</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL End Timestamp]</td> 
   <td>Para devolver resultados de en una fecha específica o antes, introduzca la fecha en el formato <code>MM/DD/YYYY.</code></td> 
  </tr> 
 </tbody> 
</table>

+++

<!--+++**Associations**-->

<!--### Associations-->

<!--#### Associate CRM Objects  May need connection

This action module associates two CRM objects.-->

<!--#### Associate Multiple CRM Objects  May need connection-->



<!--#### Delete an Association May need connection-->



<!--#### Delete Multiple Associations between CRM Objects May need connection-->



<!--#### List Associations for a CRM Object May need connection-->

<!--+++-->

+++**Otro**

### Otro

#### [!UICONTROL Make an API Call]

Le permite realizar una llamada de API personalizada.

>[!NOTE]
>
>Los siguientes puntos finales quedaron obsoletos en la API de HubSpot el 31 de agosto de 2023 y ya no se pueden utilizar en los módulos de Fusion.
>
>* Enumerar eventos de contenido
>* Enumerar eventos sociales
>* Enumerar eventos de tarea de calendario
>* Enumerar todos los eventos de calendario
>* Crear tarea de calendario
>* Obtener tarea de calendario por el ID
>* Actualizar tarea de calendario
>* Eliminar una tarea de calendario

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL HubSpot CRM] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>Escriba una ruta relativa a https://api.hubapi.com/. Por ejemplo, /contacts/v1/lists/all/contacts/all</p> <p>Para obtener la lista de puntos finales disponibles, consulte la <a href="https://legacydocs.hubspot.com/docs/overview">[!DNL HubSpot]Documentación de la API </a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>Seleccione el método HTTP que desea utilizar:</p> <p>[!UICONTROL GET]</p> <p>para recuperar la información de una entrada.</p> <p>[!UICONTROL POST]</p> <p>para crear una nueva entrada.</p> <p>[!UICONTROL PUT]</p> <p>para actualizar o reemplazar una entrada existente.</p> <p>[!UICONTROL PATCH]</p> <p>para realizar una actualización de entrada parcial.</p> <p>[!UICONTROL DELETE]</p> <p>para eliminar una entrada.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p> Introduzca los encabezados de solicitud deseados. No tiene que añadir encabezados de autorización; ya lo hemos hecho nosotros.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> Introduzca la cadena de consulta de la solicitud.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar. Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, ponga las comillas fuera de la instrucción condicional.<img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"></p> </td> 
  </tr> 
 </tbody> 
</table>

>[!INFO]
>
>**Ejemplo:** la siguiente llamada de API devuelve todos los contactos de su cuenta de [!DNL HubSpot]:
>
>**URL**: `/contacts/v1/lists/all/contacts/all`
>
>**Método**: `GET`
>
>![](/help/workfront-fusion/references/apps-and-modules/assets/hubspot-api-config.png)
>
>Las coincidencias de la búsqueda se pueden encontrar en la salida del módulo en [!UICONTROL Bundle] > [!UICONTROL Body] > [!UICONTROL contacts].
>
>En nuestro ejemplo, se han devuelto 3 contactos:
>
>![](/help/workfront-fusion/references/apps-and-modules/assets/hubspot-api-output.png)

+++

## Crear una nueva aplicación

1. Inicie sesión en su cuenta de desarrollador de [!DNL HubSpot].
1. Seleccione la opción **[!UICONTROL Create an App]**.
1. Escriba el nombre de la aplicación y [!UICONTROL Save] el cuadro de diálogo.
1. Seleccione los ámbitos que necesitará para su webhook.

   Por ejemplo, añada ámbitos de contactos para activar el módulo cuando se cree o elimine un nuevo contacto.

   [!UICONTROL contacts scope] es todo lo que necesita para recibir contactos, ofertas y webhooks de eventos de la compañía.

   >[!IMPORTANT]
   >
   >No rellene el campo [!UICONTROL Redirect URL].
