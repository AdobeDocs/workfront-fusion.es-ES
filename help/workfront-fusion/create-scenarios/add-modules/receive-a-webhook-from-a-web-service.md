---
title: Configuración de un webhook para un servicio web sin conector
description: Si un servicio web no tiene actualmente un conector específico en Workfront Fusion, pero admite la entrega de webhooks, puede añadir el servicio a un escenario utilizando el módulo de webhook personalizado como déclencheur instantáneo.
author: Becky
feature: Workfront Fusion
exl-id: 51ef13fb-2978-4927-8d5f-7d83995f11e0
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 28%

---

# Configuración de un webhook para un servicio web sin conector

Si un servicio web no tiene actualmente un conector específico en Workfront Fusion, pero admite la entrega de webhooks, puede añadir el servicio a un escenario utilizando el módulo de webhook personalizado como déclencheur instantáneo. Este proceso se denomina recepción de un webhook y requiere cierta configuración en el lado de la aplicación a la que se está conectando.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront 
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
   <p>Heredado: cualquiera </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Plan Select or Prime Workfront: su organización debe adquirir Adobe Workfront Fusion.</li><li>Plan Ultimate Workfront: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe adquirir Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Recepción de un webhook

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea agregar un webhook.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Agregue el módulo **Webhooks > Webhook personalizado** para comenzar su escenario.
1. Haga clic en **Agregar** junto al campo Webhook.
1. Escriba un **nombre de webhook** en el cuadro que se muestra
1. (Opcional) configure el webhook.

   Para obtener instrucciones, consulte [Webhooks](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md).

1. Haga clic en **Guardar**.

1. Haga clic en **Copiar dirección al portapapeles** y, a continuación, haga clic en **Aceptar**.

1. Inicie sesión en el servicio web y haga lo siguiente allí:

   1. En el área Configuración del servicio web, cree un webhook.

      Las instrucciones específicas dependen de la aplicación. Recomendamos buscar en la documentación de la aplicación &quot;Crear un webhook&quot;.
   1. Pegue la dirección que ha copiado en el portapapeles en el paso 3.
   1. Seleccione el evento que activará el webhook.

1. Ejecute el escenario.

   Cuando se produce el evento o los eventos, el módulo del gancho web personalizado entra en déclencheur y se ejecuta el escenario.
