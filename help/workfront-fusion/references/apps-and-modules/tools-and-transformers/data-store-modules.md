---
title: Módulos del almacén de datos
description: Un almacén de datos de [!DNL Adobe Workfront Fusion] , algo similar a una base de datos o tabla simple, puede almacenar datos de escenarios, lo que permite transferir datos entre escenarios individuales o ejecuciones de escenarios. Puede utilizar un almacén de datos para almacenar nuevos datos de varios sistemas durante la sincronización.
author: Becky
feature: Workfront Fusion
exl-id: 0338b822-b345-429e-850d-3978b692231d
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1016'
ht-degree: 90%

---

# Módulos de [!UICONTROL Data store]

Un almacén de datos de [!DNL Adobe Workfront Fusion], algo similar a una base de datos o tabla simple, puede almacenar datos de escenarios, lo que permite transferir datos entre escenarios individuales o ejecuciones de escenarios. Puede utilizar un almacén de datos para almacenar nuevos datos de varios sistemas durante la sincronización.

Los módulos del almacén de datos permiten agregar, reemplazar, actualizar, recuperar, eliminar, buscar o contar registros en el almacén de datos de [!DNL Adobe Workfront Fusion].

<!--For information on creating, editing, and troubleshooting data stores, see [Data Stores in [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/references/mapping-panel/data-types/)-->

Para ver un vídeo introductorio a los almacenes de datos en Workfront Fusion, consulte:

* [Almacenes de datos](https://video.tv.adobe.com/v/3427029/){target=_blank}

## Requisitos de acceso

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] plan*</td>
  <td> <p>[!UICONTROL Pro] o superior</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licencia*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licencia**</td> 
   <td>
   <p>Requisito de licencia actual: no se requiere ninguna licencia de [!DNL Workfront Fusion].</p>
   <p>O</p>
   <p>Requisito de licencia heredado: [!UICONTROL [!DNL Workfront Fusion] para automatización e integración de trabajo, [!UICONTROL [!DNL Workfront Fusion] para automatización de trabajo</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Requisito de producto actual: si tiene el plan [!UICONTROL Select] o [!UICONTROL Prime] [!DNL Adobe Workfront], su organización debe adquirir [!DNL Adobe Workfront Fusion] así como [!DNL Adobe Workfront] para utilizar la funcionalidad descrita en este artículo. [!DNL Workfront Fusion] está incluido en el plan [!UICONTROL Ultimate] [!DNL Workfront].</p>
   <p>O</p>
   <p>Requisito de productos heredados: su organización debe comprar [!DNL Adobe Workfront Fusion] y [!DNL Adobe Workfront] para utilizar la funcionalidad descrita en este artículo.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Para saber qué plan, tipo de licencia o acceso tiene, póngase en contacto con el administrador de [!DNL Workfront].

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## Requisitos previos

Para usar módulos de [!UICONTROL Data Store], primero debe crear un almacén de datos.

<!--For information on creating data stores, see [Data Stores in [!UICONTROL Adobe Workfront Fusion]]()-->

## Módulos de [!UICONTROL Data Store] y sus campos

Al configurar los módulos del almacén de datos, [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, es posible que se muestren otros campos de almacén de datos adicionales, dependiendo de factores como su nivel de acceso en la aplicación o servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

Todos los módulos de [!UICONTROL Data Store] son módulos de tipo acción.

* [Añadir o reemplazar un registro](#addreplace-a-record)
* [Actualizar un registro](#update-a-record)
* [Obtener un registro](#get-a-record)
* [Comprobar la existencia de un registro](#check-the-existence-of-a-record)
* [Eliminación de un registro](#delete-a-record)
* [Eliminar todos los registros](#delete-all-records)
* [Búsqueda de registros](#search-records)
* [Recuento de registros](#count-records)

### [!UICONTROL Add/Replace a Record]

Este módulo de acción añade o reemplaza un registro.

Especifique el almacén de datos y la clave del registro.

El módulo devuelve el ID del registro y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

>[!NOTE]
>
>El módulo genera un error cuando intenta agregar el registro que ya está en el almacén de datos con el mismo nombre y la opción [!UICONTROL Overwrite an existing record] está deshabilitada.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store]</td> 
   <td> <p> Seleccione o añada el almacén de datos en el que desea crear un registro. </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Key] </td> 
   <td> <p>Introduzca la clave única del registro que desea que el módulo añada o reemplace. La clave se puede utilizar más adelante para recuperar el registro. Si deja este campo en blanco, se genera una clave automáticamente.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Overwrite an existing record] </td> 
   <td> <p>Active esta opción para sobrescribir el registro. El registro que desea sobrescribir debe especificarse en el campo Clave anterior.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record] </td> 
   <td> <p>Introduzca los valores deseados en los campos del registro.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Update a Record]

Este módulo de acción actualiza un registro.

Especifique el almacén de datos y la clave del registro.

El módulo devuelve el identificador del registro y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store]</td> 
   <td> <p> Seleccione o añada el almacén de datos en el que desea crear un registro. </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Key] </td> 
   <td> <p>Introduzca la clave única del registro que desea que actualice el módulo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Insert missing record] </td> 
   <td> <p>Active esta opción para crear un nuevo registro si el registro con la clave especificada no existe todavía.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record]</td> 
   <td> <p> Introduzca los valores deseados en los campos del registro que desee actualizar.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Get a Record]

Este módulo de acción recupera un registro.

Especifique el almacén de datos y la clave del registro.

El módulo devuelve el ID del registro y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store]</td> 
   <td> <p> Seleccione el almacén de datos desde el que desea recuperar un registro.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Key] </td> 
   <td> <p>Introduzca la clave única del registro que desea que recupere el módulo.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Check the Existence of a Record]

Este módulo de acción especifica si existe un registro en particular.

Especifique el almacén de datos y la clave del registro.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store] </td> 
   <td> <p>Seleccione el almacén de datos en el que desea comprobar la existencia del registro.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Key] </td> 
   <td> <p>Introduzca la clave única del registro que desea que el módulo compruebe si existe.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Delete a Record]

Este módulo de acción elimina un registro.

Especifique el almacén de datos y la clave del registro.

El módulo devuelve el identificador del registro y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store] </td> 
   <td> <p>Seleccione el almacén de datos en el que desea comprobar la existencia del registro.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Key] </td> 
   <td> <p>Introduzca la clave única del registro que quiera que elimine el módulo.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Delete All Records]

Este módulo de acción elimina todos los registros de un almacén de datos concreto.

Usted especifica el almacén de datos.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store] </td> 
   <td> <p>Seleccione el almacén de datos del que quiera eliminar todos los registros.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Search Records]

Este módulo de búsqueda busca registros en un objeto del almacén de datos que coincidan con la consulta de búsqueda especificada.

Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store]</td> 
   <td> <p> Seleccione el almacén de datos que quiera buscar.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Filter]</p> </td> 
   <td> <p>Establezca el filtro de búsqueda.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Sort]</p> </td> 
   <td> <p style="font-weight: normal;">Rellene los campos siguientes de cada campo por el que quiera ordenar:</p> <p style="font-weight: bold;">[!UICONTROL Key]</p> <p>Seleccione el nombre de columna por el que quiera ordenar los resultados.</p> <p style="font-weight: bold;">[!UICONTROL Order]</p> <p>Seleccione si desea ordenar los resultados en orden ascendente o descendente.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td> <p> Establezca el número máximo de resultados de búsqueda que devolverá [!DNL Workfront Fusion] durante un ciclo de ejecución.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Continue the execution of the route even if the module returns no results]</td> 
   <td> <p> En caso de habilitarse, la ruta de la que forma parte este módulo continuará procesándose aunque no devuelva resultados.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Count Records]

Este módulo de acción numera los registros de un almacén de datos.

Usted especifica el almacén de datos.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store] </td> 
   <td> <p>Seleccione el almacén de datos que contenga los registros que quiera contar.</p> </td> 
  </tr> 
 </tbody> 
</table>
