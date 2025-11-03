---
title: Módulos JWT
description: La aplicación Adobe Workfront Fusion [!UICONTROL JWT] proporciona un módulo que crea tokens JWT basados en el algoritmo proporcionado.
author: Becky
feature: Workfront Fusion
exl-id: 380f60db-b2ec-411a-86ee-0d5699f19b41
source-git-commit: 4697ea1449f77ddb8648658990098b3b4bc58ad2
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 77%

---

# Módulo [!UICONTROL JWT]

La aplicación Adobe Workfront Fusion [!UICONTROL JWT] proporciona un módulo que crea tokens JWT basados en el algoritmo proporcionado.

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



## Información de API de JWT

El conector JWT utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
   <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.1.5</td> 
  </tr>
 </tbody> 
 </table>

## Módulo JWT y sus campos

### Generar JWT

Este módulo genera un JWT basado en el algoritmo seleccionado.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Algorithm]</td> 
   <td> <p>Seleccione el algoritmo con el que desea generar el JWT.</p> <ul>
   <li><b>HS256</b>: HMAC con algoritmo hash SHA-256</li>
   <li><b>HS384</b>: HMAC con algoritmo hash SHA-384</li>
   <li><b>HS512</b>: HMAC con algoritmo hash SHA-512</li>
   <li><b>RS256</b>: RSASSA-PKCS1-v1_5 con algoritmo hash SHA-256</li>
   <li><b>RS384</b>: RSASSA-PKCS1-v1_5 con algoritmo hash SHA-384</li>
   <li><b>RS512</b>: RSASSA-PKCS1-v1_5 con algoritmo hash SHA-512</li>
   <li><b>PS256</b>: RSASSA-PSS con algoritmo hash SHA-256 (solo nodo ^6.12.0 O &gt;=8.0.0)</li>
   <li><b>PS384</b>: RSASSA-PSS con algoritmo hash SHA-384 (solo nodo ^6.12.0 O &gt;=8.0.0)</li>
   <li><b>PS512</b>: RSASSA-PSS con algoritmo hash SHA-512 (solo nodo ^6.12.0 O &gt;=8.0.0)</li>
   <li><b>ES256</b>: ECDSA con curva P-256 y algoritmo hash SHA-256</li>
   <li><b>ES384</b>: ECDSA con curva P-384 y algoritmo hash SHA-384</li>
   <li><b>ES512</b>: ECDSA con curva P-521 y algoritmo hash SHA-512</li>
   </ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Payload] </td> 
   <td> <p>Para cada elemento de carga útil que desee añadir, haga clic en <b>Añadir elemento</b> e introduzca la clave y el valor del elemento.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Options] </td> 
   <td> <p>Para cada elemento de opción que desee añadir, haga clic en <b>Añadir elemento</b> e introduzca la clave y el valor del elemento.</p> <p>Las claves disponibles son las siguientes:
   <ul>
   <li><b>algoritmo</b>: (predeterminado: RS256)</li>
   <li><b>expiresIn</b>: expresado en segundos o en una cadena que describe un lapso de tiempo (por ejemplo, 2 días, 10 h, 7 d). Un valor numérico se interpreta como una cantidad en segundos. Si utiliza una cadena, asegúrese de proporcionar las unidades de tiempo (días, horas, etc.); de lo contrario, se utiliza la unidad de milisegundos de forma predeterminada (120 es igual a 120 ms).</li>
   <li><b>notBefore</b>: expresado en segundos o en una cadena que describe un periodo de tiempo (por ejemplo, 2 días, 10 h, 7 d). Un valor numérico se interpreta como una cantidad en segundos. Si utiliza una cadena, asegúrese de proporcionar las unidades de tiempo (días, horas, etc.); de lo contrario, se utiliza la unidad de milisegundos de forma predeterminada (120 es igual a 120 ms).
</li>
   <li><b>audience</b></li>
   <li><b>issuer</b></li>
   <li><b>jwtid</b></li>
   <li><b>subject</b></li>
   <li><b>noTimestamp</b></li>
   <li><b>header</b></li>
   <li><b>keyid</b></li>
   <li><b>mutatePayload</b>: si es <code>true</code>, la función signo modificará directamente el objeto de carga útil. Esto resulta útil si necesita una referencia sin procesar a la carga útil después de que se le hayan aplicado notificaciones, pero antes de que se haya codificado en un token.</li>
   <li><b>allowInsecureKeySizes</b>: si es <code>true</code>, permite que se usen claves privadas con un módulo inferior a 2048 para RSA.</li>
   <li><b>allowInvalidAsymmetricKeyTypes</b>: si es <code>true</code>, permite claves asimétricas que no coinciden con el algoritmo especificado. Esta opción está diseñada únicamente para la compatibilidad con versiones anteriores y debe evitarse.</li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>
