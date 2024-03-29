---
title: Envíos de administrador
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar el portal de envíos en el Centro de seguridad y cumplimiento de & para enviar correos electrónicos sospechosos, correos de suplantación de identidad sospechosos, correo no deseado y otros mensajes, direcciones URL y archivos potencialmente dañinos a Microsoft para su análisis.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d0b91808aa9008f467f66b8200f2c05a120fbcd9
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107235"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Usar el Envío para administradores para enviar correo no deseado, de suplantación de identidad, direcciones URL y archivos sospechosos a Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)


En Microsoft 365 organizaciones con buzones de correo en Exchange Online, los administradores pueden usar el portal de envíos del Centro de seguridad y cumplimiento de & para enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft para examinarlos.

Cuando envíe un mensaje de correo electrónico, recibirá:

1. **Comprobación de autenticación de** correo electrónico: detalles sobre si la autenticación de correo electrónico se ha pasado o no cuando se entregó.
2. **Aciertos de** directiva: información sobre las directivas que pueden haber permitido o bloqueado el correo electrónico entrante en su inquilino, invalidando nuestros veredictos de filtro de servicio.
3. **Reputación/detonación de carga:** examen de las direcciones URL y los datos adjuntos del mensaje.
4. **Análisis del calificador:** revisión realizada por calificadores humanos para confirmar si los mensajes son malintencionados o no.

> [!IMPORTANT]
> El análisis de reputación/detonación y calificador de carga no se realiza en todos los inquilinos. La información se bloquea para que no salga de la organización cuando los datos no deben salir del límite del espacio empresarial con fines de cumplimiento.

Para obtener otras formas de enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la **página Envío,** use <https://protection.office.com/reportsubmission> .

- Para enviar mensajes y archivos a Microsoft, debe ser miembro de uno de los siguientes grupos de roles:

  - **Administración de** la organización **o Lector de seguridad** en el Centro de seguridad & [cumplimiento](permissions-in-the-security-and-compliance-center.md).

  - **Administración de** la [organización en Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

    Tenga en cuenta que la pertenencia a este grupo de roles es necesaria para ver los [envíos](#view-user-submissions-to-the-custom-mailbox) de usuarios al buzón personalizado, tal como se describe más adelante en este artículo.

- Para obtener más información acerca de cómo los usuarios pueden enviar mensajes y archivos a Microsoft, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="report-suspicious-content-to-microsoft"></a>Informar de contenido sospechoso a Microsoft

1. En el Centro de seguridad &  cumplimiento, vaya a \> **Envíos** de administración de amenazas , compruebe que está en la pestaña **Envíos** de administrador y, a continuación, haga clic en **Nuevo envío**.

2. Use **El menú desplegable** Nuevo envío que parece enviar el mensaje, la dirección URL o los datos adjuntos, tal como se describe en las secciones siguientes.

### <a name="submit-a-questionable-email-to-microsoft"></a>Enviar un correo electrónico cuestionable a Microsoft

1. En la **sección Tipo de objeto,** seleccione **Correo electrónico**. En la **sección Formato de** envío, use una de las siguientes opciones:

   - **Id.** de mensaje de red: se trata de un valor GUID que está disponible en el encabezado **X-MS-Exchange-Organization-Network-Message-Id** del mensaje o en el encabezado **X-MS-Office365-Filtering-Correlation-Id** en mensajes en cuarentena.

   - **Archivo:** haga clic **en Elegir archivo**. En el cuadro de diálogo que se abre, busque y seleccione el archivo .eml o .msg y, a continuación, haga clic **en Abrir**.

   > [!NOTE]
   > La capacidad de enviar mensajes tan antiguos como 30 días se ha suspendido temporalmente para Defender para Office 365 clientes. Los administradores solo podrán volver 7 días atrás.

2. En la **sección Destinatarios,** especifique uno o varios destinatarios con los que desea ejecutar una comprobación de directiva. La comprobación de directivas determinará si el correo electrónico omitió el examen debido a directivas de usuario u organización.

3. En la **sección Motivo del envío,** seleccione una de las siguientes opciones:

   - **No se debería haber bloqueado**

   - **Debería haber sido bloqueado:** Seleccione **Correo no deseado,** **Suplantación** de identidad o **Malware.** Si no está seguro, use su mejor criterio.

4. Cuando haya terminado, haga clic en el **botón Enviar.**

   ![Ejemplo de envío de nueva dirección URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Enviar una dirección URL sospechosa a Microsoft

1. En la **sección Tipo de objeto,** seleccione **Dirección URL**. En el cuadro que aparece, escriba la dirección URL completa (por ejemplo, `https://www.fabrikam.com/marketing.html` ).

2. En la **sección Motivo del envío,** seleccione una de las siguientes opciones:

   - **No se debería haber bloqueado**

   - **Debería haber sido bloqueado:** Seleccione **Phishing** o **Malware**.

3. Cuando haya terminado, haga clic en el **botón Enviar.**

   ![Ejemplo de nuevo envío de correo electrónico](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Enviar un archivo sospechoso a Microsoft

1. En la **sección Tipo de objeto,** seleccione **Datos adjuntos**.

2. Haga clic **en Elegir archivo**. En el cuadro de diálogo que se abre, busque y seleccione el archivo y, a continuación, haga clic en **Abrir**.

3. En la **sección Motivo del envío,** seleccione una de las siguientes opciones:

   - **No se debería haber bloqueado**

   - **Debería haber sido bloqueado:** **el malware** es la única opción y se selecciona automáticamente.

4. Cuando haya terminado, haga clic en el **botón Enviar.**

   ![Ejemplo de nuevo envío de datos adjuntos](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a>Ver elementos enviados para el análisis

En el Centro de & cumplimiento, vaya a **Envíos** de administración de amenazas , compruebe que está en la pestaña \> Enviado para **el análisis**

Cerca de la parte superior de la página, puede escribir una fecha de inicio, una fecha de finalización y ( de forma predeterminada) puede filtrar por identificador de envío **(un** valor GUID que se asigna a cada envío) especificando un valor en el cuadro y haciendo clic en el botón Actualizar ![ ](../../media/scc-quarantine-refresh.png) . Update

Para cambiar los criterios de filtro, haga clic en el botón **Identificador de** envío y elija uno de los siguientes valores:

- **Sender**
- **Asunto/DIRECCIÓN URL/Nombre de archivo**
- **Enviado por**
- **Tipo de envío**
- **Estado**

![Nuevas opciones de filtro para envíos de administrador](../../media/admin-submission-email-filter-options.png)

Para exportar los resultados, haga clic **en Exportar** cerca de la parte superior de la página y seleccione Datos **del gráfico** o **Tabla**. En el cuadro de diálogo que aparece, guarde el .csv archivo.

Debajo del gráfico, hay tres pestañas: **Correo** electrónico (predeterminado), **DIRECCIÓN URL** y **Datos adjuntos**.

### <a name="view-admin-email-submissions"></a>Ver envíos de correo electrónico de administrador

Haga clic en **la pestaña Correo** electrónico.

Puede hacer clic en el **botón Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:

- **Fecha**
- **Identificador de envío:** valor GUID que se asigna a cada envío.
- **Enviado por**<sup>\*</sup>
- **Asunto**<sup>\*</sup>
- **Sender**
- **IP del remitente**<sup>\*</sup>
- **Tipo de envío**
- **Motivo de entrega**
- **Estado**<sup>\*</sup>

  <sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.

#### <a name="admin-submission-rescan-details"></a>Detalles de reescaneo de envío de administrador

Los mensajes que se envían en envíos de administración se examinan de nuevo y los resultados se muestran en el menú desplegable de detalles:

- Si hubo un error en la autenticación de correo electrónico del remitente en el momento de la entrega.
- Información sobre los aciertos de directiva que puedan haber afectado o invalidado el veredicto de un mensaje.
- Actualice los resultados de cancelación para ver si las direcciones URL o los archivos contenidos en el mensaje son malintencionados o no.
- Comentarios de los calificadores.

Si se encontró una invalidación, se volverá a ejecutar una detección que se completará en unos minutos. Si no hubo un problema en la autenticación o entrega de correo electrónico no se vio afectado por una invalidación, los comentarios de los calificadores podrían tardar hasta un día.

### <a name="view-admin-url-submissions"></a>Ver envíos de url de administrador

Haga clic en la **pestaña Dirección** URL.

Puede hacer clic en el **botón Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:

- **Fecha**
- **Identificador de envío**
- **Enviado por**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **Tipo de envío**
- **Estado**<sup>\*</sup>

  <sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.

### <a name="view-admin-attachment-submissions"></a>Ver envíos de datos adjuntos de administrador

Haga clic en **la pestaña Datos** adjuntos.

Puede hacer clic en el **botón Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:

- **Fecha**
- **Identificador de envío**
- **Enviado por**<sup>\*</sup>
- **Nombre de archivo**<sup>\*</sup>
- **Tipo de envío**
- **Estado**<sup>\*</sup>

  <sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.

## <a name="view-user-submissions-to-microsoft"></a>Ver envíos de usuario a Microsoft

Si ha implementado el complemento Report [Message](enable-the-report-message-add-in.md), el complemento [Report Phishing](enable-the-report-phish-add-in.md)o los usuarios usan los informes integrados en Outlook en la [web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)puede ver lo que los usuarios están informando en la pestaña **Envíos** de usuarios.

1. En el Centro de & cumplimiento, vaya a **Envíos de administración** \> **de amenazas**.

2. Seleccione la **pestaña Envíos de** usuario y, a continuación, haga clic **en Nuevo envío.**

Puede hacer clic en el **botón Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:

- **Enviado en**
- **Enviado por**<sup>\*</sup>
- **Asunto**<sup>\*</sup>
- **Sender**
- **IP del remitente**<sup>\*</sup>
- **Tipo de envío**

<sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.

Cerca de la parte superior de la página, puede escribir una fecha de  inicio, una fecha de finalización y , de forma predeterminada, puede filtrar por remitente especificando un valor en el cuadro y haciendo clic en el botón ![ Actualizar ](../../media/scc-quarantine-refresh.png) . Update

Para cambiar los criterios de filtro, haga clic en el **botón Remitente** y elija uno de los siguientes valores:

- **Dominio del remitente**
- **Asunto**
- **Enviado por**
- **Tipo de envío**
- **IP del remitente**

![Nuevas opciones de filtro para envíos de usuarios](../../media/user-submissions-filter-options.png)

Para exportar los resultados, haga clic **en Exportar** cerca de la parte superior de la página y seleccione Datos **del gráfico** o **Tabla**. En el cuadro de diálogo que aparece, guarde el .csv archivo.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>Ver envíos de usuario al buzón personalizado

**Si** ha configurado un [buzón](user-submission.md) personalizado para recibir mensajes notificados por el usuario, puede ver y enviar también mensajes que se entregaron al buzón de informes.

1. En el Centro de & cumplimiento, vaya a **Envíos de administración** \> **de amenazas**.

2. Seleccione la **pestaña Buzón personalizado.**

Puede hacer clic en el **botón Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:

- **Enviado en**
- **Enviado por**<sup>\*</sup>
- **Asunto**<sup>\*</sup>
- **Sender**
- **IP del remitente**<sup>\*</sup>
- **Tipo de envío**

Cerca de la parte superior de la página, puede escribir una fecha de inicio, una fecha de finalización y puede filtrar por **Enviado** especificando un valor en el cuadro y haciendo clic en el botón ![ Actualizar ](../../media/scc-quarantine-refresh.png) . Update

Para exportar los resultados, haga clic **en Exportar** cerca de la parte superior de la página y seleccione Datos **del gráfico** o **Tabla**. En el cuadro de diálogo que aparece, guarde el .csv archivo.

> [!NOTE]
> Si las organizaciones están configuradas para enviar solo al buzón personalizado, los mensajes notificados no se enviarán para volver a examinarse y los resultados en el portal de mensajes notificados por el usuario siempre estarán vacíos.

## <a name="undo-user-submissions"></a>Deshacer envíos de usuarios

Una vez que un usuario envía un correo electrónico sospechoso al buzón personalizado, el usuario y el administrador no tienen ninguna opción para deshacer el envío. Si el usuario desea recuperar el correo electrónico, estará disponible para su recuperación en las carpetas Elementos eliminados o Correo no deseado.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Enviar mensajes a Microsoft desde el buzón personalizado

Si ha configurado el buzón personalizado para interceptar mensajes notificados por el usuario sin enviar los mensajes a Microsoft, puede buscar y enviar mensajes específicos a Microsoft para su análisis. Esto mueve de forma eficaz un envío de usuario a un envío de administrador.

En la **pestaña Mensajes notificados por** el usuario, seleccione un mensaje en la lista, haga clic en el botón Acción y realice una de las siguientes selecciones: 

- **Informe limpio**
- **Report phishing**
- **Informar de malware**
- **Notificar correo no deseado**

![Nuevas opciones en el botón Acción](../../media/user-submission-custom-mailbox-action-button.png)
