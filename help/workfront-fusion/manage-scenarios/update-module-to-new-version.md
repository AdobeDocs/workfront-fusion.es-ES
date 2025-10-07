---
title: Actualización de un módulo a una nueva versión
description: Dado que las aplicaciones a las que se conecta Workfront Fusion pueden actualizar o lanzar una nueva versión, a veces es necesario que Fusion lance módulos actualizados para esas aplicaciones.
author: Becky
feature: Workfront Fusion
exl-id: b7f07fa5-9d81-48b3-b0ce-7a18b3b44508
source-git-commit: d0d9d7cdad993ecceaa0abf0ac69e9a9abd78b69
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 58%

---

# Actualización de un módulo a una nueva versión

Dado que las aplicaciones a las que se conecta Workfront Fusion pueden actualizar o lanzar una nueva versión, a veces es necesario que Fusion lance módulos actualizados para esas aplicaciones.

Si ve un icono verde del módulo de actualización en un módulo en un escenario, significa que Workfront Fusion ha lanzado una nueva versión de ese módulo.

![Icono de actualización](assets/update-indicator-workfront.png)

Puede actualizar el módulo sin crear un nuevo escenario.

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
  <tr data-mc-conditions=""> 
   <td role="rowheader">Configuraciones de nivel de acceso*</td> 
   <td> 
     <p>Debe ser administrador de Workfront Fusion para su organización.</p>
     <p>Debe ser administrador de Workfront Fusion para su equipo.</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Actualización de un módulo de Workfront a una nueva versión

1. Haga clic en el icono **Actualizar módulo** ![Actualizar icono](assets/upgrade-icon.png) del módulo en el que desee actualizar a una nueva versión.
   ![Icono de actualización](assets/update-indicator-workfront.png)
1. Seleccione una de las siguientes opciones:

   * Para seleccionar un módulo nuevo que reemplace este módulo (en lugar de actualizar el módulo), haga clic en **Elegir nuevo** y continúe como se describe en [Actualizar un módulo que no sea de Workfront a una nueva versión](#upgrade-a-non-workfront-module-to-a-new-version).
   * Para actualizar solo este módulo, conservando la configuración del módulo, haga clic en **Actualizar**.
   * Para actualizar todos los módulos de Workfront en el escenario, haga clic en **Actualizar todo**.

1. Guarde el escenario.

>[!NOTE]
>
>Si ha actualizado los módulos de Workfront, le recomendamos que los abra y compruebe la configuración del módulo.

## Actualización de un módulo que no sea de Workfront a una nueva versión

1. Haga clic en el icono **Actualizar módulo** ![Actualizar icono](assets/upgrade-icon.png) del módulo en el que desee actualizar a una nueva versión.
   ![Icono de actualización](assets/update-indicator.png)
1. Haga clic en **Elegir nuevo**.
1. Seleccione el módulo que desea reemplazar al módulo anterior.
1. Configure el módulo con los mismos ajustes que el módulo existente.
1. Conecte el módulo nuevo al escenario en el mismo lugar que el módulo existente.
1. Elimine el módulo antiguo.
1. Guarde el escenario.
