---
title: Más información sobre la retención para Yammer
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Más información sobre las directivas de retención que se aplican a Yammer.
ms.openlocfilehash: 0426fdf04090e535a99f8acd3bf376adfb016796
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917806"
---
# <a name="learn-about-retention-for-yammer"></a>Más información sobre la retención para Yammer

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Esta característica se encuentra en versión preliminar y todavía no está disponible para todos los clientes.

La información de este artículo complementa el contenido de [Más información sobre la retención](retention.md) porque tiene información que es específica de Yammer.

Para otras cargas de trabajo, vea:

- [Obtenga más información sobre la retención de SharePoint y OneDrive](retention-policies-sharepoint.md)
- [Más información sobre las directivas de retención para Microsoft Teams](retention-policies-teams.md)
- [Más información sobre las directivas de retención de Exchange](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>Qué se incluye para la retención y eliminación

Los siguientes elementos Yammer se pueden retener y eliminar mediante directivas de retención para los Yammer: chats y mensajes de canal.

En estos mensajes no se incluyen las reacciones de otras personas en forma de iconos gestuales.

## <a name="how-retention-works-with-yammer"></a>Cómo funciona la retención con Yammer

Puede usar una directiva de retención para conservar y eliminar mensajes de la comunidad y mensajes privados en Yammer. Los mensajes privados se almacenan en una carpeta oculta en el buzón de cada usuario incluido en el mensaje, y los mensajes de la comunidad se almacenan en una carpeta oculta similar en el buzón de correo del grupo de la comunidad.

Los mensajes de Yammer no se ven afectados por las directivas de retención que se configuran para los buzones de los usuarios o grupos. Si bien los mensajes de Yammer se almacenan en Exchange, estos datos de Yammer se incluyen sólo por una directiva de retención que está configurada para los **mensajes de la comunidad de Yammer** y las ubicaciones de los **mensajes privados de Yammer**.

> [!NOTE]
> Si un usuario está incluido en una directiva de retención activa que retiene los datos de Yammer y usted elimina el buzón de un usuario incluido en esta directiva, dicho buzón se convierte en un [buzón inactivo](inactive-mailboxes-in-office-365.md) para retener los datos de Yammer. Si no necesita retener los datos de Yammer del usuario, excluya la cuenta del usuario de la directiva de retención antes de eliminar su buzón.

Una vez que se configura una directiva de retención para los mensajes de Yammer, un trabajo de temporizador del servicio de Exchange evalúa de manera periódica los elementos de la carpeta oculta en la que se almacenan estos mensajes de Yammer. El trabajo de temporizador tarda hasta siete días en ejecutarse. Cuando el período de retención de estos elementos caduca, se trasladan a la carpeta SubstrateHolds, una carpeta oculta ubicada en cada buzón de usuario o grupo para almacenar los elementos "eliminados temporalmente" antes de que se eliminen de forma permanente.

Una vez que se configura una directiva de retención para los mensajes de Yammer, las rutas que seguirá el contenido dependerán de si la directiva de retención se configura para retener y luego eliminar, solo para retener, o solo para eliminar.

Cuando la directiva de retención consiste en retener y luego eliminar:

![Diagrama de flujo de retención de los mensajes de Yammer](../media/yammerretentionlifecycle.png)

Para las dos rutas en el diagrama:

1. Si el usuario **edita o elimina un mensaje de Yammer** durante el período de retención, el mensaje original se copia (si se edita) o se traslada (si se elimina) a la carpeta SubstrateHolds de manera inmediata. El mensaje se almacena hasta que finaliza el período de retención y, luego, se elimina de forma permanente e inmediata.

2. **Si no se elimina un mensaje de Yammer**, o se editan mensajes actuales, el mensaje se traslada a la carpeta SubstrateHolds después de que el período de retención expire. Esta acción tarda hasta siete días después de la fecha de expiración. Cuando un mensaje se encuentra en la carpeta SubstrateHolds, se elimina entonces de forma permanente e inmediata. 

> [!NOTE]
> Los mensajes de la carpeta SubstrateHolds se pueden buscar con las herramientas de eDiscovery. Hasta antes de que los mensajes se eliminen de forma permanente (en la carpeta SubstrateHolds), aún se los puede encontrar con las herramientas de eDiscovery.

Cuando la directiva de retención es de solo retención, o solo eliminación, las rutas de acceso de contenido son variaciones de retener y eliminar.

### <a name="content-paths-for-retain-only-retention-policy"></a>Rutas de contenido para la directiva de retención de solo retención

1. **Si se edita o elimina un mensaje de Yammer**: se crea, de manera inmediata, una copia del mensaje original en la carpeta SubstrateHolds y se retiene ahí hasta que expire el periodo de retención. Luego, el mensaje se elimina de forma permanente e inmediata de la carpeta SubstrateHolds.

2. **Si el mensaje de Yammer no se modifica ni se elimina** y se editan mensajes actuales durante el período de retención: no sucede nada antes ni después del período de retención. El mensaje permanece en su ubicación original.

### <a name="content-paths-for-delete-only-retention-policy"></a>Rutas de contenido para la directiva de retención de sólo eliminar

1. **Si el mensaje de Yammer no se elimina** durante el período de retención: al final del período de retención, el mensaje se mueve a la carpeta SubstrateHolds. Esta acción tarda hasta siete días después de la fecha de expiración. Luego, el mensaje se elimina de forma permanente e inmediata de la carpeta SubstrateHolds.

2. **Si el usuario elimina el mensaje de Yammer** durante el período, el elemento se mueve inmediatamente a la carpeta SubstrateHolds, donde se eliminará de forma permanente e inmediata.


## <a name="messages-and-external-users"></a>Mensajes y usuarios externos

De forma predeterminada, una directiva de retención para los mensajes privados de Yammer se aplica a todos los usuarios de su organización, pero no a los usuarios externos. Puede aplicar una directiva de retención a usuarios externos con la opción **Elegir usuario** y especificando su cuenta. 

En este momento, no se admiten usuarios invitados B2B de Azure.

## <a name="when-a-user-leaves-the-organization"></a>Cuando un usuario deja la organización 

Si un usuario deja la organización y su cuenta de Microsoft 365 se elimina, los mensajes privados de Yammer que estén sujetos a la retención se almacenarán en un buzón inactivo. Estos mensajes seguirán sujetos a cualquier directiva de retención que se haya aplicado al buzón antes de pasar a estado inactivo, y el contenido estará disponible para la búsqueda de eDiscovery. Para obtener más información, consulte [Buzones de correo inactivos en Exchange Online](inactive-mailboxes-in-office-365.md). 

Si el usuario ha guardado archivos en Yammer, consulte la [sección equivalente](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) para SharePoint y OneDrive.

## <a name="limitations"></a>Limitaciones

Actualmente, las directivas de retención de Yammer se encuentran en versión preliminar y estamos trabajando continuamente para optimizar la funcionalidad de retención. Mientras tanto, tenga en cuenta las siguientes limitaciones al usar la retención para los mensajes de la comunidad de Yammer y los mensajes privados:

- Al seleccionar **Elegir usuarios** para la ubicación de los **mensajes privados de Yammer**, puede que vea invitados y usuarios sin buzón de correo. Las directivas de retención no están diseñadas para estos usuarios, así que no los seleccione.

## <a name="configuration-guidance"></a>Instrucciones de configuración

Si va a configurar la retención en Microsoft 365 por primera vez, consulte [Introducción a las directivas y las etiquetas de retención](get-started-with-retention.md).

Si está listo para configurar una directiva de retención para Yammer, consulte [Crear y configurar directivas de retención](create-retention-policies.md).