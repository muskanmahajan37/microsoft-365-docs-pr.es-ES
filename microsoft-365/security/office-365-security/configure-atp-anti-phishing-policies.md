---
title: Configurar las directivas de protección contra suplantación de ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre cómo crear, modificar y eliminar las Directivas avanzadas de suplantación de identidad (ATP) que están disponibles en las organizaciones con la protección contra amenazas avanzada (ATP) de Office 365.
ms.openlocfilehash: b0316133c90837bedc657bde355f31d50ffe76ea
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537466"
---
# <a name="configure-atp-anti-phishing-policies-in-office-365"></a><span data-ttu-id="1acd7-103">Configurar las directivas de protección contra suplantación de identidad (ATP) en Office 365</span><span class="sxs-lookup"><span data-stu-id="1acd7-103">Configure ATP anti-phishing policies in Office 365</span></span>

<span data-ttu-id="1acd7-104">Las directivas antiphishing de ATP forman parte de la [protección contra amenazas avanzada de Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="1acd7-104">ATP anti-phishing policies are part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="1acd7-105">Las directivas antiphishing de ATP pueden ayudar a proteger a su organización de ataques de suplantación de identidad (phishing) malintencionados y otros tipos de ataques de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="1acd7-105">ATP anti-phishing policies can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="1acd7-106">Para obtener más información acerca de las diferencias entre las directivas antiphishing en Exchange Online Protection (EOP) y las directivas antiphishing de ATP, consulte [protección contra la suplantación de identidad (phishing) en Office 365](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="1acd7-106">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and ATP anti-phishing policies, see [Anti-phishing protection in Office 365](anti-phishing-protection.md).</span></span>

<span data-ttu-id="1acd7-107">Los administradores pueden ver, editar y configurar (pero no eliminar) la Directiva antiphishing predeterminada de ATP.</span><span class="sxs-lookup"><span data-stu-id="1acd7-107">Admins can view, edit, and configure (but not delete) the default ATP anti-phishing policy.</span></span> <span data-ttu-id="1acd7-108">Para una mayor granularidad, también puede crear directivas antiphishing de ATP personalizadas que se aplican a usuarios, grupos o dominios específicos de la organización.</span><span class="sxs-lookup"><span data-stu-id="1acd7-108">For greater granularity, you can also create custom ATP anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="1acd7-109">Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="1acd7-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="1acd7-110">Puede configurar las directivas antiphishing de ATP en el centro de seguridad & cumplimiento de Office 365 o en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1acd7-110">You can configure ATP anti-phishing policies in the Office 365 Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="1acd7-111">Para obtener información acerca de la configuración de una directiva de antiphishing integrada más limitada que está disponible en las organizaciones de Exchange Online Protection (es decir, Office 365 organizaciones sin ATP), vea [Configure the default anti-phishing Policy in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="1acd7-111">For information about configuring the more limited built-in anti-phishing policy that's available in Exchange Online Protection organizations (that is, Office 365 organizations without ATP), see [Configure the default anti-phishing policy in EOP](configure-anti-phishing-policies-eop.md).</span></span>

## <a name="atp-anti-phishing-policies-in-the-office-365-security--compliance-center-vs-exchange-online-powershell"></a><span data-ttu-id="1acd7-112">Directivas antiphishing de ATP en el centro de seguridad & cumplimiento de Office 365 frente a PowerShell de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1acd7-112">ATP anti-phishing policies in the Office 365 Security & Compliance Center vs Exchange Online PowerShell</span></span>

<span data-ttu-id="1acd7-113">Los elementos básicos de una directiva contra la suplantación de identidad ATP son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1acd7-113">The basic elements of an ATP anti-phishing policy are:</span></span>

- <span data-ttu-id="1acd7-114">**La Directiva ANTIPHISH**: especifica las protecciones de suplantación de identidad (phishing) que se deben habilitar o deshabilitar y las acciones para aplicar opciones.</span><span class="sxs-lookup"><span data-stu-id="1acd7-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="1acd7-115">**La regla anti-phish**: especifica la prioridad y los filtros de destinatarios (a los que se aplica la Directiva) para una directiva antiphishing.</span><span class="sxs-lookup"><span data-stu-id="1acd7-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="1acd7-116">La diferencia entre estos dos elementos no es obvia cuando se administran las directivas antiphishing de ATP en el centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="1acd7-116">The difference between these two elements isn't obvious when you manage ATP anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="1acd7-117">Al crear una directiva contra la suplantación de identidad ATP en el centro de seguridad & cumplimiento, en realidad está creando una regla ANTIPHISH y la Directiva ANTIPHISH asociada al mismo tiempo con el mismo nombre para ambas.</span><span class="sxs-lookup"><span data-stu-id="1acd7-117">When you create an ATP anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="1acd7-118">Cuando modifica una directiva de ATP antiphishing en el centro de seguridad & cumplimiento, la configuración relacionada con los filtros nombre, prioridad, habilitado o deshabilitado, y de destinatarios modifica la regla contra el phish.</span><span class="sxs-lookup"><span data-stu-id="1acd7-118">When you modify an ATP anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="1acd7-119">Todas las demás opciones modifican la Directiva ANTIPHISH asociada.</span><span class="sxs-lookup"><span data-stu-id="1acd7-119">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="1acd7-120">Al quitar una directiva de ATP contra la suplantación de identidad del centro de seguridad & cumplimiento, se quita la regla antiphishing y la Directiva de ANTIPHISH asociada.</span><span class="sxs-lookup"><span data-stu-id="1acd7-120">When you remove an ATP anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="1acd7-121">En Exchange Online PowerShell, la diferencia entre las directivas antiphishing y las reglas antiphishing es evidente.</span><span class="sxs-lookup"><span data-stu-id="1acd7-121">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="1acd7-122">Las directivas antiphishing se administran mediante los \*\* \*cmdlets-AntiPhishPolicy\*\* y se administran las reglas antiphishing mediante los \*\* \*cmdlets-AntiPhishRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="1acd7-122">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="1acd7-123">En PowerShell, se crea la Directiva ANTIPHISH en primer lugar y, a continuación, se crea la regla ANTIPHISH que identifica la Directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="1acd7-123">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="1acd7-124">En PowerShell, la configuración de la Directiva antiphishing y la regla antiphishing se modifican por separado.</span><span class="sxs-lookup"><span data-stu-id="1acd7-124">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

- <span data-ttu-id="1acd7-125">Cuando se quita una directiva ANTIPHISH de PowerShell, la regla antiphishing correspondiente no se elimina automáticamente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="1acd7-125">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="1acd7-126">Directiva antiphishing de ATP predeterminada</span><span class="sxs-lookup"><span data-stu-id="1acd7-126">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="1acd7-127">Cada organización ATP tiene una directiva antiphishing de ATP integrada llamada Office365 ANTIPHISH predeterminada con estas propiedades:</span><span class="sxs-lookup"><span data-stu-id="1acd7-127">Every ATP organization has a built-in ATP anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="1acd7-128">La Directiva ANTIPHISH denominada Office365 ANTIPHISH predeterminada se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla antiphishing (filtros de destinatario) asociada a la Directiva.</span><span class="sxs-lookup"><span data-stu-id="1acd7-128">The anti-phish policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="1acd7-129">La Directiva denominada predeterminada de la ANTIPHISH de Office365 tiene el valor de prioridad personalizado **más bajo** que no se puede modificar (la Directiva se aplica siempre en último lugar).</span><span class="sxs-lookup"><span data-stu-id="1acd7-129">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="1acd7-130">Cualquier directiva personalizada que cree siempre tendrá una prioridad mayor que la Directiva denominada Office365 ANTIPHISH predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1acd7-130">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="1acd7-131">La Directiva denominada Office365 ANTIPHISH predeterminada es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True`) y no se puede eliminar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1acd7-131">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="1acd7-132">Para aumentar la eficacia de la protección contra suplantación de identidad (phishing), puede crear directivas antiphishing personalizadas de ATP con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="1acd7-132">To increase the effectiveness of anti-phishing protection, you can create custom ATP anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1acd7-133">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="1acd7-133">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1acd7-134">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="1acd7-134">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="1acd7-135">Para ir directamente a la página **contra la suplantación de identidad ATP** , use <https://protection.office.com/antiphishing>.</span><span class="sxs-lookup"><span data-stu-id="1acd7-135">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="1acd7-136">Para conectarse a PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1acd7-136">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="1acd7-137">Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="1acd7-137">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="1acd7-138">Para agregar, modificar y eliminar directivas antiphishing, debe ser miembro de los grupos de roles administración de la **organización** o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="1acd7-138">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="1acd7-139">Para el acceso de solo lectura a las directivas antiphishing, debe ser miembro del grupo de roles **lector de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="1acd7-139">For read-only access to anti-phishing policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="1acd7-140">Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="1acd7-140">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="1acd7-141">Para obtener la configuración recomendada para las directivas antiphishing de ATP, consulte [configuración de la Directiva de antiphishing de Office ATP](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="1acd7-141">For our recommended settings for ATP anti-phishing policies, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="1acd7-142">Permitir que se aplique una directiva nueva o actualizada durante un máximo de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="1acd7-142">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="1acd7-143">Para obtener información sobre la aplicación de directivas contra la suplantación de identidad (phishing) en la canalización de filtros, consulte [Order and Precedence of email Protection in Office 365](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="1acd7-143">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection in Office 365](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a><span data-ttu-id="1acd7-144">Usar el centro de seguridad & cumplimiento para crear directivas contra la suplantación de identidad ATP</span><span class="sxs-lookup"><span data-stu-id="1acd7-144">Use the Security & Compliance Center to create ATP anti-phishing policies</span></span>

<span data-ttu-id="1acd7-145">La creación de una directiva antiphishing de ATP personalizada en el centro de seguridad & cumplimiento crea la regla ANTIPHISH y la Directiva de ANTIPHISH asociada al mismo tiempo con el mismo nombre para ambas.</span><span class="sxs-lookup"><span data-stu-id="1acd7-145">Creating a custom ATP anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="1acd7-146">Al crear una directiva contra la suplantación de identidad ATP, solo puede especificar el nombre de la Directiva, la descripción y el filtro de destinatarios que identifica a quién se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="1acd7-146">When you create an ATP anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="1acd7-147">Después de crear la Directiva, puede modificar la Directiva para cambiar o revisar la configuración predeterminada de la suplantación de identidad (phishing).</span><span class="sxs-lookup"><span data-stu-id="1acd7-147">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="1acd7-148">En el centro de seguridad & cumplimiento, vaya a **Directiva** \> de **Administración** \> de amenazas **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-148">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="1acd7-149">En la página **contra la suplantación de identidad** , haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-149">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="1acd7-150">Se abrirá el Asistente para **crear una nueva Directiva antiphishing** .</span><span class="sxs-lookup"><span data-stu-id="1acd7-150">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="1acd7-151">En la página **asigne un nombre a la Directiva** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="1acd7-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="1acd7-152">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="1acd7-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="1acd7-153">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="1acd7-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="1acd7-154">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="1acd7-155">En la página **aplicado a** que aparece, identifique los destinatarios internos a los que se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="1acd7-155">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="1acd7-156">Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción.</span><span class="sxs-lookup"><span data-stu-id="1acd7-156">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="1acd7-157">Varios valores de la misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="1acd7-157">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="1acd7-158">Diversas condiciones o excepciones usan la lógica AND (por ejemplo, _\<recipient1\>_ and _\<miembro del grupo 1\>_).</span><span class="sxs-lookup"><span data-stu-id="1acd7-158">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="1acd7-159">Haga clic en **Agregar condición**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-159">Click **Add a condition**.</span></span> <span data-ttu-id="1acd7-160">En la lista desplegable que aparece, seleccione una condición en **aplicado si**:</span><span class="sxs-lookup"><span data-stu-id="1acd7-160">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="1acd7-161">**El destinatario es**: especifica uno o más buzones de correo, usuarios de correo o contactos de correo de su organización.</span><span class="sxs-lookup"><span data-stu-id="1acd7-161">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="1acd7-162">**El destinatario es un miembro de**: especifica uno o más grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="1acd7-162">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="1acd7-163">**El dominio del destinatario es**: especifica los destinatarios en uno o varios de los dominios aceptados configurados en Office 365.</span><span class="sxs-lookup"><span data-stu-id="1acd7-163">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in Office 365.</span></span>

   <span data-ttu-id="1acd7-164">Después de seleccionar la condición, aparece la lista desplegable correspondiente con una **de estas** casillas.</span><span class="sxs-lookup"><span data-stu-id="1acd7-164">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="1acd7-165">Haga clic en el cuadro y desplácese por la lista de valores que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="1acd7-165">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="1acd7-166">Haga clic en el cuadro y comience a escribir para filtrar la lista y seleccionar un valor.</span><span class="sxs-lookup"><span data-stu-id="1acd7-166">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="1acd7-167">Para agregar más valores, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="1acd7-167">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="1acd7-168">Para quitar entradas individuales, haga **Remove** ![clic en el](../../media/scc-remove-icon.png) icono quitar quitar del valor.</span><span class="sxs-lookup"><span data-stu-id="1acd7-168">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="1acd7-169">Para quitar toda la condición, haga **Remove** ![clic en quitar](../../media/scc-remove-icon.png) icono de eliminación en la condición.</span><span class="sxs-lookup"><span data-stu-id="1acd7-169">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="1acd7-170">Para agregar una condición adicional, haga clic en **Agregar condición** y seleccione un valor restante en **aplicado si**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-170">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="1acd7-171">Para agregar excepciones, haga clic en **Agregar una condición** y seleccione una excepción en **excepto si**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-171">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="1acd7-172">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="1acd7-172">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="1acd7-173">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-173">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="1acd7-174">En la página **Revise la configuración** que aparece, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="1acd7-174">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="1acd7-175">Puede hacer clic en **Editar** en cada configuración para modificarla.</span><span class="sxs-lookup"><span data-stu-id="1acd7-175">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="1acd7-176">Cuando haya terminado, haga clic en **crear esta directiva**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-176">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="1acd7-177">Haga clic en **Aceptar** en el cuadro de diálogo de confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="1acd7-177">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="1acd7-178">Después de crear la Directiva contra la suplantación de identidad ATP con estas opciones de directiva generales, siga las instrucciones de la siguiente sección para configurar las opciones de protección de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="1acd7-178">After you create the ATP anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a><span data-ttu-id="1acd7-179">Usar el centro de seguridad & cumplimiento para modificar las directivas antiphishing de ATP</span><span class="sxs-lookup"><span data-stu-id="1acd7-179">Use the Security & Compliance Center to modify ATP anti-phishing policies</span></span>

<span data-ttu-id="1acd7-180">Use los siguientes procedimientos para modificar las directivas antiphishing de ATP: una nueva directiva que ha creado o las directivas existentes que ya ha personalizado.</span><span class="sxs-lookup"><span data-stu-id="1acd7-180">Use the following procedures to modify ATP anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="1acd7-181">Si aún no está ahí, abra el centro de seguridad & cumplimiento y vaya a la **Threat management** \> **Directiva** \> de administración de amenazas de **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-181">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="1acd7-182">Seleccione la Directiva antiphishing de ATP personalizada que quiera modificar.</span><span class="sxs-lookup"><span data-stu-id="1acd7-182">Select the custom ATP anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="1acd7-183">Si ya está seleccionada, anule la selección y vuelva a seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="1acd7-183">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="1acd7-184">Aparece el control flotante **editar el nombre \<\> de la Directiva** .</span><span class="sxs-lookup"><span data-stu-id="1acd7-184">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="1acd7-185">Al hacer clic en **Editar** en cualquier sección, obtendrá acceso a la configuración de esa sección.</span><span class="sxs-lookup"><span data-stu-id="1acd7-185">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="1acd7-186">Los pasos siguientes se presentan en el orden en que aparecen las secciones, pero no son secuenciales (puede seleccionar y modificar las secciones en cualquier orden).</span><span class="sxs-lookup"><span data-stu-id="1acd7-186">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="1acd7-187">Después de hacer clic en **Editar** en una sección, la configuración disponible se presenta en un formato de asistente, pero puede saltar dentro de las páginas en cualquier orden y puede hacer clic en **Guardar** en cualquier página (o en **Cancelar** o **cerrar** ![el icono](../../media/scc-remove-icon.png) cerrar para volver a la página **editar el \<nombre\> de la Directiva** (no es necesario visitar la última página del Asistente para guardarla o dejarla).</span><span class="sxs-lookup"><span data-stu-id="1acd7-187">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="1acd7-188">**Configuración de directiva**: haga clic en **Editar** para modificar la misma configuración que estaba disponible cuando [creó la Directiva](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) en la sección anterior:</span><span class="sxs-lookup"><span data-stu-id="1acd7-188">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="1acd7-189">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="1acd7-189">**Name**</span></span>
   - <span data-ttu-id="1acd7-190">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1acd7-190">**Description**</span></span>
   - <span data-ttu-id="1acd7-191">**Aplicado a**</span><span class="sxs-lookup"><span data-stu-id="1acd7-191">**Applied to**</span></span>
   - <span data-ttu-id="1acd7-192">**Revisar la configuración**</span><span class="sxs-lookup"><span data-stu-id="1acd7-192">**Review your settings**</span></span>

   <span data-ttu-id="1acd7-193">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="1acd7-193">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="1acd7-194">**Suplantación**: haga clic en **Editar** para modificar los remitentes protegidos y los dominios protegidos en la Directiva.</span><span class="sxs-lookup"><span data-stu-id="1acd7-194">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="1acd7-195">Esta configuración es una condición para la Directiva que identifica a los remitentes suplantados para que busquen (de forma individual o por dominio) en la dirección de de los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="1acd7-195">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="1acd7-196">Para obtener más información, consulte [configuración de suplantación en las directivas de antiphishing de ATP](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="1acd7-196">For more information, see [Impersonation settings in ATP anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="1acd7-197">**Agregar usuarios para proteger**: el valor predeterminado es **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-197">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="1acd7-198">Para activarla, deslice el botón de alternancia a **activado**y, a continuación, haga clic en el botón **Agregar usuario** que aparece.</span><span class="sxs-lookup"><span data-stu-id="1acd7-198">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="1acd7-199">En el control flotante **Agregar usuario** que aparece, configure los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="1acd7-199">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="1acd7-200">**Dirección de correo electrónico**:</span><span class="sxs-lookup"><span data-stu-id="1acd7-200">**Email address**:</span></span>

        - <span data-ttu-id="1acd7-201">Haga clic en el cuadro y desplácese por la lista de usuarios que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="1acd7-201">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="1acd7-202">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario.</span><span class="sxs-lookup"><span data-stu-id="1acd7-202">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="1acd7-203">Para quitar una entrada, haga **Remove** ![clic en quitar](../../media/scc-remove-icon.png) icono de eliminación en el usuario.</span><span class="sxs-lookup"><span data-stu-id="1acd7-203">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="1acd7-204">**Nombre**: este valor se rellena en función de la dirección de correo electrónico que haya seleccionado, pero puede cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="1acd7-204">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="1acd7-205">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="1acd7-205">When you're finished, click **Save** on any page.</span></span>

    <span data-ttu-id="1acd7-206">Para editar una entrada existente, seleccione el usuario protegido en la lista.</span><span class="sxs-lookup"><span data-stu-id="1acd7-206">To edit an existing entry, select the protected user in the list.</span></span>

   - <span data-ttu-id="1acd7-207">**Agregar dominios para proteger**: configure una o ambas de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="1acd7-207">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="1acd7-208">**Incluir automáticamente los dominios que tengo**: el valor predeterminado es **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-208">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="1acd7-209">Para activarla, deslice el botón de alternancia a **activado**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-209">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="1acd7-210">**Incluir dominios personalizados**: el valor predeterminado es **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-210">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="1acd7-211">Para activarla, deslice el botón de alternancia a **activado**y, en el cuadro **Agregar dominios** , escriba el nombre de dominio (por ejemplo, contoso.com), presione entrar y repita lo mismo según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="1acd7-211">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="1acd7-212">**Acciones**: haga clic en **Editar**</span><span class="sxs-lookup"><span data-stu-id="1acd7-212">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="1acd7-213">**Si un usuario suplantado envía un correo electrónico**: configure una de las siguientes acciones para los mensajes en los que el remitente falso sea uno de los usuarios protegidos que ha especificado en **Agregar usuarios para proteger**:</span><span class="sxs-lookup"><span data-stu-id="1acd7-213">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="1acd7-214">**No aplicar ninguna acción**</span><span class="sxs-lookup"><span data-stu-id="1acd7-214">**Don't apply any action**</span></span>
       - <span data-ttu-id="1acd7-215">**Redirigir un mensaje a otras direcciones de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="1acd7-215">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="1acd7-216">**Mover mensaje a la carpeta Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="1acd7-216">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="1acd7-217">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="1acd7-217">**Quarantine the message**</span></span>
       - <span data-ttu-id="1acd7-218">**Entregar el mensaje y agregar otras direcciones a la línea CCO**</span><span class="sxs-lookup"><span data-stu-id="1acd7-218">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="1acd7-219">**Eliminar el mensaje antes de su entrega**</span><span class="sxs-lookup"><span data-stu-id="1acd7-219">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="1acd7-220">**Si un dominio suplantado envía un correo electrónico**: configure una de las siguientes acciones para los mensajes en los que el remitente falso esté en uno de los dominios protegidos que ha especificado en **Agregar dominios para proteger**:</span><span class="sxs-lookup"><span data-stu-id="1acd7-220">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

     - <span data-ttu-id="1acd7-221">**No aplicar ninguna acción**</span><span class="sxs-lookup"><span data-stu-id="1acd7-221">**Don't apply any action**</span></span>
     - <span data-ttu-id="1acd7-222">**Redirigir un mensaje a otras direcciones de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="1acd7-222">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="1acd7-223">**Mover mensaje a la carpeta Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="1acd7-223">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="1acd7-224">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="1acd7-224">**Quarantine the message**</span></span>
     - <span data-ttu-id="1acd7-225">**Entregar el mensaje y agregar otras direcciones a la línea CCO**</span><span class="sxs-lookup"><span data-stu-id="1acd7-225">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="1acd7-226">**Eliminar el mensaje antes de su entrega**</span><span class="sxs-lookup"><span data-stu-id="1acd7-226">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="1acd7-227">Haga clic en **Activar sugerencias de seguridad de suplantación** y configure cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="1acd7-227">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="1acd7-228">**Mostrar sugerencia para usuarios suplantados**: el valor predeterminado es **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-228">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="1acd7-229">Para activarla, deslice el botón de alternancia a **activado**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-229">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="1acd7-230">**Mostrar sugerencia para dominios suplantados**: el valor predeterminado es **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-230">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="1acd7-231">Para activarla, deslice el botón de alternancia a **activado**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-231">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="1acd7-232">**Mostrar sugerencia para caracteres inusuales**: el valor predeterminado es **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-232">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="1acd7-233">Para activarla, deslice el botón de alternancia a **activado**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-233">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="1acd7-234">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-234">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="1acd7-235">**Inteligencia de buzones de correo**:</span><span class="sxs-lookup"><span data-stu-id="1acd7-235">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="1acd7-236">**¿Habilitar la inteligencia de buzones?**: el valor predeterminado es **activado**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-236">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="1acd7-237">Para desactivarla, deslice el botón de alternancia a **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-237">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="1acd7-238">**¿Habilitar la protección de suplantación basada en buzones de correo?**: esta opción solo está disponible si **Habilitar inteligencia de buzones de correo?** es **activado**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-238">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="1acd7-239">En **si un usuario suplantado envía un correo electrónico**, puede especificar una de las siguientes acciones para que se realicen en los mensajes que no superen la inteligencia del buzón (las mismas acciones que están disponibles para los usuarios protegidos y los dominios protegidos):</span><span class="sxs-lookup"><span data-stu-id="1acd7-239">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="1acd7-240">**No aplicar ninguna acción**</span><span class="sxs-lookup"><span data-stu-id="1acd7-240">**Don't apply any action**</span></span>
       - <span data-ttu-id="1acd7-241">**Redirigir un mensaje a otras direcciones de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="1acd7-241">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="1acd7-242">**Mover mensaje a la carpeta Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="1acd7-242">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="1acd7-243">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="1acd7-243">**Quarantine the message**</span></span>
       - <span data-ttu-id="1acd7-244">**Entregar el mensaje y agregar otras direcciones a la línea CCO**</span><span class="sxs-lookup"><span data-stu-id="1acd7-244">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="1acd7-245">**Eliminar el mensaje antes de su entrega**</span><span class="sxs-lookup"><span data-stu-id="1acd7-245">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="1acd7-246">**Agregue los remitentes y dominios de confianza**: especifique las excepciones de la Directiva:</span><span class="sxs-lookup"><span data-stu-id="1acd7-246">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="1acd7-247">**Remitentes de confianza**:</span><span class="sxs-lookup"><span data-stu-id="1acd7-247">**Trusted senders**:</span></span>

       - <span data-ttu-id="1acd7-248">Haga clic en el cuadro y desplácese por la lista de usuarios que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="1acd7-248">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="1acd7-249">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario.</span><span class="sxs-lookup"><span data-stu-id="1acd7-249">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="1acd7-250">Para quitar una entrada, haga **Remove** ![clic en quitar](../../media/scc-remove-icon.png) icono de eliminación en el usuario.</span><span class="sxs-lookup"><span data-stu-id="1acd7-250">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="1acd7-251">**Dominios de confianza**: escriba el nombre del dominio (por ejemplo, contoso.com), presione entrar y repita el procedimiento según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="1acd7-251">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="1acd7-252">**Revise la configuración**: en lugar de hacer clic en cada paso individual, la configuración se muestra en un resumen.</span><span class="sxs-lookup"><span data-stu-id="1acd7-252">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="1acd7-253">Puede hacer clic en **Editar** en cada sección para volver a la página correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1acd7-253">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="1acd7-254">Puede activar o **desactivar** la siguiente configuración **directamente en esta** página:</span><span class="sxs-lookup"><span data-stu-id="1acd7-254">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="1acd7-255">**Usuarios protegidos**</span><span class="sxs-lookup"><span data-stu-id="1acd7-255">**Protected users**</span></span>
       - <span data-ttu-id="1acd7-256">Los **dominios** \> protegidos **incluyen los dominios que yo posee**</span><span class="sxs-lookup"><span data-stu-id="1acd7-256">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="1acd7-257">Dominios protegidos dominios **protegidos** (dominios personalizados) **Protected domains** \></span><span class="sxs-lookup"><span data-stu-id="1acd7-257">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="1acd7-258">**Inteligencia de buzones**</span><span class="sxs-lookup"><span data-stu-id="1acd7-258">**Mailbox intelligence**</span></span>

   <span data-ttu-id="1acd7-259">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="1acd7-259">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="1acd7-260">**Suplantación de identidad**: haga clic en **Editar** para activar o desactivar la inteligencia de suplantación, activar o desactivar la identificación del remitente sin autenticar en Outlook y configurar la acción para aplicar a los mensajes de los remitentes suplantados bloqueados.</span><span class="sxs-lookup"><span data-stu-id="1acd7-260">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="1acd7-261">Para obtener más información, consulte [configuración de la suplantación de identidades en directivas antiphishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="1acd7-261">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="1acd7-262">Tenga en cuenta que esta configuración es idéntica a la configuración que está disponible en la Directiva antiphishing predeterminada en EOP.</span><span class="sxs-lookup"><span data-stu-id="1acd7-262">Note that these settings are identical to the settings that are available in the default anti-phishing policy in EOP.</span></span>

   - <span data-ttu-id="1acd7-263">**Configuración del filtro de suplantación de identidad**: el valor predeterminado es **activado**y se recomienda que lo deje activado.</span><span class="sxs-lookup"><span data-stu-id="1acd7-263">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="1acd7-264">Para desactivarla, deslice el botón de alternancia a **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-264">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="1acd7-265">Para obtener más información, consulte [configurar inteligencia de identidades en Office 365](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="1acd7-265">For more information, see [Configure spoof intelligence in Office 365](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="1acd7-266">No es necesario deshabilitar la protección contra la suplantación de identidad si el registro MX no apunta a Office 365; en su lugar, se habilita el filtrado mejorado para los conectores.</span><span class="sxs-lookup"><span data-stu-id="1acd7-266">You don't need to disable anti-spoofing protection if your MX record doesn't point to Office 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="1acd7-267">Para obtener instrucciones, vea [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="1acd7-267">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="1acd7-268">**Habilitar la característica de remitente sin autenticar**: el valor predeterminado es **activado**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-268">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="1acd7-269">Para desactivarla, deslice el botón de alternancia a **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-269">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="1acd7-270">**Acciones**: especificar la acción que se realizará en los mensajes que no superen la inteligencia de identidad:</span><span class="sxs-lookup"><span data-stu-id="1acd7-270">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="1acd7-271">**Si el correo electrónico lo envía alguien que no tiene permiso para suplantar su dominio**:</span><span class="sxs-lookup"><span data-stu-id="1acd7-271">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="1acd7-272">**Mover mensaje a las carpetas de correo no deseado de los destinatarios**</span><span class="sxs-lookup"><span data-stu-id="1acd7-272">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="1acd7-273">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="1acd7-273">**Quarantine the message**</span></span>

   - <span data-ttu-id="1acd7-274">**Revise la configuración**: en lugar de hacer clic en cada paso individual, la configuración se muestra en un resumen.</span><span class="sxs-lookup"><span data-stu-id="1acd7-274">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="1acd7-275">Puede hacer clic en **Editar** en cada sección para volver a la página correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1acd7-275">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="1acd7-276">Puede activar o **desactivar** la siguiente configuración **directamente en esta** página:</span><span class="sxs-lookup"><span data-stu-id="1acd7-276">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="1acd7-277">**Habilitar la protección contra la suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="1acd7-277">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="1acd7-278">**Habilitar la característica de remitente sin autenticar**</span><span class="sxs-lookup"><span data-stu-id="1acd7-278">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="1acd7-279">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="1acd7-279">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="1acd7-280">**Configuración avanzada**: haga clic en **Editar** para configurar los umbrales de suplantación de identidad avanzada.</span><span class="sxs-lookup"><span data-stu-id="1acd7-280">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="1acd7-281">Para obtener más información, consulte [umbrales de suplantación de identidad avanzada en las directivas de antiphishing de ATP](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="1acd7-281">For more information, see [Advanced phishing thresholds in ATP anti-phishing policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="1acd7-282">**Umbrales de suplantación de identidad avanzada**: Seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="1acd7-282">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="1acd7-283">**1-estándar** (este es el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="1acd7-283">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="1acd7-284">**2-agresivo**</span><span class="sxs-lookup"><span data-stu-id="1acd7-284">**2 - Aggressive**</span></span>
   - <span data-ttu-id="1acd7-285">**3-más agresivo**</span><span class="sxs-lookup"><span data-stu-id="1acd7-285">**3 - More aggressive**</span></span>
   - <span data-ttu-id="1acd7-286">**4: más agresivo**</span><span class="sxs-lookup"><span data-stu-id="1acd7-286">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="1acd7-287">**Revise la configuración**: haga clic en **Editar** para volver a la página **umbrales de suplantación de identidad avanzada** .</span><span class="sxs-lookup"><span data-stu-id="1acd7-287">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="1acd7-288">Cuando haya terminado, haga clic en **Guardar** en cualquiera de las páginas.</span><span class="sxs-lookup"><span data-stu-id="1acd7-288">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="1acd7-289">De nuevo en la página **Editar \<el\> nombre de la Directiva** , revise la configuración y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-289">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a><span data-ttu-id="1acd7-290">Usar el centro de seguridad & cumplimiento para modificar la Directiva antiphishing de ATP predeterminada</span><span class="sxs-lookup"><span data-stu-id="1acd7-290">Use the Security & Compliance Center to modify the default ATP anti-phishing policy</span></span>

<span data-ttu-id="1acd7-291">La Directiva antiphishing de ATP predeterminada se denomina Office365 ANTIPHISH predeterminada y no aparece en la lista de directivas.</span><span class="sxs-lookup"><span data-stu-id="1acd7-291">The default ATP anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="1acd7-292">Para modificar la Directiva antiphishing de ATP predeterminada, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="1acd7-292">To modify the default ATP anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="1acd7-293">En el centro de seguridad & cumplimiento, vaya a **Directiva** \> de **Administración** \> de amenazas **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-293">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="1acd7-294">En la página **contra la suplantación de identidad** , haga clic en **directiva predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-294">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="1acd7-295">Aparecerá la página **editar la Directiva de ANTIPHISH predeterminada de Office365** .</span><span class="sxs-lookup"><span data-stu-id="1acd7-295">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="1acd7-296">Las siguientes secciones están disponibles, que contienen ajustes idénticos para cuando se [modifica una directiva personalizada](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span><span class="sxs-lookup"><span data-stu-id="1acd7-296">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span></span>

   - <span data-ttu-id="1acd7-297">**Suplantación**</span><span class="sxs-lookup"><span data-stu-id="1acd7-297">**Impersonation**</span></span>
   - <span data-ttu-id="1acd7-298">**Suplantación**</span><span class="sxs-lookup"><span data-stu-id="1acd7-298">**Spoof**</span></span>
   - <span data-ttu-id="1acd7-299">**Configuración avanzada**</span><span class="sxs-lookup"><span data-stu-id="1acd7-299">**Advanced settings**</span></span>

   <span data-ttu-id="1acd7-300">Las siguientes opciones de configuración no están disponibles cuando se modifica la directiva predeterminada:</span><span class="sxs-lookup"><span data-stu-id="1acd7-300">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="1acd7-301">Puede ver la sección y los valores de configuración de la **Directiva** , pero no hay ningún vínculo **Editar** , por lo que no puede modificar la configuración (nombre de Directiva, Descripción y a quién se aplica la Directiva (se aplica a todos los destinatarios)).</span><span class="sxs-lookup"><span data-stu-id="1acd7-301">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="1acd7-302">No puede eliminar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1acd7-302">You can't delete the default policy.</span></span>
   - <span data-ttu-id="1acd7-303">No puede cambiar la prioridad de la directiva predeterminada (siempre se aplica en último lugar).</span><span class="sxs-lookup"><span data-stu-id="1acd7-303">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="1acd7-304">En la página **editar la Directiva de ANTIPHISH predeterminada de Office365** , revise la configuración y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-304">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a><span data-ttu-id="1acd7-305">Habilitar o deshabilitar las directivas antiphishing de ATP personalizadas</span><span class="sxs-lookup"><span data-stu-id="1acd7-305">Enable or disable custom ATP anti-phishing policies</span></span>

1. <span data-ttu-id="1acd7-306">En el centro de seguridad & cumplimiento, vaya a **Directiva** \> de **Administración** \> de amenazas **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-306">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="1acd7-307">Observe el valor de la columna **Estado** :</span><span class="sxs-lookup"><span data-stu-id="1acd7-307">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="1acd7-308">Deslice el botón de alternancia a **desactivado** para deshabilitar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="1acd7-308">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="1acd7-309">Deslice el botón de alternancia a **activado** para habilitar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="1acd7-309">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="1acd7-310">No se puede deshabilitar la Directiva antiphishing predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1acd7-310">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a><span data-ttu-id="1acd7-311">Establecer la prioridad de las directivas anti-phishing personalizadas de ATP</span><span class="sxs-lookup"><span data-stu-id="1acd7-311">Set the priority of custom ATP anti-phishing policies</span></span>

<span data-ttu-id="1acd7-312">De forma predeterminada, las directivas antiphishing de ATP reciben una prioridad que se basa en el orden en que se crearon (las directivas más recientes tienen una prioridad más baja que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="1acd7-312">By default, ATP anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="1acd7-313">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="1acd7-313">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="1acd7-314">Dos directivas no pueden tener la misma prioridad.</span><span class="sxs-lookup"><span data-stu-id="1acd7-314">No two policies can have the same priority.</span></span>

<span data-ttu-id="1acd7-315">Las directivas de antiphishing de ATP personalizadas se muestran en el orden en que se procesan (la primera Directiva tiene el valor de **prioridad** 0).</span><span class="sxs-lookup"><span data-stu-id="1acd7-315">Custom ATP anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="1acd7-316">La Directiva antiphishing predeterminada denominada Office365 ANTIPHISH predeterminada tiene el valor de prioridad personalizado **más bajo**y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="1acd7-316">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="1acd7-317">**Nota**: en el centro de seguridad & cumplimiento, solo puede cambiar la prioridad de la Directiva contra la suplantación de identidad (phishing) de ATP después de crearla.</span><span class="sxs-lookup"><span data-stu-id="1acd7-317">**Note**: In the Security & Compliance Center, you can only change the priority of the ATP anti-phishing policy after you create it.</span></span> <span data-ttu-id="1acd7-318">En PowerShell, puede invalidar la prioridad predeterminada al crear la regla antiphishing (que puede afectar a la prioridad de las reglas existentes).</span><span class="sxs-lookup"><span data-stu-id="1acd7-318">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="1acd7-319">Para cambiar la prioridad de una directiva, haga clic en **aumentar prioridad** o **disminuir prioridad** en las propiedades de la Directiva (no puede modificar directamente el número de **prioridad** en el centro de seguridad & cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="1acd7-319">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="1acd7-320">Cambiar la prioridad de una directiva solo tiene sentido si tiene varias directivas.</span><span class="sxs-lookup"><span data-stu-id="1acd7-320">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="1acd7-321">En el centro de seguridad & cumplimiento, vaya a **Directiva** \> de **Administración** \> de amenazas **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-321">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="1acd7-322">Seleccione la Directiva que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="1acd7-322">Select the policy that you want to modify.</span></span> <span data-ttu-id="1acd7-323">Si ya está seleccionada, anule la selección y vuelva a seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="1acd7-323">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="1acd7-324">Aparece el control flotante **editar el nombre \<\> de la Directiva** .</span><span class="sxs-lookup"><span data-stu-id="1acd7-324">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="1acd7-325">La Directiva antiphishing de ATP personalizada con el valor de **prioridad** **0** solo tiene el botón **disminuir prioridad** disponible.</span><span class="sxs-lookup"><span data-stu-id="1acd7-325">The custom ATP anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="1acd7-326">La Directiva antiphishing de ATP personalizada con el valor de **prioridad** más bajo (por ejemplo, **3**) solo tiene el botón **aumentar prioridad** disponible.</span><span class="sxs-lookup"><span data-stu-id="1acd7-326">The custom ATP anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="1acd7-327">Si tiene tres o más directivas de suplantación de identidad personalizadas, las directivas entre los valores de prioridad mayor y menor tienen los botones **aumentar prioridad** y **disminuir prioridad** disponibles.</span><span class="sxs-lookup"><span data-stu-id="1acd7-327">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="1acd7-328">Haga clic en **aumentar prioridad** o **disminuir prioridad** para cambiar el valor de **prioridad** .</span><span class="sxs-lookup"><span data-stu-id="1acd7-328">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="1acd7-329">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-329">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a><span data-ttu-id="1acd7-330">Usar el centro de seguridad & cumplimiento para ver las directivas de ATP antiphishing</span><span class="sxs-lookup"><span data-stu-id="1acd7-330">Use the Security & Compliance Center to view ATP anti-phishing policies</span></span>

1. <span data-ttu-id="1acd7-331">En el centro de seguridad & cumplimiento y vaya a la **Directiva** \> de **Administración** \> de amenazas de **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-331">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="1acd7-332">Realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1acd7-332">Do one of the following steps:</span></span>

   - <span data-ttu-id="1acd7-333">Seleccione una directiva antiphishing de ATP personalizada que quiera ver.</span><span class="sxs-lookup"><span data-stu-id="1acd7-333">Select a custom ATP anti-phishing policy that you want to view.</span></span> <span data-ttu-id="1acd7-334">Si ya está seleccionada, anule la selección y vuelva a seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="1acd7-334">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="1acd7-335">Haga clic en **directiva predeterminada** para ver la Directiva contra la suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1acd7-335">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="1acd7-336">Aparece el control flotante **editar el nombre \<\> de la Directiva** , donde puede ver la configuración y los valores.</span><span class="sxs-lookup"><span data-stu-id="1acd7-336">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a><span data-ttu-id="1acd7-337">Usar el centro de seguridad & cumplimiento para quitar las directivas antiphishing de ATP</span><span class="sxs-lookup"><span data-stu-id="1acd7-337">Use the Security & Compliance Center to remove ATP anti-phishing policies</span></span>

1. <span data-ttu-id="1acd7-338">En el centro de seguridad & cumplimiento, vaya a **Directiva** \> de **Administración** \> de amenazas **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-338">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="1acd7-339">Seleccione la Directiva que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="1acd7-339">Select the policy that you want to remove.</span></span> <span data-ttu-id="1acd7-340">Si ya está seleccionada, anule la selección y vuelva a seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="1acd7-340">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="1acd7-341">En el control flotante **Editar \<el\> nombre** de la Directiva que aparece, haga clic en **eliminar Directiva**y, a continuación, haga clic en **sí** en el cuadro de diálogo de advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="1acd7-341">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="1acd7-342">No puede quitar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1acd7-342">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a><span data-ttu-id="1acd7-343">Usar Exchange Online PowerShell para configurar las directivas antiphishing de ATP</span><span class="sxs-lookup"><span data-stu-id="1acd7-343">Use Exchange Online PowerShell to configure ATP anti-phishing policies</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="1acd7-344">Usar PowerShell para crear directivas antiphishing</span><span class="sxs-lookup"><span data-stu-id="1acd7-344">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="1acd7-345">La creación de una directiva contra la suplantación de identidad (phishing) en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="1acd7-345">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="1acd7-346">Cree la Directiva contra phish.</span><span class="sxs-lookup"><span data-stu-id="1acd7-346">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="1acd7-347">Cree la regla ANTIPHISH que especifica la Directiva antiphishing a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="1acd7-347">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="1acd7-348">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="1acd7-348">**Notes**:</span></span>

- <span data-ttu-id="1acd7-349">Puede crear una nueva regla antiphishing y asignarle una directiva ANTIPHISH existente no asociada.</span><span class="sxs-lookup"><span data-stu-id="1acd7-349">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="1acd7-350">Una regla antiphishing no puede asociarse con más de una directiva antiphishing.</span><span class="sxs-lookup"><span data-stu-id="1acd7-350">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="1acd7-351">Puede configurar las siguientes opciones en nuevas directivas antiphishing en PowerShell que no están disponibles en el centro de seguridad & cumplimiento hasta que se crea la Directiva:</span><span class="sxs-lookup"><span data-stu-id="1acd7-351">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="1acd7-352">Cree la nueva directiva como deshabilitada (_habilitada_ `$false` en el cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="1acd7-352">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="1acd7-353">Establezca la prioridad de la Directiva durante la creación ( _ \<número\>_ de_prioridad_ ) en el cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="1acd7-353">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="1acd7-354">Una nueva Directiva antiphishing que cree en PowerShell no es visible en el centro de seguridad & cumplimiento hasta que asigna la Directiva a una regla antiphishing.</span><span class="sxs-lookup"><span data-stu-id="1acd7-354">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="1acd7-355">Paso 1: usar PowerShell para crear una directiva ANTIPHISH</span><span class="sxs-lookup"><span data-stu-id="1acd7-355">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="1acd7-356">Para crear una directiva contra phish, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="1acd7-356">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="1acd7-357">En este ejemplo se crea una directiva contra phish denominada Research Quarantine con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="1acd7-357">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="1acd7-358">La Directiva está habilitada (no se usa el parámetro _Enabled_ y el valor predeterminado es `$true`).</span><span class="sxs-lookup"><span data-stu-id="1acd7-358">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="1acd7-359">La descripción es: Research Department Policy.</span><span class="sxs-lookup"><span data-stu-id="1acd7-359">The description is: Research department policy.</span></span>
- <span data-ttu-id="1acd7-360">Habilita la protección de dominios de organización para todos los dominios aceptados y la protección de dominios de destino para fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="1acd7-360">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="1acd7-361">Especifica el Mai Fuji (mfujito@fabrikam.com) como el usuario que se va a proteger de la suplantación.</span><span class="sxs-lookup"><span data-stu-id="1acd7-361">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="1acd7-362">Habilita la inteligencia de buzones.</span><span class="sxs-lookup"><span data-stu-id="1acd7-362">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="1acd7-363">Habilita la protección de inteligencia de buzones de correo y especifica la acción de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="1acd7-363">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="1acd7-364">Habilita las sugerencias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1acd7-364">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Default monitoring policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="1acd7-365">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="1acd7-365">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="1acd7-366">Paso 2: usar PowerShell para crear una regla contra el phish</span><span class="sxs-lookup"><span data-stu-id="1acd7-366">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="1acd7-367">Para crear una regla contra el phish, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="1acd7-367">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="1acd7-368">En este ejemplo se crea una regla ANTIPHISH denominada Research Department con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="1acd7-368">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="1acd7-369">La regla está asociada a la Directiva ANTIPHISH denominada Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="1acd7-369">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="1acd7-370">La regla se aplica a los miembros del grupo denominado Research Department.</span><span class="sxs-lookup"><span data-stu-id="1acd7-370">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="1acd7-371">Como no se usa el parámetro _Priority_ , se usa la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1acd7-371">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="1acd7-372">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="1acd7-372">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="1acd7-373">Usar PowerShell para ver las directivas ANTIPHISH</span><span class="sxs-lookup"><span data-stu-id="1acd7-373">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="1acd7-374">Para ver las directivas ANTIPHISH existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="1acd7-374">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="1acd7-375">En este ejemplo se devuelve una lista resumida de todas las directivas contra phish junto con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="1acd7-375">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="1acd7-376">En este ejemplo se devuelven todos los valores de propiedad de la Directiva ANTIPHISH denominada Executives.</span><span class="sxs-lookup"><span data-stu-id="1acd7-376">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="1acd7-377">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="1acd7-377">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="1acd7-378">Usar PowerShell para ver las reglas ANTIPHISH</span><span class="sxs-lookup"><span data-stu-id="1acd7-378">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="1acd7-379">Para ver las reglas ANTIPHISH existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="1acd7-379">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="1acd7-380">En este ejemplo se devuelve una lista resumida de todas las reglas antiphishing junto con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="1acd7-380">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="1acd7-381">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="1acd7-381">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="1acd7-382">En este ejemplo se devuelven todos los valores de propiedad de la regla antiphishing denominada ejecutivos de contoso.</span><span class="sxs-lookup"><span data-stu-id="1acd7-382">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="1acd7-383">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="1acd7-383">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="1acd7-384">Usar PowerShell para modificar las directivas ANTIPHISH</span><span class="sxs-lookup"><span data-stu-id="1acd7-384">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="1acd7-385">Aparte de los siguientes elementos, la misma configuración está disponible cuando se modifica una directiva ANTIPHISH en PowerShell como cuando se crea la Directiva tal como se describe en la sección [paso 1: usar PowerShell para crear una directiva ANTIPHISH](#step-1-use-powershell-to-create-an-anti-phish-policy) anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="1acd7-385">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="1acd7-386">El modificador _MakeDefault_ que convierte la Directiva especificada en la directiva predeterminada (aplicado a todos, siempre la prioridad **más baja** y no puede eliminarla) solo está disponible cuando se modifica una directiva ANTIPHISH en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1acd7-386">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="1acd7-387">No se puede cambiar el nombre de una directiva antiphishing (el cmdlet **set-AntiPhishPolicy** no tiene un parámetro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="1acd7-387">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="1acd7-388">Al cambiar el nombre de una directiva antiphishing en el centro de seguridad & cumplimiento, sólo cambia el nombre de la _regla_antiphishing.</span><span class="sxs-lookup"><span data-stu-id="1acd7-388">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="1acd7-389">Para modificar una directiva contra phish, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="1acd7-389">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="1acd7-390">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="1acd7-390">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="1acd7-391">Usar PowerShell para modificar reglas antiphishing</span><span class="sxs-lookup"><span data-stu-id="1acd7-391">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="1acd7-392">La única opción que no está disponible cuando se modifica una regla antiphishing en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="1acd7-392">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="1acd7-393">Para habilitar o deshabilitar las reglas de ANTIPHISH existentes, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="1acd7-393">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="1acd7-394">De lo contrario, no hay opciones de configuración adicionales disponibles cuando se modifica una regla antiphishing en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1acd7-394">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="1acd7-395">La misma configuración está disponible cuando se crea una regla tal y como se describe en la sección [paso 2: usar PowerShell para crear una regla ANTIPHISH](#step-2-use-powershell-to-create-an-anti-phish-rule) anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="1acd7-395">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="1acd7-396">Para modificar una regla antiphishing, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="1acd7-396">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="1acd7-397">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="1acd7-397">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="1acd7-398">Usar PowerShell para habilitar o deshabilitar reglas antiphishing</span><span class="sxs-lookup"><span data-stu-id="1acd7-398">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="1acd7-399">La habilitación o deshabilitación de una regla antiphishing en PowerShell habilita o deshabilita toda la Directiva antiphishing (la regla ANTIPHISH y la Directiva de ANTIPHISH asignada).</span><span class="sxs-lookup"><span data-stu-id="1acd7-399">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="1acd7-400">No se puede habilitar o deshabilitar la Directiva de suplantación de identidad (phishing) predeterminada (siempre se aplica a todos los destinatarios).</span><span class="sxs-lookup"><span data-stu-id="1acd7-400">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="1acd7-401">Para habilitar o deshabilitar una regla antiphishing en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="1acd7-401">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="1acd7-402">En este ejemplo se deshabilita la regla antiphishing denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="1acd7-402">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="1acd7-403">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="1acd7-403">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="1acd7-404">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/enable-AntiPhishrule) y [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/disable-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="1acd7-404">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="1acd7-405">Usar PowerShell para establecer la prioridad de las reglas antiphishing</span><span class="sxs-lookup"><span data-stu-id="1acd7-405">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="1acd7-406">El valor de prioridad máximo que se puede establecer en una regla es 0.</span><span class="sxs-lookup"><span data-stu-id="1acd7-406">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="1acd7-407">El valor mínimo que se puede establecer depende del número de reglas.</span><span class="sxs-lookup"><span data-stu-id="1acd7-407">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="1acd7-408">Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4.</span><span class="sxs-lookup"><span data-stu-id="1acd7-408">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="1acd7-409">El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas.</span><span class="sxs-lookup"><span data-stu-id="1acd7-409">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="1acd7-410">Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="1acd7-410">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="1acd7-411">Para establecer la prioridad de una regla anti-phish en PowerShell, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="1acd7-411">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="1acd7-412">Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2.</span><span class="sxs-lookup"><span data-stu-id="1acd7-412">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="1acd7-413">Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="1acd7-413">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="1acd7-414">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="1acd7-414">**Notes**:</span></span>

- <span data-ttu-id="1acd7-415">Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-AntiPhishRule** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="1acd7-415">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="1acd7-416">La Directiva ANTIPHISH predeterminada no tiene una regla ANTIPHISH correspondiente y siempre tiene el valor de prioridad no modificable **más bajo**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-416">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="1acd7-417">Usar PowerShell para quitar directivas antiphishing</span><span class="sxs-lookup"><span data-stu-id="1acd7-417">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="1acd7-418">Cuando se usa PowerShell para quitar una directiva antiphishing, no se elimina la regla antiphishing correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1acd7-418">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="1acd7-419">Para quitar una directiva ANTIPHISH en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="1acd7-419">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="1acd7-420">En este ejemplo se quita la Directiva antiphishing denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="1acd7-420">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="1acd7-421">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="1acd7-421">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="1acd7-422">Usar PowerShell para eliminar reglas antiphishing</span><span class="sxs-lookup"><span data-stu-id="1acd7-422">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="1acd7-423">Cuando se usa PowerShell para quitar una regla antiphishing, no se elimina la Directiva antiphishing correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1acd7-423">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="1acd7-424">Para quitar una regla contra el phish en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="1acd7-424">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="1acd7-425">En este ejemplo se quita la regla antiphishing denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="1acd7-425">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="1acd7-426">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="1acd7-426">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="1acd7-427">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="1acd7-427">How do you know these procedures worked?</span></span>

<span data-ttu-id="1acd7-428">Para comprobar que ha configurado correctamente las directivas antiphishing de ATP, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="1acd7-428">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="1acd7-429">En el centro de seguridad & cumplimiento, vaya a **Directiva** \> de **Administración** \> de amenazas **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="1acd7-429">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="1acd7-430">Compruebe la lista de directivas, sus valores de **Estado** y sus valores de **prioridad** .</span><span class="sxs-lookup"><span data-stu-id="1acd7-430">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="1acd7-431">Para ver más detalles, realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1acd7-431">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="1acd7-432">Seleccione la Directiva de la lista y vea los detalles en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="1acd7-432">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="1acd7-433">Haga clic en **directiva predeterminada** y vea los detalles en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="1acd7-433">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="1acd7-434">En Exchange Online PowerShell, reemplace \<name\> por el nombre de la Directiva o regla y ejecute el siguiente comando y Compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="1acd7-434">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```