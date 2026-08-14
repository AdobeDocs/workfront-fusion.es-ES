---
title: Módulos de Adobe Workfront Planning
description: 'Con los módulos  [!DNL Adobe Workfront Planning] , puede iniciar un escenario de Adobe Workfront Fusion basado en los eventos de su cuenta de Workfront Planning, crear, leer o actualizar acuerdos y otros registros, buscar registros con los criterios que haya establecido y cargar documentos. [!DNL Adobe] '
author: Becky
feature: Workfront Fusion
exl-id: d1bc9e39-da49-4090-a106-14b52855bc8f
TQID: https://experienceleague.adobe.com/QHOFWDOT-18-c0b3wLXsRV5cjGVxlcyLhvZdkev3GFg
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: b7d7ae3c0a4ce47428ca993fd173f21994a58653
workflow-type: tm+mt
source-wordcount: 6097
ht-degree: 37%

---


# Módulos de Adobe Workfront Planning

Con los módulos [!DNL Adobe Workfront Planning], puede almacenar en déclencheur un escenario cuando se produzcan eventos en Workfront Planning. También puede crear, leer, actualizar y eliminar registros, o realizar una llamada de API personalizada a su cuenta de [!DNL Adobe Workfront Planning].

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
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td>
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Requisitos previos

Debe tener lo siguiente para acceder a Workfront Planning:

* Un nuevo paquete y licencia de Workfront. Workfront Planning no está disponible para paquetes o licencias de Workfront heredados.
* Un paquete de Workfront Planning.
* La instancia de Workfront de su organización debe incorporarse a la experiencia unificada de Adobe.

## Información de API de Adobe Workfront Planning

El conector de Adobe Workfront Planning utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">URL base</td> 
   <td><pre><code>https://&#123;&#123;connection.host&#125;&#125;/maestro/api/&#123;&#123;common.maestroApiVersion&#125;&#125;/</code></pre></td> 
  </tr>
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.13.7</td> 
  </tr>
 </tbody> 
 </table>

## Conexión de Workfront Planning a Workfront Fusion

El conector de Workfront Planning utiliza OAuth 2.0 para conectarse a Workfront Planning.

Puede crear una conexión a su cuenta de Workfront Planning directamente desde un módulo de Workfront Planning Fusion.

* [Conectarse a Workfront Planning mediante el ID de cliente y el secreto de cliente](#connect-to-workfront-planning-using-client-id-and-client-secret)
* [Conectar con Workfront Planning mediante una conexión de servidor a servidor](#connect-to-workfront--planning-using-a-server-to-server-connection)

### Conectarse a Workfront Planning mediante el ID de cliente y el secreto de cliente

1. En cualquier módulo de Adobe Workfront Planning, haga clic en **Agregar** junto al campo Conexión.
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
          <p>Seleccione la conexión <b>Adobe Workfront auth</b>.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>Introduzca un nombre para la nueva conexión.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Introduzca su ID de cliente de Workfront. Esto se puede encontrar en el área Aplicaciones OAuth2 del área Configuración en Workfront. Abra la aplicación específica a la que se está conectando para ver el ID de cliente.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Introduzca el secreto de cliente de Workfront. Esto se puede encontrar en el área Aplicaciones OAuth2 del área Configuración en Workfront. Si no dispone de un secreto de cliente para la aplicación OAuth2 en Workfront, puede generar otro. Para obtener instrucciones, consulte la documentación de Workfront.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Authentication URL]</td>
        <td>Este puede seguir siendo el valor predeterminado, o bien puede introducir la dirección URL de su instancia de Workfront, seguida de <code>/integrations/oauth2</code>. <p>Ejemplo: <code>https://mydomain.my.workfront.com/integrations/oauth2</code></p></td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Host prefix]</td>
        <td>En la mayoría de los casos, este valor debe ser <code>origin</code>.
      </tr>
    </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.

   Si no ha iniciado sesión en Workfront Planning, se le dirigirá a una pantalla de inicio de sesión. Después de iniciar sesión, puede permitir la conexión.

>[!NOTE]
>
>* Las conexiones de OAuth 2.0 a la API de Workfront ya no dependen de las claves API.
>* Para crear una conexión con un entorno de zona protegida de Workfront, debe crear una aplicación OAuth2 en ese entorno y, a continuación, utilizar el ID de cliente y el secreto de cliente generados por esa aplicación en la conexión.

### Conectar con Workfront Planning mediante una conexión de servidor a servidor

1. En cualquier módulo de Adobe Workfront Planning, haga clic en **Agregar** junto al campo Conexión.
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
          <p>Seleccione <b>Conexión de servidor a servidor de Adobe Workfront</b>.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>Introduzca un nombre para la nueva conexión.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Instance name]</td>
        <td>
          <p>Introduzca el nombre de su instancia, también conocido como su dominio.</p><p>Ejemplo: si su URL es <code>https://example.my.workfront.com</code>, introduzca <code>example</code>.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Instance lane]</td>
        <td>
          <p>Introduzca el tipo de entorno al que se conectará esta conexión.</p><p>Ejemplo: si su URL es <code>https://example.my.workfront.com</code>, introduzca <code>my</code>.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Introduzca su ID de cliente de Workfront. Esto se puede encontrar en el área Aplicaciones OAuth2 del área Configuración en Workfront. Abra la aplicación específica a la que se está conectando para ver el ID de cliente.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Introduzca el secreto de cliente de Workfront. Esto se puede encontrar en el área Aplicaciones OAuth2 del área Configuración en Workfront. Si no dispone de un secreto de cliente para la aplicación OAuth2 en Workfront, puede generar otro. Para obtener instrucciones, consulte la documentación de Workfront.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Scopes]</td>
        <td>Escriba los ámbitos aplicables para esta conexión.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Host prefix]</td>
        <td>En la mayoría de los casos, este valor debe ser <code>origin</code>.
      </tr>
    </tbody>
    </table>

1. Haga clic en **[!UICONTROL Continuar]** para guardar la conexión y volver al módulo.

   Si no ha iniciado sesión en Workfront Planning, se le dirigirá a una pantalla de inicio de sesión. Después de iniciar sesión, puede permitir la conexión.

>[!NOTE]
>
>* Las conexiones de OAuth 2.0 a la API de Workfront ya no dependen de las claves API.
>* Para crear una conexión con un entorno de zona protegida de Workfront, debe crear una aplicación OAuth2 en ese entorno y, a continuación, utilizar el ID de cliente y el secreto de cliente generados por esa aplicación en la conexión.

## [!DNL Adobe Workfront Planning] módulos de versión 2 y sus campos

>[!IMPORTANT]
>
>Los módulos de esta sección pertenecen al conector Workfront Planning V2.
>Para ver los módulos del conector Workfront Planning V1, consulte [[!DNL Adobe Workfront Planning] Módulos de la versión 1 y sus campos](#adobe-workfront-planning-version-1-modules-and-their-fields).

Al configurar los módulos de Workfront Planning, Workfront Fusion muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse campos adicionales de Workfront, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, consulte [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

* [Espacios de trabajo](#workspaces-v2)
* [Tipos de registro](#record-types-v2)
* [Registros](#records-v2)
* [Campos](#fields-v2)
* [Vistas](#views-v2)
* [Permisos](#permissions-v2)
* [Otros](#other-v2)

### Espacios de trabajo (V2)

* [Crear un espacio de trabajo](#create-a-workspace-v2)
* [Eliminación de un espacio de trabajo](#delete-a-workspace-v2)
* [Obtener todos los espacios de trabajo](#get-all-workspaces-v2)
* [Obtener un espacio de trabajo](#get-a-workspace-v2)
* [Actualización de un espacio de trabajo](#update-a-workspace-v2)

#### Creación de un espacio de trabajo (V2)

Este módulo de acción crea un nuevo espacio de trabajo en Planning.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace name]</p>
      </td>
      <td>Introduzca o asigne un nombre para el nuevo espacio de trabajo.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Descripción</p>
      </td>
      <td>Escriba o asigne una descripción para el nuevo espacio de trabajo/td&gt; 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Color</p>
      </td>
      <td>Seleccione el color que desee utilizar para representar el nuevo tipo de registro</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Icono</p>
      </td>
      <td>Asigne el icono que desee utilizar para este tipo de registro.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Propietario</p>
      </td>
      <td>Introduzca o asigne el ID de usuario de Adobe IMS del usuario del que desea que sea propietario del espacio de trabajo.</td> 
    </tr>
  </tbody>
</table>

#### Eliminación de un espacio de trabajo (V2)

Este módulo de acción elimina un solo espacio de trabajo, especificado por ID.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL ID de espacio de trabajo]</p>
      </td>
      <td>Introduzca o asigne el ID del espacio de trabajo que desea eliminar.</td> 
    </tr>
  </tbody>
</table>

#### Obtener todos los espacios de trabajo (V2)

Este módulo recupera una lista de todos los espacios de trabajo.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Maximum number of returned workspaces]</p>
      </td>
      <td>Introduzca o asigne el número máximo de espacios de trabajo que el módulo devolverá durante un ciclo de ejecución.</td> 
    </tr>
  </tbody>
</table>

#### Obtener un espacio de trabajo (V2)

Este módulo recupera un espacio de trabajo por su ID.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL ID de espacio de trabajo]</p>
      </td>
      <td>Introduzca o asigne el ID del espacio de trabajo que desea recuperar.</td> 
    </tr>
  </tbody>
</table>

#### Actualización de un espacio de trabajo (V2)

Este módulo de acción actualiza un nuevo espacio de trabajo en Planning.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>Seleccione el espacio de trabajo que desea actualizar.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace name]</p>
      </td>
      <td>Introduzca o asigne un nombre para el nuevo espacio de trabajo.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Descripción</p>
      </td>
      <td>Escriba o asigne una descripción para el nuevo espacio de trabajo/td&gt; 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Color</p>
      </td>
      <td>Seleccione el color que desee utilizar para representar el nuevo tipo de registro</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Icono</p>
      </td>
      <td>Asigne el icono que desee utilizar para este tipo de registro.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Propietario</p>
      </td>
      <td>Introduzca o asigne el ID de usuario de Adobe IMS del usuario del que desea que sea propietario del espacio de trabajo.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Secciones de tipo de registro</p>
      </td>
      <td>Para cada sección de tipo de registro que desee agregar a esta área de trabajo, haga clic en <b>Agregar elemento</b> e introduzca el nombre de la sección, los identificadores de tipo de registro y si desea sobrescribir los identificadores de tipo de registro existentes.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Secciones de tipo de registro &gt; Sobrescribir</p>
      </td>
      <td>Seleccione si desea reemplazar las secciones existentes por las del módulo. Si no es así, las secciones del módulo se añaden a la lista de secciones existente.</td> 
    </tr>
  </tbody>
</table>


### Tipos de registro (V2)

* [Creación de un tipo de registro](#create-a-record-type-v2)
* [Eliminación de un tipo de registro](#delete-a-record-type-v2)
* [Obtener tipos de registros globales](#get-global-record-types-v2)
* [Obtener un tipo de registro](#get-a-record-type-v2)
* [Obtener tipos de registros](#get-record-types-v2)
* [Actualización de un tipo de registro](#update-a-record-type-v2)

#### Creación de un tipo de registro (V2)

Este módulo de acción crea un nuevo tipo de registro en el espacio de trabajo seleccionado.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>Seleccione el espacio de trabajo en el que desea crear un tipo de registro.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Nombre para mostrar</p>
      </td>
      <td>Introduzca o asigne un nombre para el nuevo tipo de registro.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Descripción</p>
      </td>
      <td>Introduzca o asigne una descripción para el nuevo tipo de registro.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Icono</p>
      </td>
      <td>Asigne el icono que desee utilizar para este tipo de registro.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Color</p>
      </td>
      <td>Seleccione el color que desee utilizar para representar el nuevo tipo de registro</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Tipo de registro de Source</p>
      </td>
      <td>Si utiliza otro tipo de registro para copiar como punto de partida, seleccione ese tipo de registro.</td> 
    </tr>
  </tbody>
</table>

#### Eliminación de un tipo de registro (V2)

Este módulo de acción elimina un solo tipo de registro, especificado por ID.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL ID de tipo de registro]</p>
      </td>
      <td>Introduzca o asigne el ID del tipo de registro que desea eliminar.</td> 
    </tr>
  </tbody>
</table>

#### Obtener tipos de registros globales (V2)

Este módulo recupera una lista de tipos de registros en una cuenta de Adobe Workfront Planning.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>Seleccione un espacio de trabajo. El módulo devolverá los tipos de registros globales que están disponibles para agregarlos a este espacio de trabajo.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Número máximo de tipos de registro devueltos]</p>
      </td>
      <td>Introduzca o asigne el número máximo de tipos de registro que devolverá el módulo durante un ciclo de ejecución.</td> 
    </tr>
  </tbody>
</table>

#### Obtener un tipo de registro (V2)

Este módulo recupera un tipo de registro por su ID.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL ID de tipo de registro]</p>
      </td>
      <td>Introduzca o asigne el ID del tipo de registro que desea recuperar.</td> 
    </tr>
  </tbody>
</table>

#### Obtener tipos de registros (V2)

Este módulo recupera una lista de tipos de registros disponibles en un espacio de trabajo determinado.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>Seleccione el espacio de trabajo para el que desea recuperar los tipos de registro.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Número máximo de tipos de registro devueltos]</p>
      </td>
      <td>Introduzca o asigne el número máximo de tipos de registro que devolverá el módulo durante un ciclo de ejecución.</td> 
    </tr>
  </tbody>
</table>

#### Actualización de un tipo de registro (V2)

Este módulo actualiza un tipo de registro.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>Seleccione el espacio de trabajo en el que desea actualizar un tipo de registro.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>Seleccione el espacio de trabajo en el que desea actualizar un tipo de registro.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Nombre para mostrar</p>
      </td>
      <td>Introduzca o asigne un nombre para el tipo de registro.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Descripción</p>
      </td>
      <td>Introduzca o asigne una descripción para el tipo de registro.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>ID del campo principal</p>
      </td>
      <td>Introduzca o asigne el ID del campo que se utiliza como título del tipo de registro.</td> 
    </tr>
     <tr>
      <td role="rowheader">
        <p>Icono</p>
      </td>
      <td>Asigne el icono que desee utilizar para este tipo de registro.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Color</p>
      </td>
      <td>Seleccione el color que desee utilizar para representar el nuevo tipo de registro</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Vinculable con Workspace ID</p>
      </td>
      <td>Para cada área de trabajo a la que desee que este tipo de registro pueda vincularse, haga clic en <b>Agregar elemento</b> e introduzca el identificador del área de trabajo.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Vinculable con Workspace ID &gt; Sobrescribir</p>
      </td>
      <td>Seleccione si desea reemplazar los espacios de trabajo existentes por los del módulo. Si no es así, los espacios de trabajo del módulo se añaden a la lista existente de espacios de trabajo.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Autorizado para crear un tipo de registro dinámico</p>
      </td>
      <td>Para cada sujeto autorizado para crear tipos de registros dinámicos a partir de este tipo de registro, haga clic en <b>Agregar elemento</b> e introduzca el tipo y el identificador del sujeto.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Autorizado para crear un tipo de registro dinámico &gt; Sobrescribir</p>
      </td>
      <td>Seleccione si desea reemplazar los temas existentes por los del módulo. Si no es así, los asuntos del módulo se añaden a la lista de asuntos existente.</td> 
    </tr>
  </tbody>
</table>



### Registros (V2)

* [Crear un registro](#create-a-record-v2)
* [Eliminación de un registro](#delete-a-record-v2)
* [Obtener un registro](#get-a-record-v2)
* [Obtener registros por tipo de registro](#get-records-by-record-type-v2)
* [Mover registros](#move-records-v2)
* [Búsqueda de registros](#search-records-v2)
* [Actualizar un registro](#update-a-record-v2)

#### Creación de un registro (V2)

Esta acción crea un único registro en Workfront Planning.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>Seleccione el espacio de trabajo en el que desea crear un registro.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>Seleccione el tipo de registro que desea crear.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Otros campos</p>
      </td>
      <td>Introduzca los valores que desea que tenga el nuevo registro. Estos campos se basan en el tipo de registro seleccionado y son exclusivos de su organización de Workfront Planning.</td> 
    </tr>
  </tbody>
</table>

#### Eliminación de un registro (V2)

Este módulo de acción elimina un único registro, especificado por ID.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record ID]</p>
      </td>
      <td>Introduzca o asigne el ID del registro que desea eliminar.</td> 
    </tr>
  </tbody>
</table>

#### Obtener un registro (V2)

Este módulo de acción recupera un registro, especificado por su ID.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL ID de espacio de trabajo]</p>
      </td>
      <td>Introduzca o asigne el ID del registro que desea recuperar.</td> 
    </tr>
  </tbody>
</table>

#### Obtención de registros por tipo de registro (V2)

Este módulo recupera una lista de todos los registros del tipo de registro dado.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>Seleccione el espacio de trabajo que contiene los registros que desea recuperar.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>Seleccione el tipo de registro que desea devolver.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Maximum number of returned records]</p>
      </td>
      <td>Introduzca o asigne el número máximo de registros que devolverá el módulo durante un ciclo de ejecución.</td> 
    </tr>
  </tbody>
</table>

#### Movimiento de registros (V2)

Este módulo reordena uno o más registros dentro de un tipo de registro especificando dónde colocarlos.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>Seleccione el espacio de trabajo que contiene los registros que desea mover.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>Seleccione el tipo de registro que desea mover.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>Seleccione el espacio de trabajo que contiene los registros que desea mover.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>Seleccione el espacio de trabajo que contiene los registros que desea mover.</td> 
    </tr>
  </tbody>
</table>

#### Buscar registros (V2)

Devolver registros según los criterios especificados

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>Seleccione el espacio de trabajo que contiene los registros que desea recuperar.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>Seleccione el tipo de registro que contiene los registros que desea recuperar.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Other fields]</p>
      </td>
      <td>Para cada campo por el que desee filtrar, introduzca el operador y el valor para ese campo. Estos campos se basan en el tipo de registro seleccionado y son exclusivos de su organización de Workfront Planning.</td> 
    </tr>
  </tbody>
</table>

#### Actualización de un registro (V2)

Este módulo actualiza el registro especificado.



<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>Seleccione el espacio de trabajo que contiene el registro que desea actualizar.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL ID de tipo de registro]</p>
      </td>
      <td>Seleccione el tipo de registro que desee actualizar.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record ID]</p>
      </td>
      <td>Introduzca o asigne el ID del registro que desea actualizar.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Other fields]</p>
      </td>
      <td>Introduzca valores para otros campos. Los campos disponibles dependen del registro seleccionado.</td> 
    </tr>
  </tbody>
</table>


### Campos (V2)

* [Creación de un campo](#create-a-field-v2)
* [Eliminación de un campo](#delete-a-field-v2)
* [Obtener un campo](#get-a-field-v2)
* [Obtener campos por tipo de registro](#get-fields-by-record-type-v2)
* [Actualizar un campo](#update-a-field-v2)

#### Creación de un campo (V2)

Este módulo de acción crea un nuevo campo en el tipo de registro especificado.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>Seleccione el espacio de trabajo en el que desea crear un campo.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>Seleccione el tipo de registro para el que desea crear un campo.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Nombre para mostrar</p>
      </td>
      <td>Introduzca o asigne un nombre para el nuevo campo.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Descripción</p>
      </td>
      <td>Introduzca o asigne una descripción para el nuevo campo.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Tipo de campo</p>
      </td>
      <td>Seleccione el tipo de datos del campo.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Otros campos</p>
      </td>
      <td>Pueden estar disponibles otros campos específicos del tipo de campo seleccionado. Rellene los valores de estos campos.</td> 
    </tr>
  </tbody>
</table>

#### Eliminación de un campo (V2)

Este módulo de acción elimina un solo campo, especificado por ID.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Field ID]</p>
      </td>
      <td>Introduzca o asigne el ID del campo que desea eliminar.</td> 
    </tr>
  </tbody>
</table>

#### Obtener un campo (V2)

Este módulo recupera un campo por su ID.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Field ID]</p>
      </td>
      <td>Introduzca o asigne el ID del campo que desea recuperar.</td> 
    </tr>
  </tbody>
</table>

#### Obtener campos por tipo de registro (V2)

Este módulo recupera una lista de campos para un tipo de registro específico.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>Seleccione el espacio de trabajo que contiene los campos que desea devolver.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>Seleccione el tipo de registro para el que desea devolver campos.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Número máximo de campos devueltos]</p>
      </td>
      <td>Introduzca o asigne el número máximo de campos que devolverá el módulo durante un ciclo de ejecución.</td> 
    </tr>
  </tbody>
</table>

#### Actualización de un campo (V2)

Este módulo actualiza parcialmente un campo por su ID.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Tipo de recurso]</p>
      </td>
      <td>Seleccione el tipo de recurso que contiene el campo que desea actualizar.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Field ID]</p>
      </td>
      <td>Seleccione el campo que desea actualizar.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Nombre para mostrar]</p>
      </td>
      <td>Introduzca o asigne un nombre para el campo.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Description]</p>
      </td>
      <td>Introduzca o asigne una descripción para el campo.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Otros parámetros]</p>
      </td>
      <td>Introduzca valores para otros parámetros de campo. Los parámetros disponibles dependen del campo seleccionado.</td> 
    </tr>
  </tbody>
</table>


### Vistas (V2)

* [Creación de una vista](#create-a-view-v2)
* [Eliminación de una vista](#delete-a-view-v2)
* [Obtener una vista](#get-a-view-v2)
* [Obtener vistas por tipo de registro](#get-views-by-record-type-v2)
* [Actualización de una vista](#update-a-view-v2)

#### Creación de una vista (V2)

Este módulo de acción crea una nueva vista para el tipo de registro seleccionado.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>Seleccione el espacio de trabajo en el que desea crear una vista.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>Seleccione el tipo de registro para el que desea crear una vista.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Nombre de la vista</p>
      </td>
      <td>Introduzca o asigne un nombre para la nueva vista.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Tipo de vista</p>
      </td>
      <td>Seleccione si la nueva vista es una vista de tabla, de escala de tiempo o de calendario.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Campo de fecha de inicio</p>
      </td>
      <td>Si la vista será una vista de escala de tiempo o de calendario, seleccione el campo que utilizará la vista para colocar el registro en la escala de tiempo.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Campo Fecha de finalización.</p>
      </td>
      <td>Si la vista será una vista de escala de tiempo o de calendario, seleccione el campo que la vista utilizará para determinar la fecha de finalización de la escala de tiempo.</td> 
    </tr>
  </tbody>
</table>

#### Eliminación de una vista (V2)

Este módulo de acción elimina una sola vista, especificada por el ID.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Ver ID]</p>
      </td>
      <td>Introduzca o asigne el ID de la vista que desea eliminar.</td> 
    </tr>
  </tbody>
</table>

#### Obtener una vista (V2)

Este módulo recupera una vista por su ID.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Ver ID]</p>
      </td>
      <td>Introduzca o asigne el ID de la vista que desea recuperar.</td> 
    </tr>
  </tbody>
</table>

#### Obtener vistas por tipo de registro (V2)

Este módulo recupera una lista de vistas para el tipo de registro específico.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>Seleccione el espacio de trabajo que contiene las vistas que desea recuperar.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>Seleccione el tipo de registro que contiene las vistas que desea recuperar.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Número máximo de vistas devueltas]</p>
      </td>
      <td>Introduzca o asigne el número máximo de vistas que devolverá el módulo durante un ciclo de ejecución.</td> 
    </tr>
  </tbody>
</table>

#### Actualización de una vista (V2)

Este módulo de acción actualiza la vista especificada.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>Seleccione el espacio de trabajo en el que desea actualizar una vista.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>Seleccione el tipo de registro para el que desea actualizar una vista.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Identificador de la vista</p>
      </td>
      <td>Seleccione la vista que desee actualizar.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Nombre de la vista</p>
      </td>
      <td>Introduzca o asigne un nombre para la nueva vista.</td> 
    </tr>
  </tbody>
</table>

### Permisos (V2)

* [Descartar solicitudes de acceso](#dismiss-access-requests-v2)
* [Obtener todos los miembros y sus funciones para un recurso](#get-all-members-and-their-roles-for-a-resource-v2)
* [Obtener los permisos efectivos del usuario actual de un recurso](#get-the-current-users-effective-permissions-on-a-resource-v2)
* [Enumeración de solicitudes de acceso pendientes para un recurso](#list-pending-access-requests-for-a-resource-v2)
* [Solicitud de acceso a un recurso](#request-access-to-a-resource-v2)

#### Descartar solicitudes de acceso (V2)

Este módulo de acción descarta una o más solicitudes de acceso, especificadas por el ID.



<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Tipo de recurso]</p>
      </td>
      <td>Introduzca o asigne el ID de la Workspace que desea eliminar.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Id. de recurso]</p>
      </td>
      <td>Introduzca o asigne el ID del recurso para el que desea descartar las solicitudes de acceso.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL ID de solicitud]</p>
      </td>
      <td>Para cada solicitud de acceso que desee rechazar, haga clic en <b>Agregar elemento</b> e introduzca el identificador de la solicitud.</td> 
    </tr>
  </tbody>
</table>

#### Obtener todos los miembros y sus funciones para un recurso (V2)

Este módulo enumera todos los usuarios, grupos y equipos que tienen una relación de uso compartido explícita en el recurso. Las credenciales utilizadas en la conexión para este módulo deben tener permiso de administración en el recurso.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Tipo de recurso]</p>
      </td>
      <td>Seleccione el tipo de recurso para el que desea recuperar información.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Id. de recurso]</p>
      </td>
      <td>Introduzca o asigne el ID del recurso para el que desea recuperar información.</td> 
    </tr>
  </tbody>
</table>

#### Obtener los permisos efectivos del usuario actual de un recurso (V2)

Este módulo devuelve la vista, edición, eliminación y adición de permisos del usuario actual para un recurso determinado.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Tipo de recurso]</p>
      </td>
      <td>Seleccione el tipo de recurso para el que desea recuperar permisos.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Id. de recurso]</p>
      </td>
      <td>Introduzca o asigne el ID del recurso para el que desea recuperar permisos.</td> 
    </tr>
  </tbody>
</table>

#### Enumeración de solicitudes de acceso pendientes para un recurso (V2)

Este módulo devuelve todas las solicitudes de acceso pendientes del recurso determinado.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Tipo de recurso]</p>
      </td>
      <td>Seleccione el tipo de recurso para el que desea recuperar información.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Id. de recurso]</p>
      </td>
      <td>Introduzca o asigne el ID del recurso para el que desea recuperar información.</td> 
    </tr>
  </tbody>
</table>

#### Solicitud de acceso a un recurso (V2)

Este módulo crea o actualiza una solicitud de acceso para el usuario actual en el recurso determinado.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Tipo de recurso]</p>
      </td>
      <td>Seleccione el tipo de recurso para el que desea crear o actualizar una solicitud de acceso.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Id. de recurso]</p>
      </td>
      <td>Introduzca o asigne el ID del recurso para el que desea crear o actualizar una solicitud de acceso.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Message]</p>
      </td>
      <td>Introduzca o asigne el texto de un mensaje que desee incluir en la solicitud de acceso.</td> 
    </tr>
  </tbody>
</table>



### Otros (V2)

* [Obtener ID de autenticación de Workfront ID](#get-auth-id-from-workfront-id-v2)
* [Realizar una llamada API personalizada](#make-a-custom-api-call-v2)
* [Ver eventos](#watch-events-v2)

#### Obtener el ID de autenticación de Workfront ID (V2)

Este módulo toma un ID de usuario de Workfront y devuelve el ID de autorización coincidente que utiliza Planning.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL ID de usuario de Workfront]</p>
      </td>
      <td>Introduzca o asigne el ID de Workfront del usuario para el que desea recuperar un ID de autorización.</td> 
    </tr>
  </tbody>
</table>

#### Realizar una llamada de API personalizada (V2)&lt;table

Este módulo realiza una llamada personalizada a la API de Workfront Planning.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su aplicación de Workfront a Workfront Fusion, consulte <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Conectar Workfront a Workfront Fusion</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td> <p>Introduzca una ruta relativa a <code> https://&lt;WORKFRONT_DOMAIN>/maestro/api/.</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL API Version]</td> 
   <td>Seleccione la versión de la API de Workfront que desea que utilice el módulo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada de la API. Para obtener más información, consulte los <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de petición HTTP en Adobe Workfront Fusion</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar. Determina el tipo de contenido de la petición.</p> <p>Por ejemplo:<code> {"Content-type":"application/json"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Añada la consulta para la llamada de API en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"name":"something-urgent"}</code></p> <p>Sugerencia: Le recomendamos que envíe información a través del cuerpo de JSON en lugar de como parámetros de consulta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### Ver eventos (V2)

Este módulo de déclencheur inicia un escenario cuando se crea, actualiza o elimina un registro, tipo de registro o espacio de trabajo en Workfront Planning.

>[!IMPORTANT]
>
>Puede editar este módulo más adelante, que editará el webhook.
>
>Tenga en cuenta lo siguiente al actualizar un webhook:
>
>* Las suscripciones a eventos de Workfront tratan el webhook editado como una suscripción nueva. El historial de suscripción de eventos no se conserva para la configuración de ganchos web anterior, ya que se considera una suscripción de evento independiente.
>* Es posible que el cambio de la suscripción de evento antigua a la nueva no esté perfectamente sincronizado. Por lo tanto, es posible recibir un evento dos veces (si la nueva suscripción empieza a ejecutarse antes de que la anterior se detenga) o perderse un evento (si la antigua suscripción se detiene antes de que la nueva comience a ejecutarse).
>
>Para obtener más información sobre cómo editar los enlaces web, consulte [Editar enlaces web](/help/workfront-fusion/manage-scenarios/edit-webhooks.md).

>[!NOTE]
>
>A partir del 23 de agosto de 2026, Fusion habilitará la seguridad basada en authToken de forma predeterminada para todos los módulos de Workfront Planning > Ver evento, incluidos los existentes.


<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Webhook]</td>
      <td>Seleccione el webhook que desee utilizar o haga clic en Agregar para crear uno nuevo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Object type]</td>
      <td>Seleccione si desea ver registros, tipos de registros o espacios de trabajo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Objetos que ver]</td>
      <td>Seleccione si desea ver registros nuevos, registros actualizados, registros nuevos y actualizados o registros eliminados.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Tipo de configuración]</td>
      <td>Seleccione si desea una configuración simple o avanzada. <p>Para obtener más información sobre la configuración avanzada, consulte <a href="#example-of-advanced-logic-in-the-watch-events-module" class="MCXref xref" >Ejemplo de lógica avanzada en el módulo de eventos de inspección</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL State]</td>
      <td>Seleccione si desea ver el estado antiguo o el nuevo.<ul><li><p><b>[!UICONTROL New state]</b></p><p>Active un escenario cuando el registro cambia <b>a </b> un valor determinado.</p></li><li><p><b>[!UICONTROL Old state]</b></p><p>Activa un escenario cuando el registro cambia <b>de </b> un valor determinado.</p></li></ul></td> 
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>Si observa registros, seleccione el Workspace que desee ver para ver los registros.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Record type]</td>
      <td>Si inspecciona registros, seleccione el tipo de registro que desee inspeccionar.</td>
    </tr>
    </tr>
    <tr data-mc-conditions=""> 
      <td> <p>[!UICONTROL Events filters]</p> </td> 
      <td> <p>Puede establecer filtros para ver solo los registros que cumplan los criterios seleccionados.</p> <p>Para cada filtro, introduzca el campo que desea que evalúe el filtro, el operador y el valor que desea que permita el filtro. Puede utilizar más de un filtro añadiendo reglas AND.</p> <p>Nota: Los filtros no se pueden editar en los webhooks de Workfront existentes. Para configurar diferentes filtros para suscripciones a eventos de Workfront, elimine el webhook actual y cree uno nuevo.</p> <p>Para obtener más información sobre los filtros de eventos, consulte <a href="/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#event-subscription-filters-in-the-workfront--watch-events-modules" class="MCXref xref">Filtros de suscripción de eventos en Workfront &gt; Módulos de [!UICONTROL Watch Events]</a> en el artículo Módulos de Workfront.</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Objetos que ver]</td>
      <td>Seleccione si desea ver las nuevas. registros actualizados, nuevos y actualizados o eliminados.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Excluir actualizaciones realizadas por esta conexión]</p>
      </td>
      <td>Habilite esta opción para evitar que el escenario se active cuando la conexión utilizada por este módulo realice un cambio. Esto evita que se active otra instancia del escenario si este realiza una acción de activación.</td> 
    </tr>
  </tbody>
</table>

Para ver un ejemplo de uso de lógica avanzada en este módulo, vea [Ejemplo de lógica avanzada en el módulo de eventos de inspección](#example-of-advanced-logic-in-the-watch-events-module).






## [!DNL Adobe Workfront Planning] módulos de versión 1 y sus campos

>[!IMPORTANT]
>
>Los módulos de esta sección pertenecen al conector Workfront Planning V1.
>Para ver los módulos del conector Workfront Planning V2, consulte [[!DNL Adobe Workfront Planning] Módulos de la versión 2 y sus campos](#adobe-workfront-planning-version-2-modules-and-their-fields).

Al configurar los módulos de Workfront Planning, Workfront Fusion muestra los campos que se indican a continuación. Junto con estos, podrían mostrarse campos adicionales de Workfront, según factores como el nivel de acceso en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, consulte [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).


![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Activadores](#triggers)
* [Acciones](#actions)
* [Búsquedas](#searches)
* [Sin categoría](#uncategorized)

### Activadores

#### Ver eventos

Este módulo de déclencheur inicia un escenario cuando se crea, actualiza o elimina un registro, tipo de registro o espacio de trabajo en Workfront Planning.

>[!IMPORTANT]
>
>Puede editar este módulo más adelante, que editará el webhook.
>
>Tenga en cuenta lo siguiente al actualizar un webhook:
>
>* Las suscripciones a eventos de Workfront tratan el webhook editado como una suscripción nueva. El historial de suscripción de eventos no se conserva para la configuración de ganchos web anterior, ya que se considera una suscripción de evento independiente.
>* Es posible que el cambio de la suscripción de evento antigua a la nueva no esté perfectamente sincronizado. Por lo tanto, es posible recibir un evento dos veces (si la nueva suscripción empieza a ejecutarse antes de que la anterior se detenga) o perderse un evento (si la antigua suscripción se detiene antes de que la nueva comience a ejecutarse).
>
>Para obtener más información sobre cómo editar los enlaces web, consulte [Editar enlaces web](/help/workfront-fusion/manage-scenarios/edit-webhooks.md).

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Webhook]</td>
      <td>Seleccione el webhook que desee utilizar o haga clic en Agregar para crear uno nuevo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Object type]</td>
      <td>Seleccione si desea ver registros, tipos de registros o espacios de trabajo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL State]</td>
      <td>Seleccione si desea ver el estado antiguo o el nuevo.<ul><li><p><b>[!UICONTROL New state]</b></p><p>Active un escenario cuando el registro cambia <b>a </b> un valor determinado.</p></li><li><p><b>[!UICONTROL Old state]</b></p><p>Activa un escenario cuando el registro cambia <b>de </b> un valor determinado.</p></li></ul></td> 
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>Si observa registros, seleccione el Workspace que desee ver para ver los registros.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Record type]</td>
      <td>Si inspecciona registros, seleccione el tipo de registro que desee inspeccionar.</td>
    </tr>
    </tr>
    <tr data-mc-conditions=""> 
      <td> <p>[!UICONTROL Events filters]</p> </td> 
      <td> <p>Puede establecer filtros para ver solo los registros que cumplan los criterios seleccionados.</p> <p>Para cada filtro, introduzca el campo que desea que evalúe el filtro, el operador y el valor que desea que permita el filtro. Puede utilizar más de un filtro añadiendo reglas AND.</p> <p>Nota: Los filtros no se pueden editar en los webhooks de Workfront existentes. Para configurar diferentes filtros para suscripciones a eventos de Workfront, elimine el webhook actual y cree uno nuevo.</p> <p>Para obtener más información sobre los filtros de eventos, consulte <a href="/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#event-subscription-filters-in-the-workfront--watch-events-modules" class="MCXref xref">Filtros de suscripción de eventos en Workfront &gt; Módulos de [!UICONTROL Watch Events]</a> en el artículo Módulos de Workfront.</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Objetos que ver]</td>
      <td>Seleccione si desea ver las nuevas. registros actualizados, nuevos y actualizados o eliminados.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Excluir actualizaciones realizadas por esta conexión]</p>
      </td>
      <td>Habilite esta opción para evitar que el escenario se active cuando la conexión utilizada por este módulo realice un cambio. Esto evita que se active otra instancia del escenario si este realiza una acción de activación.</td> 
    </tr>
  </tbody>
</table>

Para ver un ejemplo de uso de lógica avanzada en este módulo, vea [Ejemplo de lógica avanzada en el módulo de eventos de inspección](#example-of-advanced-logic-in-the-watch-events-module).

### Acciones

* [Eliminación de un tipo de registro](#delete-a-record-type)
* [Realizar una llamada de IA personalizada](#make-a-custom-api-call)

#### Eliminación de un tipo de registro

Este módulo de acción elimina un solo tipo de registro en Workfront Planning por su ID.

>[!WARNING]
>
>Al eliminar un tipo de registro en Workfront Planning también se eliminan todos los registros de la tabla de tipo de registro.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL ID de tipo de registro]</p>
      </td>
      <td>Introduzca o asigne el ID del tipo de registro que desea eliminar.</td> 
    </tr>
  </tbody>
</table>

#### Realizar una llamada API personalizada

Este módulo realiza una llamada de API personalizada a la API de [!DNL Adobe Workfront Planning].

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL URL]</p>
      </td>
      <td>
        <p>Introduzca una ruta relativa a <code>https://(YOUR_WORKFRONT_DOMAIN)/maestro/api/</code></p>
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
        <p>Para cada par clave/valor que desee agregar a la cadena de consulta, haga clic en <b>Agregar elemento</b> e introduzca la clave y el valor.</p>
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


### Búsquedas

#### Búsqueda de registros

Este módulo de acción recupera una lista de registros en función de los criterios especificados.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>Introduzca o asigne el Workspace que contiene los registros que desea buscar.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>Seleccione el tipo de registro que desea buscar.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record Fields]</p>
      </td>
      <td>Para cada campo que desee utilizar en la búsqueda, localice ese campo, seleccione el operador e introduzca o asigne el valor que desee buscar. Los campos están disponibles en función del tipo de registro seleccionado.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Condición para filtros]</p>
      </td>
      <td>Seleccione la condición de los filtros:<ul><li><b>Y</b><p>El módulo devuelve registros que cumplen <b>todos</b> los valores de campo que seleccionó.</p></li><li><b>O</b><p>El módulo devuelve registros que cumplen <b>cualquier</b> de los valores de campo que seleccionó.</p></li></ul></td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Limit]</p>
      </td>
   <td> <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p> </td> 
    </tr>
  </tbody>
</table>


### Sin categoría


#### Crear un registro

Esta acción crea un único registro en Workfront Planning.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL ID de tipo de registro]</p>
      </td>
      <td>Introduzca o asigne el tipo de registro que desea crear. Los tipos de registro disponibles se basan en su cuenta de Workfront Planning.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Otros campos</p>
      </td>
      <td>Introduzca los valores que desea que tenga el nuevo registro. Estos campos se basan en el tipo de registro seleccionado.</td> 
    </tr>
    <tr>
  </tbody>
</table>

### Eliminación de un registro

Este módulo de acción elimina el registro especificado en Workfront Planning.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record ID]</p>
      </td>
      <td>Introduzca o asigne el ID del registro que desea eliminar.</td> 
    </tr>
  </tbody>
</table>

### Obtener un registro

Este módulo de acción recupera un único registro de [!DNL Adobe Workfront Planning], especificado por su identificador.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Record ID]</td>
      <td>Introduzca o asigne el ID del registro que desea recuperar.</td>
    </tr>
  </tbody>
</table>

### Obtener registros por tipo de registro

Este módulo de acción recupera todos los registros del tipo especificado.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>Seleccione o asigne el espacio de trabajo que contiene los registros que desea recuperar.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Record type]</td>
      <td>Seleccione el tipo de registro que desea recuperar.</td>
    </tr>
    <!--
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Maximum number of returned records]</p>
      </td>
      <td>Enter or map the maximum number of records you want the module to return during each scenario execution cycle.</td>
    </tr>
    -->
  </tbody>
</table>

### Obtener tipos de registros

Este módulo de acción recupera una lista de tipos de registro en una cuenta de [!DNL Adobe Workfront Planning].

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>Seleccione o asigne el espacio de trabajo que contiene los tipos de registro que desea recuperar.</td>
    </tr>
  </tbody>
</table>

### Actualizar registro

Esta acción actualiza un único registro en Workfront Planning.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Para obtener instrucciones sobre cómo crear una conexión con [!DNL Adobe Workfront Planning], consulte <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Crear una conexión con [!DNL Adobe Workfront Planning]</a> en este artículo.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record ID]</p>
      </td>
      <td>Introduzca o asigne el tipo de registro que desea actualizar Los tipos de registro disponibles se basan en su cuenta de Workfront Planning.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Otros campos</p>
      </td>
      <td>Introduzca los nuevos valores que desea que tenga el registro. Estos campos se basan en el tipo de registro seleccionado.</td> 
    </tr>
    <tr>
  </tbody>
</table>


## Usar JSONata para el desglose legible `record-types`

La siguiente expresión JSONata crea un resultado legible en lenguaje natural de la consulta de Planning que le proporciona el desglose de tipos de registros. Esto hace que el nombre del tipo de registro, los nombres de campo y los nombres de opciones de campo (cuando corresponda) sean legibles por un nombre y mantiene el resto de la estructura intacta.

```
(
    $s0 := ({"data":$ ~> | fields | {"options":(options){name:$}} |});
    $s1 := ({"data":$s0.data ~> | **.fields | {"options_name":(options.*){displayName:$}} | });
    $s2 := $s1 ~> | data | {"fields":(fields){displayName:$}} |; 
    $s2.data{displayName:$}
)
```

Para obtener información sobre el uso de módulos JSONata, consulte [módulos JSONata](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/jsonata-module.md).

## Ejemplo de lógica avanzada en el módulo Ver eventos

Este es un ejemplo del formato que adopta la lógica avanzada al utilizar el módulo Workfront Planning > Ver eventos.

```
[
  {
    "fieldName": "recordTypeId",
    "fieldValue": "Rt68c886502d4b5554ee80896b",
    "comparison": "eq",
    "state": "newState"
  },
  {
    "fieldName": "data",
    "fieldValue": {
      "F68c886502d4b5554ee808975": "planning"
    },
    "comparison": "eq",
    "state": "newState"
  },
  {
    "fieldName": "data",
    "fieldValue": {
      "F68c886502d4b5554ee808975": "active"
    },
    "comparison": "eq",
    "state": "newState"
  }
]
```

Tenga en cuenta lo siguiente al utilizar la lógica avanzada en el módulo Ver evento:

* La primera entrada `"fieldvalue":` es el identificador de tipo de registro de planificación extraído de la dirección URL. En este ejemplo, el identificador del tipo de registro de planificación es `Rt68c886502d4b5554ee80896b`.
* Los datos de Planning se devuelven dentro de una matriz denominada `data `, que aparece en este ejemplo como `"fieldName": "data"`.
* Los nombres de los campos de planificación se devuelven como identificadores que comienzan por `F`.
* Dado que este ejemplo está evaluando con un conector de filtro `OR`, tiene dos entradas para el mismo campo (`F68c886502d4b5554eec808975`).  Las dos opciones desplegables con las que filtra el módulo son `"planning"` y `"active"`.

