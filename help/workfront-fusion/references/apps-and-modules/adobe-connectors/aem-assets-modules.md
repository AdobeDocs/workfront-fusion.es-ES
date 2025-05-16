---
title: Módulos de Adobe Experience Manager Assets
description: Con el  [!DNL Adobe Experience Manager Assets] conector para [!DNL Adobe Workfront Fusion], puede crear, cargar y actualizar recursos, así como copiar o mover carpetas y recursos.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 361e6c9c-1497-4f47-85bb-503619744968
source-git-commit: 40470e5d2183f690ad65f5e1170f78c37dee8603
workflow-type: tm+mt
source-wordcount: '1727'
ht-degree: 80%

---

# Módulos de [!DNL Adobe Experience Manager Assets]

Con el conector [!DNL Adobe Experience Manager Assets] para [!DNL Adobe Workfront Fusion], puede crear, cargar y actualizar recursos, así como copiar o mover carpetas y recursos.

Para ver un vídeo introductorio del conector de Adobe Experience Manager Assets, consulte:

* [Adobe Experience Manager Assets](https://video.tv.adobe.com/v/3427034/){target=_blank}

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
   <p>Heredado: Workfront Fusion para automatización e integración </p>
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

* Debe tener una cuenta de [!DNL Adobe Experience Manager Assets] para utilizar estos módulos.
* Debe configurar el flujo de [!UICONTROL servidor a servidor] en la [!DNL Adobe Developer console].

  Para obtener instrucciones sobre la configuración del flujo de [!UICONTROL servidor a servidor] en la [!DNL Adobe Developer console], consulte [Generación de tokens de acceso para las API del lado del servidor](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/generating-access-tokens-for-server-side-apis.html#the-server-to-server-flow).
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

## Conectar [!DNL Adobe Experience Manager Assets] a [!DNL Workfront Fusion] {#connect-adobe-experience-manager-assets-to-workfront-fusion}

Para crear una conexión para los módulos de [!DNL Adobe Experience Manager Assets]:

1. Haga clic en [!UICONTROL Añadir] junto al cuadro [!UICONTROL Conexión].

2. Seleccione el tipo de conexión que está creando:

   * **[!DNL AEM Assets as a Cloud Service]**

     Esta configuración requiere información de [!DNL Adobe Admin Console].

   * **[!DNL AEM Assets Basic]([!DNL Adobe Managed Services])**

     Esta configuración requiere un nombre de usuario y una contraseña.

3. Rellene los campos del tipo de conexión que está creando.

   Para [!DNL AEM Assets as a Cloud Service], consulte [Configurar la conexión para [!DNL AEM Assets as a Cloud Service]](#configure-the-connection-for-aem-assets-as-a-cloud-service).

   Para [!UICONTROL AEM Assets Basic] ([!DNL Adobe Managed Services]), consulte [Configuración de la conexión para [!UICONTROL AEM Assets Basic]](#configure-the-connection-for-aemassets-basic-adobe-managed-services).

4. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.


### Configurar la conexión para [!DNL AEM Assets as a Cloud Service]

>[!NOTE]
>
>* La información de estos campos se genera como parte del flujo de configuración de [!UICONTROL servidor a servidor] en la [!DNL Adobe Developer Console]. Puede encontrar estos valores en el archivo JSON de credenciales de servicio generado como parte de esa configuración.
>
>   Para obtener instrucciones sobre cómo configurar el flujo de [!UICONTROL servidor a servidor] en la [!UICONTROL Adobe Developer Console], consulte [Generación de tokens de acceso para las API del lado del servidor](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/generating-access-tokens-for-server-side-apis.html#the-server-to-server-flow).
>
>* La cuenta técnica de Adobe Experience Manager debe tener permisos de escritura.
>
>   Para obtener instrucciones sobre cómo añadir permisos de escritura a su cuenta técnica de Adobe Experience Manager, consulte [Credenciales de servicio](https://experienceleague.adobe.com/en/docs/experience-manager-learn/getting-started-with-aem-headless/authentication/service-credentials) en la documentación de Adobe Experience Manager.


<table style="table-layout:auto"> 
          <col/>
          <col/>
          <tbody>
              <tr>
                  <td role="rowheader">[!UICONTROL Connection name]</td>
                  <td>
                      <p>Introduzca un nombre para esta conexión.</p>
                  </td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Instance URL without a trailing slash]</td>
                  <td>Introduzca la URL de la instancia [!DNL Adobe Experience Manager]. No incluya una barra diagonal <code>/</code> al final de la URL.</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Detalles de cuenta, opciones de relleno]</td>
                  <td>Seleccione si desea proporcionar un archivo JSON que describa los detalles de su cuenta o si desea introducir los detalles manualmente.</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Detalles técnicos de la cuenta en formato JSON]</td>
                  <td>Si proporciona JSON, introduzca o pegue el JSON que describe los detalles de la cuenta.</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Client ID]</td>
                  <td>Si introduce los detalles manualmente, introduzca el ID de cliente generado en la configuración de [!UICONTROL Servidor a servidor].</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Client Secret]</td>
                  <td>Si introduce los detalles manualmente, introduzca el Secreto de cliente generado en la configuración de [!UICONTROL Servidor a servidor].</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Technical account ID]</td>
                  <td>Si introduce los detalles manualmente, introduzca el ID de la cuenta técnica. Este es el campo "[!UICONTROL id]" en el archivo JSON de credenciales del cliente.</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Org ID]</td>
                  <td class="">Si introduce los detalles manualmente, introduzca el ID de su organización. Este es el campo "[!UICONTROL org]" en el archivo JSON de credenciales del cliente.</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Meta Scopes]</td>
                  <td>Introduzca los meta ámbitos generados en la configuración [!UICONTROL Server-to-server].</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Private key]</td>
                  <td>Introduzca la clave privada generada durante la instalación de [!UICONTROL Server-to-server]. Para extraer la clave privada, haga clic en [!UICONTROL Extract] y, a continuación, introduzca el archivo que desea extraer y la contraseña del archivo.</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Authentication URL]</td>
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
                <td role="rowheader">[!UICONTROL Connection name]</td>
                <td>
                    <p>Introduzca un nombre para esta conexión.</p>
                </td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL Instance URL without a trailing slash]</td>
                <td>Introduzca la URL de la instancia [!DNL Adobe Experience Manager]. No incluya una barra diagonal <code>/</code> al final de la URL.</td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL Username]</td>
                <td>Introduzca el nombre de usuario de la cuenta [!DNL AEM Assets] que utiliza esta conexión.</td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL Password]</td>
                <td>Introduzca la contraseña de la cuenta [!DNL AEM Assets] que utiliza esta conexión.</td>
            </tr>
        </tbody>
    </table>


## Módulos de [!DNL Adobe Experience Manager Assets] y sus campos

Al configurar módulos de [!DNL Adobe Experience Manager Essentials], [!DNL Workfront Fusion] muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse [!DNL Adobe Experience Manager Essentials] campos adicionales, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Copiar una carpeta o un recurso](#copy-a-folder-or-asset)
* [Crear un registro](#create-a-record)
* [Eliminar una carpeta, un recurso o una representación](#delete-a-folder-asset-or-rendition)
* [Obtener una lista de carpetas](#get-a-folder-listing)
* [Realizar una llamada de API personalizada](#make-a-custom-api-call)
* [Mover una carpeta o un recurso](#move-a-folder-or-asset)
* [Actualizar un registro](#update-a-record)
* [Cargar un recurso](#upload-an-asset)

### [!UICONTROL Copiar una carpeta o un recurso]

Este módulo de acción copia una carpeta o un recurso en otra ubicación de su cuenta de Adobe Experience Manager Assets.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Adobe Experience Manager Assets] a [!DNL Workfront Fusion], consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Adobe Experience Manager Assets] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>Seleccione si desea copiar una carpeta o un recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder] / [!UICONTROL Asset]</td> 
   <td>Seleccione o asigne la carpeta o el recurso que desee copiar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination path]</td> 
   <td>Seleccione o asigne la ruta a la ubicación de la nueva carpeta o recurso.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name of copied folder] / [!UICONTROL asset]</td> 
   <td>Introduzca un nombre para la nueva carpeta o recurso. El nombre de carpeta que se muestra en [!DNL Adobe Experience Manager Assets] es el mismo que el nombre original. El nombre introducido aquí aparece en la URL de la nueva carpeta o recurso.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy children]</td> 
   <td>Si copia una carpeta, habilite esta opción para copiar subcarpetas o recursos dentro de la carpeta.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Overwrite]</td> 
   <td>Active esta opción para sobrescribir cualquier carpeta o recurso en la ubicación de destino que tenga el mismo nombre que la carpeta o el recurso que se está copiando.</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Crear un registro]

Este módulo de acción crea una carpeta o un comentario de recurso.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Adobe Experience Manager Assets] a [!DNL Workfront Fusion], consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Adobe Experience Manager Assets] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object type]</td> 
   <td> <p>Seleccione si desea crear una carpeta o un comentario en un recurso.</p> 
    <ul> 
     <li> <p>[!UICONTROL Folder]</p> <p>Rellene los campos siguientes:</p> 
      <ul> 
       <li> <p>[!UICONTROL Name]</p> <p>Introduzca un nombre para la carpeta. Este nombre aparecerá en la ruta de archivo, por lo que no debe incluir espacios ni otros caracteres. </p> </li> 
       <li> <p>[!UICONTROL Title]</p> <p>Introduzca un título para la carpeta, el cual puede mostrarse en lugar del nombre.</p> </li> 
      </ul> </li> 
     <li> <p>[!UICONTROL Asset comment]</p> <p>Rellene los campos siguientes:</p> 
      <ul> 
       <li> <p>[!UICONTROL Asset selection]</p> <p>Seleccione o asigne el ID del recurso al que desea añadir un comentario.</p> </li> 
       <li> <p>[!UICONTROL Comment]</p> <p>Introduzca el texto del comentario.</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Eliminar una carpeta, recurso o representación]

Este módulo de acción elimina una carpeta, un recurso o una representación.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Adobe Experience Manager Assets] a [!DNL Workfront Fusion], consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Adobe Experience Manager Assets] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>Seleccione si desea eliminar una carpeta, un recurso o una representación.</p> 
    <ul> 
     <li> <p>[!UICONTROL Folder]</p> <p>Seleccione la carpeta que desea eliminar seleccionando las carpetas en su ruta.</p> </li> 
     <li> <p>[!UICONTROL Asset] </p> <p>Seleccione el recurso seleccionando las carpetas de su ruta y, a continuación, el recurso que desea eliminar.</p> </li> 
     <li> <p>[!UICONTROL Rendition]</p> <p>Seleccione la representación seleccionando las carpetas en su ruta.</p> <p>Introduzca o asigne el nombre de la representación.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Obtener un listado de carpetas]

Este módulo de acción recupera una representación de una carpeta existente y de sus entidades secundarias (carpetas o recursos).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Adobe Experience Manager Assets] a [!DNL Workfront Fusion], consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Adobe Experience Manager Assets] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>Seleccione o asigne la carpeta que desea recuperar. Para añadir subcarpetas a la ruta, haga clic en el icono de signo más y seleccione la subcarpeta.</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Realizar una llamada de API personalizada]

Este módulo de acción realiza una llamada de API personalizada a la API [!DNL Adobe Experience Manager Assets].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Adobe Experience Manager Assets] a [!DNL Workfront Fusion], consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Adobe Experience Manager Assets] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>Introduzca una ruta relativa a la URL base [!DNL Adobe Experience Manager].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] añade encabezados de autorización automáticamente.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String] </td> 
   <td> <p>Introduzca la cadena de consulta de la solicitud. Para cada par clave/valor, haga clic en <b>[!UICONTROL Add item]</b> e introduzca el [!UICONTROL Key] y [!UICONTROL Value].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la instrucción condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Mover una carpeta o un recurso]

Este módulo de acción mueve el recurso o la carpeta en la ruta determinada a una nueva ubicación.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Adobe Experience Manager Assets] a [!DNL Workfront Fusion], consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Adobe Experience Manager Assets] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>Seleccione si desea mover una carpeta o un recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder] / [!UICONTROL Asset]</td> 
   <td>Seleccione o asigne la carpeta o el recurso que desee mover.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination path]</td> 
   <td>Seleccione o asigne la ruta a la ubicación a la que desee mover la carpeta o el recurso.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name of moved folder] / [!UICONTROL asset]</td> 
   <td>Introduzca un nombre nuevo para la carpeta o el recurso movido. El nombre de carpeta que se muestra en [!DNL Adobe Experience Manager Assets] es el mismo que el nombre original. El nombre introducido aquí aparece en la URL de la carpeta o el recurso movido.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Overwrite]</td> 
   <td>Active esta opción para sobrescribir cualquier carpeta o recurso en la ubicación de destino que tenga el mismo nombre que la carpeta o el recurso que se está moviendo.</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Actualizar un registro]

Este módulo de acción actualiza un registro existente.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Adobe Experience Manager Assets] a [!DNL Workfront Fusion], consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Adobe Experience Manager Assets] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>Seleccione si desea eliminar los metadatos del recurso o una representación del recurso.</p> 
    <ul> 
     <li> <p>[!UICONTROL Asset metadata]</p> 
      <ul> 
       <li> <p>Seleccione el recurso cuyos metadatos desea actualizar.</p> </li> 
       <li> <p>Introduzca el nuevo título del recurso.</p> </li> 
      </ul> </li> 
     <li> <p>[!UICONTROL Asset rendition]</p> 
      <ul> 
       <li> <p>Seleccione el recurso para el que desea actualizar la representación.</p> </li> 
       <li> <p>Seleccione un archivo de origen de un módulo anterior o asigne el nombre y los datos del archivo de origen.</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Cargar un recurso]

Este módulo de acción carga un recurso en su cuenta de [!DNL Adobe Experience Manager Assets].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Adobe Experience Manager Assets] a [!DNL Workfront Fusion], consulte <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Adobe Experience Manager Assets] a [!DNL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination]</td> 
   <td> <p>Seleccione la carpeta en la que desea cargar un recurso.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>Introduzca o asigne el nombre y los datos del archivo de origen.</td> 
  </tr> 
 </tbody> 
</table>
