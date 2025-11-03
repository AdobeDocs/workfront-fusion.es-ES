---
title: Módulos JSONata
description: El conector JSONata de Adobe Workfront Fusion proporciona un módulo para procesar datos en formato JSON para que Adobe Workfront Fusion pueda trabajar aún más con el contenido de datos.
author: Becky
feature: Workfront Fusion
exl-id: 8c117ecb-3c05-47d4-a629-18dbc546e2a2
source-git-commit: 4697ea1449f77ddb8648658990098b3b4bc58ad2
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 8%

---

# Módulos [!UICONTROL JSONata]

El conector [!UICONTROL JSONata] de Adobe Workfront Fusion le permite consultar objetos JSON. Este módulo no requiere conexión.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront</td> 
   <td> <p>Cualquier paquete de flujo de trabajo de Adobe Workfront y cualquier paquete de integración y automatización de Adobe Workfront</p><p>Workfront Ultimate</p><p>Paquetes Workfront Prime y Select, con una compra adicional de Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencias de Adobe Workfront</td> 
   <td> <p>Estándar</p><p>Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete Select o Prime Workfront que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++



## Módulos JSONata y sus campos

### Evaluar

Este módulo de acción consulta un objeto JSON y devuelve una matriz.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expression]</td> 
   <td>Introduzca la expresión que desea utilizar para evaluar el objeto JSON. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data] </td> 
   <td> Introduzca el objeto JSON que desea evaluar.  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Stringify output] </td> 
   <td> Active esta opción para convertir la salida en una cadena.  </td> 
  </tr> 
  </tbody>
  </table>

>[!BEGINSHADEBOX]

**Ejemplo**:

El objetivo es devolver una matriz de nombres del siguiente objeto JSON:

```JSON
{
  "people": [
    { "name": "Alice", "age": 30 },
    { "name": "Bob", "age": 25 },
    { "name": "Charlie", "age": 35 }
  ]
}
```

1. En el campo de expresión, escriba `people.name`.
1. En el campo de datos, introduzca el objeto JSON.

El módulo devuelve una matriz de nombres extraídos del objeto JSON.

>[!ENDSHADEBOX]



### MCP de JSONata

Este módulo de acción genera expresiones JSONata analizando los esquemas de entrada y salida especificados. Proporcione los esquemas que utiliza el Protocolo de contexto de modelo (MCP) para generar la expresión que transforma la entrada en la salida.




<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Seleccione la conexión que utiliza para conectarse al modelo de idioma grande (LLM) que desea utilizar para este módulo.</p> <p>Actualmente, solo se admite la clave API Anthropic.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Esquema de entrada]</td> 
   <td> <p>Introduzca o asigne el esquema de entrada que se utilizará para esta expresión.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Esquema de salida]</td> 
   <td> <p>Introduzca o asigne el esquema de salida que se utilizará para esta expresión.</p> </td> 
  </tr> 
 </tbody> 
</table>
