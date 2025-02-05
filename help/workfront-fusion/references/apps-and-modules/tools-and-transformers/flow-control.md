---
title: Control de flujo
description: Al crear o editar un escenario, es posible configurar opciones para controlar el modo en que los datos fluirán a través de el.
author: Becky
feature: Workfront Fusion
exl-id: b3aed366-c399-44fa-8967-54ecb8647d96
source-git-commit: 5a95b2c191d4e6d8750dc57a47923f416612b4a9
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 39%

---

# Control de flujo

Al crear o editar un escenario, es posible configurar opciones para controlar el modo en que los datos fluirán a través de el.

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
   <p>No se requiere licencia de Workfront Fusion.</p>
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

Para obtener información sobre las licencias de [!DNL Adobe Workfront Fusion], consulte Licencias de [[!DNL Adobe Workfront Fusion] ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Repetidor

Puede usar un módulo [!UICONTROL Repeater] para repetir una tarea un número determinado de veces. Un módulo [!UICONTROL Repeater] genera paquetes uno tras otro.


<table>
    <tr>
        <td>[!UICONTROL Initial value]</td>
        <td>Introduzca o asigne el valor que desea que tenga el módulo en la primera iteración. El valor predeterminado es 1.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Repeats]</td>
        <td>Introduzca o asigne el número de veces que quiera que el módulo se repita. Este número debe ser mayor o igual que 0, y menor o igual que 10 000.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Step]</td>
        <td>Es el número en el que el módulo aumenta el valor. El valor predeterminado es 1.</td>
    </tr>
</table>

>[!BEGINSHADEBOX]

Por ejemplo, podría utilizar un módulo [!UICONTROL Repeater] para enviar cinco correos electrónicos con los temas &quot;Hello 1&quot;, &quot;Hello 2&quot;, etc., conectando el módulo **[!UICONTROL Email]>[!UICONTROL Send me an email]** al módulo [!UICONTROL Repeater].

1. Haga clic en el icono [!UICONTROL Flow Control] ![icono de control de flujo](/help/workfront-fusion/references/apps-and-modules/assets/flow-control-icon.gif) en la parte inferior de la pantalla y, a continuación, haga clic en **[!UICONTROL Repeater]** en el menú que se muestra.
1. Haga clic en el módulo [!UICONTROL Repeater] y, a continuación, haga clic en **[!UICONTROL Connect automatically]** en el cuadro que se muestra.

   Se abrirá el módulo Repetidor.

1. En el campo **[!UICONTROL Repeats]**, introduzca el número de repeticiones (paquetes generados) que desea que produzca el módulo.

   En este ejemplo, debe introducir 5.

   ![Repetidor](/help/workfront-fusion/references/apps-and-modules/assets/repeater-2-350x207.png)

   El valor del elemento aumenta en cada repetición según este valor especificado en el campo **[!UICONTROL Step]**, que puede ver seleccionando **[!UICONTROL Show advanced settings]**. Este número se establece en 1 de forma predeterminada.

1. Haga clic en **[!UICONTROL OK]** para cerrar el cuadro **[!UICONTROL Flow Control]**.

1. Haga clic en la aplicación o el módulo de servicio conectado al módulo [!UICONTROL Repeater].
1. En el cuadro que aparecerá, escriba la información que quiera repetir.

   En nuestro ejemplo de correo electrónico, escribiría Hello en el cuadro [!UICONTROL Subject] y, a continuación, asignaría `i` desde el módulo de repetición.

   ![Repetidor](/help/workfront-fusion/references/apps-and-modules/assets/repeater-3-350x207.png)



>[!NOTE]
>
>El número de repeticiones no está determinado por el valor de `i`, ya que sería un bucle en la programación. El módulo repetirá la cantidad de veces indicada en el campo [!UICONTROL Repeats]. El valor de `i` cambia con cada iteración del módulo [!DNL repeater] y se puede asignar a módulos posteriores. El ejemplo anterior asigna el valor de `i` al mensaje Hola, lo que da como resultado mensajes que dicen “Hola 1”, “Hola 2”, etc.

>[!ENDSHADEBOX]

## [!UICONTROL Iterator]

Un [!UICONTROL Iterator] es un tipo especial de módulo que convierte una matriz en una serie de paquetes. Cada elemento de matriz será un paquete independiente en la salida del módulo [!UICONTROL Iterator]. Para obtener más información, consulte [Módulo iterador](/help/workfront-fusion/references/modules/iterator-module.md).

## Agregador de matrices

Un agregador de matrices es un tipo especial de módulo que permite combinar varios paquetes en uno solo. Para obtener más información, consulte [Módulo de agregado](/help/workfront-fusion/references/modules/aggregator-module.md).

## [!UICONTROL Router]

El módulo [!UICONTROL Router] le permite bifurcar el flujo en varias rutas y procesar los datos de cada ruta de forma diferente. Una vez que un módulo [!UICONTROL Router] recibe un paquete, lo reenvía a cada ruta conectada en el orden en que se adjuntaron las rutas al módulo [!UICONTROL Router]. Para obtener más información, consulte [Módulo Enrutador en [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/create-scenarios/add-modules/router-module.md).

## Directivas

Las directivas de gestión de errores permiten controlar cómo reacciona el escenario a los errores.

Para obtener información acerca de las directivas de control de errores, consulte [Directivas de control de errores](/help/workfront-fusion/references/errors/directives-for-error-handling.md).

