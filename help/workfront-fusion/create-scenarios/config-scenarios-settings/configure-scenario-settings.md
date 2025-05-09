---
content-type: reference
title: Configuración de escenarios
description: Puede configurar opciones específicas para escenarios en el panel Configuración de escenarios.
author: Becky
feature: Workfront Fusion
exl-id: 105e3d39-b0ef-4c22-901d-fb4f29e685a9
source-git-commit: a7411649c0d65956552f40a7710315536755dc65
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 54%

---

# Configuración de escenarios

Puede configurar opciones específicas para escenarios en el panel Configuración de escenarios.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] plan</td> 
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
   <p>Nuevo:</p> <ul><li>Plan [!UICONTROL Select] o [!UICONTROL Prime] [!DNL Workfront]: su organización debe comprar [!DNL Adobe Workfront Fusion].</li><li>Plan [!UICONTROL Ultimate] [!DNL Workfront]: [!DNL Workfront Fusion] está incluido.</li></ul>
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

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación de Workfront](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de [!DNL Adobe Workfront Fusion], consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Abrir la configuración del escenario

1. Haga clic en **Escenarios** en el panel izquierdo.
1. Busque el escenario que desee y haga clic en el nombre.
1. Haga clic en cualquier lugar del escenario para ingresar al editor de escenarios.
1. Haga clic en el icono de engranaje situado cerca de la esquina inferior izquierda de la página.

   ![Configuración de escenario](assets/scenario-settings-350x221.png)

   En el panel [!UICONTROL Configuración de escenario] que se muestra, puede configurar varias opciones avanzadas para el escenario.
1. Habilite o deshabilite la configuración de Escenario según sea necesario. Consulte [Opciones de configuración de escenarios](#scenario-settings-options) a continuación.

## Opciones de configuración de escenarios

### [!UICONTROL Procesamiento secuencial]

Esta opción fuerza que todas las ejecuciones se produzcan en orden y es principalmente relevante para los webhooks y para las ejecuciones incompletas.

Cuando se habilita el procesamiento secuencial, se desactivan las ejecuciones paralelas del escenario.

**Webhooks instantáneos**: Si un déclencheur de webhook está configurado como `instant` y el &quot;Procesamiento secuencial&quot; está habilitado, todas las cargas instantáneas de webhook se pondrán en cola y se procesarán en el orden en que lleguen. Esto puede resultar útil cuando se procesan eventos de sistemas externos en un orden exacto.

>[!NOTE]
>
>Habrá retrasos de procesamiento automático a medida que cada carga útil se procese antes de que se inicie la siguiente.

**Ejecuciones incompletas**: si también está habilitada la opción &quot;Ejecuciones incompletas&quot;, si se produce un error durante la ejecución de un escenario, este se detendrá. A continuación, se produce una de las siguientes acciones:

* Si la opción Sequential processing está **habilitada**, Workfront Fusion deja de procesar la secuencia preexistente hasta que se resuelven todas las ejecuciones incompletas.
* Si la opción de procesamiento secuencial está **deshabilitada**, el escenario seguirá ejecutándose según su programación, acompañado de repetidos intentos de volver a ejecutar las ejecuciones incompletas.

  Para obtener más información sobre las ejecuciones incompletas, vea [Ver y resolver ejecuciones incompletas](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md).

  >[!NOTE]
  >
  >El procesamiento secuencial puede provocar un retraso en la ejecución de un escenario. Si todavía hay ejecuciones incompletas en la cola cuando se activa un escenario instantáneo o uno programado está configurado para ejecutarse, este se ejecutará después de que se hayan completado todas las ejecuciones antes de que esté en la cola.
  >
  >Si el caso de uso para sus escenarios no requiere procesamiento secuencial, se recomienda desactivar la opción de procesamiento secuencial.

  Para obtener más información sobre la programación, consulte [Programar un escenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md).

### Los datos son confidenciales

Una vez ejecutado un escenario, puede mostrar de forma predeterminada información sobre los datos que han procesado los módulos en el escenario. Si no desea almacenar esta información, habilite la opción [!UICONTROL Datos confidenciales].

>[!IMPORTANT]
>
>Si activa esta opción, puede resultar difícil resolver los errores que pueden producirse durante la ejecución de un escenario.

### [!UICONTROL Permitir almacenar ejecuciones incompletas]

Esta opción determina cómo procede [!DNL Adobe Workfront Fusion] si se produce un error durante la ejecución de un escenario. Con esta opción habilitada, el escenario se detiene y se mueve a la carpeta de ejecución incompleta. Esto le ofrece la posibilidad de solucionar el problema y seguir ejecutando desde el lugar en el que se detuvo el escenario. Si esta opción está desactivada, la ejecución del escenario se detiene y se inicia una fase de reversión.

Para obtener más información sobre las ejecuciones incompletas, vea [Ver y resolver ejecuciones incompletas](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md).

### Habilitar la pérdida de datos

Esta opción tiene que ver con habilitar la pérdida de datos si [!DNL Workfront Fusion] no puede guardar un paquete en la cola de ejecuciones incompletas (por ejemplo, debido a la falta de espacio libre). Con esta opción habilitada, los datos se pierden para evitar interrupciones en la ejecución general del escenario. Esto resulta útil en escenarios en los que la prioridad más alta es la ejecución continua y los datos erróneos entrantes no son tan importantes.

Aparte de esto, al ejecutar un escenario, un módulo a veces puede encontrar un archivo que sea más grande que el tamaño máximo permitido. En este caso, [!DNL Workfront Fusion] procede de acuerdo con la configuración de la opción [!UICONTROL Habilitar la pérdida de datos] y se muestra un mensaje de advertencia.

Para obtener más información sobre las ejecuciones incompletas, vea [Ver y resolver ejecuciones incompletas](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md).

Para obtener más información sobre el tamaño máximo de archivo, consulte [Protecciones de rendimiento de Fusion](/help/workfront-fusion/references/scenarios/fusion-performance-guardrails.md#files).

Para obtener más información sobre las advertencias, consulte [Tipos de error](/help/workfront-fusion/references/errors/error-processing.md).

### [!UICONTROL Confirmación automática]

La configuración de [!UICONTROL confirmación automática] se aplica a las transacciones y define la forma de procesar un escenario. Si la opción de confirmación automática está activada, la fase de confirmación de cada módulo se inicia inmediatamente después de completar la fase de operación. Con la opción de confirmación automática desactivada, no se produce ninguna confirmación hasta que se ejecutan las operaciones para todos los módulos (este es el modo predeterminado).

### Número máximo de ciclos

>[!NOTE]
>
>Debe activar la casilla de verificación **Mostrar configuración avanzada** para ver esta opción.


La configuración de más ciclos puede resultar útil cuando desea evitar la interrupción de la conexión a un servicio de terceros y garantizar que todos los registros se procesen dentro de la ejecución de un escenario.

* Si el escenario comienza con un activador de sondeo, el ajuste define el número máximo de ciclos permitidos durante la ejecución del escenario.

  Para obtener más información sobre los déclencheur de sondeo, consulte [déclencheur de sondeo](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#polling-triggers) en el artículo Información general del módulo.

* Si el escenario comienza con un activador instantáneo, el ajuste se ignora y todos los eventos pendientes se procesan durante una sola ejecución de escenario, un evento por ciclo.

  Para obtener más información sobre los déclencheur instantáneos, consulte [déclencheur instantáneos](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#instant-triggers) en el artículo Información general del módulo.

* Si el escenario no comienza con un activador (instantáneo/sondeo), siempre se realiza el número máximo de ciclos especificado.

>[!BEGINSHADEBOX]

**Ejemplos:** [!DNL Workfront] > [!UICONTROL Observar registro] observa los nuevos problemas que se producen y [!DNL Workfront] >[!UICONTROL Convertir objeto] convierte la nueva solicitud en un proyecto y le asigna la plantilla adecuada.

![Configuración de escenario](assets/scenario-settings-ex-1-350x157.png)

La configuración [!UICONTROL más ciclos] solo se aplica cuando se programa la ejecución del escenario. Al usar el botón [!UICONTROL Ejecutar una vez], se tiene en cuenta la configuración del ciclo.

#### El número máximo de ciclos se establece en 1 (predeterminado)

![Número máximo de ciclos](assets/max-number-cycles-1-350x201.png)

El número máximo de ciclos en el módulo Workfront > Ver registros está establecido en `10`.
Si se envían 100 solicitudes a [!DNL Workfront] y el campo Número máximo de ciclos se establece en 10, entonces quedan 90 archivos sin procesar después de que se ejecute un escenario. Los siguientes 10 archivos se procesan en la posterior ejecución de escenario programada.

#### El número máximo de ciclos se establece en 10

El número máximo de ciclos en el módulo Workfront > Ver registros está establecido en `10`.

Si se añaden 100 archivos a la carpeta Dropbox y la opción Número máximo de ciclos se define en 10, se procesarán 10 archivos durante el primer ciclo, los 10 archivos siguientes en el segundo, los 10 archivos siguientes en el tercer ciclo, etc., hasta que se procesen todos los archivos.

Todos los archivos se procesan en un escenario de ejecución.

Puede ver los ciclos ya ejecutados en los detalles del escenario:

![Detalle del escenario](assets/scenario-detail-350x207.png)

Para obtener más información acerca de esta página, vea [Detalles del escenario](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-details.md).

>[!ENDSHADEBOX]

### Número de errores consecutivos

Define el número máximo de intentos de ejecución consecutivos antes de desactivar la ejecución de un escenario (excluyendo `DataError`, `DuplicateDataError` y `ConnectionError`).

Para obtener más información sobre los errores, consulte [Tipos de error](/help/workfront-fusion/references/errors/error-processing.md).

>[!NOTE]
>
>Si un escenario comienza con un activador instantáneo, la configuración se ignora y el escenario se desactiva inmediatamente después de que se haya producido el primer error.

### Grupo de trabajo

>[!NOTE]
>
>Esta configuración solo es visible si se cumplen las dos condiciones siguientes:
>
>* Es administrador o propietario de una organización
>* Hay más de un grupo de trabajadores asociado a su organización.

Esta configuración asigna el escenario a un grupo de trabajadores específico asociado a su organización, lo que le permite dedicar recursos a escenarios de alta prioridad.
