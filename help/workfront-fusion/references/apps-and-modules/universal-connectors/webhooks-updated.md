---
title: Webhooks
description: Un webhook es una llamada HTTP activada por un evento. Puede utilizar webhooks para activar módulos de activador instantáneos. Cualquier aplicación que esté conectada a Internet y permita peticiones HTTP puede enviar webhooks a Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 8e415378-e9c1-4b49-874b-6d38aba0c303
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '1331'
ht-degree: 68%

---

# Webhooks



<!--This information moved to the webhooks article in the create scenarios folders in the new repo-->

Un webhook es una llamada HTTP activada por un evento. Puede utilizar webhooks para activar módulos de activador instantáneos. Cualquier aplicación que esté conectada a Internet y permita peticiones HTTP puede enviar webhooks a Adobe Workfront Fusion.

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
   <td> <p>Nuevo: estándar</p><p>O</p><p>Actual: Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion**</td> 
   <td>
   <p>Actual: no se requiere licencia de Workfront Fusion.</p>
   <p>O</p>
   <p>Heredado: Workfront Fusion para la automatización e integración del trabajo </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Seleccione o paquete de Prime Workfront: su organización debe adquirir Adobe Workfront Fusion.</li><li>Paquete de Ultimate Workfront: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe adquirir Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Usar un webhook en [!DNL Workfront Fusion]

>[!NOTE]
>
>Para llamar a un webhook de terceros (un webhook saliente), utilice uno de los módulos HTTP. Para obtener más información, consulte [Módulos HTTP](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#universal-connectors).

Para usar un webhook para conectar una aplicación a [!DNL Workfront Fusion]:

1. Agregue el módulo de déclencheur instantáneo **[!UICONTROL Webhooks]** >**[!UICONTROL Custom Webhook]** a su escenario.

1. Haga clic en **[!UICONTROL Add]** junto al campo Webhook e introduzca un nombre para el nuevo webhook.
1. (Opcional) Haga clic en **[!UICONTROL Advanced Settings]**.
1. En el campo **[!UICONTROL IP restrictions]**, escriba una lista separada por comas de las direcciones IP desde las que el módulo puede aceptar datos.
1. Haga clic **[!UICONTROL Save]**

Después de crear un webhook, aparece una dirección URL única. Esta es la dirección a la que el webhook envía los datos. Workfront Fusion valida los datos enviados a esta dirección y los transmite para su procesamiento en el escenario.

>[!NOTE]
>
>Una vez creado un webhook, puede utilizarlo en más de un escenario a la vez.

### Configuración de la estructura de datos del webhook {#configure-the-webhook-s-data-structure}

Para reconocer la estructura de datos de la carga útil entrante, [!DNL Workfront Fusion] analiza los datos de ejemplo que envía a la dirección mostrada. Puede proporcionar los datos de muestra realizando un cambio en el servicio o la aplicación que hará que ese servicio o aplicación llame al webhook. Por ejemplo, puede quitar un archivo.

O bien, puede enviar los datos de ejemplo a través del módulo [!UICONTROL HTTP] > [!UICONTROL Make a request]:

1. Cree un nuevo escenario con el módulo **[!UICONTROL HTTP]** > **[!UICONTROL Make a request]**

1. Configure el módulo con los siguientes valores:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"><p>[!UICONTROL URL] </p></td> 
      <td>Introduzca la URL del webhook. Puede encontrar esta URL en el módulo [!UICONTROL Webhooks] que utilizó para configurar el webhook.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Method] </td> 
      <td><p>[!UICONTROL POST]</p></td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Body type]</td> 
      <td><p> [!UICONTROL Raw]</p></td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Content type]</td> 
      <td><p> JSON (aplicación/json)</p></td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Request content]</td> 
      <td><p>Se esperaba un JSON sin procesar en el webhook</p></td> 
     </tr> 
    </tbody> 
   </table>

   ![Nueva configuración de escenario](/help/workfront-fusion/references/apps-and-modules/assets/new-scenario-set-up-like-this-350x446.png)

1. Abra el escenario con el módulo [!UICONTROL Webhooks] en una pestaña o ventana independiente del explorador.
1. En el módulo de webhooks, haga clic en **[!UICONTROL Redetermine data structure]**.

   No es necesario desvincular otros módulos del módulo de webhooks.

1. Cambie al escenario con el módulo [!UICONTROL HTTP] y ejecútelo.
1. Vuelva al escenario con el módulo Webhooks.

   Un mensaje &quot;[!UICONTROL Successfully determined]&quot; significa que el módulo ha determinado correctamente la estructura de datos.

   ![Determinado correctamente](/help/workfront-fusion/references/apps-and-modules/assets/successfully-determined-350x175.png)

1. Haga clic en **[!UICONTROL OK]** para guardar la estructura de datos.

   Los elementos del webhook ahora están disponibles en el panel de asignación para su uso con módulos posteriores en el escenario.

## La cola de ganchos web

Si un webhook recibe datos y no hay un escenario activo que los espere, los datos se almacenan en la cola. Una vez activado el escenario, se procesan secuencialmente todos los paquetes que esperan en la cola.

>[!IMPORTANT]
>
>Las colas de webhook se comparten entre escenarios que utilizan el mismo webhook. Si uno de los escenarios está desactivado, todos los datos entrantes se retienen en la cola.

## Formatos de datos entrantes admitidos

[!DNL Workfront Fusion] admite 3 formatos de datos entrantes: [!UICONTROL Query String], [!UICONTROL Form Data] y [!UICONTROL JSON].

[!DNL Workfront Fusion] valida todos los datos entrantes con respecto a la estructura de datos seleccionada. A continuación, según la configuración del escenario, los datos se almacenan en la cola para su procesamiento o se procesan inmediatamente.

Si alguna parte de los datos no supera la validación, [!DNL Workfront Fusion] devuelve un código de estado HTTP 400 y especifica, en el cuerpo de la respuesta HTTP, el motivo por el que los datos entrantes no superaron las comprobaciones de validación. Si la validación de los datos entrantes se realiza correctamente, Workfront Fusion devuelve el estado &quot;[!UICONTROL 200 Accepted]&quot;.

* [[!UICONTROL Query String]](#query-string)
* [[!UICONTROL Form Data]](#form-data)
* [[!UICONTROL JSON]](#json)

### [!UICONTROL Query String]

```
GET https://app.workfrontfusion.com/wh/<yourunique32characterslongstring>?name=<yourname>&job=automate
```

### [!UICONTROL Form Data]

```
POST https://app.workfrontfusion.com/wh/<yourunique32characterslongstring>

Content-Type: application/x-www-form-urlencoded

name=<yourname>&job=automate
```

#### Datos de formulario multiparte

```
POST https://app.workfrontfusion.com/wh/<yourunique32characterslongstring>


Content-Type: multipart/form-data; boundary=---generatedboundary

---generatedboundary

Content-Disposition: form-data; name="file"; filename="file.txt"


Content-Type: text/plain


Content of file.txt


---generatedboundary

Content-Disposition: form-data; name="name"

Workfront Fusion

---generatedboundary
```

Para recibir archivos codificados con `multipart/form-data`, debe configurar una estructura de datos con un campo de tipo `collection` que contenga los campos anidados `name`, `mime` y `data`. El campo `name` es un tipo `text` y contiene el nombre del archivo cargado. `mime` es un tipo `text` y contiene un archivo en formato MIME. El campo `data` es un tipo `buffer` y contiene datos binarios para el archivo que se está transfiriendo.

Para obtener más información sobre el formato MIME, consulte [Módulos MIME](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/mime.md).

### [!UICONTROL JSON]

```
POST https://app.workfrontfusion.com/wh/<yourunique32characterslongstring>

Content-Type: application/json

{"name": "Workfront Fusion", "job": "automate"}
```

>[!TIP]
>
>Si desea acceder al JSON original, habilite el paso a través de JSON al configurar el webhook.
>
>1. Haga clic en **[!UICONTROL Add]** para agregar un nuevo enlace web.
>1. Haga clic en **[!UICONTROL Show advanced settings]**.
>1. Haga clic en **[!UICONTROL JSON pass-through]**.
>

## Encabezados del webhook

Para acceder a los encabezados del webhook, habilitar encabezados de petición GET al configurar el webhook.

1. Haga clic en **[!UICONTROL Add]** para agregar un nuevo enlace web.
1. Haga clic en **[!UICONTROL Show advanced settings]**.
1. Haga clic en **[!UICONTROL Get request headers]**.

Puede extraer un valor de encabezado determinado con la combinación de las funciones `map()` y `get()`.

>[!INFO]
>
>**Ejemplo:**
>
>El ejemplo siguiente muestra una fórmula que extrae el valor del encabezado `authorization` de la matriz `Headers[]`. La fórmula se utiliza en un filtro que compara el valor extraído con el texto dado para pasar solo webhooks si hay una coincidencia.
>
>![Configurar un filtro](/help/workfront-fusion/references/apps-and-modules/assets/set-up-a-filter-350x169.png)
>
>Para obtener más información sobre cómo obtener un elemento de una matriz con una clave determinada, vea [Asignar un elemento de una matriz con una clave determinada](/help/workfront-fusion/create-scenarios/map-data/map-an-array.md#map-an-arrays-element-with-a-given-key) en el artículo Asignar una matriz.

## Respuesta a los webhooks

La respuesta predeterminada a una llamada de webhook es el texto “Aceptado”. La respuesta se devuelve a la aplicación que llamó al webhook durante la ejecución del módulo webhook personalizado.

* [Prueba de la respuesta a un webhook](#test-the-response-to-a-webhook)
* [Ejemplo de respuesta del HTML](#html-response-example)
* [Ejemplo de redireccionamiento](#redirect-example)

### Prueba de la respuesta a un webhook

1. Incluya el módulo **[!UICONTROL Custom Webhook]** en su escenario.
1. Añada un nuevo webhook al módulo.
1. Copie la URL del webhook en el portapapeles.
1. Ejecute el escenario.

   El icono del rayo en el módulo [!UICONTROL Custom Webhook] cambia a puntos giratorios. Esto muestra que el módulo está esperando la llamada del webhook.

1. Abra una nueva ventana del explorador, pegue la dirección URL copiada en la barra de direcciones y presione **[!UICONTROL Enter]**.

   El módulo [!UICONTROL Custom Webhook] se activa y el explorador mostrará una nueva página.

Si desea personalizar la respuesta del webhook, emplee el módulo Respuesta de webhook.

La configuración del módulo contiene dos campos: [!UICONTROL Status] y [!UICONTROL Body].

* El campo [!UICONTROL Status] contiene códigos de estado de respuesta HTTP como 2xx para Success (por ejemplo, `200` para OK), 3xx para Redirection (por ejemplo, `307` para Temporary Redirect), 4xx para Client errors (por ejemplo, `400` para Bad Request), etc.

* El campo [!UICONTROL Body] contiene cualquier elemento que sea aceptado por la llamada del gancho web. Puede ser texto simple, HTML, XML, JSON, etc.

  >[!TIP]
  >
  >Se recomienda establecer el encabezado de `Content-Type` en el tipo MIME correspondiente: `text/plain` para texto sin formato, `text/html` para HTML, `application/json` para JSON, `application/xml` para XML, etc. Para obtener más información sobre los tipos MIME, consulte [Módulos MIME](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/mime.md).

El tiempo de espera para enviar una respuesta es de 40 segundos. Si la respuesta no está disponible dentro de ese periodo, Workfront Fusion devuelve el estado “200 Aceptado”.

### Ejemplo de respuesta del HTML

>[!INFO]
>
>**Ejemplo:**
>
>Configure el módulo [!UICONTROL Webhook Response] de la siguiente manera:
>
><table style="table-layout:auto"> 
&gt; <col> 
&gt; <col> 
&gt; <tbody> 
&gt;  <tr> 
&gt;   <td role="rowheader">[!UICONTROL Status] </td> 
&gt;   <td> <p>Código de estado HTTP de éxito 2xx, p. ej. 200</p> </td> 
&gt;  </tr> 
&gt;  <tr> 
&gt;   <td role="rowheader">[!UICONTROL Body] </td> 
&gt;   <td> <p>Código de HTML</p> </td> 
&gt;  </tr> 
&gt;  <tr> 
&gt;   <td role="rowheader"> <p>[!UICONTROL Custom headers]</p> </td> 
&gt;   <td> 
&gt;    <ul> 
&gt;     <li><strong>Clave</strong>: Content-type</li> 
&gt;     <li><strong>Valor</strong>: text/html</li> 
&gt;    </ul> </td> 
&gt;  </tr> 
&gt; </tbody> 
&gt;</table>
>
>![Encabezados personalizados](/help/workfront-fusion/references/apps-and-modules/assets/custom-headers-350x235.png)
>
>Esto producirá una respuesta del HTML que se mostrará en un explorador web:
>
>![Respuesta HEML](/help/workfront-fusion/references/apps-and-modules/assets/html-response-350x70.png)

### Ejemplo de redireccionamiento

>[!INFO]
>
>**Ejemplo:** Configure el módulo [!UICONTROL Webhook Response] de la siguiente manera:
>
><table style="table-layout:auto"> 
&gt; <col> 
&gt; <col> 
&gt; <tbody> 
&gt;  <tr> 
&gt;   <td role="rowheader">[!UICONTROL Status] </td> 
&gt;   <td> <p>Código de estado HTTP de redirección 3xx, p. ej. 303</p> </td> 
&gt;  </tr> 
&gt;  <tr> 
&gt;   <td role="rowheader"> <p>[!UICONTROL Custom headers]</p> </td> 
&gt;   <td> 
&gt;    <ul> 
&gt;     <li><strong>[!UICONTROL Key]</strong>: Ubicación</li> 
&gt;     <li><strong>[!UICONTROL Value]</strong>: Dirección URL a la que desea redirigir el mensaje.</li> 
&gt;    </ul> </td> 
&gt;  </tr> 
&gt; </tbody> 
&gt;</table>
>
>![Respuesta de webhook](/help/workfront-fusion/references/apps-and-modules/assets/webhook-response-350x279.png)

## Desactivación de un webhook

Los webhooks se desactivan automáticamente si se aplica cualquiera de las siguientes opciones:

* El webhook no ha estado conectado a ningún escenario durante más de 5 días
* El webhook solo se utiliza en escenarios inactivos, que han estado inactivos durante más de 30 días.

Los webhooks desactivados se borran y no se registran automáticamente si no están conectados a ningún escenario y han permanecido en estado desactivado durante más de 30 días.


## Resolución de problemas

### Elementos que faltan en el panel de asignación

Si faltan algunos elementos en el panel de asignación en la configuración de los módulos que siguen al módulo [!UICONTROL Webhooks] > [!UICONTROL Custom Webhook], haga clic en el módulo **[!UICONTROL Webhooks]>[!UICONTROL Custom Webhook]** para abrir su configuración y haga clic en **[!UICONTROL Re-determine data structure]**:

![Volver a determinar la estructura de datos](/help/workfront-fusion/references/apps-and-modules/assets/redetermine-data-structure-btn-350x195.png)

A continuación, siga los pasos descritos en la sección [Configurar la estructura de datos del webhook](#configure-the-webhook-s-data-structure) en este artículo.
