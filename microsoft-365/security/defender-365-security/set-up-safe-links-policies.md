---
title: Configurar directivas de vínculos seguros en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a ver, crear, modificar y eliminar directivas de vínculos seguros y la configuración global de vínculos seguros en Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c8b2cb8b57dcf630b3e07ac387e96ab099ca7403
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072563"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="6218b-103">Configurar directivas de vínculos seguros en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="6218b-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6218b-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="6218b-104">**Applies to**</span></span>
- [<span data-ttu-id="6218b-105">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="6218b-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6218b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6218b-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="6218b-107">Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="6218b-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="6218b-108">Si es un usuario principal que busca información sobre safelinks en Outlook, vea [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="6218b-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="6218b-109">Vínculos seguros es una característica de [Microsoft Defender para Office 365](defender-for-office-365.md) que proporciona el examen de direcciones URL de los mensajes de correo electrónico entrantes en el flujo de correo y el tiempo de comprobación de clics de las direcciones URL y vínculos en mensajes de correo electrónico y en otras ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="6218b-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="6218b-110">Para obtener más información, vea [Vínculos seguros en Microsoft Defender para Office 365](safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="6218b-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="6218b-111">No hay ninguna directiva de vínculos seguros integrada o predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6218b-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="6218b-112">Para obtener el examen de vínculos seguros de las direcciones URL, debe crear una o más directivas de vínculos seguros, tal como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="6218b-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="6218b-113">Puede configurar la configuración global para la protección de vínculos seguros **fuera** de las directivas de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="6218b-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="6218b-114">Para obtener instrucciones, vea [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="6218b-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="6218b-115">Puede configurar directivas de vínculos seguros en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones elegibles de Microsoft 365 con buzones en Exchange Online; PowerShell EOP independiente para organizaciones sin buzones de Exchange Online, pero con suscripciones de complementos de Microsoft Defender para Office 365).</span><span class="sxs-lookup"><span data-stu-id="6218b-115">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="6218b-116">Los elementos básicos de una directiva de vínculos seguros son:</span><span class="sxs-lookup"><span data-stu-id="6218b-116">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="6218b-117">La directiva de vínculos **seguros:** activar la protección de vínculos seguros, activar el examen de direcciones URL en tiempo real, especificar si se debe esperar a que se complete el examen en tiempo real antes de entregar el mensaje, activar el examen de mensajes internos, especificar si se va a realizar un seguimiento de los clics del usuario en las direcciones URL y especificar si se va a permitir a los usuarios hacer clic en la url original.</span><span class="sxs-lookup"><span data-stu-id="6218b-117">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="6218b-118">**La regla de vínculos seguros:** especifica la prioridad y los filtros de destinatarios (a quién se aplica la directiva).</span><span class="sxs-lookup"><span data-stu-id="6218b-118">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="6218b-119">La diferencia entre estos dos elementos no es obvia al administrar las directivas de vínculos seguros en el Centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="6218b-119">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="6218b-120">Al crear una directiva de vínculos seguros, está creando una regla de vínculos seguros y la directiva de vínculos seguros asociada al mismo tiempo con el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="6218b-120">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="6218b-121">Al modificar una directiva de vínculos seguros, la configuración relacionada con el nombre, la prioridad, la habilitada o deshabilitada y los filtros de destinatarios modifican la regla de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="6218b-121">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="6218b-122">Todas las demás opciones modifican la directiva de vínculos seguros asociada.</span><span class="sxs-lookup"><span data-stu-id="6218b-122">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="6218b-123">Al quitar una directiva de vínculos seguros, se quitan la regla de vínculos seguros y la directiva de vínculos seguros asociada.</span><span class="sxs-lookup"><span data-stu-id="6218b-123">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="6218b-124">En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado.</span><span class="sxs-lookup"><span data-stu-id="6218b-124">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="6218b-125">Para obtener más información, vea la sección [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="6218b-125">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6218b-126">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="6218b-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6218b-127">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="6218b-127">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="6218b-128">Para ir directamente a la **página Vínculos seguros,** use <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="6218b-128">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="6218b-129">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="6218b-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="6218b-130">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="6218b-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="6218b-131">Debe tener asignados permisos antes de poder realizar los procedimientos descritos en este artículo:</span><span class="sxs-lookup"><span data-stu-id="6218b-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="6218b-132">Para crear, modificar y eliminar directivas de vínculos seguros, debe ser miembro de los grupos de  roles Administración de  la organización o Administrador de seguridad en el Centro de cumplimiento de & de seguridad y miembro del grupo de roles Administración de la organización en Exchange Online.  </span><span class="sxs-lookup"><span data-stu-id="6218b-132">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="6218b-133">Para obtener acceso de solo lectura a directivas de vínculos seguros, debe ser miembro de los grupos de roles Lector **global** o **Lector de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="6218b-133">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="6218b-134">Para obtener más información, vea [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="6218b-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="6218b-135">Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6218b-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="6218b-136">Para más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="6218b-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="6218b-137">.</span><span class="sxs-lookup"><span data-stu-id="6218b-137">.</span></span> <span data-ttu-id="6218b-138">- El **grupo de roles Administración** de la organización de solo vista en Exchange [Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="6218b-138">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="6218b-139">Para obtener la configuración recomendada para las directivas de vínculos seguros, consulte [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="6218b-139">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="6218b-140">Permitir hasta 30 minutos para que se aplique una directiva nueva o actualizada.</span><span class="sxs-lookup"><span data-stu-id="6218b-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="6218b-141">[Las nuevas características se agregan continuamente a Microsoft Defender para Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="6218b-141">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="6218b-142">A medida que se agregan nuevas características, es posible que deba realizar ajustes en las directivas de vínculos seguros existentes.</span><span class="sxs-lookup"><span data-stu-id="6218b-142">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="6218b-143">Usar el Centro de seguridad & cumplimiento para crear directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="6218b-143">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="6218b-144">La creación de una directiva de vínculos seguros personalizada en el Centro de seguridad & cumplimiento crea la regla de vínculos seguros y la directiva de vínculos seguros asociada al mismo tiempo con el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="6218b-144">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="6218b-145">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas \> **Vínculos** seguros de ATP \> **.**</span><span class="sxs-lookup"><span data-stu-id="6218b-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="6218b-146">En la **página Vínculos seguros,** haga clic **en Crear**.</span><span class="sxs-lookup"><span data-stu-id="6218b-146">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="6218b-147">Se **abrirá el Asistente para nueva directiva de vínculos** seguros.</span><span class="sxs-lookup"><span data-stu-id="6218b-147">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="6218b-148">En la **página Nombre de la directiva,** configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="6218b-148">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="6218b-149">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="6218b-149">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="6218b-150">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="6218b-150">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="6218b-151">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6218b-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="6218b-152">En la **página Configuración** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="6218b-152">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="6218b-153">**Seleccione la acción para direcciones** URL potencialmente malintencionadas desconocidas en mensajes: Seleccione **Activar** para habilitar la protección de vínculos seguros para vínculos en mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6218b-153">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="6218b-154">**Seleccione la acción para las direcciones** URL desconocidas o potencialmente malintencionadas de Microsoft Teams: Seleccione Activar para habilitar la protección de vínculos seguros para vínculos en Teams. </span><span class="sxs-lookup"><span data-stu-id="6218b-154">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="6218b-155">**Aplicar análisis de direcciones URL** en tiempo real en busca de vínculos sospechosos y vínculos que apunten a archivos: seleccione esta opción para habilitar el examen en tiempo real de vínculos en mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6218b-155">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="6218b-156">**Espere a que se complete el examen** de direcciones URL antes de entregar el mensaje: seleccione esta opción para esperar a que se complete el examen de direcciones URL en tiempo real antes de entregar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="6218b-156">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="6218b-157">**Aplicar vínculos seguros a los** mensajes de correo electrónico enviados dentro de la organización: seleccione esta opción para aplicar la directiva Vínculos seguros a los mensajes entre remitentes internos y destinatarios internos.</span><span class="sxs-lookup"><span data-stu-id="6218b-157">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="6218b-158">**No realizar un seguimiento de los clics del** usuario: deje esta configuración sin elegir para habilitar los clics de usuario de seguimiento en las direcciones URL de los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6218b-158">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="6218b-159">**No permitir que los usuarios hagan clic en** la dirección URL original: seleccione esta opción para impedir que los usuarios hagan clic en la dirección URL original en las páginas de [advertencia.](safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="6218b-159">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="6218b-160">**No vuelva a escribir las siguientes direcciones URL:** permite obtener acceso a las direcciones URL especificadas que, de lo contrario, serían bloqueadas por vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="6218b-160">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="6218b-161">En el cuadro, escriba la dirección URL o el valor que desee y, a continuación, haga clic en</span><span class="sxs-lookup"><span data-stu-id="6218b-161">In the box, type the URL or value that you want, and then click</span></span> ![Icono de botón Agregar](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="6218b-163">.</span><span class="sxs-lookup"><span data-stu-id="6218b-163">.</span></span>

     <span data-ttu-id="6218b-164">Para quitar una entrada existente, selecciónelo y, a continuación, haga clic en</span><span class="sxs-lookup"><span data-stu-id="6218b-164">To remove an existing entry, select it and then click</span></span> ![Icono del botón Eliminar](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="6218b-166">.</span><span class="sxs-lookup"><span data-stu-id="6218b-166">.</span></span>

     <span data-ttu-id="6218b-167">Para obtener sintaxis de entrada, vea Sintaxis de entrada para la lista "No volver a [escribir las siguientes direcciones URL".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="6218b-167">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="6218b-168">Para obtener información detallada acerca de esta configuración, vea [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) y Safe Links settings for Microsoft [Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="6218b-168">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="6218b-169">Para obtener más información sobre los valores recomendados para la configuración de directivas estándar y estricta, consulte [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="6218b-169">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="6218b-170">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6218b-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6218b-171">En la **página Aplicada a** que aparece, identifique los destinatarios internos a los que se aplica la directiva.</span><span class="sxs-lookup"><span data-stu-id="6218b-171">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="6218b-172">Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción.</span><span class="sxs-lookup"><span data-stu-id="6218b-172">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="6218b-173">Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="6218b-173">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="6218b-174">Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="6218b-174">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="6218b-175">Haga **clic en Agregar una condición**.</span><span class="sxs-lookup"><span data-stu-id="6218b-175">Click **Add a condition**.</span></span> <span data-ttu-id="6218b-176">En el desplegable que aparece, seleccione una condición en **Aplicada si**:</span><span class="sxs-lookup"><span data-stu-id="6218b-176">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="6218b-177">**El destinatario es**: especifica uno o varios buzones, usuarios de correo o contactos de correo de la organización.</span><span class="sxs-lookup"><span data-stu-id="6218b-177">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="6218b-178">**El destinatario es miembro de**: Especifica uno o más grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="6218b-178">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="6218b-179">**El dominio del destinatario es**: especifica los destinatarios en uno o varios de los dominios aceptados configurados en su organización.</span><span class="sxs-lookup"><span data-stu-id="6218b-179">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="6218b-180">Después de seleccionar la condición, aparece un desplegable correspondiente con **un cuadro Cualquiera de estos.**</span><span class="sxs-lookup"><span data-stu-id="6218b-180">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="6218b-181">Haga clic en el cuadro y desplácese por la lista de valores que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="6218b-181">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="6218b-182">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un valor.</span><span class="sxs-lookup"><span data-stu-id="6218b-182">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="6218b-183">Para agregar valores adicionales, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="6218b-183">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="6218b-184">Para quitar entradas individuales, haga clic **en Quitar** ![ icono Quitar del ](../../media/scc-remove-icon.png) valor.</span><span class="sxs-lookup"><span data-stu-id="6218b-184">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="6218b-185">Para quitar toda la condición, haga clic **en Quitar** icono Quitar en ![ la ](../../media/scc-remove-icon.png) condición.</span><span class="sxs-lookup"><span data-stu-id="6218b-185">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="6218b-186">Para agregar una condición adicional, haga clic **en Agregar una condición** y seleccione un valor restante en Aplicado **si**.</span><span class="sxs-lookup"><span data-stu-id="6218b-186">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="6218b-187">Para agregar excepciones, haga clic **en Agregar una condición** y seleccione una excepción en Excepto **si**.</span><span class="sxs-lookup"><span data-stu-id="6218b-187">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="6218b-188">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="6218b-188">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="6218b-189">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6218b-189">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6218b-190">En la **página Revisar la configuración** que aparece, revisa la configuración.</span><span class="sxs-lookup"><span data-stu-id="6218b-190">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="6218b-191">Puede hacer clic **en Editar** en cada configuración para modificarla.</span><span class="sxs-lookup"><span data-stu-id="6218b-191">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="6218b-192">Cuando haya terminado, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="6218b-192">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="6218b-193">Usar el Centro de seguridad & cumplimiento para ver directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="6218b-193">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="6218b-194">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas \> **Vínculos** seguros de ATP \> **.**</span><span class="sxs-lookup"><span data-stu-id="6218b-194">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="6218b-195">En la **página Vínculos seguros,** seleccione una directiva de la lista y haga clic en ella (no active la casilla).</span><span class="sxs-lookup"><span data-stu-id="6218b-195">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="6218b-196">Los detalles de la directiva aparecen en un desplegable</span><span class="sxs-lookup"><span data-stu-id="6218b-196">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="6218b-197">Usar el Centro de seguridad & cumplimiento para modificar directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="6218b-197">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="6218b-198">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas \> **Vínculos** seguros de ATP \> **.**</span><span class="sxs-lookup"><span data-stu-id="6218b-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="6218b-199">En la **página Vínculos seguros,** seleccione una directiva de la lista y haga clic en ella (no active la casilla).</span><span class="sxs-lookup"><span data-stu-id="6218b-199">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="6218b-200">En el desplegable de detalles de la directiva que aparece, haga clic **en Editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="6218b-200">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="6218b-201">La configuración disponible en el menú desplegable que aparece es idéntica a la descrita en la sección Usar el Centro de seguridad & cumplimiento para crear directivas [de vínculos seguros.](#use-the-security--compliance-center-to-create-safe-links-policies)</span><span class="sxs-lookup"><span data-stu-id="6218b-201">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="6218b-202">Para habilitar o deshabilitar una directiva o establecer el orden de prioridad de la directiva, consulte las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="6218b-202">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="6218b-203">Habilitar o deshabilitar directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="6218b-203">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="6218b-204">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas \> **Vínculos** seguros de ATP \> **.**</span><span class="sxs-lookup"><span data-stu-id="6218b-204">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="6218b-205">Observe el valor de la **columna Estado:**</span><span class="sxs-lookup"><span data-stu-id="6218b-205">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="6218b-206">Mueva el botón de alternancia a la izquierda para deshabilitar la directiva:</span><span class="sxs-lookup"><span data-stu-id="6218b-206">Move the toggle to the left to disable the policy:</span></span> ![Desactivar directiva](../../media/scc-toggle-off.png)<span data-ttu-id="6218b-208">.</span><span class="sxs-lookup"><span data-stu-id="6218b-208">.</span></span>

   - <span data-ttu-id="6218b-209">Mueva el botón de alternancia a la derecha para habilitar la directiva:</span><span class="sxs-lookup"><span data-stu-id="6218b-209">Move the toggle to the right to enable the policy:</span></span> ![Activar directiva](../../media/scc-toggle-on.png)<span data-ttu-id="6218b-211">.</span><span class="sxs-lookup"><span data-stu-id="6218b-211">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="6218b-212">Establecer la prioridad de las directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="6218b-212">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="6218b-213">De forma predeterminada, las directivas de vínculos seguros tienen una prioridad que se basa en el orden en que se crearon (las directivas más recientes tienen menor prioridad que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="6218b-213">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="6218b-214">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="6218b-214">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="6218b-215">Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.</span><span class="sxs-lookup"><span data-stu-id="6218b-215">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="6218b-216">Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="6218b-216">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="6218b-217">Las directivas de vínculos seguros se muestran en el orden en que se procesan (la primera directiva tiene el **valor de** prioridad 0).</span><span class="sxs-lookup"><span data-stu-id="6218b-217">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

> [!NOTE]
> <span data-ttu-id="6218b-218">En el Centro de & seguridad, solo puede cambiar la prioridad de la directiva vínculos seguros después de crearla.</span><span class="sxs-lookup"><span data-stu-id="6218b-218">In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="6218b-219">En PowerShell, puede invalidar la prioridad predeterminada al crear la regla de vínculos seguros (lo que puede afectar a la prioridad de las reglas existentes).</span><span class="sxs-lookup"><span data-stu-id="6218b-219">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="6218b-220">Para cambiar la prioridad de una directiva, suba o baje la directiva en la lista (no puede modificar directamente el número de **Prioridad** en el Centro de seguridad y cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="6218b-220">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="6218b-221">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas \> **Vínculos** seguros de ATP \> **.**</span><span class="sxs-lookup"><span data-stu-id="6218b-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="6218b-222">En la **página Vínculos seguros,** seleccione una directiva de la lista y haga clic en ella (no active la casilla).</span><span class="sxs-lookup"><span data-stu-id="6218b-222">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="6218b-223">En el desplegable de detalles de la directiva que aparece, haga clic en el botón de prioridad disponible:</span><span class="sxs-lookup"><span data-stu-id="6218b-223">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="6218b-224">La directiva Vínculos seguros con **el valor de** **prioridad 0** solo tiene disponible **el botón Disminuir** prioridad.</span><span class="sxs-lookup"><span data-stu-id="6218b-224">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="6218b-225">La directiva Vínculos seguros con el valor **de prioridad** más bajo (por ejemplo, **3**) solo tiene disponible **el botón Aumentar** prioridad.</span><span class="sxs-lookup"><span data-stu-id="6218b-225">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="6218b-226">Si tiene tres o más directivas de vínculos seguros, las  directivas entre los valores de prioridad más alta y más baja tienen disponibles los botones Aumentar prioridad y Disminuir **prioridad.**</span><span class="sxs-lookup"><span data-stu-id="6218b-226">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="6218b-227">Haga **clic en Aumentar prioridad** o Disminuir **prioridad** para cambiar el valor **De** prioridad.</span><span class="sxs-lookup"><span data-stu-id="6218b-227">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="6218b-228">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="6218b-228">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="6218b-229">Usar el Centro de seguridad & cumplimiento para quitar directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="6218b-229">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="6218b-230">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas \> **Vínculos** seguros de ATP \> **.**</span><span class="sxs-lookup"><span data-stu-id="6218b-230">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="6218b-231">En la **página Vínculos seguros,** seleccione una directiva de la lista y haga clic en ella (no active la casilla).</span><span class="sxs-lookup"><span data-stu-id="6218b-231">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="6218b-232">En el desplegable de detalles de directiva que aparece, haga clic en **Eliminar** directiva y, a continuación, haga clic en **Sí** en el cuadro de diálogo de advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="6218b-232">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="6218b-233">Usar PowerShell de Exchange Online o PowerShell de EOP independiente para configurar directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="6218b-233">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="6218b-234">Como se describió anteriormente, una directiva de vínculos seguros consta de una directiva de vínculos seguros y una regla de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="6218b-234">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="6218b-235">En PowerShell, la diferencia entre las directivas de vínculos seguros y las reglas de vínculos seguros es aparente.</span><span class="sxs-lookup"><span data-stu-id="6218b-235">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="6218b-236">Las directivas de vínculos seguros se administran mediante los cmdlets **\* -SafeLinksPolicy** y se administran reglas de vínculos seguros mediante los cmdlets **\* -SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="6218b-236">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="6218b-237">En PowerShell, primero se crea la directiva de vínculos seguros y, a continuación, se crea la regla de vínculos seguros que identifica la directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="6218b-237">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="6218b-238">En PowerShell, se modifica la configuración de la directiva de vínculos seguros y la regla de vínculos seguros por separado.</span><span class="sxs-lookup"><span data-stu-id="6218b-238">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="6218b-239">Al quitar una directiva de vínculos seguros de PowerShell, la regla de vínculos seguros correspondiente no se quita automáticamente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="6218b-239">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="6218b-240">Usar PowerShell para crear directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="6218b-240">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="6218b-241">Crear una directiva de vínculos seguros en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="6218b-241">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="6218b-242">Cree la directiva de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="6218b-242">Create the safe links policy.</span></span>
2. <span data-ttu-id="6218b-243">Cree la regla de vínculos seguros que especifica la directiva de vínculos seguros a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="6218b-243">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="6218b-244">Puede crear una nueva regla de vínculos seguros y asignarle una directiva de vínculos seguros existente y sin asociar.</span><span class="sxs-lookup"><span data-stu-id="6218b-244">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="6218b-245">Una regla de vínculos seguros no se puede asociar a más de una directiva de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="6218b-245">A safe links rule can't be associated with more than one safe links policy.</span></span>
> 
> - <span data-ttu-id="6218b-246">Puede configurar las siguientes opciones en nuevas directivas de vínculos seguros en PowerShell que no estén disponibles en el Centro de seguridad y cumplimiento de & hasta después de crear la directiva:</span><span class="sxs-lookup"><span data-stu-id="6218b-246">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
> 
>   - <span data-ttu-id="6218b-247">Cree la nueva directiva como deshabilitada (_Habilitada_ `$false` en el cmdlet **New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="6218b-247">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="6218b-248">Establezca la prioridad de la directiva durante la creación (_Prioridad_ _\<Number\>_ ) en el cmdlet **New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="6218b-248">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
> 
> - <span data-ttu-id="6218b-249">Una nueva directiva de vínculos seguros que cree en PowerShell no está visible en el Centro de seguridad & cumplimiento hasta que asigne la directiva a una regla de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="6218b-249">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="6218b-250">Paso 1: Usar PowerShell para crear una directiva de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="6218b-250">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="6218b-251">Para crear una directiva de vínculos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6218b-251">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - <span data-ttu-id="6218b-252">Para obtener más información acerca de la sintaxis de entrada que se va a usar para el parámetro _DoNotRewriteUrls,_ vea [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="6218b-252">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
> 
> - <span data-ttu-id="6218b-253">Para obtener una sintaxis adicional que puede usar para el parámetro _DoNotRewriteUrls_ al modificar las directivas de vínculos seguros existentes mediante el cmdlet **Set-SafeLinksPolicy,** vea la sección Usar [PowerShell](#use-powershell-to-modify-safe-links-policies) para modificar directivas de vínculos seguros más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="6218b-253">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="6218b-254">En este ejemplo se crea una directiva de vínculos seguros denominada Contoso All con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="6218b-254">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="6218b-255">Activa la detección y reescritura de direcciones URL en los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6218b-255">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="6218b-256">Activa el examen de direcciones URL en Teams (solo vista previa de TAP).</span><span class="sxs-lookup"><span data-stu-id="6218b-256">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="6218b-257">Activa el examen en tiempo real de las direcciones URL en las que se hace clic, incluidos los vínculos en los que se hace clic que apuntan a archivos.</span><span class="sxs-lookup"><span data-stu-id="6218b-257">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="6218b-258">Espere a que se complete el examen de direcciones URL antes de entregar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="6218b-258">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="6218b-259">Activa la detección y reescritura de direcciones URL para los mensajes internos.</span><span class="sxs-lookup"><span data-stu-id="6218b-259">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="6218b-260">Realizar un seguimiento de los clics de usuario relacionados con la protección de vínculos seguros (no estamos usando el parámetro _DoNotTrackUserClicks_ y el valor predeterminado es $false, lo que significa que se realiza un seguimiento de los clics de usuario).</span><span class="sxs-lookup"><span data-stu-id="6218b-260">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="6218b-261">No permitir que los usuarios hagan clic en la dirección URL original.</span><span class="sxs-lookup"><span data-stu-id="6218b-261">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="6218b-262">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="6218b-262">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="6218b-263">Paso 2: Usar PowerShell para crear una regla de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="6218b-263">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="6218b-264">Para crear una regla de vínculos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6218b-264">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="6218b-265">En este ejemplo se crea una regla de vínculos seguros denominada Contoso All con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="6218b-265">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="6218b-266">La regla está asociada con la directiva de vínculos seguros denominada Contoso All.</span><span class="sxs-lookup"><span data-stu-id="6218b-266">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="6218b-267">La regla se aplica a todos los destinatarios del contoso.com dominio.</span><span class="sxs-lookup"><span data-stu-id="6218b-267">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="6218b-268">Dado que no estamos usando el parámetro _Priority,_ se usa la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6218b-268">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="6218b-269">La regla está habilitada (no estamos usando el parámetro _Enabled_ y el valor predeterminado es `$true` ).</span><span class="sxs-lookup"><span data-stu-id="6218b-269">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="6218b-270">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="6218b-270">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="6218b-271">Usar PowerShell para ver directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="6218b-271">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="6218b-272">Para ver las directivas de vínculos seguros existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6218b-272">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="6218b-273">En este ejemplo se devuelve una lista resumida de todas las directivas de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="6218b-273">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="6218b-274">En este ejemplo se devuelve información detallada sobre la directiva de vínculos seguros denominada Ejecutivos de Contoso.</span><span class="sxs-lookup"><span data-stu-id="6218b-274">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="6218b-275">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="6218b-275">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="6218b-276">Usar PowerShell para ver reglas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="6218b-276">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="6218b-277">Para ver las reglas de vínculos seguros existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6218b-277">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="6218b-278">En este ejemplo se devuelve una lista resumida de todas las reglas de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="6218b-278">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="6218b-279">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="6218b-279">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="6218b-280">En este ejemplo se devuelve información detallada para la regla de vínculos seguros denominada Ejecutivos de Contoso.</span><span class="sxs-lookup"><span data-stu-id="6218b-280">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="6218b-281">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="6218b-281">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="6218b-282">Usar PowerShell para modificar directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="6218b-282">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="6218b-283">No puede cambiar el nombre de una directiva de vínculos seguros en PowerShell (el cmdlet **Set-SafeLinksPolicy** no tiene ningún _parámetro Name)._</span><span class="sxs-lookup"><span data-stu-id="6218b-283">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="6218b-284">Al cambiar el nombre de una directiva de vínculos seguros en el Centro de seguridad & cumplimiento, solo se cambia el nombre de la regla de vínculos _seguros._</span><span class="sxs-lookup"><span data-stu-id="6218b-284">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="6218b-285">La única consideración adicional para modificar directivas de vínculos seguros en PowerShell es la sintaxis disponible para el parámetro _DoNotRewriteUrls_ (la lista ["No volver](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)a escribir las siguientes direcciones URL" ):</span><span class="sxs-lookup"><span data-stu-id="6218b-285">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="6218b-286">Para agregar valores que reemplacen las entradas existentes, use la sintaxis siguiente: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="6218b-286">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="6218b-287">Para agregar o quitar valores sin afectar a otras entradas existentes, use la sintaxis siguiente: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="6218b-287">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="6218b-288">De lo contrario, la misma configuración está disponible al crear una directiva de vínculos seguros como se describe en el paso [1: Usar PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) para crear una directiva de vínculos seguros anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="6218b-288">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="6218b-289">Para modificar una directiva de vínculos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6218b-289">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="6218b-290">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="6218b-290">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="6218b-291">Usar PowerShell para modificar reglas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="6218b-291">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="6218b-292">La única configuración que no está disponible al modificar una regla de vínculos seguros en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="6218b-292">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="6218b-293">Para habilitar o deshabilitar las reglas de vínculos seguros existentes, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="6218b-293">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="6218b-294">De lo contrario, la misma configuración está disponible al crear una regla tal como se describe en el paso [2: Usar PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) para crear una regla de vínculos seguros anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="6218b-294">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="6218b-295">Para modificar una regla de vínculos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6218b-295">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="6218b-296">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="6218b-296">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="6218b-297">Usar PowerShell para habilitar o deshabilitar reglas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="6218b-297">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="6218b-298">Habilitar o deshabilitar una regla de vínculos seguros en PowerShell habilita o deshabilita toda la directiva de vínculos seguros (la regla de vínculos seguros y la directiva de vínculos seguros asignada).</span><span class="sxs-lookup"><span data-stu-id="6218b-298">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="6218b-299">Para habilitar o deshabilitar una regla de vínculos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6218b-299">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="6218b-300">En este ejemplo se deshabilita la regla de vínculos seguros denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="6218b-300">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="6218b-301">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="6218b-301">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="6218b-302">Para obtener información detallada acerca de la sintaxis y los parámetros, vea [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) y [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="6218b-302">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="6218b-303">Usar PowerShell para establecer la prioridad de las reglas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="6218b-303">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="6218b-304">El valor de prioridad máximo que se puede establecer en una regla es 0.</span><span class="sxs-lookup"><span data-stu-id="6218b-304">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="6218b-305">El valor mínimo que se puede establecer depende del número de reglas.</span><span class="sxs-lookup"><span data-stu-id="6218b-305">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="6218b-306">Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4.</span><span class="sxs-lookup"><span data-stu-id="6218b-306">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="6218b-307">El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas.</span><span class="sxs-lookup"><span data-stu-id="6218b-307">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="6218b-308">Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="6218b-308">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="6218b-309">Para establecer la prioridad de una regla de vínculos seguros en PowerShell, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6218b-309">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="6218b-310">Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2.</span><span class="sxs-lookup"><span data-stu-id="6218b-310">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="6218b-311">Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="6218b-311">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="6218b-312">Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-SafeLinksRule** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="6218b-312">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="6218b-313">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="6218b-313">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="6218b-314">Usar PowerShell para quitar directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="6218b-314">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="6218b-315">Cuando usa PowerShell para quitar una directiva de vínculos seguros, no se quita la regla de vínculos seguros correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6218b-315">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="6218b-316">Para quitar una directiva de vínculos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6218b-316">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="6218b-317">En este ejemplo se quita la directiva de vínculos seguros denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="6218b-317">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="6218b-318">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="6218b-318">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="6218b-319">Usar PowerShell para quitar reglas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="6218b-319">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="6218b-320">Cuando usa PowerShell para quitar una regla de vínculos seguros, no se quita la directiva de vínculos seguros correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6218b-320">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="6218b-321">Para quitar una regla de vínculos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6218b-321">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="6218b-322">En este ejemplo se quita la regla de vínculos seguros denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="6218b-322">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="6218b-323">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="6218b-323">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="6218b-324">Para comprobar que vínculos seguros está analizando mensajes, compruebe los informes disponibles de Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="6218b-324">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="6218b-325">Para obtener más información, vea [View reports for Defender for Office 365](view-reports-for-mdo.md) y Use Explorer in the Security & Compliance [Center](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="6218b-325">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="6218b-326">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="6218b-326">How do you know these procedures worked?</span></span>

<span data-ttu-id="6218b-327">Para comprobar que ha creado, modificado o quitado correctamente directivas de vínculos seguros, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6218b-327">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="6218b-328">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas \> **Vínculos** seguros de ATP \> **.**</span><span class="sxs-lookup"><span data-stu-id="6218b-328">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="6218b-329">Compruebe la lista de directivas, sus **valores de** estado y sus **valores de** prioridad.</span><span class="sxs-lookup"><span data-stu-id="6218b-329">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="6218b-330">Para ver más detalles, seleccione la directiva de la lista y vea los detalles en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="6218b-330">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="6218b-331">En PowerShell de Exchange Online o Exchange Online Protection PowerShell, reemplace por el nombre de la directiva o regla, ejecute el siguiente comando y \<Name\> compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="6218b-331">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```