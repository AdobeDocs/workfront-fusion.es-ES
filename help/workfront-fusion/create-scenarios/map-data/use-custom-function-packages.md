---
title: Usar paquetes de funciones personalizadas
description: Al asignar elementos, puede utilizar funciones para crear fórmulas simples o complejas.
author: Becky
feature: Workfront Fusion
source-git-commit: eb4c1ed6991606928beccbb57a8a86182e58a9e7
workflow-type: tm+mt
source-wordcount: '1992'
ht-degree: 6%

---


# Uso de paquetes de funciones personalizadas

Los paquetes le permiten crear y ejecutar su propia lógica personalizada dentro de Adobe Workfront Fusion sin salir de la interfaz de Fusion. Cuando los módulos estándar no hacen exactamente lo que necesita, puede utilizar una función para transformar datos, hacer un cálculo, llamar a un servicio externo o envolver una rutina que desee reutilizar. A continuación, puede probarlo, activarlo y utilizarlo desde sus escenarios.

Las funciones complejas pueden requerir recursos como variables y dependencias, como bibliotecas. Para estas funciones, puede crear un paquete que incluya la función y sus recursos.

Un paquete puede incluir:

* **Funciones**: La lógica que se ejecuta durante la ejecución de un escenario.
* **Variables**: valores reutilizables, como una dirección URL base o una clave de API, que usa la función en el paquete.
* **Dependencias**: Fuera de las bibliotecas en las que pueden confiar sus funciones.
* **Historial**: versiones anteriores de cada función, guardadas automáticamente, a las que puede hacer referencia.


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

## Configurar la conexión del entorno de tiempo de ejecución

>[!NOTE]
>
>Esta es una configuración única.

La primera vez que su equipo utilice esta función, deberá configurar el entorno que ejecuta las funciones. Solo lo hace una vez por equipo.

1. Haga clic en la ficha **Paquetes** ![Icono de paquetes](assets/packages-icon.png) en el panel de navegación izquierdo.

   Si no se ha configurado el entorno, aparecerá la pantalla **Entorno de tiempo de ejecución no configurado**.

1. Haga clic en **Inicializar tiempo de ejecución**.

1. Para escribir un nombre distinto del predeterminado, escriba el nombre en el campo **Nombre de conexión**.

1. Seleccione el proyecto de Adobe App Builder al que pertenecerá este paquete:

   * Para seleccionar un proyecto existente, empiece a escribir el nombre del proyecto y, a continuación, selecciónelo cuando aparezca.
   * Para crear un nuevo proyecto, escribe un nombre que no exista y haz clic en **Crear nuevo**.
   * Si deja esto vacío, Fusion utilizará un proyecto predeterminado.

1. Seleccione **Continuar**.

   Fusion finaliza la configuración y está listo para crear paquetes.

   Su entorno aparecerá como una pestaña de conexión en la parte superior de la página.

   ![Entorno como ficha de conexión](assets/package-environment-as-connection.png)

1. (Condicional) Para agregar un entorno adicional, haga clic en el icono + y siga las instrucciones de esta sección.

1. (Condicional) Para quitar un entorno existente, pase el ratón sobre la pestaña de conexión del entorno y haga clic en **X** cuando aparezca.

   >[!WARNING]
   >
   >Al eliminar una conexión, Fusion se desconecta de ese entorno. Los paquetes que contiene ya no están disponibles en Fusion a través de esa conexión.

## Creación y apertura de un paquete

1. Haga clic en la ficha **Paquetes** ![Icono de paquetes](assets/packages-icon.png) en el panel de navegación izquierdo.

1. Seleccione la pestaña de la conexión en la que desea trabajar.

1. Haga clic en **Crear paquete**.

1. Escriba un nombre y seleccione **Crear**.

   El paquete se abre automáticamente.

1. Para volver a abrir un paquete más tarde, selecciónelo en la lista Paquetes y seleccione **Ver**.
1. Para eliminar un paquete, selecciónelo en la lista Paquetes y elija **Eliminar**.

   >[!WARNING]
   >
   >Al eliminar un paquete, se elimina permanentemente, y todo lo que contiene.

## Administración de un paquete

Un paquete abierto se divide en cuatro partes:

* **Funciones**: cree, pruebe y publique la función.
* **Variables**: configure variables para la función.
* **Dependencias**: instale dependencias, como bibliotecas externas, para esta función.
* **Historial**: vea las versiones anteriores de cada función.

Además de estas cuatro áreas, un medidor de Almacenamiento en la parte superior muestra la cantidad de espacio que se utiliza. Cada paquete tiene un límite de tamaño total de **21 MB**. Esto incluye funciones, variables y dependencias, incluidas versiones guardadas.

Si se queda sin espacio, le recomendamos que elimine las dependencias, variables o versiones anteriores que no utilice para liberar espacio.

Para volver a la lista de paquetes, seleccione la flecha hacia atrás junto al nombre del paquete.

<!--Create toc here-->

### Funciones

El área **Funciones** muestra una lista de funciones en el paquete, incluido el nombre de la función, su estado, su tamaño y cuántas entradas espera.

Para filtrar la lista de funciones:

1. Filtre por estado haciendo clic en **Todos**, **Borradores** o **Publicados**.
1. Utilice la barra de búsqueda para buscar funciones específicas.

#### Estado de función

Una función puede tener el estado de borrador o publicada.

* **Borrador**: Las funciones en estado de Borrador están en curso. Puede editar y probar libremente sin afectar a los datos activos.
* **Publicado**: Las versiones publicadas están activas. Los escenarios ejecutan versiones publicadas de funciones.

El uso de borradores le permite realizar cambios con seguridad. Puede refinar un borrador, probarlo y, a continuación, publicarlo cuando esté satisfecho.

| Estado | Lo que significa |
|---|---|
| **Publicadas** | Existe una versión activa. |
| **Borrador** | La función sigue en curso o una función activa tiene cambios que aún no ha publicado. |

#### Cree o edite una función en el área Paquetes

1. Haga clic en la ficha **Paquetes** ![Icono de paquetes](assets/packages-icon.png) en el panel de navegación izquierdo.
1. En el área **Funciones**, seleccione **Crear función**.

   O

   Haga clic en la casilla de verificación que hay junto a una función existente y seleccione **Editar** en la barra de acciones de la parte inferior de la página.

1. (Condicional) Si está creando una función nueva, en el campo **Nueva función**, escriba un nombre para la función.

1. (Opcional y condicional) Para cambiar el nombre de una función existente, haga clic en el icono Editar junto al nombre de la función e introduzca el nuevo nombre.

1. En la ficha **Código**, escriba la lógica de función.

   Tenga en cuenta lo siguiente al crear la función:

   * Las funciones deben escribirse en JavaScript.
   * Puede leer las entradas que defina, reutilizar las variables y llamar a las demás funciones.
   * A medida que escribe, aparecen sugerencias.

1. Para limpiar el formato de la función, haz clic en **Beautify**.

1. (Opcional) En la ficha **Parámetros**, defina las entradas que espera la función.

   Para obtener información sobre las entradas, consulte [Definir entradas](#define-inputs) en este artículo.

1. En la ficha **Probar**, pruebe su función.

   Para obtener instrucciones, vea [Probar una función](#test-a-function) en este artículo.

1. Para guardar esta función como borrador, haga clic en **Guardar como borrador**.

   O

   Para publicar la función, haga clic en **Publicar**.

   >[!NOTE]
   >
   >Al publicar una función, se borra el historial de versiones. La versión publicada se convierte en el punto de partida actual y las versiones de borrador anteriores ya no se conservan.

##### Definir entradas

Puede usar la ficha **Parámetros** para describir la información que necesita la función cada vez que se ejecuta.

1. Haga clic en la ficha **Paquetes** ![Icono de paquetes](assets/packages-icon.png) en el panel de navegación izquierdo.
1. En el área **Funciones**, seleccione **Crear función**.

   O

   Haga clic en la casilla de verificación que hay junto a una función existente y seleccione **Editar** en la barra de acciones de la parte inferior de la página.

1. Haga clic en la ficha **Parámetros**.

1. Para cada parámetro que desee agregar, haga clic en **Agregar parámetro** y configure lo siguiente:

* **Nombre**: nombre de la entrada
* **Etiqueta**: nombre descriptivo que se muestra al probar la función
* **Tipo**: El tipo de datos, como texto, número, verdadero/falso o un objeto estructurado.
* **Requerido**: Si se debe proporcionar un valor.

Estas entradas se convierten en los campos que se rellenan al realizar la prueba y en los valores que el escenario transmite cuando ejecuta la función.

##### Prueba de una función

Se recomienda probar una función antes de publicarla.

1. Haga clic en la ficha **Paquetes** ![Icono de paquetes](assets/packages-icon.png) en el panel de navegación izquierdo.
1. En el área **Funciones**, seleccione **Crear función**.

   O

   Haga clic en la casilla de verificación que hay junto a una función existente y seleccione **Editar** en la barra de acciones de la parte inferior de la página.

1. Haga clic en la ficha **Prueba**.

1. Introduzca un valor para cada entrada.

1. Ejecute la función:

   * Seleccione **Borrador de prueba** para probar la versión de trabajo en curso.
   * Seleccione **Ejecutar publicado** para ejecutar la versión activa.

1. Revise el resultado, incluido si se realizó correctamente, cuánto tiempo tardó y el resultado que devolvió.

>[!NOTE]
>
>**Ejecutar publicado** solo está disponible después de que se haya publicado una función.

#### Realizar cambios en una función activa

Después de publicar una función, el botón **Publicar** se convierte en un menú:

* **Volver a publicar**: inserta los cambios de borrador más recientes en la versión activa.
* **Cancelar la publicación**: elimine la función del servicio. Su trabajo se mantiene como borrador para que pueda volver a él.

#### Eliminación de una función

1. Haga clic en la ficha **Paquetes** ![Icono de paquetes](assets/packages-icon.png) en el panel de navegación izquierdo.
1. Haga clic en la casilla de verificación que hay junto a una función existente y seleccione **Eliminar** en la barra de acciones de la parte inferior de la página.

>[!WARNING]
>
>Al eliminar una función, esta se elimina por completo, junto con su historial. Cualquier escenario o función que lo utilice dejará de funcionar.

## Variables

Las variables son valores reutilizables que las funciones pueden utilizar, como una dirección URL base, un ID de cuenta o una clave de API. Almacenarlas como variables significa que establece un valor una vez y lo actualiza en un lugar, en lugar de actualizarlo en muchas funciones.

### Crear o editar una variable

1. Haga clic en la ficha **Paquetes** ![Icono de paquetes](assets/packages-icon.png) en el panel de navegación izquierdo.
1. En la ficha **Variables**, seleccione **Nueva variable**.

   O


   Haga clic en el icono **Editar** junto a la variable que desee editar.

1. Complete los detalles:

   * **Clave**: Escriba el nombre que utilizan las funciones para hacer referencia al valor.

   Para cambiar el nombre de esta variable, cambie el valor Key.
   * **Valor**: escriba el valor que desea almacenar.
   * **Type**: seleccione si el tipo de valor es texto, un número, un valor booleano (true/false) o un objeto estructurado.
   * **Descripción**: escribe una nota opcional para recordarte para qué sirve.
   * **Público**: Active esta opción si desea usar la variable en el diseñador de escenarios. Cuando está desactivada, la variable solo está disponible dentro de las funciones del paquete.
   * **Secreto**: active esta opción para ocultar valores confidenciales, como claves. El valor se oculta en la lista de variables y también se sanea para que no se exponga en el diseñador de escenarios. Las funciones seguirán recibiendo el valor real cuando se ejecuten.

1. Seleccione **Crear variable** o **Guardar cambios**.

### Eliminar una variable

1. Haga clic en la ficha **Paquetes** ![Icono de paquetes](assets/packages-icon.png) en el panel de navegación izquierdo.
1. En la ficha **Variables**, haga clic en el icono **Eliminar** que aparece junto a la variable que desea eliminar.

>[!WARNING]
>
>Las funciones que utilizan una variable eliminada dejarán de funcionar.

## Dependencias

Algunas funciones requieren bibliotecas adicionales para realizar su trabajo. En la ficha **Dependencias** se agregan y administran esas bibliotecas.

### Añadir bibliotecas

1. Haga clic en la ficha **Paquetes** ![Icono de paquetes](assets/packages-icon.png) en el panel de navegación izquierdo.
1. En la ficha **Dependencias**, escriba uno o varios nombres de biblioteca separados por comas. Puede solicitar una versión específica agregándola después del nombre (por ejemplo, `axios, lodash@4.17.21`).

1. Haga clic en **Instalar**.

### Eliminación de una biblioteca

1. Haga clic en la ficha **Paquetes** ![Icono de paquetes](assets/packages-icon.png) en el panel de navegación izquierdo.
1. En la ficha **Dependencias**, haga clic en el icono **Eliminar** situado junto a la biblioteca que desee eliminar.

>[!WARNING]
>
>Las funciones que dependen de una biblioteca eliminada pueden dejar de funcionar.

## Historia

Cada vez que se guarda un borrador de una función, Fusion guarda una copia. La pestaña **History** le permite ver y restaurar versiones anteriores.

1. Haga clic en la ficha **Paquetes** ![Icono de paquetes](assets/packages-icon.png) en el panel de navegación izquierdo.
1. En la ficha **Historial**, seleccione una función a la izquierda para ver sus versiones guardadas, la más reciente primero.
1. Seleccione una versión para ver exactamente lo que contenía en ese momento.
1. Para restaurar una versión, haga clic en **Restaurar como borrador**.

   La versión se restaura como un nuevo borrador, por lo que puede revisarla y probarla antes de publicarla. La versión activa permanecerá en su lugar hasta que publique.
1. Para eliminar una versión, selecciónela, haga clic en **Eliminar versión** y confirme la acción.

>[!NOTE]
>
>* La publicación de una función borra su historial. El historial registra los cambios realizados mientras trabaja en un borrador, hasta que realice la publicación.
>* La eliminación de una versión no se puede deshacer.



## Uso de un paquete en un escenario

El propósito de crear funciones y variables es ponerlas a trabajar en sus escenarios. Para usar funciones y variables, usa el conector **Adobe App Builder**.

* **Usar función del paquete**: Este módulo ejecuta una de las funciones como paso en un escenario. Elija el paquete y la función, rellene las entradas que haya definido y el resultado de la función se pasará a los módulos que siguen.
* **Usar variable del paquete**: Este módulo incorpora una de las variables del paquete en un escenario para que pueda asignar su valor a otros módulos.

Para obtener información e instrucciones, consulte [Módulos App Builder de Adobe](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-app-builder.md).

<!--

To add one:

1. In the scenario designer, add a module and choose the **Adobe App Builder** connector.

1. Select **Use function from package** or **Use variable from package**.

1. Choose the package and the function or variable you want, then map the inputs or value as needed.

>[!NOTE]
>
>Publish a function before using it in a scenario, and turn on **Public** for any variable you want to use there.

-->


