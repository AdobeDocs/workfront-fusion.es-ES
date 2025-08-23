---
content-type: reference
title: 'Configurar y administrar organizaciones y equipos: índice de artículos'
description: Esta sección contiene artículos relacionados con la configuración y gestión de organizaciones y equipos en Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: aa570f28-7387-47c5-9968-e3554921b0f5
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 56%

---

# Eliminar usuarios mediante la [!DNL Adobe Admin Console]

Solo puede quitar un usuario de Adobe Workfront Fusion y dejar el acceso a cualquier otro perfil de producto de [!DNL Adobe], o bien puede quitar el usuario de [!DNL Adobe Admin Console] por completo.

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
   <td> <p>Nuevo: estándar</p><p>O</p><p>Actual: [!UICONTROL Work] o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion**</td> 
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
  <tr data-mc-conditions=""> 
   <td role="rowheader">Configuraciones de nivel de acceso*</td> 
   <td> 
     <p>Debe ser administrador de [!DNL Adobe Admin Console] para su organización.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Eliminar un usuario solo de Adobe Workfront Fusion

Puede eliminar un usuario de Workfront Fusion sin modificar los demás permisos de productos de Adobe.

Para obtener instrucciones, consulte &quot;Quitar usuarios y grupos de usuarios de un producto&quot; en el artículo [Administrar productos en Admin Console](https://helpx.adobe.com/es/enterprise/using/manage-products.html).

## Desactivar un usuario en todos los productos de [!DNL Adobe Admin Console]

Para eliminar un usuario, debe desactivarlo a través de [!DNL Adobe Admin Console].

Un usuario se desactiva de la [!DNL Adobe Admin Console] cuando se da una de las siguientes circunstancias:

* El usuario se elimina de un producto o perfil de producto, y no se asigna a ningún otro producto o perfil de producto.
* El usuario se elimina de un grupo vinculado a un perfil de producto y no se incluye en ningún otro grupo vinculado a un perfil de producto.
* El usuario se elimina de un perfil de producto y no se asigna a otro perfil de producto.
* El usuario se elimina o desactiva en la organización que incluye Workfront Fusion.

  Para obtener instrucciones, consulte la sección &quot;Eliminar usuarios&quot; en [Administrar usuarios individualmente](https://helpx.adobe.com/enterprise/using/manage-users-individually.html?lang=es).

En Workfront Fusion, la desactivación afecta al usuario de una de las siguientes maneras:

* Si el usuario está en una sola organización, se desactiva.
* Si el usuario se encuentra en más de una organización, se eliminará de la organización en la que se modificó el usuario en el [!DNL Adobe Admin Console].
* Tenga en cuenta lo siguiente al eliminar un usuario.

### Consideraciones al eliminar un usuario en Workfront Fusion

Tenga en cuenta lo siguiente al eliminar un usuario.

* Cuando se elimina un usuario, se eliminan sus conexiones, claves y enlaces web.
* Cualquier escenario que pertenezca al usuario se transfiere al propietario de la organización. Las conexiones en estos escenarios deben actualizarse, ya que las conexiones que pertenecen al usuario ya no son válidas.
* Si el usuario eliminado es propietario de aplicaciones o plantillas públicas, estas se transfieren al propietario de la organización. Si no hay ningún propietario de la organización, las aplicaciones o plantillas públicas se transfieren a otro usuario.
