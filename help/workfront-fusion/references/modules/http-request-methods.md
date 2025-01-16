---
title: Métodos de solicitud HTTP
description: Cuando configure una llamada de API en un módulo, debe seleccionar el método de solicitud HTTP. Este artículo describe los métodos disponibles y por qué seleccionaría cada uno de ellos.
author: Becky
feature: Workfront Fusion
exl-id: 481131c9-356a-4c62-a653-d6bba9be5be8
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 3%

---

# Métodos de solicitud HTTP

Cuando configure una llamada de API en un módulo, debe seleccionar el método de solicitud HTTP. Este artículo describe los métodos disponibles y por qué seleccionaría cada uno de ellos.

## Métodos HTTP

Utilice uno de los siguientes métodos HTTP.

* **[!UICONTROL GET]**: recupera datos de un servidor web en función de sus parámetros. [!UICONTROL GET] solicita una representación del recurso especificado y recibe un mensaje de respuesta [!UICONTROL 200 OK] con el contenido solicitado si se realiza correctamente.
* **[!UICONTROL POST]**: envía datos a un servidor web en función de sus parámetros. [!UICONTROL POST] solicitudes incluyen acciones como cargar un archivo. Si se usan varios [!UICONTROL POST], el resultado puede ser diferente al de un solo [!UICONTROL POST], por lo que debe tener cuidado al enviar varios [!UICONTROL POST] de forma involuntaria. Si un [!UICONTROL POST] se ha realizado correctamente, recibirá un mensaje de respuesta de [!UICONTROL 200 OK].
* **[!UICONTROL PUT]**: envía datos a una ubicación del servidor web en función de sus parámetros. [!UICONTROL PUT] solicitudes incluyen acciones como cargar un archivo. La diferencia entre [!UICONTROL PUT] y [!UICONTROL POST] es que el PUT es idempotente, lo que significa que el resultado de un único [!UICONTROL PUT] correcto es el mismo que muchos [!UICONTROL PUT]s idénticos. Si un PUT tiene éxito, recibe un mensaje de respuesta 200 (normalmente 201 o 204).
* **[!UICONTROL PATCH]**: (No disponible para algunos módulos de llamada de API) Aplica modificaciones parciales a un recurso en un servidor web en función de sus parámetros. [!UICONTROL PATCH] no es idempotente, lo que significa que el resultado de [!UICONTROL PATCH] múltiples podría tener consecuencias no deseadas. Si un [!UICONTROL PATCH] se realiza correctamente, recibirá un mensaje de respuesta de 200 (normalmente 204).
* **[!UICONTROL DELETE]**: elimina el recurso especificado del servidor web en función de sus parámetros (si el recurso existe). Si un [!UICONTROL DELETE] se ejecuta correctamente, recibirá un mensaje de respuesta 200 OK.
