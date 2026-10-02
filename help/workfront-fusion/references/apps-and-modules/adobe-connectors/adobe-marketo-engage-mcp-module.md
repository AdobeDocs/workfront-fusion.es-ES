---
title: Módulo MCP de Adobe Marketo Engage
description: El módulo MCP de Adobe Marketo Engage le permite enviar un mensaje en lenguaje natural al servidor MCP (Model Context Protocol) de Adobe Marketo Engage.
author: Becky
feature: Workfront Fusion
exl-id: 3f29ab35-7a90-4afb-a283-4faaacec5b15
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: b58ad82f-df6b-4b01-81a3-3a02ab9567a0
    internal-label: APIs
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
  - id: e14a7f57-c82c-4874-a495-5d036cbbdc3d
    internal-label: Resource management
subfeature_v2:
  - id: b70a979b-965d-47a9-a360-e7ec2a19b8c1
    internal-label: Digital content and documents
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 9e08c421a53c7ca499715fa8e32be6c10fbde1d9
workflow-type: tm+mt
source-wordcount: '1579'
ht-degree: 11%
---
# Módulo MCP de Adobe Marketo Engage

El módulo MCP de Adobe Marketo Engage le permite enviar un mensaje en lenguaje natural al servidor MCP (Model Context Protocol) de Adobe Marketo Engage, utilizando un modelo de IA para interpretar la solicitud y llamar a las propias herramientas de Marketo para cumplirla. A diferencia de un conector Marketo tradicional en el que cada módulo realiza una acción fija, como &quot;Crear un posible cliente&quot;, este conector tiene un solo módulo que acepta una instrucción abierta en inglés sin formato y permite a la IA decidir qué operaciones de Marketo son necesarias para satisfacerla.

Este conector es específicamente para el servidor MCP de Marketo Engage

Para conectarse a MCP para otras aplicaciones, consulte [Agregar un mensaje de IA a su escenario](/help/workfront-fusion/create-scenarios/add-modules/add-an-ai-prompt-to-your-scenario.md).

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

* Debe tener una cuenta de Adobe Marketo Engage y una instancia de Marketo válida.

## Conexión de Adobe Marketo Engage MCP a Workfront Fusion {#connect-adobe-marketo-engage-mcp-to-workfront-fusion}

Puede crear una conexión con la instancia de Marketo directamente desde el módulo MCP de Adobe Marketo Engage.

1. En el módulo MCP de Adobe Marketo Engage, haga clic en **Agregar** junto al campo **Conexión**.
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
          <p>Introduzca un nombre para la nueva conexión.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>
          <p>Seleccione si desea conectarse a un entorno de producción o de no producción.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>
          <p>Seleccione si desea conectarse a una cuenta de servicio o a una personal.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>
          <p>Introduzca el ID de cliente para el servicio de API de REST de Marketo, tal como se crea en Marketo LaunchPoint.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>
          <p>Introduzca el Secreto de cliente para el servicio de API de REST de Marketo, tal como se crea en Marketo LaunchPoint.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Munchkin ID]</td>
        <td>
          <p>Introduzca el Munchkin ID de su instancia de Marketo (por ejemplo, 123-ABC-456). El Munchkin ID se muestra en Marketo en <b>Admin → Munchkin</b>.</p>
        </td>
      </tr>
    </tbody>
   </table>

1. Haga clic en **Continue** para crear la conexión y volver al módulo.

>[!IMPORTANT]
>
> * En lugar de reutilizar una cuenta de administrador, utilice un usuario de Marketo dedicado solo a la API con la función y los permisos mínimos requeridos para el escenario.
> * La creación de la conexión no valida las credenciales. Fusion los guarda sin una llamada de prueba, por lo que la conexión puede parecer que se ha creado correctamente incluso si un valor es incorrecto o está mal escrito. Si una credencial es incorrecta, el error suele aparecer más adelante cuando el módulo intenta llegar a Marketo por primera vez o cuando las listas de herramientas no se pueden cargar.

## El módulo: &quot;Procesar un mensaje de usuario&quot;

Este es el único módulo que proporciona el conector. Un escenario lo utiliza al proporcionar:

1. **Conexión**: la conexión de Marketo creada anteriormente.
2. **Escriba el mensaje**: la instrucción, en inglés sin formato (por ejemplo, &quot;encuentre todos los posibles clientes agregados a la lista Seminario web de primavera en la última semana y dígame cuáles no tienen establecido un nombre de compañía&quot;).
3. **Herramientas** (opcional): se describe a continuación. Estos campos solo aparecen una vez seleccionada una conexión.
4. **Clave LLM** (opcional, avanzada) — se describe a continuación.

Devuelve la respuesta final de la inteligencia artificial como texto, además de una pista de auditoría completa de lo que ocurrió mientras se producía esa respuesta.

## Módulo MCP de Adobe Marketo Engage y sus campos

### Procesar un mensaje de usuario

Este módulo de acción envía una instrucción en inglés sin formato al servidor MCP de Adobe Marketo Engage y devuelve la respuesta de la API.

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
   <td><p>Para obtener instrucciones sobre cómo conectar su cuenta de Marketo a Workfront Fusion, consulte <a href="#connect-adobe-marketo-engage-mcp-to-workfront-fusion" class="MCXref xref">Conectar Adobe Marketo Engage MCP a Workfront Fusion</a> en este artículo.</p></td>
  </tr>
  <tr>
   <td role="rowheader">Mensaje de usuario</td>
   <td><p>Introduzca o asigne la instrucción, en inglés sin formato, que desea que realice la IA.</p><p>Ejemplo: <i>Busque todos los posibles clientes agregados a la lista de seminarios web de primavera en los últimos siete días y resuma qué sectores son los más comunes.</i></p></td>
  </tr>
 </tbody>
</table>

### Salida de módulo

El resultado es un paquete único que contiene lo siguiente:

* Respuesta: La respuesta final de la IA, en forma de texto. Puede asignar estos datos en módulos subsiguientes.
* Pista de auditoría: registro detallado de la ejecución, que incluye un ID de sesión, la petición de datos original, las horas de inicio y finalización, la duración total, el estado general, la respuesta final y una lista de llamadas de herramienta. Cada entrada de llamada a la herramienta registra qué herramienta de Marketo se ejecutó, sus argumentos, su salida, su hora de inicio y finalización, si se realizó correctamente y su orden en la secuencia.
* Resumen: La misma ejecución condensada a recuentos: llamadas de herramienta totales, llamadas correctas, llamadas fallidas, tiempo de procesamiento y estado.

### Modelos de IA

De forma predeterminada, el módulo utiliza automáticamente el servicio de IA administrado por el propio Adobe, sin claves ni credenciales que introducir.

En su lugar, puede seleccionar una clave LLM específica para utilizar OpenAI, Anthropic Claude o Amazon Bedrock, si su organización tiene una cuenta con una de estas.

### Elección de las acciones de Marketo que puede realizar la API

Una vez seleccionada una conexión, el módulo pregunta al servidor MCP de Marketo qué herramientas ofrece y las presenta como listas de selección múltiple, cada una de las cuales muestra cuántas herramientas contiene:

* Herramientas de solo lectura: Acciones que solo buscan algo y nunca cambian nada, como encontrar un posible cliente, enumerar miembros de una campaña o leer los detalles de un programa.
* Herramientas de escritura/eliminación: acciones que cambian algo, como crear o actualizar un posible cliente, agregar a alguien a una lista, activar una campaña o aprobar o enviar un correo electrónico.
* Otras herramientas: Una tercera lista que aparece únicamente si el servidor de Marketo ofrece herramientas que no han sido etiquetadas como de solo lectura o no. Se muestran por separado en lugar de considerarse seguros o inseguros. Si el servidor lo etiqueta todo, esta lista no aparece.

Si no se selecciona ninguna herramienta, la IA puede utilizarlas todas. Puede restringir una lista a acciones específicas. Por ejemplo, seleccionar solo 2 acciones de &quot;escritura&quot; específicas mientras se deja solo &quot;solo lectura&quot; significa que la IA puede buscar lo que necesite libremente, pero solo puede realizar esos 2 tipos específicos de cambios. Si se deja vacía una lista, se permiten todas las acciones de esa categoría. Para restringir la IA, es necesario elegir activamente qué acciones específicas permitir en esa categoría. De este modo, puede asegurarse de que la IA no realice una acción destructiva inesperada contra los datos de marketing en directo, al tiempo que permite que recopile información libremente.

Dado que las listas se leen en directo desde el servidor de Marketo, las herramientas exactas que se muestran pueden cambiar a medida que Adobe actualiza ese servidor.

### No hay historial de conversaciones persistentes

Cada ejecución de este módulo es una ejecución única e independiente. La IA no puede formular una pregunta complementaria y esperar una respuesta. En lugar de ello, debe emitir su mejor juicio y dar una respuesta completa y definitiva de una sola vez. Si una solicitud es ambigua, la AI hará una suposición razonable, la declarará como parte de su respuesta y procederá. No se detendrá y pedirá al usuario que lo aclare, ya que no hay forma de que reciba una respuesta dentro de una sola ejecución.

También se indica a la API que compruebe los hechos con una llamada a la herramienta en lugar de depender de la memoria, ya que los datos de Marketo pueden haber cambiado desde la ejecución anterior.

La API solo realiza una acción de escritura, actualización o eliminación cuando el mensaje realmente lo solicita. No se realiza una acción que no se solicitó, como activar o desactivar campañas, crear o eliminar posibles clientes y listas, y aprobar o enviar correos electrónicos, incluso en la misma ejecución en la que se está haciendo algo más que el usuario pidió.

Como cada ejecución es independiente, la IA no tiene memoria de una ejecución anterior por sí misma. Un escenario que desee una experiencia de varias vueltas y tipo chat debe proporcionar explícitamente ese historial como parte del nuevo mensaje, por ejemplo, almacenando la pregunta y respuesta anteriores en el almacén de datos de Fusion, o pasando entre módulos, e incluyéndolos como texto al principio del nuevo mensaje, seguido de la nueva pregunta. No hay ningún ID de sesión o conversación que recuerde automáticamente las ejecuciones anteriores.

## Ejemplos de peticiones

Puede utilizar indicadores como los siguientes:

* *Enumere los posibles clientes que se han unido al programa &quot;Lanzamiento de productos en el tercer trimestre&quot; en los últimos siete días y resuma de qué industrias proceden.*
* *Comprueba si la campaña inteligente &#39;Serie de bienvenida&#39; está activa actualmente y dime cuántas personas hay en ella.*
* *Encuentra el formulario que usamos en nuestra página de precios y dime qué campos están marcados como obligatorios.*
* *Agregue el posible cliente con correo electrónico `jane@example.com` a la lista estática &#39;Clientes de VIP&#39;.*
* *Resumir el rendimiento de cada correo electrónico en el programa &#39;Boletín de primavera&#39;.*

<!--

## What a content writer should NOT claim

* Connection form: Do not describe the connection as an OAuth or "sign in with Adobe" flow. It is not one. It is three credential fields that the user copies out of Marketo's LaunchPoint and Munchkin admin pages. Screenshots or steps borrowed from the AEM MCP connector docs would be wrong here.
* Credential validation: Do not imply that the connection form validates the credentials. It saves them without testing them.
* Module scope: This is not a substitute for individual Marketo action modules. It is a single, flexible AI-driven module, not a set of deterministic single-purpose modules.
* Reliability: Results are AI-generated and can occasionally be imperfect, even with every safeguard above in place. This is appropriate for automation where a human is not reviewing every single run in real time, but it is not a guarantee of 100% deterministic behavior the way a traditional Marketo module is. This deserves extra emphasis for Marketo specifically, because a write action here can email real customers or alter real lead records.
* Tool restrictions: The read/write tool split limits what categories of Marketo actions the AI can take. It is not a way to sandbox or limit what the AI is capable of reasoning about or discussing in its answer text.
* Tool naming: Do not name specific Marketo MCP tools or actions unless they are verified against the live tool list. This document intentionally describes capability areas, such as leads, lists, campaigns, programs, emails, forms, snippets, and bulk operations, rather than exact tool names, since the server's exact tool set may evolve.
* API limits: Do not state Marketo API rate limits, quotas, or daily call caps as if this connector defines them. Any such limit comes from the user's own Marketo subscription and REST API allowance; verify with the Marketo team before publishing numbers.

## Reference links used while compiling this

* Adobe Marketo Engage MCP server (developer documentation):
  https://experienceleague.adobe.com/es/docs/marketo-developer/marketo/mcp-server

  -->
