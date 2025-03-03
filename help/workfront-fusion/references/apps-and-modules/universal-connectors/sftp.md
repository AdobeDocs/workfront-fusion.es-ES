---
title: Módulos SFTP
description: Los módulos [!DNL Adobe Workfront Fusion SFTP]  permiten supervisar los cambios de archivo en una carpeta o subcarpeta seleccionada, subir nuevos archivos a la carpeta deseada, modificar o eliminar archivos existentes que ya están en una carpeta o cambiar los permisos de archivo.
author: Becky
feature: Workfront Fusion
exl-id: bde3cbda-8a19-4d9f-b970-f56d73a1f8dd
source-git-commit: e1e15985db9683525250d1f9f9276224b2baf0e6
workflow-type: tm+mt
source-wordcount: '1851'
ht-degree: 81%

---

# Módulos SFTP

Los módulos SFTP de [!DNL Adobe Workfront Fusion] le permiten supervisar los cambios de archivo en una carpeta o subcarpeta seleccionada, subir nuevos archivos a la carpeta deseada, modificar o eliminar los archivos existentes que ya están en una carpeta o cambiar los permisos de archivo.

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
   <p>Actual: no se requiere licencia de Workfront Fusion.</p>
   <p>O</p>
   <p>Heredado: Workfront Fusion para la automatización e integración del trabajo </p>
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

## Requisitos previos

Para usar el SFTP con [!DNL Workfront Fusion], es necesario tener una cuenta de SFTP (como el hosting web [!DNL GoDaddy]).

## Conectar SFTP a [!DNL Workfront Fusion] {#connect-sftp-to-workfront-fusion}

Para conectar su cuenta SFTP a [!DNL Workfront Fusion], debe crear una conexión que especifique el host de destino y las credenciales SFTP (nombre de usuario y contraseña o nombre de usuario y clave).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection name]</td> 
   <td> <p> Introduzca el nombre de la conexión SFTP.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Environment]</td>
    <td>Seleccione si desea conectarse a un entorno de producción o de no producción.</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Type]</td>
    <td>Seleccione si le importa conectarse a una cuenta de servicio o a una cuenta personal.</td>
  </tr>
  <tr>
   <td role="rowheader"> <p>[!UICONTROL Host]</p> </td> 
   <td> <p>Introduzca el nombre del host del servidor SFTP al que desea conectarse.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Port] </td> 
   <td> <p>Introduzca el puerto del servidor SFTP. Por ejemplo, 22.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Auth type]</p> </td> 
   <td> <p>Seleccione el método de autorización que desee utilizar para conectarse al servidor SFTP.</p> 
    <ul> 
     <li><strong>[!UICONTROL User name and password]</strong>: introduzca sus credenciales.</li> 
     <li> <p><strong>[!UICONTROL User name and key]</strong>: introduzca su nombre de usuario y la clave privada/certificado</p> <p>Suba la clave privada para utilizar la autorización del lado del cliente o suba el certificado (archivo P12 o PFX) si desea utilizar TLS con el certificado autofirmado. Si utiliza la autorización de certificados del lado del cliente, puede introducir el certificado de CA aquí.</p> <p>[!DNL Workfront Fusion] no conserva ni almacena ningún dato (archivos, contraseñas) que usted proporciona aquí. El archivo y la contraseña solo se utilizan para extraer una clave privada o un certificado.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Key exchange algorithms] </td> 
   <td> <p>Puede introducir un conjunto de algoritmos para el intercambio de claves. El módulo prioriza los algoritmos en función del orden en que se agregaron. Para cada algoritmo que desee agregar, haga clic en <b>Agregar elemento</b> y seleccione el algoritmo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Ciphers] </td> 
   <td> <p>Puede introducir un conjunto de cifras para el intercambio de claves. El módulo prioriza las cifras en función del orden en que se agregaron. Para cada cifrado que desee agregar, haga clic en <b>Agregar elemento</b> y seleccione el cifrado.</p> </td> 
  </tr> 
 </tbody> 
</table>

Después de escribir la información de conexión, haga clic en **[!UICONTROL Continue]** para establecer una conexión.

## Módulos de [!UICONTROL SFTP] y sus campos

Al configurar módulos de [!UICONTROL SFTP], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!UICONTROL SFTP] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Activadores

* [Ver archivos en una carpeta](#watch-files-in-a-folder)
* [Ver subcarpetas en una carpeta](#watch-subfolders-in-a-folder)

#### [!UICONTROL Watch Files in a Folder]

Devuelve archivos con detalles cuando se crea o cambia un archivo en una carpeta especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta SFTP a [!DNL Workfront Fusion], consulte <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Conectar SFTP a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Escriba la carpeta que desee ver. Puede especificar una ruta de acceso absoluta como <code>/home/user/</code>, o bien una ruta de acceso relativa que apunte a una carpeta específica del usuario que ha iniciado sesión, como <code>./.</code></p> </td> 
  </tr> 
  <tr> 
   <td>Tamaño del búfer [B]</td> 
   <td> <p> Introduzca el tamaño del búfer en bytes. El valor define el tamaño de los fragmentos transferidos desde el servidor. Algunos servidores pueden causar problemas o corromper archivos cuando el valor es demasiado alto.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned files]</td> 
   <td> <p> Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Subfolders in a Folder]

Devuelve carpetas con detalles cuando se crea o cambia una carpeta en una carpeta especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta SFTP a [!DNL Workfront Fusion], consulte <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Conectar SFTP a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Introduzca o asigne la carpeta que desee ver. Puede especificar una ruta absoluta como <code>/home/user/</code>. O puede especificar una ruta relativa que señale a una carpeta específica del usuario que ha iniciado sesión, como <code>./.</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned files]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Acciones

* [Crear una carpeta](#create-a-folderr)
* [Eliminación de un archivo](#delete-a-file)
* [Eliminar una carpeta](#delete-a-folder)
* [Obtener un archivo](#get-a-file)
* [Obtener archivos](#get-files)
* [Enumeración del contenido de una carpeta](#list-a-folders-content)
* [Mover un archivo](#move-a-file)
* [Cambiar nombre de archivo](#rename-a-file)
* [Actualizar permisos de archivo](#update-file-permissions)
* [Cargar un archivo](#upload-a-file)

#### [!UICONTROL Create a folder]

Crea una carpeta nueva en la ubicación especificada.

>[!NOTE]
>
>Si la carpeta ya existe, el módulo genera un error. Para continuar el flujo sin interrupciones, adjunte una ruta de controlador de error al módulo para detectar el error y use la directiva [!UICONTROL Resume] para continuar el flujo. Para obtener información acerca de cómo adjuntar una ruta de controlador de error, vea [Control de errores en [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md). Para obtener información acerca de la ruta del controlador de error, vea [Directivas para la gestión de errores en [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/references/errors/directives-for-error-handling.md).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta SFTP a [!DNL Workfront Fusion], consulte <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Conectar SFTP a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Especifique una carpeta existente como la ubicación de almacenamiento para la nueva carpeta. Puede especificar una ruta absoluta como <code>/home/user/file.txt</code>. O puede especificar una ruta relativa que señale a una carpeta específica del usuario que ha iniciado sesión, como <code>./</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder Name]</td> 
   <td> <p> Introduzca el nombre de la carpeta.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Permissions]</p> </td> 
   <td> <p>Establezca los permisos de carpeta deseados. Utilice parámetros chmod. Por ejemplo, <code>777</code> o <code>-rwxrwxrwx</code>.</p> <p>Estos permisos deben coincidir con el patrón <code>/(.?([r-][w-][x-]){3})|[0-7]{3}/.</code></p> <p>Para obtener más información sobre chmod, consulte la <a href="https://ss64.com/bash/chmod.html">documentación de chmod</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a file]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta SFTP a [!DNL Workfront Fusion], consulte <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Conectar SFTP a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File Path]</td> 
   <td> <p> Escriba la ruta de acceso al archivo que desea eliminar. Puede especificar una ruta absoluta como <code>/home/user/file.txt</code>. O puede especificar una ruta relativa que señale a una carpeta específica del usuario que ha iniciado sesión, como <code>./file.txt</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a folder]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta SFTP a [!DNL Workfront Fusion], consulte <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Conectar SFTP a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!DNL Folder Path]</td> 
   <td> <p> Especifique la ruta de acceso a la carpeta que desea eliminar. Puede especificar una ruta absoluta como <code>/home/user/</code>. O puede especificar una ruta relativa que señale a una carpeta específica del usuario que ha iniciado sesión, como <code>./.</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a file]

Este módulo recupera detalles del archivo, incluidos los datos de un archivo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta SFTP a [!DNL Workfront Fusion], consulte <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Conectar SFTP a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Buffer Size [B]]</td> 
   <td> <p> Introduzca el tamaño del búfer en bytes. El valor define el tamaño de los fragmentos transferidos desde el servidor. Algunos servidores pueden causar problemas o corromper archivos cuando el valor es demasiado alto.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File Path] </td> 
   <td> <p>Introduzca la ruta al archivo. Puede especificar una ruta absoluta como <code>/home/user/file.txt</code>. O puede especificar una ruta relativa que señale a una carpeta específica del usuario que ha iniciado sesión, como <code>./file.txt</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get files]

Este módulo devuelve archivos de una carpeta especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta SFTP a [!DNL Workfront Fusion], consulte <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Conectar SFTP a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Buffer Size [B]]</td> 
   <td> <p> Introduzca el tamaño del búfer en bytes. El valor define el tamaño de los fragmentos transferidos desde el servidor. Algunos servidores pueden causar problemas o corromper archivos cuando el valor es demasiado alto.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Escriba o asigne la carpeta que contiene los archivos o carpetas que desea listar. Puede especificar una ruta absoluta como <code>/home/user/</code>. O puede especificar una ruta relativa que señale a una carpeta específica del usuario que ha iniciado sesión, como <code>./.</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search] </td> 
   <td> <p>Introduzca o asigne el término de búsqueda. Por ejemplo, si desea buscar archivos con la extensión .txt, introduzca <code>.txt</code>. También puede introducir o asignar el nombre del archivo que desea buscar.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sort By]</td> 
   <td> <p> Seleccione si desea ordenar los resultados por el nombre del archivo, el tamaño, la fecha del último acceso o la fecha de la última modificación.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sort Order]</td> 
   <td> <p> Seleccione si el resultado debe devolverse en orden ascendente o descendente.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Continue the execution of the route even if the module returns no results]</p> </td> 
   <td>Habilite esta opción para asegurarse de que este módulo no detenga el escenario si no devuelve resultados.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned results]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List a folder's content]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta SFTP a [!DNL Workfront Fusion], consulte <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Conectar SFTP a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Show] </td> 
   <td> <p>Seleccione si desea recuperar archivos, carpetas o ambos.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Escriba o asigne la carpeta que contiene los archivos o carpetas que desea listar. Puede especificar una ruta absoluta como <code>/home/user/</code>. O puede especificar una ruta relativa que señale a una carpeta específica del usuario que ha iniciado sesión, como <code>./.</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search] </td> 
   <td> <p>Introduzca o asigne el término de búsqueda. Por ejemplo, si desea buscar archivos con la extensión .txt, introduzca <code>.txt</code>. También puede introducir o asignar el nombre del archivo que desea buscar.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sort By]</td> 
   <td> <p> Seleccione si desea ordenar los resultados por nombre de archivo, tamaño, fecha de último acceso o fecha de última modificación.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sort Order] </td> 
   <td> <p>Seleccione si el resultado debe devolverse en orden ascendente o descendente.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Continue the execution of the route even if the module returns no results]</p> </td> 
   <td>Habilite esta opción para asegurarse de que este módulo no detenga el escenario si no devuelve resultados.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned results]</td> 
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move a File]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta SFTP a [!DNL Workfront Fusion], consulte <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Conectar SFTP a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File Path]</td> 
   <td> <p> Escriba la ruta de acceso al archivo que desea mover. Puede especificar una ruta absoluta como <code>/home/user/file.txt</code>. O puede especificar una ruta relativa que señale a una carpeta específica del usuario que ha iniciado sesión, como <code>./file.txt</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL New Folder]</td> 
   <td> <p> Introduzca la ruta a la nueva ubicación del archivo. Puede especificar una ruta absoluta como <code>/home/user/</code>. O puede especificar una ruta relativa que señale a una carpeta específica del usuario que ha iniciado sesión, como <code>./.</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Rename a File]

Cambia el nombre de un archivo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta SFTP a [!DNL Workfront Fusion], consulte <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Conectar SFTP a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File Path]</td> 
   <td> <p> Escriba la ruta de acceso al archivo cuyo nombre desea cambiar. Puede especificar una ruta absoluta como <code>/home/user/file.txt</code>. O puede especificar una ruta relativa que señale a una carpeta específica del usuario que ha iniciado sesión, como <code>./file.txt</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL New file name]</td> 
   <td> <p> Introduzca el nuevo nombre del archivo, incluida su extensión.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update file permissions]

Le permite cambiar los permisos del archivo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta SFTP a [!DNL Workfront Fusion], consulte <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Conectar SFTP a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File Path]</td> 
   <td> <p> Escriba la ruta de acceso al archivo que desea mover. Puede especificar una ruta absoluta como <code>/home/user/file.txt</code>. O puede especificar una ruta relativa que señale a una carpeta específica del usuario que ha iniciado sesión, como <code>./file.txt</code>.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Permissions]</p> </td> 
   <td> <p>Establezca los permisos de archivo deseados. Utilice parámetros chmod. Por ejemplo, <code>777</code> o <code>-rwxrwxrwx</code>.</p> <p>Estos permisos deben coincidir con el patrón <code>/(.?([r-][w-][x-]){3})|[0-7]{3}/.</code></p> <p>Para obtener más información sobre chmod, consulte la <a href="https://ss64.com/bash/chmod.html">documentación de chmod</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a File]

Este módulo le permite subir un archivo en el servidor SFTP.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta SFTP a [!DNL Workfront Fusion], consulte <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Conectar SFTP a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Especifique una carpeta existente como ubicación de almacenamiento para el archivo. Puede especificar una ruta absoluta como <code>/home/user/</code>. O puede especificar una ruta relativa que señale a una carpeta específica del usuario que ha iniciado sesión, como <code>./.</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source File]</td> 
   <td> <p> Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Permissions]</p> </td> 
   <td> <p>Establezca los permisos deseados para el archivo o la carpeta. Utilice parámetros chmod. Por ejemplo, <code>777</code> o <code>-rwxrwxrwx</code>.</p> <p>Estos permisos deben coincidir con el patrón <code>/(.?([r-][w-][x-]){3})|[0-7]{3}/.</code></p> <p>Para obtener más información sobre chmod, consulte la <a href="https://ss64.com/bash/chmod.html">documentación de chmod</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>
