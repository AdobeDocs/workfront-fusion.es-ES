---
title: Configuración de un módulo
description: Debe establecer la configuración para cada módulo que crea.
author: Becky
feature: Workfront Fusion
exl-id: ae82d1fe-31e1-424a-9c1a-42dc1a20b749
source-git-commit: c83070a7c2d1d048000a4eace4aaede73c7ec49d
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 41%

---

# Configuración de un módulo

Debe establecer la configuración para cada módulo que crea.

Por ejemplo, el módulo a Workfront > Cargar documento requiere que especifique el registro en el que desea cargar un documento.

>[!NOTE]
>
>Además de la configuración del módulo, también puede ajustar la configuración de un escenario. Puede cambiar el nombre del escenario y su programación, además de especificar configuraciones adicionales, entre otras acciones.

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

+++## Configurar la configuración de un módulo

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
