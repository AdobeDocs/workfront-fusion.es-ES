---
title: Resumen de API
description: Las interfaces de programación de aplicaciones (API) son una forma de que las aplicaciones y los servicios se comuniquen entre sí. Fusion utiliza las API para comunicarse con la aplicación a la que se está conectando. Cada aplicación tiene una API independiente.
author: Becky
feature: Workfront Fusion
source-git-commit: b30aac8040cc0b6bcad92914b1c0997a8ddebdd5
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 0%

---

# Información general sobre las API de Fusion

<!--Add me to TOCs-->

Las interfaces de programación de aplicaciones (API) son una forma de que las aplicaciones y los servicios se comuniquen entre sí. Fusion utiliza las API para comunicarse con las aplicaciones a las que se conecta.

Los propietarios de la aplicación crean y controlan las API. Por ejemplo, la API de Workfront es propiedad del equipo de Workfront en Adobe y la API de Microsoft Graph es propiedad de Microsoft. El propietario de la API define qué acciones están disponibles a través de la API.

## Consideraciones

El hecho de que las API estén definidas por sus propietarios y no por Fusion lleva a algunas consideraciones importantes:

* **Puede usar Fusion para conectarse a cualquier aplicación o servicio que tenga una API pública**, independientemente de si Fusion ofrece o no un conector dedicado a esa aplicación o servicio. Puede utilizar los conectores universales de Fusion para incorporar estas aplicaciones o servicios a sus escenarios.

  Para obtener una lista de conectores universales, consulte [Conectores universales](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#universal-connectors).

* **Los cambios realizados por el propietario en la API de una aplicación pueden afectar a la funcionalidad de Fusion.** Si los cambios son lo suficientemente graves, Fusion puede necesitar actualizar módulos o tipos de conexión, o en casos extremos puede crear un nuevo conector para la aplicación.

  Para obtener más información sobre estas situaciones extremas, conocidas como &quot;cambios importantes&quot;, consulte [Cambios importantes](#breaking-changes) en este artículo.


## Cambios importantes

Una causa común de cambios importantes es la obsolescencia, cuando el propietario de una API elimina parte o la totalidad de una API de la disponibilidad. Cuando esto sucede, el equipo de Fusion hace todo lo posible para realinear rápidamente la funcionalidad de Fusion con la nueva versión de la API de la aplicación. Esto generalmente adopta la forma de nuevos módulos, tipos de conexión o conectores.

Como los escenarios de Fusion están configurados con los datos específicos, es posible que tenga que actualizar los escenarios.

* Si los cambios estaban relacionados con la autenticación o la autorización, es posible que tenga que actualizar las conexiones para esa aplicación.
* Si los cambios estaban relacionados con una acción específica (punto final) en la API, es posible que tenga que actualizar cualquier módulo relacionado con esa acción a una nueva versión del módulo.
* Si la versión completa de la API utilizada por Fusion está en desuso, es posible que tenga que actualizar todos los módulos de ese conector a una nueva versión.

En muchos casos, puede actualizar a la nueva versión de un módulo sin necesidad de volver a configurar ese módulo.

Para obtener información e instrucciones sobre cómo actualizar un módulo, vea [Actualizar un módulo a una nueva versión](/help/workfront-fusion/manage-scenarios/update-module-to-new-version.md).
