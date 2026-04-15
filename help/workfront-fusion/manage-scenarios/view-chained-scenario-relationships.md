---
title: Ver relaciones de escenario encadenado
description: Puede crear un mapa de las relaciones entre los escenarios principal y secundario.
author: Becky
feature: Workfront Fusion
source-git-commit: e7b12ec51474440990cc28996bc70fd97688b082
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 22%

---

# Ver y administrar relaciones de escenarios encadenados

Puede crear un mapa de las relaciones entre los escenarios principal y secundario. También puede utilizar el mapa para saltar a diferentes escenarios de la cadena.

Para obtener más información sobre escenarios encadenados, vea [Encadenar varios escenarios](/help/workfront-fusion/create-scenarios/plan-a-scenario/chain-scenarios.md).

Para obtener información sobre la configuración de escenarios encadenados, consulte [Módulos de cadena](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/chain-modules.md)

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

## Ver un mapa de relaciones encadenadas

Puede ver un mapa del escenario actual y de sus escenarios principales o secundarios. El mapa muestra un diagrama del flujo de datos a través de los escenarios encadenados.

![Relaciones de escenario encadenado](assets/chained-scenario-relationships-2.png)

<!--get a better picture-->

Para ver el mapa de relaciones de un escenario encadenado:

1. Haga clic en la ficha **[!UICONTROL Escenario]** en el panel izquierdo y, a continuación, haga clic en el escenario.

   O

   Si está trabajando en el escenario en el Editor de escenarios, haga clic en la flecha izquierda ![Salir de la flecha de edición](assets/exit-editing-arrow.png) cerca de la esquina superior izquierda de la ventana.

1. Haga clic en la ficha **Relaciones**.

   ![Ficha Relaciones](assets/relations-tab.png)

1. Para obtener detalles generales sobre cada escenario encadenado, consulte las etiquetas.

   Cada escenario tiene una o más de las siguientes etiquetas:

   * Raíz: el escenario es el principio de la cadena y no tiene escenario principal.
   * Principal: El escenario es un escenario principal.
   * Secundario: el escenario es secundario. Un escenario puede ser tanto un escenario principal como un escenario secundario.
   * Actual: Este es el escenario que el usuario está viendo en este momento. En otras palabras, este es el escenario desde el que el usuario abrió el mapa de relaciones.

   ![Etiquetas de escenario en el mapa de relación](assets/chained-scenario-maps-tag.png)
1. (Opcional) Para ver un pequeño diagrama de un escenario, pase el ratón sobre él.
1. (Opcional) Para ir directamente a otro escenario desde el mapa, haga clic en el escenario.

   El escenario donde se hizo clic se abre en otra ventana.
1. (Opcional) Para cambiar entre las vistas horizontal y vertical del mapa, haga clic en **Horizontal** o **Vertical** cerca de la parte superior derecha de la página Detalles del escenario.
1. (Opcional) Para ver una vista simplificada del mapa, compruebe la esquina inferior derecha de la página.

   Esto puede ser conveniente si el mapa de la cadena es grande o complejo.

   * Si sólo está viendo una parte del mapa, esa parte es más oscura en el mapa simplificado.
   * El escenario actual está marcado en azul en el mapa simplificado.


