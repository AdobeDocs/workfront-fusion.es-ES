---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: Información general de extensibilidad de IU
description: Extensiones personalizadas en Workfront Fusion
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: 925a8ee910434c474d527c2914897d7c42e4a3d1
workflow-type: tm+mt
source-wordcount: 835
ht-degree: 0%

---

# Información general de extensibilidad de IU

La extensibilidad de la interfaz de usuario le permite incorporar su lógica personalizada y su interfaz de usuario (interfaz de usuario) en Adobe Workfront Fusion. Con Adobe App Builder, puede modificar la experiencia de Workfront Fusion de su organización para satisfacer mejor las necesidades de la organización, sin dejar de depender de la funcionalidad principal de Fusion.

Este artículo ofrece información general sobre la extensibilidad de la interfaz de usuario y cómo se comunica la extensión personalizada con Workfront Fusion.

## Estructura de las extensiones

* [Hosts e invitados](#hosts-and-guests)
* [La tecnología subyacente](#the-technology-underneath)

### Hosts e invitados

Fusion puede mostrar la interfaz de usuario que no haya creado el equipo de Workfront Fusion. Para asegurarse de que estos cambios en la interfaz de usuario no afecten a la funcionalidad principal de Fusion, la interfaz de usuario se ejecuta en su propio marco de navegador aislado (un `<iframe>`), completamente independiente del código de Fusion.

* **Host**: La aplicación que *contiene* la extensión. Aquí, ese es **Fusion**. El host decide dónde pueden aparecer las extensiones y qué datos compartirá con ellas.
* **Invitado**: *Su* extensión. Es una pequeña aplicación web que el host carga en un iframe.

Al crear una extensión de interfaz de usuario, no modifica Fusion. Puede crear y publicar un invitado, que Fusion puede utilizar después de que se publique el invitado.

### La tecnología subyacente

Su invitado está construido con dos tecnologías de Adobe:

* **Adobe App Builder**: Una plataforma de alojamiento y herramientas gratuita para pequeñas aplicaciones web y acciones sin servidor. La extensión es una aplicación de App Builder. App Builder le proporciona un lugar en el que alojar la interfaz de usuario (en la red de distribución de contenido `*.adobeio-static.net` de Adobe) y una herramienta de línea de comandos llamada `aio` para crearla, crearla y publicarla.
* **SDK de extensibilidad de la interfaz de usuario de Adobe (UIX)**: Las bibliotecas que permiten hablar al host y al invitado. Utilizará un paquete, `@adobe/uix-guest`, de su lado. Fusion utiliza el paquete `@adobe/uix-host` coincidente de su lado.

<!--

```
   ┌────────── Browser ─────────────────────────────┐
   │                                                                   │
   │   Fusion (Host)                      Your extension (Guest)       │
   │   ────────────                       ─────────────────────        │
   │   @adobe/uix-host   ◀── messages ──▶  @adobe/uix-guest            │
   │        │                                    │                     │
   │   renders an iframe ───────────────▶  your React/HTML UI          │
   │                                                                   │
   └───────────────────────────────────────────────────────────────────┘

   Your UI files are hosted by Adobe App Builder at
   https://<your-app>.adobeio-static.net
```

-->

## Puntos de extensión

Un punto de extensión es una &quot;ranura&quot; con nombre en el host en la que se permite la aparición de un invitado. Fusion define sus espacios y usted elige cuál usará el huésped.

Un nombre de punto de extensión tiene tres partes: `service/name/version`.

Fusion ofrece los siguientes puntos de extensión:

| Punto de extensión | Dónde aparece la interfaz de usuario en Fusion | Cuándo se debe utilizar |
| --- | --- | ---- |
| `fusion/nav-organization/1` | En la sección **Organización** de la navegación izquierda. | Su herramienta es sobre toda la organización. |
| `fusion/nav-team/1` | En la sección **Equipo** de la navegación izquierda (se muestra cuando se selecciona un equipo). | La herramienta trata sobre un equipo específico. |

* `fusion` es el **servicio** (el producto, Fusion).
* `nav-organization` / `nav-team` es el **nombre** (la ranura específica).
* `1` es la **versión**.

Una extensión puede implementar uno o ambos puntos de extensión. La mayoría de las extensiones utilizan un punto.

En función del punto de extensión seleccionado, Fusion añade un botón con el título de la extensión a la sección de navegación correspondiente. Al hacer clic en él, se abre una página dedicada en el área de contenido principal de Fusion y se carga la interfaz de usuario allí.

## Marcos incluidos en una extensión de IU

>[!IMPORTANT]
>
>En esta sección se analiza un aspecto de las extensiones de interfaz de usuario que puede causar confusión. Recomendamos leerlo con cuidado.

Cuando Fusion cargue su invitado, su extensión se ejecutará en **dos** fotogramas:

1. **Marco de registro (invisible).** Se ejecuta primero, en segundo plano. El marco de registro indica a Fusion lo que ofrece su extensión. Por ejemplo, puede indicar que tiene un widget de panel y enviar el título del widget y la dirección URL de su interfaz de usuario. El marco de registro hace esto llamando a `register(...)`. No procesa ninguna interfaz de usuario visible.
1. **Marco de la interfaz de usuario (visible).** Esta es la página que Fusion muestra al usuario. Debe anunciarse al host llamando a `attach(...)`. Si nunca llama a `attach`, Fusion espera y finalmente agota el tiempo de espera con un error.

>[!BEGINSHADEBOX]

Este ejemplo muestra el flujo cuando un usuario hace clic en el botón de extensión.

1. Se hace clic en el botón.
1. Fusion carga su cuadro de REGISTRO (oculto).

   ```
   register({ methods: { dashboard: { getWidget() {...} } } })
   ```

   `getWidget()` devuelve la dirección URL de su IU visible
1. Fusion carga el marco de la interfaz de usuario (visible) en esa dirección URL.

   ```
   attach({ id }) 
   ```

   Es obligatorio o se agota el tiempo de espera de Fusion
1. Fusion envía el contexto y la interfaz de usuario se procesa.

>[!ENDSHADEBOX]

Ambos marcos se escriben al crear la interfaz de usuario. Lo importante es recordar que la página visible **debe** llamar a `attach`.

Para obtener más información sobre cómo generar la interfaz de usuario, consulte [Crear la interfaz de usuario de la extensión personalizada](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-05-build-ui-procedure.md).

## Contexto de Fusion

Una vez adjunta la extensión, Fusion comparte un objeto `context` con el invitado. Contiene:

* **Usuario**: El perfil Fusion del usuario que inició sesión y el ID de usuario de Adobe IMS.
* **Organización**: el registro de organización Fusion completo de la organización activa y el ID de organización IMS de Adobe.
* **Equipo**: El equipo activo, cuando corresponda.
* **Token de acceso de Adobe IMS**: Llama a las API de Adobe o Fusion en nombre del usuario, si es necesario.

Fusion también inserta actualizaciones. Por ejemplo, si el usuario cambia de organización o de equipo mientras la interfaz de usuario está abierta, Fusion enviará el nuevo contexto para que la interfaz de usuario pueda reaccionar al instante.

Para obtener la lista completa de campos de contexto, consulte [La referencia de contexto de Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md).

## Creación de una extensión de IU

Para crear una extensión de interfaz de usuario, siga estos pasos:

1. [Instalar herramientas y crear un proyecto de Adobe](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-02-set-up-tools-account.md).
1. [Genere un proyecto App Builder en blanco, diríjalo a un punto de extensión Fusion y registre su widget](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-03-04-create-project-configure-fusion.md).
1. [Cree la interfaz de usuario y conéctese a Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-05-build-ui-procedure.md).
1. [Usar el contexto que Fusion envía](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md).
1. [Publicar para que Fusion pueda encontrarlo](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-07-publish.md).
1. (Opcional) [Llame a las API de Workfront/Fusion para obtener datos reales sin CORS](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-10-calling-apis.md).

Para comenzar el proceso, ve a [Configurar tus herramientas y tu cuenta de Adobe](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-02-set-up-tools-account.md).


