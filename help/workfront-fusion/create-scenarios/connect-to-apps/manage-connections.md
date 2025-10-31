---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: connections-annd-webhooks
title: Administrar conexiones
description: Para la mayoría de las aplicaciones, es necesario crear una conexión a través de la cual Adobe Workfront Fusion pueda comunicarse con el servicio de terceros proporcionado según la configuración del escenario específico.
author: Becky
feature: Workfront Fusion
exl-id: 26d7caad-8e12-4f04-ac7c-f71686c90ee6
source-git-commit: 93d06cb917680f9cabc1bad6be0f9cd843449d07
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 21%

---

# Administrar conexiones

Una conexión representa la autorización y los permisos que Fusion utiliza para acceder a la aplicación. Puede crear una o más conexiones para cada aplicación y utilizar la misma conexión en varios módulos o escenarios.

Puede administrar estas conexiones en el área Conexiones.

Para obtener más información sobre las conexiones, consulte [Información general sobre la conexión](/help/workfront-fusion/get-started-with-fusion/understand-fusion/connection-overview.md).

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront</td> 
   <td> <p>Cualquier paquete de flujo de trabajo de Adobe Workfront y cualquier paquete de integración y automatización de Adobe Workfront</p><p>Workfront Ultimate</p><p>Paquetes Workfront Prime y Select, con una compra adicional de Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencias de Adobe Workfront</td> 
   <td> <p>Estándar</p><p>Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion</td> 
   <td>
   <p>Basado en operaciones: no se requiere licencia de Workfront Fusion</p>
   <p>Basado en conectores (heredado): para conectarse a aplicaciones fuera de la familia de productos de Workfront, debe tener Workfront Fusion para la automatización e integración del trabajo </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete Select o Prime Workfront que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Ver y administrar conexiones

Puede administrar todas las conexiones desde el área Conexiones.

>[!NOTE]
>
>Las conexiones son propiedad de los equipos. Si no encuentra la conexión que busca, compruebe que está viendo el equipo correcto.
>
>Para seleccionar un nuevo equipo, haga clic en el nombre del equipo en el panel de navegación izquierdo y seleccione un nuevo equipo.

1. Para abrir el área Conexiones, haga clic en **Conexiones** ![Icono de conexiones](assets/connections-icon.png) en el panel de navegación izquierdo.
1. Busque la conexión que desea administrar y, a continuación, realice uno o más de los siguientes pasos en la línea correspondiente a esa conexión.
1. (Opcional) Asigne un entorno y un tipo de conexión haciendo clic en los desplegables **Entorno** y **Tipo** y seleccionando una opción.
1. (Opcional) Para ver qué permisos se concedieron a Workfront Fusion para la conexión, haga clic en el icono Ver ![Ver permisos de conexión](assets/view-connection-permissions.png) para esa conexión.
1. (Opcional) Para cambiar el nombre de una conexión, resalte el nombre de la conexión y escriba el nuevo nombre.
1. (Opcional) Para volver a autorizar una conexión, marque la casilla que hay junto a la conexión y luego haga clic en **Volver a autorizar**, cerca de la parte inferior de la pantalla.
1. (Opcional) Para eliminar una conexión, marque la casilla que hay junto a la conexión, haga clic en **Eliminar**, cerca de la parte inferior de la pantalla, y después haga clic en **Realmente?**.
1. (Opcional) Para verificar que la conexión al servicio se estableció correctamente, marque la casilla de verificación que hay junto a la conexión y luego haga clic en **Verificar** cerca de la parte inferior de la pantalla.
1. (Opcional) Para ver los escenarios activos que utilizan esta conexión, marque la casilla que hay junto a la conexión y, a continuación, haga clic en **Recuperar escenarios activos**. A continuación, puede hacer clic en un escenario de la lista Escenarios activos para ir a ese escenario.

## Renovación de una conexión

Workfront Fusion generalmente obtiene derechos de acceso a un servicio determinado durante un período de tiempo ilimitado. Algunas aplicaciones requieren que el permiso de acceso se renueve después de un determinado período de tiempo. En estos casos, Workfront Fusion le notifica por correo electrónico poco antes de que expiren sus derechos de acceso.

Para renovar una conexión:

1. Para abrir el área Conexiones, haga clic en **Conexiones** ![Icono de conexiones](assets/connections-icon.png) en el panel de navegación izquierdo.
1. Busque la conexión que desea renovar.
1. En la línea de esa conexión, marca la casilla que hay junto a la conexión y luego haz clic en **Volver a autorizar** cerca de la parte inferior de la pantalla.

## Recursos

* Para obtener más información sobre los metadatos de conexión, como el entorno y el tipo, consulte [Metadatos de conexión](/help/workfront-fusion/references/connections/connection-metadata.md).
