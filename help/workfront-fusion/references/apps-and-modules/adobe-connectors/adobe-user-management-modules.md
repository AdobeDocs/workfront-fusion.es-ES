---
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: apps-and-their-modules
title: Adobe de módulos de User Management
description: En un  [!DNL Adobe Workfront Fusion] escenario, puede automatizar los flujos de trabajo que administran a los usuarios en su cuenta de Adobe.
author: Becky
feature: Workfront Fusion
exl-id: e8fe8ec4-4b00-4c9a-81a5-acb2039b153b
source-git-commit: 640fec2de63ad59ba89fae5373f85b8147d8dac0
workflow-type: tm+mt
source-wordcount: '2323'
ht-degree: 15%

---

# Adobe de módulos de User Management

En un escenario de [!DNL Adobe Workfront Fusion], puede automatizar los flujos de trabajo que administran a los usuarios en su cuenta de Adobe.

Si necesita instrucciones sobre cómo crear un escenario, vea los artículos en [Crear un escenario: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, vea los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

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

+++

## Crear una conexión con Administración de usuarios de Adobe

Para crear una conexión para los módulos de [!DNL Adobe User Management]:

1. Haga clic en **[!UICONTROL Add]** junto al cuadro Conexión.

1. Rellene los campos siguientes:

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>Introduzca un nombre para esta conexión.</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>Seleccione si desea conectarse a un entorno de producción o de no producción.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>Seleccione si desea conectarse a una cuenta de servicio o a una personal.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Escriba su [!UICONTROL Adobe] [!UICONTROL Client ID]. Esto se puede encontrar en la sección de detalles [!UICONTROL Credentials] del [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Escriba su [!DNL Adobe] [!UICONTROL Client Secret]. Esto se puede encontrar en la sección de detalles [!UICONTROL Credentials] del [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL IMS Organization ID]</td>
        <td>Escriba sus credenciales de IMS [!DNL Adobe]. El identificador único de una organización. Es una cadena con el formato A495E53@AdobeOrg donde el prefijo antes de @ es un número hexadecimal. Puede encontrar este valor como parte de la ruta URL de la organización en el Admin Console o en la consola de adobe.io para su integración de User Management.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Additional scopes]</td>
        <td>Para cada ámbito adicional que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca el ámbito.</td>
        </tr>
      </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continue]** para guardar la conexión y volver al módulo.



## Módulos de administración de usuarios de Adobe y sus campos

Al configurar los módulos de Administración de usuarios de Adobe, Workfront Fusion muestra los campos que se indican a continuación. Junto con estos, pueden mostrarse campos adicionales de Adobe de Administración de usuarios, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)


* [Búsquedas](#searches)
* [Acciones del usuario](#user-actions)
* [Acciones del grupo de usuarios](#user-group-actions)
* [Otro](#other)

### Búsquedas

* [Obtener grupos de usuarios y perfiles de producto](#get-user-groups-and-product-profiles)
* [Obtener información del usuario](#get-user-information)
* [Obtener usuarios en un grupo de usuarios o un perfil de producto](#get-users-in-a-user-group-or-product-profile)
* [Obtener usuarios de una organización](#get-users-in-an-organization)

#### Obtener grupos de usuarios y perfiles de producto

Este módulo de búsqueda recupera una lista de todos los grupos de usuarios y perfiles de producto de su organización, junto con detalles sobre los grupos y perfiles.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Administración de usuarios de Adobe, consulte <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Crear una conexión con Administración de usuarios de Adobe</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Número máximo de resultados devueltos</td> 
   <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td> 
  </tr> 
 </tbody> 
</table>

#### Obtener información del usuario

Este módulo de búsqueda recupera los detalles de un único usuario de la organización, identificado por su dirección de correo electrónico.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Administración de usuarios de Adobe, consulte <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Crear una conexión con Administración de usuarios de Adobe</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Dirección de correo electrónico</td> 
   <td>Introduzca o asigne la dirección de correo electrónico del usuario cuyos detalles desea devolver. Para los usuarios de Adobe ID, Enterprise y federados por correo electrónico, esta debe ser la dirección de correo electrónico completa, incluido el dominio. En todos los casos, el parámetro no distingue entre mayúsculas y minúsculas.</td> 
  </tr> 
 </tbody> 
</table>

#### Obtener usuarios en un grupo de usuarios o un perfil de producto

Este módulo de búsqueda recupera una lista de todos los usuarios del grupo de usuarios o perfil de producto especificado, junto con detalles sobre los usuarios.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Administración de usuarios de Adobe, consulte <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Crear una conexión con Administración de usuarios de Adobe</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre del grupo</td> 
   <td>El grupo de usuarios, el nombre del perfil de producto o un grupo administrativo. Para un grupo de administración, el nombre puede ser uno de los grupos fijos <code>_org_admin</code>, <code>_deployment_admin</code> o <code>_support_admin</code>; o un grupo de administración específico de un grupo. Se identifican con un prefijo en el nombre del grupo, como <code>_admin_groupName</code>, <code>_product_admin_productName</code> o <code>_developer_groupName</code>. Si el grupo existe pero el grupo de administradores no, se devuelve una lista vacía.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Solo directo</td> 
   <td>Especifique si el campo de grupos de la estructura de usuario devuelta contiene solo los perfiles de producto de los que ese usuario es miembro directo. Si es false, devuelve todos los grupos (grupos de usuarios, perfiles de producto y grupos de administradores) que contienen al usuario, independientemente de si una asignación de derechos para un perfil de producto en particular se obtiene directamente (mediante asignación de usuarios) o indirectamente (mediante un grupo de usuarios que contiene al usuario asignado al perfil de producto). Si es true, devuelve todos los grupos de usuarios y grupos de administradores que contienen el usuario, pero solo aquellos perfiles de producto a los que se ha asignado explícitamente un derecho al usuario. Un usuario puede ser miembro directo e indirecto de un perfil de producto.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Excluir grupos</td> 
   <td>Especifique si la respuesta excluye la matriz de grupos de la devolución para cada usuario individual.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Estado</td> 
   <td>Esta opción solo se aplica a perfiles de producto. Seleccione activo para enumerar los usuarios que se han aprovisionado para el producto y tienen una licencia activa. Seleccione Inactivo para enumerar los usuarios que se han añadido al perfil del producto, pero que no tienen una licencia activa. Si se deja en blanco, el módulo devuelve todos los usuarios miembros independientemente de su estado de derecho.
</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Número máximo de resultados devueltos</td> 
   <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td> 
  </tr> 
 </tbody> 
</table>

#### Obtener usuarios de una organización

Este módulo de búsqueda devuelve todos los usuarios de la organización asociada con la conexión.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Administración de usuarios de Adobe, consulte <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Crear una conexión con Administración de usuarios de Adobe</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Número máximo de resultados devueltos</td> 
   <td>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</td> 
  </tr> 
 </tbody> 
</table>

### Acciones del usuario

* [Agregar un usuario como miembro de un grupo](#add-a-user-as-a-member-of-a-group)
* [Crear un usuario](#create-a-user)
* [Quitar un usuario de los grupos](#remove-a-user-from-groups)
* [Actualizar un usuario](#update-a-user)

#### Agregar un usuario como miembro de un grupo

Este módulo de acción agrega un usuario como miembro del grupo o grupos especificados. Este módulo puede añadir al usuario hasta cuatro grupos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Administración de usuarios de Adobe, consulte <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Crear una conexión con Administración de usuarios de Adobe</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Usuario</td> 
   <td>Introduzca o asigne el usuario que desea agregar a los grupos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Dominio</td> 
   <td>En el caso de los Federated ID que no sean direcciones de correo electrónico, introduzca el dominio al que pertenece el usuario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Grupos</td> 
   <td>Para cada grupo al que desee agregar al usuario, haga clic en <b>Agregar elemento</b> y escriba o asigne el grupo. Puede introducir hasta cuatro grupos y debe introducir al menos uno.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Uso de Adobe ID</td> 
   <td>Seleccione true para asegurarse de que el ID de usuario se interpreta como una referencia a un Adobe ID existente aunque exista un Enterprise o un Federated ID con el mismo nombre.</td> 
  </tr> 
 </tbody> 
</table>

#### Crear un usuario

Este módulo de acción crea un nuevo usuario en la organización.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Administración de usuarios de Adobe, consulte <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Crear una conexión con Administración de usuarios de Adobe</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de ID</td> 
   <td>Seleccione si desea crear un usuario con un Adobe ID, un Enterprise ID o un Federated ID. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Inicio de sesión</td> 
   <td>Si está creando un usuario con un Federated ID, seleccione el tipo de inicio de sesión.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Correo electrónico</td> 
   <td>Introduzca o asigne la dirección de correo electrónico del nuevo usuario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Dominio</td> 
   <td>Si está creando un usuario con un Federated ID con un inicio de sesión basado en el dominio, introduzca o asigne el dominio.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Usuario</td> 
   <td>Si está creando un usuario con un Federated ID con un inicio de sesión basado en el dominio, introduzca o asigne el usuario que representará este nuevo usuario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre</td> 
   <td>Introduzca o asigne el nombre del usuario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Apellido</td> 
   <td>Introduzca o asigne los apellidos del usuario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">País</td> 
   <td>Introduzca o asigne el código de país ISO de dos caracteres. Esto no se puede cambiar una vez creado el usuario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Opción</td> 
   <td>Seleccione la acción que desea realizar si el usuario ya existe en la organización. Si no se selecciona ninguna opción y el usuario ya existe, el módulo devuelve un error.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Uso de Adobe ID</td> 
   <td>Cuando es true, el ID de usuario se interpreta como una referencia a un Adobe ID existente aunque exista un Enterprise o un Federated ID con el mismo nombre.</td> 
  </tr> 
 </tbody> 
</table>

#### Quitar un usuario de los grupos

Este módulo de acción elimina la pertenencia de un usuario a los grupos especificados. Puede eliminar un usuario de hasta cuatro grupos a la vez.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Administración de usuarios de Adobe, consulte <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Crear una conexión con Administración de usuarios de Adobe</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Usuario</td> 
   <td>Introduzca o asigne el usuario que desea eliminar de los grupos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Dominio</td> 
   <td>En el caso de los Federated ID que no sean direcciones de correo electrónico, introduzca el dominio al que pertenece el usuario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Grupos</td> 
   <td>Para cada grupo del que desee quitar el usuario, haga clic en <b>Agregar elemento</b> y escriba o asigne el grupo. Puede introducir hasta cuatro grupos y debe introducir al menos uno.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Uso de Adobe ID</td> 
   <td>Seleccione true para asegurarse de que el ID de usuario se interpreta como una referencia a un Adobe ID existente aunque exista un Enterprise o un Federated ID con el mismo nombre.</td> 
  </tr> 
 </tbody> 
</table>



#### Actualizar un usuario

Este módulo de acción actualiza un usuario existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Administración de usuarios de Adobe, consulte <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Crear una conexión con Administración de usuarios de Adobe</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Usuario</td> 
   <td>Introduzca o asigne el ID del usuario que desea actualizar. Esta es la dirección de correo electrónico del usuario, como <code>user@example.com</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">Dominio</td> 
   <td>Si va a actualizar un usuario con un Federated ID que no sea una dirección de correo electrónico, introduzca o asigne el dominio al que pertenece el usuario para identificarlo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Correo electrónico</td> 
   <td>Introduzca o asigne la nueva dirección de correo electrónico del usuario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre</td> 
   <td>Introduzca o asigne el nombre del usuario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Apellido</td> 
   <td>Introduzca o asigne los apellidos del usuario.</td> 
  </tr> 
 </tbody> 
</table>

### Acciones del grupo de usuarios

* [Agregar pertenencias a un grupo de usuarios](#add-memberships-for-a-user-group)
* [Crear un grupo de usuarios](#create-a-user-group)
* [Eliminar un grupo de usuarios](#delete-a-user-group)
* [Eliminación de suscripciones de un grupo de usuarios](#remove-memberships-for-a-user-group)
* [Actualizar un grupo de usuarios](#update-a-user-group)

#### Agregar pertenencias a un grupo de usuarios

Este módulo de acción agrega usuarios y perfiles de producto a un grupo de usuarios. Los usuarios agregados al grupo de usuarios obtienen derechos para todos los perfiles de producto del grupo de usuarios. Añadir un perfil de producto da derecho a ese perfil a los usuarios del grupo de usuarios.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Administración de usuarios de Adobe, consulte <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Crear una conexión con Administración de usuarios de Adobe</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre del grupo</td> 
   <td>Introduzca o asigne un nombre al grupo del que desee quitar los usuarios o perfiles.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Usuarios</td> 
   <td>Para cada usuario que desee agregar, haga clic en <b>Agregar usuario</b> e introduzca la dirección de correo electrónico del usuario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Perfiles</td> 
   <td>Para cada perfil que desee agregar al grupo, haga clic en <b>Agregar usuario</b> e introduzca el nombre del perfil</td> 
  </tr> 
 </tbody> 
</table>

#### Crear un grupo de usuarios

Este módulo de acción crea un nuevo grupo de usuarios. Si ya existe un grupo con el nombre dado, el módulo puede actualizar el grupo existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Administración de usuarios de Adobe, consulte <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Crear una conexión con Administración de usuarios de Adobe</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre del grupo</td> 
   <td>Introduzca o asigne un nombre para el nuevo grupo de usuarios.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Descripción</td> 
   <td>Escriba o asigne una descripción para el nuevo grupo de usuarios.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Opción</td> 
   <td>Seleccione la acción que desea realizar si el grupo de usuarios ya existe en la organización. Si no se selecciona ninguna opción y el grupo de usuarios ya existe, el módulo devuelve un error.</td> 
  </tr> 
 </tbody> 
</table>

#### Eliminar un grupo de usuarios

Este módulo de acción elimina un grupo de usuarios existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Administración de usuarios de Adobe, consulte <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Crear una conexión con Administración de usuarios de Adobe</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre del grupo</td> 
   <td>Introduzca o asigne el nombre del grupo que desea eliminar.</td> 
  </tr> 
 </tbody> 
</table>

#### Eliminación de suscripciones de un grupo de usuarios

Este módulo de acción elimina usuarios o perfiles de un grupo de usuarios.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Administración de usuarios de Adobe, consulte <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Crear una conexión con Administración de usuarios de Adobe</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre del grupo</td> 
   <td>Introduzca o asigne un nombre al grupo del que desee quitar los usuarios o perfiles.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Usuarios</td> 
   <td>Para cada usuario que desee eliminar, haga clic en <b>Agregar usuario</b> e introduzca la dirección de correo electrónico del usuario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Perfiles</td> 
   <td>Para cada perfil que desee quitar del grupo, haga clic en <b>Agregar usuario</b> e introduzca el nombre del perfil</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Uso de Adobe ID</td> 
   <td>Cuando es true, el ID de usuario se interpreta como una referencia a un Adobe ID existente aunque exista un Enterprise o un Federated ID con el mismo nombre.</td> 
  </tr> 
 </tbody> 
</table>

#### Actualizar un grupo de usuarios

Este módulo de acción actualiza un grupo de usuarios existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con Administración de usuarios de Adobe, consulte <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Crear una conexión con Administración de usuarios de Adobe</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre del grupo original</td> 
   <td>Introduzca o asigne el nombre actual del grupo que desea actualizar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nuevo nombre de grupo</td> 
   <td>Introduzca o asigne el nuevo nombre que desea que tenga el grupo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre del grupo original</td> 
   <td>Introduzca o asigne la descripción actualizada del grupo.</td> 
  </tr> 
 </tbody>

### Otro

Este módulo de acción realiza una llamada personalizada a la API de administración de usuarios de Adobe.

#### Realizar una llamada de API personalizada

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con Administración de usuarios de Adobe, consulte <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Crear una conexión con Administración de usuarios de Adobe</a> en este artículo.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>URL</p>
      </td>
      <td>
        <p>Introduzca una ruta relativa a <code>https://usermanagement.adobe.io/v2/usermanagement/</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>Método</p>
      </td>
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de solicitud HTTP</a>.</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">Encabezados</td>
      <td>
        <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p>
        <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p>
        <p>[!DNL Workfront Fusion] añade automáticamente encabezados de autorización y encabezados x-api-key.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">Cadena de consulta  </td>
      <td>
        <p>Introduzca la cadena de consulta de la solicitud.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">Cuerpo</td>
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la instrucción condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>
