---
title: Módulo App Builder de Adobe
description: El conector App Builder de Adobe le permite utilizar funciones personalizadas en sus escenarios.
author: Becky
feature: Workfront Fusion
exl-id: 92661a0c-436b-4fbd-808a-a4fbe3cd2339
source-git-commit: 02c396f33b6398635462bac8741f446eb82bf5a9
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 18%
---
# Módulo App Builder de Adobe

Puede crear funciones personalizadas en el área Funciones de Fusion. A continuación, agregue estas funciones a sus escenarios en forma de módulo de Adobe App Builder.

Dado que las funciones personalizadas funcionan a través de Adobe App Builder, su organización debe tener una licencia de Adobe App Builder para utilizarlas.

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
   <p><ul><li>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li><li>Debe tener una licencia de Adobe App Builder para utilizar funciones personalizadas.</ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Creación de una conexión con Adobe App Builder

La conexión utiliza las credenciales de Adobe I/O Runtime de un espacio de trabajo del proyecto de App Builder. Antes de crear la conexión, obtenga estas credenciales de Adobe Developer Console.

### Obtenga sus credenciales de tiempo de ejecución

1. Inicie sesión en [Adobe Developer Console](https://developer.adobe.com/console) con la organización que tenga su licencia de App Builder.
1. Abra el proyecto de App Builder que contiene sus funciones y, a continuación, seleccione el área de trabajo a la que desea conectarse (por ejemplo, **Producción**).
1. Haga clic en **Descargar todo** en la esquina superior derecha para descargar el archivo JSON de configuración del área de trabajo.
1. Abra el archivo y busque la sección `runtime`. Contiene:

   * `namespace`: el valor que se va a escribir en el campo **Espacio de nombres**
   * `auth`: un valor con formato `username:password`. La parte anterior a los dos puntos es **Username**, y la parte posterior a los dos puntos es **Password**.

   >[!NOTE]
   >
   >También puede encontrar el área de nombres y los valores de autenticación ejecutando `aio runtime namespace get` o `aio app use` en la CLI de Adobe I/O.

### Creación de la conexión

1. En el módulo, haga clic en **Agregar** junto al campo **Conexión**.
1. Rellene los campos siguientes:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Connection name]</td> 
      <td>Introduzca un nombre para esta conexión.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Environment]</td> 
      <td>Seleccione si desea conectarse a un entorno de producción o de no producción.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Type]</td> 
      <td>Seleccione <b>Cuenta de servicio</b>.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Username]</td> 
      <td>Escriba el nombre de usuario del valor <code>auth</code> del área de trabajo (la parte anterior a los dos puntos).</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Password]</td> 
      <td>Escriba la contraseña del valor <code>auth</code> del área de trabajo (la parte posterior a dos puntos).</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Espacio de nombres]</td> 
      <td>Introduzca el valor <code>namespace</code> de la sección <code>runtime</code> del archivo de configuración de Workspace.</td> 
     </tr> 
    </tbody> 
   </table>

1. Haga clic en **Continuar** para guardar la conexión.

## Módulos de Adobe App Builder

### Ejecutar un bloque de código personalizado

Este módulo le permite ejecutar un bloque de código. El bloque de código se configura al configurar el módulo y se ejecuta cuando el módulo se ejecuta durante la ejecución de un escenario.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Seleccione la conexión que contiene la función personalizada que desea ejecutar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bloque de código]</td> 
   <td>Escriba el bloque de código que desea que ejecute el módulo.<p>Para dar formato al código para facilitar la lectura, haga clic en el icono <b>Formato del código</b>.</td> 
  </tr> 
   </tbody> 
</table>

### Ejecutar una función personalizada desde el paquete

Este módulo ejecuta una función desde un paquete.

Para obtener información sobre los paquetes, consulte [Usar paquetes de funciones personalizadas](/help/workfront-fusion/create-scenarios/map-data/use-custom-function-packages.md).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Seleccione la conexión que contiene la función personalizada que desea ejecutar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Paquete]</td> 
   <td>Seleccione el paquete que incluye la función que desea ejecutar en el escenario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Variable] </td> 
   <td>Seleccione la función que desea ejecutar en el escenario.</p></td> 
  </tr> 
   </tbody> 
</table>

### Usar variable del paquete

Este módulo incorpora una variable configurada en un paquete a su escenario.

Para obtener información sobre los paquetes, consulte [Usar paquetes de funciones personalizadas](/help/workfront-fusion/create-scenarios/map-data/use-custom-function-packages.md).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Seleccione la conexión que contiene la función personalizada que desea ejecutar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Paquete]</td> 
   <td>Seleccione el paquete que incluye la variable que desea incluir en el escenario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Variable] </td> 
   <td>Seleccione la variable que desee incluir en el escenario.</p></td> 
  </tr> 
   </tbody> 
</table>

### Ejecutar una función personalizada o un bloque de código

Este módulo le permite utilizar una función personalizada de JavaScript previamente configurada y almacenada en el área Funciones.

Para obtener instrucciones sobre cómo configurar una función personalizada, vea [Asignar datos mediante funciones personalizadas](/help/workfront-fusion/create-scenarios/map-data/map-using-custom-functions.md).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Seleccione la conexión que contiene la función personalizada que desea ejecutar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Action]</td> 
   <td>Seleccione la función personalizada que desea ejecutar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Parámetros] </td> 
   <td>Introduzca los valores de los parámetros de función. Los parámetros disponibles se basan en los parámetros configurados cuando se creó la función.<p>Si un parámetro tiene un valor predeterminado, no lo verá en el campo, pero puede anularlo introduciendo o asignando un valor en el campo.</p></td> 
  </tr> 
   </tbody> 
</table>


