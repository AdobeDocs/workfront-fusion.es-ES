---
title: Módulos MCP de Adobe Workfront
description: Con el módulo MCP de Adobe Workfront, puede enviar un mensaje en inglés sin formato al servidor MCP de Adobe Workfront y permitir que un modelo de IA realice la solicitud.
author: Becky
feature: Workfront Fusion
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 71573ee33f852111d4541ee61567a51b137c7df5
workflow-type: tm+mt
source-wordcount: 871
ht-degree: 18%

---

# Módulos MCP de Adobe Workfront

El conector MCP de Adobe Workfront es una integración de Fusion específica para el servidor de MCP (Model Context Protocol) propio de Adobe Workfront. A diferencia de un conector típico, en el que cada módulo realiza una acción fija, este conector tiene un solo módulo que acepta una instrucción de inglés sin formato de extremo abierto y permite que un modelo de IA decida qué operaciones de Workfront son necesarias para cumplirla.

Por ejemplo, puede introducir el mensaje &quot;Buscar todos mis proyectos activos que están retrasados y resumir su estado&quot;, y el módulo devolverá una respuesta sintetizada, en lugar de tener que encadenar varios módulos Obtener y Filtrar.

Puede restringir qué acciones de Workfront puede realizar la IA, de modo que incluso un escenario desatendido pueda garantizar que no se realice ninguna acción destructiva inesperada.

De forma predeterminada, este módulo utiliza IA administrada por Adobe, que usa el modelo `claude-sonnet-5`. Puede configurar el módulo para que utilice un LLM diferente, usando una clave y otras credenciales que proporcione.

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

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Conexión de Adobe Workfront MCP a Workfront Fusion

El conector MCP de Adobe Workfront utiliza OAuth 2.0 para conectarse a Workfront. A diferencia de otros conectores de Workfront, no hay campos de conexión manual, como un host, un ID de cliente o un Secreto de cliente, que rellenar.

Para crear una conexión:

1. En el módulo MCP de Adobe Workfront, haga clic en **[!UICONTROL Agregar]** junto al campo Conexión.
1. Rellene los campos siguientes:

   <table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>Introduzca un nombre para esta conexión.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>Seleccione si desea conectarse a un entorno de producción o de no producción.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>Seleccione si desea conectarse a una cuenta de servicio o a una personal.</td>
      </tr>
    </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.

   Si no ha iniciado sesión en Workfront, se le dirigirá a una pantalla de inicio de sesión. Inicie sesión y apruebe el acceso.

Se le redirigirá de nuevo a Workfront Fusion y la nueva conexión estará disponible en el módulo.

>[!NOTE]
>
>Al utilizarla por primera vez, la conexión se registra automáticamente en el servidor MCP de Workfront y vuelve a utilizar ese registro para cada conexión posterior que cree.

## Módulo MCP de Adobe Workfront y sus campos

### Procesar un mensaje de usuario

Este módulo de acción procesa un mensaje en inglés sin formato en el servidor MCP de Workfront, utilizando el modelo de idioma especificado y devuelve la respuesta de la API.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody>

<tr> 
   <td>Clave LLM <i>(opcional, avanzada)</i></td> 
   <td> <p>De forma predeterminada, este módulo procesa la solicitud mediante Adobe Managed AI y no es necesario seleccionar una clave.</p> <p>Para usar tu propio proveedor de IA en su lugar, selecciona una clave LLM existente o crea una nueva haciendo clic en <b>Agregar</b> e introduciendo la siguiente información:</p>
     <ul>
       <li><b>Nombre de clave</b>: escriba un nombre para la nueva clave.</li>
       <li><b>LLM</b>: seleccione el modelo de idioma grande con el que está asociada esta clave. Los proveedores admitidos son OpenAI, Anthropic y Amazon Bedrock.</li>
       <li><b>Clave</b>: escriba o asigne la clave de API para el proveedor seleccionado.</li>
       <li><b>Modelo</b>: seleccione el modelo LLM que utilizará la clave.</li>
       <li><b>Otros campos</b>: escriba valores para cualquier otro campo que requiera su LLM.</li>
      </ul>
    </td> 
  </tr>   <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-adobe-workfront-mcp-to-workfront-fusion" class="MCXref xref">Conectar Adobe Workfront MCP a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>Herramientas de solo lectura <i>(opcional)</i></td> 
   <td> <p>Restrinja qué acciones de Workfront de solo lectura puede llamar la API. Si no se selecciona ninguna herramienta, se permiten todas las herramientas de solo lectura.</p> </td> 
  </tr> 
  <tr> 
   <td>Herramientas de escritura/eliminación <i>(opcional)</i></td> 
   <td> <p>Introduzca las acciones de escritura o eliminación de Workfront a las que la API puede llamar. Si deja esto vacío, se permiten todas las herramientas de escritura y eliminación.</p> <p>Para garantizar que un escenario desatendido nunca realice una acción destructiva, se recomienda dejar este campo establecido en una selección deliberadamente vacía en lugar de dejarlo sin restricciones.</p> </td> 
  </tr> 
  <tr> 
   <td>Introduzca el mensaje</td> 
   <td> <p>Introduzca o asigne la instrucción, en inglés sin formato, que desea que realice la IA.</p> <p>Ejemplo: <i>Buscar todos los proyectos que se me asignaron con retraso.</i></p> </td> 
  </tr>  </tbody> 
</table>

Para obtener una lista de las herramientas que puede seleccionar para los campos Herramientas de solo lectura y Herramientas de escritura/eliminación, consulte [Herramientas del servidor MCP de Adobe Workfront](https://experienceleague.adobe.com/en/docs/workfront/using/basics/workfront-mcp-server/workfront-mcp-server-tools) en la documentación de Workfront.

El módulo devuelve la siguiente información, que puede asignar en módulos posteriores en el escenario:

* **Respuesta**: La respuesta final de la IA, como texto.
* **Pista de auditoría**: Un registro de la sesión, que incluye la petición de datos original, la hora de inicio y finalización y los detalles de cada llamada de herramienta realizada por la API, como el nombre de la herramienta, los argumentos, si se realizó correctamente, la duración y el resultado.
* **Resumen**: Totales de la sesión, incluido el número de llamadas de herramienta intentadas, el número de llamadas correctas o fallidas, el tiempo total de procesamiento y el estado general.
