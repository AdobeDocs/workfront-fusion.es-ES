---
title: Módulos de Adobe Photoshop
description: Con los módulos de Adobe Photoshop, puede iniciar un escenario de Adobe Workfront Fusion basado en los eventos de su cuenta de Adobe Photoshop, crear, leer o actualizar acuerdos y otros registros, buscar registros utilizando los criterios definidos y cargar documentos.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 0e41d1af-af69-4f9b-a5b3-479562254084
TQID: https://experienceleague.adobe.com/RratZmko93V0LMxJ6qTy6cNvRqgPNvNgHTflRngE6BI
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: ce3fb5604ac4ed85af1bcc51143732499dfb0404
workflow-type: tm+mt
source-wordcount: 7285
ht-degree: 66%

---

# Módulos de [!DNL Adobe Photoshop]

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!DNL Adobe Photoshop], así como conectarlo a varias aplicaciones y servicios de terceros.

Si necesita instrucciones sobre cómo crear un escenario, vea los artículos en [Crear un escenario: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, consulte los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

>[!IMPORTANT]
>
>Adobe Photoshop ha desaprobado algunos elementos de su API, que Fusion utiliza para realizar acciones en Photoshop.
>
>**Por lo tanto, algunos de los módulos de Photoshop existentes no funcionarán después del 30 de julio de 2026.**
>
>Se recomienda actualizar cualquier escenario que utilice estos módulos a los módulos actualizados lo antes posible.
>
>Para obtener una lista de los módulos afectados, consulte [Actualizaciones de desaprobación de API de Adobe Photoshop](#adobe-photoshop-api-deprecation-updates).
>
>Para obtener información sobre cómo afectan los cambios de API a Workfront Fusion, consulte [Información general sobre las API en Fusion](/help/workfront-fusion/get-started-with-fusion/understand-fusion/api-overview.md).

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Paquete de Adobe Workfront</td> 
   <td> <p>Cualquier paquete del flujo de trabajo de Adobe Workfront y cualquier paquete de integración y automatización de Adobe Workfront</p><p>Workfront Ultimate</p><p>Paquetes Workfront Prime y Select, con una compra adicional de Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencias de Adobe Workfront</td> 
   <td> <p>Estándar</p><p>Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion</td> 
   <td>
   <p>Basado en operaciones: no se requiere licencia de Workfront Fusion</p>
   <p>Basado en conector (heredado): Workfront Fusion for Work Automation and Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Antes de poder usar el conector de [!DNL Adobe Photoshop], debe asegurarse de que se cumplen los siguientes requisitos previos:

* Debe tener una cuenta de [!DNL Adobe Photoshop] activa.
* Debe tener una licencia de Firefly Services.
* Debe tener un ID de cliente y un Secreto de cliente. Puede adquirirlos en Adobe Developer Console.

## Actualizaciones de desaprobación de API de Adobe Photoshop

Adobe Photoshop ha desaprobado algunos elementos de su API, que Fusion utiliza para realizar acciones en Photoshop.

**Por lo tanto, algunos de los módulos de Photoshop existentes no funcionarán después del 30 de julio de 2026.**

Esta tabla indica qué módulos se han visto afectados por esta obsolescencia y a qué módulo debe actualizar.

| Módulo heredado obsoleto | Actualizar al nuevo módulo |
|---|---|
| Aplicar ediciones de PSD | Crear o editar un compuesto |
| Convertir formato de imagen | Crear o editar un compuesto |
| Crear un compuesto | Crear o editar un compuesto |
| Crear un nuevo PSD | Crear o editar un compuesto |
| Crear representaciones | Crear o editar un compuesto |
| Editar capas de texto | Ejecutar acciones, scripts y transformaciones de Photoshop |
| Editar capas de texto 2 | Ejecutar acciones, scripts y transformaciones de Photoshop |
| Ejecutar un JSON de acción | Ejecutar acciones, scripts y transformaciones de Photoshop |
| Ejecutar desenfoque de profundidad | (No disponible) |
| Ejecutar acciones de Photoshop | Ejecutar acciones, scripts y transformaciones de Photoshop |
| Ejecutar recorte de producto | Ejecutar acciones, scripts y transformaciones de Photoshop |
| Obtener información de capa | Generar un manifiesto |
| Cambiar el tamaño de una imagen | Crear o editar un compuesto |
| Reemplazar objeto inteligente | Crear o editar un compuesto |
| Reemplazar objeto inteligente 2 | Crear o editar un compuesto |
| Rotar una imagen | Ejecutar acciones, scripts y transformaciones de Photoshop |
| Aplicar una marca de agua a una imagen | Crear o editar un compuesto |

## Información de API de Adobe Photoshop

El conector de Adobe Photoshop utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL base</td> 
   <td>https://image.adobe.io/pie/psdService</td> 
  </tr>
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.12.31</td> 
  </tr>
 </tbody> 
 </table>

## Crear una conexión a [!DNL Adobe Photoshop]

Para crear una conexión para los módulos de [!DNL Adobe Photoshop]:

1. En cualquier módulo, haga clic en **[!UICONTROL Agregar]** junto al cuadro Conexión.

1. Rellene los campos siguientes:

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">[!UICONTROL Connection type]</td>
        <td>
          <p>Seleccione si desea utilizar una conexión JWT o una conexión servidor a servidor.</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>Introduzca un nombre para esta conexión.</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Introduzca el [!UICONTROL Adobe] [!UICONTROL Client ID]. Esto se puede encontrar en la sección de detalles de [!UICONTROL Credentials] del [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Introduzca su [!DNL Adobe] [!UICONTROL Client Secret]. Esto se puede encontrar en la sección de detalles de [!UICONTROL Credentials] del [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Technical account ID]</td>
        <td>Si utiliza una conexión JWT, escriba su [!DNL Adobe] ID de cuenta técnica de . Esto se puede encontrar en la sección de detalles de [!UICONTROL Credentials] del [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Organization ID]</td>
        <td>Si utiliza una conexión JWT, escriba su [!DNL Adobe] [!UICONTROL Organization ID]. Esto se puede encontrar en la sección de detalles de [!UICONTROL Credentials] del [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Private key]</td>
        <td>
          <p>Si está usando una conexión JWT, escriba la clave privada que se generó cuando se crearon sus credenciales en [!DNL Adobe Developer Console]. </p>
          <p>Para extraer la clave privada o el certificado:</p>
          <ol>
            <li value="1">
              <p>Haga clic en <b>[!UICONTROL Extract]</b>.</p>
            </li>
            <li value="2">
              <p>Seleccione el tipo de archivo que va a extraer.</p>
            </li>
            <li value="3">
              <p>Seleccione el archivo que contiene la clave privada o el certificado.</p>
            </li>
            <li value="4">
              <p>Introduzca la contraseña del archivo.</p>
            </li>
            <li value="5">
              <p>Haga clic en <b>Guardar</b> para extraer el archivo y volver a la configuración de conexión.</p>
            </li>
          </ol>
        </td>
        </tr>
      </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.

## Módulos de [!DNL Adobe Photoshop] y sus campos

Al configurar módulos de [!DNL Adobe Photoshop], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL Adobe Photoshop] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, consulte [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Acciones

* [Convertir HEX a RGB](#convert-hex-to-rgb)
* [Creación de una mesa de trabajo](#create-an-artboard)
* [Crear o editar un compuesto](#create-or-edit-a-composite)
* [Edición de una imagen con varios ajustes](#edit-an-image-with-various-adjustments)
* [Ejecutar acciones, scripts y transformaciones de Photoshop](#execute-photoshop-actions-scripts-and-transformations)
* [Generar un manifiesto](#generate-a-manifest)
* [Quitar el fondo](#remove-background)

#### Convertir HEX a RGB

Este módulo convierte un código de color HEX en color RGB.



Este módulo realiza ajustes de estilo Lightroom en una imagen.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL HEX]</td>
      <td>Introduzca o asigne el código HEX que desea convertir a RGB.</td>
    </tr>
    </tbody>
</table>

#### Creación de una mesa de trabajo

Este módulo crea una nueva mesa de trabajo en Photoshop.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Imágenes]</td>
      <td>
        <p>Para cada imagen que desee agregar a esta mesa de trabajo, haga clic en <b>Agregar elemento</b> e introduzca el tipo de origen y la ubicación de la imagen.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Espaciado entre mesas de trabajo]</p>
      </td>
   <td>Especifique o asigne el espaciado, en píxeles, que desea que haya entre cada mesa de trabajo.</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>Para cada archivo convertido que desee crear, haga clic en Agregar elemento e introduzca las opciones de almacenamiento, ubicación y otras como se muestran en la lista.</p>
      </td>
    </tr>
    </tbody>
</table>

#### Crear o editar un compuesto

Este módulo crea o edita un compuesto en Photoshop.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Imágenes]</td>
      <td>
        <p>Para cada imagen que desee agregar a esta mesa de trabajo, haga clic en <b>Agregar elemento</b> e introduzca el tipo de origen y la ubicación de la imagen.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Width]</p>
      </td>
   <td>Si está creando una imagen, introduzca su anchura en píxeles.</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Height]</td>
      <td>
        <p>Si está creando una imagen, introduzca la altura de la imagen en píxeles.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Mode]</td>
      <td>
        <p>Seleccione el modo de color para esta imagen.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Relleno]</td>
      <td>
        <p>Seleccione el tipo de relleno para la capa de fondo.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Name]</td>
      <td>
        <p>Introduzca o asigne un nombre para la nueva imagen.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Factor de escala de píxeles]</td>
      <td>
        <p>Introduzca o asigne el factor de escala de píxeles. Debe ser un número entre 0,1 y 1.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Resolución]</td>
      <td>
        <p>En el campo <b>Valor</b>, escriba el valor de la resolución en unidades de densidad (píxeles por pulgada). El valor predeterminado es 72.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Tipo de perfil]</td>
      <td>
        <p>Si desea anular el perfil de color predeterminado, seleccione un tipo de perfil e introduzca los detalles como se indica a continuación.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Recorte &gt; Superior/Izquierda/Inferior/Derecha]</td>
      <td>
        <p>Introduzca los límites a los que desea recortar la imagen.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Ocultar]</td>
      <td>
        <p>Seleccione sí para ocultar los píxeles fuera de los límites de recorte. Si se establece en false, se eliminan los píxeles fuera de los límites de recorte. El valor predeterminado es false.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Cambiar tamaño &gt; Anchura]</td>
      <td>
        <p>Seleccione la unidad que desee utilizar para la anchura y, a continuación, seleccione el valor que representa la anchura que desee. </p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Cambiar tamaño &gt; Altura]</td>
      <td>
        <p>Seleccione la unidad que desea utilizar para la altura y, a continuación, seleccione el valor que representa la altura que desea. </p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Resolución]</td>
      <td>
        <p>Seleccione la unidad que desea utilizar para la resolución y, a continuación, seleccione el valor que representa la resolución que desea.</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Remuestreo]</td>
      <td>
        <p>Seleccione el método de remuestreo que se utilizará al cambiar el tamaño.</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Restringir proporciones]</td>
      <td>
        <p>Seleccione Sí para mantener la relación de aspecto entre anchura y altura. Seleccione No para permitir un ajuste independiente de la anchura y la altura.</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Rasterizar]</td>
      <td>
        <p>Seleccione si desea rasterizar la imagen.</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Estilos de escala]</td>
      <td>
        <p>Seleccione si desea aplicar escala a los estilos cuando cambie el tamaño de la imagen.</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Recortar tras]</td>
      <td>
        <p>Seleccione si desea recortar los píxeles transparentes.</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Layers]</td>
      <td>
        <p>Para cada elemento posterior que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca los detalles de la capa. </p><p>Para obtener más información, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/photoshop-v2/#operation/createComposite">Crear o editar un elemento compuesto</a> en la documentación de Adobe.</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Fuente predeterminada PostScript name]</td>
      <td>
        <p>Escriba o asigne el nombre de PostScript de la fuente predeterminada que desee utilizar.</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Falta estrategia de fuente]</td>
      <td>
        <p>Seleccione si desea que falle la creación o edición, o si desea utilizar la fuente predeterminada en caso de que no haya una fuente disponible.</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Fuentes adicionales]</td>
      <td>
        <p>Para cada fuente que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca la dirección URL de origen de la fuente. </p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>Para cada archivo editado que desee crear, haga clic en Agregar elemento e introduzca los detalles de salida. </p><p>Para obtener más información, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/photoshop-v2/#operation/createComposite">Crear o editar un elemento compuesto</a> en la documentación de Adobe.</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Maximum number of results]</td>
      <td>
        <p>Introduzca o asigne el número máximo de resultados con los que desea que funcione el módulo durante un ciclo de ejecución.</p>
      </td>
      </tr>
      </tbody>
</table>

#### Edición de una imagen con varios ajustes

Este módulo realiza ajustes de estilo Lightroom en una imagen.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Imágenes]</td>
      <td>
        <p>Introduzca o asigne el tipo de origen y la ubicación de la imagen.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Other fields]</p>
      </td>
   <td><p>Para obtener más información, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/photoshop-v2/#operation/edit">Editar una imagen con varios ajustes</a> en la documentación de Adobe.</p></td> 
    </tr>
    </tbody>
</table>

#### Ejecutar acciones, scripts y transformaciones de Photoshop

Este módulo ejecuta acciones, scripts y transformaciones disponibles en la API de Photoshop de Firefly.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Imágenes]</td>
      <td>
        <p>Introduzca o asigne el tipo de origen y la ubicación de la imagen.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Acciones]</p>
      </td>
   <td><p>Para cada acción que desee agregar, haga clic en <b>Agregar elemento</b> e introduzca el origen, la dirección URL y el nombre de la acción.</p></td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL UXP source]</p>
      </td>
   <td><p>Si utiliza un script UXP, seleccione si desea proporcionar una dirección URL o contenido en línea y, a continuación, introduzca o asigne la dirección URL o el contenido.</p></td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Contenido adicional]</p>
      </td>
   <td><p>Añada hasta 25 archivos a los que se haga referencia desde la acción o UXP.</p></td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>Para cada archivo editado que desee crear, haga clic en Agregar elemento e introduzca el formato, el destino y el patrón de salida.</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Maximum number of results]</td>
      <td>
        <p>Introduzca o asigne el número máximo de resultados con los que desea que funcione el módulo durante un ciclo de ejecución.</p>
      </td>
      </tr>
    </tbody>
</table>

#### Generar un manifiesto

Este módulo genera un manifiesto de PSD para la imagen de entrada determinada.



<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Source]</td>
      <td>
        <p>Introduzca o asigne el tipo de origen y la ubicación de la imagen.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>Para cada archivo editado que desee crear, haga clic en Agregar elemento e introduzca los detalles de destino.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Incluir miniaturas de capa]</p>
      </td>
   <td><p>Seleccione Sí si desea que el módulo genere una representación de miniaturas para cada capa del manifiesto.</p></td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Profundidad máxima de la miniatura]</p>
      </td>
   <td><p>Introduzca o asigne la profundidad máxima para representaciones de miniaturas. Para la profundidad máxima, escriba <code>0</code>.</p></td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Formato de miniatura de capa]</p>
      </td>
   <td><p>Seleccione si desea que las miniaturas estén en formato JPEG o PNG.</p></td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Extraer datos de objetos inteligentes]</td>
      <td>
        <p>Seleccione si desea extraer objetos inteligentes incrustados e incluir una dirección URL con firma previa en el manifiesto.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Recortar a transparencia]</td>
      <td>
        <p>Seleccione si desea recortar la miniatura de cada capa para eliminar los píxeles transparentes.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Maximum number of results]</td>
      <td>
        <p>Introduzca o asigne el número máximo de resultados con los que desea que funcione el módulo durante un ciclo de ejecución.</p>
      </td>
      </tr>
    </tbody>
</table>

#### Quitar el fondo

Este módulo de acción identifica el asunto principal de la imagen y elimina el fondo.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que se almacena el archivo del que desea quitar el fondo.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo del que desea quitar el fondo. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde desea almacenar el nuevo archivo.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta donde se almacenará el nuevo archivo.  Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista. Esto solo se aplica a los archivos en el almacenamiento de Adobe.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Color space]</p>
      </td>
   <td>Seleccione si la imagen de salida utiliza RGB o color RGBA. </td> 
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Mask format]</p>
      </td>
   <td>Seleccione si los bordes de la imagen deben ser suaves (calados) o binarios. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Optimize]</p>
      </td>
   <td>Seleccione Rendimiento para optimizar la velocidad o Lote para permitir el tiempo de espera. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Post process]</p>
      </td>
   <td>Seleccione si desea habilitar el posprocesamiento.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Version]</p>
      </td>
   <td>El valor predeterminado es 4.0</td> 
    </tr> 
    </tbody>
</table>


### Heredado

* [Aplicar ediciones de PSD (heredadas)](#apply-psd-edits-legacy)
* [Corrección automática de color de una imagen (heredada)](#auto-color-correct-an-image-legacy)
* [Convertir formato de imagen (heredado)](#convert-image-format-legacy)
* [Crear una máscara (heredada)](#create-a-mask-legacy)
* [Crear un nuevo PSD (heredado)](#create-a-new-psd-legacy)
* [Crear representaciones (heredadas)](#create-renditions-legacy)
* [Edición de capas de texto (heredadas)](#edit-text-layers-legacy)
* [Editar capas de texto 2 (heredadas)](#edit-text-layers-2-legacy)
* [Ejecutar una acción JSON (heredada)](#execute-an-action-json-legacy)
* [Ejecutar desenfoque de profundidad (heredado)](#execute-depth-blur-legacy)
* [Ejecutar acciones de Photoshop (heredadas)](#execute-photoshop-actions-legacy)
* [Ejecutar recorte de productos (heredado)](#execute-product-crop-legacy)
* [Obtener información de capa (heredada)](#get-layer-info-legacy)
* [Realizar una llamada de API personalizada (heredada)](#make-a-custom-api-call-legacy)
* [Quitar fondo (heredado)](#remove-background-legacy)
* [Reemplazar un objeto inteligente (heredado)](#replace-a-smart-object-legacy)
* [Reemplazar un objeto inteligente 2 (heredado)](#replace-a-smart-object-2-legacy)
* [Cambiar el tamaño de una imagen (heredada)](#resize-an-image-legacy)
* [Marca de agua de una imagen (heredada)](#watermark-an-image-legacy)

#### Aplicar ediciones de PSD (heredadas)

>[!NOTE]
>
>Este módulo ha quedado obsoleto y dejará de funcionar a partir del 30 de julio de 2026.
>Actualice este módulo a [Cree o edite un módulo compuesto](#create-or-edit-a-composite).

Este módulo de acción aplica una variedad de ediciones a nivel de documento y capa.

Este módulo admite archivos grandes. Para obtener más información sobre los archivos grandes, consulte [Trabajar con archivos grandes](/help/workfront-fusion/references/scenarios/fusion-large-files.md).

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivo donde se almacena el archivo que desea editar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo que desea editar. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options &gt; Document &gt; Image size) Height]</p>
      </td>
      <td> Introduzca o asigne la altura de la imagen en píxeles. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options &gt; Document &gt; Image size) Width]</p>
      </td>
      <td> Introduzca o asigne la anchura de la imagen en píxeles. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options &gt; Document &gt; Canvas size) Top]</p>
      </td>
   <td> Escriba o asigne, en píxeles, la coordenada y de la esquina superior izquierda del documento. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options &gt; Document &gt; Canvas size) Bottom]</p>
      </td>
   <td> Escriba o asigne, en píxeles, la coordenada y de la esquina inferior derecha del documento. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options &gt; Document &gt; Canvas size) Left]</p>
      </td>
   <td> Escriba o asigne, en píxeles, la coordenada x de la esquina superior izquierda del documento. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options &gt; Document &gt; Canvas size) Right]</p>
      </td>
   <td> Escriba o asigne, en píxeles, la coordenada x de la esquina inferior derecha del documento. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options &gt; Document) Trim]</p>
      </td>
   <td> Seleccione Píxeles transparentes para basar el recorte en píxeles transparentes de la imagen. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Default font]</p>
      </td>
   <td> Introduzca el nombre completo del PostScript de la fuente que se vaya a utilizar como valor predeterminado global para el documento. Esta fuente se utilizará para cualquier capa de texto a la que le falte una fuente y no se haya proporcionado específicamente ninguna otra fuente para esa capa. Si falta esa fuente, la opción que se haya especificado en Administrar fuentes que faltan es la que se aplicará. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Fonts]</p>
      </td>
   <td> Para cada fuente que necesite el documento, haga clic en Agregar elemento e introduzca la ubicación de almacenamiento y la ubicación de archivo de la fuente. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Manage missing fonts]</p>
      </td>
   <td> Seleccione la acción que debe realizarse si en el documento faltan una o más fuentes. <ul><li><code>fail</code>: el trabajo no se realizará correctamente y el estado se establecerá en fallido; los detalles del error se proporcionarán en la sección de detalles del estado.</li><li><code>useDefault</code>: el trabajo se realizará correctamente y todas las fuentes que faltan se reemplazarán con ArialMT.</li></ul></td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Layers]</p>
      </td>
   <td> Para cada capa que desee añadir, haga clic en Añadir elemento y rellene los detalles de la capa. <p>Para obtener más información sobre las opciones de capa, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/modifyDocumentAsync">Aplicar ediciones de PSD</a> en la documentación de Adobe Photoshop.  </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>Para cada archivo editado que desee crear, haga clic en Agregar elemento e introduzca el almacenamiento, la ubicación y el tipo que aparecen en la lista.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde desea almacenar el nuevo archivo.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta donde se almacenará el nuevo archivo. Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Type]</p>
      </td>
   <td>Seleccione el tipo de archivo al que desea convertir el archivo. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado ha de sobrescribir cualquier archivo de salida que ya exista. Esto solo se aplica a los archivos en el almacenamiento de Adobe.</p>
      </td>
    </tr>
        <tr>
      <td role="rowheader">
        <p>[!UICONTROL (salida) Recortar a lienzo]</p>
      </td>
   <td>Seleccione si las representaciones deben ser de tamaño Lienzo. True recorta las representaciones al tamaño Lienzo, mientras que False hace que las representaciones tengan el tamaño Tamaño</td> 
    </tr>
    </tbody>
</table>

#### Corrección automática de color de una imagen (heredada)

El color automático de este módulo de acción corrige la imagen especificada.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde se almacena el archivo con el color correcto.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo cuyo color desea corregir. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde desea almacenar el nuevo archivo.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta donde se almacenará el nuevo archivo. Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Type]</p>
      </td>
   <td>Seleccione el tipo de archivo al que desea convertir el archivo. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado ha de sobrescribir cualquier archivo de salida que ya exista. Esto solo se aplica a los archivos en el almacenamiento de Adobe.</p>
      </td>
    </tr>
    </tbody>
</table>

#### Convertir formato de imagen (heredado)

>[!NOTE]
>
>Este módulo ha quedado obsoleto y dejará de funcionar a partir del 30 de julio de 2026.
>Actualice este módulo a [Cree o edite un módulo compuesto](#create-or-edit-a-composite).

Este módulo de acción convierte un archivo en JPEG, PNG, PSD o TIFF.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que se almacena el archivo del que desea quitar el fondo.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo del que desea quitar el fondo. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>Para cada archivo convertido que desee crear, haga clic en Agregar elemento e introduzca el almacenamiento, la ubicación y el tipo como se indica a continuación.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde desea almacenar el nuevo archivo.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta donde se almacenará el nuevo archivo. Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Type]</p>
      </td>
   <td>Seleccione el tipo de archivo al que desea convertir el archivo. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado ha de sobrescribir cualquier archivo de salida que ya exista. Esto solo se aplica a los archivos en el almacenamiento de Adobe.</p>
      </td>
    </tr>
    </tbody>
</table>

#### Crear una máscara (heredada)

Este módulo de acción devuelve un archivo PNG con una máscara aplicada alrededor del asunto.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos desde el que se almacena el archivo del que desea crear una máscara.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Escriba o asigne la dirección URL o la ruta de acceso del archivo del que desea crear una máscara. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde desea almacenar el archivo de máscara.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta de acceso donde se almacenará el archivo de máscara. Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista. Esto solo se aplica a los archivos en el almacenamiento de Adobe.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Color space]</p>
      </td>
   <td>Seleccione si la imagen de salida utiliza RGB o color RGBA. </td> 
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Mask format]</p>
      </td>
   <td>Seleccione si la máscara debe ser suave (con calado) o binaria. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Optimize]</p>
      </td>
   <td>Seleccione Rendimiento para optimizar la velocidad o Lote para permitir el tiempo de espera. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Post process]</p>
      </td>
   <td>Seleccione si desea habilitar el posprocesamiento.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Version]</p>
      </td>
   <td>El valor predeterminado es 4.0</td> 
    </tr> 
    </tbody>
</table>

#### Crear un nuevo PSD (heredado)

>[!NOTE]
>
>Este módulo ha quedado obsoleto y dejará de funcionar a partir del 30 de julio de 2026.
>Actualice este módulo a [Cree o edite un módulo compuesto](#create-or-edit-a-composite).

Este módulo de acción crea un nuevo PSD con capas opcionales y genera representaciones o las guarda como un PSD.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options &gt; Document &gt; Image size) Height]</p>
      </td>
      <td> Introduzca o asigne la altura de la imagen en píxeles. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options &gt; Document &gt; Image size) Width]</p>
      </td>
      <td> Introduzca o asigne la anchura de la imagen en píxeles. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Resolución de [!UICONTROL (Opciones &gt; Documento)]</p>
      </td>
   <td> Especifique o asigne la resolución de la imagen en píxeles por pulgada. Debe estar entre 72 y 300. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Opciones &gt; Documento) Modo]</p>
      </td>
   <td> Seleccione el modo de la imagen. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Opciones &gt; Documento) Fill]</p>
      </td>
   <td> Seleccione si desea que el relleno de la capa de fondo sea transparente, blanco o el color de fondo de la imagen. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Opciones &gt; Documento) Profundidad]</p>
      </td>
   <td> Seleccione la profundidad de bits de la imagen. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Layers]</p>
      </td>
   <td> Para cada capa que desee añadir, haga clic en Añadir elemento y rellene los detalles de la capa. <p>Para obtener más información sobre las opciones de capa, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/createDocumentAsync">Crear PSD</a> en la documentación de Adobe Photoshop.  </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Opciones) Fuente global]</p>
      </td>
   <td> Introduzca el nombre completo del PostScript de la fuente que se vaya a utilizar como valor predeterminado global para el documento. Esta fuente se utilizará para cualquier capa de texto a la que le falte una fuente y no se haya proporcionado específicamente ninguna otra fuente para esa capa. Si falta esa fuente, la opción que se haya especificado en Administrar fuentes que faltan es la que se aplicará. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Fonts]</p>
      </td>
   <td> Para cada fuente que necesite el documento, haga clic en Agregar elemento e introduzca la ubicación de almacenamiento y la ubicación de archivo de la fuente. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Manage missing fonts]</p>
      </td>
   <td> Seleccione la acción que debe realizarse si en el documento faltan una o más fuentes. <ul><li><code>fail</code>: el trabajo no se realizará correctamente y el estado se establecerá en fallido; los detalles del error se proporcionarán en la sección de detalles del estado.</li><li><code>useDefault</code>: el trabajo se realizará correctamente y todas las fuentes que faltan se reemplazarán con ArialMT.</li></ul></td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>Para cada archivo que desee crear, haga clic en Agregar elemento e introduzca el almacenamiento, la ubicación y el tipo que aparecen en la lista.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde desea almacenar el nuevo archivo.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta donde se almacenará el nuevo archivo. Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Type]</p>
      </td>
   <td>Seleccione el tipo de archivo al que desea convertir el archivo. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Salida) Otros campos]</td>
      <td>
        <p><p>Para obtener más información sobre las opciones de salida, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/createDocumentAsync">Crear PSD</a> en la documentación de Adobe Photoshop.  </p>
      </td>
    </tr>
    </tbody>
</table>

#### Crear representaciones (heredadas)

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivo donde se almacena el archivo que desea editar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo que desea editar. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>Para cada archivo que desee crear, haga clic en Agregar elemento e introduzca la opción de almacenamiento, ubicación, tipo y sobrescritura como se muestra en la lista.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Salidas) Almacenamiento]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que desea almacenar el archivo editado.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Salidas) Ubicación del archivo]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta de acceso donde se desea almacenar el archivo editado.  Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Salidas) Tipo]</p>
      </td>
   <td> Seleccione el tipo de archivo para el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Salidas) Sobrescribir]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista.</p>
      </td>
    </tr>
      </tbody>
</table>

#### Edición de capas de texto (heredadas)

>[!NOTE]
>
>Este módulo ha quedado obsoleto y dejará de funcionar a partir del 30 de julio de 2026.
>Actualice este módulo al módulo [Ejecutar acciones, scripts y transformaciones de Photoshop](#execute-photoshop-actions-scripts-and-transformations).

Este módulo de acción edita las capas de texto en un archivo Photoshop. Puede introducir detalles de edición independientes para varias capas en el mismo archivo.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Input file storage]</td>
      <td>
        <p>Seleccione el servicio de archivo donde se almacena el archivo que desea editar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Input file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo que desea editar. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Manage missing fonts]</td>
      <td>
        <p>Seleccione la acción que debe realizarse si en el documento faltan una o más fuentes. Si no se proporciona la fuente, el módulo utilizará la fuente predeterminada.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Default font]  </td>
      <td>
        <p>Introduzca el nombre completo del PostScript de la fuente que se vaya a utilizar como valor predeterminado global para el documento. Esta fuente se utilizará para cualquier capa de texto a la que le falte una fuente y no se haya proporcionado específicamente ninguna otra fuente para esa capa. Si falta esa fuente, la opción que se haya especificado en Administrar fuentes que faltan es la que se aplicará.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Fonts]</p>
      </td>
   <td> Introduzca la ubicación de almacenamiento y la ubicación del archivo de la fuente. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Layers]</td>
   <td> <p>Para cada capa de texto que desee editar, haga clic en <b>Agregar elemento</b> e introduzca las opciones de capa.<p>Para obtener detalles sobre las opciones de capa, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/editTextLayerAsync">Editar texto</a> en la documentación de Adobe Photoshop.</p>  </td>     </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que desea almacenar el archivo editado.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta de acceso donde se desea almacenar el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Type]</p>
      </td>
   <td> Seleccione el tipo de archivo para el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Editar capas de texto 2 (heredadas)

>[!NOTE]
>
>Este módulo ha quedado obsoleto y dejará de funcionar a partir del 30 de julio de 2026.
>Actualice este módulo al módulo [Ejecutar acciones, scripts y transformaciones de Photoshop](#execute-photoshop-actions-scripts-and-transformations).

Este módulo de acción edita una capa de texto en un archivo Photoshop.

Para editar varias capas, use el módulo [Editar capas de texto](#edit-text-layers).

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Input file storage]</td>
      <td>
        <p>Seleccione el servicio de archivo donde se almacena el archivo que desea editar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Input file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo que desea editar. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Manage missing fonts]</td>
      <td>
        <p>Seleccione la acción que debe realizarse si en el documento faltan una o más fuentes. Si no se proporciona la fuente, el módulo utilizará la fuente predeterminada.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Default font]  </td>
      <td>
        <p>Introduzca el nombre completo del PostScript de la fuente que se vaya a utilizar como valor predeterminado global para el documento. Esta fuente se utilizará para cualquier capa de texto a la que le falte una fuente y no se haya proporcionado específicamente ninguna otra fuente para esa capa. Si falta esa fuente, la opción que se haya especificado en Administrar fuentes que faltan es la que se aplicará.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Fonts]</p>
      </td>
   <td> Introduzca la ubicación de almacenamiento y la ubicación del archivo de la fuente. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Layers]</td>
   <td> <p>Para obtener detalles sobre las opciones de capa, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/editTextLayerAsync">Editar capa de texto</a> en la documentación de Adobe Photoshop.</p>  </td>     </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Output file storage]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que desea almacenar el archivo editado.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que desea almacenar el archivo editado.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta de acceso donde se desea almacenar el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Type]</p>
      </td>
   <td> Seleccione el tipo de archivo para el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista.</p>
      </td>
    </tr>
  </tbody>
</table>


#### Ejecutar una acción JSON (heredada)

>[!NOTE]
>
>Este módulo ha quedado obsoleto y dejará de funcionar a partir del 30 de julio de 2026.
>Actualice este módulo al módulo [Ejecutar acciones, scripts y transformaciones de Photoshop](#execute-photoshop-actions-scripts-and-transformations).

Este módulo de acción ejecuta acciones de Photoshop mediante comandos JSON.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivo donde se almacena el archivo que desea editar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo que desea editar. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Action JSON]</td>
      <td>
        <p>Introduzca el comando JSON para la acción que desea realizar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Fonts / Patterns / Brushes / Additional images]</td>
      <td>
        <p>Para cada fuente, patrón, pincel o imagen adicional que desee utilizar en esta acción, haga clic en Agregar elemento e introduzca el almacenamiento y la ubicación de archivo del elemento.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Font / Pattern / Brush file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo que desea utilizar. </td> 
    </tr>
    <tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>Para cada archivo que desee crear, haga clic en Agregar elemento e introduzca la opción de almacenamiento, ubicación, tipo y sobrescritura como se muestra en la lista.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Salidas) Almacenamiento]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que desea almacenar el archivo editado.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Salidas) Archivo URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta de acceso donde se desea almacenar el archivo editado.  Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Salidas) Tipo]</p>
      </td>
   <td> Seleccione el tipo de archivo para el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Salidas) Sobrescribir]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista.</p>
      </td>
    </tr>
      </tbody>
</table>

#### Ejecutar desenfoque de profundidad (heredado)

>[!NOTE]
>
>Este módulo ha quedado obsoleto y dejará de funcionar a partir del 30 de julio de 2026.

Este módulo de acción ejecuta el desenfoque de la profundidad en el archivo seleccionado.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Input file storage]</td>
      <td>
        <p>Seleccione el servicio de archivo donde se almacena el archivo que desea editar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Input file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo que desea editar. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Salidas) Almacenamiento]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que desea almacenar el archivo editado.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Salidas) Archivo URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta de acceso donde se desea almacenar el archivo editado.  Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Salidas) Tipo]</p>
      </td>
   <td> Seleccione el tipo de archivo para el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Salidas) Sobrescribir]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista.</p>
      </td>
    </tr>
   <tr>
      <td role="rowheader">[!UICONTROL Other fields]</td>
      <td>
        <p>Para obtener más información sobre otras opciones de desenfoque de la profundidad, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/applyDepthBlurAsync">Ejecutar desenfoque de la profundidad </a> en la documentación de la API de Adobe Photoshop.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Ejecutar acciones de Photoshop (heredadas)

>[!NOTE]
>
>Este módulo ha quedado obsoleto y dejará de funcionar a partir del 30 de julio de 2026.
>Actualice este módulo al módulo [Ejecutar acciones, scripts y transformaciones de Photoshop](#execute-photoshop-actions-scripts-and-transformations).

Este módulo de acción ejecuta una acción de Photoshop en la imagen seleccionada.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Input file storage]</td>
      <td>
        <p>Seleccione el servicio de archivo donde se almacena el archivo que desea editar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Input file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo que desea editar. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Actions file storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde se almacena el archivo de acciones.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Actions file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo de acciones. </td> 
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Action name]</p>
      </td>
   <td> Si solo desea ejecutar una acción concreta, puede especificar la acción que se debe reproducir desde ActionSet. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Font / Pattern / Brush storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde se almacena el archivo que desea utilizar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Font / Pattern / Brush file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo que desea utilizar. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Salidas) Almacenamiento]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que desea almacenar el archivo editado.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Salidas) Archivo URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta de acceso donde se desea almacenar el archivo editado.  Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Salidas) Tipo]</p>
      </td>
   <td> Seleccione el tipo de archivo para el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Salidas) Sobrescribir]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista.</p>
      </td>
    </tr>
   <tr>
      <td role="rowheader">[!UICONTROL Other fields]</td>
      <td>
        <p>Para obtener más información sobre otras opciones de desenfoque de la profundidad, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/applyDepthBlurAsync">Ejecutar desenfoque de la profundidad </a> en la documentación de la API de Adobe Photoshop.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Ejecutar recorte de productos (heredado)

>[!NOTE]
>
>Este módulo ha quedado obsoleto y dejará de funcionar a partir del 30 de julio de 2026.
>Actualice este módulo al módulo [Ejecutar acciones, scripts y transformaciones de Photoshop](#execute-photoshop-actions-scripts-and-transformations).

Este módulo de acción ejecuta el recorte de productos en la imagen seleccionada.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Input file storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde almacenar el archivo que desea recortar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Input file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo que desea recortar. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Unit]</p>
      </td>
   <td> Seleccione si desea describir el ajuste de altura y anchura en píxeles o como un porcentaje. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Width]</p>
      </td>
   <td> Introduzca o asigne la cantidad de relleno de anchura que desea añadir. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Height]</p>
      </td>
   <td> Introduzca o asigne la cantidad de relleno de altura que desea añadir. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Salidas) Almacenamiento]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que desea almacenar el archivo editado.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Salidas) Archivo URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta de acceso donde se desea almacenar el archivo editado.  Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Salidas) Tipo]</p>
      </td>
   <td> Seleccione el tipo de archivo para el archivo editado. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Salidas) Sobrescribir]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista.</p>
      </td>
    </tr>
   <tr>
      <td role="rowheader">[!UICONTROL Other fields]</td>
      <td>
        <p>Para obtener más información sobre otras opciones de desenfoque de la profundidad, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/applyDepthBlurAsync">Ejecutar desenfoque de la profundidad </a> en la documentación de la API de Adobe Photoshop.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Obtener información de capa (heredada)

>[!NOTE]
>
>Este módulo ha quedado obsoleto y dejará de funcionar a partir del 30 de julio de 2026.
>Actualice este módulo al módulo [Generar un manifiesto](#generate-a-manifest).

Este módulo de acción recupera información de capa del archivo de PSD especificado.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Input file storage]</td>
      <td>
        <p>Seleccione el servicio de archivos en el que se almacena el archivo del que desea recuperar información de capa.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Input file URL]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo del que desea recuperar información de capa. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Thumbnails]</p>
      </td>
   <td> Seleccione el tipo de archivo que desea que tengan las miniaturas. Las miniaturas son pequeñas previsualizaciones para cualquier capa procesable.</td> 
    </tr>
  </tbody>
</table>

#### Realizar una llamada API personalizada

Este módulo de acción realiza una llamada personalizada a la API de Photoshop.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p>Introduzca una ruta relativa a <code>https://image.adobe.io/pie/psdService</code>. Ejemplo: <code>/photoshopActions</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
      </td>
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, consulte <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de petición HTTP</a>.</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p>
        <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion añade encabezados de autorización automáticamente.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Query String]  </td>
      <td>
        <p>Introduzca la cadena de consulta de la solicitud.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Body]</td>
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>

#### Reemplazar un objeto inteligente (heredado)

>[!NOTE]
>
>Este módulo ha quedado obsoleto y dejará de funcionar a partir del 30 de julio de 2026.
>Actualice este módulo a [Cree o edite un módulo compuesto](#create-or-edit-a-composite).

>[!NOTE]
>
>Este módulo ha quedado obsoleto y dejará de funcionar a partir del 30 de julio de 2026.
>Actualice este módulo a [Cree o edite un módulo compuesto](#create-or-edit-a-composite).

Este módulo de acción sustituye un objeto inteligente en una capa de PSD y genera nuevas representaciones.

Este módulo utiliza la versión 2 de la API de objetos inteligentes.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde se almacena el objeto inteligente.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del objeto inteligente. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Layers]</p>
      </td>
   <td>Para cada capa que desee añadir al objeto inteligente, haga clic en Añadir elemento e introduzca el nombre o ID del objeto, el servicio de archivos donde se almacena el objeto inteligente y la dirección URL o la ruta de la capa.<p>Para obtener descripciones de la configuración avanzada en esta área, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/replaceSmartObjectAsync">Reemplazar un objeto inteligente</a> en la documentación de la API de Photoshop </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Cambiar tamaño de imagen durante la ubicación]</p>
      </td>
   <td> Seleccione si desea cambiar el tamaño de la imagen.</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>Para cada nueva representación que desee que produzca el módulo, haga clic en Añadir elemento y rellene los campos siguientes. Se pueden tener un máximo de 25 archivos de salida.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde desea almacenar el nuevo archivo.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta donde se almacenará el nuevo archivo.  Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Salidas) Tipo]</p>
      </td>
   <td> Seleccione el tipo de archivo para el archivo editado. </td> 
    </tr>
     </tbody>
</table>

#### Reemplazar un objeto inteligente 2 (heredado)

Este módulo de acción sustituye un objeto inteligente en una capa de PSD y genera nuevas representaciones.

Este módulo utiliza la versión heredada de los objetos inteligentes.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde se almacena el objeto inteligente.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del objeto inteligente. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Layers]</p>
      </td>
   <td>Para cada capa que desee añadir al objeto inteligente, haga clic en Añadir elemento e introduzca el nombre o ID del objeto, el servicio de archivos donde se almacena el objeto inteligente y la dirección URL o la ruta de la capa.<p>Para obtener descripciones de la configuración avanzada en esta área, consulte <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/replaceSmartObjectAsync">Reemplazar un objeto inteligente</a> en la documentación de la API de Photoshop </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>Para cada nueva representación que desee que produzca el módulo, haga clic en Añadir elemento y rellene los campos siguientes. Se pueden tener un máximo de 25 archivos de salida.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde desea almacenar el nuevo archivo.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta donde se almacenará el nuevo archivo.  Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Width]</p>
      </td>
   <td> La anchura, en píxeles, del archivo de salida. El módulo conservará la relación de aspecto original. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado ha de sobrescribir cualquier archivo de salida que ya exista. Esto solo se aplica a los archivos en el almacenamiento de Adobe.</p>
      </td>
    </tbody>
</table>

#### Cambiar el tamaño de una imagen (heredada)

>[!NOTE]
>
>Este módulo ha quedado obsoleto y dejará de funcionar a partir del 30 de julio de 2026.
>Actualice este módulo a [Cree o edite un módulo compuesto](#create-or-edit-a-composite).

Esta acción cambia el tamaño de una imagen con la misma relación de aspecto.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde se almacena el archivo cuyo tamaño desea cambiar.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo cuyo tamaño desea cambiar.  Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>Para cada archivo convertido que desee crear, haga clic en Agregar elemento e introduzca las opciones de almacenamiento, ubicación y otras como se muestran en la lista.</p>
      </td>
    </tr>
    <tr>
    <tr>
      <td role="rowheader">[!UICONTROL Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde desea almacenar el nuevo archivo.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL File location]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta donde se almacenará el nuevo archivo.  Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Width]</p>
      </td>
   <td> La anchura, en píxeles, del archivo de salida. El módulo conservará la relación de aspecto original. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Max width]</p>
      </td>
   <td>Cuando la anchura es 0, se puede proporcionar el valor máximo para obtener el tamaño. La anchura máxima tiene prioridad porque es más pequeña que la anchura del documento.</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado sobrescribirá cualquier archivo de salida que ya exista. Esto solo se aplica a los archivos en el almacenamiento de Adobe.</p>
      </td>
    </tr>
        <tr>
      <td role="rowheader">
        <p>[!UICONTROL Trim to canvas]</p>
      </td>
   <td>Seleccione Sí para recortar las representaciones al tamaño de lienzo o No para que su tamaño sea de capa.</td> 
    </tr>
    </tbody>
</table>

#### Marca de agua de una imagen (heredada)

>[!NOTE]
>
>Este módulo ha quedado obsoleto y dejará de funcionar a partir del 30 de julio de 2026.
>Actualice este módulo a [Cree o edite un módulo compuesto](#create-or-edit-a-composite).

Este módulo de acción añade una marca de agua a la imagen seleccionada.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Photoshop], consulte <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Crear una conexión con [!DNL Adobe Photoshop]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">Almacenamiento de [!UICONTROL (Base &gt; Entrada)]</td>
      <td>
        <p>Seleccione el servicio de archivos donde se almacena el archivo al que quiera añadir una marca de agua.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Base &gt; Entrada) Ubicación del archivo]</p>
      </td>
   <td> Introduzca o asigne la dirección URL o la ruta del archivo al que quiera añadir una marca de agua. </td> 
    </tr>
    <tr>
      <td role="rowheader">Almacenamiento de [!UICONTROL (filigrana &gt; entrada)]</td>
      <td>
        <p>Seleccione el servicio de archivos donde se almacene la marca de agua que se quiera añadir.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">Almacenamiento de [!UICONTROL (filigrana &gt; entrada)]</td>
      <td>
        <p>Seleccione el servicio de archivos donde se almacene la marca de agua que se quiera añadir.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Marca de agua &gt; Límites) Altura]</p>
      </td>
   <td>Introduzca o asigne la altura deseada de la marca de agua en píxeles.</td> 
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Marca de agua &gt; Límites) Anchura]</p>
      </td>
   <td> Especifique o asigne el ancho deseado de la marca de agua en píxeles. </td> 
    </tr>  
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Marca de agua &gt; Límites) Izquierda]</p>
      </td>
   <td> Especifique o asigne la distancia en píxeles desde el lado izquierdo de la imagen a la que debería estar la marca de agua.</td> 
    </tr>  
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Marca de agua &gt; Límites) Superior]</p>
      </td>
   <td> Especifique o asigne la distancia en píxeles desde la parte superior de la imagen a la que debería estar la marca de agua.</td> 
    </tr>  
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Seleccione el servicio de archivos donde quiera almacenar el archivo de marca de agua.</p><p>Al seleccionar el almacenamiento interno de Fusion, el archivo está disponible para módulos posteriores, pero no lo está fuera de este escenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Escriba o asigne la dirección URL o ruta donde se almacenará el archivo de marca de agua. Esto solo es necesario si no ha elegido el almacenamiento interno de Fusion para el almacenamiento de salida.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Type]</p>
      </td>
   <td>Seleccione el tipo de archivo al que desea convertir el archivo. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Width]</p>
      </td>
   <td> La anchura, en píxeles, del archivo de salida. El módulo conservará la relación de aspecto original. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Overwrite]</td>
      <td>
        <p>Seleccione si el archivo recién editado ha de sobrescribir cualquier archivo de salida que ya exista. Esto solo se aplica a los archivos en el almacenamiento de Adobe.</p>
      </td>
    </tbody>
</table>
