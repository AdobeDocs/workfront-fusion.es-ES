---
title: Control de flujo
description: Al crear o editar un escenario, es posible configurar opciones para controlar el modo en que los datos fluirán a través de el.
author: Becky
feature: Workfront Fusion
exl-id: b3aed366-c399-44fa-8967-54ecb8647d96
source-git-commit: ce2f13866fef97b5687991dfcf5d9579a5e539e4
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 50%

---

# Control de flujo

Al crear o editar un escenario, es posible configurar opciones para controlar el modo en que los datos fluirán a través de el.

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
   <p>Requisito de licencia heredado: [!UICONTROL [!DNL Workfront Fusion] para automatización e integración de trabajo, [!UICONTROL [!DNL Workfront Fusion] para automatización de trabajo</p>
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

Para obtener información sobre las licencias de [!DNL Adobe Workfront Fusion], consulte Licencias de [[!DNL Adobe Workfront Fusion] ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## Repetidor

Puede usar un módulo [!UICONTROL Repeater] para repetir una tarea un número determinado de veces. Un módulo [!UICONTROL Repeater] genera paquetes uno tras otro.

Por ejemplo, podría utilizar un módulo [!UICONTROL Repeater] para enviar cinco correos electrónicos con los temas &quot;Hello 1&quot;, &quot;Hello 2&quot;, etc., conectando el módulo **[!UICONTROL Email]>[!UICONTROL Send me an email]** al módulo [!UICONTROL Repeater].

Para usar un módulo [!UICONTROL Repeater]:

1. Haga clic en el icono [!UICONTROL Flow Control] ![](/help/workfront-fusion/references/apps-and-modules/assets/flow-control-icon.gif) en la parte inferior de la pantalla y, a continuación, haga clic en **[!UICONTROL Repeater]** en el menú que se muestra.
1. Haga clic en el paquete [!UICONTROL Repeater] y, a continuación, haga clic en **[!UICONTROL Connect automatically]** en el cuadro que se muestra.
1. En el cuadro [!UICONTROL Flow Control] que aparece, escriba el número de repeticiones (paquetes generados) que desee en el cuadro **[!UICONTROL Repeats]**.

   En el ejemplo de correo electrónico, debe escribir 5.

   ![](/help/workfront-fusion/references/apps-and-modules/assets/repeater-2-350x207.png)

   El valor del elemento aumenta en cada repetición según este valor especificado en el campo **[!UICONTROL Step]**, que puede ver seleccionando **[!UICONTROL Show advanced settings]**. Este número se establece en 1 de forma predeterminada.

1. Haga clic en **[!UICONTROL OK]** para cerrar el cuadro **[!UICONTROL Flow Control]**.

1. Haga clic en la aplicación o el módulo de servicio conectado al módulo [!UICONTROL Repeater].
1. En el cuadro que aparecerá, escriba la información que quiera repetir.

   En nuestro ejemplo de correo electrónico, escribiría Hello en el cuadro [!UICONTROL Subject] y, a continuación, asignaría `i` desde el módulo de repetición.

   ![](/help/workfront-fusion/references/apps-and-modules/assets/repeater-3-350x207.png)

| Elemento | Descripción |
|---|---|
| [!UICONTROL Initial value] | Escriba o asigne el número que quiera que el módulo establezca como `i` en la primera iteración. El valor predeterminado es 1. |
| [!UICONTROL Repeats] | Introduzca o asigne el número de veces que quiera que el módulo se repita. Este número debe ser mayor o igual que 0, y menor o igual que 10 000. |
| [!UICONTROL Step] | Es el número por el que el módulo aumenta el valor de `i`. El valor predeterminado es 1. |

{style="table-layout:auto"}

>[!NOTE]
>
>El número de repeticiones no está determinado por el valor de `i`, ya que sería un bucle en la programación. El módulo repetirá la cantidad de veces indicada en el campo [!UICONTROL Repeats]. El valor de `i` cambia con cada iteración del módulo [!DNL repeater] y se puede asignar a módulos posteriores. El ejemplo anterior asigna el valor de `i` al mensaje Hola, lo que da como resultado mensajes que dicen “Hola 1”, “Hola 2”, etc.

## [!UICONTROL Iterator]

Un [!UICONTROL Iterator] es un tipo especial de módulo que convierte una matriz en una serie de paquetes. Cada elemento de matriz será un paquete independiente en la salida del módulo [!UICONTROL Iterator]. Para obtener más información, consulte [Módulo iterador](/help/workfront-fusion/references/modules/iterator-module.md).

## Agregador de matrices

Un agregador de matrices es un tipo especial de módulo que permite combinar varios paquetes en uno solo. Para obtener más información, consulte [Módulo de agregado](/help/workfront-fusion/references/modules/aggregator-module.md).

## [!UICONTROL Router]

El módulo [!UICONTROL Router] le permite bifurcar el flujo en varias rutas y procesar los datos de cada ruta de forma diferente. Una vez que un módulo [!UICONTROL Router] recibe un paquete, lo reenvía a cada ruta conectada en el orden en que se adjuntaron las rutas al módulo [!UICONTROL Router]. Para obtener más información, consulte [Módulo Enrutador en [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/create-scenarios/add-modules/router-module.md).

<!--
<div>
<h2>Directives</h2>
<p>The error handling directives allow you to control how your scenario reacts to errors. For more information, see <a href="/help/workfront-fusion/create-scenarios/config-error-handling/advanced-error-handling.md" class="MCXref xref">Advanced error handling in Adobe Workfront Fusion</a> and <a href="/help/workfront-fusion/references/errors/directives-for-error-handling.md" class="MCXref xref">Directives for error handling in Adobe Workfront Fusion</a>.</p>
</div>
-->
