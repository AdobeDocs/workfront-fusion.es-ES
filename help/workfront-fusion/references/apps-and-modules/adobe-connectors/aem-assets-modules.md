---
title: Módulos de Adobe Experience Manager Assets
description: Con el conector de Adobe Experience Manager Assets para Adobe Workfront Fusion, puede crear, cargar y actualizar recursos, así como copiar o mover carpetas y recursos.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 361e6c9c-1497-4f47-85bb-503619744968
source-git-commit: d4bdc4005a3b7b22d64adc8ca1d20bcf534ddfd1
workflow-type: tm+mt
source-wordcount: '3734'
ht-degree: 24%

---

# Módulos de Adobe Experience Manager Assets

Con el conector de Adobe Experience Manager Assets para Adobe Workfront Fusion, puede crear, cargar y actualizar recursos, así como copiar o mover carpetas y recursos.

Para ver un vídeo introductorio del conector de Adobe Experience Manager Assets, consulte:

* [Adobe Experience Manager Assets](https://video.tv.adobe.com/v/3427034/){target=_blank}

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
   <td role="rowheader">Licencia de Adobe Workfront Fusion</td> 
   <td>
   <p>Basado en operaciones: no se requiere licencia de Workfront Fusion</p>
   <p>Basado en conectores (heredado): Workfront Fusion para la automatización e integración del trabajo </p>
   </td> 
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

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

* Debe tener una cuenta de Adobe Experience Manager Assets para utilizar estos módulos.
* Debe configurar el flujo de servidor a servidor en la consola de Adobe Developer.

  Para obtener instrucciones sobre cómo configurar el flujo de servidor a servidor en la consola de Adobe Developer, consulte [Generación de tokens de acceso para las API del servidor](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/generating-access-tokens-for-server-side-apis.html#the-server-to-server-flow).
* La cuenta técnica de Adobe Experience Manager debe tener permisos de escritura.

  Para obtener instrucciones sobre cómo añadir permisos de escritura a su cuenta técnica de Adobe Experience Manager, consulte [Credenciales de servicio](https://experienceleague.adobe.com/en/docs/experience-manager-learn/getting-started-with-aem-headless/authentication/service-credentials) en la documentación de Adobe Experience Manager.

## Información de API de Adobe Experience Manager Assets

El conector de Adobe Experience Manager Assets utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.8.61</td> 
  </tr>
 </tbody> 
 </table>

## Conexión de Adobe Experience Manager Assets a Workfront Fusion {#connect-adobe-experience-manager-assets-to-workfront-fusion}

Para crear una conexión para los módulos de Adobe Experience Manager Assets:

1. Haga clic en Agregar junto al cuadro Conexión.

2. Seleccione el tipo de conexión que está creando:

   * **AEM Assets as a Cloud Service**

     Esta configuración requiere información de Adobe Admin Console.

   * **AEM Assets básicos (Adobe Managed Services)**

     Esta configuración requiere un nombre de usuario y una contraseña.

3. Rellene los campos del tipo de conexión que está creando.

   Para el as a Cloud Service de AEM Assets, consulte [Configuración de la conexión para el as a Cloud Service de AEM Assets](#configure-the-connection-for-aem-assets-as-a-cloud-service).

   Para AEM Assets básicos (Adobe Managed Services), consulte [Configuración de la conexión para AEM Assets básicos](#configure-the-connection-for-aemassets-basic-adobe-managed-services).

4. Haga clic en **Continuar** para guardar la conexión y volver al módulo.


### Configuración de la conexión para AEM Assets as a Cloud Service

>[!NOTE]
>
>* La información de estos campos se genera como parte de la configuración del flujo de servidor a servidor en Adobe Developer Console. Puede encontrar estos valores en el archivo JSON de credenciales de servicio generado como parte de esa configuración.
>
>   Para obtener instrucciones sobre cómo configurar el flujo de servidor a servidor en Adobe Developer Console, consulte [Generación de tokens de acceso para las API del servidor](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/generating-access-tokens-for-server-side-apis.html#the-server-to-server-flow).
>
>* La cuenta técnica de Adobe Experience Manager debe tener permisos de escritura.
>
>   Para obtener instrucciones sobre cómo añadir permisos de escritura a su cuenta técnica de Adobe Experience Manager, consulte [Credenciales de servicio](https://experienceleague.adobe.com/en/docs/experience-manager-learn/getting-started-with-aem-headless/authentication/service-credentials) en la documentación de Adobe Experience Manager.


<table style="table-layout:auto"> 
          <col/>
          <col/>
          <tbody>
              <tr>
                  <td role="rowheader">Nombre de conexión</td>
                  <td>
                      <p>Introduzca un nombre para esta conexión.</p>
                  </td>
              </tr>
              <tr>
                  <td role="rowheader">URL de instancia sin barra diagonal</td>
                  <td>Introduzca la URL de la instancia de Adobe Experience Manager. No incluya una barra diagonal <code>/</code> al final de la URL.</td>
              </tr>
              <tr>
                  <td role="rowheader">Opciones de relleno de detalles de cuenta</td>
                  <td>Seleccione si desea proporcionar un archivo JSON que describa los detalles de su cuenta o si desea introducir los detalles manualmente.</td>
              </tr>
              <tr>
                  <td role="rowheader">Detalles técnicos de la cuenta en formato JSON</td>
                  <td>Si proporciona JSON, introduzca o pegue el JSON que describe los detalles de la cuenta.</td>
              </tr>
              <tr>
                  <td role="rowheader">Id. de cliente</td>
                  <td>Si introduce los detalles manualmente, introduzca el ID de cliente generado en la configuración de servidor a servidor.</td>
              </tr>
              <tr>
                  <td role="rowheader">Secreto de cliente</td>
                  <td>Si introduce los detalles manualmente, introduzca el Secreto de cliente generado en la configuración de servidor a servidor.</td>
              </tr>
              <tr>
                  <td role="rowheader">ID de cuenta técnica</td>
                  <td>Si introduce los detalles manualmente, introduzca el ID de la cuenta técnica. Este es el campo "id" en el archivo JSON de credenciales del cliente.</td>
              </tr>
              <tr>
                  <td role="rowheader">ID de organización</td>
                  <td class="">Si introduce los detalles manualmente, introduzca el ID de su organización. Este es el campo "org" en el archivo JSON de credenciales del cliente.</td>
              </tr>
              <tr>
                  <td role="rowheader">Ámbitos de Meta</td>
                  <td>Introduzca los ámbitos de Meta generados en la configuración servidor a servidor.</td>
              </tr>
              <tr>
                  <td role="rowheader">Clave privada</td>
                  <td>Introduzca la clave privada generada durante la configuración de servidor a servidor. Para extraer la clave privada, haga clic en Extract e introduzca el archivo que desea extraer y la contraseña del archivo.</td>
              </tr>
              <tr>
                  <td role="rowheader">URL de autenticación</td>
                  <td>Introduzca la URL de autenticación de esta cuenta.</td>
              </tr>
          </tbody>
      </table>


### Configuración de la conexión para AEM Assets Basic (Adobe Managed Services)

<table style="table-layout:auto"> 
        <col/>
        <col />
        <tbody>
            <tr>
                <td role="rowheader">Nombre de conexión</td>
                <td>
                    <p>Introduzca un nombre para esta conexión.</p>
                </td>
            </tr>
            <tr>
                <td role="rowheader">URL de instancia sin barra diagonal</td>
                <td>Introduzca la URL de la instancia de Adobe Experience Manager. No incluya una barra diagonal <code>/</code> al final de la URL.</td>
            </tr>
            <tr>
                <td role="rowheader">Nombre de usuario</td>
                <td>Introduzca el nombre de usuario de la cuenta de AEM Assets que utiliza esta conexión.</td>
            </tr>
            <tr>
                <td role="rowheader">Contraseña</td>
                <td>Escriba la contraseña de la cuenta de AEM Assets que utiliza esta conexión.</td>
            </tr>
        </tbody>
    </table>


## Módulos Adobe Experience Manager Assets y sus campos

Al configurar los módulos de Adobe Experience Manager Assets, Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden mostrarse campos de Adobe Experience Manager Assets adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Operaciones de archivos](#files-operations)
* [Otro](#other)
* [Assets (API de autor)](#assets-author-api)
* [Eventos (API de autor)](#events-author-api)
* [Metadatos (API de autor)](#metadata-author-api)
* [Importación (API de autor)](#import-author-api)
* [Relaciones (API de autor)](#relations-author-api)
* [Carpetas (API de carpetas)](#folders-folders-api)

### Operaciones de archivos

* [Carga completa](#complete-upload)
* [Obtener almacenamiento con firma previa](#get-presigned-storage)
* [Iniciar carga](#initiate-upload)
* [Cargar un recurso](#upload-an-asset)

#### Carga completa

Este módulo de acción completa una carga iniciada, una vez cargadas todas las partes del archivo.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre del archivo</td> 
   <td> <p>Introduzca o asigne un nombre para el archivo cargado.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Cargar token</td> 
   <td>Introduzca o asigne el token de carga para el binario, tal como lo proporciona el inicio.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo MIME</td> 
   <td>Introduzca o asigne el tipo MIME del archivo completado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">URI completo</td> 
   <td>Introduzca o asigne el URI completo del archivo.</td> 
  </tr> 
 </tbody> 
</table>


#### Obtener almacenamiento con firma previa

Este módulo de acción crea una URL prefirmada temporal para cargar o descargar archivos de forma segura desde AEM sin requerir credenciales directas.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de búsqueda</td> 
   <td> <p>Seleccione si desea buscar el recurso por su ruta o su ID.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Recurso</td> 
   <td>Seleccione la ruta al recurso.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">UDID</td> 
   <td>Introduzca o asigne el UDID del recurso.</td> 
  </tr> 
 </tbody> 
</table>

#### Iniciar carga

Este módulo de acción inicia una carga.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Destino</td> 
   <td> <p>Seleccione la carpeta en la que desea cargar un archivo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre del archivo</td> 
   <td> <p>Introduzca o asigne un nombre para el archivo cargado</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tamaño máximo de archivo</td> 
   <td>Introduzca o asigne el tamaño, en bytes, del archivo cargado.</td> 
  </tr> 
 </tbody> 
</table>


#### Cargar un recurso

Este módulo de acción carga un recurso en su cuenta de Adobe Experience Manager Assets.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Destino</td> 
   <td> <p>Seleccione la carpeta en la que desea cargar un recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">archivo de Source</td> 
   <td>Introduzca o asigne el nombre y los datos del archivo de origen.</td> 
  </tr> 
 </tbody> 
</table>

### Otro


* [Copiar una carpeta o un recurso](#copy-a-folder-or-asset)
* [Crear un registro](#create-a-record)
* [Eliminar una carpeta, un recurso o una representación](#delete-a-folder-asset-or-rendition)
* [Obtener una lista de carpetas](#get-a-folder-listing)
* [Realizar una llamada de API personalizada](#make-a-custom-api-call)
* [Mover una carpeta o un recurso](#move-a-folder-or-asset)
* [Actualizar un registro](#update-a-record)



#### Copiar una carpeta o un recurso

Este módulo de acción copia una carpeta o un recurso en otra ubicación de su cuenta de Adobe Experience Manager Assets.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de registro</td> 
   <td> <p>Seleccione si desea copiar una carpeta o un recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Carpeta/recurso</td> 
   <td>Seleccione o asigne la carpeta o el recurso que desee copiar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Ruta de destino</td> 
   <td>Seleccione o asigne la ruta a la ubicación de la nueva carpeta o recurso.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre de la carpeta/recurso copiado</td> 
   <td>Introduzca un nombre para la nueva carpeta o recurso. El nombre de la carpeta que se muestra en Adobe Experience Manager Assets es el mismo que el nombre original. El nombre introducido aquí aparece en la URL de la nueva carpeta o recurso.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Copiar elementos secundarios</td> 
   <td>Si copia una carpeta, habilite esta opción para copiar subcarpetas o recursos dentro de la carpeta.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Sobrescribir</td> 
   <td>Habilite esta opción para sobrescribir cualquier carpeta o recurso en la ubicación de destino que tenga el mismo nombre que la carpeta o el recurso que se está copiando.</td> 
  </tr> 
 </tbody> 
</table>



#### Crear un registro

Este módulo de acción crea una carpeta o un comentario de recurso.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de objeto</td> 
   <td> <p>Seleccione si desea crear una carpeta o un comentario en un recurso.</p> 
    <ul> 
     <li> <p>Carpeta</p> <p>Rellene los campos siguientes:</p> 
      <ul> 
       <li> <p>Nombre</p> <p>Introduzca un nombre para la carpeta. Este nombre aparecerá en la ruta de archivo, por lo que no debe incluir espacios ni otros caracteres. </p> </li> 
       <li> <p>Título</p> <p>Introduzca un título para la carpeta, el cual puede mostrarse en lugar del nombre.</p> </li> 
      </ul> </li> 
     <li> <p>Comentario de recurso</p> <p>Rellene los campos siguientes:</p> 
      <ul> 
       <li> <p>Selección de recursos</p> <p>Seleccione o asigne el ID del recurso al que desea añadir un comentario.</p> </li> 
       <li> <p>Comentario</p> <p>Introduzca el texto del comentario.</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### Eliminar una carpeta, un recurso o una representación

Este módulo de acción elimina una carpeta, un recurso o una representación.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de registro</td> 
   <td> <p>Seleccione si desea eliminar una carpeta, un recurso o una representación.</p> 
    <ul> 
     <li> <p>Carpeta</p> <p>Seleccione la carpeta que desea eliminar seleccionando las carpetas en su ruta.</p> </li> 
     <li> <p>Recurso</p> <p>Seleccione el recurso seleccionando las carpetas de su ruta y, a continuación, el recurso que desea eliminar.</p> </li> 
     <li> <p>Representación</p> <p>Seleccione la representación seleccionando las carpetas en su ruta.</p> <p>Introduzca o asigne el nombre de la representación.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### Obtener una lista de carpetas

Este módulo de acción recupera una representación de una carpeta existente y de sus entidades secundarias (carpetas o recursos).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Carpeta</td> 
   <td>Seleccione o asigne la carpeta que desea recuperar. Para añadir subcarpetas a la ruta, haga clic en el icono de signo más y seleccione la subcarpeta.</td> 
  </tr> 
 </tbody> 
</table>

#### Realizar una llamada de API personalizada

Este módulo de acción realiza una llamada de API personalizada a la API de Adobe Experience Manager Assets.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>URL</p> </td> 
   <td> <p>Introduzca una ruta relativa a la URL base de Adobe Experience Manager.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Método</p> </td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Encabezados</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p> Workfront Fusion añade encabezados de autorización automáticamente.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Cadena de consulta</td> 
   <td> <p>Introduzca la cadena de consulta de la solicitud. Para cada par clave/valor, haga clic en <b>Agregar elemento</b> e introduzca la clave y el valor.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Cuerpo</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### Mover una carpeta o un recurso

Este módulo de acción mueve el recurso o la carpeta en la ruta determinada a una nueva ubicación.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de registro</td> 
   <td> <p>Seleccione si desea mover una carpeta o un recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Carpeta/recurso</td> 
   <td>Seleccione o asigne la carpeta o el recurso que desee mover.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Ruta de destino</td> 
   <td>Seleccione o asigne la ruta a la ubicación a la que desee mover la carpeta o el recurso.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nombre de la carpeta/recurso movido</td> 
   <td>Introduzca un nombre nuevo para la carpeta o el recurso movido. El nombre de la carpeta que se muestra en Adobe Experience Manager Assets es el mismo que el nombre original. El nombre introducido aquí aparece en la URL de la carpeta o el recurso movido.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Sobrescribir</td> 
   <td>Active esta opción para sobrescribir cualquier carpeta o recurso en la ubicación de destino que tenga el mismo nombre que la carpeta o el recurso que se está moviendo.</td> 
  </tr> 
 </tbody> 
</table>

#### Actualizar un registro

Este módulo de acción actualiza un registro existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipo de registro</td> 
   <td> <p>Seleccione si desea eliminar los metadatos del recurso o una representación del recurso.</p> 
    <ul> 
     <li> <p>Metadatos de recursos</p> 
      <ul> 
       <li> <p>Seleccione el recurso cuyos metadatos desea actualizar.</p> </li> 
       <li> <p>Introduzca el nuevo título del recurso.</p> </li> 
      </ul> </li> 
     <li> <p>Representación de recursos</p> 
      <ul> 
       <li> <p>Seleccione el recurso para el que desea actualizar la representación.</p> </li> 
       <li> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Assets (API de autor)

* [Eliminar recurso](#delete-asset)
* [Obtener estado del trabajo](#get-job-status)

#### Eliminar recurso

Este módulo de acción elimina un solo recurso por su ID.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID del recurso</td> 
   <td> <p>Introduzca o asigne el ID del recurso que desea eliminar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Forzar</td> 
   <td>Active esta opción para forzar la eliminación del recurso, incluso si se hace referencia a él.</td> 
  </tr> 
 </tbody> 
</table>

#### Obtener estado del trabajo

Este módulo de acción obtiene el estado actual de un trabajo asincrónico.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de trabajo</td> 
   <td> <p>Introduzca o asigne el ID del trabajo para el que desea obtener el estado.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Eventos (API de autor)

#### Ver eventos

Este módulo de déclencheur inicia un escenario cuando se produce un evento en los AEM Assets.

El módulo contiene un solo campo: Webhook. Seleccione un webhook existente para usar en estos eventos o cree uno nuevo.

Para crear un nuevo webhook:

1. Haga clic en **Agregar** junto al campo Webhook.
1. Rellene los campos siguientes:

   <table>
     <col/>
     <col/>
     <tbody>
       <tr>
         <td role="rowheader">Nombre del webhook</td>
        <td>Escriba un nombre para este webhook.</td>
       </tr>
       <tr>
         <td role="rowheader">Conexión</td>
        <td>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</td>
       </tr>
     </tbody>
   </table>

1. Haga clic en Guardar para guardar el webhook y volver al módulo.


### Metadatos (API de autor)

* [Obtener metadatos de recursos](#get-asset-metadata)
* [Actualizar metadatos del recurso](#update-asset-metadata)

#### Obtener metadatos de recursos

Este módulo de acción recupera metadatos sobre el recurso especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID del recurso</td> 
   <td> <p>Introduzca o asigne el ID del recurso para el que desea obtener los metadatos.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Actualizar metadatos del recurso

Este módulo de acción actualiza los metadatos del recurso especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID del recurso</td> 
   <td> <p>Introduzca o asigne el ID del recurso para el que desea actualizar los metadatos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Actualizaciones</td> 
   <td> <p>Para cada elemento de metadatos que desee actualizar, haga clic en <b>Agregar elemento</b> y seleccione la operación. Otros campos del cuadro Agregar elemento dependen de la operación seleccionada.</p> </td> 
  </tr> 
 </tbody> 
</table>


### Importación (API de autor)

* [Obtener resultados del trabajo de importación](#get-import-job-results)
* [Obtener estado del trabajo de importación](#get-import-job-status)
* [Cargar un recurso desde una dirección URL](#upload-an-asset-from-a-url)

#### Obtener resultados del trabajo de importación

Este módulo de acción recupera los resultados del trabajo de importación especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Importar ID de trabajo</td> 
   <td> <p>Introduzca o asigne el ID del trabajo para el que desea recuperar los resultados.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Obtener estado del trabajo de importación

Este módulo de acción recupera el estado del trabajo de importación especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Importar ID de trabajo</td> 
   <td> <p>Introduzca o asigne el ID del trabajo del que desea recuperar el estado.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Cargar un recurso desde una dirección URL

Este módulo de acción carga un nuevo recurso mediante la importación de archivos desde las direcciones URL especificadas.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Título</td> 
   <td> <p>Escriba o asigne un título para el recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Descripción</td> 
   <td> <p>Introduzca o asigne una descripción para el recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Asunto</td> 
   <td> <p>Introduzca o asigne un asunto para el recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Creador</td> 
   <td> <p>Introduzca o asigne el creador del recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Fecha de caducidad</td> 
   <td> <p>Introduzca o asigne la fecha de caducidad del recurso.</p><p>Para obtener una lista de los formatos de fecha y hora admitidos, consulte <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Coerción de tipos</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Metadatos personalizados</td> 
   <td> <p>Para cada elemento de metadatos personalizados que desee agregar al recurso, haga clic en <b>Agregar elemento</b> e introduzca el nombre y el valor de los metadatos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Ruta de carpeta o ID</td> 
   <td> <p>Seleccione si desea especificar la carpeta de destino por su ruta o ID y, a continuación, seleccione la ruta o introduzca el ID.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Archivos para importar</td> 
   <td> <p>Para cada archivo que desee importar, haga clic en <b>Agregar elemento&lt;/&gt; y rellene los detalles del archivo. <code>Title</code> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"></td> 
   <td> <p></p> </td> 
  </tr> 
 </tbody> 
</table>

### Relaciones (API de autor)

* [Crear relaciones de recursos](#create-asset-relations)
* [Eliminar relación de recursos](#create-asset-relations)
* [Obtener tipos de relación de recursos](#get-asset-relation-types)
* [Obtener relaciones de recursos](#get-asset-relations)

#### Crear relaciones de recursos

Este módulo de acción crea nuevas relaciones de recurso para el recurso seleccionado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID del recurso</td> 
   <td> <p>Introduzca o asigne el activo de ID con el que desea relacionar otros activos.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Recursos relacionados</td> 
   <td> <p>Para cada recurso que desee relacionar con el recurso seleccionado, haga clic en <b>Agregar elemento</b> e introduzca o asigne el ID del recurso y el tipo de relación.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Eliminar relación de recursos

Este módulo de acción elimina una relación de recurso para un recurso.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID del recurso</td> 
   <td> <p>Introduzca o asigne el activo de ID desde el que desea eliminar una relación.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Recursos relacionados</td> 
   <td> <p>Introduzca o asigne el tipo de relación que desea eliminar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Proporcione un ID específico del recurso relacionado que se va a eliminar</td> 
   <td> <p>Marque esta casilla si desea eliminar una relación específica. Si esta casilla no está activada, se eliminarán todas las relaciones del tipo seleccionado.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de recurso relacionado</td> 
   <td> <p>Si va a eliminar una relación específica, introduzca o asigne el ID de relación que desea eliminar.</p> </td> 
  </tr> 
 </tbody> 
</table>


#### Obtener tipos de relación de recursos

Este módulo enumera los tipos de relación de recursos que existen para el recurso especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID del recurso</td> 
   <td> <p>Introduzca o asigne el recurso de ID para el que desea enumerar los tipos de relación.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Obtener relaciones de recursos

Este módulo enumera las relaciones de recurso para el recurso especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID del recurso</td> 
   <td> <p>Introduzca o asigne el recurso de ID para el que desea enumerar las relaciones.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tipos de relación</td> 
   <td> <p>Introduzca o asigne una lista separada por comas de los tipos de relación para los que desea enumerar las relaciones.</p> </td> 
  </tr> 
 </tbody> 
</table>



### Carpetas (API de carpetas)

* [Creación de carpetas](#create-folders)
* [Eliminar una carpeta por identificador](#delete-a-folder-by-id)
* [Eliminar carpetas por ruta](#delete-folders-by-path)
* [Obtener resultados del trabajo de carpetas](#get-folders-job-results)
* [Obtener estado del trabajo de carpetas](#get-folders-job-status)
* [Enumerar carpetas](#list-folders)

#### Creación de carpetas

Este módulo de acción crea una nueva carpeta en Adobe Experience Manager Assets.



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Carpetas para crear</td> 
   <td> <p>Para cada carpeta que desee crear, haga clic en <b>Agregar elemento</b> e introduzca la siguiente información:</p>
   <ul>
   <li><b>Nueva ubicación de carpeta</b><p>Seleccione la ruta a la ubicación en la que desea crear la nueva carpeta.</p></li>
       <li> <b>Nombre</b> <p>Introduzca un nombre para la carpeta. Este nombre aparecerá en la ruta de archivo, por lo que no debe incluir espacios ni otros caracteres. </p> </li> 
       <li> <b>Título</b> <p>Introduzca un título para la carpeta, el cual puede mostrarse en lugar del nombre.</p> </li> 
   </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### Eliminar una carpeta por identificador

Este módulo de acción elimina la carpeta Adobe Experience Manager Assets con el ID especificado.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Identificador de carpeta</td> 
   <td> Introduzca o asigne el ID de la carpeta que desea eliminar.</td>
  </tr> 
 <tr> 
   <td role="rowheader">Eliminar subcarpetas</td> 
   <td> Active esta opción para eliminar la carpeta y todas sus subcarpetas.</td>
  </tr> 
 <tr> 
   <td role="rowheader">Forzar</td> 
   <td> Active esta opción para forzar la eliminación de las carpetas, incluso si se hace referencia a ella.</td>
  </tr> 
 </tbody> 
</table>

#### Eliminar carpetas por ruta

Este módulo de acción elimina las carpetas de Adobe Experience Manager Assets en las rutas especificadas.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Rutas de carpeta</td> 
   <td>Para cada carpeta que desee eliminar, haga clic en <b>Agregar elemento</b> y seleccione la ruta de la carpeta.</td>
  </tr> 
 <tr> 
   <td role="rowheader">Eliminar subcarpetas</td> 
   <td> Active esta opción para eliminar la carpeta y todas sus subcarpetas.</td>
  </tr> 
 <tr> 
   <td role="rowheader">Forzar</td> 
   <td> Active esta opción para forzar la eliminación del recurso, incluso si se hace referencia a él.</td>
  </tr> 
 </tbody> 
</table>

#### Obtener resultados del trabajo de carpetas

Este módulo recupera los resultados de un trabajo asincrónico creado por la API de carpetas de Adobe Experience Manager Assets.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de trabajo</td> 
   <td> Introduzca o asigne el ID del trabajo para el que desea recuperar los resultados.</td>
  </tr> 
 </tbody> 
</table>

#### Obtener estado del trabajo de carpetas

Este módulo recupera el estado de un trabajo asincrónico creado por la API de carpetas de Adobe Experience Manager Assets.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID de trabajo</td> 
   <td> Introduzca o asigne el ID del trabajo para el que desea recuperar el estado.</td>
  </tr> 
 </tbody> 
</table>


#### Enumerar carpetas

Este módulo enumera las subcarpetas de la carpeta especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Conexión</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de Adobe Experience Manager Assets a Workfront Fusion, consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar Adobe Experience Manager Assets a Workfront Fusion</a> en este artículo.</p> </td> 
   </tr> 
   <tr> 
   <td role="rowheader">Ruta de carpeta o ID</td> 
   <td> <p>Seleccione si desea especificar la carpeta de destino por su ruta o ID y, a continuación, seleccione la ruta o introduzca el ID.</p> </td> 
  </tr> 
 </tbody> 
</table>

<!--
i! I added a lot of modules to the AEM Assets connector and we need new documentation for them. The connector is available in the QA environment. Heres the added modules and a brief description of them, more info about them can be found in the Assets Author Api docs and the Folders Api docs. Im not fully confident that i kept all the best practices for naming things :sweat_smile:, i hope you can take a look at that as well. Let me know if theres anything i can tell about the modules and thanks again in advance!
Author API
Assets
Delete Asset
Deletes an asset when provided an Asset ID, There is a force parameter that when toggled will delete the folder regardless if it's referenced.
Return either nothing if the deletion takes less than a few seconds or a job ID which can be used in another module to track the job of deleting the folder.
Get assets job status
Given an assets job ID will return the state that the job is currently in (PROCESSING, COMPLETED, etc.)
Events
AEM Assets events
The costumer can create a web hook in this module and register it in the Adobe admin console
Metadata
Get asset metadata
Given asset ID returns assets metadata.
Update asset metadata
Given asset ID, there are 6 patch operations that can be done with the metadata. The operations are visible in the module as well as the documentation.
Import
Get import job results
Given Job ID returns it's result.
Get import job status
Given Job ID returns its status.
Upload an asset from url
Takes global metadata which applies to all the assets and local ones which apply individually.In both it is also possible to specify custom metadata.
Also takes the folder path or folder ID to place the assets there and url-s of the assets.
Relations
Create asset relation
Given asset ID and a list of related asset ID as well as the relation types creates those relationships.
Delete asset relations
Given asset ID and relation type deletes all relations of that type. Can also specify a related asset to target only that.
 there is a checkbox that is checked by default and when unchecked reveals a field where the user can specify the related user ID.
Get asset relation types
Given asset ID returns all the relation types that the asset has.
Get asset relations
Given asset ID returns all relations. Can also specify a specific type of relation.
Folders API
Create folders
Given a list of folders with their path, name, title, creates them.
Delete a folder by ID
Given Folder ID deletes the folder. There is also a way to specify if it should delete folders recursively and if it should be forced.
Return either nothing if the deletion takes less than a few seconds or a job ID which can be used in another module to track the job of deleting the folder.
Delete folders by path
Given a list of paths, deletes everything in them. There is also a way to specify if it should delete folders recursively and if it should be forced.
Return either nothing if the deletion takes less than a few seconds or a job ID which can be used in another module to track the job of deleting the folder.
Get folders job results
Given job ID returns its result.
Get folders job status
Given job ID returns its status.
List Folders
List folders under the given folder. In the module you can choose the root folder either by ID or by Path.
-->

