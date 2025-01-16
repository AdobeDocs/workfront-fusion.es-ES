---
title: Configuración de direcciones IP para Fusion en la lista de permitidos de su organización
description: Fusion utiliza direcciones IP y dominios específicos para la comunicación web. Deben añadirse a la lista de permitidos de su organización para poder utilizar Workfront en su organización.
author: Becky
feature: Workfront Fusion
exl-id: 406dd45c-0863-4270-a80e-c1c115e0b367
source-git-commit: 59d739093c88238af7a7e97499fd0c7d7cf6053a
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 33%

---

# Configuración de direcciones IP para Fusion en la lista de permitidos de su organización

Dado que Adobe Workfront Fusion se comunica con la red de su organización, el cortafuegos de esta debe configurarse para permitir dicha comunicación. Los cortafuegos son medidas de seguridad muy efectivas que funcionan al separar la red de una organización de internet. Garantizan que solo los datos seleccionados y el tráfico de red puedan entrar o salir de la red de la organización. El cortafuegos permite o bloquea los datos en función del sitio que envía o recibe los datos. Como administrador de Fusion, debe asegurarse de que los datos enviados a o desde Fusion puedan pasar a través del cortafuegos de su organización.

Esto se logra a través de una lista de permitidos, que es esencialmente una “lista” de sitios a los que se les “permite” enviar o recibir datos a través del cortafuegos. Los sitios se pueden identificar de una de las dos maneras siguientes:

* **Dirección IP**: una serie de números como 52.31.132.175
* **Dominio**: parte de una dirección URL, como `thisdomain` en `www.thisdomain.com`

Fusion utiliza direcciones IP y dominios específicos para la comunicación web. Deben añadirse a la lista de permitidos de su organización para poder utilizar Workfront en su organización.

Normalmente, la lista de permitidos la configura un administrador de red. Póngase en contacto con el administrador de red de su organización para asegurarse de que el cortafuegos permite estas direcciones IP. Si no sabe quién es el administrador de red, el departamento de TI de su organización puede indicarle la dirección correcta.

>[!IMPORTANT]
>
>Como administrador de Fusion, debe asegurarse de que estas direcciones IP y dominios se añadan a la lista de permitidos de su organización. Esto es así, incluso si no los añade usted mismo. Fusion no puede configurar la lista de permitidos de su organización.

Puede añadir todas las direcciones IP y dominios de Fusion a la lista de permitidos o puede localizar el clúster de Fusion y añadir solo las direcciones IP y los dominios de ese clúster.

## Añadir todas las direcciones IP y dominios de Fusion

Añada las siguientes direcciones IP a su lista de permitidos:

* 52.30.133.50
* 54.220.93.204
* 34.254.76.122
* 54.244.142.219
* 52.39.217.230
* 44.241.82.96
* 100.20.126.137
* 34.223.32.4
* 52.39.176.220
* 20.36.133.48/28
* 20.81.156.240/28
* 172.172.84.48/28

Además, si su organización utiliza el filtrado de red saliente, añada el siguiente dominio a su lista de permitidos para permitir que su sistema acceda a Workfront Fusion.

* hook.app.workfrontfusion.com
* hook.app-eu.workfrontfusion.com
* hook.app-az.workfrontfusion.com

## Añadir direcciones IP y dominios de Fusion solo para su clúster

### Identificación del centro de datos

Las direcciones IP varían en función del lugar en el que se almacenan los datos.

Si accede a Fusion a través de una dirección URL, puede examinarla para localizar el centro de datos.

| URL | Datacenter |
| --- | --- |
| `https://app.workfrontfusion.com` | centro de datos estadounidense |
| `https://app-eu.workfrontfusion.com` | centro de datos UE |
| `https://app-az.workfrontfusion.com` | clúster de Azure |

Si accede a Fusion a través de `experience.adobe.com`, puede comprobar la pestaña de red en su explorador para identificar el centro de datos.

| URL | Datacenter |
| --- | --- |
| Llamadas a `https://fusion.adobe.com` | centro de datos estadounidense |
| Llamadas a `https://eu.fusion.adobe.com` | centro de datos UE |
| Llamadas a `https://az.fusion.adobe.com` | clúster de Azure |

### Añadir direcciones IP y dominios al centro de datos

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] Centro de datos UE</td> 
   <td> 
    <ul> 
     <li>52.30.133.50</li> 
     <li>54.220.93.204</li> 
     <li>34.254.76.122</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!DNL Adobe Workfront] US Datacenter</p> </td> 
   <td> 
    <ul> 
     <li>54.244.142.219</li> 
     <li>52.39.217.230</li> 
     <li>44.241.82.96</li>
     <li>100.20.126.137</li>
     <li>34.223.32.4</li>
     <li>52.39.176.220</li>
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] en el clúster de Microsoft Azure</td> 
   <td> 
    <ul> 
     <li>20.36.133.48/28</li> 
     <li>20.81.156.240/28</li> 
     <li>172.172.84.48/28</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Además, si su organización utiliza el filtrado de red saliente, añada el siguiente dominio a su lista de permitidos para permitir que su sistema acceda a Workfront Fusion. Se utilizan para los webhooks

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] Centro de datos UE</td> 
   <td> <p> hook.app-eu.workfrontfusion.com </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!DNL Adobe Workfront] US Datacenter</p> </td> 
   <td> <p>hook.app.workfrontfusion.com </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!DNL Adobe Workfront Fusion] en el clúster de Microsoft Azure</p> </td> 
   <td> <p>hook.app-az.workfrontfusion.com </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>El filtrado de red saliente es poco común. Consulte con el administrador de la red si necesita actualizar la lista de permitidos para adaptarla.
