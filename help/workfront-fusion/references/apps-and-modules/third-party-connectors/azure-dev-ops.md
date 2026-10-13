---
title: Módulos de Azure DevOps
description: En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!DNL Azure DevOps], así como conectarlo a varias aplicaciones y servicios de terceros.
author: Becky
feature: Workfront Fusion
exl-id: c0919a9a-ce99-485c-9627-45353741f6d8
TQID: 'https://experienceleague.adobe.com/RFI6MFgF-C1Cnn0bvjOLVf3qahyRblEp4dtypNrxqzE'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: b58ad82f-df6b-4b01-81a3-3a02ab9567a0
    internal-label: APIs
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0922a5503bbeded91ae116849465d0f898ef4686
workflow-type: tm+mt
source-wordcount: '3792'
ht-degree: 41%
---
# Módulos de [!DNL Azure DevOps]

En un escenario de Adobe Workfront Fusion, puede automatizar los flujos de trabajo que utilizan [!DNL Azure DevOps], así como conectarlo a varias aplicaciones y servicios de terceros.

Para obtener instrucciones sobre cómo crear un escenario, consulte los artículos en [Crear escenarios: índice de artículos](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Para obtener información acerca de los módulos, consulte los artículos en [Módulos: índice de artículos](/help/workfront-fusion/references/modules/modules-toc.md).

## Requisitos de acceso

+++ Expanda para ver los requisitos de acceso para la funcionalidad en este artículo.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Paquete de Adobe Workfront</td> 
   <td> <p>Cualquier paquete del flujo de trabajo de Adobe Workfront y cualquier paquete de integración y automatización de Adobe Workfront</p><p>Workfront Ultimate</p><p>Paquetes Workfront Prime y Select, con una compra adicional de Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Licencias de Adobe Workfront</td> 
   <td> <p>Estándar</p><p>Trabajo o superior</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Licencia de Adobe Workfront Fusion</td> 
   <td>
   <p>Basado en operaciones: disponible para organizaciones con licencias basadas en operaciones</p>
   <p>Basado en conector (heredado): Workfront Fusion for Work Automation and Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Producto</td> 
   <td>
   <p>Si su organización tiene un paquete de Workfront Select o Prime que no incluye la automatización y la integración de Workfront, su organización debe adquirir Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Para obtener más información sobre el contenido de esta tabla, consulte [Requisitos de acceso en la documentación](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Para obtener información sobre las licencias de Adobe Workfront Fusion, consulte [licencias de Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Requisitos previos

Para usar módulos de [!DNL Azure DevOps], debe tener una cuenta de DevOps de [!DNL Azure].

## Información de la API [!DNL Azure DevOps]

El conector DevOps de Azure utiliza lo siguiente:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Versión de API</td> 
   <td> Versión 5.1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Etiqueta de API</td> 
   <td>Versión 1.29.33</td> 
  </tr>
 </tbody> 
</table>

## Conexión de [!DNL Azure DevOps] a Workfront Fusion {#connect-azure-devops-to-workfront-fusion}

* [Conexión de Azure DevOps a Workfront Fusion mediante una conexión federada](#connect-azure-devops-to-workfront-fusion-using-a-federated-connection)
* [Conexión de Azure DevOps a Workfront Fusion mediante EntraApp](#connect-azure-devops-to-workfront-fusion-using-entraapp)
* [Conexión de Azure DevOps a Workfront Fusion mediante una entidad de servicio](#connect-azure-devops-to-workfront-fusion-using-a-service-principal)

### Conexión de Azure DevOps a Adobe Workfront Fusion mediante una conexión federada

Una conexión federada funciona como la conexión principal de servicio, excepto que no utiliza un secreto de cliente.

En lugar de almacenar un secreto, indique a Microsoft Entra ID que confíe en los tokens que Workfront Fusion emite para una conexión específica. Cuando se ejecuta la conexión, Fusion presenta una prueba de identidad de corta duración y Microsoft Entra ID devuelve un token de acceso. Como no hay ningún secreto de cliente, no hay nada que caduque ni ningún secreto que rotar o almacenar.

+++ Amplíe para ver las instrucciones para conectar Azure DevOps a Adobe Workfront Fusion mediante una conexión federada.

>[!NOTE]
>
>* La configuración de esta conexión requiere dos visitas al Centro de administración de Microsoft Entra. Primero registre la aplicación y, a continuación, cree la conexión en Workfront Fusion y vuelva a Microsoft Entra ID para añadir la credencial federada. Esto se debe a que la credencial federada identificó una conexión específica y ese identificador no existe hasta que se crea la conexión.
>* Se aplican los mismos límites a esta conexión que a la conexión principal de servicio. Un pequeño número de acciones a nivel de administrador, como la administración de licencias de usuario, aún requieren una conexión de cuenta personal.

* [Requisitos previos para conectar Azure DevOps a Workfront Fusion mediante una conexión federada](#prerequisites-to-connecting-azure-devops-to-workfront-fusion-using-a-federated-connection)
* [Cree el registro de la aplicación en Microsoft Entra ID (conexión federada)](#create-the-app-registration-in-microsoft-entra-id-federated-connection)
* [Recopile sus datos de conexión (conexión federada)](#collect-your-connection-details-federated-connection)
* [Creación de la conexión en Workfront Fusion (conexión federada)](#create-the-connection-in-workfront-fusion-federated-connection)
* [Agregar la credencial federada en Microsoft Entra ID](#add-the-federated-credential-in-microsoft-entra-id)
* [Compruebe la conexión (conexión federada)](#verify-the-connection-federated-connection)

#### Requisitos previos para conectar Azure DevOps a Workfront Fusion mediante una conexión federada


Para crear esta conexión, necesita lo siguiente:

* Acceso de administrador global o administrador de aplicaciones en Microsoft Entra ID para registrar la aplicación y añadir las credenciales federadas. Si no tiene este acceso, pídale a alguien de su equipo de TI o de identidad que siga estos pasos.
* Acceso de administrador de recopilación de proyectos en su organización de Azure DevOps para agregar la entidad de servicio como miembro. A menudo se trata de una persona diferente a la persona que administra el Microsoft Entra ID.
* Nombre de su organización de DevOps de Azure. Puede encontrar esto en su URL de DevOps de Azure: `dev.azure.com/<your organization name>`.

#### Cree el registro de la aplicación en Microsoft Entra ID (conexión federada)

1. Inicie sesión en el Centro de administración de Microsoft Entra.
1. Vaya a Registros de aplicaciones > Nuevo registro.
1. Asigne a la aplicación un nombre claro y reconocible. Por ejemplo, `Workfront Fusion Azure DevOps Integration`.
1. Deje URI de redireccionamiento en blanco. Esta conexión no implica iniciar sesión a través de un explorador.
1. Seleccione Registrar.
1. No cree un secreto de cliente. Una conexión federada no utiliza una.
1. Continúe a [Recopilar sus detalles de conexión](#collect-your-connection-details-federated-connection).


#### Recopile sus datos de conexión (conexión federada)

1. En la página Información general del registro de la aplicación, tenga en cuenta los siguientes valores. Estos se introducen al crear la conexión en el módulo.

   <table style="table-layout:auto">
    <col>
    <col>
    <tbody>
     <tr>
      <td role="rowheader">[!UICONTROL Tenant ID]</td>
      <td>En la página Información general, con la etiqueta <b>Directorio (inquilino) ID</b>.</td>
     </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Client ID]</td>
      <td>En la página Información general, <b>ID de aplicación (cliente)</b>.</td>
     </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Organization]</td>
      <td>Nombre de su organización de Azure DevOps. Por ejemplo, si la dirección URL es <code>dev.azure.com/yourorg</code>, escriba <code>yourorg</code>.</td>
     </tr>
    </tbody>
   </table>

1. Continuar a [Crear la conexión en Workfront Fusion](#create-the-connection-in-workfront-fusion-federated-connection).

>[!NOTE]
>
>Al igual que con la conexión principal del servicio, puede omitir el área de permisos de API del registro de la aplicación. El acceso a Azure DevOps se concede dentro de Azure DevOps, en el siguiente procedimiento.

#### Creación de la conexión en Workfront Fusion (conexión federada)

1. En la pantalla de configuración de la conexión del módulo, seleccione el tipo de conexión federada.
1. Introduzca lo siguiente:

   * ID de inquilino
   * Id. de cliente
   * Organización

1. Seleccione **Crear**.

   Workfront Fusion muestra tres valores. Deje esta página abierta, ya que necesitará estos valores más adelante en el proceso de creación de la conexión.

   <table style="table-layout:auto">
    <col>
    <col>
    <tbody>
     <tr>
      <td role="rowheader">[!UICONTROL Emisor]</td>
      <td><code>https://oidc.automations.adobe.com</code>.</td>
     </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Subject]</td>
      <td>Esto identifica esta conexión. Se ve como <code>fusion:6e5b1c2a345bd8d1ed98b6b4f1459818:28964</code>. Es diferente para cada conexión que cree.</td>
     </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Audience]</td>
      <td><code>api://AzureADTokenExchange</code>.</td>
     </tr>
    </tbody>
   </table>

   >[!IMPORTANT]
   >
   >No cierre el panel ni seleccione Cancelar. La conexión no finaliza hasta que complete el resto del procedimiento. Si cierra el panel, debe eliminar la conexión y volver a iniciarla, ya que una nueva conexión recibe un nuevo Asunto.

1. Copie el valor **Subject**.
1. Continuar a [Agregar la credencial federada en Microsoft Entra ID](#add-the-federated-credential-in-microsoft-entra-id).

#### Agregar la credencial federada en Microsoft Entra ID

Este procedimiento es el que reemplaza el secreto de cliente. Indica a Microsoft Entra ID que acepte tokens que Workfront Fusion emite para esta conexión.

1. En una nueva pestaña del explorador, vuelva al Centro de administración de Microsoft Entra y abra el registro de la aplicación.
1. Vaya a Certificados y secretos > Credenciales federadas.
1. Seleccione Agregar credencial.
1. En el escenario de Credenciales federadas, seleccione Otro emisor.
1. Introduzca lo siguiente:

   <table style="table-layout:auto">
    <col>
    <col>
    <tbody>
     <tr>
      <td role="rowheader">[!UICONTROL Emisor]</td>
      <td><code>https://oidc.automations.adobe.com</code></td>
     </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Identificador de asunto]</td>
      <td>El asunto que ha copiado de Workfront Fusion. Péguelo exactamente sin añadir espacios.</td>
     </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Name]</td>
      <td>Un nombre que identifica esta conexión, para que pueda encontrarla más adelante. Por ejemplo, <code>workfront-fusion-connection-28964</code>.</td>
     </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Audience]</td>
      <td><code>api://AzureADTokenExchange</code>. Normalmente, esto se rellena para usted. Mantenga el valor predeterminado.</td>
     </tr>
    </tbody>
   </table>

1. Haga clic en **Añadir**.
1. Continuar a [Verificar la conexión](#verify-the-connection-federated-connection).

>[!NOTE]
>
>El Microsoft Entra ID permite un máximo de 20 credenciales federadas en un único registro de aplicación, y el identificador de sujeto debe coincidir exactamente. No se admiten caracteres comodín. Dado que cada conexión de Workfront Fusion tiene su propio asunto, cada conexión necesita su propia credencial federada. Si espera más de 20 conexiones, registre más de una aplicación y extienda las conexiones entre ellas.


#### Compruebe la conexión (conexión federada)

1. Vuelva a la pestaña del explorador de Workfront Fusion, donde el panel de conexión sigue abierto.
1. Haga clic en **Guardar**.

   * Si todo está configurado correctamente, la conexión se valida correctamente y puede continuar con la configuración del módulo.
   * Si la verificación falla, el panel permanece abierto y muestra el error. Corrija el problema en Microsoft Entra ID o en Azure DevOps y vuelva a seleccionar Guardar. No es necesario volver a crear la conexión y el asunto no cambia.

>[!NOTE]
>
>Una credencial federada que agregue al Microsoft Entra ID puede tardar poco tiempo en activarse. Si la verificación falla inmediatamente después de agregar la credencial, espere un minuto y seleccione Guardar de nuevo antes de investigar más a fondo.


Resolución de problemas

<table style="table-layout:auto">
 <col>
 <col>
 <tbody>
  <tr>
   <td role="rowheader">La conexión falla en la verificación con un cliente no válido o un error de solicitud no válido</td>
   <td>El ID de Microsoft Entra no pudo hacer coincidir el token con una credencial federada. Compruebe que el emisor sea exactamente <code>https://oidc.automations.adobe.com</code> sin barra diagonal y que el identificador de asunto sea idéntico carácter por carácter al asunto mostrado en Workfront Fusion. La causa más común es un asunto copiado de una conexión diferente.</td>
  </tr>
  <tr>
   <td role="rowheader">La conexión se verifica, pero los módulos devuelven 401 o 403 desde Azure DevOps</td>
   <td>La identidad es de confianza, pero no tiene acceso a los datos de Azure DevOps. Confirme que ha completado <a href="#add-the-service-principal-to-your-azure-devops-organization">Agregar la entidad de seguridad de servicio a su organización de Azure DevOps</a> y que la entidad de seguridad de servicio está asignada al proyecto específico que utiliza el módulo.</td>
  </tr>
  <tr>
   <td role="rowheader">No puede agregar otra credencial federada</td>
   <td>Ha alcanzado el límite de 20 credenciales federadas para el registro de esa aplicación. Registre una aplicación adicional y cree más conexiones con ella.</td>
  </tr>
 </tbody>
</table>

+++

### Conexión de Azure DevOps a Workfront Fusion mediante EntraApp

Puede conectar Azure DevOps a Workfront Fusion mediante EntraApp.

+++ Amplíe para ver las instrucciones para conectar Azure DevOps a Workfront Fusion mediante EntraApp

1. Añada un módulo de [!DNL Azure DevOps] a su escenario.
1. Haga clic en **[!UICONTROL Añadir]** junto al campo [!UICONTROL conexión].
1. En el campo [!UICONTROL Tipo de conexión], seleccione el tipo de conexión que desea utilizar.

   >[!NOTE]
   >
   >[!UICONTROL [!DNL Azure DevOps] (EntraApp)] le permite solicitar todos los ámbitos de la conexión.

1. Rellene los campos siguientes:

   <table style="table-layout:auto">
      <tr>
            <td>[!UICONTROL Connection name]</td>
            <td>Introduzca un nombre para la conexión que está creando.</td>
      </tr>
      <tr>
            <td>[!UICONTROL Organization]</td>
            <td>Introduzca el nombre de la organización en la que ha creado la aplicación [!DNL Azure DevOps].</td>
      </tr>
      <tr>
            <td>[!UICONTROL App ID]</td>
            <td>Introduzca el ID de la aplicación DevOps a la que se está conectando.</td>
      </tr>
      <tr>
            <td>[!UICONTROL Client Secret]</td>
            <td>Escriba el secreto de cliente para las aplicaciones DevOps a las que se está conectando.</td>
      </tr>
      <tr>
            <td>[!UICONTROL Solicitar todos los ámbitos]</td>
            <td>Si está usando el tipo de conexión [!DNL Azure DevOps] (EntraApp), habilite esta opción para solicitar todos los ámbitos de la conexión.</td>
      </tr>
   </table>

1. Para escribir un ID de aplicación o un secreto de cliente de Azure DevOps, haga clic en <b>Mostrar configuración avanzada</b> e ingréselos en los campos que se abren.
1. Haga clic en **[!UICONTROL Continuar]** para finalizar la configuración de la conexión y continuar creando el escenario.

+++

### Conexión de Azure DevOps a Workfront Fusion mediante una entidad de servicio

Puede crear una conexión que utilice una entidad de seguridad de servicio (una conexión API de aplicación) en lugar de una cuenta personal. Esto resulta útil cuando desea que la conexión se ejecute como una identidad de aplicación o servicio en lugar de como una persona específica. Esto puede resultar útil para que la integración no se interrumpa si, por ejemplo, esa persona abandona la empresa o cambia su contraseña.

Este tipo de conexión está disponible para todos los módulos DevOps de Azure.

+++ Amplíe para ver las instrucciones para conectar Azure DevOps a Adobe Workfront Fusion mediante una entidad de seguridad de servicio.


>[!NOTE]
>
>La autenticación principal de servicio no es compatible con todas las funciones de Azure DevOps. Un pequeño número de acciones a nivel de administrador, como la administración de licencias de usuario, aún requieren una conexión de cuenta personal. Utilice la autenticación de entidad de seguridad de servicio si solo lo necesita para elementos de trabajo, tableros, repositorios o canalizaciones.

* [Requisitos previos para conectar Azure DevOps a Workfront Fusion mediante una entidad de servicio](#prerequisites-to-connecting-azure-devops-to-workfront-fusion-using-a-service-principal)
* [Creación del registro de la aplicación en Microsoft Entra ID](#create-the-app-registration-in-microsoft-entra-id-service-principal)
* [Crear un secreto de cliente](#create-a-client-secret)
* [Recopilar los detalles de la conexión](#collect-your-connection-details-service-principal)
* [Añada la entidad de seguridad de servicio a su organización de DevOps de Azure](#add-the-service-principal-to-your-azure-devops-organization)
* [Creación de la conexión](#create-the-connection)

#### Requisitos previos para conectar Azure DevOps a Workfront Fusion mediante una entidad de servicio

Para crear esta conexión, necesita lo siguiente:

* **Administrador global** o **Administrador de aplicaciones** tienen acceso a la Microsoft Entra ID para registrar la aplicación. Si no tiene este acceso, pida a alguien de su equipo de TI o de identidad que complete ese paso por usted.
* **Administrador de recopilación de proyectos** tiene acceso a en su organización de Azure DevOps para agregar la entidad de seguridad de servicio como miembro. A menudo se trata de una persona diferente a la persona que administra el Microsoft Entra ID.
* Nombre de su organización de DevOps de Azure. Puede encontrar esto en su URL de DevOps de Azure: `dev.azure.com/<your organization name>`.

#### Cree el registro de la aplicación en Microsoft Entra ID (entidad de servicio)

1. Inicie sesión en el centro de administración de [!DNL Microsoft Entra].
1. Vaya a **[!UICONTROL Registros de aplicaciones]** > **[!UICONTROL Nuevo registro]**.
1. Asigne a la aplicación un nombre claro y reconocible. Por ejemplo, `Workfront Fusion Azure DevOps Integration`.
1. Deje **[!UICONTROL URI de redireccionamiento]** en blanco. Esta conexión no implica iniciar sesión a través de un explorador.
1. Seleccione **[!UICONTROL Registrar]**.
1. Continuar a [Crear un secreto de cliente](#create-a-client-secret).

#### Crear un secreto de cliente

1. En el registro de la nueva aplicación, ve a **[!UICONTROL Certificados y secretos]**.
1. Seleccione **[!UICONTROL Nuevo secreto de cliente]**, agregue una descripción y elija un período de caducidad.
1. Seleccione **[!UICONTROL Agregar]**.
1. Copie el **[!UICONTROL Valor]** del secreto inmediatamente. Se muestra solo una vez. Si se aleja antes de copiarlo, debe crear uno nuevo.
1. Continúe a [Recopilar sus detalles de conexión](#collect-your-connection-details).

#### Recopilar los detalles de conexión (entidad de seguridad de servicio)

1. En la página **[!UICONTROL Información general]** del registro de la aplicación, tenga en cuenta los siguientes valores. Estos se introducen al crear la conexión en el módulo.

   <table style="table-layout:auto">
    <col>
    <col>
    <tbody>
     <tr>
      <td role="rowheader">[!UICONTROL Tenant ID]</td>
      <td>En la página Información general, con la etiqueta <b>Directorio (inquilino) ID</b>.</td>
      </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Client ID]</td>
      <td>En la página Información general, <b>ID de aplicación (cliente)</b>.</td>
     </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Client Secret]</td>
      <td>El valor que copió en <a href="#create-a-client-secret" class="MCXref xref">Crear un secreto de cliente</a>.</td>
     </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Organization]</td>
      <td>Nombre de su organización de Azure DevOps. Por ejemplo, si la dirección URL es <code>dev.azure.com/yourorg</code>, escriba <code>yourorg</code>.</td>
     </tr>
    </tbody>
   </table>

   >[!NOTE]
   >
   >Puede omitir el área **permisos de API** del registro de la aplicación. Si agrega las DevOps de Azure, solo están disponibles **permisos delegados**. **Los permisos de la aplicación** aparecen atenuados. Esto es de esperar, ya que Azure DevOps no admite la concesión de acceso de esta manera. En su lugar, el acceso se concede directamente dentro de las operaciones de desarrollo de Azure, en la siguiente parte.

1. Continuar a [Agregar la entidad de seguridad de servicio a su organización de DevOps de Azure](#add-the-service-principal-to-your-azure-devops-organization).

#### Añada la entidad de seguridad de servicio a su organización de DevOps de Azure

Al registrar la aplicación en Microsoft Entra ID, solo se crea su identidad. Todavía no da a la aplicación acceso a los datos de Azure DevOps. Este procedimiento concede ese acceso.

1. Inicie sesión en su organización de DevOps de Azure, en `dev.azure.com/<your organization name>`.
1. Seleccione **[!UICONTROL Configuración de la organización]** en la esquina inferior izquierda, luego seleccione **[!UICONTROL Usuarios]**.
1. Seleccione **[!UICONTROL Agregar usuarios]**.
1. En el cuadro de búsqueda, busque por el nombre para mostrar de la aplicación, que es el nombre que le dio al registrar la aplicación. No buscar por ID de cliente.
1. Seleccione un nivel de acceso:

   * **[!UICONTROL Básico]** suele ser suficiente para leer y escribir elementos de trabajo, tableros y repositorios.
   * Si el flujo de trabajo necesita examinar los procesos disponibles, como Agile, Scrum o plantillas personalizadas, como parte de la configuración, agregue la entidad de seguridad de servicio al grupo **[!UICONTROL Administradores de la colección de proyectos]** en su lugar. Se trata de un nivel de acceso más amplio, por lo que solo debe otorgarlo si necesita esa capacidad.

1. Asigne el principal de servicio al proyecto o proyectos específicos que necesite, siguiendo las prácticas de acceso habituales de su organización.
1. Seleccione **[!UICONTROL Agregar]**.
1. Continuar a [Crear la conexión en Workfront Fusion](#create-the-connection-in-workfront-fusion-service-principal).

#### Crear la conexión en Workfront Fusion (entidad de servicio)

1. En la pantalla de configuración de la conexión del módulo, seleccione el tipo de conexión **[!UICONTROL Service Principal]**.
1. Introduzca lo siguiente:

   * [!UICONTROL Id. de inquilino]
   * [!UICONTROL ID de cliente]
   * [!UICONTROL Secreto de cliente]
   * [!UICONTROL Organización]

1. Guarde la conexión.

   Si todo está configurado correctamente, la conexión se valida correctamente.

+++

## Módulos de [!UICONTROL Azure DevOps] y sus campos

Al configurar módulos de [!DNL Azure DevOps], Workfront Fusion muestra los campos que se indican a continuación. Junto a estos, pueden aparecer campos de [!DNL Azure DevOps] adicionales, en función de factores como el nivel de acceso del que disponga en la aplicación o el servicio. El título en negrita en un módulo indica un campo obligatorio.

Si ve el botón Asignar encima de un campo o función, puede utilizarlo para establecer variables y funciones para ese campo. Para obtener más información, consulte [Asignar información de un módulo a otro](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Conmutador Asignar](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Activadores](#triggers)
* [Acciones](#actions)
* [Búsquedas](#searches)

### Activadores

#### [!UICONTROL Ver elementos de trabajo]

Este módulo de activador instantáneo ejecuta un escenario cuando se añade, actualiza o elimina un registro en [!UICONTROL Azure DevOps].

El módulo devuelve cualquier campo estándar asociado con el registro, junto con los campos y valores personalizados a los que accede la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>Seleccione o añada un webhook para el módulo.</p> <p>Para obtener más información sobre los webhooks en los módulos de déclencheur, consulte <a href="/help/workfront-fusion/references/modules/webhooks-reference.md" class="MCXref xref">déclencheur instantáneos (webhooks)</a>.</p> <p>Para obtener información sobre cómo crear un webhook, consulte <a href="/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md" class="MCXref xref">Webhooks</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Acciones

* [Crear un registro](#create-a-record)
* [Llamada API personalizada](#custom-api-call)
* [Descargar un archivo adjunto](#download-an-attachment)
* [Vincular elementos de trabajo](#link-work-items)
* [Leer registro](#read-record)
* [Actualizar un elemento de trabajo](#update-a-work-item)
* [[!UICONTROL Cargar un archivo adjunto]](#upload-an-attachment)

#### [!UICONTROL Creación de un registro]

Este módulo de acción crea un nuevo proyecto o elemento de trabajo.

El módulo genera el ID de objeto para el elemento de trabajo recién creado o la URL y el código de estado de un proyecto recién creado.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Azure DevOps] a Workfront Fusion, consulte <a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Azure DevOps] a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>Seleccione si desea crear un elemento de trabajo o un proyecto.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Project]</strong> </p> <p>Rellene los campos siguientes:</p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Name]</strong>: escriba o asigne un nombre para el nuevo proyecto.</p> </li> 
       <li> <p><strong>[!UICONTROL Descripción]</strong>: escriba o asigne una descripción para el nuevo proyecto. </p> </li> 
       <li> <p><strong>[!UICONTROL Visibility]</strong>: seleccione si desea que el proyecto sea público o privado. Para poder interactuar con un proyecto privado, los usuarios deben haber iniciado sesión en su organización y se les debe haber concedido acceso al proyecto. Los proyectos públicos son visibles para los usuarios que no han iniciado sesión en su organización.</p> </li> 
       <li> <p><strong>[!UICONTROL Version control]</strong>: seleccione si desea que el proyecto use [!DNL Git] o [!UICONTROL Team Foundation Version Control (TFCV)] para el control de versiones.</p> </li> 
       <li> <p><strong>[!UICONTROL Work item process]</strong>: seleccione el proceso de trabajo que desee utilizar para el proyecto. Las opciones son [!UICONTROL Basic], [!UICONTROL Scrum], [!UICONTROL Capability Maturity Model Integration (CMMI)] y [!UICONTROL Agile].</p> <p>Para obtener más información sobre [!DNL Azure DevOps] procesos, consulte <a href="https://docs.microsoft.com/en-us/azure/devops/boards/work-items/guidance/choose-process?view=azure-devops&amp;tabs=basic-process">Procesos predeterminados y plantillas de proceso</a> en la documentación de [!DNL Azure DevOps].</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL Work item]</strong> </p> <p>Rellene los campos siguientes:</p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Project]</strong>: seleccione el proyecto donde desea crear el elemento de trabajo.</p> </li> 
       <li> <p><strong>[!UICONTROL Work item type]</strong>: seleccione el tipo de elemento de trabajo que desea crear.</p> </li> 
       <li> <p><strong>[!UICONTROL Otros campos]</strong>: en estos campos, escriba el valor que desea que tenga el elemento de trabajo para una propiedad determinada. Los campos disponibles dependen del tipo de elemento de trabajo.</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Llamada API personalizada]

Este módulo de acción le permite realizar una llamada autenticada personalizada a la API [!DNL Azure DevOps]. De este modo, puede crear una automatización del flujo de datos imposibles de realizar por los otros [!DNL Azure DevOps] módulos.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Azure DevOps] a Workfront Fusion, consulte <a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Azure DevOps] a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Base URL]</td> 
   <td> <p>Seleccione o asigne la dirección URL base que utiliza para conectarse a su cuenta de [!DNL Azure DevOps]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Relative URL]</td> 
   <td> <p>Introduzca la dirección URL relativa a la que desea conectarse para esta llamada API.</p> <p><b>Ejemplo: </b><code>{organization}/_apis[/{area}]/{resource}</code> </p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL API Version]</td> 
   <td>Seleccione o asigne la versión de la API de [!DNL Azure DevOps] a la que desee conectarse para esta llamada API. Si no se ha seleccionado ninguna versión, Workfront Fusion se conecta a la versión 5.1 de la API [!DNL Azure DevOps].</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Seleccione el método de petición HTTP que necesita para configurar la llamada API. Para obtener más información, consulte <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Métodos de petición HTTP</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Añada los encabezados de la solicitud en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"Content-type":"application/json"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Añada la consulta para la llamada API en forma de objeto JSON estándar.</p> <p>Por ejemplo: <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Añada el contenido del cuerpo para la llamada API en forma de objeto JSON estándar.</p> <p>Nota:  <p>Cuando utilice afirmaciones condicionales como <code>if</code> en su JSON, coloque las comillas fuera de la afirmación condicional.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Descargar un archivo adjunto]

Este módulo de acción descarga un archivo adjunto.

El módulo devuelve el contenido del archivo adjunto.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Azure DevOps] a Workfront Fusion, consulte <a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Azure DevOps] a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Attachment URL]</td> 
   <td> <p>Introduzca o asigne la dirección URL del archivo adjunto que desea descargar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Vincular elementos de trabajo]

Este módulo de acción vincula dos elementos de trabajo y define la relación entre ellos.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Azure DevOps] a Workfront Fusion, consulte <a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Azure DevOps] a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Work item ID]</td> 
   <td>Escriba o asigne el identificador del elemento de trabajo principal al que desee vincular otro elemento de trabajo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Linked work item ID]</td> 
   <td>Introduzca o asigne el ID del elemento de trabajo que desee vincular al elemento de trabajo principal.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Link Type]</td> 
   <td> <p>Defina la relación entre los elementos de trabajo que desea vincular.</p> <p>Para obtener más información, consulte <a href="https://docs.microsoft.com/es-es/azure/devops/boards/queries/link-type-reference?view=azure-devops">Guía de referencia para tipos de vínculos</a> en la documentación de [!UICONTROL Azure DevOps].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment]</td> 
   <td>Escriba o asigne el texto de un comentario. Esto resulta útil para explicar el razonamiento o la intención del vínculo.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Leer registro]

Este módulo de acción lee datos de un único registro en [!DNL Azure DevOps].

Especifique el identificador del registro.

El módulo devuelve el ID del registro y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Azure DevOps] a Workfront Fusion, consulte <a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Azure DevOps] a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>Seleccione si desea leer un proyecto o un elemento de trabajo</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Proyecto]</strong>: seleccione el proyecto que desea leer.</p> </li> 
     <li> <p><strong>[!UICONTROL Work item]</strong>: seleccione el proyecto que contiene el elemento de trabajo que desea leer y, a continuación, seleccione el tipo de elemento de trabajo.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Seleccione la información que desea incluir en el paquete de salida para este módulo. Los campos disponibles dependen del tipo de elemento de trabajo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Introduzca o asigne el ID del registro que desea leer.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Actualizar un elemento de trabajo]

Este módulo de acción actualiza un elemento de trabajo existente mediante su ID.

El módulo devuelve el ID del elemento de trabajo actualizado.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Azure DevOps] a Workfront Fusion, consulte <a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Azure DevOps] a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project]</td> 
   <td>Seleccione el proyecto que contiene el elemento de trabajo que desea actualizar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Work Item Type]</td> 
   <td> <p>Seleccione el tipo de elemento de trabajo que desea actualizar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Other Fields]</td> 
   <td>En cada uno de estos campos, introduzca el valor que desea que tenga el elemento de trabajo para una propiedad determinada. Los campos disponibles dependen del tipo de elemento de trabajo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Work item ID]</td> 
   <td>Escriba o asigne el ID del elemento de trabajo que desea actualizar.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Cargar un archivo adjunto]

Este módulo de acción carga un archivo y lo adjunta a un elemento de trabajo.

El módulo devuelve el ID de archivo adjunto y una URL de descarga para el archivo adjunto.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Azure DevOps] a Workfront Fusion, consulte <a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Azure DevOps] a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project] </td> 
   <td> <p>Seleccione el proyecto en el que desea cargar un archivo adjunto.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Work item ID]</td> 
   <td> <p>Introduzca o asigne el ID del elemento de trabajo en el que desea cargar un archivo adjunto.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment]</td> 
   <td>Escriba el texto del comentario que desee añadir al archivo adjunto cargado.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Archivo de origen] </td> 
   <td>Seleccione un archivo de origen de un módulo anterior o introduzca o asigne el nombre y el contenido del archivo de origen.</td> 
  </tr> 
 </tbody> 
</table>

### Búsquedas

#### [!UICONTROL Lista de elementos de trabajo]

Este módulo de acción recupera todos los elementos de trabajo de un tipo específico en un proyecto de [!DNL Azure DevOps].

El módulo devuelve el ID del elemento de trabajo principal y cualquier campo asociado, junto con cualquier campo y valor personalizados a los que acceda la conexión. Puede asignar esta información en módulos subsiguientes en el escenario.

Al configurar este módulo, se muestran los campos siguientes.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Para obtener instrucciones sobre cómo conectar su cuenta de [!DNL Azure DevOps] a Workfront Fusion, consulte <a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Conectar [!DNL Azure DevOps] a [!UICONTROL Workfront Fusion]</a> en este artículo.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project]</td> 
   <td>Seleccione el proyecto cuyos elementos de trabajo desea recuperar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Work item type]</td> 
   <td> <p>Seleccione el tipo de elemento de trabajo que desea recuperar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Seleccione las propiedades que desea que aparezcan en la salida del módulo. Los campos disponibles dependen del tipo de elemento de trabajo que desee recuperar. Debe seleccionar al menos una propiedad.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Introduzca o asigne el número máximo de elementos de trabajo que Workfront Fusion devuelve durante un ciclo de ejecución.</td> 
  </tr> 
 </tbody> 
</table>
