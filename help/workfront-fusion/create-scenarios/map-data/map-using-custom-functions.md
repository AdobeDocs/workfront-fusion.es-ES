---
title: Asignación de datos mediante funciones personalizadas
description: Al asignar elementos, puede utilizar funciones para crear fórmulas simples o complejas.
author: Becky
feature: Workfront Fusion
exl-id: dc4e697a-a65c-48bc-99de-8e26fbeb7ba7
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: c716296d771974ffdb59e916f9865c9efb2ad5a9
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 11%
---
# Asignación de datos mediante funciones personalizadas

Puede crear funciones personalizadas en el área Funciones de Fusion. A continuación, agregue estas funciones a sus escenarios en forma de módulo de Adobe App Builder.

Dado que las funciones personalizadas funcionan a través de Adobe App Builder, su organización debe tener una licencia de Adobe App Builder para utilizarlas.

Las funciones personalizadas, como la mayoría de los elementos de escenarios, son propiedad de los equipos.

Las funciones son funciones simples de JavaScript. Para incluir variables o dependencias en la lógica de función, utilice paquetes.

Para obtener información sobre los paquetes, consulte [Usar paquetes de funciones personalizadas](/help/workfront-fusion/create-scenarios/map-data/use-custom-function-packages.md).

Workfront Fusion también incluye funciones integradas que le permiten crear fórmulas simples o complejas. Estas funciones abarcan una amplia variedad de casos de uso, incluidas las funciones para matrices, cadenas, números y datos de módulos anteriores.

Para obtener información e instrucciones sobre las funciones integradas, vea [Asignar un elemento mediante funciones integradas](/help/workfront-fusion/create-scenarios/map-data/map-using-functions.md).

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
   <p><ul><li>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li><li>Debe tener una licencia de Adobe App Builder para utilizar funciones personalizadas.</ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Configuración de una función personalizada

Puede crear una función personalizada en el área Funciones que se puede utilizar en varios escenarios o puede configurar funciones personalizadas en escenarios individuales.

* [Crear una función personalizada para utilizarla en varios escenarios](#create-a-custom-function-to-use-in-multiple-scenarios)
* [Creación de una función personalizada dentro de un escenario](#create-a-custom-function-within-a-scenario)

### Crear una función personalizada para utilizarla en varios escenarios

Las funciones personalizadas que se pueden utilizar en varios escenarios se configuran en el área Funciones de Workfront Fusion. Una vez configurada una función, puede agregarla a un escenario mediante el conector de App Builder de Adobe.

* [Inicialice el entorno de tiempo de ejecución](#initialize-your-runtime-environment)
* [Conectar un proyecto de App Builder existente](#connect-an-existing-app-builder-project)
* [Cree una función personalizada en el área Funciones](#create-a-custom-function-in-the-functions-area)

#### Inicialice el entorno de tiempo de ejecución

Para poder crear funciones personalizadas, debe inicializar el entorno de tiempo de ejecución. Esto solo debe hacerse si su equipo no tiene funciones personalizadas.

>[!IMPORTANT]
>
>La inicialización solo puede realizarse con un usuario con acceso a Adobe App Builder, ya sea un desarrollador o un administrador del sistema dentro de la organización IMS.
>
>Una vez finalizada la inicialización, todos los usuarios del equipo en el que se ha realizado pueden crear y utilizar funciones.

1. Haga clic en la ficha **Funciones** ![Icono de funciones](assets/functions-icon.png) del panel izquierdo.

   Si aún no ha configurado el tiempo de ejecución, verá el mensaje &quot;Entorno de ejecución no configurado&quot;.
1. Haga clic en **Inicializar tiempo de ejecución**.

   Después de un tiempo, aparece una lista Funciones, con dos funciones de ejemplo.

#### Conectar un proyecto de App Builder existente

Cuando Fusion crea el proyecto de App Builder, se encarga de la configuración del tiempo de ejecución. Si su equipo ya tiene un proyecto de App Builder creado antes de utilizar Fusion, debe conectarlo manualmente, creando una conexión de App Builder que utilice el área de nombres y las credenciales de tiempo de ejecución de ese proyecto. No es necesario que vuelva a crear el proyecto.

>[!NOTE]
>
>Las credenciales que introduzca en Fusion son credenciales de tiempo de ejecución. No son los detalles de inicio de sesión de Adobe. Mantenga seguro el archivo de configuración que descargue y no comparta su valor `auth`.

1. En Fusion, seleccione el equipo que necesita la conexión.
1. Haga clic en la ficha **Conexiones** en el panel izquierdo y, a continuación, haga clic en **Crear conexión**.
1. Seleccione **Adobe App Builder** como tipo de conexión y escriba un nombre que identifique el proyecto existente.
1. En [Adobe Developer Console](https://developer.adobe.com/console), abra el proyecto existente y, a continuación, seleccione el área de trabajo a la que desea conectarse.
1. En la descripción general del proyecto, haga clic en **Descargar todo** para descargar el archivo JSON de configuración del área de trabajo y abra el archivo en un editor de texto.
1. En la sección `runtime` del archivo, busque el valor `namespace`. En Fusion, ingréselo en el campo **Espacio de nombres**.
1. En la sección `runtime`, busque el valor `auth`. Tiene el formato `username:password`.

   * En Fusion, introduzca la parte antes de los dos puntos en el campo **Nombre de usuario**.
   * En Fusion, introduzca la parte después de dos puntos en el campo **Contraseña**.

1. Haga clic en **Continuar** para guardar la conexión.
1. Vuelva a la ficha **Funciones** en Fusion y actualice la página si es necesario.

Para obtener más información sobre los campos de conexión, consulte [Módulos App Builder de Adobe](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-app-builder.md#create-a-connection-to-adobe-app-builder).

#### Cree una función personalizada en el área Funciones

Una vez configurado el entorno de tiempo de ejecución, puede empezar a crear funciones personalizadas.

>[!IMPORTANT]
>
>* La función personalizada **debe** ser una función de JavaScript.
>* La función personalizada **debe** devolver un objeto.
>* Después de crear una función personalizada, no puede:
>
>   * Cambiar su nombre
>   * Ver los valores de parámetro predeterminados

1. Haga clic en la ficha **Funciones** ![Icono de funciones](assets/functions-icon.png) del panel izquierdo.
1. Haga clic en **Agregar función**.
1. Introduzca un nombre para la función personalizada.

   No podrá cambiar este nombre más adelante.
1. Introduzca el código de la función.
1. Para cada valor de parámetro predeterminado que desee agregar, haga clic en **Agregar parámetro** y escriba el nombre del parámetro y el valor predeterminado.

   Puede anular los parámetros predeterminados al agregar la función a un escenario.
1. Haga clic en **Guardar**

### Creación de una función personalizada dentro de un escenario

Para crear una función personalizada dentro de un escenario, usa el módulo **Ejecutar un bloque de código personalizado** en el conector App Builder de Adobe.

Para obtener instrucciones, consulte [módulo App Builder de Adobe](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-app-builder.md).

## Agregar una función personalizada a un escenario

Para añadir una función personalizada a un escenario, utilice el conector App Builder de Adobe.

Para obtener instrucciones, consulte [módulo App Builder de Adobe](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-app-builder.md).

