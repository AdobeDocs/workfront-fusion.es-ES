---
title: Configuración del servidor MCP de Adobe Workfront Fusion
description: Conecte Adobe Workfront Fusion a una plataforma independiente de IA compatible con MCP o a Coworker (independiente o en el carril derecho de Fusion).
source-git-commit: 6d447c16d199c69ae670f59bb56cf79464cbe057
workflow-type: tm+mt
source-wordcount: '1177'
ht-degree: 1%
---

# Configuración del servidor MCP de Adobe Workfront Fusion

El servidor MCP de Adobe Workfront Fusion le permite trabajar con los escenarios, ejecuciones, conexiones, webhooks, almacenes de datos y mucho más de su organización de Fusion, a través de una conversación en lenguaje natural en una plataforma independiente de IA compatible.

Para obtener una lista de las herramientas disponibles en el servidor MCP de Adobe Workfront Fusion, consulte [Herramientas del servidor MCP de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-fusion-mcp-server/fusion-mcp-server-tools.md).

## Plataformas agénticas de IA compatibles

El servidor MCP de Fusion funciona con cualquier plataforma agéntica de IA que admita el Protocolo de contexto de modelo (MCP) y servidores MCP remotos (HTTP transmisible) con OAuth.

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
>Si utiliza una plataforma compatible con MCP diferente, como Gemini, Cursor o Código VS, siga la documentación de dicha plataforma para agregar un servidor MCP personalizado. Cuando se le pida la URL del servidor MCP, introduzca:
>
>```
>https://mcp.fusion.adobe.com/mcp
>```

## Requisitos previos

Antes de poder conectar Fusion a una plataforma agéntica de IA, debe:

* Tener una licencia activa de Adobe Workfront Fusion y acceso a al menos una organización de Fusion.
* Tener una función de usuario y funciones de equipo de Fusion que concedan acceso a los datos con los que desee trabajar.
* Inicie sesión con un Adobe ID (Adobe Identity Management System, IMS).
* Tener acceso a una plataforma agéntica de IA compatible con MCP o a Coworker.

## Uso de Fusion con Coworker

El compañero es el agente de IA de Adobe. Fusion está integrado en Coworker, por lo que no es necesario introducir una URL de MCP ni registrar una aplicación de OAuth. Puede utilizar Coworker con Fusion en dos lugares:

* [Compañero de trabajo (independiente)](#use-fusion-in-coworker): Trabaje con Fusion junto con sus otras aplicaciones de Adobe.
* [Colaborador en el carril derecho de Fusion](#use-coworker-in-the-fusion-right-rail): Abra Colaborador en un panel dentro de la interfaz de usuario de Fusion.

Ambos utilizan las mismas herramientas de Fusion MCP, su Adobe ID y sus permisos de Fusion. La configuración de las herramientas MCP de lectura o escritura se aplica en ambos. Las acciones destructivas, como eliminar, borrar colas o sobrescribir, siempre piden confirmación.

### Uso de Fusion en Coworker

1. Abra Compañero de trabajo.
2. Abrir **Personalización** > **Integraciones**
3. Busque **fusion-mcp** y haga clic en **Probar**.
4. Si tiene acceso a más de una organización de Fusion, se seleccionará automáticamente. Si es necesario, puede pedir a sus compañeros que cambien de organización más tarde.

### Uso de Coworker en el carril derecho de Fusion

En Fusion, el compañero se abre en el carril derecho

1. Inicie sesión en Workfront Fusion.
2. Haga clic en el icono **Compañero** en el carril derecho.
3. Formule una pregunta en el panel.

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
2. En el menú de la izquierda, seleccione **Personalizar**.
3. Seleccione **Conectores**.
4. Seleccione **+**, luego **Agregar conector personalizado**.
5. Introduzca un nombre (por ejemplo, &quot;Workfront Fusion&quot;) y la URL del servidor MCP:

   ```
   https://mcp.fusion.adobe.com/mcp
   ```

6. Haga clic en **Conectar**.
7. Iniciar sesión. Seleccione un perfil y una organización de Fusion.

Para Claude Code, puede agregar el servidor desde la línea de comandos:

```
claude mcp add --transport http fusion-mcp https://mcp.fusion.adobe.com/mcp
```

## Conectar Fusion a ChatGPT

Añada Fusion como servidor MCP personalizado.

### ChatGPT Desktop o Codex

1. En ChatGPT, abra **Configuración**.
2. Haga clic en **Complementos**.
3. Haga clic en **Agregar servidor**.
4. Escriba un nombre para el servidor.
5. Para el tipo, seleccione **HTTP transmisible**.
6. Introduzca la URL del servidor MCP:

   ```
   https://mcp.fusion.adobe.com/mcp
   ```

7. Haga clic en **Guardar**.
8. Haga clic en **Autenticar** para el nuevo servidor e inicie sesión.
9. Asegúrese de que la opción junto al servidor esté activada.

### ChatGPT en la web

1. Iniciar sesión en [ChatGPT](https://chatgpt.com).
2. Vaya a [https://chatgpt.com/plugins](https://chatgpt.com/plugins). (Es posible que sea necesario habilitar el modo de desarrollador en **Configuración**; en los planes de empresa/empresa, un administrador debe permitir conectores personalizados).
3. Haga clic en **+**.
4. Escriba un **Nombre**.
5. Para **Conexión**, seleccione **URL del servidor** e introduzca la URL del servidor MCP.
6. Deje **Authentication** establecida en **OAuth**.
7. Lea el mensaje de riesgo y marque la casilla de verificación.
8. Haz clic en **Crear** y luego inicia sesión con tu cuenta.

## Conexión de Fusion a una solución MCP personalizada

Si está creando su propia aplicación o agente, conéctese directamente al servidor MCP de Fusion.

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
| Verá un mensaje que indica que el acceso a MCP está deshabilitado. | El acceso a MCP está desactivado para su organización de Fusion. | Solicite a su administrador de Fusion que lo habilite. |
| El agente puede leer escenarios, pero no puede crearlos, ejecutarlos, actualizarlos o eliminarlos. | Las herramientas Escribir MCP están deshabilitadas o la función de su equipo no lo permite. | Pida al administrador de Fusion que habilite las herramientas de escritura o que le otorgue la función de equipo necesaria. |
| Se ha rechazado la autenticación de aplicación personalizada. | La URL de devolución de llamada no está en la lista autorizada. | Pida al administrador que añada la URL de devolución de llamada exacta. |
| Fusion no aparece en Coworker o Coworker no aparece en el carril derecho de Fusion. | Función no habilitada para su organización. <!-- BECKY CHECK ME: confirm whether this is the correct admin guidance before publishing. --> | Póngase en contacto con su administrador de Fusion. |

## Preguntas frecuentes

### ¿Hay un conector Fusion oficial para Claude o ChatGPT?

En este momento no. Utilice la URL personalizada del servidor MCP. Coworker (independiente y en el carril derecho de Fusion) tiene Fusion integrado.

### ¿Puedo utilizar más de una organización de Fusion?

Sí. Puede cambiar la organización activa durante una conversación sin volver a conectarse.

### ¿Qué puede hacer el agente en mi nombre?

El agente actúa como usted, utilizando su función de Fusion y los permisos de equipo. No puede acceder a nada a lo que no pueda acceder en Fusion. Las acciones destructivas requieren una confirmación explícita.

### ¿El agente ve mis secretos de conexión?

No. Las herramientas de conexión y clave devuelven metadatos (nombre, tipo, ámbitos, caducidad), no credenciales ni valores secretos.
