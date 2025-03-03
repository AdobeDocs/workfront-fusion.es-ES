---
title: Módulos JWT
description: La aplicación  [!DNL Adobe Workfront Fusion] [!UICONTROL JWT] proporciona un módulo que crea tokens JWT basados en el algoritmo proporcionado.
author: Becky
feature: Workfront Fusion
exl-id: 380f60db-b2ec-411a-86ee-0d5699f19b41
source-git-commit: e1e15985db9683525250d1f9f9276224b2baf0e6
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 82%

---

# [!UICONTROL JWT] módulo

La aplicación [!DNL Adobe Workfront Fusion] [!UICONTROL JWT] proporciona un módulo que crea tokens JWT basados en el algoritmo proporcionado.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">paquete de Adobe Workfront</td> 
   <td> <p>Cualquiera</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencia de Adobe Workfront</td> 
   <td> <p>Nuevo: estándar</p><p>O</p><p>Actual: Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion**</td> 
   <td>
   <p>No se requiere licencia de Workfront Fusion.</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Seleccione o paquete de Prime Workfront: su organización debe adquirir Adobe Workfront Fusion.</li><li>Paquete de Ultimate Workfront: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe adquirir Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

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
