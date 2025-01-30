---
title: Módulos de Microsoft SQL Server
description: Puede usar [!DNL Adobe Workfront Fusion] para conectarse a Microsoft SQL Server.
author: Becky
feature: Workfront Fusion
exl-id: 8f3293f7-8b45-4e42-8ad8-f9d4969b63fd
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 86%

---

# Módulos de [!DNL Microsoft SQL Server]

Puede usar [!DNL Adobe Workfront Fusion] para conectarse a [!UICONTROL Microsoft SQL Server].

## Requisitos de acceso

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
   <p>Requisito de licencia heredado: [!UICONTROL [!DNL Workfront Fusion] para automatización e integración de trabajo </p>
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

Para obtener información sobre las licencias de [!DNL Adobe Workfront Fusion], consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).



## Conexión con el servicio [!DNL Microsoft SQL Server] a [!DNL Workfront Fusion]

Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Microsoft SQL Server] a [!UICONTROL Workfront Fusion], consulte [Crear una conexión con [!UICONTROL Adobe Workfront Fusion]: instrucciones básicas](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

>[!NOTE]
>
>Algunas aplicaciones de Microsoft utilizan la misma conexión, que está vinculada a permisos de usuario individuales. Por lo tanto, al crear una conexión, la pantalla de consentimiento de permisos muestra los permisos que se otorgaron previamente a la conexión de este usuario, además de cualquier nuevo permiso que sea necesario para la aplicación actual.
>
>Por ejemplo, si a un usuario se le han otorgado permisos de &quot;Leer tabla&quot; a través del conector de Excel y luego crea una conexión en el conector de Outlook para leer correos electrónicos, la pantalla de consentimiento de permisos mostrará tanto el permiso de &quot;Leer tabla&quot; ya otorgado como el nuevo permiso requerido de &quot;Escribir correo electrónico&quot;.

## Uso de módulos [!DNL Microsoft SQL Server]

Puede ejecutar la lógica personalizada directamente en el servidor de base de datos mediante procedimientos almacenados. [!DNL Adobe Workfront Fusion] carga dinámicamente la interfaz de parámetros de entrada/salida y el conjunto de registros para que cada parámetro o valor se pueda asignar individualmente. Antes de comenzar a configurar el escenario, asegúrese de que la cuenta que está utilizando para conectarse a la base de datos tiene acceso de lectura a las vistas `INFORMATION_SCHEMA.ROUTINES` y `INFORMATION_SCHEMA.PARAMETERS`.

Cuando [!DNL Fusion] establece la conexión con el destino [!DNL SQL server], el usuario [!DNL Fusion] identifica el host (el nombre de dominio o la dirección IP donde está alojado el servidor) y el puerto. [!DNL Fusion] puede conectarse a cualquier host y puerto disponible.

Para obtener información acerca de las direcciones IP específicas que usa [!DNL Workfront Fusion], consulte [Direcciones IP para acceder a [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/set-up-ip-addresses-for-fusion.md)

Para obtener más información acerca de cómo crear un procedimiento almacenado, consulte la documentación de [!DNL Microsoft SQL Server].

>[!NOTE]
>
>[!DNL Workfront Fusion] no admite varios conjuntos de registros. Solo se procesa el primero.

## Solucionando problemas de error [!UICONTROL ER_LOCK_WAIT_TIMEOUT: Lock wait timeout exceeded; try restarting transaction]

Este error se produce cuando se modifican los mismos datos utilizando varios módulos. Se debe a transacciones SQL.

Cuando se ejecuta cualquier módulo SQL, se inicia una transacción. La transacción finaliza después de que el escenario se ejecute completamente.

Si otro módulo intenta acceder a los mismos datos, debe esperar hasta que finalice la transacción anterior. Dado que la primera transacción finalizará después de que finalice el escenario, la segunda transacción nunca podrá comenzar.

### Solución:

Activar la confirmación automática. La confirmación automática finaliza (confirma) todas las transacciones inmediatamente después de que se haya completado la ejecución del módulo.

1. Haga clic en el icono [!UICONTROL Scenario settings] ![icono de configuración de escenario](/help/workfront-fusion/references/apps-and-modules/assets/scenario-settings-icon.png)en la parte inferior de la pantalla.
1. Haga clic en la casilla **[!UICONTROL Auto commit]**.
1. Haga clic en **[!UICONTROL OK]** para guardar la configuración del escenario.
