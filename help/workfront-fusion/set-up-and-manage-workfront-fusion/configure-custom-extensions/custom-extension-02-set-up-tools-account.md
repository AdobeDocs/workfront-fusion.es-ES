---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: fusion
navigation-topic: workfront-fusion-navigation-topic
title: Configurar las herramientas y la cuenta de extensión de IU
description: Configurar las herramientas y la cuenta de extensión de IU
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
source-wordcount: 500
ht-degree: 0%

---


# Configurar las herramientas y la cuenta de extensión de IU

Para poder crear una extensión de la interfaz de usuario para Workfront Fusion, debe configurar sus herramientas y su cuenta. Esto solo debe hacerse una vez.

>[!NOTE]
>
>Este artículo asume cierta familiaridad con las herramientas de desarrollo de software.

<!--Access requirements-->

## Requisitos previos

Para configurar las herramientas y la cuenta de extensibilidad de la interfaz de usuario, necesita lo siguiente:

* **Un Adobe ID** con acceso a una organización de Adobe. Esta es la cuenta que utiliza para iniciar sesión en Fusion.
* **Acceso de desarrollador a App Builder.** Es posible que el administrador de su organización tenga que otorgarle la función **Desarrollador** y agregarlo a un **Perfil de producto** que incluya App Builder. Si más adelante los comandos fallan con &quot;usted no es un desarrollador&quot; o no puede ver su organización, pídale al administrador de organización de Adobe que le añada.
* **Administrador del sistema** <!--Adobe? Fusion?--> (posiblemente otro miembro de su equipo) para el paso final de la versión. La creación y la implementación solo necesitan la función de Desarrollador, pero **el envío de una extensión para su aprobación o publicación requiere la función de Administrador del sistema**.

  Para obtener más información sobre los niveles de acceso de Adobe, consulte
  [Cómo obtener acceso](https://developer.adobe.com/uix/docs/guides/get-access/) en la documentación de Adobe.

* **Equipo donde puede instalar software** y ejecutar comandos de terminal (macOS, Windows o Linux).

## Instalar Node.js

La herramienta Adobe se ejecuta en **Node.js**. Debe instalar la versión de **LTS** (18 o 20).

1. Vaya a <https://nodejs.org> y descargue el instalador **LTS**.
1. Ejecute el instalador y acepte los valores predeterminados.
1. Confirme que ha funcionado abriendo un terminal y ejecutando:

   ```sh
   node --version
   npm --version
   ```

   Debería ver los números de versión (por ejemplo, `v20.17.0` y `10.x`).

1. (Condicional) Si no se encuentra `node`, cierre y vuelva a abrir el terminal o reinicie el equipo.

1. Continúe con [Instalar la CLI de Adobe I/O (`aio`)](#install-the-adobe-io-cli-aio).

>[!TIP]
>
>* Si trabaja con varias versiones de nodo, es conveniente tener un administrador de versiones como `nvm`, pero es opcional.
>* La CLI de Adobe requiere el nodo 18 o posterior. Las versiones muy nuevas que no son de LTS pueden causar problemas ocasionalmente, por lo que recomendamos usar LTS.

## Instale la CLI de Adobe I/O (`aio`)

La herramienta de línea de comandos que usa para crear, generar y publicar la extensión se llama `aio`.

Para instalarlo globalmente:

1. Use el siguiente comando `npm` en la línea de comandos.

   ```sh
   npm install -g @adobe/aio-cli
   ```

1. Confirme que está instalado mediante el siguiente comando:

   ```sh
   aio --version
   ```

   Debería ver algo como `@adobe/aio-cli/11.x.x`.

1. Continuar a [Iniciar sesión en Adobe](#sign-in-to-adobe).

>[!NOTE]
>
> Si ve un error de permisos en macOS/Linux, **no** usa `sudo`. En su lugar, corrija los permisos de carpeta globales de npm o use un administrador de versiones de Node que se instale en su directorio personal.

## Iniciar sesión en Adobe

1. Conecte la CLI a su cuenta de Adobe mediante el siguiente comando:

   ```sh
   aio login
   ```

1. En la ventana del explorador que se abre, inicie sesión con su Adobe ID y apruebe el acceso.

1. Una vez que el inicio de sesión se haya realizado correctamente, cierre la pestaña del explorador y vuelva al terminal.

1. (Opcional) Para cerrar sesión más tarde (por ejemplo, para cambiar de cuenta), use el comando: `aio logout`.
1. Continuar a [Confirmar tu organización activa](#confirm-your-active-organization).

## Confirme su organización activa

Compruebe a qué organización apunta la CLI:

```sh
aio console org list      # see organizations you can use
aio console where         # see your currently selected org/project/workspace
```

Si pertenece a varias organizaciones, seleccione la correcta:

```sh
aio console org select
```

Ya está listo para crear el proyecto.
