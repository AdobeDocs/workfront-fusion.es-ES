---
title: Módulos MariaDB
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan  [!DNL MariaDB], así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
draft: Probably
feature: Workfront Fusion
exl-id: 41179cfe-c0f9-4d18-ab7e-374670ac688b
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 38%

---

# Módulos de [!DNL MariaDB]

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!DNL MariaDB], así como conectarlo a varias aplicaciones y servicios de terceros.

Para obtener instrucciones sobre cómo crear un escenario, vea los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

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
   <td> <p>Nuevo: estándar</p><p>O</p><p>Actual: Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion**</td> 
   <td>
   <p>Actual: No se requiere licencia de Workfront Fusion</p>
   <p>O</p>
   <p>Heredado: Workfront Fusion para la automatización e integración del trabajo </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Seleccione o paquete de Prime Workfront: su organización debe adquirir Adobe Workfront Fusion.</li><li>Paquete de Ultimate Workfront: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe comprar Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Para utilizar módulos de [!DNL MariaDB], debe disponer de una cuenta de [!DNL MariaDB].

## Conexión de [!DNL MariaDB] a Workfront Fusion

Puede crear una conexión con su cuenta de [!DNL MariaDB] directamente desde un módulo de [!DNL MariaDB].

1. En cualquier módulo de [!DNL MariaDB], haga clic en **[!UICONTROL Añadir]** junto al campo [!UICONTROL Conexión].
1. Configure los campos siguientes:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td> <p>Introduzca un nombre para la nueva conexión.</p> </td> 
     </tr> 
        <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>Seleccione si esta conexión es para un entorno de producción o de no producción.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>Seleccione si desea conectarse a una cuenta de servicio o a una personal.</td>
        </tr>
     <tr> 
      <td role="rowheader">[!UICONTROL Host]</td> 
      <td> <p>Introduzca la dirección IP o el nombre de host de la instancia de base de datos. Se debe poder acceder a este host desde fuera de la red.</p> <p>Ejemplo: <code>[!DNL mariadb.hwoh2j5h.us-east-1.rds.amazon.com]</code></p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Port]</td> 
      <td>El puerto predeterminado es 3306. Si utiliza un puerto no estándar, establezca este número en el puerto. </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Base de datos &#x200B;]</td> 
      <td>Introduzca el nombre de la base de datos con la que desea interactuar.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL User]</td> 
      <td>Escriba su nombre de usuario.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Password]</td> 
      <td>Introduzca su contraseña.</td> 
     </tr> 
    </tbody> 
   </table>

1. Haga clic en **[!UICONTROL Continuar]** para crear la conexión y volver al módulo.

## Módulos de [!DNL MariaDB] y sus campos

Al configurar módulos de [!DNL MariaDB], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL MariaDB] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Ejecución de una consulta (avanzada)

Este módulo de acción recupera información de la base de datos, en función de la consulta proporcionada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL MariaDB] a Workfront Fusion, consulte <a href="#connect-mariadb-to-workfront-fusion" class="MCXref xref">Conectar [!DNL MariaDB] a Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td> <p>Introduzca la consulta SQL que desea que utilice el módulo para recuperar datos.</p> <p>Importante: Las variables utilizadas en la consulta no se sanean. Asegúrese de sanear las variables correctamente para evitar la inyección de SQL.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Seleccionar filas de una tabla (avanzado)]

Este módulo lee registros de la base de datos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL MariaDB] a Workfront Fusion, consulte <a href="#connect-mariadb-to-workfront-fusion" class="MCXref xref">Conectar [!DNL MariaDB] a Workfront Fusion</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Table]</td> 
   <td> <p>Seleccione la tabla que contiene los registros que desea leer.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td> <p>Configure el filtro mediante el cual desea seleccionar filas</p> 
    <ul> 
     <li> <p>Seleccione el campo por el que desea buscar</p> </li> 
     <li> <p>Seleccione el operador que desee utilizar para la búsqueda</p> </li> 
     <li> <p>Introduzca o asigne el valor que desea buscar.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort] </td> 
   <td> <p>Para cada nivel por el que desee ordenar los resultados, haga clic en <strong>[!UICONTROL Agregar elemento]</strong> y, a continuación, seleccione el campo por el que desea ordenar los resultados y si desea ordenar de forma ascendente o descendente</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>
