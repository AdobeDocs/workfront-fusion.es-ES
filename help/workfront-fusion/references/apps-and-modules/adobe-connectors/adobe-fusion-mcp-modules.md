---
title: Módulos de MCP de Adobe Fusion
description: Con el módulo MCP de Adobe Fusion, puede enviar un mensaje en inglés sin formato al servidor MCP de Adobe Fusion y permitir que un modelo de IA realice la solicitud.
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: 06ba1c54288fff09f866bffa5c3fce7381c71ad2
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 16%
---
# Módulos de MCP de Adobe Fusion

El conector MCP de Adobe Fusion envía un mensaje en inglés sin formato al servidor de Protocolo de contexto de modelo (MCP) de Adobe Fusion. Un modelo de IA interpreta la solicitud y llama a las herramientas de Fusion necesarias para completarla.

El conector solo funciona con el servidor MCP de Adobe Fusion alojado. No puede apuntar a otro servidor MCP.

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
   <p>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Conexión de Adobe Fusion MCP a Workfront Fusion

Puede crear una conexión directamente desde el módulo MCP de Adobe Fusion.

1. En el módulo MCP de Adobe Fusion, haga clic en **[!UICONTROL Agregar]** junto al campo **Conexión**.
1. Rellene los campos siguientes:

   <table style="table-layout:auto">
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">Nombre de la conexión</td>
        <td>
          <p>Introduzca un nombre para esta conexión.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">Entorno</td>
        <td>
          <p>Seleccione si desea conectarse a un entorno de producción o de no producción.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">Tipo</td>
        <td>
          <p>Seleccione si desea conectarse a una cuenta de servicio o a una personal.</p>
        </td>
      </tr>
    </tbody>
   </table>

1. Haga clic en **[!UICONTROL Continuar]**.

Se le redirigirá a la página de inicio de sesión de Adobe. Inicie sesión con su cuenta de Adobe y apruebe el acceso. Se le redirigirá de nuevo a Workfront Fusion y la nueva conexión estará disponible en el módulo.

## Módulo MCP de Adobe Fusion y sus campos

### Procesar un mensaje de usuario

Este módulo de acción envía un mensaje en inglés sin formato al servidor MCP de Adobe Fusion. Un modelo de IA interpreta el mensaje, llama a las herramientas de Fusion necesarias para completarlo y devuelve el resultado.

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
  </tr> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar Adobe Fusion MCP a Workfront Fusion, consulte <a href="#connect-adobe-fusion-mcp-to-workfront-fusion" class="MCXref xref">Conectar Adobe Fusion MCP a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>Herramientas de solo lectura <i>(opcional)</i></td> 
   <td> <p>Seleccione herramientas específicas de solo lectura para restringir la IA. Si no se selecciona ninguna, se permiten todas las herramientas de solo lectura de esta categoría.</p> </td> 
  </tr> 
  <tr> 
   <td>Herramientas de escritura/eliminación <i>(opcional)</i></td> 
   <td> <p>Seleccione herramientas de escritura o eliminación específicas para restringir la IA. Si no se selecciona ninguna, se permiten todas las herramientas de escritura y eliminación de esta categoría.</p> <p>Para garantizar que un escenario desatendido nunca realice una acción destructiva, se recomienda dejar este campo establecido en una selección deliberadamente vacía en lugar de dejarlo sin restricciones.</p> </td> 
  </tr> 
  <tr> 
   <td>Introduzca el mensaje</td> 
   <td> <p>Introduzca o asigne la instrucción, en inglés sin formato, que desea que realice la IA.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Restringir las herramientas a las que puede llamar la IA

Puede limitar a qué herramientas de Fusion puede llamar la IA seleccionando herramientas en los campos Herramientas de solo lectura y Herramientas de escritura/eliminación.

* Si deja un campo vacío, la IA puede llamar a todas las herramientas de esa categoría.
* Si deja ambos campos vacíos, la IA puede llamar a todas las herramientas del servidor MCP de Fusion.

Para evitar que un escenario desatendido realice una acción de escritura o eliminación, seleccione únicamente las herramientas que desee permitir en el campo Herramientas de solo lectura y, al menos, una herramienta en el campo Herramientas de escritura o eliminación que se sienta cómodo con la llamada de IA.

Los nombres de las herramientas en las listas proceden del servidor MCP de Fusion.

#### Cómo procesa el módulo el mensaje

* El módulo no tiene un turno de seguimiento. Si su pregunta no es clara, la AI hace una suposición razonable y lo indica en la respuesta en lugar de hacerle una pregunta.
* La API verifica la información que puede cambiar mediante el uso de las herramientas.
* La API no realiza ninguna acción de escritura o eliminación aparte de lo que solicita el mensaje.
* El módulo requiere una conexión válida. No se ejecuta sin uno.

#### Salida

El módulo devuelve la siguiente información, que puede asignar en módulos posteriores en el escenario:

* **Respuesta**: La respuesta final de la IA, como texto.
* **Pista de auditoría**: Un registro de la sesión, incluidas las herramientas llamadas, sus argumentos y resultados, y los tiempos.
* **Resumen**: Totales de la sesión, incluido el número de llamadas de herramienta correctas y el estado final.
