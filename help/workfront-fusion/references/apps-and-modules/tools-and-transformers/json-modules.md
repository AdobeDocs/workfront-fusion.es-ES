---
title: Módulos JSON
description: La aplicación JSON de Adobe Workfront Fusion proporciona módulos para procesar datos en formato JSON, de manera que Adobe Workfront Fusion pueda trabajar con el contenido de los datos o crear nuevo contenido JSON.
author: Becky
feature: Workfront Fusion
exl-id: f8b281c5-bb63-4412-98c5-d82f45f8eafc
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1254'
ht-degree: 83%

---

# [!UICONTROL Módulos JSON]

La aplicación Adobe Workfront Fusion [!UICONTROL JSON] proporciona módulos para procesar datos en formato JSON para que Adobe Workfront Fusion pueda trabajar aún más con el contenido de datos o crear contenido JSON nuevo.

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

## Consideraciones al analizar JSON

* [Estructuras de datos](#data-structure)
* [Colección frente a matriz](#collection-vs-array)

### Estructuras de datos

La estructura de datos describe cómo están organizados los datos JSON y permite asignar elementos JSON individuales a otros módulos en su escenario. Si no proporciona la estructura de datos, puede ejecutar manualmente el módulo y Workfront Fusion creará la estructura a partir del JSON proporcionado:

1. Añada el módulo [!UICONTROL Analizar JSON] a un escenario.
1. En el campo **[!UICONTROL cadena JSON]**, escriba el JSON a partir del cual desea crear una estructura de datos.
1. Aún no conecte otros módulos al módulo [!UICONTROL Analizar JSON]. Debido a que Workfront Fusion aún no conoce la estructura de los datos JSON, todavía no es posible asignar datos del módulo [!UICONTROL Analizar JSON] a otros módulos en su escenario.
1. Ejecute manualmente el escenario. Esto permite que el módulo [!UICONTROL Analizar JSON] identifique la estructura de JSON a partir del JSON que ha proporcionado.
1. Ahora puede conectar los siguientes módulos. Los elementos del módulo JSON de análisis ya están disponibles para su asignación.

Para obtener más información, consulte [Estructuras de datos en [!UICONTROL Adobe Workfront Fusion]](/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md).

### Colección frente a matriz

Si el campo de cadena JSON contiene una colección `{ ... }`, el resultado es un paquete único que contiene los elementos de la colección.

>[!BEGINSHADEBOX]

**Ejemplo:**

```
{
    "name" : "Peter",

    "ID" : 1>}
```


![Colección JSON](/help/workfront-fusion/references/apps-and-modules/assets/json-collection.png)

>[!ENDSHADEBOX]

Si el campo de cadena JSON contiene una matriz `[ ... ]`, el resultado es una serie de paquetes. cada paquete contiene un elemento de la matriz.

>[!BEGINSHADEBOX]

**Ejemplo:**

```
[
  {
    "name" : "Peter",
    "ID" : 1
  },

  {
    "name" : "Mike",
    "ID" : 2
  }
]
```

![Matriz JSON](/help/workfront-fusion/references/apps-and-modules/assets/json-array.png)

>[!ENDSHADEBOX]

## [!UICONTROL JSON] módulos y sus campos

Al configurar módulos de [!DNL JSON], Workfront Fusion muestra los campos que se indican a continuación. Junto con estos, es posible que se muestren campos JSON adicionales, dependiendo de factores como su nivel de acceso en la aplicación o servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, vea [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Convertir JSON a XML](#convert-json-to-xml)
* [Analizar JSON](#parse-json)
* [Crear JSON](#create-json)
* [Transformar JSON](#transform-json)

### Agregadores

#### [!UICONTROL Añadir a JSON]

Este módulo de agregador agrega la salida de un módulo anterior a JSON.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source module] </td> 
   <td> <p>Seleccione el módulo que genera los datos que desea añadir a JSON.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data structure]</td> 
   <td> <p>Seleccione la estructura de datos que desea utilizar para crear JSON. La estructura de datos determina qué otros campos están disponibles en este módulo. Para obtener más información, consulte <a href="#data-structure" class="MCXref xref">Estructura de datos</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Indentation]</td> 
   <td> <p> Seleccione si desea aplicar sangría al JSON mediante pestañas, dos espacios o cuatro espacios.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Group by]</td> 
   <td>Defina una expresión por la cual desea agrupar la salida agregada. Esta expresión puede contener uno o varios elementos asignados. Los datos añadidos se separan en grupos utilizando el valor de esta expresión. Cada grupo genera como un paquete independiente con una clave (la expresión evaluada) y un valor (el texto añadido). Puede utilizar la clave como filtro en módulos posteriores.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Stop processing after an empty aggregation]</td> 
   <td>Active esta opción para detener el escenario cuando no haya resultados.</td> 
  </tr> 
 </tbody> 
</table>

### Transformadores

* [Convertir JSON a XML](#convert-json-to-xml)
* [Crear JSON](#create-json)
* [Analizar JSON](#parse-json)
* [Transformar JSON](#transform-json)

#### [!UICONTROL Convertir JSON a XML]

Este módulo de acción convierte una cadena JSON a XML.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL JSON string] </td> 
   <td> <p>Introduzca o asigne el JSON que desea convertir en XML.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Crear JSON]

Este módulo de acción crea JSON a partir de una estructura de datos.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Estructuras de datos</td> 
   <td> <p>Seleccione la estructura de datos que desea utilizar para crear JSON. Para obtener más información, consulte <a href="#data-structure" class="MCXref xref">Estructura de datos</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Sangría</td> 
   <td> <p>Seleccione la sangría que desee utilizar para este JSON.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Analizar JSON]

Este módulo de acción analiza una cadena JSON en una estructura de datos, lo que le permite acceder a los datos dentro de la cadena JSON.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data structure]</td> 
   <td> <p>Seleccione la estructura de datos que desea utilizar para crear JSON. Para obtener más información, consulte <a href="#data-structure" class="MCXref xref">Estructura de datos</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL JSON string] </td> 
   <td> <p>Introduzca o asigne el JSON que desea analizar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Transformar JSON]

Este módulo de acción transforma un objeto en una cadena JSON.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Sangría</td> 
   <td> <p>Seleccione la sangría que desee utilizar para este JSON.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object]</td> 
   <td> <p>Introduzca o asigne el objeto que desea transformar en JSON.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Transformación de registros de datos a JSON

>[!BEGINSHADEBOX]

**Ejemplo:** El siguiente ejemplo muestra cómo transformar registros de datos de [!DNL Google Sheets] al formato JSON:

1. Coloque el módulo [!DNL Google Sheets] > [!UICONTROL Seleccionar filas] en su escenario para recuperar los datos. Configure el módulo para recuperar filas de la hoja de cálculo de [!DNL Google]. Establezca el **[!UICONTROL Número máximo de filas devueltas]** en un número pequeño, pero mayor que uno para realizar pruebas (por ejemplo, tres). Ejecute el módulo de [!DNL Google Sheets] haciendo clic con el botón secundario en él y eligiendo &quot;**[!UICONTROL Ejecutar este módulo solamente]**&quot;. Compruebe la salida del módulo.

1. Conecte el módulo [!UICONTROL Agregador de matrices] después del módulo [!DNL Google Sheets]. En la configuración del módulo, elija el módulo de [!DNL Google Sheets] en el campo **[!UICONTROL Nodo de origen]**. Deje los demás campos tal como están por el momento.

1. Conecte el módulo [!UICONTROL JSON] > [!UICONTROL Crear JSON] después del módulo [!UICONTROL Agregador de matrices]. La configuración del módulo requiere una estructura de datos que describa el formato JSON. Haga clic en **[!UICONTROL Añadir]** para abrir la configuración de la estructura de datos. La forma más sencilla de crear esta estructura de datos es generarla automáticamente a partir de una muestra JSON. Haga clic en **[!UICONTROL Generador]** y pegue la muestra JSON en el campo **[!UICONTROL Datos de muestra]**:

   **Ejemplo:**

   ```
   {
   "books": [
   {
   "id": "ID",
   "title": "Title",
   "author": "Author"
   }
   ]
   }
   ```

1. Haga clic en **[!UICONTROL Guardar]**. El campo [!UICONTROL Especificación] de la estructura de datos ahora contiene la estructura generada.
1. Cambie el nombre de la estructura de datos por otro más específico y haga clic en **[!UICONTROL Guardar]**. Un campo correspondiente al atributo de la matriz raíz aparece como un campo asignable en la configuración del módulo JSON.

1. Haga clic en el botón **[!UICONTROL Map]** junto al campo y asigne el elemento `Array[]` de la salida del agregador de matrices a este.

1. Haga clic en **[!UICONTROL Aceptar]** para cerrar la configuración del módulo [!UICONTROL JSON].

1. Abra la configuración del módulo [!UICONTROL Agregador de matrices]. Cambie la **[!UICONTROL estructura de destino]** de [!UICONTROL Personalizado] al campo del módulo [!UICONTROL JSON] correspondiente al atributo de la matriz raíz. Asigne elementos del módulo [!DNL Google Sheets] a los campos correspondientes.

1. Haga clic en **[!UICONTROL Aceptar]** para cerrar la configuración del módulo [!UICONTROL Agregador de matrices].

1. Ejecute el escenario.

   El módulo [!UICONTROL JSON] genera el formato JSON correcto.

1. Abra la configuración del módulo [!DNL Google Sheets] y aumente el número de [!UICONTROL Número máximo de filas devueltas] para que sea mayor que el número de filas en su hoja de cálculo para procesar todos los datos.

>[!ENDSHADEBOX]

## Resolución de problemas

### No se pueden asignar datos del módulo [!UICONTROL Analizar JSON]

Asegúrese de que el contenido JSON esté asignado correctamente al módulo [!UICONTROL Analizar JSON] y de que la estructura de datos esté definida correctamente. Para obtener más información, consulte [Transformación de registros de datos a JSON](#transforming-data-records-to-json) en este artículo.

### El módulo falla al utilizar afirmaciones condicionales en JSON

Cuando utilice afirmaciones condicionales como `if` en su JSON, coloque las comillas fuera de la afirmación condicional.

>[!BEGINSHADEBOX]

**Ejemplo:**

![Comillas en JSON](/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png)

>[!ENDSHADEBOX]
