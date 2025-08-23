---
title: 'Creación de una conexión: instrucciones básicas'
description: Muchos conectores de Adobe Workfront Fusion no requieren una configuración personalizada al crear una conexión. Este artículo describe el proceso de creación de conexiones predeterminado.
author: Becky
feature: Workfront Fusion
exl-id: e47ab4d9-6612-4d9a-a024-da508a8bbfb2
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 41%

---

# Creación de una conexión: instrucciones básicas

Muchos conectores de Adobe Workfront Fusion no requieren una configuración personalizada al crear una conexión. Este artículo describe el proceso de creación de conexiones predeterminado.

>[!NOTE]
>
>
>Si Adobe Workfront Fusion no ofrece una aplicación para el servicio web que le gustaría utilizar en su situación, puede conectarse al servicio web mediante los módulos HTTP y Webhooks de Workfront Fusion, como se explica en los siguientes artículos:
>
>* [Conecte Adobe Workfront Fusion a un servicio web que use la autorización de token de API](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-wf-web-service-uses-api-token-auth.md)
>* [Configurar un webhook para un servicio web sin un conector](/help/workfront-fusion/create-scenarios/add-modules/receive-a-webhook-from-a-web-service.md)

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront 
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
   <p>Heredado: cualquiera </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Plan Select or Prime Workfront: su organización debe comprar Adobe Workfront Fusion.</li><li>Plan Ultimate Workfront: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe comprar Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Crear una conexión

Para crear una conexión con una aplicación determinada, debe estar en un módulo para esa aplicación. Por ejemplo, para crear una conexión con Workfront, debe estar en un módulo de Workfront.

Para crear una conexión dentro de un módulo de Workfront Fusion:

1. En cualquier módulo de la aplicación determinada, haga clic en **[!UICONTROL Agregar]** junto al cuadro [!UICONTROL Conexión] para abrir el panel **[!UICONTROL Crear una conexión]**.
1. (Opcional) Cambie el **[!UICONTROL Nombre de conexión]** predeterminado.
1. En el campo Entorno, seleccione si es un entorno de producción o de no producción.
1. En el campo Tipo, seleccione si se trata de una cuenta de servicio o personal.
1. (Condicional) Si la aplicación requiere configuraciones avanzadas de conexión, como un ID, clave o [!UICONTROL secreto], ingrese esa información.

   Es posible que tengas que hacer clic en **[!UICONTROL Mostrar configuración avanzada]** para mostrar los campos donde puedes introducir este tipo de información.

1. Haga clic en **[!UICONTROL Continuar]**.
1. En la ventana de inicio de sesión que aparece, introduzca sus credenciales para iniciar sesión en la aplicación si aún no lo ha hecho.
1. (Condicional) Si aparece un botón **[!UICONTROL Permitir]**, examine las acciones que podrá realizar el conector y, a continuación, haga clic en el botón para conectar la aplicación a Workfront Fusion.

   >[!NOTE]
   >
   >* Los campos Entorno y Tipo son solo informativos y no cambian la funcionalidad de la conexión. Esta información aparece en el área Conexiones de Fusion, lo que le permite determinar qué conexión utilizar para un caso de uso determinado en su organización.
   >* Algunas aplicaciones de Microsoft utilizan la misma conexión, que está vinculada a permisos de usuario individuales. Por lo tanto, al crear una conexión, la pantalla de consentimiento de permisos muestra los permisos que se otorgaron previamente a la conexión de este usuario, además de cualquier nuevo permiso que sea necesario para la aplicación actual.
   >
   >   Por ejemplo, si a un usuario se le han otorgado permisos de &quot;Leer tabla&quot; a través del conector de Excel y luego crea una conexión en el conector de Outlook para leer correos electrónicos, la pantalla de consentimiento de permisos mostrará tanto el permiso de &quot;Leer tabla&quot; ya otorgado como el nuevo permiso requerido de &quot;Escribir correo electrónico&quot;.
