---
title: 'Creación de una conexión: instrucciones básicas'
description: Muchos conectores de  [!DNL Adobe Workfront Fusion]  no requieren una configuración personalizada al crear una conexión. Este artículo describe el proceso de creación de conexiones predeterminado.
author: Becky
feature: Workfront Fusion
exl-id: e47ab4d9-6612-4d9a-a024-da508a8bbfb2
source-git-commit: ef1a96d9ef4c2c82eaf376c84188e3ed6ea7b2cf
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 49%

---

# Creación de una conexión: instrucciones básicas

Muchos conectores [!DNL Adobe Workfront Fusion] no requieren una configuración personalizada al crear una conexión. Este artículo describe el proceso de creación de conexiones predeterminado.

>[!NOTE]
>
>
>Si Adobe Workfront Fusion no ofrece una aplicación para el servicio web que le gustaría utilizar en su escenario, puede conectarse al servicio web utilizando [!DNL Workfront Fusion] módulos HTTP y Webhooks, como se explica en los siguientes artículos:
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
   <p>Actual: no se requiere licencia de Workfront Fusion.</p>
   <p>O</p>
   <p>Heredado: cualquiera </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Plan Select or Prime Workfront: su organización debe adquirir Adobe Workfront Fusion.</li><li>Plan Ultimate Workfront: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe adquirir Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Crear una conexión

Para crear una conexión dentro de un módulo de [!DNL Workfront Fusion]:

1. Haga clic en **[!UICONTROL Add]** junto al cuadro [!UICONTROL Connection] para abrir el panel **[!UICONTROL Create a connection]**.
1. (Opcional) Cambie el valor predeterminado **[!UICONTROL Connection name]**.
1. En el campo Entorno, seleccione si es un entorno de producción o de no producción. Esta información aparece en el área Conexiones de Fusion.
1. En el campo Tipo, seleccione si se trata de una cuenta de servicio o personal. Esta información aparece en el área Conexiones de Fusion.
1. (Condicional) Si la aplicación requiere una configuración de conexión avanzada, como un identificador, una clave o [!UICONTROL secret], escriba esa información.

   Es posible que deba hacer clic en **[!UICONTROL Show advanced settings]** para mostrar los campos donde puede introducir este tipo de información.

1. Haga clic en **[!UICONTROL Continue]**.
1. En la ventana de inicio de sesión que aparece, introduzca sus credenciales para iniciar sesión en la aplicación si aún no lo ha hecho.
1. (Condicional) Si aparece un botón **[!UICONTROL Allow]**, examine las acciones que podrá realizar el conector y, a continuación, haga clic en el botón para conectar la aplicación a [!DNL Workfront Fusion].

   >[!NOTE]
   >
   >Algunas aplicaciones de Microsoft utilizan la misma conexión, que está vinculada a permisos de usuario individuales. Por lo tanto, al crear una conexión, la pantalla de consentimiento de permisos muestra los permisos que se otorgaron previamente a la conexión de este usuario, además de cualquier nuevo permiso que sea necesario para la aplicación actual.
   >
   >Por ejemplo, si a un usuario se le han otorgado permisos de &quot;Leer tabla&quot; a través del conector de Excel y luego crea una conexión en el conector de Outlook para leer correos electrónicos, la pantalla de consentimiento de permisos mostrará tanto el permiso de &quot;Leer tabla&quot; ya otorgado como el nuevo permiso requerido de &quot;Escribir correo electrónico&quot;.
