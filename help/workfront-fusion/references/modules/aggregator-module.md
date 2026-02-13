---
title: Módulo de agregado
description: Un módulo agregador es un tipo de módulo diseñado para combinar varios paquetes de datos en un único paquete.
author: Becky
feature: Workfront Fusion
exl-id: 93cde0d0-4013-463a-b19c-d58180632739
source-git-commit: a871a130a1ac023dcb4ce8da7241918da2431d3a
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 36%

---

# Módulo [!UICONTROL Aggregator]

Un módulo de agregador es un módulo que combina varios paquetes de datos en un solo paquete.

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

## Información general sobre el módulo [!UICONTROL Agregador]

Cuando se ejecuta un módulo [!UICONTROL Agregador], hace lo siguiente:

* Acumula todos los paquetes desde el funcionamiento de un solo módulo de origen.
* Genera un solo paquete con una matriz que contiene un elemento por paquete acumulado. El contenido de los elementos de la matriz depende del módulo [!UICONTROL Aggregator] en particular y de su configuración.

La siguiente imagen muestra una configuración típica del módulo [!UICONTROL Agregador]:

![Agregador de matrices](assets/array-aggregator.png)

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Source Module]</p> </td> 
   <td> <p>Módulo en el que se inicia la agregación del paquete. El módulo de origen suele ser un iterador o un módulo de búsqueda que genera una serie de paquetes.</p><p>Al configurar el módulo de origen del agregador (y cerrar la configuración del agregador), la ruta entre el módulo de origen y el módulo del agregador se ajusta en una zona gris, de modo que pueda ver claramente el inicio y el final de la agregación. 
   </p> <p>Para obtener más información sobre los iteradores, vea <a href="/help/workfront-fusion/references/modules/iterator-module.md" class="MCXref xref">[!UICONTROL Iterator] module</a>.</p> 
   <p>Para obtener más información sobre los módulos de búsqueda, consulte <a href="/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#search-modules" class="MCXref xref">Módulos de búsqueda</a> en Información general del módulo.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Target structure type]</p><p>(Aplicable únicamente para el módulo [!UICONTROL Array aggregator]).</p> </td> 
   <td> <p> Estructura de destino donde se agregan los datos. La opción predeterminada, [!UICONTROL Custom], le permite elegir elementos que deberían agregarse al <code>Array </code>elemento del paquete de salida del [!UICONTROL Array aggregator]:</p> <p> <img src="assets/output-bundle-array-item.png"> </p> <p>Después de conectar más módulos después del módulo [!UICONTROL Array aggregator] y volver a la configuración del módulo de agregador, el menú desplegable de tipo de estructura de [!UICONTROL Target] contiene todos los módulos siguientes y sus campos que son del tipo Matriz de colecciones. <p>En este ejemplo, el campo [!UICONTROL Attachments] del módulo [!DNL Slack] &gt;[!UICONTROL Crear un mensaje] aparece en el campo Array aggregator &gt; Target structure type. </p> <p> <img src="assets/array-aggregator-slack.png"> </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Aggregated fields]</td> 
   <td>Campos que desea incluir en la salida del módulo del agregador.</td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Group by]</p> </td> 
   <td> <p>Con el campo Agrupar por, puede definir una expresión que contenga uno o varios elementos asignados. Los datos agregados se separan en grupos por el valor de la expresión. Cada grupo genera un paquete independiente que contiene una clave y una matriz de datos. Al agrupar los resultados, puede utilizar la clave como filtro en módulos posteriores.</p>
   <p>Cada paquete contiene dos elementos:</p> 
    <ul> 
     <li><code>Key</code>: Valor por el que está agrupando.</li> 
     <li><code>Array</code>: Los datos agregados de los paquetes para los que la fórmula se evaluó en el valor <code>Key</code>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <p>Detener procesamiento después de una agregación vacía</p> </td> 
   <td> <p>De forma predeterminada, el módulo [!UICONTROL Aggregator] genera el resultado de la agregación incluso cuando ningún paquete ha llegado al módulo [!UICONTROL Aggregator] (por ejemplo, porque todos se han filtrado fuera de la ruta que incluye el agregador). Si la opción [!UICONTROL Detener procesamiento después de una agregación vacía] está habilitada, el módulo [!UICONTROL Aggregator] no produce ningún paquete de salida cuando no hay paquetes de entrada. En su lugar, el flujo se detiene.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Los paquetes generados por los módulos entre el módulo de origen y el módulo [!UICONTROL Aggregator] no son generados por el módulo [!UICONTROL Aggregator]. No se puede acceder a estos paquetes desde los módulos del flujo después de [!UICONTROL Aggregator]. Si necesita datos de un paquete generado por un módulo entre el módulo de origen y el módulo [!UICONTROL Aggregator], asegúrese de incluir el elemento proporcionado en la configuración del módulo [!UICONTROL Aggregator] (como en el campo [!UICONTROL Campos agregados] de la configuración del módulo [!UICONTROL Array aggregator]).


## Escenario de ejemplo de cómo funcionan los agregadores

Este escenario de ejemplo muestra cómo comprimir todos los archivos adjuntos de correo electrónico y cargar el ZIP en [!DNL Dropbox].

![Ejemplo de archivo Dropbox](assets/dropbox-archive.png)

El siguiente escenario muestra cómo:

* El primer módulo vigila un buzón en busca de correos electrónicos entrantes. El déclencheur [!UICONTROL Correo electrónico] >[!UICONTROL Ver correos electrónicos] genera un paquete con el elemento `Attachments[]`, que es una matriz que contiene todos los archivos adjuntos del correo electrónico.

* El segundo modelo itera los archivos adjuntos del correo electrónico: [!UICONTROL Correo electrónico] >[!UICONTROL Iterar archivos adjuntos] el iterador toma los elementos de la matriz `Attachments[]` uno por uno y los envía más como paquetes separados.

* El tercer módulo es el agregador. Agrega los paquetes generados por el módulo [!UICONTROL Correo electrónico] >[!UICONTROL Archivos adjuntos iterativos]. [!UICONTROL Archivo] >[!UICONTROL Crear un agregador de archivos] acumula todos los paquetes que recibe y genera un solo paquete que contiene el archivo ZIP.

* El último módulo carga el archivo ZIP resultante en [!DNL Dropbox].  [!DNL Dropbox] > [!UICONTROL Cargar un archivo] obtiene el archivo ZIP del módulo [!UICONTROL Archivo] > [!UICONTROL Crear un archivo] y lo sube a [!DNL Dropbox].



A continuación, se muestra una configuración de ejemplo del agregador [!UICONTROL Archivo] > [!UICONTROL Crear un archivo]:

![Crear un archivo](assets/archive-create-an-archive.png)
