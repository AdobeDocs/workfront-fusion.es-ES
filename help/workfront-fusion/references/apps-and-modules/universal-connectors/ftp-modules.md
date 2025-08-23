---
title: Módulos FTP
description: Los módulos FTP permiten supervisar los cambios realizados en un archivo de una carpeta seleccionada, cargar nuevos archivos en la carpeta deseada y modificar o eliminar los archivos existentes que ya se encuentran en una carpeta.
author: Becky
feature: Workfront Fusion
exl-id: 1e14f778-ab8c-421f-a4b4-c57be66c7cad
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1391'
ht-degree: 79%

---

# Módulos FTP

Los módulos FTP permiten supervisar los cambios realizados en un archivo de una carpeta seleccionada, cargar nuevos archivos en la carpeta deseada y modificar o eliminar los archivos existentes que ya se encuentran en una carpeta.

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
   <p>Actual: No se requiere licencia de Workfront Fusion</p>
   <p>O</p>
   <p>Heredado: Workfront Fusion para la automatización e integración del trabajo </p>
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

## Requisitos previos

Para utilizar módulos FTP, debe tener una cuenta con un servicio FTP.

## Crear una conexión en un módulo FTP {#create-a-connection}

1. En cualquier módulo FTP, haga clic en **Agregar** junto al cuadro de conexión.
1. Cumplimente los campos siguientes.

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td>[!UICONTROL Connection name]</td> 
      <td> <p> Escriba el nombre de la conexión FTP.</p> </td> 
     </tr> 
     <tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Environment]</p> </td> 
      <td> <p>Seleccione si está utilizando un entorno de producción o de no producción.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Type]</p> </td> 
      <td> <p>Seleccione si utiliza una cuenta de servicio o una cuenta personal.</p> </td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL Host] </td> 
      <td> <p>Introduzca el nombre de host del servidor FTP. Ejemplo: <code>myftp123.server.com</code></p> </td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL Port] </td> 
      <td> <p>Introduzca el número de puerto del servidor FTP. Ejemplo: <code>21</code></p> </td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL User name] </td> 
      <td> <p>Introduzca el nombre de usuario de su cuenta de FTP.</p> </td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL Password] </td> 
      <td> <p>Introduzca la contraseña de la cuenta de FTP.</p> </td> 
     </tr> 
     <tr> 
      <td> <p>Usar una conexión segura (TLS)</p> </td> 
      <td> <p>Seleccione si desea utilizar una conexión segura.</p> <ul><li><p><b>[!UICONTROL No]</b></p> <p>La conexión no es segura.</p></li><li> <p><b>Cifrado explícito</b> o <b>cifrado implícito</b></p> <p>La conexión está protegida mediante SSL.</p> </td> 
     </tr> 
    <tr> 
   <td> <p>[!UICONTROL Reject unauthorized certificates]</p> </td> 
   <td> <p>Active esta opción para comprobar el certificado del servidor FTP. Si la verificación falla, no se creará la conexión. Para aprobar la verificación, el certificado debe cumplir uno de los siguientes criterios:</p> 
    <ul> 
     <li>estar firmado por una entidad emisora de certificados raíz</a></li> 
     <li>estar firmado por una autoridad de certificación intermedia. En este caso, todos los certificados intermedios deben instalarse en el servidor FTP.</li> 
     <li>ser un certificado firmado automáticamente suministrado en el campo [!UICONTROL Self-signed certificate] (consulte a continuación)</li> </ul>
     <p>Si esta opción está desactivada, el certificado del servidor FTP no se verifica. Desaconsejamos desactivar la opción, ya que hace que la conexión sea insegura y supone un riesgo de seguridad grave.</p></td>
    </tr> 
    <tr> 
     <td> <p>[!UICONTROL Self-signed certificate]</p> </td> 
     <td> <p>Haga clic en el botón <b>[!UICONTROL Extract]</b> para abrir el cuadro de diálogo de carga.</p> <p>Cargue el certificado para utilizar TLS con el certificado autofirmado. Workfront Fusion no conserva ni almacena ningún dato que usted proporcione, como archivos y contraseñas. El archivo y la contraseña solo se utilizan para extraer el certificado.</p> </td> 
    </tr> 
   </tbody> 
   </table>

1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.

## Módulos FTP y sus campos

* [Activadores](#triggers)
* [Acciones](#actions)

### Activadores

#### [!UICONTROL Ver archivos]

[!UICONTROL Ver archivos] es el único módulo de activador para FTP. Supervisa el contenido del archivo de la carpeta seleccionada. El déclencheur se ejecuta cuando se agrega un nuevo archivo sobre la carpeta especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo establecer una conexión con la cuenta de FTP, consulte <a href="#create-a-connection" class="MCXref xref">[!UICONTROL Create a connection] en un módulo FTP</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Folder]</p> </td> 
   <td> <p>Seleccione la carpeta que desee ver.</p> <p><b>Nota:</b> Solo se permite una carpeta por escenario. Las subcarpetas se omiten.</p> <p><b>Sugerencia:</b> Para ver varias carpetas, cree un escenario independiente para cada una de ellas.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned files] </td> 
   <td> <p>Defina el número máximo de resultados con los que desea que trabaje el módulo durante un ciclo. Si el valor es demasiado alto, la conexión puede interrumpirse en el lado del servidor FTP. Workfront Fusion no influye en esto. Le recomendamos que establezca un valor menor y defina un valor mayor para el número máximo de ciclos o que ejecute el escenario con más frecuencia.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Acciones

* [[!UICONTROL Cambiar permisos]](#change-permissions)
* [[!UICONTROL Crear una carpeta]](#create-a-folder)
* [[!UICONTROL Eliminar un archivo]](#delete-a-file)
* [[!UICONTROL Eliminar una carpeta]](#delete-a-folder)
* [[!UICONTROL Obtener un archivo]](#get-a-file)
* [[!UICONTROL Lista de archivos de una carpeta]](#list-of-files-in-a-folder)
* [[!UICONTROL Mover un archivo o carpeta]](#move-a-file-or-folder)
* [[!UICONTROL Subir] un archivo](#upload-a-file)

#### [!UICONTROL Cambiar permisos]

Este módulo de acción cambia la configuración de permisos de un archivo o carpeta.

<table>
   <col>
   <col>
   <tbody>
         <tr>
            <td>[!UICONTROL Connection]</td>
            <td>Para obtener instrucciones sobre el establecimiento de una conexión en la cuenta de FTP, consulte <a href="#Create" class="MCXref xref" >[!UICONTROL Create a connection] en un módulo FTP</a> en este artículo.</td>
         </tr>
         <tr>
            <td>[!UICONTROL Change permission settings of]</td>
            <td>
               <p>Seleccione si desea cambiar la configuración de un archivo o carpeta.</p>
            </td>
         </tr>
         <tr>
            <td>[!UICONTROL File path]</td>
            <td>Introduzca o asigne la ruta del archivo a la carpeta o archivo.</td>
         </tr>
         <tr>
            <td>[!UICONTROL Permissions]</td>
            <td>
               <p>Establezca los permisos de archivo o carpeta que desee. Utilice los parámetros chmod. Por ejemplo: <code>777 </code> o <code>-rwxrwxrwx</code>.</p>
               <p>Los permisos deben coincidir con el patrón <code> /(.?([r-][w-][x-]){3})|[0-7]{3,4}/</code>.</p>
            </td>
         </tr>
   </tbody>
</table>

#### [!UICONTROL Crear una carpeta]

Este módulo de acción crea una nueva carpeta.

<table>
   <col>
   <col>
   <tbody>
         <tr>
            <td>[!UICONTROL Connection]</td>
            <td>Para obtener instrucciones sobre cómo establecer una conexión con la cuenta de FTP, consulte <a href="#Create" class="MCXref xref" >[!UICONTROL Create a connection] en un módulo FTP</a> en este artículo.</td>
         </tr>
         <tr>
            <td>[!UICONTROL Folder path]</td>
            <td>Introduzca o asigne la ruta del archivo a la nueva carpeta.</td>
         </tr>
         <tr>
            <td>[!UICONTROL New folder name]</td>
            <td>
               <p>Introduzca o asigne un nombre para la nueva carpeta.</p>
            </td>
         </tr>
   </tbody>
</table>

#### [!UICONTROL Eliminar un archivo]

Este módulo de acción elimina un archivo de la carpeta especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
            <td>Para obtener instrucciones sobre cómo establecer una conexión con la cuenta de FTP, consulte <a href="#Create" class="MCXref xref" >[!UICONTROL Create a connection] en un módulo FTP</a> en este artículo.</td>
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Seleccione la carpeta FTP desde la que desee eliminar un archivo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File name]</td> 
   <td> <p> Introduzca el nombre de archivo, incluida su extensión. Ejemplo: <code>[!DNL image].png</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Eliminar una carpeta]

Este módulo de acción elimina permanentemente la carpeta especificada.

<table>
   <col>
   <col>
   <tbody>
         <tr>
            <td>[!UICONTROL Connection]</td>
            <td>Para obtener instrucciones sobre cómo establecer una conexión con la cuenta de FTP, consulte <a href="#Create" class="MCXref xref" >[!UICONTROL Create a connection] en un módulo FTP</a> en este artículo.</td>
         </tr>
         <tr>
            <td>[!UICONTROL Folder]</td>
            <td>
               <p>Seleccione la carpeta FTP desde la que desee eliminar un archivo.</p>
            </td>
         </tr>
   </tbody>
</table>

#### [!UICONTROL Obtener un archivo]

Este módulo de acción recupera un archivo del servidor FTP.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo establecer una conexión con la cuenta de FTP, consulte <a href="#creating-the-ftp-connection" class="MCXref xref">Creación de la conexión FTP</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File path]</td> 
   <td> <p> Introduzca la ruta del archivo que desea obtener.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Lista de archivos en una carpeta]

Este módulo de acción recupera información de archivos o carpetas.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo establecer una conexión con la cuenta de FTP, consulte <a href="#creating-the-ftp-connection" class="MCXref xref">Creación de la conexión FTP</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Seleccione la carpeta FTP en la que desee buscar.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Show] </td> 
   <td> <p>Seleccione si desea recuperar información sobre archivos o carpetas, o ambos.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search] </td> 
   <td> <p>Introduzca el término de búsqueda. Si no se escribe ningún término de búsqueda, se recuperarán todos los archivos o carpetas de la carpeta especificada.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned files]</td> 
   <td> <p>Introduzca o asigne el número máximo de resultados con los que desea que funcione el módulo durante un ciclo.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Mover un archivo o carpeta]

Este módulo de acción mueve un archivo o carpeta a una ubicación diferente.

<table>
   <col>
   <col>
   <tbody>
         <tr>
            <td>[!UICONTROL Connection]</td>
            <td>Para obtener instrucciones sobre cómo establecer una conexión con la cuenta de FTP, consulte <a href="#Create" class="MCXref xref" >[!UICONTROL Create a connection] en un módulo FTP</a> en este artículo.</td>
         </tr>
         <tr>
            <td>[!UICONTROL Old file path]</td>
            <td>
               <p>Introduzca la ruta de acceso desde la que desea mover el archivo. Ejemplo: <code>/folder1/document.txt</code>.</p>
            </td>
         </tr>
         <tr>
            <td>[!UICONTROL New file path]</td>
            <td>
               <p>Introduzca la ruta de acceso a la que desea mover el archivo. Ejemplo: <code>/folder2/document.txt</code></p>
            </td>
         </tr>
   </tbody>
</table>


#### [!UICONTROL Upload a file]

Carga un archivo en el servidor FTP.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td>Para obtener instrucciones sobre cómo establecer una conexión con la cuenta de FTP, consulte <a href="#creating-the-ftp-connection" class="MCXref xref">Creación de la conexión FTP</a> en este artículo.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Seleccione la carpeta FTP en la que desea copiar el archivo. </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file] </td> 
   <td> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Append to an already existing file]</td> 
   <td> <p>Si esta opción está habilitada y el archivo ya existe en el servidor FTP, el contenido del archivo se anexa al archivo existente. Si esta opción no está activada, el contenido del archivo se sobrescribirá.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Create folders if don't exist] </td> 
   <td> <p>Si esta opción está habilitada y la carpeta introducida en el campo Carpeta no existe en el servidor FTP, el módulo crea la carpeta</p> </td> 
  </tr> 
 </tbody> 
</table>

## Resolución de problemas {#troubleshooting}

Si tiene problemas con la aplicación FTP durante la creación de la conexión o durante la operación de un módulo, intente utilizar uno de los clientes FTP más populares e intente realizar la misma acción (por ejemplo, crear una conexión o enumerar archivos en una carpeta). con el cliente FTP. Si también tiene los mismos problemas con el cliente FTP, el motivo podría ser una configuración incorrecta del servidor FTP.
