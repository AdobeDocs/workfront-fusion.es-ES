---
title: Módulos de Adobe Experience Manager Forms
description: Con el conector  [!DNL Adobe Experience Manager Forms] para Adobe Workfront Fusion, puedes iniciar un escenario basado en eventos en tu cuenta de  [!DNL Adobe Experience Manager Forms] y crear, cargar y actualizar recursos, y copiar o mover carpetas y recursos.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: e0d7a655-1353-4d24-83d4-7da73d859a63
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 68%

---

# Módulos de [!DNL Adobe Experience Manager Forms]

Con el conector [!DNL Adobe Experience Manager Forms] para Adobe Workfront Fusion, puede iniciar un escenario basado en eventos en su cuenta de [!DNL Adobe Experience Manager Forms] creando un webhook.

Puede configurar un formulario dentro de [!DNL Adobe Experience Manager Forms] para enviar envíos de formularios a este webhook.

## Requisitos de acceso

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Plan de Adobe Workfront*</td>
  <td> <p>[!UICONTROL Pro] o superior</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencia de Adobe Workfront*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion**</td> 
   <td>
   <p>Requisito de licencia actual: no se requiere licencia de Workfront Fusion.</p>
   <p>O</p>
   <p>Requisito de licencia heredado: [!UICONTROL Workfront Fusion para automatización e integración de trabajo] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Requisito actual del producto: si tiene el plan de Adobe Workfront de [!UICONTROL Select] o [!UICONTROL Prime], su organización debe adquirir Adobe Workfront Fusion y Adobe Workfront para utilizar la funcionalidad que se describe en este artículo. Workfront Fusion está incluido en el plan de Workfront de [!UICONTROL Ultimate].</p>
   <p>O</p>
   <p>Requisito de productos heredados: su organización debe adquirir Adobe Workfront Fusion así como Adobe Workfront para utilizar la funcionalidad descrita en este artículo.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Para saber qué plan, tipo de licencia o acceso tiene, póngase en contacto con el administrador de Workfront.

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## Requisitos previos

* Debe tener una cuenta de [!DNL Adobe Experience Manager Forms] para utilizar este módulo.

## Información de API de Adobe Experience Manager Assets

El conector de Adobe Experience Manager Assets utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.2.27</td> 
  </tr>
 </tbody> 
 </table>

## Creación de una conexión a Adobe Experience Manager Forms

Para crear una conexión para los módulos de [!DNL Adobe Experience Manager Forms]:

1. En cualquier módulo, haga clic en **[!UICONTROL Agregar]** junto al cuadro Conexión.

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
        <td>
          <p>Seleccione si esta conexión se conecta a un entorno de producción o de no producción.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>
          <p>Seleccione si esta cuenta es una cuenta de servicio o una cuenta personal.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Instance URL without a trailing slash]</td>
        <td>
          <p>Introduzca la URL que utiliza para acceder a la cuenta, sin la barra final.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL IMS endpoint]</td>
        <td>
          <p><code>https://ims-na1.adobelogin.com</code></p>
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
        <td role="rowheader">[!UICONTROL Org ID]</td>
        <td>Introduzca el ID de organización de [!DNL Adobe]. Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Technical account ID]</td>
        <td>Escriba su ID de cuenta técnica de [!DNL Adobe]. Esto se puede encontrar en la sección [!UICONTROL Credentials details] de [!DNL Adobe Developer Console].
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Meta Scopes]</td>
        <td>Introducir los metaámbitos adecuados       </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Private key]</td>
        <td>
          <p>Introduzca la clave privada que se generó cuando se crearon sus credenciales en [!DNL Adobe Developer Console]. </p>
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
    </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continue]** para guardar la conexión y volver al módulo.

## Módulo Adobe Experience Manager Forms y sus campos

Actualmente, solo hay un módulo en el conector de Adobe Experience Manager Forms.

### Observar eventos de formulario

Este activador instantáneo (webhook) permite iniciar un escenario cuando se produce una acción de envío en un formulario de Adobe Experience Manager Forms.

>[!IMPORTANT]
>
>Este módulo también requiere configuración en Adobe Experience Manager. Después de configurar este webhook, debe abrir Adobe Experience Manager y configurar el formulario para realizar envíos al webhook.
>
><!--For instructions on the required form configuration, see insert url here-->

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name]</td> 
   <td> <p>Introducir un nombre para el webhook</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Adobe Experience Manager] a Workfront Fusion, consulte <a href="/help/workfront-fusion/references/apps-and-modules/adobe-connectors/aem-forms-modules.md#create-a-connection-to-adobe-experience-manager-forms" class="MCXref xref">Crear una conexión con [!DNL Adobe Experience Manager Forms]</a></p> </td> 
  </tr>

El módulo creará un webhook y le proporcionará la dirección del webhook, que podrá introducir en el diálogo de envío del formulario en [!DNL Adobe Experience Manager Forms].
