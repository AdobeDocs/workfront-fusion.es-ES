---
title: Módulos de archivo
description: En un escenario de  [!DNL Adobe Workfront Fusion] , puede conectar un archivo, como un archivo comprimido, a varias aplicaciones y servicios de terceros. Por ejemplo, puede configurar un escenario que
author: Becky
feature: Workfront Fusion
exl-id: 4b5ff3d5-601c-4119-ad70-3612ad5ba1ab
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 77%

---

# Módulos de [!UICONTROL Archive]

En un escenario de [!DNL Adobe Workfront Fusion], puede usar un archivo, como un archivo comprimido, en su escenario, lo que le permite utilizarlo en sus automatizaciones o integraciones.

Para obtener instrucciones sobre cómo crear un escenario, vea los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md). Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

## Módulos de [!UICONTROL Archive] y sus campos

Al configurar módulos de [!UICONTROL Archive], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!UICONTROL Archive] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [[!UICONTROL Extract an archive]](#extract-an-archive)
* [[!UICONTROL Create an archive]](#create-an-archive)
* [[!UICONTROL Inflate]](#inflate)
* [[!UICONTROL Deflate]](#deflate)

## [!UICONTROL Extract an archive]

Este módulo de acción extrae un archivo que usted identifica en un archivo.

El módulo devuelve el identificador del archivo y cualquier campo asociado, junto con cualquier otro campo personalizado y valor al que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td> <p> Seleccione el archivo que desee extraer. Este archivo se puede asignar desde un módulo anterior (como el módulo [!DNL Workfront] &gt;[!UICONTROL Download a document]).</p>  </td> 
  </tr> 
 </tbody> 
</table>

>[!INFO]
>
>**Ejemplo:** Obtenga el archivo ZIP de la carpeta [!DNL Dropbox] definida (por ejemplo, Archivos), extráigalo mediante el módulo [!UICONTROL Archive] y envíe los archivos extraídos a la dirección de correo electrónico deseada como archivos adjuntos con el módulo [!UICONTROL Email] o [!DNL Gmail].
>
>![](/help/workfront-fusion/references/apps-and-modules/assets/example-dropbox-350x134.png)

## [!UICONTROL Create an archive]

Este módulo de agregador agrega los archivos deseados a un archivo de [!UICONTROL ZIP] o [!UICONTROL TAR].

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Source module]</td> 
   <td> <p> Seleccione el módulo del que desea recuperar los archivos.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Type] </td> 
   <td> <p>Seleccione si desea agregar archivos a un archivo [!UICONTROL ZIP] o a un archivo [!UICONTROL TAR].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Comment]</td> 
   <td>Escriba cualquier comentario que desee añadir al archivo.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Group by]</td> 
   <td> <p>Defina una expresión por la cual desea agrupar la salida agregada. Esta expresión puede contener uno o varios elementos asignados. Los datos agregados se separarán entonces en grupos utilizando el valor de esta expresión. Cada grupo genera como un paquete independiente con una clave (la expresión evaluada) y un valor (el texto añadido). Puede utilizar la clave como filtro en módulos posteriores.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Stop processing after an empty aggregation]</td> 
   <td>Seleccione esta opción para detener el escenario cuando no haya resultados.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Archive name]</td> 
   <td> <p> Introduzca un nombre para el archivo creado. No añada ninguna extensión.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!INFO]
>
>**Ejemplo:** Vea los correos electrónicos entrantes usando el módulo [!DNL Gmail] >[!UICONTROL Watch emails]. Si se recibe un correo electrónico, los archivos adjuntos se repiten en paquetes individuales y, a continuación, se archivan en el archivo [!DNL ZIP] y se guardan en la carpeta Dropbox definida.
>
>![](/help/workfront-fusion/references/apps-and-modules/assets/example-gmail-350x102.png)

## [!UICONTROL Inflate]

Este módulo transformador descomprime datos binarios usando un algoritmo de inflación.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data] </td> 
   <td> <p>Introduzca o asigne los datos que desea descomprimir con la función de inflado.</p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Deflate]

Este módulo transformador comprime datos binarios usando un algoritmo de desinflado.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data] </td> 
   <td> <p>Introduzca o asigne los datos que desea comprimir con la función de desinflado.</p> </td> 
  </tr> 
 </tbody> 
</table>
