---
title: Módulos MCP de Adobe Experience Manager
description: Con el módulo MCP de Adobe Experience Manager, puede enviar un mensaje en inglés sin formato al servidor MCP de Adobe Experience Manager y permitir que un modelo de IA realice la solicitud.
author: Becky
feature: Workfront Fusion
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 06271bbe8dd3c5eb7e3c6b45b71e7e0f7fd4d444
workflow-type: tm+mt
source-wordcount: 1020
ht-degree: 12%

---

# Módulos MCP de Adobe Experience Manager

El conector MCP de Adobe Experience Manager es una integración de Fusion específica para el servidor de MCP (Model Context Protocol) propio de Adobe Experience Manager. A diferencia de un conector típico, en el que cada módulo realiza una acción fija, este conector tiene un solo módulo que acepta una instrucción de inglés sin formato de extremo abierto y permite que un modelo de IA decida qué operaciones de Adobe Experience Manager son necesarias para cumplirla, en áreas como sitios, recursos digitales, fragmentos de contenido, carpetas, el repositorio de contenido y la IA de contenido.

Este conector está dedicado al servidor MCP propio de Adobe Experience Manager. No es compatible con otros servidores MCP no relacionados. Para un conector que pueda señalar a cualquier servidor MCP, utilice el conector del agente MCP.

Para obtener información sobre el conector del agente MCP, consulte [Módulo del agente MCP](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/model-context-protocol-mcp-connector.md).

>[!NOTE]
>
>Las respuestas de este módulo son generadas por IA y ocasionalmente pueden ser imperfectas, incluso con cada salvaguarda disponible en su lugar. Este módulo es apropiado para la automatización donde un humano no está revisando cada ejecución en tiempo real, pero no es una garantía del comportamiento determinista que obtendría de un módulo tradicional de Adobe Experience Manager.

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
   <td role="rowheader">Licencia de Adobe Workfront Fusion</td> 
   <td>
   <p>Basado en operaciones: disponible para organizaciones con licencias basadas en operaciones</p>
   <p>Basado en conector (heredado): Workfront Fusion for Work Automation and Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

* Debe tener una cuenta de Adobe Experience Manager para utilizar este módulo.

## Conexión de Adobe Experience Manager MCP a Workfront Fusion {#connect-adobe-experience-manager-mcp-to-workfront-fusion}

El conector MCP de Adobe Experience Manager utiliza OAuth para conectarse a Adobe Experience Manager. No hay campos de conexión que rellenar manualmente, como un nombre de usuario, una contraseña o una clave de API.

Para crear una conexión:

1. En el módulo MCP de Adobe Experience Manager, haga clic en **[!UICONTROL Agregar]** junto al campo Conexión.
1. Seleccione si desea conectarse a un entorno de producción o de no producción.
1. Seleccione si se está conectando a una cuenta de servicio o a una cuenta personal
1. Haga clic en **Continuar**.

   Se le redirigirá a la página de inicio de sesión de Adobe.
1. En la página de inicio de sesión de Adobe, inicie sesión y apruebe el acceso.

Se le redirigirá de nuevo a Workfront Fusion y la nueva conexión estará disponible en el módulo.

## Módulo MCP de Adobe Experience Manager y sus campos

Actualmente, solo hay un módulo en el conector MCP de Adobe Experience Manager.

### Procesar un mensaje de usuario

Este módulo de acción envía una instrucción en inglés sin formato al servidor MCP de Adobe Experience Manager y devuelve la respuesta de la API.

Cada ejecución de este módulo es una ejecución única e independiente, similar a enviar un correo electrónico en lugar de tener una conversación en directo. La IA no puede hacer una pregunta de seguimiento y esperar su respuesta. En lugar de ello, hace su mejor juicio y devuelve una respuesta completa. Si el mensaje es ambiguo, la IA indica cualquier suposición que haya hecho como parte de su respuesta, en lugar de detenerse a pedirle que la aclare.

>[!IMPORTANT]
>
>Este módulo solo realiza una acción de escritura o eliminación cuando el mensaje realmente solicita una. No toma ninguna acción extra que no solicitaste, incluso en la misma ejecución donde está llevando a cabo algo más que solicitaste.

Dado que cada ejecución es independiente, el módulo no tiene memoria de las ejecuciones anteriores por sí mismo. Para crear una experiencia conversacional de varias vueltas en varias ejecuciones, almacene la pregunta y respuesta anteriores. Para ello, puede utilizar un almacén de datos y, a continuación, incluir ese historial como texto al principio del siguiente mensaje, seguido de la nueva pregunta.

Para obtener información sobre los almacenes de datos, consulte [Almacén de datos](/help/workfront-fusion/create-scenarios/data-stores/data-store-overview.md).

<table style="table-layout:auto"> 
 <col/>
 <col/>
 <tbody>
  <tr>
   <td role="rowheader">Clave LLM <i>(opcional, avanzada)</i></td>
   <td><p>De forma predeterminada, este módulo procesa la solicitud mediante el servicio de IA propio de Adobe y no es necesario seleccionar una clave.</p><p>Para usar tu propio proveedor de IA en su lugar, selecciona una clave LLM existente o crea una nueva haciendo clic en <b>Agregar</b> e introduciendo la siguiente información:</p>
    <ul>
     <li><b>Nombre de clave</b>: escriba un nombre para la nueva clave.</li>
     <li><b>LLM</b>: seleccione el modelo de idioma grande con el que está asociada esta clave. Los proveedores admitidos son OpenAI, Anthropic Claude y Amazon Bedrock.</li>
     <li><b>Clave</b>: escriba o asigne la clave de API para el proveedor seleccionado.</li>
     <li><b>Modelo</b>: seleccione el modelo LLM que utilizará la clave.</li>
     <li><b>Otros campos</b>: escriba valores para cualquier otro campo que requiera su LLM.</li>
    </ul>
   </td>
  </tr>
  <tr>
   <td role="rowheader">Conexión</td>
   <td><p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-mcp-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager MCP a Workfront Fusion</a> en este artículo.</p></td>
  </tr>
  <tr>
   <td role="rowheader">Mensaje de usuario</td>
   <td><p>Introduzca o asigne la instrucción, en inglés sin formato, que desea que realice la IA.</p><p>Ejemplo: <i>Busque todos los recursos en la carpeta de marketing que no se hayan actualizado en 90 días.</i></p></td>
  </tr>
  <tr>
   <td role="rowheader">Herramientas de solo lectura <i>(opcional)</i></td>
   <td><p>Restrinja las acciones de solo lectura de Adobe Experience Manager a las que la IA puede llamar: acciones que solo buscan algo, como encontrar un recurso o leer el contenido de una página, y nunca cambian nada.</p><p>Si deja este campo vacío, se permiten todas las acciones de solo lectura.</p></td>
  </tr>
  <tr>
   <td role="rowheader">Herramientas de escritura/eliminación <i>(opcional)</i></td>
   <td><p>Restringir las acciones de escritura o eliminación de Adobe Experience Manager a las que la API puede llamar: acciones que cambian algo, como actualizar una página, publicar contenido o eliminar un recurso.</p><p>Si deja este campo vacío, se permiten todas las acciones de escritura y eliminación. Para garantizar que un escenario desatendido nunca realice una acción destructiva, se recomienda dejar este campo establecido en una selección deliberadamente vacía en lugar de dejarlo sin restricciones.</p></td>
  </tr>
 </tbody>
</table>

El módulo devuelve la respuesta final de la IA, en forma de texto, junto con un registro de lo que ha sucedido al producir esa respuesta, incluidas las herramientas a las que se llamó, si cada llamada se realizó correctamente y cuánto tiempo tardó el procesamiento.

