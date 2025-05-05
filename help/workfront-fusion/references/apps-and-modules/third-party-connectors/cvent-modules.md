---
title: Módulos Cvent
description: En un escenario de  [!DNL Adobe Workfront Fusion] , puede automatizar los flujos de trabajo que utilizan Cvent, así como conectarlos a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: b7e16180-1db8-4aff-bb7b-69ca98194b00
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 85%

---

# Módulos de [!DNL Cvent]

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!DNL Cvent], así como conectarlo a varias aplicaciones y servicios de terceros.

Para obtener instrucciones sobre cómo crear un escenario, vea los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

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
   <p>Requisito de licencia heredado: [!DNL Workfront Fusion] para automatización e integración de trabajo </p>
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

Para usar módulos [!DNL Cvent], debe tener una cuenta de [!DNL Cvent].

## Información de Cvent API

El conector Cvent utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> V200611.ASMX </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.7.14</td> 
  </tr>
 </tbody> 
 </table>

## Conectar [!DNL Cvent] a [!DNL Adobe Workfront Fusion] {#connect-cvent-to-adobe-workfront-fusion}

>[!NOTE]
>
>Los módulos [!DNL Cvent] funcionan a través de una API [!UICONTROL SOAP]. Para crear una conexión con [!DNL Cvent] debe asegurarse de lo siguiente:
>
>* Tiene acceso de [!UICONTROL SOAP] a la API de [!DNL Cvent].
>* Se han añadido las direcciones IP de [!DNL Workfront Fusion] a la lista de permitidos de su organización.
>
>  Para obtener una lista de [!DNL Workfront Fusion] direcciones IP, consulte [Configuración de direcciones IP para Fusion en la lista de permitidos de su organización](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/set-up-ip-addresses-for-fusion.md)


Puede crear una conexión con su cuenta de [!DNL Cvent] directamente desde un módulo de [!DNL Cvent].

1. En cualquier módulo de [!DNL Cvent], haga clic en **[!UICONTROL Add]** junto al campo [!UICONTROL Connection].
1. Seleccione la región a la que desea conectarse.

   * [!UICONTROL North America]
   * [!UICONTROL Europe]
   * [!UICONTROL Sandbox]

1. Haga clic en **[!UICONTROL Continue]** para crear la conexión y volver al módulo.

## Módulos de [!DNL Cvent] y sus campos

Al configurar módulos de [!DNL Cvent], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Cvent] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Acciones](#actions)
* [Búsquedas](#searches)

### Acciones

* [[!UICONTROL Custom API Call]](#create-meeting-request)
* [[!UICONTROL Read a record]](#read-a-record)
* [[!UICONTROL Register Invitee]](#register-invitee)
* [[!UICONTROL Add Invitee]](#add-invitee)
* [[!UICONTROL Delete Contact]](#delete-contact)
* [[!UICONTROL Update Contact]](#update-contact)
* [[!UICONTROL Create meeting request]](#create-meeting-request)

#### [!UICONTROL Custom API Call]

Este módulo de acción le permite realizar una llamada autenticada personalizada a la API [!DNL Cvent]. De este modo, puede crear una automatización del flujo de datos imposibles de realizar por los otros [!DNL Cvent] módulos.

Al configurar este módulo, se muestran los campos siguientes.

El módulo devuelve el código de estado, junto con los encabezados y el cuerpo de la llamada de API.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar la cuenta de [!DNL Cvent] a [!DNL Workfront Fusion], consulte <a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Cvent] a [!DNL Adobe Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Operación</td> 
   td&gt; <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Cuerpo (XML)</td> 
   <td> <p>Introduzca o asigne el cuerpo de la llamada de API. Esto debe incluir únicamente el XML. El módulo incluirá automáticamente los encabezados de autenticación. </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Read a record]

Este módulo de acción lee información sobre un registro específico.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Cvent] a [!DNL Workfront Fusion], consulte <a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Cvent] a [!DNL Adobe Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Record type]</p> </td> 
   <td>Seleccione el tipo de elemento del registro que quiera leer.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Contact] / [!UICONTROL Event] / [!UICONTROL Invitee ID]</td> 
   <td> <p>Escriba o asigne el identificador del elemento que quiera leer.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Seleccione los campos que desea incluir en la salida del módulo. Los campos están disponibles en función del tipo de elemento seleccionado.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Register Invitee]

Este módulo de acción registra a un invitado a un evento.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Cvent] a [!DNL Workfront Fusion], consulte <a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Cvent] a [!DNL Adobe Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ID de invitado</p> </td> 
   <td> <p>Introduzca o asigne el ID de la persona invitada que quiera registrar a un evento.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de evento</td> 
   <td> <p>Introduzca o asigne el ID del evento para el que quiera registrar al invitado.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Add Invitee]

Este módulo de acción invita a un contacto a un evento.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Cvent] a [!DNL Workfront Fusion], consulte <a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Cvent] a [!DNL Adobe Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Contact ID]</p> </td> 
   <td> <p>Introduzca o asigne el ID del contacto que quiera añadir a un evento.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event ID]</td> 
   <td> <p>Introduzca o asigne el ID del evento al que quiera añadir el contacto.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete Contact]

Este módulo de acción elimina un solo contacto en Cvent.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Cvent] a [!DNL Workfront Fusion], consulte <a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Cvent] a [!DNL Adobe Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Contact ID]</td> 
   <td> <p>Introduzca o asigne el ID del contacto que desea eliminar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update Contact]

Este módulo de acción actualiza un contacto existente mediante su ID.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Cvent] a [!DNL Workfront Fusion], consulte <a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Cvent] a [!DNL Adobe Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Contact ID]</p> </td> 
   <td> <p>Introduzca o asigne el ID del contacto que desea actualizar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td> <p>Seleccione los campos para los que desea introducir información y rellene los valores deseados para esos campos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Custom fields]</td> 
   <td> <p>Seleccione los campos para los que desea introducir información y rellene los valores deseados para esos campos.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create meeting request]

Este módulo de acción añade una convocatoria de reunión a su cuenta.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Cvent] a [!DNL Workfront Fusion], consulte <a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Cvent] a [!DNL Adobe Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Form ID]</p> </td> 
   <td> <p>Escriba o asigne el ID del formulario que desea utilizar para crear la nueva convocatoria de reunión.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Meeting Request Fields]</td> 
   <td> <p>Seleccione los campos de convocatoria de reunión para los que desea escribir información y, a continuación, rellene los valores deseados para esos campos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event Request Fields]</td> 
   <td> <p>Seleccione los campos de solicitud de evento para los que desea introducir información y, a continuación, rellene los valores deseados para esos campos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL RFP Request Fields]</td> 
   <td> <p>Seleccione los campos de solicitud de propuesta para los que desea introducir información y, a continuación, rellene los valores deseados para esos campos.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Búsquedas

#### [!UICONTROL List records]

Este módulo de búsqueda recupera información sobre todos los registros de un tipo específico.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Cvent] a [!DNL Workfront Fusion], consulte <a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">Conectar [!DNL Cvent] a [!DNL Adobe Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Record type]</p> </td> 
   <td> <p>Seleccione el tipo de registro que desea enumerar.</p> 
    <ul> 
     <li> <p>Todos los eventos de su cuenta de [!DNL Cvent]</p> </li> 
     <li> <p>Todas las sesiones de un evento</p> </li> 
     <li> <p>Todos los invitados a un evento</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event ID]</td> 
   <td> <p>Si está enumerando invitados o sesiones, introduzca o asigne el ID del evento al que están asociados dichos invitados o sesiones.</p> </td> 
  </tr> 
 </tbody> 
</table>
