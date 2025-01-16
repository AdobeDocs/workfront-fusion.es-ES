---
title: Módulo SOAP
description: SOAP SOAP Puede utilizar el módulo de la para conectarse a las API de la en Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: dbcc04f8-8306-4a81-aed8-1ce0798e145f
source-git-commit: bf9af473f08463c00578a1a8b07c800239225f09
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 16%

---

# [!UICONTROL SOAP] módulo

Puede usar el módulo [!UICONTROL SOAP] para conectarse a las API [!UICONTROL SOAP] en [!UICONTROL Adobe Workfront Fusion].

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

## Limitaciones del módulo [!UICONTROL SOAP]

>[!NOTE]
>
>Las redirecciones se desactivan durante la carga de WDSL. Esta es una función de seguridad, pero puede significar que las redirecciones no verificadas se bloquean cuando se ejecuta el módulo.

El módulo [!UICONTROL SOAP] se encuentra actualmente en la versión beta y no admite:

* Redefinir elementos
* Restricciones de dígitos de fracción
* Total de restricciones de dígitos
* Restricciones de espacio en blanco
* Varias partes en los mensajes de entrada y salida. Solo se admiten mensajes de una sola parte
* Elementos de esquema XML personalizados definidos con la ayuda de [[!UICONTROL SOAP] Codificación ](https://schemas.xmlsoap.org) esquemas y elementos.

>[!INFO]
>
>**Ejemplo:**
>  
>[!UICONTROL Workfront Fusion] no reconocería correctamente lo siguiente:
>
>```
><complexType name="ArrayOfFloat">
>     <complexContent>
>           <restriction base="soapenc:Array">
>                 <attribute ref="soapenc:arrayType"
>                       wsdl:arrayType="xsd:integer[]"/>
>           </restriction>
>     </complexContent>
></complexType>
>```
>
>Este ejemplo incluye las referencias `soapenc:Array`, `soapenc:arrayType` y `wsdl:arrayType`, que aún no son compatibles con [!UICONTROL Workfront Fusion].

## Solución

Si el módulo [!UICONTROL SOAP] se niega a procesar el archivo WSDL o genera varios errores en la configuración del módulo, puede intentar usar el módulo universal **[!UICONTROL HTTP]>[!UICONTROL Make a request]** en su lugar:

1. En [!DNL Workfront Fusion], cree un nuevo escenario.
1. Inserte el módulo **[!UICONTROL HTTP]>[!UICONTROL Make a request]** en el escenario.
1. Abra la configuración del módulo y rellene los campos siguientes:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Method]</td> 
      <td> <p>[!UICONTROL POST]</p> </td> 
     </tr> 
     <tr data-mc-conditions=""> 
      <td role="rowheader">[!UICONTROL Body type]</td> 
      <td> <p>[!UICONTROL Raw]</p> </td>
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Content type]</td> 
      <td> <p>[!UICONTROL XML (application/xml)]</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Parse response]</td> 
      <td>[!UICONTROL Enabled]</td> 
     </tr> 
    </tbody> 
   </table>

   <!--![](/help/workfront-fusion/references/apps-and-modules/assets/workaround-350x443.png)-->

1. Abra una nueva ventana o pestaña del explorador web.
1. Pegue la URL de WSDL en la barra de direcciones del explorador web y recupere el archivo XML.

   La dirección URL de WSDL suele terminar con `?wsdl`, pero no necesariamente, por ejemplo `http://voip.ms/api/v1/server.wsdl`.

1. Si el archivo WSDL no se muestra directamente en el explorador web, abra el archivo descargado en un editor de texto.
1. Busque la etiqueta `<service>` o `<wsdl:service>`:

   <!--![](/help/workfront-fusion/references/apps-and-modules/assets/service-350x65.png)-->

1. Una vez localizada, copie la dirección URL del atributo `location`.
1. En [!DNL Workfront Fusion], pegue la dirección URL en el campo URL del módulo HTTP.
1. Abra [Cliente en línea [!UICONTROL SOAP]](https://wsdlbrowser.com/) en una nueva ventana o ficha del explorador web.
1. Pegue la URL de WSDL en el campo URL de WSDL.
1. Haga clic en **[!UICONTROL Browse]**.
1. Elija de la lista de funciones a la izquierda, por ejemplo `getLanguages`.
1. Copie el contenido del área de texto [!UICONTROL Request XML].
1. En [!UICONTROL Workfront Fusion], pegue el contenido copiado en el campo URL del módulo.
1. Proporcione valores para los parámetros seleccionados reemplazando los signos de interrogación por valores reales:

   <!--![](/help/workfront-fusion/references/apps-and-modules/assets/request-xml-350x172.png)-->

1. Cierre la configuración del módulo haciendo clic en **[!UICONTROL OK]**.
1. Ejecute el escenario o módulo.
