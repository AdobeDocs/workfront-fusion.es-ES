---
title: Asignación de elementos mediante funciones integradas
description: Al asignar elementos, puede utilizar funciones para crear fórmulas simples o complejas.
author: Becky
feature: Workfront Fusion
exl-id: b9d7643e-febf-42e2-9ddc-8ec8eba98e7a
source-git-commit: 3c726c1df589785719c0f141fbd5bc17194cc218
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 45%

---

# Asignación de un elemento mediante funciones integradas

Workfront Fusion incluye funciones integradas que le permiten crear fórmulas simples o complejas. Estas funciones abarcan una amplia variedad de casos de uso, incluidas las funciones para matrices, cadenas, números y datos de módulos anteriores.

Además, puede crear funciones personalizadas que los escenarios pueden utilizar para transformar y manipular los datos.

Para obtener información e instrucciones sobre las funciones personalizadas, vea [Asignar datos con funciones personalizadas](/help/workfront-fusion/create-scenarios/map-data/map-using-custom-functions.md).

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

## Asignación de datos mediante funciones integradas

Al asignar elementos, puede utilizar funciones para crear fórmulas simples o complejas. Las funciones disponibles son similares a las funciones de Excel y de algunos lenguajes de programación:

* Evalúan la lógica general, las matemáticas, el texto, las fechas y las matrices.
* Permiten realizar lógica condicional y transformaciones de los valores de los elementos, como convertir un texto a mayúsculas, recortar texto, convertir una fecha a un formato diferente y mucho más.

### Inserción de funciones en campos

Para insertar una función en un campo:

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea asignar datos.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haga clic en el campo en el que desee insertar una función.
1. Seleccione la pestaña en el panel de asignación que contiene la función que desea insertar.

   Para obtener información sobre cómo asignar fichas del panel, consulte [Descripción general de la función](/help/workfront-fusion/get-started-with-fusion/understand-fusion/function-overview.md)
   1. Haga clic en el nombre de la función.

      O

      Arrastre la función al campo.
1. Configure los parámetros de función.

   Para obtener una explicación de los parámetros de función, pase el ratón sobre la función en el panel Asignación.

   Para obtener más información acerca de las funciones y sus parámetros, vea los artículos en [Referencias de funciones: índice de artículos](/help/workfront-fusion/references/mapping-panel/functions/functions-toc.md).

1. Continúe configurando el módulo o haga clic en **Aceptar**.

>[!TIP]
>
>Cuando cree una fórmula compleja que desee reutilizar en otro campo, puede hacer clic en el campo que contiene la combinación, utilizar Cmd-A o Ctrl-A para seleccionarla y, a continuación, copiarla y pegarla en el otro campo.


>[!BEGINSHADEBOX]

**Ejemplo:** algunos tipos de datos impiden que los usuarios introduzcan más de un determinado número de caracteres. Puede utilizar la función subcadena para limitar un valor a un determinado número de caracteres.

En este ejemplo, la función de subcadena limita el nombre del proyecto a 50 caracteres.

![Ejemplo de restricción de longitud de reunión](assets/example-meet-length-restriction-350x184.png)

>[!ENDSHADEBOX]

### Anidado de funciones

Puede anidar funciones entre sí.

>[!BEGINSHADEBOX]

**Ejemplo:**

En este ejemplo, la función subcadena limita el nombre del proyecto recortado a 50 caracteres.

![Nombre recortado](assets/trimmed-name-under-50.png)

>[!ENDSHADEBOX]

Para anidar una función:

1. Haga clic en el campo en el que está creando una fórmula.

   Se abrirá el panel Asignación.

1. Haga clic en la primera función que desee agregar. Esta es la función en el exterior. En el siguiente ejemplo, esta es la función `substring`.
1. En esa función, haga clic donde desee que vaya la función anidada. En este ejemplo, la función anidada sustituye al primer parámetro.
1. En el panel de asignación, haga clic en la función anidada. En este ejemplo, esta es la función `trim`.
1. Continúe configurando la función como desee.
1. Continúe configurando el módulo o haga clic en **Aceptar**.

### Usar funciones de [!DNL Google Sheets]

Si Workfront Fusion no incluye una función que desee utilizar, pero la presenta [!DNL Google Sheets], puede utilizarla siguiendo estos pasos:

1. En [!DNL Google Sheets], cree una nueva hoja de cálculo vacía.
1. En Workfront Fusion, abra su escenario.
1. Añada el módulo **[!DNL Google Sheets]** >**[!UICONTROL Update a cell]** al escenario.

1. Configure el módulo:

   1. Elija la hoja de cálculo recién creada en el campo **[!UICONTROL Spreadsheet]**.
   1. Inserte la fórmula que contiene las funciones [!DNL Google Sheets] en el campo **[!UICONTROL Value]**.

      Puede utilizar la salida de los módulos anteriores como de costumbre.

      ![Usar funciones de hojas de Google](assets/exploit-google-sheet-functions-350x218.png)

1. Inserte el módulo **[!UICONTROL Google Sheets] >[!UICONTROL Get a cell]** para obtener el resultado calculado.
1. Configure el módulo con el mismo ID de celda utilizado en el paso 4.

   ![Usar funciones de hojas de Google](assets/exploit-google-sheet-functions-2-350x187.png)
