---
title: Uso de archivos grandes
description: Actualmente, se admite archivos grandes para los conectores Workfront y HTTP.
author: Becky
feature: Workfront Fusion
exl-id: 6df81943-e70c-42b3-aa44-d82343598a51
source-git-commit: c4696ad91dd0a2cf753147bffbb6e7b74bb99b02
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 0%

---

# Uso de archivos grandes

>[!IMPORTANT]
>
>La funcionalidad de archivos de gran tamaño solo está disponible para los clientes de Workfront Ultimate y se está implementando por fases. Todas las organizaciones de Fusion con un plan de Ultimate de Workfront tendrán capacidad de archivos de gran tamaño en enero de 2025.

Las funciones mejoradas de transferencia de datos ya están disponibles en Workfront Fusion, lo que permite a los escenarios procesar archivos considerablemente más grandes.

Para gestionar archivos de mayor tamaño, se deben actualizar los escenarios.

>[!NOTE]
>
>Esta funcionalidad solo está disponible para los usuarios con el paquete Ultimate Workfront.

## Conectores compatibles con archivos grandes

Para la versión inicial, los siguientes conectores admiten archivos grandes.

* Workfront > Cargar documento
* Adobe Experience Manager Assets > Cargar documento
* Workfront Proof > Cargar archivo
* Adobe Authenticator > Realizar una llamada de API personalizada
* SharePoint > Crear un archivo y SharePoint > Obtener un archivo
* Salesforce > Cargar archivo
* AWS S3 > Cargar archivo y AWS S3 > Obtener archivo
* HTTP

En futuras versiones se admitirán otros conectores.

## Actualice los escenarios para gestionar archivos grandes

El módulo Workfront > Cargar documento se ha modificado para gestionar archivos de mayor tamaño. La versión anterior de este módulo ahora muestra `(Legacy)` anexado al nombre del módulo. En la mayoría de los casos, el módulo heredado seguirá funcionando.

Si planea trabajar con archivos más grandes, le recomendamos reemplazar el módulo heredado con el nuevo módulo Cargar documento. El nuevo módulo Cargar documento evita tiempos de espera y otros errores.

![Subir documento](assets/new-upload-document.png)

## Preguntas frecuentes

### ¿Cuál es el nuevo límite de tamaño de archivo?

Los usuarios ahora pueden procesar archivos que superen el límite anterior de 1 GB, lo que mejora la eficiencia y la productividad.  Aunque la plataforma puede admitir archivos individuales de hasta 15 GB para una sola acción (como cargar un archivo), hay otros factores que afectan a la transferencia de datos. El límite de tamaño de archivo de una sola acción depende en última instancia del servicio web al que se conecta Fusion. La transferencia de datos es el procesamiento total de una sola ejecución. Esto significa que varias acciones en una sola ejecución contribuyen a la transferencia total de datos.

Fusion procesa los archivos hasta que se alcanza el límite de ejecución de 40 minutos. Los archivos grandes pueden tardar algún tiempo en cargarse, descargarse o procesarse en su escenario de Fusion. Aunque no hay límite en el tamaño de archivo individual, hay un límite de 40 minutos en el tiempo de ejecución del escenario. Por lo tanto, si los archivos grandes hacen que la ejecución tarde más de 40 minutos, el escenario falla. El tiempo de ejecución de un escenario también puede verse afectado por el tamaño del escenario, la complejidad del módulo y la velocidad de la red. Por lo tanto, le recomendamos que tenga en cuenta estos aspectos de los escenarios al utilizar archivos grandes.

### ¿Cómo funciona la nueva transferencia de archivos de Fusion?

Cuando Fusion procesa archivos, los archivos más grandes se añaden al almacenamiento persistente (S3 Bucket o Azure Blob Storage). Cuando un módulo de Fusion ejecuta una acción de archivo, como cargar o descargar, Fusion utiliza el archivo en almacenamiento persistente como fuente en lugar de la memoria activa.

### ¿Puedo trabajar con archivos más grandes con ejecuciones incompletas?

Sí, Fusion admite ejecuciones incompletas con archivos de mayor tamaño. Tenga en cuenta que las ejecuciones incompletas tienen un tamaño limitado para una organización y deben administrarse de forma activa.

### ¿Puedo utilizar archivos más grandes con cualquier conector?

Cada conector Fusion debe actualizarse para admitir archivos de mayor tamaño. Los conectores admitidos son Workfront, HTTP y AEM Assets. Los conectores Fusion siguen estando limitados por el tamaño de archivo admitido por el servicio web. Los límites de tamaño de archivo generalmente se incluyen en la documentación de la API para puntos finales de servicios web que descargan y cargan archivos.

### ¿Afecta esto a las operaciones?

No, el número de operaciones ejecutadas por un módulo es el mismo.

### ¿Cuándo se actualizará la interfaz de usuario de Fusion para mostrar los datos de transferencia de archivos?

Estamos trabajando activamente en las actualizaciones de la IU de Fusion para la transferencia de archivos en el tablero y en la página de detalles de la ejecución del escenario, con una versión objetivo en el primer trimestre de 2025.

### ¿Cuáles son algunas formas de pensar acerca de los nuevos límites de procesamiento de archivos que me ayudarán a diseñar escenarios?

Diseñar un escenario para que funcione dentro del límite de ejecución de 40 minutos puede parecer complicado. Se recomienda tener en cuenta lo siguiente al diseñar un escenario:

* **Comprenda sus requisitos empresariales para el tiempo de ejecución**: El límite de tiempo de ejecución de Fusion para la plataforma es de 40 minutos, pero se espera que la mayoría de las automatizaciones de procesos empresariales se ejecuten mucho más rápido. Por ejemplo, se esperaría que las automatizaciones iniciadas por el usuario con una continuación dependiente de los resultados se completaran muy por debajo del límite de 40 minutos.
* **Tenga en cuenta el tiempo de ejecución al diseñar**: Al diseñar su escenario, es esencial comprender el tiempo de ejecución del módulo para acciones de archivo individuales, como cargas y descargas. Este conocimiento le ayuda a planificar escenarios que implican varias acciones de archivo.  Para garantizar la precisión en el diseño, se recomienda redondear el tiempo de ejecución del módulo hasta incluir un búfer.
Por ejemplo, si Fusion descarga un documento en 144 segundos (2,4 minutos), puede anticipar que una sola ejecución puede realizar acciones similares varias veces. En este ejemplo, la ejecución del módulo tarda 144 segundos en ejecutarse y debe planificar durante 3 minutos el tiempo de ejecución para la descarga. Si sus requisitos incluyen una carga y una descarga, el tiempo de ejecución esperado sería de aproximadamente 6 minutos. Tenga en cuenta que los tiempos de ejecución de Fusion se limitan a 40 minutos.

* **Consolidar acciones de archivo**: el ejemplo más común de acciones de archivo en un escenario de Fusion es una descarga y una carga. La mayoría de los escenarios con solo estas dos acciones se ejecutarán en unos minutos. Cuando sea posible, los diseñadores de Fusion deben restringir sus escenarios a una descarga y una carga.

* **Calcular tamaño mediante el panel de asignación**: Workfront y otros servicios web incluyen el tamaño de archivo de un archivo en la salida del módulo de descarga. Puede utilizar estos datos para filtrar los archivos demasiado grandes para una carga de módulo o demasiado grandes para el tiempo de ejecución del escenario.

* **Aísle las acciones de archivo en su propio escenario cuando trabaje con varios archivos**: los diseñadores de Fusion deben considerar la posibilidad de aislar las acciones de archivo en escenarios separados. Por ejemplo, un escenario de Fusion activado por una nueva solicitud de Workfront con varios archivos adjuntos puede necesitar acomodar hasta 30 archivos. Dado que cargar y descargar cada archivo puede llevar hasta 3 minutos, procesar todos los archivos en una sola ejecución superaría el límite de ejecución de 40 minutos de Fusion. La solución es crear un escenario de acciones de archivo dedicado a administrar la carga y descarga de archivos individuales. El escenario activado por la solicitud se reproduciría a través de los archivos adjuntos, invocando el escenario de acciones de archivo para cada archivo usando el módulo HTTP. Este método garantiza que cada archivo se procese dentro de los límites de tiempo de ejecución.

<!--
## Connectors that do not support large files

Some Fusion connectors do not support large files. For these connectors, Fusion's total processing capacity for files is **1 GB**. 

This limit is based on a total memory cost. Every operation contributes to that cost. If a single file of 400 MB is downloaded and uploaded then the total cost to the file capacity would be 800 MB.

The following connectors do **not** support large files. 

* Archive
* Box
* Convert
* CSV
* Datastores
* Flow control
* FTP
* JSON
* JWT
* Markdown
* Math
* Microsoft Word templates
* MIME
* Microsoft SQL
* SFTP
* Adobe Acrobat Sign
* SOAP
* Tools
* XML

If a connector is not on this list, it does not support large files. For these connectors, Fusion's total processing capacity for files is **1 GB**. 

This limit is based on a total memory cost. Every operation contributes to that cost. If a single file of 400 MB is downloaded and uploaded then the total cost to the file capacity would be 800 MB.-->






<!--## Connectors that support large files

The following connectors support large files.

Workfront
HTTP
Webhooks
Salesforce
Microsoft Email
Workfront Proof
AEM Assets
Email
Slack
Jira
Microsoft Excel
SharePoint
Frame.io
Adobe PDF Services
Marketo
Azure Devops 
Google Email
Jira Server
Google Sheets
Microsoft OneDrive
ServiceNow 
AWS S3
Bynder
OneDrive Business
Adobe Authenticator
Google Drive
Microsoft Dynamics
Google Docs
NetSuite
Airtable
Azure AD
QuickBase 
Adobe Target
Adobe Campaign Classic
Microsoft Calendar
Workfront Planning
HubSpot CRM  
DropBox
Cloud Convert
Egnyte
Adobe Firefly
OpenAI / Chat GPT
Allocadia
Cvent
GitLab 
Google Team Drive
Google Calendar
Workfront SDL Managed Translation
Widen
Workfront Boards
Google Slides
Qualtrics
Microsoft Power BI
Adobe Photoshop
Anaplan
DocuSign 
MariaDB
Adobe Creative Cloud Libraries
Figma
AEM Forms
Datadog
GitHub 
Google Forms
Adobe I/O Events
Trello
Workday
Adobe Journey Optimizer
Adobe Lightroom


If a file is not on this list, it does not support large files. For these connectors, Fusion's total processing capacity for files is **1 GB**. 

This limit is based on a total memory cost. Every operation contributes to that cost. If a single file of 400 MB is downloaded and uploaded then the total cost to the file capacity would be 800 MB.

-->
