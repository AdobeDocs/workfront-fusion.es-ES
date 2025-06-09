---
title: Módulos de Protocolo de contexto de modelo (MCP)
description: El módulo Protocolo de contexto de modelo (MCP) permite procesar un mensaje de usuario mediante MCP.
author: Becky
feature: Workfront Fusion
source-git-commit: d8ae176db714d2b9f041b74a62e8276171745c4b
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 17%

---

# Módulos de Protocolo de contexto de modelo (MCP)

El Protocolo de contexto de modelo (MCP) es una forma de conectar de forma segura los modelos de lenguaje de IA con otras aplicaciones. Los servidores MCP se configuran para permitir que el modelo de IA acceda a la aplicación. A continuación, puede enviar una solicitud al modelo de IA y devolver información de la aplicación.

Por ejemplo, puede configurar un servidor MCP para conectar un modelo de IA con Gmail. Cuando envíes el mensaje &quot;Dame mis últimos 5 correos electrónicos de Gmail&quot;, puede acceder a tu Gmail y devolver los correos electrónicos.

El módulo Protocolo de contexto de modelo (MCP) permite procesar un mensaje de usuario mediante un modelo de idioma y servidores MCP.

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
   <p>Actual: Su organización debe adquirir Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Módulo de protocolo de contexto del modelo y sus campos

Al configurar el módulo MCP, [!DNL Adobe Workfront Fusion] muestra los campos que se indican a continuación. El título en negrita en un módulo indica un campo obligatorio.

### Mensaje de usuario de proceso

Este módulo de acción procesa una solicitud utilizando el modelo de idioma y los servidores MCP especificados.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Clave de [!UICONTROL Large language model (LLM)]</td> 
   <td> <p>Escriba o asigne la clave de API para el modelo de idioma grande que desee utilizar en esta solicitud. </p> <p>Actualmente, solo se admite la clave API Anthropic.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL servidores MCP]</td> 
   <td> <p>Para cada servidor MCP que desee poner a disposición de esta solicitud, haga clic en <b>Agregar elemento</b> e introduzca el nombre y el host del servidor. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Escriba el mensaje]</td> 
   <td> <p>Introduzca o asigne el mensaje para el modelo de idioma grande. </p> </td> 
  </tr> 
 </tbody> 
</table>
