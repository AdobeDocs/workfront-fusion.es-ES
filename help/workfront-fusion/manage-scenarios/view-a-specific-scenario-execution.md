---
title: Ver la ejecución de un escenario específico
description: Puede ver los detalles de la ejecución de un escenario específico, incluido el filtrado y la búsqueda de eventos de escenario.
author: Becky
feature: Workfront Fusion
exl-id: 34dd9836-9a1b-4ce2-b24e-ae769888a52a
source-git-commit: 42be02d6a59a5d7b8faccdcfe40e8b967153c6eb
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 10%

---

# Ver la ejecución de un escenario específico

Puede ver los detalles de la ejecución de un escenario específico, incluido el filtrado y la búsqueda de eventos de escenario.

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

## Ver una ejecución específica

Puede ver una ejecución desde el historial de escenarios del escenario.


1. Haga clic en la ficha **[!UICONTROL Escenario]** en el panel izquierdo y, a continuación, haga clic en el escenario.

   O

   Si está trabajando en el escenario en el Editor de escenarios, haga clic en la flecha izquierda ![Salir de la flecha de edición](assets/exit-editing-arrow.png) cerca de la esquina superior izquierda de la ventana.

1. Haga clic en **Historial** cerca del nombre del escenario.
   ![ficha de historial](assets/history-tab.png)


1. Busque la ejecución que desee ver y haga clic en **Detalles** en el extremo derecho de la línea correspondiente a esa ejecución. El vínculo [!UICONTROL detalles] solo es visible si la ejecución tiene detalles disponibles.

   Se abre el diagrama de escenario con el panel de detalles de ejecución abierto a la derecha.

   Los módulos que produjeron resultados para esta ejecución se marcan con títulos verdes.

   Los módulos que no se ejecutaron aparecen atenuados.

1. Para ver la salida de un módulo, haga clic en la burbuja de detalles de salida cerca del módulo. El número de la burbuja representa el número de paquetes que genera la salida del módulo.

   ![Burbuja de salida cerca de un módulo](assets/output-bubble.png)

1. Para ver los paquetes que pasan por un filtro, haga clic en el filtro. El número cerca del filtro representa el número de paquetes que han pasado a través del filtro.
1. Para buscar un módulo o evento específico en el panel de ejecución, escriba el término de búsqueda en el cuadro **Buscar eventos de ejecución**. Los resultados aparecen a medida que escribe.
1. Para limitar los resultados de búsqueda del panel de ejecución por estado, como Correcto o Advertencia, haga clic en el menú desplegable **Filtro de estado** y seleccione el estado.




>[!NOTE]
>
>Para crear un vínculo a un módulo específico, agregue `?moduleId=<module-id>` a la dirección URL cuando visualice las siguientes páginas:
>
>* Página de edición de escenario (la dirección URL termina en `/edit`)
>* Ejecución de un escenario específico (la dirección URL termina en `/logs/<log-id>`)
>
>`<module-id>` hace referencia al número que hay junto a la etiqueta del módulo cuando visualiza el escenario.
>
>Esto puede resultar útil al depurar escenarios o copiar la configuración del módulo.
