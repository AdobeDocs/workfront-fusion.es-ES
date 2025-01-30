---
title: Asignación de elementos mediante funciones
description: Al asignar elementos, puede utilizar funciones para crear fórmulas simples o complejas.
author: Becky
feature: Workfront Fusion
exl-id: b9d7643e-febf-42e2-9ddc-8ec8eba98e7a
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 44%

---

# Asignación de un elemento mediante funciones

Al asignar elementos, puede utilizar funciones para crear fórmulas simples o complejas. Las funciones disponibles son similares a las funciones de Excel y de algunos lenguajes de programación:

* Evalúan la lógica general, las matemáticas, el texto, las fechas y las matrices.
* Permiten realizar lógica condicional y transformaciones de los valores de los elementos, como convertir un texto a mayúsculas, recortar texto, convertir una fecha a un formato diferente y mucho más.

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

Para utilizar la funcionalidad de este artículo debe tener el siguiente acceso:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] paquete</td> 
   <td> <p>Cualquiera</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licencia</td> 
   <td> <p>Nuevo: [!UICONTROL Standard]</p><p>O</p><p>Actual: [!UICONTROL Work] o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licencia**</td> 
   <td>
   <p>Actual: no se requiere licencia para [!DNL Workfront Fusion].</p>
   <p>O</p>
   <p>Heredado: cualquiera </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>[!UICONTROL Select] o plan [!UICONTROL Prime] [!DNL Workfront]: su organización debe comprar [!DNL Adobe Workfront Fusion].</li><li>[!UICONTROL Ultimate] [!DNL Workfront] plan: [!DNL Workfront Fusion] está incluido.</li></ul>
   <p>O</p>
   <p>Actual: su organización debe comprar [!DNL Adobe Workfront Fusion].</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">Configuraciones de nivel de acceso*</td> 
   <td> 
     <p>Debe ser administrador de [!DNL Workfront Fusion] de su organización.</p>
     <p>Debe ser administrador de [!DNL Workfront Fusion] de su equipo.</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Inserción de funciones en campos

Para insertar una función en un campo:

1. Haga clic en la ficha **[!UICONTROL Scenarios]** en el panel izquierdo.
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

## Anidado de funciones

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

## Usar funciones de [!DNL Google Sheets]

Si [!DNL Workfront Fusion] no incluye una función que desee usar, pero la incluye [!DNL Google Sheets], puede usarla siguiendo estos pasos:

1. En [!DNL Google Sheets], cree una nueva hoja de cálculo vacía.
1. En [!DNL Workfront Fusion], abra su escenario.
1. Agregue el módulo **[!DNL Google Sheets]** >**[!UICONTROL Update a cell]** al escenario.

1. Configure el módulo:

   1. Elija la hoja de cálculo recién creada en el campo **[!UICONTROL Spreadsheet]**.
   1. Inserte la fórmula que contiene las funciones [!DNL Google Sheets] en el campo **[!UICONTROL Value]**.

      Puede utilizar la salida de los módulos anteriores como de costumbre.

      ![Usar funciones de hojas de Google](assets/exploit-google-sheet-functions-350x218.png)

1. Inserte el módulo **[!UICONTROL Google Sheets]>[!UICONTROL Get a cell]** para obtener el resultado calculado.
1. Configure el módulo con el mismo ID de celda utilizado en el paso 4.

   ![Usar funciones de hojas de Google](assets/exploit-google-sheet-functions-2-350x187.png)
