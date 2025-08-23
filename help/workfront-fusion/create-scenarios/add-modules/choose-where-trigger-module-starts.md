---
title: Elegir dónde se inicia un módulo de activador
description: Algunos módulos de activación le permiten seleccionar el primer paquete desde el que desea que se inicie la recuperación de paquetes.
author: Becky
feature: Workfront Fusion
exl-id: 83628fa5-82e2-4f67-bfed-70a4c3c19f7f
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 54%

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
   <td role="rowheader">paquete de Adobe Workfront</td> 
   <td> <p>Cualquiera</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencia de Adobe Workfront</td> 
   <td> <p>Nuevo: estándar</p><p>O</p><p>Actual: [!UICONTROL Work] o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion**</td> 
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

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Elegir dónde se inicia un módulo de activador

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea elegir dónde comienza el déclencheur.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Configure y guarde un módulo de déclencheur.

   O

   Haga clic con el botón derecho en el déclencheur del módulo y seleccione **Elegir por dónde empezar**.

   ![Elija por dónde empezar](assets/choose-where-to-start.png)

1. Seleccione una opción en el cuadro **[!UICONTROL Elegir por dónde empezar]** que aparece.

   Las opciones mostradas dependen de las posibilidades de un servicio determinado. Pueden incluir lo siguiente:

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody>
    <tr>
    <td>[!UICONTROL From now on] (valor predeterminado)</td>
    <td>Recupera todos los paquetes añadidos o actualizados (según la configuración) después de seleccionar esta opción</td>
    </tr>
     <tr>
    <td>[!UICONTROL Desde fecha específica]</td>
    <td>Recupera todos los paquetes añadidos o actualizados (según la configuración) después de una fecha y hora especificadas</td>
      </tr>
      <tr>
    <td>[!UICONTROL All]</td>
    <td>Recupera todos los paquetes disponibles</td>
     </tr>
      <tr>
    <td>[!UICONTROL Elegir manualmente]</td>
    <td>Permite seleccionar el primer paquete desde el que se va a iniciar la recuperación de paquetes</td>
     </tr>
     </tbody>
   </table>
