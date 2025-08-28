---
title: Módulo SOAP
description: Puede utilizar el módulo de SOAP para conectarse a las API de SOAP en Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: dbcc04f8-8306-4a81-aed8-1ce0798e145f
source-git-commit: 95d52f8227c8a40c0db165eea9d2877e60446de9
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 15%

---

# módulo [!UICONTROL SOAP]

Puede usar el módulo [!UICONTROL SOAP] para conectarse a las API de [!UICONTROL SOAP] en [!UICONTROL Adobe Workfront Fusion].

## Módulo SOAP y sus campos

El conector de SOAP solo incluye un módulo, Ejecutar acción de SOAP

### Ejecutar acción de SOAP

Este módulo de acción ejecuta la acción especificada de SOAP.



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
   <p>Actual: No se requiere licencia de Workfront Fusion</p>
   <p>O</p>
   <p>Heredado: Workfront Fusion para la automatización e integración del trabajo </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Seleccione o paquete de Prime Workfront: su organización debe adquirir Adobe Workfront Fusion.</li><li>Paquete de Ultimate Workfront: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe comprar Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Módulo SOAP y sus campos

Al configurar los módulos de SOAP, Workfront Fusion muestra los campos que se indican a continuación.  El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Ejecutar acción de SOAP

Este módulo de acción ejecuta una acción de SOAP basada en el WSDL especificado.

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL WSDL]</td> 
   <td> Seleccione el WSDL que desea que utilice el módulo. Para crear un WSDL, haga clic en <b>Agregar</b> junto al campo y rellene los campos. </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Encabezados HTTP]</td> 
   <td> Para cada encabezado HTTP que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca el nombre y valor del encabezado.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Encabezados de SOAP]</td> 
   <td> Para cada encabezado de SOAP que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca el nombre, valor, área de nombres y XMLNS del encabezado.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Forzar encabezados SOAP]</td> 
   <td> Active esta opción para configurar los encabezados de SOAP 1.2. </td> 
  </tr> 
  </tbody> 
</table>

## Limitaciones del módulo [!UICONTROL SOAP]

>[!NOTE]
>
>Las redirecciones se desactivan durante la carga de WDSL. Esta es una función de seguridad, pero puede significar que las redirecciones no verificadas se bloquean cuando se ejecuta el módulo.

El módulo [!UICONTROL SOAP] está actualmente en fase beta y no admite:

* Redefinir elementos
* Restricciones de dígitos de fracción
* Total de restricciones de dígitos
* Restricciones de espacio en blanco
* Varias partes en los mensajes de entrada y salida. Solo se admiten mensajes de una sola parte
* Elementos de esquema XML personalizados definidos con la ayuda de esquemas y elementos de SOAP Encoding.

>[!BEGINSHADEBOX]

**Ejemplo:**

[!UICONTROL Workfront Fusion] no reconocería correctamente lo siguiente:

```
<complexType name="ArrayOfFloat">
   <complexContent>
      <restriction base="soapenc:Array">
         <attribute ref="soapenc:arrayType"
            wsdl:arrayType="xsd:integer[]"/>
      </restriction>
   </complexContent>
</complexType>
```

Este ejemplo incluye las referencias `soapenc:Array`, `soapenc:arrayType` y `wsdl:arrayType`, que aún no son compatibles con [!UICONTROL Workfront Fusion].

>[!ENDSHADEBOX]

## Solución

Si el módulo [!UICONTROL SOAP] se niega a procesar el archivo WSDL o genera varios errores en la configuración del módulo, puede intentar usar el módulo universal **[!UICONTROL HTTP] > [!UICONTROL Realizar una solicitud]** en su lugar:

1. En Workfront Fusion, cree un nuevo escenario.
1. Inserte el módulo **[!UICONTROL HTTP] > [!UICONTROL Realice una solicitud]** en el escenario.
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
      <td>[!UICONTROL Habilitado]</td> 
     </tr> 
    </tbody> 
   </table>

   <!--![Workaround](/help/workfront-fusion/references/apps-and-modules/assets/workaround-350x443.png)-->

1. Abra una nueva ventana o pestaña del explorador web.
1. Pegue la URL de WSDL en la barra de direcciones del explorador web y recupere el archivo XML.

   La dirección URL de WSDL suele terminar con `?wsdl`, pero no necesariamente, por ejemplo `http://voip.ms/api/v1/server.wsdl`.

1. Si el archivo WSDL no se muestra directamente en el explorador web, abra el archivo descargado en un editor de texto.
1. Busque la etiqueta `<service>` o `<wsdl:service>`:

   <!--![Service](/help/workfront-fusion/references/apps-and-modules/assets/service-350x65.png)-->

1. Una vez localizada, copie la dirección URL del atributo `location`.
1. En Workfront Fusion, pegue la dirección URL en el campo URL del módulo HTTP.
1. Proporcione valores para los parámetros seleccionados reemplazando los signos de interrogación por valores reales.

   >[!NOTE]
   >
   > Para obtener valores específicos del archivo WSDL, utilice un visualizador WSDL en línea.

   <!--![Request](/help/workfront-fusion/references/apps-and-modules/assets/request-xml-350x172.png)-->

1. Cierre la configuración del módulo haciendo clic en **[!UICONTROL Aceptar]**.
1. Ejecute el escenario o módulo.
