---
title: Módulos de Microsoft SQL Server
description: Puede usar [!DNL Adobe Workfront Fusion] para conectarse a Microsoft SQL Server.
author: Becky
feature: Workfront Fusion
exl-id: 8f3293f7-8b45-4e42-8ad8-f9d4969b63fd
source-git-commit: ef1a96d9ef4c2c82eaf376c84188e3ed6ea7b2cf
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 83%

---

# Módulos de [!DNL Microsoft SQL Server]

Puede usar [!DNL Adobe Workfront Fusion] para conectarse a [!UICONTROL Microsoft SQL Server].

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
   <p>Actual: no se requiere licencia de Workfront Fusion.</p>
   <p>O</p>
   <p>Heredado: Workfront Fusion para la automatización e integración del trabajo </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Seleccione o paquete de Prime Workfront: su organización debe adquirir Adobe Workfront Fusion.</li><li>Paquete de Ultimate Workfront: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe adquirir Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de [!DNL Adobe Workfront Fusion], consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

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
