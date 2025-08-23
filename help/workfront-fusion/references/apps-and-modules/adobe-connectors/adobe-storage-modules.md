---
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: apps-and-their-modules
title: Módulos de almacenamiento de Adobe
description: En un escenario de Adobe Workfront Fusion, debe crear y administrar proyectos en Adobe Admin Console.
author: Becky
feature: Workfront Fusion
exl-id: 78ee905f-4713-44a4-bffb-c64cdb3665c2
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1400'
ht-degree: 17%

---

# Módulos de almacenamiento de Adobe

En un escenario de Adobe Workfront Fusion, puede crear y administrar proyectos en Adobe Admin Console.

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

## Crear una conexión al almacenamiento de Adobe

La creación de una conexión a Adobe Storage requiere cierta configuración tanto en Adobe Developer Console como en Fusion.

### Configuración del proyecto en Adobe Developer Console

Debe agregar la API al proyecto en Adobe Developer Console.

1. Abra el proyecto en Adobe Developer Console.
1. Haga clic en **Agregar al proyecto** y seleccione **API**.
1. En la lista de API disponibles, seleccione **Adobe Cloud Platform y la API de Collaboration**.
1. En la pantalla Seleccionar tipo de autenticación, seleccione **Servidor a servidor OAuth** y haga clic en **Siguiente**.
1. Añada un nombre para la credencial.
1. Haga clic en **Siguiente** y, a continuación, haga clic en **Guardar la API configurada**.
1. Tome nota de las credenciales proporcionadas, que utilizará al configurar la conexión en Workfront Fusion.
1. Continuar a [Haz que tu cuenta técnica sea un administrador en Adobe Admin Console](#make-your-technical-account-an-admin-in-the-adobe-admin-console).

### Convierta su cuenta técnica en administrador en Adobe Admin Console

En la página de Adobe Admin Console, seleccione la pestaña Productos en la barra de navegación superior y, a continuación, seleccione Workfront Fusion

1. Busque y copie la dirección de correo electrónico del usuario de la cuenta técnica de su organización.
1. Si aparece una lista, seleccione el vínculo en la parte superior.
1. Esta es la instancia de producción en la que trabajan los usuarios.
1. En la lista que se muestra, con la pestaña Perfiles de producto seleccionada, haga clic en el nombre del vínculo Perfil de producto de Workfront.

   Esta lista incluye todos los usuarios que ya están asignados a la instancia de producción de Workfront.

1. Seleccione la ficha **Administradores** situada encima de la lista de usuarios.
1. Seleccione **Agregar administrador**.
1. En el cuadro Agregar administradores de perfil de producto, escriba las direcciones de correo electrónico de la cuenta técnica y, a continuación, seleccione **Guardar**.

   La cuenta técnica se convierte en administrador.

1. Continuar a [Crear la conexión en Workfront Fusion](#create-the-connection-in-workfront-fusion).

### Creación de la conexión en Workfront Fusion

Para crear una conexión para los módulos de [!DNL Adobe Storage]:

1. En cualquier módulo, haga clic en **[!UICONTROL Agregar]** junto al cuadro Conexión.

1. Rellene los campos siguientes:

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">[!UICONTROL Connection type]</td>
        <td>Seleccione <code>Server to server</code>.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>Introduzca un nombre para esta conexión.</p>
        </td>
        </tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Introduzca el [!UICONTROL Adobe] [!UICONTROL Client ID]. Se encuentra en la sección [!UICONTROL Credential details] del proyecto en [!DNL Adobe Developer Console].</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Introduzca su [!DNL Adobe] [!UICONTROL Client Secret].  Se encuentra en la sección [!UICONTROL Credential details] del proyecto en [!DNL Adobe Developer Console].</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL IMS Organization ID]</td>
        <td>Introduzca o asigne su ID de organización de IMS de Adobe. Es una cadena con el formulario <code> 123abc@AdobeOrg</code>, donde la sección antes de @ es un número hexadecimal. Puede encontrar este valor como parte de la ruta URL para su organización en Adobe Admin Console o en la consola de Adobe.IO para su integración de administración de usuarios.</td>
        </tr>
      </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.

## Módulos de almacenamiento de Adobe y sus campos

Al configurar los módulos de Administración de usuarios de Adobe, Workfront Fusion muestra los campos que se indican a continuación. Junto con estos, pueden mostrarse campos adicionales de Administración de usuarios de Adobe, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Tiendas de ESM](#esm-stores)
* [Invitaciones](#invitations)
* [Otro](#other)

### Tiendas de ESM

* [Crear una tienda de ESM](#create-an-esm-store)
* [Eliminar un almacén de ESM](#delete-an-esm-store)
* [Descartar un almacén de ESM](#discard-an-esm-store)
* [Restaurar un almacén de ESM](#restore-an-esm-store)

#### Crear una tienda de ESM

Este módulo de acción configura un nuevo almacén de Enterprise Storage Management (ESM) para organizar y administrar los recursos críticos para la empresa.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con el almacenamiento de Adobe, consulte <a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Crear una conexión con el almacenamiento de Adobe</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre del proyecto</td> 
   <td>Escriba o asigne un nombre para el nuevo proyecto.</td> 
  </tr> 
 </tbody> 
</table>

#### Eliminar un almacén de ESM

Este módulo de acción elimina permanentemente un almacén de ESM existente y todos sus datos asociados. Esta acción no se puede deshacer.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con el almacenamiento de Adobe, consulte <a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Crear una conexión con el almacenamiento de Adobe</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de tienda</td> 
   <td>Introduzca o asigne el ID de la tienda que desea eliminar.</td> 
  </tr> 
 </tbody> 
</table>

#### Descartar un almacén de ESM

Este módulo de acción marca un almacén de EMS para su eliminación, lo que permite un período de gracia antes de la eliminación permanente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con el almacenamiento de Adobe, consulte <a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Crear una conexión con el almacenamiento de Adobe</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de tienda</td> 
   <td>Introduzca o asigne el ID de la tienda que desea descartar.</td> 
  </tr> 
 </tbody> 
</table>

#### Restaurar un almacén de ESM

Este módulo de acción recupera un almacén de ESM eliminado anteriormente y restaura el acceso a sus datos y configuraciones.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con el almacenamiento de Adobe, consulte <a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Crear una conexión con el almacenamiento de Adobe</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de tienda</td> 
   <td>Introduzca o asigne el ID del almacén que desea restaurar.</td> 
  </tr> 
 </tbody> 
</table>

### Invitaciones

#### Invitar al usuario

Este módulo de acción envía una invitación para conceder a un nuevo usuario acceso a un almacén de ESM específico, lo que permite la colaboración y la administración de archivos.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td>Para obtener instrucciones sobre cómo crear una conexión con el almacenamiento de Adobe, consulte <a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Crear una conexión con el almacenamiento de Adobe</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Dirección de correo electrónico</td> 
   <td>Introduzca o asigne la dirección de correo electrónico del usuario al que desea invitar a la tienda.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID del recurso</td> 
   <td>Introduzca o asigne el ID del recurso al que desea invitar al usuario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Función</td> 
   <td>Seleccione la función que desea que el usuario recién invitado tenga para el recurso.<ul><li>Propietario</li><li>Editor</li><li>Visualizador</li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">Puede comentar</td> 
   <td>Active esta opción para permitir que el usuario realice comentarios en el recurso.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Se puede compartir</td> 
   <td>Active esta opción para permitir que el usuario comparta el recurso con otro usuario.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Aceptación requerida</td> 
   <td>Habilite esta opción para asegurarse de que el usuario debe aceptar la invitación antes de poder colaborar en el recurso.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Uso de montajes</td> 
   <td>Active esta opción si se debe crear un punto de montaje en el recurso para el invitado. Para activar esta opción, debe activarse la opción Aceptación requerida.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de notificación</td> 
   <td>Introduzca o asigne el tipo de notificación de Adobe que desea utilizar para notificar la invitación al usuario. Si se deja vacío, el tipo de notificación se basa en el tipo MIME del recurso.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre de plantilla</td> 
   <td>Introduzca o asigne el ID de la oficina de correos de Adobe de la plantilla que desee utilizar para el correo electrónico de invitación.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Configuración regional</td> 
   <td>Introduzca la configuración regional del usuario en forma de código de idioma y código de país. <p>Ejemplo: <code>en-us</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Externo</td> 
   <td>Establezca esta opción como verdadera si desea enviar notificaciones mediante un sistema externo al servicio de invitaciones de Adobe. La notificación externa solo se admite cuando no se requiere aceptación.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de recurso</td> 
   <td>Introduzca o asigne el tipo de recurso.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Mensaje</td> 
   <td>Introduzca o asigne un mensaje para incluirlo en el correo electrónico de invitación.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL de destino</td> 
   <td>Introduzca o asigne la dirección URL que el invitado puede utilizar para ver el recurso.</td> 
  </tr> 
 </tbody> 
</table>

### Otro

#### Realizar una llamada de API personalizada

Este módulo de acción realiza una solicitud HTTP personalizada a la API de almacenamiento de Adobe.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Conexión</td>
   <td>Para obtener instrucciones sobre cómo crear una conexión con el almacenamiento de Adobe, consulte <a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Crear una conexión con el almacenamiento de Adobe</a> en este artículo.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>URL</p>
      </td>
      <td>
        <p>Introduzca una ruta relativa a <code>https://ccprojects.adobe.io/api/v3/.</code></p>
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
        <p>Workfront Fusion añade automáticamente encabezados de autorización y encabezados x-api-key.</p>
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
