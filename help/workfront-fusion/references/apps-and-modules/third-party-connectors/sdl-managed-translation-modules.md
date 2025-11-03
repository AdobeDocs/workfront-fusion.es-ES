---
title: Módulos de traducción gestionada por SDL
description: En el caso de Adobe Workfront Fusion, puede conectar su cuenta de SDL Managed Translation a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: 41953b04-9011-4ddb-9f53-cdf11e807e04
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 73%

---

# Módulos de [!DNL SDL Managed Translation]

En un escenario de Adobe Workfront Fusion, puede conectar su cuenta de [!DNL SDL Managed Translation] a varias aplicaciones y servicios de terceros.

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
   <p>Basado en conectores (heredado): Workfront Fusion para la automatización e integración del trabajo </p>
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

## Información de la API de traducción gestionada de SDL

El conector de traducción gestionada por SDL utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Dirección URL base</td> 
   <td>https://languagecloud.sdl.com</td> 
  </tr>
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.4.26</td> 
  </tr>
 </tbody> 
 </table>

## Módulos de [!DNL SDL Managed Translation]

>[!NOTE]
>
>El tiempo de espera de la operación para las llamadas a [!DNL SDL Managed Translation] es de **120 segundos**.

### Archivos

#### [!UICONTROL Download Translated File]

Este módulo recupera el contenido de un solo archivo traducido, contenido en el proyecto especificado. Si el archivo solicitado aún no se encuentra en el estado de descarga, es posible que el contenido del archivo aún no se haya traducido completamente. Si el archivo se encuentra en estado de descarga y lo ha recuperado correctamente, asegúrese de marcar el archivo como completado con el método `Cancel or Complete File`.

#### [!UICONTROL Upload a File]

Este módulo permite cargar archivos para su traducción o inclusión en un proyecto de traducción como material de referencia. Las cargas deben enviarse con multipart/form-data y pueden contener más de un archivo. Usted especifica los `ProjectOptionId` que se deben usar para evaluar los archivos cargados. Esto determina si cada archivo que carga es un posible candidato para la traducción o debe manejarse como material de referencia. En el caso de los archivos (`zip `, `rar`, `7z`, `tar`), la aplicación examina el contenido del archivo e indica si el archivo en su conjunto se puede traducir o si contiene una mezcla de archivos traducibles y no traducibles.

>[!NOTE]
>
>No se recomienda cargar más de un archivo a la vez, ya que puede aumentar el impacto de cualquier error.

#### [!UICONTROL Add a Reference File]

Este módulo añade un archivo de referencia.

### Proyectos

#### [!UICONTROL Create a project]

Este módulo crea el proyecto especificado.

#### Cancelar o completar un proyecto

Este módulo cancela o completa el proyecto especificado. Si el proyecto está a la espera de descarga, pasa a través de los pasos finales del flujo de trabajo y, finalmente, se mueve a finalización. Si el proyecto está a la espera de aprobación o si se cancela la selección del proveedor. Si el proyecto se encuentra en cualquier otro estado, la solicitud fallará.

#### [!UICONTROL Download Project Zip]

Este módulo obtiene el archivo `zip` de archivos traducidos para el proyecto especificado.

#### [!UICONTROL Read a Project]

Este módulo obtiene el proyecto especificado.

#### [!UICONTROL Obtener proyectos en estado]

Este módulo obtiene todos los proyectos disponibles en el estado especificado. Este método permite paginar los resultados especificando los parámetros de consulta `$top`, `$skip` y `$orderby`.

#### [!UICONTROL Obtener lista de proyectos]

Obtiene una lista simple de todos los proyectos, proporcionando información general sobre cada proyecto. Este método permite que los resultados sean páginas especificando los parámetros de consulta `$top`, `$skip` y `$orderby`.

#### [!UICONTROL Buscar opciones de creación de proyectos]

Este módulo obtiene las opciones de creación de proyectos.

### Otro

#### [!UICONTROL Realizar una llamada de API]

Este módulo realiza una llamada de API autorizada arbitraria.
