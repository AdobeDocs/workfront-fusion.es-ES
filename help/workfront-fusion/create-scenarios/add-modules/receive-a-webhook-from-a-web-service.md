---
title: Configuración de un webhook para un servicio web sin conector
description: Si un servicio web no tiene actualmente un conector específico en Workfront Fusion, pero admite la entrega de webhooks, puede añadir el servicio a un escenario utilizando el módulo de webhook personalizado como déclencheur instantáneo.
author: Becky
feature: Workfront Fusion
exl-id: 51ef13fb-2978-4927-8d5f-7d83995f11e0
TQID: https://experienceleague.adobe.com/Ux37ZShkz3kxnJg3Guwqvqt8TISuzV0kAVZ-kKfy0zI
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 354
ht-degree: 37%

---

# Configuración de un webhook para un servicio web sin conector

Si un servicio web no tiene actualmente un conector específico en Workfront Fusion, pero admite la entrega de webhooks, puede añadir el servicio a un escenario utilizando el módulo de webhook personalizado como déclencheur instantáneo. Este proceso se denomina recepción de un webhook y requiere cierta configuración en el lado de la aplicación a la que se está conectando.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Paquete de Adobe Workfront</td> 
   <td> <p>Cualquier paquete del flujo de trabajo de Adobe Workfront y cualquier paquete de integración y automatización de Adobe Workfront</p><p>Workfront Ultimate</p><p>Paquetes Workfront Prime y Select, con una compra adicional de Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencias de Adobe Workfront</td> 
   <td> <p>Estándar</p><p>Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Recepción de un webhook

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea agregar un webhook.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Agregue el módulo **Webhooks > Webhook personalizado** para comenzar su escenario.
1. Haga clic en **Añadir** junto al campo Webhook.
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
