---
title: Elegir dónde se inicia un módulo de activador
description: Algunos módulos de activación le permiten seleccionar el primer paquete desde el que desea que se inicie la recuperación de paquetes.
author: Becky
feature: Workfront Fusion
exl-id: 83628fa5-82e2-4f67-bfed-70a4c3c19f7f
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 59%

---

# Elegir dónde se inicia un módulo de activador

Algunos módulos de activación le permiten seleccionar el primer paquete desde el que desea que se inicie la recuperación de paquetes.

También puede especificar si desea recuperar todos los paquetes o solo los paquetes después de una fecha específica.

Para obtener más información acerca de los módulos de déclencheur, consulte la sección [Módulos de Déclencheur](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#trigger-modules) en el artículo Información general del módulo.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] paquete</td> 
   <td> <p>Cualquiera</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licencia</td> 
   <td> <p>Nuevo: [!UICONTROL Standard]</p><p>O</p><p>Actual: [!UICONTROL Work] o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licencia**</td> 
   <td>
   <p>Actual: no se requiere licencia para [!DNL Workfront Fusion].</p>
   <p>O</p>
   <p>Heredado: cualquiera </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>[!UICONTROL Select] o plan [!UICONTROL Prime] [!DNL Workfront]: su organización debe comprar [!DNL Adobe Workfront Fusion].</li><li>[!UICONTROL Ultimate] [!DNL Workfront] plan: [!DNL Workfront Fusion] está incluido.</li></ul>
   <p>O</p>
   <p>Actual: su organización debe comprar [!DNL Adobe Workfront Fusion].</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de [!DNL Adobe Workfront Fusion], consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Elegir dónde se inicia un módulo de activador

1. Haga clic en la ficha **[!UICONTROL Scenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea elegir dónde comienza el déclencheur.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Configure y guarde un módulo de déclencheur.

   O

   Haga clic con el botón derecho en el déclencheur del módulo y seleccione **Elegir por dónde empezar**.

   ![Elija por dónde empezar](assets/choose-where-to-start.png)

1. Seleccione una opción en el cuadro **[!UICONTROL Choose where to start]** que aparece.

   Las opciones mostradas dependen de las posibilidades de un servicio determinado. Pueden incluir lo siguiente:

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody>
    <tr>
    <td>[!UICONTROL From now on] (predeterminado)</td>
    <td>Recupera todos los paquetes añadidos o actualizados (según la configuración) después de seleccionar esta opción</td>
    </tr>
     <tr>
    <td>[!UICONTROL Since specific date]</td>
    <td>Recupera todos los paquetes añadidos o actualizados (según la configuración) después de una fecha y hora especificadas</td>
      </tr>
      <tr>
    <td>[!UICONTROL All]</td>
    <td>Recupera todos los paquetes disponibles</td>
     </tr>
      <tr>
    <td>[!UICONTROL Choose manually]</td>
    <td>Permite seleccionar el primer paquete desde el que se va a iniciar la recuperación de paquetes</td>
     </tr>
     </tbody>
   </table>



   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td>Escriba un nombre para la nueva conexión de [!DNL DocuSign]</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Account type]</td> 
      <td>Seleccione si la cuenta a la que desea conectarse es una cuenta de producción o una cuenta de demostración.</td> 
     </tr> 
    </tbody> 
   </table>


