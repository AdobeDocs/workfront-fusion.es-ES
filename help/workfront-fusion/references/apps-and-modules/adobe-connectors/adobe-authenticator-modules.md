---
title: módulo de Adobe Authenticator
description: Con el módulo Adobe Authenticator, puede conectarse a cualquier producto de Adobe con una API mediante una sola conexión.
author: Becky
feature: Workfront Fusion
exl-id: af4da661-eeee-4033-a2bb-a2196e446a3d
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1118'
ht-degree: 75%

---

# Módulos de Adobe Authenticator

El módulo Adobe Authenticator le permite conectarse a cualquier API de Adobe mediante una sola conexión. Esto le permite conectarse más fácilmente a los productos de Adobe que aún no tienen un conector Fusion específico.

La ventaja sobre los módulos HTTP es que se puede crear una conexión, como en una aplicación específica.

Para ver una lista de las API de Adobe disponibles, consulte [API de Adobe](https://developer.adobe.com/apis). Es posible que solo pueda utilizar las API que le han sido asignadas.

## Requisitos de acceso

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] paquete</td>
      <td>
        <p>Nuevo: cualquiera</p><p>O</p><p>Actual: [!UICONTROL Pro] o superior</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] licencia</td>
      <td>
        <p>Nuevo: estándar</p><p>O</p><p>Actual: [!UICONTROL Plan], [!UICONTROL Work]</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront Fusion] licencia</td>
      <td>
   <p>Requisito de licencia de Fusion actual: no se requiere licencia de [!DNL Workfront Fusion].</p>
   <p>O</p>
   <p>Requisito de licencia de Fusion heredada: [!UICONTROL [!DNL Workfront Fusion] para automatización e integración de trabajo </p>
   </td>
    </tr>
    <tr>
      <td role="rowheader">Producto</td>
      <td>
   <p>Nuevo plan de Workfront: si tiene el plan [!UICONTROL Select] o [!UICONTROL Prime] [!DNL Adobe Workfront], su organización debe adquirir [!DNL Adobe Workfront Fusion] y [!DNL Adobe Workfront] para usar la funcionalidad descrita en este artículo. [!DNL Workfront Fusion] está incluido en el plan [!UICONTROL Ultimate] [!DNL Workfront].</p>
   <p>O</p>
   <p>Plan actual de Workfront: su organización debe adquirir [!DNL Adobe Workfront Fusion] y [!DNL Adobe Workfront] para poder usar la funcionalidad descrita en este artículo.</p>
   </td>
    </tr>
  </tbody>
</table>

## Requisitos previos

* Debe tener acceso al producto de Adobe al que desea que se conecte el módulo.
* Debe tener acceso a Adobe Developer Console.
* Debe tener un proyecto en Adobe Developer Console que incluya la API a la que desea que se conecte el módulo. Puede:

   * Crear un nuevo proyecto con la API.

     O
   * Añadir la API a un proyecto existente.

  Para obtener información sobre cómo crear o añadir una API a un proyecto en Adobe Developer Console, consulte [Crear un proyecto](https://developer.adobe.com/dep/guides/dev-console/create-project/) en la documentación de Adobe.

## Información de API de Adobe Authenticator

El conector de Adobe Authenticator utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.1.4</td> 
  </tr>
 </tbody> 
 </table>

## Crear una conexión

Una conexión de Adobe Authenticator se conecta a un solo proyecto en Adobe Developer Console. Para utilizar la misma conexión para más de una API de Adobe, añada las API al mismo proyecto y cree una conexión con ese proyecto.

Puede crear conexiones independientes a proyectos independientes, pero no puede utilizar una conexión para acceder a una API que no esté en el proyecto especificado en esa conexión.

>[!IMPORTANT]
>
>Con el conector de Adobe Authenticator, puede elegir entre realizar una conexión de servidor a servidor OAuth o una conexión de cuenta de servicio (JWT). Adobe tiene credenciales de JWT obsoletas, que dejarán de funcionar el 1 de enero de 2025. **Por lo tanto, recomendamos encarecidamente la creación de conexiones de OAuth.**
>
>Para obtener más información sobre estos tipos de conexiones, consulte [Autenticación de servidor a servidor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/) en la documentación de Adobe.

Para crear una conexión:

1. En cualquier módulo de Adobe Authenticator, haga clic en **Añadir** junto al campo Conexión.
1. Rellene los campos siguientes:

   <table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL Connection type]</td>
        <td>
          <p>Seleccione si desea crear una conexión de servidor a servidor OAuth o una conexión de cuenta de servicio (JWT).</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>Introduzca un nombre para esta conexión.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Escriba su ID de cliente de [!DNL Adobe]. Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Escriba su secreto de cliente de [!DNL Adobe]. Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Scopes]</td>
        <td>Si ha seleccionado una conexión OAuth, introduzca los ámbitos necesarios para esta conexión.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Technical account ID]</td>
        <td>Escriba su ID de cuenta técnica de [!DNL Adobe]. Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Organization ID]</td>
        <td>Si ha seleccionado una conexión JWT, introduzca su ID de organización de [!DNL Adobe]. Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Meta Scopes]</td>
        <td>Si ha seleccionado una conexión JWT, introduzca los metaámbitos necesarios para esta conexión. </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Private key]</td>
        <td>
          <p>Si ha seleccionado una conexión JWT, introduzca la clave privada que se generó cuando se crearon sus credenciales en [!DNL Adobe Developer Console]. </p>
          <p>Para extraer la clave privada o el certificado:</p>
          <ol>
            <li value="1">
              <p>Haga clic en <b>[!UICONTROL Extract]</b>.</p>
            </li>
            <li value="2">
              <p>Seleccione el tipo de archivo que va a extraer.</p>
            </li>
            <li value="3">
              <p>Seleccione el archivo que contiene la clave privada o el certificado.</p>
            </li>
            <li value="4">
              <p>Introduzca la contraseña del archivo.</p>
            </li>
            <li value="5">
              <p>Haga clic en <b>[!UICONTROL Save]</b> para extraer el archivo y volver a la configuración de conexión.</p>
            </li>
          </ol>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Base URLs]</td>
        <td>Debe añadir las direcciones URL base que desea que permita este autenticador. Cuando utilice el módulo Crear una llamada de API personalizada más adelante en el escenario, añadirá una ruta relativa a la dirección URL elegida. Al introducir las direcciones URL aquí, puede controlar a qué se puede conectar el módulo Crear una llamada de API personalizada, lo que aumenta la seguridad.<p>Para cada URL base que desee añadir al autenticador, haga clic en <b>Agregar elemento</b> e introduzca la URL base.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Authentication URL]</td>
        <td>Deje esto en blanco para usar la URL de autenticación estándar IMS de Adobe de <code>https://ims-na1.adobelogin.com</code>. Si no utiliza Adobe IMS para la autenticación, introduzca la URL que desea utilizar para la autenticación.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>Seleccione si desea conectarse a un entorno de producción o de no producción.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>Seleccione si desea conectarse a una cuenta de servicio o a una personal.</td>
      </tr>
    </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continue]** para guardar la conexión y volver al módulo.

## Módulos

* [Realizar una llamada de API personalizada](#make-a-custom-api-call)
* [Realizar una llamada de API personalizada (heredada)](#make-a-custom-api-call-legacy)

### Realizar una llamada de API personalizada

Este módulo de acción le permite realizar una llamada a cualquier API de Adobe. Admite archivos grandes, en lugar de cuerpos de solo texto.

Este módulo estuvo disponible el 14 de noviembre de 2024. Cualquier Adobe Authenticator > Realizar una llamada API personalizada configurada antes de esta fecha no gestiona archivos grandes y ahora se considera el módulo Realizar una llamada API personalizada (heredada).

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
     <td role="rowheader">[!UICONTROL Connection]</td>
     <td>Para obtener instrucciones sobre cómo crear una conexión con el módulo Adobe Authenticator, consulte <a href="#create-a-connection" class="MCXref xref" >Crear una conexión</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Base URL]</p>
      </td>
      <td>
        <p>Introduzca la dirección URL base del punto de API al que desea conectarse.</p>
      </td>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL URL]</p>
      </td>
      <td>
        <p>Introduzca la ruta relativa a la dirección URL base.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de petición HTTP en [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p>
        <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion añade encabezados de autorización automáticamente.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Query String]  </td>
      <td>
        <p>Introduzca la cadena de consulta de la solicitud.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Body Type]</td>
   <td> Seleccione el tipo de cuerpo para esta solicitud de API:
   <ul>
   <li>application/x-www-form-urlencoded</li>
   <li>Sin procesar</li>
   <li>multipart/form-data</li>
   </ul>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Fields]  </td>
      <td>
        <p>Para cada archivo que desee agregar a la solicitud de APU, haga clic en <b>Agregar elemento</b> e introduzca el texto del archivo (para datos sin procesar), o bien escriba la clave <code>uploadedFile</code> y asigne los datos del archivo.</p>
      </td>
    </tr>
    </tr>
  </tbody>
</table>

### Realizar una llamada de API personalizada (heredada)

Este módulo de acción le permite realizar una llamada a cualquier API de Adobe.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
     <td role="rowheader">[!UICONTROL Connection]</td>
     <td>Para obtener instrucciones sobre cómo crear una conexión con el módulo Adobe Authenticator, consulte <a href="#create-a-connection" class="MCXref xref" >Crear una conexión</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Base URL]</p>
      </td>
      <td>
        <p>Introduzca la dirección URL base del punto de API al que desea conectarse.</p>
      </td>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL URL]</p>
      </td>
      <td>
        <p>Introduzca la ruta relativa a la dirección URL base.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de petición HTTP en [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p>
        <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion añade encabezados de autorización automáticamente.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Query String]  </td>
      <td>
        <p>Introduzca la cadena de consulta de la solicitud.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Body]</td>
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"></p> 
     </div> </p> </td>     </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Limit]  </td>
      <td>
        <p>Introduzca el número máximo de resultados que desea que devuelva el módulo en un ciclo de ejecución.</p>
      </td>
    </tr>
  </tbody>
</table>
