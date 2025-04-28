---
title: Copiar módulos o escenarios
description: Puede copiar módulos, grupos de módulos o escenarios completos en Adobe Workfront Fusion. Esta capacidad le permite reutilizar escenarios o partes de escenarios sin tener que volver a crearlos.
author: Becky
feature: Workfront Fusion
exl-id: 5cece7d4-b2c7-4276-8a6f-f65bad799c7a
source-git-commit: 860209fdcf2e7707663cc2d454c0499972b1261e
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 66%

---

# Copiar módulos o escenarios

Puede copiar módulos, grupos de módulos o escenarios completos en Adobe Workfront Fusion. Esta capacidad le permite reutilizar escenarios o partes de escenarios sin tener que volver a crearlos.

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
   <p>Nuevo:</p> <ul><li>Plan [!UICONTROL Select] o [!UICONTROL Prime] [!DNL Workfront]: su organización debe adquirir [!DNL Adobe Workfront Fusion].</li><li>Se incluye el plan [!DNL Workfront] de [!UICONTROL Ultimate]: [!DNL Workfront Fusion].</li></ul>
   <p>O</p>
   <p>Actual: su organización debe comprar [!DNL Adobe Workfront Fusion].</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre [!DNL Adobe Workfront Fusion] licencias, consulte [[!DNL Adobe Workfront Fusion] licencias](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Los módulos deben existir en un escenario para poder copiarlos.

## Copiar un módulo o un grupo de módulos

Al copiar un módulo, la copia conserva todos los valores de campo y la configuración del módulo original.

Puede pegar el módulo o módulos en otra área del mismo escenario o en un escenario diferente.

Tenga en cuenta lo siguiente al pegar módulos en un escenario diferente:

* Cualquier valor de campo que extraiga información de otro módulo que no haya copiado ya no podrá acceder a esa información. Debe configurar estos campos para extraer información del nuevo escenario.
* Si pega los módulos en un escenario propiedad de otro equipo u organización, todas las conexiones deben actualizarse a conexiones propiedad del equipo u organización propietario del nuevo escenario.

### Copiar módulos

Copiar un grupo de módulos es similar a copiar un solo módulo.

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea copiar un módulo.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haga clic con el botón derecho en el módulo que desea copiar.

   >[!NOTE]
   >
   >Para seleccionar más de un módulo, mantenga presionada la tecla [!UICONTROL Mayús] y haga clic en los módulos que desea copiar. Al copiar un grupo de módulos también se copian las líneas de conexión, los filtros o la lógica de enrutamiento entre ellos.

1. Seleccione **[!UICONTROL Copiar módulo]**.
1. Mueva el cursor al área del escenario donde desea la copia del escenario.
1. Haga clic con el botón derecho y seleccione **[!UICONTROL Pegar]**.
1. Conecte los módulos pegados al escenario arrastrándolos a la ubicación adecuada en el escenario.

   También puede utilizar métodos abreviados del teclado para copiar y pegar.

## Copiar un escenario mediante clonación

Al clonar un escenario, se crea una copia del mismo que luego puede editar.

1. Abra la página de detalles del escenario:

   1. Haga clic en la pestaña **[!UICONTROL Escenario]** en el panel izquierdo y, a continuación, haga clic en un escenario sobre el que desea obtener detalles.

      O

      Si está trabajando en el escenario en el editor de escenarios, haga clic en la flecha izquierda ![Salir de la flecha de edición](assets/exit-editing-arrow.png) cerca de la esquina superior izquierda de la ventana.

1. Haga clic con el botón derecho en **[!UICONTROL Opciones]** en la parte superior derecha de la página.
1. Seleccione **[!UICONTROL Clonar]**.
1. (Opcional) Escriba un nombre para el nuevo escenario.
1. (Opcional) Habilite **[!UICONTROL Mantener los estados de los nuevos módulos igual que los que se están duplicando]** para asegurarse de que el escenario copiado también incluya información sobre los registros más recientes procesados por el escenario original.
1. Haga clic en **[!UICONTROL Guardar]** para crear el escenario.

## Copiar un escenario mediante modelos

Los modelos de escenario representan la disposición, la asignación y los valores de campo de un escenario determinado en un momento determinado. Puede exportar un modelo de escenario a un archivo JSON de su equipo y, a continuación, importarlo al crear un nuevo escenario. Los escenarios importados de un modelo de escenario se pueden editar.

Un modelo de escenario representa todo el escenario. Si desea copiar solamente ciertos módulos de un escenario, consulte [Copiar un módulo o un grupo de módulos](#copy-a-module-or-a-group-of-modules) en este artículo.

### Exportar un modelo de escenario

1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea exportar un modelo.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. En el escenario, haga clic en el menú **[!UICONTROL Más]** del área de configuración del escenario.
1. Haga clic en **[!UICONTROL Exportar modelo]**.

   Se crea un archivo JSON y se descarga en el equipo. Puede localizar este archivo en la carpeta [!DNL Downloads].

>[!NOTE]
>
>Para exportar el modelo de una versión anterior de un escenario, consulte [Ver y administrar versiones de escenarios](/help/workfront-fusion/manage-scenarios/restore-a-scenario-version.md).

### Importar un modelo

>[!IMPORTANT]
>
>Si importa un modelo a un escenario existente, el modelo de escenario reemplazará al escenario existente. No se puede anexar un modelo a un escenario existente.

1. Empiece a crear un nuevo escenario.
1. En el escenario, haga clic en el menú **[!UICONTROL Más]** del área de configuración del escenario.
1. Haga clic en **[!UICONTROL Importar modelo]**.
1. En el diálogo que aparece, haga clic en **[!UICONTROL Examinar]**
1. Vaya al modelo que desee importar y haga clic en **[!UICONTROL Abrir]**.
1. Haga clic en **[!UICONTROL Guardar]**.

   Se crea un archivo JSON y se descarga en el equipo. Encontrará este archivo en su carpeta [!UICONTROL Descargas].

## Copiar y reutilizar escenarios mediante plantillas

Puede crear plantillas como punto de partida para sus escenarios de [!DNL Workfront Fusion]. Cuando crea un escenario a partir de una plantilla, puede modificarlo sin modificar la plantilla. Los valores de campo no se guardan en las plantillas.

Para obtener más información sobre cómo crear un escenario con una plantilla, vea [Crear escenarios con plantillas](/help/workfront-fusion/create-scenarios/add-modules/create-scenarios-with-fusion-templates.md).

## Resolución de problemas

Si está copiando y pegando módulos como se describe en [Copie un módulo o un grupo de módulos](#copy-a-module-or-a-group-of-modules) y no aparece nada al pegar, compruebe la configuración del sitio del explorador para asegurarse de que se permite pegar desde el portapapeles.
