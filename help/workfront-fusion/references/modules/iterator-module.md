---
title: Módulo Iterator
description: Un módulo de iterador es un tipo especial de módulo que convierte una matriz en una serie de paquetes. Cada elemento de matriz se presenta como un paquete independiente.
author: Becky
feature: Workfront Fusion
exl-id: 43d39955-3dd7-453d-8eb0-3253a768e114
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 28%

---

# Módulo [!UICONTROL Iterator]

Un [!UICONTROL Iterator] es un tipo de módulo que convierte una matriz en una serie de paquetes. Cada elemento de matriz se presenta como un paquete independiente.

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
   <td> Nuevo: estándar<p>O</p><p>Actual: Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de [!UICONTROL Adobe Workfront Fusion]</td> 
   <td>
   <p>Actual: no se requiere licencia de Workfront Fusion.</p>
   <p>O</p>
   <p>Heredado: cualquiera </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Plan de Workfront de [!UICONTROL Select] o [!UICONTROL Prime]: su organización debe adquirir Adobe Workfront Fusion.</li><li>Plan de Workfront de [!UICONTROL Ultimate]: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe comprar Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>


Para saber qué plan, tipo de licencia o acceso tiene, póngase en contacto con el administrador de Workfront.

Para obtener más información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Configuración del módulo [!UICONTROL del iterador]

El módulo Iterator general tiene un solo campo, [!UICONTROL Matriz]. Este campo contiene la matriz que se va a convertir o dividir en paquetes independientes.

![Configurar iterador](assets/set-up-iterator.jpg)

Otros conectores pueden incluir módulos de iterador específicos de ese iterador. Contienen un campo de módulo de Source, que le permite seleccionar el módulo que genera la matriz que desea repetir.

![Iteradores especializados](assets/specialized-iterators.jpg)

Para obtener más información, consulte [Configurar un módulo](/help/workfront-fusion/create-scenarios/add-modules/configure-a-modules-settings.md).

>[!BEGINSHADEBOX]

**Ejemplos**

* El siguiente escenario muestra cómo recuperar correos electrónicos con archivos adjuntos y guardarlos como archivos únicos en una carpeta [!DNL Dropbox] seleccionada.

  Los correos electrónicos pueden contener una matriz de archivos adjuntos. El módulo [!UICONTROL Iterator] después del primer módulo permite que el escenario gestione cada archivo adjunto por separado. El módulo [!UICONTROL del iterador] divide la matriz de archivos adjuntos en paquetes únicos. Cada paquete, con un archivo adjunto, se guarda de uno en uno en una carpeta [!DNL Dropbox] seleccionada. El campo [!UICONTROL Matriz] del módulo Iterator debe contener la matriz `Attachments`.

  ![Matriz de archivos adjuntos](assets/attachments-array.jpg)

>[!ENDSHADEBOX]


## Resolución de problemas

### Problema: El panel de asignación no muestra elementos asignables en el módulo [!UICONTROL Iterator]

Cuando un módulo [!UICONTROL Iterator] no tiene información sobre la estructura de los elementos de la matriz, el panel de asignación de los módulos que siguen al módulo [!UICONTROL Iterator] muestra solo dos elementos bajo el módulo [!UICONTROL Iterator]: `Total number of bundles` y `Bundle order position`.

![El panel de asignación no se muestra](assets/mapping-panel-doesnt-display.png)

Esto se debe a que cada módulo es responsable de proporcionar información sobre los elementos que genera, de modo que estos elementos se puedan mostrar correctamente en el panel de asignación en los módulos posteriores. Sin embargo, es posible que varios módulos no puedan proporcionar esta información en algunos casos. Por ejemplo, los módulos de [!UICONTROL JSON] > [!UICONTROL Analizar JSON] o [!UICONTROL Webhooks] > [!UICONTROL Webhook personalizado] a los que les falta estructura de datos no proporcionarían la información.

#### Solución

La solución es ejecutar manualmente el escenario. Esto fuerza al módulo a crear una salida. Fusion puede aplicar el formato de esta salida a módulos posteriores en el escenario.

Por ejemplo, un escenario incluye un módulo [!UICONTROL JSON] > [!UICONTROL Analizar JSON] sin una estructura de datos.

![Analizar JSON](assets/json-parse-json.png)

Un módulo [!UICONTROL Iterator] conectado a este módulo JSON no puede asignar la salida del módulo al campo Array en el panel de configuración del módulo [!UICONTROL Iterator].

![Conectar módulo de iterador](assets/connect-iterator-module.png)

Para resolver esto:

Inicie manualmente el escenario en el editor de escenarios.

>[!NOTE]
>
>Para evitar que se ejecute todo el escenario, puede:
>
>* Desvincule los módulos después del módulo [!UICONTROL JSON] > [!UICONTROL Analice el JSON] para evitar que el flujo continúe.
>  &#x200B;>   O
>* Haga clic con el botón derecho en el módulo [!UICONTROL JSON] > [!UICONTROL Analizar JSON] y elija **[!UICONTROL Ejecutar este módulo solo]** del menú contextual para ejecutar solo el módulo [!UICONTROL JSON] > [!UICONTROL Analizar JSON].

Después de ejecutar [!UICONTROL JSON] > [!UICONTROL Analizar JSON], puede proporcionar información sobre sus resultados a todos los módulos subsiguientes, incluido el módulo Iterator. A continuación, el panel de asignación de la configuración del iterador muestra los elementos siguientes:

![El panel de asignación muestra elementos](assets/mapping-panel-displays-items.png)

además, el panel de asignación de los módulos conectados después del módulo [!UICONTROL Iterator] muestra los elementos contenidos en la matriz:

![Elementos contenidos en la matriz](assets/items-contained-in-array.png)
