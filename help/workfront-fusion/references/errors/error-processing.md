---
content-type: reference
title: Tipos de error
description: A veces, se puede producir un error durante la ejecución de un escenario. Esto suele ocurrir si un servicio no está disponible debido a un error al conectarse a un servicio o si falla una validación. En este artículo se analizan los errores comunes que pueden producirse.
author: Becky
feature: Workfront Fusion
exl-id: abf5f844-d13b-416e-a8b8-2d4ee1786262
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1235'
ht-degree: 33%

---

# Tipos de error

A veces, se puede producir un error durante la ejecución de un escenario. Esto suele ocurrir si un servicio no está disponible debido a un error al conectarse al servicio o si falla una validación.

Adobe Workfront Fusion distingue entre varios tipos de error básicos. El tipo de error determina las siguientes acciones de su escenario de Fusion.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">paquete de Adobe Workfront</td> 
   <td> <p>Cualquiera</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencia de Adobe Workfront</td> 
   <td> Nuevo: estándar<p>O</p><p>Actual: Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de [!UICONTROL Adobe Workfront Fusion]</td> 
   <td>
   <p>Actual: no se requiere licencia de Workfront Fusion.</p>
   <p>O</p>
   <p>Heredado: cualquiera </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Plan de Workfront de [!UICONTROL Select] o [!UICONTROL Prime]: su organización debe adquirir Adobe Workfront Fusion.</li><li>Plan de Workfront de [!UICONTROL Ultimate]: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe comprar Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>


Para saber qué plan, tipo de licencia o acceso tiene, póngase en contacto con el administrador de Workfront.

Para obtener más información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Error de conexión

`ConnectionError`

Los errores de conexión son uno de los errores más comunes. Por lo general, se deben a la falta de disponibilidad del servicio de terceros por varios motivos, como sobrecarga, mantenimiento o interrupción del servicio. La administración predeterminada de este error depende del módulo que haya encontrado el error.

* Si el error se produce en el primer módulo, la ejecución del escenario termina con un mensaje de advertencia. A continuación, Workfront Fusion intenta repetidamente volver a ejecutar el escenario en intervalos de tiempo crecientes. Si todos los intentos fallan, Workfront Fusion desactiva el escenario.
* Si el error de conexión se produce en otro módulo distinto del primero, los pasos siguientes dependen de la opción Permitir almacenamiento de ejecuciones incompletas en la configuración avanzada del escenario:

   * Si esta opción está habilitada, la ejecución del escenario se mueve a la carpeta [!UICONTROL Ejecuciones incompletas], donde Workfront Fusion intenta repetidamente volver a ejecutar el escenario en intervalos de tiempo cada vez mayores. Si todos los intentos fallan, la ejecución permanecerá en la carpeta de ejecuciones incompletas a la espera de la resolución manual por parte del usuario.

     Para obtener más información sobre las ejecuciones incompletas, vea [Ver y resolver ejecuciones incompletas](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md).
   * Si esta opción está desactivada, la ejecución del escenario finaliza con un error seguido de una fase de reversión. A continuación, Workfront Fusion intenta repetidamente volver a ejecutar el escenario en intervalos de tiempo crecientes. Si todos los intentos fallan, Workfront Fusion desactiva el escenario.

  Para obtener más información sobre la opción de configuración Permitir el almacenamiento de ejecuciones incompletas, consulte [Permitir el almacenamiento de ejecuciones incompletas](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#allow-storing-incomplete-executions) en el artículo Configurar opciones de escenario.

### Incremento de los intervalos de tiempo

El algoritmo para aumentar los intervalos de tiempo entre intentos cuando se produce un error se conoce como retroceso exponencial. Los intervalos de tiempo crecientes se establecen de la siguiente manera:

1. 10 minutos
1. 1 hora
1. 3 horas
1. 12 horas
1. 24 horas

El aumento de los intervalos de tiempo ayuda a evitar que los escenarios ejecutados con frecuencia utilicen operaciones en intentos fallidos repetidamente.

>[!BEGINSHADEBOX]

**Ejemplo**

Un escenario contiene el [!DNL Google Sheets] activador [!UICONTROL Watch Rows]. [!DNL Google Sheets] no está disponible durante 30 minutos debido al mantenimiento cuando Workfront Fusion inicia el escenario, por lo que no puede recuperar nuevas filas. El escenario se detiene y vuelve a intentarlo en 10 minutos. Debido a que [!DNL Google Sheets] sigue sin estar disponible, Workfront Fusion sigue sin poder obtener información sobre las filas nuevas. La siguiente ejecución del escenario está programada en 1 hora. [!DNL Google Sheets] vuelve a estar disponible en este momento y el escenario se ejecuta correctamente.

>[!ENDSHADEBOX]

## Error de datos

`DataError`

Se genera un error de datos cuando un elemento está asignado incorrectamente y no pasa la validación realizada ni en el lado de Workfront Fusion ni en el lado del servicio de terceros.

Si se produce este error, el escenario, hasta donde falló el módulo, se mueve a la carpeta ejecuciones incompletas, donde puede solucionar el problema. Sin embargo, el escenario no se detiene y continúa ejecutándose según su programación. Para detener la ejecución del escenario cuando aparezca el error Datos, active la opción Procesamiento secuencial en el panel Configuración de escenario.

Si no ha habilitado la opción [!UICONTROL Permitir el almacenamiento de ejecuciones incompletas] en la configuración del escenario, la ejecución del escenario finaliza con el error y se realiza una reversión.

## Error de duplicación de datos

`DuplicateDataError`

Si Workfront Fusion intenta insertar el mismo paquete dos veces en un servicio que no permite datos duplicados, se genera un error de datos duplicados. Si se produce este error, Workfront Fusion actúa de la misma manera que lo hace para el error de datos.

Para obtener más información, consulte [Error de datos](#data-error) en este artículo.


## Error de token de acceso no válido

`InvalidAccessTokenError`

Se produce un error de token de acceso no válido cuando Workfront Fusion no puede acceder a su cuenta registrada con un servicio de terceros. Esto suele ocurrir cuando se revocan los derechos de acceso para Workfront Fusion en la administración de un servicio determinado, pero los escenarios que utilizan ese servicio siguen ejecutándose según la programación.

Si se produce este error, la ejecución del escenario se detiene inmediatamente. El resto del escenario que comienza desde el módulo donde se produjo el error se mueve a la carpeta de ejecuciones incompletas.

## Error de límite de velocidad

`RateLimitError`

Si se supera un límite establecido por un servicio determinado, se genera un error de límite de velocidad. Si se produce este error, Workfront Fusion procede del mismo modo que para el error de conexión.

Para obtener más información, consulte [Error de conexión](#connection-error) en este artículo.

## Error de datos incompletos

`IncompleteDataError`

Un error de datos incompleto solo se produce con los activadores. Este error se genera si un activador no puede descargar los datos necesarios de un servicio determinado.

Si un escenario termina con `IncompleteDataError`, su comportamiento posterior dependerá de su configuración de [!UICONTROL Max number of consecutive errors]

Para obtener más información, consulte [Número de errores consecutivos](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#number-of-consecutive-errors) en el artículo Configurar opciones de escenario.

>[!BEGINSHADEBOX]

**Ejemplo:**

Un escenario tiene el déclencheur de Workfront [!UICONTROL Registro de inspección] configurado para inspeccionar documentos. El escenario se ejecutará mientras se carga un documento grande, como un vídeo largo. Dado que [!UICONTROL Workfront Fusion] intenta descargar el vídeo mientras se sigue cargando en Workfront, el escenario termina con `IncompleteDataError`.

>[!ENDSHADEBOX]

## Error de tiempo de ejecución

`RuntimeError`

Cualquier error que aparezca durante la ejecución del escenario y que no sea uno de estos tipos de error se registra como `RunTimeError`.

Si un escenario termina con `RuntimeError`, su comportamiento posterior depende de la configuración [!UICONTROL Número máximo de errores consecutivos].

Para obtener más información, consulte [Número de errores consecutivos](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#number-of-consecutive-errors) en el artículo Configurar opciones de escenario.


>[!NOTE]
>
>Si un escenario comienza con un déclencheur instantáneo y encuentra este error, se omite la configuración de [!UICONTROL Número máximo de errores consecutivos] y el escenario se desactiva inmediatamente.
>>Para obtener más información, consulte [déclencheur instantáneos](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#instant-triggers) en el artículo Información general sobre los módulos.

## Error de incoherencia

`InconsistencyError`

Si alguno de estos errores se produce durante la fase de confirmación o reversión, el escenario termina con un Error de incoherencia.

Si este error aparece en un escenario, la ejecución del escenario se detiene inmediatamente.

## Advertencia

Al ejecutar un escenario, es posible que reciba una advertencia que le informe sobre un problema. Una advertencia no impide que el escenario se complete correctamente.

Por ejemplo, puede aparecer una advertencia cuando se exceda el tamaño máximo de archivo permitido y la opción [!UICONTROL Habilitar pérdida de datos] esté deshabilitada.

## Recursos

Para obtener más información sobre la asignación, consulte [Descripción general de asignación](/help/workfront-fusion/get-started-with-fusion/understand-fusion/mapping-overview.md).

Para obtener información sobre ejecuciones incompletas, vea [Ver y resolver ejecuciones incompletas](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md).

Para obtener información acerca del panel de configuración de escenarios, vea [Configurar escenarios](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md).

Para obtener información sobre las programaciones, consulte [Programar un escenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md).

Para obtener información acerca de las fases del escenario, vea [Ejecución de escenarios, ciclos y fases](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md).

Para obtener información sobre la opción Habilitar pérdida de datos, consulte [Habilitar pérdida de datos](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#enable-data-loss) en el artículo Configurar opciones de escenario.
