---
title: Metadatos de conexión
description: Fusion utiliza metadatos para identificar los atributos importantes de una conexión.
author: Becky
feature: Workfront Fusion
exl-id: b41fbe8c-30fa-49d0-8a24-3535642b97ae
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 61%

---

# Metadatos de conexión

Fusion utiliza metadatos para identificar los atributos importantes de una conexión.

Los metadatos de la conexión se pueden establecer al crear una nueva conexión. Estos atributos se encuentran en el mismo cuadro de diálogo que sirve para configurar una conexión:

![Metadatos de conexión](assets/connection-metadata-setup.png)

Los usuarios de Fusion pueden ver y editar conexiones desde el área Conexiones.

![Metadatos de conexión en el área Conexiones](assets/connections-area-metadata.png)

## Tipo de entorno

Las conexiones de Fusion las pueden utilizar tanto los sistemas de producción como los sistemas que no son de producción. Puede marcar el tipo de entorno al que se conecta una conexión, lo que ayuda a proteger los entornos de producción.

El tipo de entorno, como otros metadatos de conexión, se utiliza solo con fines informativos. Los usuarios son responsables de configurar con precisión este atributo y utilizar una conexión con el entorno correcto en un escenario.

## Tipo de autenticación

Las conexiones de Fusion se pueden utilizar tanto para cuentas de servicio como para cuentas personales. Las cuentas de servicio se utilizan para la autenticación cuando un escenario se automatiza como Fusion. Las cuentas personales son una autenticación basada en una persona específica. El tipo de autenticación que se use depende de los requisitos del escenario. Las cuentas personales deben utilizarse para las acciones automatizadas de los usuarios. Por ejemplo, si un escenario de Fusion automatiza la aprobación por parte de una persona específica, el tipo de autenticación debe ser para esa persona. De lo contrario, Fusion actúa como Fusion y el tipo debe ser Cuenta de servicio.

El tipo de autenticación, como otros metadatos de conexión, se utiliza únicamente con fines informativos. Los usuarios son responsables de configurar con precisión este atributo y utilizar el tipo de conexión correcto en un escenario.

Para obtener más información sobre los tipos de autenticación, consulte [Autenticación](https://developer.adobe.com/developer-console/docs/guides/authentication/) en la Guía de autenticación de Adobe.

## Recursos

* Para obtener instrucciones sobre cómo administrar metadatos de conexión, consulte [Administrar conexiones](/help/workfront-fusion/create-scenarios/connect-to-apps/manage-connections.md).
