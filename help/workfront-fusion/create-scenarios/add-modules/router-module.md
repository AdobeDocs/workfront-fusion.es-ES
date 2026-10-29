---
title: Añadir un módulo de enrutador y configurar rutas
description: El módulo Enrutador permite bifurcar el flujo en varias rutas y procesar los datos de cada una de forma diferente. Una vez que un módulo Enrutador recibe un paquete, lo reenvía a cada ruta conectada en el orden en que se hayan adjuntado las rutas al módulo Enrutador.
author: Becky
feature: Workfront Fusion
exl-id: 8344cde4-df3e-4b72-9d10-46ff4b186400
TQID: 'https://experienceleague.adobe.com/ZKrvE8zGuVmfPCTMx7LZHw979aPLo89lARWejMCSETs'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: cc160f0e8c2465b4f102b6d1755088335b2a9fe5
workflow-type: tm+mt
source-wordcount: '1869'
ht-degree: 10%
---
# Añadir un módulo de enrutador y configurar rutas

El módulo Enrutador le permite bifurcar el escenario en varias rutas y procesar los datos de cada ruta de forma diferente. Cuando un módulo Enrutador recibe un paquete, lo reenvía a cada ruta conectada en el orden en que se adjuntaron las rutas al módulo Enrutador.

Las rutas se procesan secuencialmente, no en paralelo. No se envía un paquete a la siguiente ruta hasta que la ruta anterior lo haya procesado completamente.

>[!NOTE]
>
>Workfront Fusion está cambiando el editor de escenarios a una nueva experiencia. Durante esta transición, tanto las experiencias clásicas como las nuevas están disponibles y puede cambiar entre ellas en cualquier momento. Recomendamos utilizar la nueva experiencia. Para obtener más información, consulte [Experiencias nuevas y clásicas](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md#new-and-classic-experiences) en el artículo Editor de escenarios.

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

## Agregar un módulo Enrutador a un escenario

Debe agregar un módulo Enrutador antes de configurar las rutas.

* [Agregar un módulo Enrutador a un escenario en la nueva experiencia (recomendado)](#add-a-router-module-to-a-scenario-in-the-new-experience-recommended)
* [Agregar un módulo Enrutador a un escenario en la experiencia clásica](#add-a-router-module-to-a-scenario-in-the-classic-experience)

### Agregar un módulo Enrutador a un escenario en la nueva experiencia (recomendado)

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea agregar un enrutador.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Pase el ratón sobre el borde derecho del módulo después del cual quiera agregar el enrutador y luego haga clic en **[!UICONTROL Agregar otro módulo]** cuando aparezca. En la lista que se abre, seleccione la categoría **[!UICONTROL Built-in]** y, a continuación, seleccione **[!UICONTROL Flow Control]** > **[!UICONTROL Router]**.

   O

   Para insertar el módulo Enrutador entre dos módulos, haga clic con el botón secundario en la ruta que conecta los dos módulos y, a continuación, seleccione **[!UICONTROL Agregar un enrutador]**.

   ![Agregar un enrutador entre dos módulos](assets/add-a-module-between-modules.png)

1. Agregue la primera ruta al enrutador pasando el puntero sobre el borde derecho del enrutador y agregando un módulo, de forma similar a agregar cualquier módulo.
1. Para agregar otra ruta, haga clic en el módulo enrutador. Aparecerá una ruta. Agregue módulos a esta ruta según desee.

   Puede agregar todas las rutas que desee.

1. Para verificar el orden de las rutas, compruebe la etiqueta de cada ruta. La Ruta 1 se ejecuta primero, luego la Ruta 2, etc.

   O

   Haga clic en el icono de **Alineación automática** ![Alineación automática](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/assets/auto-align-icon-new.png) en el área Controles.

   Las rutas se organizan en el orden en que se ejecutan. La ruta superior se ejecuta primero.

1. (Opcional) Para cambiar el orden de ruta, haga clic con el botón secundario en el módulo Enrutador y seleccione **Ordenar rutas**. Arrastre y suelte las rutas en el orden en que desee que se ejecuten. Las rutas están marcadas por el primer módulo que sigue al enrutador (el primer módulo de la ruta).
1. (Opcional) Para deshabilitar una ruta, haga clic con el botón secundario en la ruta que lleva del enrutador a esa ruta y seleccione **Deshabilitar ruta**.

   Las rutas deshabilitadas muestran puntos grises que llevan del enrutador al primer módulo de la ruta y muestran el icono de ruta deshabilitada ![Icono de ruta deshabilitada](assets/disabled-route-icon.png) en la etiqueta.

1. (Opcional y condicional) Para habilitar una ruta deshabilitada, haga clic en el icono de ruta deshabilitada ![Icono de ruta deshabilitada](assets/disabled-route-icon.png) en la etiqueta de la ruta.
1. Continuar a [Agregar un filtro a una ruta en la nueva experiencia](#add-a-filter-to-a-route-in-the-new-experience-recommended).

### Agregar un módulo Enrutador a un escenario en la experiencia clásica

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea agregar un enrutador.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. En el editor de escenarios, haga clic en el controlador derecho del módulo después del cual desea agregar el enrutador y, a continuación, seleccione **[!UICONTROL Control de flujo]** > **Enrutador** en la lista de módulos que se muestra.

   ![Conectar la ruta](assets/connect-the-router-350x108.png)

   O

   Para insertar el módulo Enrutador entre dos módulos, haz clic en el icono de la llave inglesa debajo de la ruta que conecta los dos módulos y selecciona **[!UICONTROL Agregar un enrutador]** del menú.

   ![Insertar enrutador](assets/insert-router-350x191.png)
1. Agregue la primera ruta al enrutador haciendo clic en el controlador derecho del enrutador y agregando un módulo, de forma similar a agregar cualquier módulo.
1. Para agregar otra ruta, haga clic en el módulo enrutador. Aparecerá una ruta. Agregue módulos a esta ruta según desee.

   Puede agregar todas las rutas que desee.

1. Para verificar el orden de las rutas, compruebe la etiqueta de cada ruta. La Ruta 1 se ejecuta primero, luego la Ruta 2, etc.

   O

   Haga clic en el icono de alineación automática ![Icono de alineación automática](assets/auto-align.png).

   Las rutas se organizan en el orden en que se ejecutan. La ruta superior se ejecuta primero.

1. (Opcional) Para cambiar el orden de las rutas, haga clic con el botón derecho en el módulo Enrutador y seleccione **Ordenar rutas** Arrastre y suelte las rutas en el orden en que desee que se ejecuten. Las rutas están marcadas por el primer módulo que sigue al enrutador (el primer módulo de la ruta).

   ![Solicitar ruta](assets/order-routes.png)

1. (Opcional) Para deshabilitar una ruta, haga clic con el botón secundario en los puntos que llevan del enrutador a esa ruta y seleccione **Deshabilitar ruta**.

   Las rutas deshabilitadas muestran puntos grises que llevan del enrutador al primer módulo de la ruta y muestran el icono de ruta deshabilitada ![Icono de ruta deshabilitada](assets/disabled-route-icon.png) en la etiqueta.

1. (Opcional y condicional) Para habilitar una ruta deshabilitada, haga clic en el icono de ruta deshabilitada ![Icono de ruta deshabilitada](assets/disabled-route-icon.png) en la etiqueta de la ruta.
1. Continuar a [Agregar un filtro a una ruta en la experiencia clásica](#add-a-filter-to-a-route-in-the-classic-experience).

## Adición de un filtro a una ruta

Puede colocar un filtro en una ruta después del módulo Enrutador para filtrar paquetes. Solo los paquetes que pasen a través del filtro serán administrados por los módulos en la ruta.

Si los datos pasan el filtro de más de una ruta, los datos se gestionan mediante ambas rutas. La ruta superior gestiona primero los datos.

Los enrutadores con filtros muestran el icono de filtro ![Icono de filtro](assets/fusion-scenario-filter-icon.png) en la etiqueta de ruta.

* [Añadir un filtro a una ruta en la nueva experiencia (recomendado)](#add-a-filter-to-a-route-in-the-new-experience-recommended)
* [Añadir un filtro a una ruta en la experiencia clásica](#add-a-filter-to-a-route-in-the-classic-experience)

### Añadir un filtro a una ruta en la nueva experiencia (recomendado)

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea agregar un filtro.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haga clic con el botón izquierdo en la ruta en la que desee establecer un filtro. Es la ruta entre el módulo de enrutador y el primer módulo de la ruta.

   La ventana **[!UICONTROL Configurar un filtro]** se abre directamente.

1. En el campo de etiqueta del panel que se muestra, agregue una etiqueta. Esta etiqueta se muestra en el escenario.
1. Configure las condiciones de filtro.

   Para obtener más información, consulte [Añadir un filtro a un escenario](/help/workfront-fusion/create-scenarios/add-modules/add-a-filter-to-a-scenario.md).

   ![Configurar un filtro en una ruta](assets/new-filter-specific-user.png)

1. Haga clic en **[!UICONTROL Aceptar]** para guardar la configuración del filtro.
1. (Condicional) Si el nombre del filtro es demasiado largo para que quepa en la etiqueta, pase el ratón sobre la etiqueta para mostrar el nombre completo.

1. Continuar a [Configurar una ruta de reserva en la nueva experiencia](#configure-a-fallback-route-in-the-new-experience-recommended).

### Añadir un filtro a una ruta en la experiencia clásica

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea agregar un filtro.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haga clic en el icono de llave inglesa ![Wrench](assets/wrench-icon.png) en la ruta donde desee establecer un filtro. Es la ruta entre el módulo de enrutador y el primer módulo de la ruta.
1. Seleccione **Configurar un filtro.**
1. En el campo de etiqueta del panel que se muestra, agregue una etiqueta. Esta etiqueta se muestra en el escenario.
1. Configure las condiciones de filtro.

   Para obtener más información, consulte [Añadir un filtro a un escenario](/help/workfront-fusion/create-scenarios/add-modules/add-a-filter-to-a-scenario.md).

1. Haga clic en **[!UICONTROL Aceptar]** para guardar la configuración del filtro.
1. (Condicional) Si el nombre del filtro es demasiado largo para que quepa en la etiqueta, pase el ratón sobre la etiqueta para mostrar el nombre completo.

1. Continuar a [Configurar una ruta de reserva en la experiencia clásica](#configure-a-fallback-route-in-the-classic-experience).

## Configuración de una ruta de reserva

La ruta de reserva es la ruta que se ejecuta en cualquier paquete que no pase ningún filtro a otra ruta.

Las rutas de reserva muestran &quot;Reserva&quot; en la etiqueta.

Puede habilitar una ruta de reserva en el panel de filtros.

* [Configurar una ruta de reserva en la nueva experiencia (recomendado)](#configure-a-fallback-route-in-the-new-experience-recommended)
* [Configuración de una ruta de reserva en la experiencia clásica](#configure-a-fallback-route-in-the-classic-experience)

### Configurar una ruta de reserva en la nueva experiencia (recomendado)

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea agregar una ruta de reserva.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haga clic con el botón izquierdo en la ruta en la que desee establecer un filtro. Es la ruta entre el módulo de enrutador y el primer módulo de la ruta.

   La ventana **[!UICONTROL Configurar un filtro]** se abre directamente.

1. En el campo de etiqueta del panel que se muestra, agregue una etiqueta. Esta etiqueta se muestra en el escenario.
1. Active la casilla de verificación Ruta de reserva.

   ![Ruta de reserva](assets/fallback-route-new.png)

1. Haga clic en **[!UICONTROL Aceptar]** para guardar la configuración del filtro.

La etiqueta de la ruta de reserva muestra **Reserva** en verde.

### Configuración de una ruta de reserva en la experiencia clásica

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea agregar una ruta de reserva.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haga clic en el icono de llave inglesa ![Wrench](assets/wrench-icon.png) en la ruta donde desee establecer un filtro. Es la ruta entre el módulo de enrutador y el primer módulo de la ruta.
1. Seleccione **Configurar un filtro.**
1. En el campo de etiqueta del panel que se muestra, agregue una etiqueta. Esta etiqueta se muestra en el escenario.
1. Active la casilla de verificación Ruta de reserva.

   ![Ruta de reserva](assets/fallback-route-350x260.png)

1. Haga clic en **[!UICONTROL Aceptar]** para guardar la configuración del filtro.

La ruta de reserva se marca con una flecha diferente en el módulo Enrutador:

![Enrutador de inicio de sesión con flecha](assets/arrow-sign-in-router-module-350x361.png)

## Pliegue un enrutador

>[!NOTE]
>
>Esta función solo está disponible en la nueva experiencia del editor de escenarios.

En la nueva experiencia, puede plegar un enrutador para ocultar temporalmente sus rutas. Esto resulta útil en escenarios grandes.

1. Abra el escenario en el editor de escenarios, en modo de edición.
1. Haga clic con el botón derecho en el enrutador que desee plegar y, a continuación, seleccione **Rutas plegadas**

El enrutador plegado muestra cuántas rutas y módulos están ocultos, incluida la gravedad de las advertencias o errores ocultos.

![Enrutador plegado](assets/fold-router.png)

Al plegar un enrutador no se elimina ni se deshabilita nada. El historial de búsqueda, validación, seguimiento activo y ejecución expande automáticamente un enrutador plegado cuando necesita mostrar un módulo que está dentro de él.

El estado plegado se guarda con el escenario y funciona con las opciones Deshacer y Rehacer. Cuando se revisa la ejecución de un escenario, siempre se muestra el escenario completo.

## Ejemplo: caso de uso `if/else`

>[!BEGINSHADEBOX]

Un caso de uso típico de la ruta de reserva es continuar el flujo con una ruta si se cumple la condición y con otra ruta si no lo es. como en los pasos siguientes:

En este ejemplo, la primera ruta se configura con un filtro. Representa el componente `if`.

![Configurar un filtro en la ruta](assets/new-filter-specific-user-unmarked.png)

La segunda ruta se configura como una ruta de reserva. Representa el componente `else`.

![Habilitar opción de reserva](assets/new-not-specific-user-unmarked.png)

>[!ENDSHADEBOX]
