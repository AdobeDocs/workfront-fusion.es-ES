---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: Adición de un módulo de activador a un escenario básico
description: Aprenda a añadir un módulo de activador para permitir que el escenario busque periódicamente nuevas solicitudes y las convierta en proyectos.
author: Becky
feature: Workfront Fusion
exl-id: cd8ac958-b7a6-4536-89d8-c79a2f8940a6
source-git-commit: 8884aef2237ad358c774110b81ac17b9efb386d4
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 79%

---

# Adición de un módulo de activador a un escenario básico

Los módulos de activador se colocan al principio de un escenario. Estos módulos comienzan una ejecución de escenario cuando se ha producido un cambio en un servicio determinado. El cambio puede consistir en la creación de registros nuevos, la eliminación de registros, la actualización de registros, etc. Especifique los criterios para los cambios que comienzan el escenario.

Los módulos de sondeo comprueban el servicio en un intervalo de tiempo establecido y devuelven información sobre los cambios producidos durante ese intervalo de tiempo. Si no se produjeron cambios, el activador no ejecutará el escenario.

En este ejemplo, añadirá un módulo de activador que se ejecute cada 15 minutos e inicie un escenario si se enviaron solicitudes a una cola específica. A continuación, el escenario convertirá esas solicitudes en un proyecto.

En este ejemplo se modifica el escenario que se creó en [Crear un escenario básico](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md).

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] paquete</td> 
   <td> <p>Cualquiera</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licencia</td> 
   <td> <p>Nuevo: [!UICONTROL Standard]</p><p>O</p><p>Actual: [!UICONTROL Work] o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licencia**</td> 
   <td>
   <p>Actual: no se requiere licencia para [!DNL Workfront Fusion].</p>
   <p>O</p>
   <p>Heredado: cualquiera </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>[!UICONTROL Select] o plan [!UICONTROL Prime] [!DNL Workfront]: su organización debe comprar [!DNL Adobe Workfront Fusion].</li><li>[!UICONTROL Ultimate] [!DNL Workfront] plan: [!DNL Workfront Fusion] está incluido.</li></ul>
   <p>O</p>
   <p>Actual: su organización debe comprar [!DNL Adobe Workfront Fusion].</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Es necesaria la creación del escenario descrito en [Crear un escenario básico](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md) antes de seguir con este procedimiento.

## Adición y configuración del módulo de activador

### Añadir el módulo de activador

1. Abra el escenario en el editor de escenarios.
1. Haga clic con el botón derecho en el primer módulo (Búsqueda) y seleccione **Eliminar módulo**.

   El módulo se eliminará y quedará un marcador de posición en blanco.

1. Haga clic en el módulo en blanco y seleccione **Adobe Workfront** de la lista de aplicaciones.
1. Seleccione **Ver registro**.
1. Asegúrese de que el módulo utilice la misma conexión que el resto de módulos del escenario.
1. En el campo Tipo de registro, seleccione **Problema**.
1. En el campo Filtro, seleccione **Solo registros nuevos**.
1. En el cuadro Resultados, seleccione `ID`, `Name` y `Project ID`.
1. Haga clic en **Aceptar** para guardar la configuración del módulo.

   Aparecerá la ventana Elegir por dónde comenzar.

1. Seleccione **A partir de ahora**.

### Programación del módulo de activador

1. Haga clic en el reloj del módulo Ver registros.

   Se abrirá la ventana Configuración de la programación.

1. En el campo Ejecutar escenario, seleccione **A intervalos regulares**.

1. Haga clic en **Aceptar**.

### Actualización del segundo módulo

Como se reemplazó el primer módulo, el segundo deberá asignarse al nuevo primer módulo.

1. Abra el módulo Convertir objeto.
1. En el campo ID del problema, elimine el bloque de ID negro. El bloque es negro porque el módulo desde el que se asignó ya no está disponible.
1. Seleccione el bloque de ID situado bajo el primer módulo (Ver registros) para asignarlo al segundo módulo.
1. Haga clic en **Aceptar**.

### Prueba y activación

1. Vaya al entorno de Workfront al que se conecte Fusion y añada un problema.
1. Haga clic en **[!UICONTROL Run once]** en la esquina inferior izquierda del editor de escenarios.
1. Examine el resultado para asegurarse de que el escenario se ejecutó según lo esperado.
1. Cuando esté seguro de que el escenario funciona según lo esperado, haga clic en el conmutador **Programando** de la parte inferior izquierda de la pantalla para **Activar**.

   Esto activará el escenario.
1. En [!DNL Workfront Fusion], haga clic en **[!UICONTROL Save]** cerca de la esquina inferior izquierda para guardar su progreso en el escenario.

   >[!IMPORTANT]
   >
   >Se recomienda guardar con frecuencia mientras se perfeccionan y prueban escenarios.

## Recursos

* Para obtener más información sobre los módulos de déclencheur, consulte [módulos de Déclencheur](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#trigger-modules) en el artículo Información general sobre los módulos.
