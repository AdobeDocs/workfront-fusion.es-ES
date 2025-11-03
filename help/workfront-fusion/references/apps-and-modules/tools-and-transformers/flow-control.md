---
title: Control de flujo
description: Al crear o editar un escenario, es posible configurar opciones para controlar el modo en que los datos fluirán a través de el.
author: Becky
feature: Workfront Fusion
exl-id: b3aed366-c399-44fa-8967-54ecb8647d96
source-git-commit: 4697ea1449f77ddb8648658990098b3b4bc58ad2
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 65%

---

# Control de flujo

Al crear o editar un escenario, es posible configurar opciones para controlar el modo en que los datos fluirán a través de el.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront</td> 
   <td> <p>Cualquier paquete de flujo de trabajo de Adobe Workfront y cualquier paquete de integración y automatización de Adobe Workfront</p><p>Workfront Ultimate</p><p>Paquetes Workfront Prime y Select, con una compra adicional de Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencias de Adobe Workfront</td> 
   <td> <p>Estándar</p><p>Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete Select o Prime Workfront que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++



## Repetidor

Use un módulo [!UICONTROL Repetidor] para repetir una tarea un número determinado de veces. Un módulo [!UICONTROL Repetidor] genera paquetes uno tras otro.


<table>
    <tr>
        <td>[!UICONTROL Valor inicial]</td>
        <td>Introduzca o asigne el valor que desea que tenga el módulo en la primera iteración. El valor predeterminado es 1.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Repeticiones]</td>
        <td>Introduzca o asigne el número de veces que quiera que el módulo se repita. Este número debe ser mayor o igual que 0, y menor o igual que 10 000.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Paso]</td>
        <td>Es el número en el que el módulo aumenta el valor. El valor predeterminado es 1.</td>
    </tr>
</table>

>[!BEGINSHADEBOX]

Por ejemplo, podría usarse un módulo [!UICONTROL Repetidor] para enviar cinco correos electrónicos con los temas “Hola 1”, “Hola 2”, etc., conectando el módulo **[!UICONTROL Correo electrónico] >[!UICONTROL Enviarme un correo electrónico]** al módulo [!UICONTROL Repetidor].

1. Haga clic en el icono [!UICONTROL Control de flujo] ![Icono de control de flujo](/help/workfront-fusion/references/apps-and-modules/assets/flow-control-icon.gif) en la parte inferior de la pantalla y, a continuación, haga clic en **[!UICONTROL Repetidor]** en el menú que se muestra.
1. Haga clic en el módulo [!UICONTROL Repetidor] y, a continuación, haga clic en **[!UICONTROL Conectarse automáticamente]** en el cuadro que aparece.

   Se abrirá el módulo Repetidor.

1. En el campo **[!UICONTROL Repeticiones]**, introduzca el número de repeticiones (paquetes de salida) que desea que produzca el módulo.

   En este ejemplo, debe introducir 5.

   ![Repetidor](/help/workfront-fusion/references/apps-and-modules/assets/repeater-2-350x207.png)

   El valor del elemento aumenta en cada repetición según este valor especificado en el campo **[!UICONTROL Paso]**, que se puede ver seleccionando **[!UICONTROL Mostrar ajustes avanzados]**. Este número se establece en 1 de forma predeterminada.

1. Haga clic en **[!UICONTROL Aceptar]** para cerrar el cuadro **[!UICONTROL Control de flujo]**.

1. Haga clic en la aplicación o el módulo de servicio conectado al módulo [!UICONTROL Repetidor].
1. En el cuadro que aparecerá, escriba la información que quiera repetir.

   En el ejemplo de correo electrónico, escribiría Hola en el cuadro [!UICONTROL Asunto] y, a continuación, asignaría `i` desde el módulo del repetidor.

   ![Repetidor](/help/workfront-fusion/references/apps-and-modules/assets/repeater-3-350x207.png)



>[!NOTE]
>
>El número de repeticiones no está determinado por el valor de `i`, ya que sería un bucle en la programación. El módulo repetirá la cantidad de veces indicada en el campo [!UICONTROL Repeticiones]. El valor de `i` cambia con cada iteración del módulo [!DNL repeater] y se puede asignar a módulos posteriores. El ejemplo anterior asigna el valor de `i` al mensaje Hola, lo que da como resultado mensajes que dicen “Hola 1”, “Hola 2”, etc.

>[!ENDSHADEBOX]

## [!UICONTROL Iterador]

Un [!UICONTROL Iterador] es un tipo especial de módulo que convierte una matriz en una serie de paquetes. Cada elemento de matriz será un paquete independiente en la salida del módulo [!UICONTROL Iterador]. Para obtener más información, consulte [Módulo iterador](/help/workfront-fusion/references/modules/iterator-module.md).

## Agregador de matrices

Un agregador de matrices es un tipo especial de módulo que permite combinar varios paquetes en uno solo. Para obtener más información, consulte [Módulo de agregado](/help/workfront-fusion/references/modules/aggregator-module.md).

## [!UICONTROL Enrutador]

El módulo [!UICONTROL Enrutador] permite bifurcar el flujo en varias rutas y procesar los datos de cada ruta de forma diferente. Una vez que un módulo [!UICONTROL Enrutador] recibe un paquete, lo reenvía a cada ruta conectada en el orden en que se adjuntaron las rutas al módulo [!UICONTROL Enrutador]. Para obtener más información, consulte [Módulo de enrutador en Adobe Workfront Fusion](/help/workfront-fusion/create-scenarios/add-modules/router-module.md).

## Directivas

Las directivas de gestión de errores permiten controlar cómo reacciona el escenario a los errores.

Para obtener información acerca de las directivas de control de errores, consulte [Directivas de control de errores](/help/workfront-fusion/references/errors/directives-for-error-handling.md).

