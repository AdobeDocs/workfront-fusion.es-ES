---
title: Métodos de petición HTTP
description: Cuando configure una llamada de API en un módulo, debe seleccionar el método de solicitud HTTP. Este artículo describe los métodos disponibles y por qué seleccionaría cada uno de ellos.
author: Becky
feature: Workfront Fusion
exl-id: 481131c9-356a-4c62-a653-d6bba9be5be8
TQID: https://experienceleague.adobe.com/Z11y3dk6PtoN11Gja8S2ZyJlTJZNZfXfcPPrNJWvbRk
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 303
ht-degree: 55%

---

# Métodos de petición HTTP

Cuando configure una llamada de API en un módulo, debe seleccionar el método de solicitud HTTP. Este artículo describe los métodos disponibles y por qué seleccionaría cada uno de ellos.

## Métodos HTTP

Utilice uno de los siguientes métodos HTTP.

* **[!UICONTROL GET]**: recupera datos de un servidor web en función de sus parámetros. [!UICONTROL GET] solicita una representación del recurso especificado y recibe un mensaje de respuesta [!UICONTROL 200 OK] con el contenido solicitado si se ejecuta correctamente.
* **[!UICONTROL POST]**: envía datos a un servidor web en función de sus parámetros. Las peticiones [!UICONTROL POST] incluyen acciones como cargar un archivo. Varias [!UICONTROL POST] pueden dar un resultado diferente a una sola [!UICONTROL POST], así que tenga cuidado de no enviar involuntariamente varias [!UICONTROL POST]. Si un [!UICONTROL POST] se ha realizado correctamente, recibirá un mensaje de respuesta de [!UICONTROL 200 OK].
* **[!UICONTROL PUT]**: envía datos a una ubicación del servidor web en función de sus parámetros. Las peticiones [!UICONTROL PUT] incluyen acciones como cargar un archivo. La diferencia entre [!UICONTROL PUT] y [!UICONTROL POST] es que PUT es idempotente, lo que significa que el resultado de un único [!UICONTROL PUT] correcto es el mismo que muchos [!UICONTROL PUT]s idénticos. Si una PUT se realiza correctamente, recibirá un mensaje de respuesta 200 (normalmente 201 o 204).
* **[!UICONTROL PATCH]**: (no disponible para algunos módulos de llamadas de API) Aplica modificaciones parciales a un recurso en un servidor web en función de sus parámetros. [!UICONTROL PATCH] no es idempotente, lo que significa que el resultado de varios [!UICONTROL PATCH] podría tener consecuencias no deseadas. Si un [!UICONTROL PATCH] se ejecuta correctamente, se recibe un mensaje de respuesta 200 (normalmente 204).
* **[!UICONTROL DELETE]**: elimina el recurso especificado del servidor web en función de sus parámetros (si el recurso existe). Si un [!UICONTROL DELETE] se ejecuta correctamente, se recibe un mensaje de respuesta 200 OK.
