---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: fusion
navigation-topic: workfront-fusion-navigation-topic
title: Publicación de la extensión personalizada
description: Publicación de la extensión personalizada
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: 925a8ee910434c474d527c2914897d7c42e4a3d1
workflow-type: tm+mt
source-wordcount: 1236
ht-degree: 1%

---

# Publicación de la extensión personalizada

>[!NOTE]
>
>Este artículo asume cierta familiaridad con las herramientas de desarrollo de software.

La extensión se ejecutará en Fusion solamente después de que se haya **creado**, **implementado** en Adobe y **aprobado** para su organización. Los procedimientos de esta página muestran cómo publicar la extensión y cómo comprobar el resultado.

Esta información está adaptada de la documentación oficial de Adobe y se aplica específicamente a Workfront Fusion. Para obtener la información general de Adobe, consulte [Flujo de desarrollo de extensiones de IU](https://developer.adobe.com/uix/docs/guides/development-flow/) y [Administración de extensiones de IU](https://developer.adobe.com/uix/docs/guides/publication/) en la documentación de Adobe.

## Espacios de trabajo

Cada proyecto de App Builder tiene **Stage** y **Production** Workspace. Considérelos como entornos:

* **Stage** está destinado a desarrollo y pruebas. Se implementa aquí mientras se itera. No se requiere aprobación y el resultado solo es visible a través del interruptor de prueba de Fase que se describe a continuación (o vista previa local).
* **Producción** es para liberarlo para todos. Después de implementar en Producción, envía una **solicitud de aprobación** y, una vez aprobada, la extensión se registra en el Registro de aplicaciones de Adobe y se muestra a toda la organización.

>[!NOTE]
>
> **Roles:** la creación y la implementación necesitan el rol de **Desarrollador**; el envío de la solicitud de aprobación para la publicación necesita un rol de **Administrador del sistema**.
>Para obtener más información, consulte:
>
> * [Configurar las herramientas y la cuenta de extensión de la interfaz de usuario](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-02-set-up-tools-account.md)
> * [Cómo obtener acceso](https://developer.adobe.com/uix/docs/guides/get-access/) en la documentación de Adobe.

De forma predeterminada, Fusion solo muestra **extensiones publicadas**. Son extensiones que ha implementado en el área de trabajo **Producción** y que luego envió para su **aprobación**. Este es el valor predeterminado seguro, por lo que una implementación de trabajo en curso nunca se mostrará a toda la organización por accidente.

Una implementación en el área de trabajo **Stage** no se ha publicado, por lo que no aparece en Fusion por sí sola. Existen dos formas de probar una extensión antes de publicarla:

* **Vista previa local** con `aio app run` (consulte [Vista previa local de las extensiones de la interfaz de usuario](https://developer.adobe.com/uix/docs/guides/preview-extension-locally/) en la documentación de Adobe). No se implementa nada y solo usted lo ve.
* **Cárguelo desde el escenario dentro de Fusion** activando un conmutador de prueba por usuario en su perfil de Fusion. Esto se describe en [Probar una compilación de fase en Fusion](#test-a-stage-build-in-fusion) en este artículo.

## Prueba de una compilación de fase en Fusion

Utilice este flujo para ver cómo se implementa una fase dentro de Fusion antes de publicarla.

### Paso 1: Selección del espacio de trabajo de ensayo

```sh
aio console where                  # shows current org / project / workspace
aio console workspace select       # choose Stage
```

### Paso 2: Generación

```sh
aio app build
```

Esto compila el front-end y ejecuta el enlace de metadatos (que genera `app-metadata.json`). Corrija los errores notificados antes de continuar.

### Paso 3: Implementación

```sh
aio app deploy
```

`deploy` hace dos cosas:

* **Aloja su interfaz de usuario** en la red de distribución de contenido de Adobe, en una dirección URL como `https://<project>-stage.adobeio-static.net`. La CLI imprime esta **URL de extremo de extensión** cuando finaliza. Esta es la URL que Fusion carga en su iframe.
* **Registra los extremos de su extensión** para el punto de extensión (`fusion/nav-organization/1`) en el espacio de trabajo de ensayo.

>[!TIP]
>
> **Si la implementación falla con &quot;El punto de extensión &#39;fusion/nav-organization/1&#39; no existe&quot; (error 1060):**, el punto de extensión de Fusion aún no está habilitado para su organización. Este es un paso de incorporación, no un error en el código.
>Para obtener más información, consulte [El punto de extensión no existe](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-08-troubleshooting.md#error-1060-extension-point-does-not-exist) en el artículo de solución de problemas.

### Paso 4: Activar las pruebas de ensayo en su perfil de Fusion

Fusion carga extensiones de fase solo cuando usted decide adherirse, por usuario:

1. Inicie sesión en Fusion con una cuenta en la **misma organización** que implementó en.
1. Abra el menú de avatar del usuario en la esquina superior y vaya a **Configuración del producto** > **Perfil Fusion** > **Preferencias**.
1. Active el conmutador **Extensiones de fase**.

   Fusion le pedirá que vuelva a cargar.
1. Confirme la recarga.

Después de la recarga, Fusion carga las extensiones del espacio de trabajo de fase en lugar del conjunto publicado y etiqueta cada uno **(fase)** en la navegación para que pueda distinguirlos.

Este conmutador es una configuración de prueba personal almacenada en el explorador, no una configuración de organización. Desactívela (y vuelva a cargarla) para volver a las extensiones publicadas. Como se almacena localmente, no le sigue a otro explorador o equipo.

### Paso 5: Verificar en Fusion

1. Abra la sección que coincida con el punto de extensión:
   * `fusion/nav-organization/1` → el área **Organización** de la navegación izquierda.
   * `fusion/nav-team/1` → el área **Equipo** (seleccione un equipo primero).

   Aparece un botón con el título que ha establecido en `getWidget()`, marcado como **(fase)**.
1. Haga clic en el botón que apareció.

La interfaz de usuario carga y recibe [Fusion context](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md).

Si el botón no aparece o el panel muestra un error, consulte [Solución de problemas](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-08-troubleshooting.md).

## Versión en producción

Cuando la extensión funcione en Fase y esté listo para todos los usuarios:

### Paso 1: Cambiar al espacio de trabajo de producción

```sh
aio console workspace select       # choose Production
```

Cuando la CLI le pregunte acerca del archivo `.env`, seleccione **Combinar** para conservar las variables de entorno.

### Paso 2: Generar e implementar en producción

```sh
aio app build
aio app deploy
```

### Paso 3: Envío de la solicitud de aprobación

La publicación es una **solicitud de aprobación enviada desde el área de trabajo de producción**:

1. Abra [Adobe Developer Console](https://developer.adobe.com/console), seleccione su **organización**, abra su **proyecto** y cambie al área de trabajo **Producción**.
1. Envíe su aplicación para **aprobación / publicación** (esto requiere el rol de **Administrador del sistema**).
1. Después de la aprobación, su extensión se agregará al **Registro de aplicaciones de Adobe** y estará disponible en [Adobe Experience Cloud](https://experience.adobe.com), incluida Fusion, para su organización.

Para obtener instrucciones detalladas, consulte [Administración de extensiones de IU](https://developer.adobe.com/uix/docs/guides/publication/) en la documentación de Adobe Developer.

## Estado y actualizaciones

Vale la pena conocer algunos comportamientos para poder saber que &quot;aún se está trabajando en ello&quot; aparte de &quot;algo está mal&quot;:

* **Implementado en producción no es lo mismo que visible.** `aio app deploy` a Producción carga la aplicación, pero no hace que aparezca la extensión. Solo aparece después de enviar y aprobar la solicitud de aprobación. Si ha implementado en Producción y aún no lo ve en Fusion, el motivo habitual es que aún no se ha aprobado.
* **Las actualizaciones solo de código no necesitan una nueva aprobación.** Si la extensión ya se ha publicado y solo cambia su código (la interfaz de usuario o las acciones en tiempo de ejecución), vuelva a implementar en la misma URL con:

  ```sh
  aio app deploy --force-deploy
  ```

  Los usuarios obtienen la nueva versión la próxima vez que abran la extensión. No hay nada que puedan instalar. Solo necesita enviar una nueva solicitud de aprobación cuando cambie el propio **registro**, por ejemplo, agregando un nuevo punto de extensión o cambiando lo que anuncia `getWidget()`.
* **Desaparece una extensión revocada o retirada.** Si usted revoca o retira una extensión, esta deja de aparecer en Fusion sin mensaje de error. Si una extensión que funcionaba anteriormente desaparece para todos, compruebe si se revocó antes de buscar un problema de código.

## Eliminación (revocación) de una extensión

La eliminación de una extensión publicada se realiza **revocándola** en Adobe Exchange:

1. Iniciar sesión en **Adobe Exchange**.
1. Vaya a **Administrar** > **Aplicaciones App Builder**.
1. Seleccione **Revocar** junto a la extensión que desee quitar y confirme.

Después de revocar, la extensión muestra el estado *revocado* en Extension Manager y ya no aparece en Fusion. Para eliminarlo por completo, elimine el proyecto en Developer Console. Un proyecto no se puede eliminar hasta que se revoque su extensión.

Para una implementación de prueba solo de fase, puede eliminar la implementación con:

```sh
aio app undeploy
```

## Recursos adicionales

Los siguientes recursos están disponibles en la documentación de Adobe:

* [Flujo de desarrollo de extensión de IU](https://developer.adobe.com/uix/docs/guides/development-flow/)
* [Administración de extensiones de IU (publicar/aprobar/revocar)](https://developer.adobe.com/uix/docs/guides/publication/)
* [Creación de un proyecto en Developer Console](https://developer.adobe.com/uix/docs/guides/creating-project-in-dev-console/)
* [Cómo obtener acceso (funciones)](https://developer.adobe.com/uix/docs/guides/get-access/)
* [Vista previa local de extensiones de IU](https://developer.adobe.com/uix/docs/guides/preview-extension-locally/)
