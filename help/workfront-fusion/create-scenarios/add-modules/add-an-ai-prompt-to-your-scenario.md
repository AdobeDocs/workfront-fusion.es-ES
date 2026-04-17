---
title: Añadir un indicador de IA a su escenario
description: Puede incluir una solicitud de IA en su escenario que se conecte a su
author: Becky
feature: Workfront Fusion
exl-id: d0ac0d0b-e3a0-46de-801d-e53c1c4d63ff
source-git-commit: 3d957c219cdc5fed4fdf9b0649cab724fae21871
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 0%

---

# Añada una solicitud de IA a su escenario

Puede incluir una petición de datos de IA en su escenario mediante el Protocolo de contexto de modelo (MCP) combinado con modelos de lenguaje de gran tamaño (LLM). Al configurarlos en el módulo del agente de MCP, puede utilizar la inteligencia artificial para configurar flujos de trabajo eficientes, seguros y flexibles.

## Descripción general del protocolo de contexto de modelo

El Protocolo de contexto de modelo (MCP) es una forma de conectar de forma segura los modelos de lenguaje de IA con otras aplicaciones. Los servidores MCP se configuran para permitir que el modelo de IA acceda a la aplicación. A continuación, puede enviar una solicitud al modelo de IA y devolver información de la aplicación.

Por ejemplo, puede configurar un servidor MCP para conectar un modelo de IA con Gmail. Cuando envía el mensaje &quot;Dame mis últimos 5 correos electrónicos de Gmail&quot; al modelo de idioma grande, analiza ese mensaje y lo envía al servidor MPC de Gmail, que puede acceder a tu Gmail y devolver los correos electrónicos.

El módulo Agente MCP permite procesar una solicitud de usuario utilizando un modelo de idioma y servidores MCP.

## Ventajas de utilizar MCP en los casos de Fusion

El uso de MCP en sus escenarios ofrece las siguientes ventajas:

* El uso de MCP en su escenario reduce la necesidad de pensar en todas las situaciones y posibles variaciones de una acción. Al utilizar un símbolo del sistema, se elimina la necesidad de utilizar regex o analizar datos para tener en cuenta estas variaciones.
* Puede proporcionar contexto a la solicitud utilizando elementos asignados de módulos anteriores u otras funciones del panel de asignación.
* El uso de un símbolo del sistema puede ser más eficiente y flexible que la creación de un escenario con módulos específicos, ya que puede utilizar el razonamiento en el símbolo del sistema y seleccionar el mejor curso de acción del contexto disponible.
* Debido a que configura los servidores MCP a los que se puede conectar el módulo, controla la seguridad de ese servidor y puede estar seguro de que la seguridad se ajusta a las necesidades de su organización.

>[!NOTE]
>
>La funcionalidad disponible depende de las herramientas disponibles en el servidor MCP y no está controlada por Fusion.

## Añada una solicitud de IA a su escenario

Puede agregar una petición de datos de IA a su escenario mediante el módulo del agente de MCP.

Para obtener instrucciones, consulte [Módulo del agente MCP](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/model-context-protocol-mcp-connector.md).
