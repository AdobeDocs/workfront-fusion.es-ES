---
title: Cifrador de datos
description: Los módulos del cifrador de datos de Adobe Workfront Fusion le permiten cifrar cualquier dato de texto. Actualmente, admiten el cifrado de mensajes mediante AES256 y PGP (OpenPGP).
author: Becky
feature: Workfront Fusion
exl-id: 4b119efe-6762-445e-bbc7-c59437fd5060
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 28%

---

# Cifrador de datos

Los módulos [!UICONTROL Encryptor] de Adobe Workfront Fusion le permiten cifrar cualquier dato de texto. Actualmente admiten el cifrado de mensajes mediante AES256 y PGP ([!UICONTROL OpenPGP]).

Estos módulos requieren cierta familiaridad con los procesos de cifrado.

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
   <p>No se requiere licencia de Workfront Fusion</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Seleccione o paquete de Prime Workfront: su organización debe adquirir Adobe Workfront Fusion.</li><li>Paquete de Ultimate Workfront: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe comprar Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Cifrado y descifrado de mensajes mediante PGP

Al cifrar y descifrar mediante PGP, es necesario utilizar un llavero y crear una clave privada o pública (o ambas).

Para obtener más información sobre las claves públicas y privadas, consulte [glosario de Adobe Workfront Fusion](/help/workfront-fusion/get-started-with-fusion/understand-fusion/fusion-glossary.md).

Para obtener más información sobre las claves, consulte [Claves](/help/workfront-fusion/references/modules/keys.md).

## Los módulos del [!UICONTROL Cifrador de datos] y sus campos

Cuando está configurando módulos del [!UICONTROL Cifrador de datos], se muestran los campos siguientes. El título en negrita en un módulo indica un campo obligatorio.

### Descifrado AES (avanzado)

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Key]</td>
        <td>Seleccione la clave que desea que utilice el módulo. Para crear una clave, haga clic en <b>Agregar</b> e introduzca el nombre, la clave y el tipo de codificación de la clave.</td>
    </tr>
    <tr>
        <td>Bits</td>
        <td>Seleccione si desea que el módulo utilice codificación de 128 o 256 bits.</td>
    </tr>
    <tr>
        <td>Codificación de entrada</td>
        <td>Seleccione el tipo de codificación de entrada que desea utilizar:
        <ul>
        <li>Binario</li>
        <li>Base 64</li>
        <li>Hexadecimal</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Datos</td>
        <td>Introduzca o asigne los datos que desea descifrar.</td>
    </tr>
    <tr>
        <td>Codificación de salida</td>
        <td>Seleccione el tipo de codificación de salida que desee utilizar:
        <ul>
        <li>ASCII</li>
        <li>Binario</li>
        <li>UTF-8</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Algoritmo de cifrado</td>
        <td>Seleccione el algoritmo de cifrado que desee utilizar:
        <ul>
        <li>Hemograma completo</li>
        <li>GCM</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Codificación del vector de inicialización</td>
        <td>Seleccione la codificación del vector de inicialización que desee utilizar:
        <ul>
        <li>UTF-8</li>
        <li>Binario</li>
        <li>Base 64</li>
        <li>Hexadecimal</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Codificación de etiqueta de autenticación</td>
        <td>Seleccione la codificación de etiqueta de autenticación que desee utilizar:
        <ul>
        <li>UTF-8</li>
        <li>Binario</li>
        <li>Base 64</li>
        <li>Hexadecimal</li>
        </ul>
        </td>
    </tr>
</table>

### Descifrado AES (simple)

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Key]</td>
        <td>Seleccione la clave que desea que utilice el módulo. Para crear una clave, haga clic en <b>Agregar</b> e introduzca el nombre, la clave y el tipo de codificación de la clave.</td>
    </tr>
   <tr>
        <td>Codificación de entrada</td>
        <td>Seleccione el tipo de codificación de entrada que desea utilizar:
        <ul>
        <li>Binario</li>
        <li>Base 64</li>
        <li>Hexadecimal</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Datos</td>
        <td>Introduzca o asigne los datos que desea descifrar.</td>
    </tr>
    <tr>
        <td>Codificación de salida</td>
        <td>Seleccione el tipo de codificación de salida que desee utilizar:
        <ul>
        <li>ASCII</li>
        <li>Binario</li>
        <li>UTF-8</li>
        </ul>
        </td>
     </tr>
    <tr>
        <td>Clave secreta</td>
        <td>Escriba o asigne la clave secreta que desee utilizar.</td>
    </tr>
</table>

### Cifrado AES (avanzado)

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Key]</td>
        <td>Seleccione la clave que desea que utilice el módulo. Para crear una clave, haga clic en <b>Agregar</b> e introduzca el nombre, la clave y el tipo de codificación de la clave.</td>
    </tr>
    <tr>
        <td>Bits</td>
        <td>Seleccione si desea que el módulo utilice codificación de 128 o 256 bits.</td>
    </tr>
    <tr>
        <td>Codificación de entrada</td>
        <td>Seleccione el tipo de codificación de entrada que desea utilizar:
        <ul>
        <li>Binario</li>
        <li>ASCII</li>
        <li>Hexadecimal</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Datos</td>
        <td>Escriba o asigne los datos que desea cifrar.</td>
    </tr>
    <tr>
        <td>Codificación de salida</td>
        <td>Seleccione el tipo de codificación de salida que desee utilizar:
        <ul>
        <li>ASCII</li>
        <li>Binario</li>
        <li>UTF-8</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Algoritmo de cifrado</td>
        <td>Seleccione el algoritmo de cifrado que desee utilizar:
        <ul>
        <li>Hemograma completo</li>
        <li>GCM</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Codificación del vector de inicialización</td>
        <td>Seleccione la codificación de etiqueta de autenticación que desee utilizar:
        <ul>
        <li>UTF-8</li>
        <li>Binario</li>
        <li>Base 64</li>
        <li>Hexadecimal</li>
        </ul>
        </td>
    </tr>
</table>

### Cifrado AES (simple)

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Key]</td>
        <td>Seleccione la clave que desea que utilice el módulo. Para crear una clave, haga clic en <b>Agregar</b> e introduzca el nombre, la clave y el tipo de codificación de la clave.</td>
    </tr>
   <tr>
        <td>Codificación de entrada</td>
        <td>Seleccione el tipo de codificación de entrada que desea utilizar:
        <ul>
        <li>Binario</li>
        <li>ASCII</li>
        <li>UTF-8</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Datos</td>
        <td>Escriba o asigne los datos que desea cifrar.</td>
    </tr>
    <tr>
        <td>Codificación de salida</td>
        <td>Seleccione el tipo de codificación de salida que desee utilizar:
        <ul>
        <li>Base 64</li>
        <li>Binario</li>
        <li>Hexadecimal</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Clave secreta</td>
        <td>Escriba o asigne la clave secreta que desee utilizar.</td>
    </tr>
</table>


### Crear firma digital

Este módulo le permite descifrar un mensaje utilizando claves públicas y privadas.

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Private key]</td>
        <td>Seleccione la clave privada que se utilizará para esta firma. Para agregar una clave privada, haz clic en <b>Agregar</b> e ingresa el nombre, el texto de la clave y la frase de contraseña de la clave.</td>
    </tr>
    <tr>
        <td>Algoritmo </td>
        <td>Seleccione si desea utilizar RSA-SHA1 o RSA-SHA256. </td>
    </tr>
   <tr>
        <td>Codificación de entrada</td>
        <td>Seleccione el tipo de codificación de entrada que desea utilizar:
        <ul>
        <li>ASCII</li>
        <li>Binario</li>
        <li>UTF-8</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Codificación de salida</td>
        <td>Seleccione el tipo de codificación de salida que desee utilizar:
        <ul>
        <li>Base 64</li>
        <li>Hexadecimal</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Datos</td>
        <td>Introduzca o asigne los datos a partir de los cuales desea crear la firma.</td>
    </tr>
</table>

### Descifrado de un mensaje PGP

Este módulo le permite descifrar un mensaje utilizando claves públicas y privadas.

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Private key]</td>
        <td>Seleccione la clave privada del destinatario que se utilizará para este mensaje. Para agregar una clave privada, haz clic en <b>Agregar</b> e ingresa el nombre, el texto de la clave y la frase de contraseña de la clave.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Public key]</td>
        <td>Introduzca la clave pública del remitente. Esto puede autenticar la identidad del remitente.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Message]</td>
        <td>Asigne el mensaje que desea descifrar.</td>
    </tr>
</table>

### Cifrado de un mensaje PGP

Este módulo le permite cifrar un mensaje utilizando claves públicas y privadas.

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Private key]</td>
        <td>Introduzca la clave privada del remitente. Esto puede autenticar la identidad del remitente.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Public key]</td>
        <td>Introduzca la clave pública del destinatario.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Message]</td>
        <td>Escriba el mensaje que desea cifrar.</td>
    </tr>
    </table>
