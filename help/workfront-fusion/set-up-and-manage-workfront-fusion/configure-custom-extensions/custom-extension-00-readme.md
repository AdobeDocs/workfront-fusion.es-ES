---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: 'Extensiones de IU personalizadas: índice de artículos'
description: Extensiones personalizadas en Workfront Fusion
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: a9dd86f7dc4070ad98c7c4a526a6a38939097940
workflow-type: tm+mt
source-wordcount: 603
ht-degree: 3%

---


# Extensiones de IU personalizadas: índice de artículos

Fusion puede mostrar su propia interfaz de usuario web dentro de su interfaz. Cuando se crea una pequeña aplicación web, denominada extensión, se publica en Adobe y aparece como un botón en la navegación de Fusion. Cuando un usuario hace clic en él, la interfaz de usuario se carga en el área principal de Fusion y recibe automáticamente información sobre quién ha iniciado sesión, en qué organización y equipo está trabajando, etc.

Esta sección de la documentación de fusión le explica todo el proceso, sin asumir una experiencia previa con Adobe App Builder o marcos de trabajo front-end. También incluye el código necesario, junto con explicaciones de ese código.

## Cuándo utilizar esta guía

Utilice esta guía si desea añadir una pantalla o herramienta personalizada a Fusion. No necesita ser un desarrollador experto. Debe sentirse cómodo copiando comandos en un terminal y editando algunos archivos de texto.

Para crear una extensión de IU personalizada, necesitará una Adobe ID y acceso a una organización de Adobe (el mismo tipo de acceso que utiliza para iniciar sesión en Fusion).

## Qué va a generar

Al final de esta guía encontrará lo siguiente:

1. Un proyecto Adobe **App Builder** gratuito. Aquí es donde reside su extensión.
1. Una pequeña aplicación web que procesa la interfaz de usuario personalizada.
1. Esa aplicación web se conectó a uno de los puntos de extensión de Fusion, por lo que aparece en la navegación de Fusion.
1. La interfaz de usuario lee el contexto en directo desde Fusion, como el usuario, la organización y el equipo actuales, y reacciona cuando el usuario cambia de organización o equipo.
1. La extensión publicada para que otros usuarios de su organización puedan verla.

<!--

## How it works, in one picture

```
  Fusion (the "Host")                         Your extension (the "Guest")
  ───────────────────────────────                         ──────────────────────────────
  Left navigation                             A web app hosted by Adobe
   └── Organization                            (App Builder + UI Extensibility)
       └── [Your extension button]  ── click ──▶ Fusion opens your UI in an iframe
                                              and sends it live context:
                                               * signed-in user
                                               * active organization
                                               * active team
                                               * Adobe IMS identifiers
```

Fusion is the **host**. Your extension is the **guest**. They run in separate browser frames and talk to each other through Adobe's **UI Extensibility SDK** (no custom networking required on your side).

-->

## Índice

Lea las páginas en orden la primera vez. Más tarde puede saltar directamente a la que necesita.

| # | Página | Qué cubre |
| --- | ------ | ---------------- |
| 1 | [Información general y conceptos clave](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-01-overview.md) | El vocabulario, la arquitectura y para qué sirve cada punto de extensión de Fusion. |
| 2 | [Configurar las herramientas y la cuenta de Adobe](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-02-set-up-tools-account.md) | Node.js, la CLI de Adobe I/O, el inicio de sesión y la creación del proyecto en Adobe Developer Console. |
| 3 | [Cree el proyecto y configúrelo para Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-03-04-create-project-configure-fusion.md) | Genere un proyecto de App Builder genérico con la línea de comandos `aio` (no una plantilla específica de producto). A continuación, coloque el proyecto en un punto de extensión de Fusion y registre el widget. |
| 5 | [Generar la interfaz de usuario](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-05-build-ui-procedure.md) | Procese su pantalla personalizada y complete la conexión (&quot;protocolo de enlace&quot;) con Fusion. |
| 6 | [La referencia de contexto de Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md) | Cada campo que Fusion le envía, lo que significa y cómo reaccionar ante los cambios. |
| 7 | [Publicar su extensión](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-07-publish.md) | Cree, implemente y haga visible su extensión en Fusion. |
| 8 | [Resolución de problemas](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-08-troubleshooting.md) | Correcciones de los errores más comunes. |
| 9 | [Recorrido de demostración](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-09-demo-walkthrough.md) | Un script lineal de copia y pegado: andamio de la plantilla genérica del shell de Experience Cloud → volver a destino para Fusion → implementarlo para ensayo → ejecutarlo en Fusion. Lo mejor para una demostración en vivo. |
| 10 | [Llamando a las API de Workfront y Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-10-calling-apis.md) | Llame a las API de back-end desde la extensión sin visitar el explorador CORS, mediante un proxy de tiempo de ejecución-acción. Abarca `require-adobe-auth`, encabezados de Fusion v3 y un ejemplo que funcionó. |

## Nota de disponibilidad

Fusion expone actualmente estos puntos de extensión:

* `fusion/nav-organization/1` — aparece en la sección **Organización**.
* `fusion/nav-team/1` — aparece en la sección **Equipo**.

Antes de poder publicar con uno de estos, el punto de extensión debe estar incorporado para su organización de Adobe. Si el paso de publicación falla al indicar que el punto de extensión &quot;no existe&quot;, consulte [Solución de problemas](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-08-troubleshooting.md).

## Documentación oficial de Adobe

Esta guía es específica de Fusion. Para la plataforma subyacente, las referencias canónicas son:

* [Información general de extensibilidad de IU](https://developer.adobe.com/uix/docs/)
* [Flujo de desarrollo de extensión de IU](https://developer.adobe.com/uix/docs/guides/development-flow/)
* [Administración de extensiones de IU (publicar/aprobar/revocar)](https://developer.adobe.com/uix/docs/guides/publication/)
* [Introducción a Adobe App Builder](https://developer.adobe.com/app-builder/docs/getting_started/)
