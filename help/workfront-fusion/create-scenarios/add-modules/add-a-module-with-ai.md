---
title: Generar un segmento de escenario mediante IA
description: Puede utilizar IA para escribir un mensaje de texto que describa lo que necesita que haga un segmento de su escenario. A continuación, Fusion genera uno o más módulos que realizan esas acciones y que puede utilizar en su escenario.
author: Becky
feature: Workfront Fusion
exl-id: d231e33a-6033-4e3c-b1d4-7034797c45a5
source-git-commit: 2bec2607d55e4ba2ffd6ddcae6daa51071b204c4
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 31%

---

# Generar un segmento de escenario mediante IA

<!--DO NOT DELETE - linked through CSH-->

<!--Check if this is in GA before repo goes live. If not, hide this article.-->

<!--Check if they need to have signed the rider and stuff-->

Puede utilizar IA para escribir un mensaje de texto que describa lo que necesita que haga un segmento de su escenario. A continuación, Fusion genera uno o más módulos que realizan esas acciones y que puede utilizar en su escenario.

Los segmentos de escenario generados contienen módulos para un solo conector. Para generar módulos para un conector diferente, cree un mensaje independiente y, a continuación, únase a los segmentos de escenario en su escenario.

Al igual que con cualquier elemento generado a partir de IA, le recomendamos que compruebe y pruebe los módulos generados para asegurarse de que funcionan según lo previsto.

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

Su organización debe cumplir los siguientes requisitos previos para utilizar esta funcionalidad:

* Su organización debe haber participado en el programa Beta de Workfront AI Assistant.
* Adobe debe tener un acuerdo firmado de Adobe Gen AI archivado para su organización.

  Para obtener más información sobre la firma del acuerdo, consulte [Firmar el acuerdo](https://experienceleague.adobe.com/es/docs/workfront/using/basics/ai-assistant/ai-assistant-overview#sign-the-adobe-gen-ai-agreement) de IA de Adobe Systems generación en el artículo Información general de AI Assistant en la documentación de Workfront.

## Aplicaciones de módulo de IA admitidas actualmente

Fusion AI puede generar actualmente módulos que se conectan a las siguientes aplicaciones:

* Adobe Firefly
* Azure OpenAI
* Microsoft Graph
* Adobe Workfront Planning
* Adobe Analytics
* Servicios Adobe PDF
* Adobe Marketo
* Adobe Frame.io
* Dropbox
* NetSuite
* Google Calendar
* Atlassian Jira
* GitLab
* Spotify
* Bitbucket
* OpenAI
* Slack

## Generar módulos

1. Haga clic en el **[!UICONTROL pestaña Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desee agregar un módulo.
1. Haga clic en cualquier lugar del escenario para entrar en el editor del escenario.
1. Haga clic en el icono **Asistente de IA** ![icono Asistente de IA](assets/ai-assistant-icon.png) cerca de la esquina superior derecha de la pantalla.
1. Escriba un mensaje de texto en el panel Asistente de IA.

   Para obtener sugerencias sobre las solicitudes, consulte [Sugerencias para crear solicitudes para segmentos de escenario](#tips-for-creating-prompts-for-scenario-segments) en este artículo.

   El asistente de IA genera el módulo o conjunto de módulos.
1. (Condicional) Si es necesario, agregue el token de API para el aplicación a los módulos.
1. Compruebe los módulos para asegurarse de que están configurados para la aplicación y la acción adecuadas.
1. (Condicional) Si la sección de escenario generado no está adjunta al escenario, arrástrela a su lugar.

Se recomienda probar los módulos para asegurarse de que funcionan según lo previsto.

## Sugerencias para crear peticiones de datos para segmentos de escenario

Los mensajes de texto deben incluir la siguiente información como mínimo:

* La aplicación a la que se está conectando
* La acción o acciones que desea realizar

>[!IMPORTANT]
>
>Puede generar más de un módulo a la vez, pero solo puede generar módulos para una aplicación a la vez.

>[!BEGINSHADEBOX]

**Ejemplos**:

* `Delete the records 'xyz-123', 'xyz-456', 'xyz-789' from Adobe Workfront Planning`
Esto incluye la aplicación `Workfront Planning` y la acción `delete records`. Este mensaje crea tres módulos, uno para cada registro que se eliminará.
* `Change campaign summary of the record 'xyz-123' from Adobe Workfront Planning`Esto incluye la aplicación `Workfront Planning` y la acción `change campaign summary`.
* `Get all field details in the record type with ID 'test-record' from Adobe Workfront Planning`
Esto incluye la aplicación `Workfront Planning` y la acción `get field details`.

El siguiente ejemplo NO es correcto:

* `Generate an image in Adobe Firefly and upload it to Dropbox`

  Este ejemplo es incorrecto porque incluye varias aplicaciones

>[!ENDSHADEBOX]

Tenga en cuenta lo siguiente al crear mensajes de texto:

* Utilice un lenguaje directo y sencillo.
* Compruebe y pruebe el segmento de escenario. Si no funciona como se espera, perfeccione el mensaje e inténtelo de nuevo.
