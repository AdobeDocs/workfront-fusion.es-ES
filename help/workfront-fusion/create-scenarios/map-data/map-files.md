---
title: Asignar un archivo entre módulos
description: Algunos módulos tienen la capacidad de procesar archivos. Estos módulos pueden devolver un archivo de salida para enviarlo a un procesamiento posterior o requerir que se les pase un archivo para procesarlo. Para que estos módulos puedan trabajar juntos para procesar archivos, deben asignarse entre sí.
author: Becky
feature: Workfront Fusion
exl-id: 25c632f4-169e-4d3c-989a-f57b398bd3f0
source-git-commit: 839f6edf93df8a935b2c5d0a520bdc125fe60288
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 39%

---

# Asignar un archivo entre módulos

Algunos módulos pueden procesar archivos. Estos módulos pueden devolver un archivo de salida para enviarlo a un procesamiento posterior o requerir que se les pase un archivo para procesarlo. Los archivos se pueden asignar para que otro módulo pueda procesar un archivo de salida.

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

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Asignar archivos de módulos de origen a módulos de destino

Los módulos pueden procesar archivos que requieren dos fragmentos de información:

* Nombre del archivo
* Contenido de archivo (datos)

Si algún módulo anterior genera un archivo, puede seleccionar el módulo de origen, y el nombre y los datos del archivo de salida de ese módulo se asignan al módulo de destino.

También puede introducir este nombre y los datos manualmente o asignarlos desde módulos anteriores. Esto puede resultar práctico cuando, por ejemplo, se cambia el nombre de un archivo.

>[!NOTE]
>
>Si necesita procesar un archivo desde una dirección URL, le recomendamos que utilice el módulo `HTTP > Get a File` para descargar el archivo desde la dirección URL; a continuación, asigne el archivo desde el módulo `HTTP > Get a File` al campo del módulo deseado en su escenario.
>
>![Archivo de mapa](assets/map-source-file.png)

Para asignar un archivo:

1. Haga clic en la ficha **[!UICONTROL Scenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea asignar un archivo.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. En el módulo de destino, que es el destino al que está asignando, busque el área **archivo Source**.
1. Para asignar una salida de archivo de un módulo anterior, seleccione el módulo que genera el archivo.

   ![](assets/wf-download-document.png)

1. Para asignar el nombre y los datos manualmente, seleccione Asignar y, a continuación, introduzca o asigne el nombre y los datos del archivo.

   ![](assets/use-the-map-option.png)

1. Continúe configurando el módulo o haga clic en **Aceptar**.
