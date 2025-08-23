---
title: Configuración de un módulo
description: Debe establecer la configuración para cada módulo que crea.
author: Becky
feature: Workfront Fusion
exl-id: ae82d1fe-31e1-424a-9c1a-42dc1a20b749
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 51%

---

# Configuración de un módulo

Debe establecer la configuración para cada módulo que crea.

Por ejemplo, el módulo a Workfront > Cargar documento requiere que especifique el registro en el que desea cargar un documento.

>[!NOTE]
>
>Además de la configuración del módulo, también puede ajustar la configuración de un escenario. Puede cambiar el nombre del escenario y su programación, además de especificar configuraciones adicionales, entre otras acciones.

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

## Configuración de los ajustes de un módulo

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea agregar un filtro.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Añada un módulo nuevo a un escenario.

   O

   Haga clic en el módulo que desea configurar.

1. Si es necesario para el módulo, cree una **[!UICONTROL Connection]** a su cuenta de usuario registrada para ese servicio determinado, tal como se describe en [Información general sobre Conexiones](/help/workfront-fusion/get-started-with-fusion/understand-fusion/connection-overview.md).
1. En cada campo, escriba el texto adecuado.

   O

   Asigne la salida de un módulo anterior al campo.

   Para obtener información sobre la asignación, consulte [Descripción general de asignación](/help/workfront-fusion/get-started-with-fusion/understand-fusion/mapping-overview.md).

   Para obtener información sobre los diferentes tipos de datos de elementos que Workfront Fusion puede reconocer (como fecha, número y texto), consulte [Tipos de datos de elementos](/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md).

   >[!NOTE]
   >
   >Se requieren parámetros en negrita.

1. (Condicional) Si el módulo tiene opciones avanzadas que desea mostrar y usar, seleccione **[!UICONTROL Mostrar ajustes avanzados]**.
