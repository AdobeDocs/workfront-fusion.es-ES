---
title: Módulos de Protocolo de contexto de modelo (MCP)
description: El módulo Protocolo de contexto de modelo (MCP) permite procesar un mensaje de usuario mediante MCP.
author: Becky
feature: Workfront Fusion
hide: true
hidefromtoc: true
exl-id: 748055ad-d305-4513-9a5c-9c970b74a96e
source-git-commit: 97abe6bf0ff7b10a139268f02f8a1a24f3e31b47
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 18%

---

# Módulo del agente MCP

<!--SET UP REDIRECTS-->

El Protocolo de contexto de modelo (MCP) es una forma de conectar de forma segura los modelos de lenguaje de IA con otras aplicaciones. Los servidores MCP se configuran para permitir que el modelo de IA acceda a la aplicación. A continuación, puede enviar una solicitud al modelo de IA y devolver información de la aplicación.

Por ejemplo, puede configurar un servidor MCP para conectar un modelo de IA con Gmail. Cuando envíes el mensaje &quot;Dame mis últimos 5 correos electrónicos de Gmail&quot;, puede acceder a tu Gmail y devolver los correos electrónicos.

El módulo Protocolo de contexto de modelo (MCP) permite procesar un mensaje de usuario mediante un modelo de idioma y servidores MCP.

Para obtener más información sobre MCP en escenarios de Fusion, consulte [Agregar un mensaje de IA a su escenario](/help/workfront-fusion/create-scenarios/add-modules/add-an-ai-prompt-to-your-scenario.md).

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
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte los [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Requisitos previos

* Debe tener configurado los servidores MCP a los que desea conectarse.
* Debe tener una clave LLM para el LLM (Modelo de idioma grande) seleccionado.

## Módulo de protocolo de contexto del modelo y sus campos

### Mensaje de usuario de proceso

Este módulo de acción procesa una solicitud utilizando el modelo de idioma y los servidores MCP especificados.

>[!NOTE]
>
>Este módulo debe devolver un objeto. No devuelve resultados como cadenas o números.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>Clave LLM</td> 
   <td> Seleccione una clave LLM existente o cree una nueva haciendo clic en <b>Agregar</b> e introduciendo la siguiente información: 
     <ul>
       <li><b>Nombre de clave</b>: escriba un nombre para la nueva clave.</li>
       <li><b>LLM</b>: seleccione el modelo de idioma grande con el que está asociada esta clave.</li>
       <li><b>Clave</b>: escriba o asigne la clave de API para el modelo seleccionado.</li>
       <li><b>Modelo</b>: seleccione el modelo LLM que utilizará la clave.</li>
       <li><b>Máximo de tokens</b>: escriba o asigne el número máximo de tokens que el LLM puede generar en su respuesta.<p>Un símbolo suele ser igual a cuatro caracteres, o 0,75 de una palabra en inglés. "Hello world" sería igual a dos tokens y "Authentication" sería igual a uno o dos tokens.</li>
      </ul>
    </td> 
  </tr> 
  <tr> 
   <td>Servidores MCP</td> 
   <td> <p>Para cada servidor MCP al que desee conectarse, haga clic en <b>Agregar</b> e introduzca la siguiente información: </p> 
     <ul>
       <li><b>Conexión</b>: Seleccione la conexión que Fusion utilizará para conectarse al servidor MCP.</li>
       <li><b>Host del servidor MCP</b>: Escriba la dirección URL del servidor MCP.</li>
       <li><b>Nombre de servidor MCP</b>: escriba o asigne un nombre para este servidor MCP.</li>
       <li><b>Encabezados</b>: agregue cualquier encabezado aplicable.</li>
       <li><b>Tipo de servidor MCP</b>: seleccione el tipo de servidor.</li>
      </ul>
    </td> 
  </tr> 
  <tr> 
   <td>Introduzca el mensaje </td> 
   <td> <p>Introduzca o asigne la solicitud que desea procesar.</p> </td> 
  </tr> 
 </tbody> 
</table>


