---
title: Módulos de Google Slides
description: Los módulos de Google Slides de Adobe Workfront Fusion le permiten crear, actualizar, enumerar o eliminar presentaciones y subir imágenes en presentaciones en su cuenta de diapositivas de Google.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 6f5f97b9-b06a-4336-b349-ee9e2606d4bf
source-git-commit: c9c2957aad4c885a622a80b9f25303517db0c506
workflow-type: tm+mt
source-wordcount: '1552'
ht-degree: 43%

---

# Módulos de [!DNL Google Slides]

Los módulos de [!DNL Adobe Workfront Fusion] [!DNL Google Slides] le permiten crear, actualizar, enumerar o eliminar presentaciones y subir imágenes en presentaciones de su cuenta de [!DNL Google Slides].

Para utilizar [!DNL Google Slides] con [!DNL Workfront Fusion], es necesario disponer de una cuenta de [!DNL Google]. Si todavía no tiene una cuenta de [!DNL Google], puede crearla en la página de ayuda de [!DNL Google] Account.

También necesita [!DNL Google Slides] en su [!DNL Google Drive].

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

Para usar módulos [!DNL Google Slides], debe tener una cuenta de [!DNL Google].

## Información de API de Google Slides

El conector Diapositivas de Google utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL básica</td> 
   <td> https://slides.googleapis.com/v1</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> Versión 1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.5.9</td> 
  </tr>
 </tbody> 
 </table>

## Módulos de [!DNL Google Slides] y sus campos

Al configurar módulos de [!DNL Google Slides], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL Google Slides] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Presentación](#presentation)
* [Otro](#other)

### Presentación

* [[!UICONTROL Add/Delete a Slide]](#adddelete-a-slide)
* [[!UICONTROL Create a Presentation From a Template]](#create-a-presentation-from-a-template)
* [[!UICONTROL Get a Page/Thumbnail]](#get-a-pagethumbnail)
* [[!UICONTROL Get a Presentation]](#get-a-presentation)
* [[!UICONTROL List Presentations]](#list-presentations)
* [[!UICONTROL Refresh a Chart]](#refresh-a-chart)
* [[!UICONTROL Upload an Image To a Presentation]](#upload-an-image-to-a-presentation)
* [[!UICONTROL Watch Presentations]](#watch-presentations)

#### [!UICONTROL Add/Delete a Slide]

Este módulo de acción crea una diapositiva o elimina una diapositiva existente en la presentación especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Slides] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select the method]</td> 
   <td> <p>Elija si desea añadir una diapositiva nueva o eliminar una diapositiva.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Enter a Slide ID]</td> 
   <td> <p>Si va a eliminar una diapositiva, seleccione si desea introducir el ID de diapositiva manualmente o seleccionar la diapositiva de una lista.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Presentation ID]</td> 
   <td> <p>Seleccione la presentación o asigne el ID. de presentación de la presentación para la que desea agregar o eliminar una diapositiva.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Slide Object ID]</td> 
   <td> <p>Si está eliminando una diapositiva y decide introducirla manualmente, introduzca o asigne el ID de la diapositiva. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Predefined layout type]</td> 
   <td> <p> Seleccione el diseño de diapositiva predefinido que desea que utilice la diapositiva añadida. Especifique valores para cualquier campo adicional (como [!UICONTROL Title]).</p> 
    <ul> 
     <li>[!UICONTROL Blank layout, with no placeholders]</li> 
     <li>[!UICONTROL Layout with a caption at the bottom]</li> 
     <li>[!UICONTROL Layout with a title and subtitle]</li> 
     <li>[!UICONTROL Layout with a title and body]</li> 
     <li>[!UICONTROL Layout with a title and two columns]</li> 
     <li>[!UICONTROL Layout with only a title]</li> 
     <li>[!UICONTROL Layout with a section title]</li> 
     <li>[!UICONTROL Layout with a title and subtitle on one side and description on the other]</li> 
     <li>[!UICONTROL Layout with one title and one body, arranged in a single column]</li> 
     <li>[!UICONTROL Layout with a main point]</li> 
     <li>[!DNL Layout with a big number heading]</li> 
    </ul> <p>Este campo está disponible si ha seleccionado añadir una diapositiva.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Content]</td> 
   <td> <p>Introduzca o asigne el contenido de texto de la diapositiva. Los campos están disponibles en función de la plantilla seleccionada.</p> <p>Este campo está disponible si ha seleccionado añadir una diapositiva.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Presentation From a Template]

Este módulo de acción crea una nueva presentación copiando una presentación y reemplazando todas las etiquetas como `{{Name}}`, `{{Email}}` en con los datos proporcionados.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Slides] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Title] </td> 
   <td> <p>Introduzca un nombre para la nueva presentación.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy a Presentation]</td> 
   <td> <p> Seleccione la opción si está copiando una presentación existente:</p> 
    <ul> 
     <li>[!UICONTROL By Mapping]</li> 
     <li>[!UICONTROL By Dropdown]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy of Existing Presentation ID]</td> 
   <td> <p> Introduzca la ruta o el ID de presentación de una presentación existente que desea copiar. Este campo aparece si está creando la presentación [!UICONTROL By Mapping].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive]</td> 
   <td> <p>Seleccione [!DNL Google Drive] donde se encuentran las presentaciones que desea enumerar:</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] Unidad compartida]</li> 
    </ul> <p>Este campo aparece si está creando la presentación [!UICONTROL By Dropdown].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p> Seleccione la presentación o escriba o asigne el ID de presentación de la presentación que desee utilizar como plantilla.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Values] </td> 
   <td> <p>Añada los valores:</p> 
    <ul> 
     <li><strong>[!UICONTROL Tag]</strong>: introduzca la etiqueta que desea reemplazar en la presentación. Por ejemplo: <code>&#123;&#123;Name&#125;&#125;</code></li> 
     <li><strong>[!UICONTROL Replaced Value]</strong>: introduzca el valor con el que se debe reemplazar la etiqueta existente. Por ejemplo, si una cadena <code>&#123;&#123;Name&#125;&#125;</code> en la presentación y el valor reemplazado es Sample, <code>&#123;&#123;Name&#125;&#125;</code> se reemplazará por <code>Sample</code>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New Drive Location]</td> 
   <td> <p>Seleccione [!DNL Google Drive] donde desee almacenar o agregar la nueva presentación:</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] Unidad compartida]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL New Document's Location]</p> </td> 
   <td> <p>Seleccione la carpeta donde desea almacenar o agregar la presentación.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Shared] </td> 
   <td> <p>Seleccione si desea compartir la presentación.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sharing with Other's Email Address]</td> 
   <td> <p> Escriba la dirección de correo electrónico con la que desea compartir la presentación. Si activa la opción Compartido sin introducir un correo electrónico en este campo, la presentación se puede compartir con cualquier persona.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Page/Thumbnail]

Este módulo de acción obtiene la última versión de la página especificada o de la miniatura de una página de la presentación.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Slides] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a Presentation and Page ID]</td> 
   <td> <p> Elija si desea introducir una presentación y un ID de página manualmente, o bien selecciónelos en una lista.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p> Seleccione el ID de presentación que desee recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Page Object ID]</td> 
   <td> <p> Seleccione la diapositiva para la que desea ver los detalles del objeto de la página.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show Page Thumbnail]</td> 
   <td> <p> Seleccione la casilla de verificación si desea ver la información de la miniatura de la página.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Presentation]

Este módulo de acción obtiene la última versión de una presentación especificada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Slides] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive]</td> 
   <td> <p>Seleccione [!DNL Google Drive] donde se encuentran las presentaciones que desea enumerar:</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] Unidad compartida]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p> Seleccione la presentación que desea recuperar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Presentations]

Este módulo recupera una lista de todas las presentaciones en la ubicación determinada.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Slides] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive location]</td> 
   <td> <p>Seleccione [!DNL Google Drive] donde se encuentran las presentaciones que desea enumerar:</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] Unidad compartida]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID]</td> 
   <td> <p>Elija la ubicación de la carpeta de las presentaciones que desea enumerar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de presentaciones que desea que devuelva el módulo durante un ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Refresh a Chart]

Este módulo de acción actualiza los datos del gráfico almacenados en una presentación especificada por el identificador.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Slides] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a Presentation ID]</td> 
   <td> <p> Elija si desea introducir un ID de presentación manualmente o seleccionarlo en una lista.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive]</td> 
   <td> <p>Si selecciona la presentación de una lista, seleccione la [!DNL Google Drive] en la que se encuentran las presentaciones que desea enumerar:</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] Unidad compartida]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p>Seleccione la presentación o escriba o asigne el ID de presentación de la presentación que incluye el gráfico que desea actualizar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Chart Object ID]</td> 
   <td> <p> Si introduce los datos manualmente, introduzca o asigne el ID del gráfico que desea actualizar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload an Image To a Presentation]

Carga una imagen con los datos proporcionados.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Slides] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Presentation]</td> 
   <td> <p>Elija cómo desea seleccionar la presentación en la que está cargando una imagen.</p> 
    <ul> 
     <li>[!UICONTROL By Mapping]</li> 
     <li>[!DNL By Dropdown]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive]</td> 
   <td> <p>Si elige una de las listas desplegables, seleccione la [!DNL Google Drive] en la que se encuentra la presentación a la que desea agregar una imagen:</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] Unidad compartida]</li> 
    </ul>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p> Seleccione el identificador de la presentación en la que está cargando la imagen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select the Method]</td> 
   <td> <p> Seleccione cómo desea reemplazar la imagen.</p>
   <ul>
   <li><p><b>Cargar una imagen reemplazando la etiqueta de texto</b></p><p>En el campo Valores, para cada imagen que desee cargar, haga clic en <b>Agregar elemento</b> e introduzca la etiqueta de la imagen y la dirección URL de la nueva imagen.</p></li>
   <li><p><b>Cargar una imagen reemplazando una imagen</b></p><p>En el campo Valores, para cada imagen que desee cargar, haga clic en <b>Agregar elemento</b> e introduzca el identificador de objeto de la imagen, el método replace y la dirección URL de la nueva imagen.</p></li>
   </ul>
  <p>Nota: Las imágenes deben tener un tamaño inferior a 50 MB, no pueden superar los 25 megapíxeles y deben estar en formato PNG, JPEG o GIF.</p>   </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Presentations]

Este módulo de déclencheur inicia un escenario cuando se crea o actualiza una nueva presentación.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Slides] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch] </td> 
   <td> <p>Seleccione la opción para ver las presentaciones:</p> 
    <ul> 
     <li> <p>[!UICONTROL Created Date]</p> </li> 
     <li> <p>[!UICONTROL Modified Date]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Introduzca o asigne el número máximo de presentaciones que Workfront Fusion debe devolver durante un ciclo de ejecución de escenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Otro

* [[!UICONTROL Insert Links in a Presentation]](#insert-links-in-a-presentation)
* [[!UICONTROL Make an API Call]](#make-an-api-call)

#### [!UICONTROL Insert Links in a Presentation]

Este módulo permite hacer clic en todos los vínculos de una presentación o inserta un vínculo en todos los textos de entrada coincidentes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Slides] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Presentation]</td> 
   <td> <p>Elija cómo desea seleccionar la presentación en la que está cargando una imagen.</p> 
    <ul> 
     <li>[!UICONTROL By Mapping]</li> 
     <li>[!UICONTROL By Dropdown]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive]</td> 
   <td> <p>Seleccione [!DNL Google Drive] donde se encuentran las presentaciones que desea enumerar:</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] Unidad compartida]</li> 
    </ul> <p>Este campo aparece si está creando la presentación [!UICONTROL By Dropdown].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p>Elija la ubicación de la carpeta de las presentaciones que desea enumerar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select]</td> 
   <td> <p>Seleccione si desea que se pueda hacer clic en todos los vínculos de una presentación o si desea insertar un vínculo en todos los textos de entrada coincidentes.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text Inputs]</td> 
   <td>Si va a insertar un vínculo, para cada elemento de texto para el que desee agregar un vínculo, haga clic en <b>Agregar elemento</b> e introduzca el texto y el vínculo asociado. Cada vez que el elemento aparece en la presentación, se vincula automáticamente al sitio especificado.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Make an API Call]

Realiza una llamada de API autorizada arbitraria.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Para obtener instrucciones acerca de cómo conectar su cuenta de [!DNL Google Slides] a [!DNL Workfront Fusion], vea <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión con [!DNL Adobe Workfront Fusion]: instrucciones básicas</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> <p>Escriba una ruta relativa a <code>https://developers.google.com/slides/</code>. Por ejemplo, Presentación.</p> <p>Para obtener la lista de puntos finales disponibles, consulte la <a href="https://developers.google.com/slides/reference/rest">[!DNL Google Slides] Documentación de la API </a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, vea <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Métodos de solicitud HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Introduzca los encabezados de solicitud deseados. No es necesario añadir encabezados de autorización.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> Introduzca la cadena de consulta de la solicitud.</p> </td> 
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

>[!BEGINSHADEBOX]

**Ejemplo:** con una llamada de API, puede obtener los detalles de presentación del ID de presentación que ha introducido. Puede encontrar el ID de presentación en la dirección URL cuando abra la presentación en [!DNL Google Slides].

![Ejemplo de llamada API](/help/workfront-fusion/references/apps-and-modules/assets/api-call-350x13.png)

La siguiente llamada de API devuelve los detalles de la presentación:

![Detalles de presentación](/help/workfront-fusion/references/apps-and-modules/assets/presentation-details.png)

Las coincidencias de la búsqueda se pueden encontrar en la salida del módulo en [!UICONTROL Bundle] > [!UICONTROL Body] > [!UICONTROL presentationId].

En nuestro ejemplo, se han devuelto los detalles de presentación solicitados:

![Detalles de la presentación](/help/workfront-fusion/references/apps-and-modules/assets/presentation-details-2.png)

>[!ENDSHADEBOX]
