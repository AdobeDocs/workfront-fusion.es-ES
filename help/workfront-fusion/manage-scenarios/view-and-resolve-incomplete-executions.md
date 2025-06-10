---
title: Ver y resolver ejecuciones incompletas
description: La carpeta [!UICONTROL Ejecuciones incompletas] almacena ejecuciones de escenarios que no se finalizaron correctamente debido a un error. Cada ejecución incompleta almacenada se puede resolver manualmente o automáticamente.
author: Becky
feature: Workfront Fusion
exl-id: 8891b4d7-a39a-4f14-8521-8c2ca186ca6e
source-git-commit: ad304117fb6e9d1320b8e50d71a162609dc6e6f4
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 75%

---

# Ver y resolver ejecuciones incompletas

La carpeta [!UICONTROL Ejecuciones incompletas] almacena ejecuciones de escenarios que no se finalizaron correctamente debido a un error. Cada ejecución incompleta almacenada se puede resolver manualmente o automáticamente.

>[!NOTE]
>
>De forma predeterminada, el almacenamiento de ejecuciones incompletas está deshabilitado. Para habilitarlo, habilite la opción [!UICONTROL Permitir el almacenamiento de ejecuciones incompletas] en la configuración avanzada del escenario.
>
>Para obtener más información acerca de la configuración de escenarios, vea [Configurar escenarios](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md).

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
   <p>Nuevo:</p> <ul><li>Plan [!UICONTROL Select] o [!UICONTROL Prime] [!DNL Workfront]: su organización debe adquirir [!DNL Adobe Workfront Fusion].</li><li>Se incluye el plan [!DNL Workfront] de [!UICONTROL Ultimate]: [!DNL Workfront Fusion].</li></ul>
   <p>O</p>
   <p>Actual: su organización debe comprar [!DNL Adobe Workfront Fusion].</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">Configuraciones de nivel de acceso*</td> 
   <td> 
     <p>Debe ser administrador de [!DNL Workfront Fusion] de su organización.</p>
     <p>Debe ser administrador de [!DNL Workfront Fusion] de su equipo.</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener más información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Ver ejecuciones incompletas

Si un módulo encuentra un error durante su operación, se añade una nueva ejecución incompleta a la carpeta Ejecuciones incompletas. Cada ejecución incompleta contiene el modelo del escenario y todos los paquetes que se pueden asignar al módulo fallido. Para abrir la lista de ejecuciones incompletas, haga clic en la pestaña [!UICONTROL Ejecuciones incompletas] de la página de detalles del escenario.

<!--

![Incomplete executions tab](assets/incomplete-executions-tab-350x102.png)

-->

Para obtener más información, consulte [Errores que resultan en ejecuciones incompletas](#errors-resulting-into-incomplete-executions) en este artículo.

>[!NOTE]
>
>El límite de tamaño actual de la carpeta de ejecuciones incompletas sin resolver por organización es de 500 MB. Si su organización supera este límite, es posible que vea el siguiente error:
>
>`"There is NOT ENOUGH SPACE to add a bundle to the IEQ. The reason is: Too many incomplete executions."`
>
>Para obtener más información, consulte [Habilitar la pérdida de datos](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#enable-data-loss) en el artículo Configurar opciones de escenario.


## Resolver ejecuciones incompletas desde la pestaña Ejecuciones incompletas

Cuando se almacena una nueva ejecución incompleta, puede resolverla de la siguiente manera:

1. Abra el escenario afectado.
1. Haga clic en la pestaña **[!UICONTROL Ejecuciones incompletas]**.
1. Busque la ejecución incompleta que desea resolver y haga clic en **[!UICONTROL Detalles]**.
1. Abra el registro del módulo donde se muestran todas las operaciones del módulo.
1. Busque la operación fallida y haga clic en **[!UICONTROL Resolver]**:

   ![Botón Resolver](assets/resolve-btn-350x188.png)



## Resolver ejecuciones incompletas desde la pestaña Historial

Si desea ver el registro de todas las operaciones del módulo antes de intentar resolver la ejecución incompleta, puede resolver la ejecución incompleta desde la carpeta [!UICONTROL Historial]:

1. Abra el escenario afectado.
1. Haga clic en la pestaña **[!UICONTROL Historial]**.
1. Busque la ejecución fallida del escenario y haga clic en **[!UICONTROL Detalles]**.
1. Abra el registro del módulo donde se muestran todas las operaciones del módulo.
1. Busque la operación fallida y haga clic en **[!UICONTROL Resolver]**:

   ![Botón Resolver](assets/resolve-btn-350x188.png)

## Opciones relacionadas con ejecuciones incompletas

Las siguientes opciones del panel [!UICONTROL Configuración de escenarios] determinan si se almacenan las ejecuciones incompletas y cómo se almacenan:

* Permitir almacenar ejecuciones incompletas
* Procesamiento secuencial
* Habilitar la pérdida de datos

Para obtener más información acerca de estas opciones, vea [Configurar opciones de escenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md).

## Errores que dan lugar a ejecuciones incompletas

Existen varias categorías de errores que dan lugar al almacenamiento de ejecuciones incompletas. Estos elementos pueden incluir los siguientes:

* Errores de validación derivados de datos incompletos o erróneos, principalmente debido a la falta de un elemento que se espera para procesar correctamente todos los datos que pasan por un módulo.
* Errores que se producen a partir de la falta de disponibilidad del destino final debido a un error de conexión temporal o a largo plazo (por ejemplo, durante la conexión al servidor de correo electrónico o al servidor FTP remoto).

Si se produce un error en el primer módulo del escenario, la ejecución se detiene inmediatamente y no se almacena ninguna ejecución incompleta.

Si se produce un error en cualquier otro módulo y no hay ninguna ruta de controlador de error adjunta, puede ocurrir lo siguiente:

* Se almacena un registro de ejecución incompleto con reintento automático para los siguientes tipos de error:

   * `ConnectionError`
   * `RateLimitError`
   * `OutOfSpaceError`
   * `ModuleTimeoutError`

* Se almacena un registro de ejecución incompleto sin reintento automático para los siguientes tipos de error:

   * `DataError`
   * `InvalidConfigurationError`
   * `InvalidAccessTokenError`
   * `UnexpectedError`
   * `MaxFileSizeExceededError`
   * `MaxResultsExceededError`

* Si el tipo de error es cualquier cosa que no sea lo anterior, la ejecución falla.
