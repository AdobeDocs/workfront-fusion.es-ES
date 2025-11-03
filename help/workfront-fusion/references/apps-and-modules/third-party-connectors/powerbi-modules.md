---
title: Módulos de Power BI
description: Adobe Workfront Fusion requiere una licencia Adobe Workfront Fusion y de Adobe Workfront.
author: Becky
feature: Workfront Fusion
exl-id: 73eb70e1-3f3d-419d-9cde-3ec3cda224f8
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '2606'
ht-degree: 91%

---

# Módulos de [!DNL Power BI]

[!DNL Power BI] es una aplicación que le permite visualizar y presentar datos a las partes interesadas. Puede recopilar datos de una variedad de fuentes.

>[!NOTE]
>
>Workfront Fusion no es una fuente de datos. Aunque Workfront Fusion puede crear y utilizar fuentes de datos, no almacena sus datos.


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

## Información de la API de Microsoft Power BI

El conector Power BI de Microsoft utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Dirección URL base</td> 
   <td> https://api.powerbi.com/v1.0</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> Versión 1.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.0.2</td> 
  </tr>
 </tbody> 
 </table>

## Módulos de [!DNL Power BI] y sus campos

Al configurar [!DNL Power BI], Workfront Fusion muestra los campos que se indican a continuación. Además, es posible que aparezcan otros campos en función de factores como el nivel de acceso a la aplicación o al servicio. Un título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, consulte [Asignar información de un módulo a otro en Adobe Workfront Fusion](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Paneles de control](#dashboards)
* [Informes](#reports)
* [Conjunto de datos](#dataset)
* [Aplicaciones](#apps)
* [Otro](#other)

### Paneles de control

* [Crear un tablero](#create-a-dashboard)
* [Obtener un panel](#get-a-dashboard)
* [Obtener un mosaico del panel](#get-a-dashboard-tile)
* [Mostrar mosaicos del panel](#list-dashboard-tiles)
* [Paneles de lista](#list-dashboards)

#### [!UICONTROL Crear un panel de control]

Este módulo de acción crea un nuevo panel de control.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Name]</td>
      <td>Introduzca o asigne un nombre para el panel de control.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Group ID]  </td>
      <td>Seleccione o asigne el ID del grupo propietario del nuevo panel de control.</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Conseguir un panel de control]

Este módulo de acción recupera los metadatos de un panel de control especificado.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Enter a Dashboard ID]</td>
      <td>
        <p>Seleccione o asigne la opción para elegir el panel de control para el que desea recuperar los metadatos.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Dashboard ID]</td>
      <td>
        <p>Introduzca o asigne el ID del panel de control para el que desea recuperar los metadatos.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Group ID]  </td>
      <td>Seleccione o asigne el ID del grupo propietario de los paneles de control de los que desea recuperar metadatos.</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Obtener un mosaico del panel de control]

Este módulo de acción recupera los metadatos de un mosaico de panel de control especificado.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Enter a Dashboard ID]</td>
      <td>
        <p>Seleccione o asigne la opción para elegir los detalles del panel de control que desea recuperar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Dashboard ID]</td>
      <td>
        <p>Introduzca o asigne el ID del panel de control cuyos detalles desea recuperar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Tile ID]</td>
      <td>Escriba o asigne el identificador del mosaico de [!DNL Power BI] cuyos detalles desea recuperar.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Group ID]  </td>
      <td>Seleccione o asigne el ID del grupo propietario del mosaico que desea recuperar.</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Lista de mosaicos del panel de control]

Este módulo de búsqueda recupera una lista de mosaicos del panel de control.

<table>
<col/>
<col/>
<tbody>
  <tr>
    <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Enter a Dashboard ID]</td>
    <td>
      <p>Seleccione o asigne la opción para elegir el panel de control cuyos mosaicos desee especificar.</p>
    </td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Dashboard ID]</td>
    <td>
      <p>Introduzca o asigne el ID del panel de control que contiene los mosaicos que desea especificar.</p>
    </td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Group ID]  </td>
    <td>Seleccione o asigne el ID del grupo propietario de los paneles de control que contienen los mosaicos que desea especificar.</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Limit]  </td>
    <td>
      <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p>
    </td>
  </tr>
</tbody>
</table>

#### [!UICONTROL Paneles de lista]

Este módulo de búsqueda recupera una lista de paneles de control.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Group ID]  </td>
      <td>
        <p>Seleccione o asigne el ID del grupo propietario de los paneles de control que desee enumerar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]  </td>
      <td>
        <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p>
      </td>
    </tr>
  </tbody>
</table>

### Informes

* [Copia de un informe](#copy-a-report)
* [Eliminar un informe](#delete-a-report)
* [Obtener un informe](#get-a-report)
* [Enumerar informes](#list-reports)

#### [!UICONTROL Copiar un informe]

Este módulo de acción copia un informe existente.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Enter a Report ID]</td>
      <td>
        <p>Seleccione o asigne la opción para elegir el informe que desea copiar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Report ID]</td>
      <td>
        <p>Introduzca o asigne el ID del informe que desea copiar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Group ID]  </td>
      <td>Seleccione o asigne el ID del grupo propietario del informe que desea copiar.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL New Copied Report Name]</td>
      <td>Introduzca o asigne un nombre para el nuevo informe.</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Eliminar un informe]

Este módulo de acción elimina un informe.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Enter a Report ID]</td>
      <td>
        <p>Seleccione o asigne la opción para elegir el informe que desea eliminar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Report ID]</td>
      <td>
        <p>Introduzca o asigne el ID del informe que desea eliminar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Group ID]  </td>
      <td>Seleccione o asigne el ID del grupo propietario del informe que desea eliminar.</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Obtener un informe]

Este módulo de acción recupera los metadatos de un informe especificado.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Enter a Report ID]</td>
      <td>
        <p>Seleccione o asigne la opción para elegir el informe cuyos metadatos desea recuperar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Report ID]</td>
      <td>
        <p>Introduzca o asigne el ID del informe cuyos metadatos desea recuperar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Group ID]  </td>
      <td>Seleccione o asigne el ID del grupo propietario del informe cuyos metadatos desea recuperar.</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Lista de informes]

Este módulo de búsqueda recupera una lista de informes.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Group ID]  </td>
      <td>
        <p>Seleccione o asigne el ID del grupo propietario de los informes que desea enumerar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]  </td>
      <td>
        <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p>
      </td>
    </tr>
  </tbody>
</table>


### Conjunto de datos

* [Agregar o eliminar filas en una tabla de conjunto de datos](#add-or-delete-rows-in-a-dataset-table)
* [Crear un conjunto de datos](#create-a-dataset)
* [Eliminar un conjunto de datos](#delete-a-dataset)
* [Obtener un conjunto de datos](#get-a-dataset)
* [Enumerar conjuntos de datos](#list-datasets)
* [Actualizar un conjunto de datos](#refresh-a-dataset)

#### [!UICONTROL Añadir o eliminar filas en una tabla de conjunto de datos]

Este módulo de acción añade o elimina filas de una tabla de conjunto de datos de inserción especificada.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Enter a table]</td>
      <td>Seleccione o asigne la opción para seleccionar el conjunto de datos que contiene la tabla que desea ajustar.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Dataset ID]</td>
      <td>Introduzca o asigne el ID del conjunto de datos que contiene las filas que desea añadir o eliminar.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Table Name]  </td>
      <td>
        <p>Escriba o asigne el nombre de la tabla que contiene las filas que desea añadir o eliminar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Group ID]  </td>
      <td>Introduzca o asigne el ID del grupo propietario del conjunto de datos.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Select the Action]</td>
      <td>
        <p>Seleccione o asigne la acción que desea realizar.</p>
        <ul>
          <li>
            <p>[!UICONTROL Add rows]</p>
          </li>
          <li>
            <p>[!UICONTROL Delete All Rows]</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Rows]</td>
      <td>
        <p>Añada los campos de la fila.</p>
        <ul>
          <li>
            <p><b>[!UICONTROL Key]</b>
            </p>
            <p>Introduzca o asigne el nombre de la clave.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Field Type]</b>
            </p>
            <p>Seleccione o asigne el tipo de campo:</p>
            <ul>
              <li>
                <p>Booleano</p>
              </li>
              <li>
                <p>Fecha</p>
              </li>
              <li>
                <p>Texto</p>
              </li>
              <li>
                <p>Número</p>
              </li>
            </ul>
          </li>
          <li>
            <p>[!UICONTROL Value]</p>
            <p>Introduzca o asigne el valor clave.</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Crear un conjunto de datos]

Este módulo de acción crea un nuevo conjunto de datos.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Name]</td>
      <td>Introduzca o asigne un nombre para el conjunto de datos.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Group ID]  </td>
      <td>Seleccione o asigne el ID del grupo que será el propietario del nuevo conjunto de datos.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Default Mode]</td>
      <td>
        <p>Seleccione o asigne el modo predeterminado para el conjunto de datos:</p>
        <ul>
          <li>
            <p><b>[!UICONTROL As Azure]</b>: un conjunto de datos con una conexión activa a [!DNL Azure Analysis Service]</p>
          </li>
          <li>
            <p><b>[!UICONTROL As on Prem]</b>: un conjunto de datos con una conexión activa al servicio [!DNL On-premise Analysis]</p>
          </li>
          <li>
            <p><b>[!DNL Push]</b>: conjunto de datos que permite el acceso mediante programación para insertar datos en [!DNL Power BI]</p>
          </li>
          <li>
            <p><b>[!DNL Push Streaming]</b>: conjunto de datos que admite la transmisión de datos y permite el acceso mediante programación para la inserción de datos en [!DNL Power BI]</p>
          </li>
          <li>
            <p><b>[!DNL Streaming]</b>: conjunto de datos que admite la transmisión de datos</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Tables]</td>
      <td>Añadir tablas al conjunto de datos. Para ver los campos, consulte <a href="#Table" class="MCXref_0">Campos de tabla</a></td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Data sources]</td>
      <td>Añada las fuentes de datos. Para ver los campos, consulte <a href="#Data" class="MCXref_0">Campos de las fuentes de datos</a>.</td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Default Retention Policy]  </td>
      <td>
        <p>Seleccione o asigne la directiva intencional para el conjunto de datos:</p>
        <ul>
          <li>
            <p>[!UICONTROL None]</p>
          </li>
          <li>
            <p>[!UICONTROL Basic FIFO]</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

##### Campos de tabla

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Name]</td>
      <td>
        <p>  Introduzca o asigne un nombre para la tabla.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Columns]</td>
      <td>
        <p>Añada las columnas:</p>
        <ul>
          <li>
            <p><b>[!UICONTROL Name]</b>
            </p>
            <p>Introduzca (asigne) un nombre de columna.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Data Type]</b>
            </p>
            <p>Seleccione o asigne el tipo de datos:</p>
            <ul>
              <li>
                <p>[!UICONTROL String]</p>
              </li>
              <li>
                <p>[!UICONTROL Integer]</p>
              </li>
              <li>
                <p>[!UICONTROL Boolean]</p>
              </li>
              <li>
                <p>[!UICONTROL Date Time]</p>
              </li>
            </ul>
          </li>
          <li>
            <p><b>[!UICONTROL Format String]</b>
            </p>
            <p>Introduzca (asigne) la cadena de formato.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Rows]</td>
      <td>Especifique o asigne detalles de la fila.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Measures]</td>
      <td>Añada la medida para las tablas.</td>
    </tr>
  </tbody>
</table>

##### Campos de fuentes de datos

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Database]  </td>
      <td>
        <p>Introduzca o asigne la base de datos que desea utilizar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Server]  </td>
      <td>
        <p>Introduzca o asigne el nombre del servidor que desea utilizar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]  </td>
      <td>
        <p>Introduzca o asigne la dirección URL que desea utilizar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Data source ID]</td>
      <td>
        <p>  Introduzca o asigne el ID de la fuente de datos.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Data source Type]  </td>
      <td>
        <p>Seleccione o asigne el tipo de fuente de datos. Ejemplo: SQL.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Gateway ID]  </td>
      <td>Introduzca o asigne el ID de la puerta de enlace que desea utilizar.</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Eliminar un conjunto de datos]

Este módulo de acción elimina un conjunto de datos.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Enter a Report ID]</td>
      <td>
        <p>Seleccione o asigne la opción para elegir el conjunto de datos que desea eliminar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Report ID]</td>
      <td>
        <p>Introduzca o asigne el ID del conjunto de datos que desea eliminar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Group ID]  </td>
      <td>Seleccione o asigne el ID del grupo propietario del conjunto de datos que desea eliminar.</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Obtener un conjunto de datos]

Este módulo de acción recupera los metadatos de un conjunto de datos especificado.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Enter a Report ID]</td>
      <td>
        <p>Seleccione o asigne la opción para elegir el informe cuyos metadatos desea recuperar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Report ID]</td>
      <td>
        <p>Introduzca o asigne el ID del conjunto de datos del que desea recuperar metadatos.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Group ID]  </td>
      <td>Seleccione o asigne el ID del grupo propietario del conjunto de datos para el que desea recuperar metadatos.</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Enumerar conjuntos de datos]

Este módulo de búsqueda recupera una lista de conjuntos de datos.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Group ID]  </td>
      <td>Seleccione o asigne el ID del grupo propietario del informe cuyos metadatos desea recuperar.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]</td>
      <td>
        <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Actualizar un conjunto de datos]

Este módulo de acción actualiza un conjunto de datos especificado.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Enter a dataset]</td>
      <td>Seleccione o asigne la opción para seleccionar el conjunto de datos que desea actualizar.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Dataset ID]</td>
      <td>Introduzca o asigne el ID del conjunto de datos que desea actualizar.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Table Name]  </td>
      <td>
        <p>Escriba o asigne el nombre de la tabla que contiene las filas que desea añadir o eliminar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Group ID]  </td>
      <td>Introduzca o asigne el ID del grupo propietario del conjunto de datos.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Notify Option]  </td>
      <td>
        <p>Seleccione o asigne la opción para notificar a:</p>
        <ul>
          <li>
            <p>[!UICONTROL Mail on Completion]</p>
          </li>
          <li>
            <p>[!UICONTROL Mail on Failure]</p>
          </li>
          <li>
            <p>[!UICONTROL No Notification]</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### Aplicaciones

* [Obtener una aplicación](#get-an-app)
* [Obtener el tablero de una aplicación](#get-an-apps-dashboard)
* [Obtener el informe de una aplicación](#get-an-apps-report)
* [Enumerar los paneles de la aplicación](#list-apps-dashboards)
* [Enumerar los informes de la aplicación](#list-apps-reports)
* [Enumerar aplicaciones](#list-apps)
* [Ver aplicaciones](#watch-apps)

#### [!UICONTROL Obtener una aplicación]

Este módulo de acción recupera los metadatos de una aplicación especificada.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL App ID]  </td>
      <td>
        <p>Seleccione o asigne el ID de la aplicación que desea recuperar.</p>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Obtener el panel de control de una aplicación]

Este módulo de acción recupera los metadatos del panel de control de una aplicación especificada.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL App ID]  </td>
      <td>
        <p>Seleccione o asigne el ID de la aplicación que contiene el panel de control que desea recuperar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Report ID]</td>
      <td>
        <p>  Seleccione o asigne el ID del panel de control que desea recuperar.</p>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Obtener el informe de una aplicación]

Este módulo de acción recupera los metadatos del informe de una aplicación especificada.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL App ID]  </td>
      <td>
        <p>Seleccione o asigne el ID de la aplicación que contiene el informe que desea recuperar.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Report ID]</td>
      <td>
        <p>  Seleccione o asigne el ID del informe que desea recuperar.</p>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Lista de aplicaciones]

Este módulo de búsqueda recupera una lista de todas las aplicaciones instaladas.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]  </td>
      <td>
        <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Lista de paneles de control de la aplicación]

Este módulo de búsqueda recupera una lista de paneles de control de una aplicación especificada.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL App ID]</td>
      <td>Seleccione o asigne el ID de la aplicación desde la que desea enumerar los paneles de control.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]  </td>
      <td>
        <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Lista de informes de aplicaciones]

Este módulo de búsqueda recupera una lista de todos los informes de la aplicación especificada.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL App ID]</td>
      <td>Seleccione o asigne el ID de la aplicación desde la que desea enumerar los informes.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]  </td>
      <td>
        <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Ver aplicaciones]

Este módulo de activador inicia un escenario cuando se actualiza una aplicación.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]  </td>
      <td>
        <p>Introduzca o asigne el número máximo de registros que desea que el módulo devuelva durante cada ciclo de ejecución de escenario.</p>
      </td>
    </tr>
  </tbody>
</table>

### Otro

#### [!UICONTROL Realizar una llamada de API]

Este módulo de acción realiza una llamada de API a la API de [!DNL Power BI].

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>Para obtener instrucciones sobre la conexión de la cuenta de [!DNL Power BI] a Workfront Fusion, consulte <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Crear una conexión a Adobe Workfront Fusion: instrucciones básicas</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Path]</p>
      </td>
      <td>
        <p>Escriba una ruta relativa a <code>https://api.powerbi.com</code>. Ejemplo: <code>/v1.0/myorg/datasets</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
      </td>
      <td>
        <p>Seleccione el método de petición [!UICONTROL HTTP] que necesita para configurar la llamada de API. Para obtener más información, consulte los métodos de solicitud [!UICONTROL HTTP].</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p>
        <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion añade automáticamente encabezados de autorización y encabezados x-api-key.</p>
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
   <td> <p>Añada el contenido del cuerpo para la llamada de API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice instrucciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la instrucción condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>
