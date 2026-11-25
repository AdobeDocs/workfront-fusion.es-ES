---
title: Configuración del servidor MCP de Adobe Workfront Fusion
description: Conecte Adobe Workfront Fusion a una plataforma independiente de IA compatible con MCP o a Coworker (independiente o en el carril derecho de Fusion).
source-git-commit: 6c1e5e8848003797c100a93086b615863ceb7244
workflow-type: tm+mt
source-wordcount: '1623'
ht-degree: 6%
---

# Configuración del servidor MCP de Adobe Workfront Fusion

El servidor MCP de Adobe Workfront Fusion le permite trabajar con los escenarios, ejecuciones, conexiones, webhooks, almacenes de datos y mucho más de su organización de Fusion, a través de una conversación en lenguaje natural en una plataforma independiente de IA compatible.

Para obtener una lista de las herramientas disponibles en el servidor MCP de Adobe Workfront Fusion, consulte [Herramientas del servidor MCP de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-fusion-mcp-server/fusion-mcp-server-tools.md).

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
   <p>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Requisitos previos

Antes de poder conectar Fusion a una plataforma agéntica de IA, debe:

* Tener una licencia activa de Adobe Workfront Fusion y acceso a al menos una organización de Fusion.
* Tener una función de usuario y funciones de equipo de Fusion que concedan acceso a los datos con los que desee trabajar.
* Inicie sesión con un Adobe ID (Adobe Identity Management System, IMS).
* Tener acceso a una plataforma agéntica de IA compatible con MCP o a Coworker.

## Aplicaciones MCP compatibles

El servidor Fusion MCP funciona con las siguientes aplicaciones.

**Aplicaciones de chat**

* Claude antrópico
* OpenAI ChatGPT
* Microsoft 365 Copilot

**Herramientas para desarrolladores**

* Código Claude antrópico
* Cursor
* Copiloto de GitHub
* Código VS
* Códice OpenAI
* Inspector de MCP, mcp-remote y otras herramientas que utilizan una devolución de llamada local

**Plataformas de automatización e IA**

* Adobe Workfront Fusion
* Búsqueda por IA de Google Vertex
* Glean
* Writer AI Studio
* Postman

### Limitaciones

* Solo las aplicaciones enumeradas en esta sección pueden conectarse al servidor MCP de Fusion.
* Las aplicaciones de escritorio y las interfaces de línea de comandos (CLI) funcionan si reciben la devolución de llamada de inicio de sesión en su propio equipo (`localhost`).
* No puede agregar sus propias aplicaciones. Para solicitar soporte técnico para una nueva aplicación, póngase en contacto con el equipo de Fusion en [fusiondev@adobe.com](mailto:fusiondev@adobe.com).

<!-- BECKY CHECK ME: Other parts of this article might conflict with these limitations. See the comments in the important note below, in the section Connect Fusion to a custom MCP solution, and in the troubleshooting table. -->

>[!NOTE]
>
> Actualmente, Adobe no publica un conector Workfront Fusion en el directorio de conectores de Claude o en el directorio de aplicaciones/complementos de ChatGPT. Para usar Fusion con Claude, ChatGPT o Microsoft Copilot, agréguelo como **servidor MCP personalizado** por dirección URL, tal como se describe en este artículo.

Este artículo explica los pasos de conexión para:

* [Adobe Coworker](#use-fusion-with-coworker): Coworker como independiente y Coworker en el carril derecho de Fusion
* [Claude](#connect-fusion-to-claude): conector personalizado
* [ChatGPT](#connect-fusion-to-chatgpt): servidor MCP personalizado
* [Una solución MCP personalizada](#connect-fusion-to-a-custom-mcp-solution)

>[!IMPORTANT]
>
>Si utiliza una plataforma compatible con MCP diferente, siga la documentación de esa plataforma para agregar un servidor MCP personalizado. Cuando se le pida la URL del servidor MCP, introduzca:
>
>```
>https://mcp.fusion.adobe.com/mcp
>```

## Uso de Fusion con Coworker

El compañero es el agente de IA de Adobe. Fusion está integrado en Coworker, por lo que no es necesario introducir una URL de MCP ni registrar una aplicación de OAuth. Puede utilizar Coworker con Fusion en dos lugares:

* Compañero (independiente): Trabaje con Fusion junto con sus otras aplicaciones de Adobe.
* Compañero en el carril derecho de Fusion: Abra Compañero en un panel dentro de la interfaz de usuario de Fusion.

Ambos utilizan las mismas herramientas de Fusion MCP, su Adobe ID y sus permisos de Fusion. Las preferencias de MCP de la organización para herramientas de solo lectura y escritura se aplican en ambos casos. Para obtener más información, consulte [Administrar las preferencias de MCP de su organización](#manage-mcp-preferences-for-your-organization). Las acciones destructivas, como eliminar, borrar colas o sobrescribir, siempre piden confirmación.

### Uso de Fusion en Coworker

1. Abra Compañero de trabajo. Puede encontrarlo en https://experience.adobe.com/#/coworker.
1. Abrir **personalizaciones** > **integraciones**
1. Busque o busque **fusion-mcp** y haga clic en él.
1. En la ventana que se abre, haga clic en **Probar**.
1. Si tiene acceso a más de una organización de Fusion, se seleccionará automáticamente. Si es necesario, puede pedir a sus compañeros que cambien de organización más tarde.

### Uso de Coworker en el carril derecho de Fusion

En Fusion, el compañero se abre en el carril derecho

1. Inicie sesión en Workfront Fusion.
1. Haga clic en el icono **Compañero** en el carril derecho.
1. Formule una pregunta en el panel.

### Ejemplos de peticiones

* *Mostrarme todos los escenarios que no se ejecutaron en las últimas 24 horas.*
* *Enumerar todos los escenarios creados o eliminados esta semana, ordenados por el más reciente primero.*
* *¿Qué está haciendo este escenario?*
* *¿Por qué falló esta ejecución?*

## Conectar Fusion a Claude

Añada Fusion como conector personalizado.

>[!NOTE]
>
> En Claude Team/Enterprise, debe ser el propietario para agregar un conector personalizado. Para obtener más información, consulte [Introducción a los conectores personalizados con MCP remoto](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp) en la documentación de Claude.

1. Iniciar sesión en [Claude](https://claude.ai).
1. En el menú de la izquierda, seleccione **Personalizar**.
1. Seleccione **Conectores**.
1. Seleccione **+**, luego **Agregar conector personalizado**.
1. Introduzca un nombre (por ejemplo, &quot;Workfront Fusion&quot;) y la URL del servidor MCP:

   ```
   https://mcp.fusion.adobe.com/mcp
   ```

1. Haga clic en **Conectar**.
1. Iniciar sesión. Seleccione un perfil y una organización de Fusion.

Para Claude Code, puede agregar el servidor desde la línea de comandos:

```
claude mcp add --transport http fusion-mcp https://mcp.fusion.adobe.com/mcp
```

## Conectar Fusion a ChatGPT

Añada Fusion como servidor MCP personalizado.

### ChatGPT Desktop o Codex

1. En ChatGPT, abra **Configuración**.
1. Haga clic en **Complementos**.
1. Haga clic en **Agregar servidor**.
1. Escriba un nombre para el servidor.
1. Para el tipo, seleccione **HTTP transmisible**.
1. Introduzca la URL del servidor MCP:

   ```
   https://mcp.fusion.adobe.com/mcp
   ```

1. Haga clic en **Guardar**.
1. Haga clic en **Autenticar** para el nuevo servidor e inicie sesión.
1. Asegúrese de que la opción junto al servidor esté activada.

### ChatGPT en la web

1. Iniciar sesión en [ChatGPT](https://chatgpt.com).
1. Vaya a [https://chatgpt.com/plugins](https://chatgpt.com/plugins). (Es posible que sea necesario habilitar el modo de desarrollador en **Configuración**; en los planes de empresa/empresa, un administrador debe permitir conectores personalizados).
1. Haga clic en **+**.
1. Escriba un **Nombre**.
1. Para **Conexión**, seleccione **URL del servidor** e introduzca la URL del servidor MCP.
1. Deje **Authentication** establecida en **OAuth**.
1. Lea el mensaje de riesgo y marque la casilla de verificación.
1. Haz clic en **Crear** y luego inicia sesión con tu cuenta.

## Administrar las preferencias de MCP de su organización

Los propietarios y administradores de la organización pueden elegir qué herramientas de Fusion MCP están disponibles para la organización. Otros usuarios no pueden cambiar esta configuración.

Puede permitir o deshabilitar los siguientes tipos de herramientas:

<table style="table-layout:auto">
 <col>
 <col>
 <tbody>
  <tr>
   <td role="rowheader">[!UICONTROL Herramientas MCP de solo lectura]</td>
   <td>Herramientas que solo leen datos, como enumerar y obtener escenarios, ejecuciones, conexiones y almacenes de datos.</td>
  </tr>
  <tr>
   <td role="rowheader">[!UICONTROL Write MCP tools]</td>
   <td><p>Herramientas que crean, actualizan, eliminan o ejecutan elementos, como la creación o actualización de escenarios, la ejecución de un escenario o la eliminación de una conexión.</p><p>No puede habilitar <b>[!UICONTROL Write MCP tools]</b> a menos que <b>[!UICONTROL Read-only MCP tools]</b> también esté habilitado.</p></td>
  </tr>
 </tbody>
</table>

La configuración se aplica a toda la organización. Después de guardarlo, todos los usuarios que se conecten al servidor de Fusion MCP para esa organización obtendrán solo las herramientas permitidas. Las herramientas desactivadas no aparecen en la lista de herramientas y Fusion las rechaza si un agente las llama.

>[!IMPORTANT]
>
>Esta configuración limita únicamente las llamadas de herramienta realizadas a través del servidor MCP de Fusion oficial mediante la URL del servidor MCP de este artículo. Las acciones que los usuarios realizan en la interfaz de usuario de Fusion, a través de la API o a través de cualquier otra integración siguen controladas por los propios permisos de cada usuario en Fusion.

Para administrar las preferencias de MCP:

1. En Fusion, haga clic en **[!UICONTROL Organización]** en el panel de navegación izquierdo.

1. Haga clic en **[!UICONTROL Cambiar detalles]**.

   Se abre la ventana **[!UICONTROL Cambiar detalles]**.

1. En **[!UICONTROL Preferencias de MCP]**, seleccione o borre **[!UICONTROL Herramientas de MCP de solo lectura]** y **[!UICONTROL Escribir herramientas de MCP]**.
1. Haga clic en **[!UICONTROL Guardar]**.

>[!NOTE]
>
>Si las funciones de IA están desactivadas para la organización, no puede editar las preferencias de MCP.

## Cambiar a una organización de Fusion diferente

No es necesario desconectarse para cambiar de organización. El servidor MCP de Fusion puede cambiar la organización activa dentro de una sesión:

* _¿Qué organizaciones de Fusion tengo?_
* _Cambiar a la organización 1234._

El agente usa `fusion_orgs_list` y `fusion_orgs_set`. El conmutador solo se aplica a la conversación o sesión actual. Todas las organizaciones de diferentes zonas de centros de datos (por ejemplo, EE. UU. y UE) están disponibles a través de la misma URL de MCP.

## Solucionar problemas de configuración y autenticación

| Problema | Causa probable | Corregir |
| --- | --- | --- |
| No puede encontrar un conector Fusion en el directorio Claude o ChatGPT. | Adobe no publica un conector de directorio para Fusion. | Añada Fusion como servidor MCP personalizado utilizando la URL de este artículo. |
| No se puede agregar un conector personalizado en Claude o ChatGPT. | Su plan restringe los conectores personalizados a los propietarios o administradores. | Pida a su administrador de Claude o ChatGPT que agregue el conector o permita servidores MCP personalizados. |
| Se ha conectado pero no ve ningún dato, o los datos incorrectos. | La organización de Fusion incorrecta está activa. | Pida al agente que enumere sus organizaciones y cambie a la correcta. |
| Error de autenticación o la conexión dejó de funcionar. | Sesión caducada o error de conexión. | Desconecte y vuelva a conectar el servidor. |
| Verá un mensaje que indica que el acceso a MCP está deshabilitado. | El acceso a MCP está desactivado para su organización de Fusion. | Solicite a su administrador de Fusion que lo habilite. Para obtener más información, consulte [Administrar las preferencias de MCP de su organización](#manage-mcp-preferences-for-your-organization). |
| El agente puede leer escenarios, pero no puede crearlos, ejecutarlos, actualizarlos o eliminarlos. | Las herramientas Escribir MCP están deshabilitadas o la función de su equipo no lo permite. | Pida al administrador de Fusion que habilite las herramientas de escritura en las preferencias de MCP de la organización o que le otorgue la función de equipo necesaria. Para obtener más información, consulte [Administrar las preferencias de MCP de su organización](#manage-mcp-preferences-for-your-organization). |
| Se ha rechazado la autenticación de aplicación personalizada. | La URL de devolución de llamada no está en la lista autorizada. | Pida al administrador que añada la URL de devolución de llamada exacta. |
| Fusion no aparece en Coworker o Coworker no aparece en el carril derecho de Fusion. | Función no habilitada para su organización. | Póngase en contacto con su administrador de Fusion. |

## Preguntas frecuentes

### ¿Hay un conector Fusion oficial para Claude o ChatGPT?

En este momento no. Utilice la URL personalizada del servidor MCP. Coworker (independiente y en el carril derecho de Fusion) tiene Fusion integrado.

### ¿Puedo utilizar más de una organización de Fusion?

Sí. Puede cambiar la organización activa durante una conversación sin volver a conectarse.

### ¿Qué puede hacer el agente en mi nombre?

El agente actúa como usted, utilizando su función de Fusion y los permisos de equipo. No puede acceder a nada a lo que no pueda acceder en Fusion. Las acciones destructivas requieren una confirmación explícita.

### ¿El agente ve mis secretos de conexión?

No. Las herramientas de conexión y clave devuelven metadatos (nombre, tipo, ámbitos, caducidad), no credenciales ni valores secretos.

