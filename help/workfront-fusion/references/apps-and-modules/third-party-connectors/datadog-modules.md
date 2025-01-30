---
title: Módulos Datadog
description: En un escenario de  [!DNL Adobe Workfront Fusion] , puede automatizar los flujos de trabajo que utilizan Datadog, así como conectarlo a distintas aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: c8c5f2e3-5af1-4957-bb6f-6c19c35102c5
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 81%

---

# Módulos de [!DNL Datadog]

En un escenario de [!DNL Adobe Workfront Fusion], es posible automatizar los flujos de trabajo que utilizan [!DNL Datadog], así como conectarlo a varias aplicaciones y servicios de terceros.

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

Para usar módulos [!DNL Datadog], debe tener una cuenta de [!DNL Datadog].

## Información de API de Datadog

El conector Datadog utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>1.0.11</td> 
  </tr>
 </tbody> 
 </table>

## Conectar [!DNL Datadog] a [!DNL Workfront Fusion] {#connect-datadog-to-workfront-fusion}

### Recupere la clave de API y la clave de aplicación {#retrieve-your-api-key-and-application-key}

Para conectar su cuenta de [!DNL Datadog] a [!DNL Workfront Fusion], debe recuperar una clave de API y una clave de aplicación de su cuenta de [!DNL Datadog].

1. Inicie sesión en su cuenta de [!DNL Datadog].
1. En el panel de navegación izquierdo, haga clic en **[!UICONTROL Integrations]** y luego en **[!UICONTROL APIs]**.
1. En la pantalla principal, haga clic en **[!UICONTROL API Keys]**.
1. Pase el puntero por encima de la barra morada para mostrar la clave de API.
1. Copie la clave de API en una ubicación segura.
1. En la pantalla principal, haga clic en **[!UICONTROL Application Keys]**.
1. Pase el puntero por encima de la barra morada para mostrar la clave de la aplicación.
1. Copie la clave de la aplicación en una ubicación segura.

### Crear una conexión con [!DNL Datadog] en [!DNL Workfront Fusion]

Puede crear una conexión con su cuenta de [!DNL Datadog] directamente desde un módulo de [!UICONTROL Datadog].

1. En cualquier módulo de [!UICONTROL Datadog], haga clic en **[!UICONTROL Add]** junto al campo [!UICONTROL Connection].
1. Rellene los campos del módulo de la siguiente manera:

<table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Connection Type]</td> 
      <td> <p> Seleccione la opción [!UICONTROL [!DNL Datadog] [Aplicación] para obtener acceso completo a la API [!DNL Datadog].</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Connection Name]</td> 
      <td> <p> Introduzca un nombre para la conexión. </p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Domain] </td> 
      <td> <p>Seleccione el dominio al que desea conectarse (EE. UU. o UE).</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL API Key]</td> 
      <td> <p> Escriba su clave de API de [!DNL Datadog]. </p> <p>Para obtener instrucciones sobre cómo recuperar la clave de API, consulte <a href="#retrieve-your-api-key-and-application-key" class="MCXref xref">Recuperar la clave de API y la clave de aplicación</a> en este artículo.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Application Key]</td> 
      <td> <p> Escriba la clave de aplicación de [!DNL Datadog]. </p> <p>Para obtener instrucciones sobre cómo recuperar la clave de aplicación, consulte <a href="#retrieve-your-api-key-and-application-key" class="MCXref xref">Recuperar la clave de API y la clave de aplicación</a> en este artículo.</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. Haga clic en **[!UICONTROL Continue]** para crear la conexión y volver al módulo.

## Módulos de [!DNL Datadog] y sus campos

Al configurar módulos de [!DNL Datadog], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Datadog] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Acciones

* [[!UICONTROL Post Timeseries Points]](#post-timeseries-points)
* [[!UICONTROL Make an API Call]](#make-an-api-call)

#### [!UICONTROL Post Timeseries Points]

El módulo le permite publicar datos de serie temporal que se pueden representar gráficamente en los paneles de control de [!DNL Datadog].

El límite para las cargas útiles comprimidas es de 3,2 MB (3200000) y de 62 MB (62914560) para las cargas útiles descomprimidas.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Datadog] a [!DNL Workfront Fusion], consulte <a href="#connect-datadog-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Datadog] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Series]</td> 
   <td> <p>Añada la serie temporal que desee enviar a [!DNL Datadog].</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Metric]</strong> </p> <p>Introduzca el nombre de la serie temporal.</p> </li> 
     <li> <p><strong>[!UICONTROL Type]</strong> </p> <p>Seleccione el tipo de métrica.</p> </li> 
     <li> <p><strong>[!UICONTROL Interval]</strong> </p> <p> Si el tipo de métrica es tasa o recuento, defina el intervalo correspondiente.</p> </li> 
     <li> <p><strong>[!UICONTROL Points]</strong> </p> <p>Añada puntos relacionados con una métrica.</p> <p>Esta es una matriz de puntos JSON. Cada punto tiene el formato: <code>[[POSIX_timestamp, numeric_value], ...] </code></p> <p>Nota:  <p>La marca de tiempo debe estar en segundos.</p> <p>La marca de tiempo debe ser actual. Actual se define como no más de 10 minutos en el futuro o más de 1 hora en el pasado.</p> <p> El formato de valor numérico debe ser un valor flotante.</p> </p> <p>Este campo debe contener al menos 1 elemento.</p> </li> 
     <li> <p><strong>[!UICONTROL Host]</strong> </p> <p>Introduzca el nombre del host que produjo la métrica.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Make an API Call]

Este módulo de acción le permite realizar una llamada de API personalizada.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre la conexión de su cuenta de [!DNL Datadog] a [!DNL Workfront Fusion], consulte <a href="#connect-datadog-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Datadog] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Escriba una ruta relativa a <code>https://api.datadoghq.com/api/</code>. Ejemplo:<code> /v1/org</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion añade los encabezados de autorización para usted.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Añada la consulta para la llamada de API en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la instrucción condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Ejemplo:** la siguiente llamada de API devuelve todos los paneles de su cuenta de [!DNL Datadog]:

URL: `/v1/dashboard`

Método: `GET`

![Ejemplo de llamada de API Datadog](/help/workfront-fusion/references/apps-and-modules/assets/datadog-api-example.png)

El resultado se puede encontrar en los paneles de control Salida del módulo, en Paquete > Cuerpo >.

En nuestro ejemplo, se han devuelto 3 paneles de control:

![Respuesta de la API Datadog](/help/workfront-fusion/references/apps-and-modules/assets/datadog-api-response-example.png)
