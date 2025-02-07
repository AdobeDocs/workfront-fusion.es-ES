---
title: Generación de un segmento de escenario mediante IA
description: Puede utilizar IA para escribir un mensaje de texto que describa lo que necesita que haga un segmento de su escenario. A continuación, Fusion genera uno o más módulos que realizan esas acciones y que puede utilizar en su escenario.
author: Becky
feature: Workfront Fusion
exl-id: d231e33a-6033-4e3c-b1d4-7034797c45a5
source-git-commit: 9d29abc82a3bb09affc4d17d7ea214d7bb850294
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 23%

---

# Generación de un segmento de escenario mediante IA

<!--DO NOT DELETE - linked through CSH-->

<!--Check if this is in GA before repo goes live. If not, hide this article.-->

<!--Check if they need to have signed the rider and stuff-->

Puede utilizar IA para escribir un mensaje de texto que describa lo que necesita que haga un segmento de su escenario. A continuación, Fusion genera uno o más módulos que realizan esas acciones y que puede utilizar en su escenario.

Los segmentos de escenario generados contienen módulos para un solo conector. Para generar módulos para un conector diferente, cree un mensaje independiente y, a continuación, únase a los segmentos de escenario en su escenario.

Al igual que con cualquier elemento generado a partir de IA, le recomendamos que compruebe y pruebe los módulos generados para asegurarse de que funcionan según lo previsto.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] paquete</td> 
   <td> <p>Cualquiera</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licencia</td> 
   <td> <p>Nuevo: [!UICONTROL Standard]</p><p>O</p><p>Actual: [!UICONTROL Work] o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licencia**</td> 
   <td>
   <p>Actual: no se requiere licencia para [!DNL Workfront Fusion].</p>
   <p>O</p>
   <p>Heredado: cualquiera </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>[!UICONTROL Select] o plan [!UICONTROL Prime] [!DNL Workfront]: su organización debe comprar [!DNL Adobe Workfront Fusion].</li><li>[!UICONTROL Ultimate] [!DNL Workfront] plan: [!DNL Workfront Fusion] está incluido.</li></ul>
   <p>O</p>
   <p>Actual: su organización debe comprar [!DNL Adobe Workfront Fusion].</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Su organización debe cumplir los siguientes requisitos previos para utilizar esta funcionalidad:

* Su organización debe haber participado en el programa Beta de Workfront AI Assistant.
* El Adobe debe tener un acuerdo de IA general de Adobe firmado en el archivo para su organización.

  Para obtener más información sobre la firma del acuerdo, consulte [Firmar el acuerdo de IA de generación de Adobe](https://experienceleague.adobe.com/en/docs/workfront/using/basics/ai-assistant/ai-assistant-overview#sign-the-adobe-gen-ai-agreement) en el artículo Información general del asistente de IA en la documentación de Workfront.

## Aplicaciones de módulo de IA admitidas actualmente

Fusion AI puede generar actualmente módulos que se conectan a las siguientes aplicaciones:

* Adobe Firefly
* Azure OpenAI
* Microsoft Graph
* Planificación de Adobe Workfront
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

1. Haga clic en la ficha **[!UICONTROL Scenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea agregar un módulo.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haga clic en el icono **Asistente de IA** ![icono Asistente de IA](assets/ai-assistant-icon.png) cerca de la esquina superior derecha de la pantalla.
1. Escriba un mensaje de texto en el panel Asistente de IA.

   Para obtener sugerencias sobre las solicitudes, consulte [Sugerencias para crear solicitudes para segmentos de escenario](#tips-for-creating-prompts-for-scenario-segments) en este artículo.

   El asistente de IA genera el módulo o conjunto de módulos.
1. (Condicional) Si es necesario, agregue el token de API para la aplicación en los módulos.
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
* `Change campaign summary of the record 'xyz-123' from Adobe Workfront Planning`
Esto incluye la aplicación `Workfront Planning` y la acción `change campaign summary`.
* `Get all field details in the record type with ID 'test-record' from Adobe Workfront Planning`
Esto incluye la aplicación `Workfront Planning` y la acción `get field details`.

El siguiente ejemplo NO es correcto:

* `Generate an image in Adobe Firefly and upload it to Dropbox`

  Este ejemplo es incorrecto porque incluye varias aplicaciones

>[!ENDSHADEBOX]

Tenga en cuenta lo siguiente al crear mensajes de texto:

* Utilice un lenguaje directo y sencillo.
* Compruebe y pruebe el segmento de escenario. Si no funciona como se espera, perfeccione el mensaje e inténtelo de nuevo.
