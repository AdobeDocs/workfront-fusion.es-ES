---
title: Utilice cURL para agregar un módulo HTTP
description: Puede pegar una solicitud cURL en su escenario y Fusion creará un módulo HTTP configurado a partir de la solicitud cURL.
author: Becky
feature: Workfront Fusion
exl-id: 6d466809-860d-4f72-9044-ebe2df943674
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 20%

---

# Utilice cURL para agregar un módulo HTTP

Puede pegar una solicitud cURL en su escenario y Fusion creará un módulo HTTP configurado a partir de la solicitud cURL.

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
   <td> <p>Nuevo: estándar</p><p>O</p><p>Actual: [!UICONTROL Work] o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion**</td> 
   <td>
   <p>Actual: no se requiere licencia de Workfront Fusion.</p>
   <p>O</p>
   <p>Heredado: cualquiera </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Nuevo:</p> <ul><li>Plan de Workfront de [!UICONTROL Select] o [!UICONTROL Prime]: su organización debe adquirir Adobe Workfront Fusion.</li><li>Plan de Workfront de [!UICONTROL Ultimate]: Workfront Fusion está incluido.</li></ul>
   <p>O</p>
   <p>Actual: Su organización debe comprar Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Creación de un módulo HTTP a partir de una solicitud cURL


Para crear un módulo HTTP mediante cURL:

1. Cree el texto de la solicitud cURL fuera de Fusion, como en un editor de texto.
1. Copie la solicitud cURL en el portapapeles.
1. Haga clic en la ficha **[!UICONTROL Escenarios]** en el panel izquierdo.
1. Seleccione el escenario en el que desea crear el módulo.
1. Haga clic en cualquier lugar del escenario para introducir el Editor de escenarios.
1. Haga clic con el botón derecho en cualquier espacio en blanco del editor de escenarios y seleccione **Pegar**.

   O

   Presione Ctrl + V (Windows) o Cmd + V (Mac).


   Se crea un módulo de HTML.
1. Arrastre el módulo para conectarlo a su escenario.

## Resolución de problemas

Si la cURL no se pega en el escenario, compruebe la configuración del explorador para asegurarse de que está habilitado el pegado desde el portapapeles.
