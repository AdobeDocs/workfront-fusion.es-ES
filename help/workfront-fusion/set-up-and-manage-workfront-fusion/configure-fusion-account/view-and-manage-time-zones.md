---
title: Visualización y administración de zonas horarias
description: Obtenga información sobre cómo ver y administrar la configuración de zona horaria en Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 9910d9b4-5a7a-4f4a-9e66-8600d3b6c785
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: 39c34b17e766678e187837e07c90b67f365a4f1d
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 17%
---
# Visualización y administración de zonas horarias

Adobe Workfront Fusion incluye controles para las zonas horarias en la organización y en el nivel de usuario.

* Zonas horarias de organización: los escenarios utilizan zonas horarias de organización para determinar cuándo se produce un evento programado.

* Husos horarios del usuario: los husos horarios del usuario determinan la hora que se muestra a un usuario.

>[!BEGINSHADEBOX]

Ejemplo:

Una organización tiene su sede en Nueva York y la hora de la organización se establece en UTC-5 (América/Nueva York). El escenario A es propiedad de esta organización y está programado para ejecutarse a las 9:00 a. m. todos los días. El escenario se ejecuta a las 9:00 AM en el huso horario de Nueva York.

Un usuario de esta organización vive en Los Ángeles y tiene la zona horaria del usuario establecida en UTC-8 (América/Los Ángeles). Cuando este usuario ve el historial de ejecución del escenario A, ve que el escenario se ejecutó a las 6:00 a. m. Aunque el escenario se ejecutó según la hora de Nueva York, el usuario ve la hora convertida a su propia zona horaria.

>[!ENDSHADEBOX]



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
   <p>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
  <tr> 
   <td role="rowheader">Nivel de acceso</td> 
   <td> Debe ser propietario o administrador de una organización para editar la zona horaria de dicha organización. </td>
   </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Ver y administrar la zona horaria del usuario

1. En Fusion, haga clic en el icono de su perfil de Adobe en la parte superior derecha de la pantalla.
1. En el menú que se abre, seleccione **Perfil Fusion**.
1. Seleccione la ficha **Opciones de zona horaria**. Las pestañas se encuentran directamente debajo de su nombre.
Se abre la lista Opciones de zona horaria.
1. En el área Web de la lista Opciones de huso horario, busque su nombre.

   La configuración de la zona horaria del usuario actual se muestra a la derecha de su nombre.
1. Para editar la zona horaria, haga clic en Editar ![Editar zona horaria](assets/edit-timezone-icon.png) junto a la zona horaria.
1. En la ventana Cambiar detalles, en el campo **Zona horaria**, seleccione la que desee establecer para usted.
1. Haga clic en **Guardar**.


## Ver y administrar la zona horaria de su organización

>[!NOTE]
>
>Debe ser propietario o administrador de una organización para editar la zona horaria de dicha organización.

1. En Fusion, haga clic en el icono de su perfil de Adobe en la parte superior derecha de la pantalla.
1. En el menú que se abre, seleccione **Perfil Fusion**.
1. Seleccione la ficha **Opciones de zona horaria**. Las pestañas se encuentran directamente debajo de su nombre.
Se abre la lista Opciones de zona horaria.
1. En el área Escenarios de la lista Opciones de zona horaria, busque la organización para la que desea ver o administrar la zona horaria.

   La configuración de zona horaria actual de la organización se muestra a la derecha del nombre de la organización.
1. Para editar la zona horaria, haga clic en Editar ![Editar zona horaria](assets/edit-timezone-icon.png) junto a la zona horaria.
1. En la ventana Cambiar detalles, en el campo **Zona horaria**, seleccione la zona horaria que desee establecer para su organización.
1. Haga clic en **Guardar**.


