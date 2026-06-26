---
title: Visualización y administración de versiones de escenarios
description: Puede ver, restaurar, cambiar el nombre o descargar modelos para versiones anteriores de un escenario.
author: Becky
feature: Workfront Fusion
exl-id: e7fd0351-b840-422c-b861-82ae110c703b
TQID: https://experienceleague.adobe.com/xVihxZH-fwPCIkryQAQEOWgeShtPTMXth4jEl5OLdbo
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: e24fc726107fcfa34e9288e9a35af445fc0cc765
workflow-type: tm+mt
source-wordcount: 713
ht-degree: 16%

---

# Visualización y administración de versiones de escenarios

Adobe Workfront Fusion guarda una versión de su escenario cada vez que cambia.

Puede ver, restaurar, cambiar el nombre o descargar modelos para versiones anteriores de un escenario.

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

## Ver y administrar el historial de versiones de un escenario

1. Haga clic en **[!UICONTROL Icono de escenarios]** ![escenarios](assets/scenarios-icon.png) en el panel izquierdo y, a continuación, haga clic en el escenario para abrirlo.
1. Haga clic en el icono [!UICONTROL Más] ![Más iconos](assets/more-icon.png) en la parte inferior de la pantalla y, a continuación, haga clic en **[!UICONTROL Versiones anteriores]**.

   Se muestra una lista de versiones anteriores.
1. (Opcional) Para cambiar el nombre de la versión, haga clic en el menú Más ![Menú Más](assets/more-icon-vertical.png) en la línea de esa versión, seleccione **Editar** e introduzca un nombre en el campo. Haga clic en **Guardar** para guardar el nuevo nombre.

   Se recomienda asignar un nombre que describa los cambios realizados en esta versión.
1. (Opcional) Para descargar el modelo de una versión anterior, haga clic en el menú Más ![Menú Más](assets/more-icon-vertical.png) en la línea de esa versión y, a continuación, seleccione **Descargar**.
1. (Opcional) Para comparar los cambios entre dos versiones, haga clic en **Ver cambios** para esa versión.

   Para obtener detalles e instrucciones para comparar versiones, consulte [Comparar versiones de escenarios](#compare-scenario-versions) en este artículo.
1. (Opcional) Para restaurar la versión, haga clic en **Restaurar** en la línea de esa versión


   >[!NOTE]
   >
   >La versión restaurada del escenario no se guarda automáticamente. Si desea guardar la versión restaurada del escenario, debe guardarla manualmente.



## Comparar versiones de escenarios

&#x200B;
La funcionalidad Ver cambios muestra las diferencias entre las dos versiones de escenario, una al lado de la otra, para que pueda ver exactamente qué ha cambiado antes de decidir restaurar una anterior.

1. Haga clic en **[!UICONTROL Icono de escenarios]** ![escenarios](assets/scenarios-icon.png) en el panel izquierdo y, a continuación, haga clic en el escenario para abrirlo.
1. Haga clic en el icono [!UICONTROL Más] ![Más iconos](assets/more-icon.png) en la parte inferior de la pantalla y, a continuación, haga clic en **[!UICONTROL Versiones anteriores]**.

   Se muestra una lista de versiones anteriores.
&#x200B;
1. Haga clic en **Ver cambios** para la versión de escenario que desee ver.
1. Se abre la vista **Revisar cambios** y compara esa versión con su escenario actual.

   El panel Revisar cambios se abre en paralelo para obtener una vista de dos versiones de escenarios.

   * A la izquierda, verá la versión actual.
   * A la derecha, verá la versión en la que hizo clic. Esta es la versión que puede restaurar.

   Para comprender los cambios, vea [Examinar cambios](#examine-changes) en este artículo.

1. Para seleccionar otra versión para cualquiera de los lados, haga clic en el menú desplegable **Comparar entre** o **Comparar con** situado cerca de la parte superior del panel y seleccione otra versión de escenario.
1. Para intercambiar lados, haga clic en el botón **⇄** entre los escenarios.
1. Para volver al escenario del lado derecho, haga clic en **Revertir a la versión seleccionada**

   Las versiones restauradas se guardan como versiones nuevas y, por lo tanto, se pueden revertir en el futuro.

   Para volver al escenario que se encuentra actualmente en el lado izquierdo, cambie los lados para que esté en el lado derecho y haga clic en **Revertir a la versión seleccionada**.


### Examinar cambios


Cada cambio se muestra en el lado al que pertenece y se colorea según lo que haría la restauración
hacer:

* Rojo (izquierda): este cambio no está en la versión de la derecha y se eliminaría si se restaurara la versión.
* Verde (derecha): este cambio se realiza en la versión de la derecha y se añadiría si se restaura la versión.

Si se ha cambiado algo, en lugar de eliminarlo o añadirlo, el valor aparece en rojo a la izquierda y en verde a la derecha.
Los cambios se agrupan en secciones:

* **Escenario**: nombre, descripción y tipo.
* **Configuración de escenario**: Opciones de programación y procesamiento.
* **Módulos**: módulos agregados, quitados, movidos o reconfigurados.
* **Flujos**: ramas agregadas, eliminadas o reordenadas.
* **Rutas de enrutador**: Rutas y su contenido.
* **Controladores de errores**: ramas de control de errores.
* **Grupos huérfanos**: módulos desconectados en el lienzo.
Si las dos versiones son idénticas, la vista muestra el mensaje/ **No se encontraron diferencias**.

