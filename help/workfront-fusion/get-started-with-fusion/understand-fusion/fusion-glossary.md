---
title: Glosario de Adobe Workfront Fusion
description: En el siguiente glosario se explican algunos términos comunes de Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 7f098ec2-8594-4e5d-9ce7-d1738a05f9a6
source-git-commit: 190bfe5992fb21b789a7246c4ae732a5dc7672fa
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 28%

---

# Glosario de Adobe Workfront Fusion

En el siguiente glosario se explican algunos términos comunes de Adobe Workfront Fusion.


<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>Acción</p> </td> 
   <td>Módulo que le permite realizar una acción, como leer o escribir datos desde o hacia una aplicación o servicio seleccionado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Concentrador</p> </td> 
   <td> <p>Un tipo de módulo que combina varios paquetes (varias colecciones de datos) en un solo paquete. </p><p>Para obtener más información, consulte <a href="/help/workfront-fusion/references/modules/aggregator-module.md" class="MCXref xref">Módulo de agregado</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API</td> 
   <td>Las interfaces de programación de aplicaciones (API) son una forma de que las aplicaciones y los servicios se comuniquen entre sí. Fusion utiliza las API para comunicarse con la aplicación a la que se está conectando. Cada aplicación tiene una API independiente. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Clave API</td> 
   <td>Código único que identifica al usuario, desarrollador o programa que llama a la API de un software y que se utiliza para la autenticación. Como los módulos Fusion funcionan conectando API, a veces es necesario usar claves API. La aplicación que las requiere distribuye las claves de API. Por ejemplo, si necesita una clave de API para conectar Fusion a Adobe Lightroom, debe solicitarla a través de su cuenta de Adobe Lightroom.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Aplicación o servicio</td> 
   <td> <p>Una aplicación de software. Fusion puede conectarse a la mayoría de las aplicaciones, incluso si no tiene un conector dedicado para esa aplicación.</p> <p>Una aplicación también puede ser una función especial que manipule datos, como un iterador o un agregador. </p> <p>Un servicio es una fuente de datos que puede incluir una API web, una página web, distintos tipos de servidores (FTP, SMTP, IMAP), etc. </p>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Paquete</p> </td> 
   <td> <p>Un paquete es una unidad básica de datos que devuelven o reciben los módulos. Por ejemplo, un módulo de búsqueda que devuelva tres registros generará tres paquetes de datos, uno para cada registro. Un paquete consta de elementos.</p> </td> 
  </tr> 
  <tr>
   <td role="rowheader"> <p>Conexión</p> </td> 
   <td> <p>Una conexión representa un conjunto de credenciales para conectarse a un servicio determinado. Puede configurar conexiones dentro de cualquier módulo y, a continuación, puede utilizar esa conexión en cualquier otro módulo. Cada módulo debe tener una conexión seleccionada, de modo que Fusion pueda utilizar esas credenciales para acceder a la información que requiere el módulo. </p><p>Para obtener más información, consulte <a href="/help/workfront-fusion/get-started-with-fusion/understand-fusion/connection-overview.md" class="MCXref xref">Información general sobre la conexión</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Conector</td> 
   <td>Un conector es el conjunto de módulos de una aplicación determinada. Workfront Fusion ofrece conectores a muchas aplicaciones de trabajo comunes, como Workfront, Salesforce y Jira.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Ciclo</p> </td> 
   <td> <p>Un ciclo consta de dos fases de la ejecución del escenario: operación y confirmación. El escenario puede consistir en uno o más ciclos. Para obtener información más detallada, vea <a href="/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md" class="MCXref xref">Ejecución de escenarios, ciclos y fases</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Almacén de datos</p> </td> 
   <td> <p>Un almacén de datos almacena datos de escenarios o permite transferir datos entre escenarios individuales o ejecuciones de escenarios. </p><p>Para obtener más información, consulte <a href="/help/workfront-fusion/create-scenarios/map-data/data-stores.md" class="MCXref xref">Almacenes de datos</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Filtro</p> </td> 
   <td> <p> Se puede aplicar un filtro entre dos módulos, que le permite trabajar únicamente con paquetes que se ajusten a determinados criterios. Puede aplicar una serie de filtros diferentes. </p><p>Para obtener más información, vea <a href="/help/workfront-fusion/create-scenarios/add-modules/add-a-filter-to-a-scenario.md" class="MCXref xref">Agregar un filtro a un escenario</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Identificador </p> </td> 
   <td> <p>Nombre que se utiliza para identificar paquetes de forma exclusiva. Una ID se utiliza generalmente para diferenciar un paquete que se va a actualizar o eliminar de un servicio determinado. Los ID se pueden asignar desde la salida de un módulo anterior.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Elementos</p> </td> 
   <td> <p>Parte de un paquete. Los paquetes pueden constar de varios elementos. Existen varios tipos diferentes de elementos: texto, número, booleano (sí/no), fecha, hora, búfer (datos binarios), colecciones, menú de selección, matriz y validación.</p><p> Para obtener más información, vea <a href="/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md" class="MCXref xref">Tipos de datos de elementos</a>.</p> </td> 
  </tr>
  <tr> 
   <td role="rowheader"> <p>Iterador</p> </td> 
   <td> <p>Tipo de módulo que le permite tomar un paquete de datos (una recopilación de datos) y dividirlo en paquetes separados. Estos paquetes se pueden procesar individualmente en módulos posteriores. </p><p>Para obtener más información, consulte <a href="/help/workfront-fusion/references/modules/iterator-module.md" class="MCXref xref">[!UICONTROL Iterator] módulo</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Módulo</p> </td> 
   <td> <p>Un solo paso dentro de un escenario que realiza una función, como crear un registro, dentro de la aplicación o servicio asociado.</p> <p>Cada aplicación o servicio tiene varios módulos que definen la forma en que responde a solicitudes.</p>  <p> <img src="assets/module.png"> </p> <p>Para obtener más información, consulte <a href="/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md" class="MCXref xref">Resumen del módulo</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Operación</p> </td> 
   <td> <p>Una tarea realizada por un módulo, como recuperar un registro o cargar un archivo.</p><p>Para obtener más información, consulte <a href="/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/operations-in-workfront-fusion.md" class="MCXref xref">Operaciones</a>.</p>
  </tr> 
  <tr> 
   <td role="rowheader">Claves públicas/privadas</td> 
   <td>Las claves públicas y privadas se utilizan para cifrar y descifrar datos. La clave pública se puede distribuir y cualquier persona que la tenga puede cifrar datos, pero solo la clave privada puede descifrarlos. Del mismo modo, un usuario con una clave privada podrá cifrar datos que cualquier persona que tenga la clave pública podrá descifrar. El cifrado de clave privada garantiza que los datos provengan del propietario de la misma y sirve como validación de la fuente de los datos.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Enrutador</p> </td> 
   <td>Un enrutador le permite duplicar datos o agregar nuevas rutas a un escenario, para volver a enrutar datos y administrar diferentes grupos de datos por separado.</p><p> Para obtener más información, consulte <a href="/help/workfront-fusion/create-scenarios/add-modules/router-module.md" class="MCXref xref">[!UICONTROL Router] módulo</a>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Escenario</p> </td> 
   <td> <p>Serie creada por el usuario de pasos automatizados, cada uno representado y realizado por un módulo. El propósito de un escenario es mover y manipular datos.</p> <p> <img src="assets/entire-scenario-blank.png" style="width: 350;height: 178;"> </p> <p> Para obtener más información, vea <a href="/help/workfront-fusion/get-started-with-fusion/understand-fusion/scenario-overview.md" class="MCXref xref">Información general sobre escenarios</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Segmento de escenario</p> </td> 
   <td> <p> Un segmento de escenario es una sección de un escenario que consta de una serie de módulos que se conectan todos a la misma aplicación. Los segmentos de escenario suelen representar un flujo de trabajo corto en la aplicación.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Activador</p> </td> 
   <td> <p>Un déclencheur es un tipo de módulo que inspecciona la existencia de datos nuevos y actualizados, e inicia el escenario cuando se aplican determinadas condiciones configuradas en el módulo. Los déclencheur se pueden configurar para que comiencen un escenario según una programación (sondeo) o siempre que se produzcan cambios en los datos (déclencheur instantáneo o gancho web).</p> <p>Para obtener más información, consulte <a href="/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md" class="MCXref xref">Déclencheur</a> en el artículo Información general del módulo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Webhook</p> </td> 
   <td> <p>Un tipo especial de déclencheur que le permite ejecutar un escenario inmediatamente después de que haya un nuevo paquete disponible. </p><p>Para obtener más información, consulte <a href="/help/workfront-fusion/references/modules/webhooks-reference.md" class="MCXref xref">déclencheur instantáneos (webhooks)</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>
