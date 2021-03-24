---
title: 'Directivas de documentos seguros recomendadas: Microsoft 365 para empresas | Microsoft Docs'
description: Se explican las directivas recomendadas por Microsoft para proteger el acceso a archivos de SharePoint.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 1771f71e444233ffce60a4a56273d3062fe8b70d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072507"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a><span data-ttu-id="19e22-103">Recomendaciones de directiva para proteger archivos y sitios de SharePoint</span><span class="sxs-lookup"><span data-stu-id="19e22-103">Policy recommendations for securing SharePoint sites and files</span></span>

<span data-ttu-id="19e22-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="19e22-104">**Applies to**</span></span>
- [<span data-ttu-id="19e22-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="19e22-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="19e22-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="19e22-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- <span data-ttu-id="19e22-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="19e22-107">SharePoint Online</span></span> 


<span data-ttu-id="19e22-108">En este artículo se describe cómo implementar las directivas de identidad y acceso a dispositivos recomendadas para proteger SharePoint y OneDrive para la Empresa.</span><span class="sxs-lookup"><span data-stu-id="19e22-108">This article describes how to implement the recommended identity and device-access policies to protect SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="19e22-109">Esta guía se basa en las directivas [comunes de acceso a dispositivos y identidades.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="19e22-109">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="19e22-110">Estas recomendaciones se basan en tres niveles diferentes de seguridad y protección para archivos de SharePoint que se pueden aplicar en función de la granularidad de sus necesidades: **línea** **base,** confidencial y altamente **regulado.**</span><span class="sxs-lookup"><span data-stu-id="19e22-110">These recommendations are based on three different tiers of security and protection for SharePoint files that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="19e22-111">Puede obtener más información sobre estos niveles de seguridad y los sistemas operativos de cliente recomendados, a los que se hace referencia en estas recomendaciones [en la introducción](microsoft-365-policies-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="19e22-111">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in [the overview](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="19e22-112">Además de implementar esta guía, asegúrese de configurar los sitios de SharePoint con la cantidad de protección adecuada, incluida la configuración de permisos adecuados para contenido confidencial y altamente regulado.</span><span class="sxs-lookup"><span data-stu-id="19e22-112">In addition to implementing this guidance, be sure to configure SharePoint sites with the right amount of protection, including setting appropriate permissions for sensitive and highly-regulated content.</span></span>

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a><span data-ttu-id="19e22-113">Actualizar directivas comunes para incluir SharePoint y OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="19e22-113">Updating common policies to include SharePoint and OneDrive for Business</span></span>

<span data-ttu-id="19e22-114">Para proteger los archivos de SharePoint y OneDrive, en el siguiente diagrama se muestran las directivas que se actualizarán a partir de las directivas comunes de acceso a dispositivos y identidades.</span><span class="sxs-lookup"><span data-stu-id="19e22-114">To protect files in SharePoint and OneDrive, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="19e22-115">[![Resumen de las actualizaciones de directivas para proteger el acceso a Teams y sus servicios dependientes](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span><span class="sxs-lookup"><span data-stu-id="19e22-115">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span></span>

<span data-ttu-id="19e22-116">Si incluyó SharePoint al crear las directivas comunes, solo necesita crear las nuevas directivas.</span><span class="sxs-lookup"><span data-stu-id="19e22-116">If you included SharePoint when you created the common policies, you only need to create the new policies.</span></span> <span data-ttu-id="19e22-117">Para las directivas de acceso condicional, SharePoint incluye OneDrive.</span><span class="sxs-lookup"><span data-stu-id="19e22-117">For Conditional Access policies, SharePoint includes OneDrive.</span></span>

<span data-ttu-id="19e22-118">Las nuevas directivas implementan la protección de dispositivos para contenido confidencial y altamente regulado mediante la aplicación de requisitos de acceso específicos a los sitios de SharePoint que especifique.</span><span class="sxs-lookup"><span data-stu-id="19e22-118">The new policies implement device protection for sensitive and highly-regulated content by applying specific access requirements to SharePoint sites that you specify.</span></span>

<span data-ttu-id="19e22-119">En la tabla siguiente se enumeran las directivas que necesita revisar y actualizar o crear nuevas para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="19e22-119">The following table lists the policies you either need to review and update or create new for SharePoint.</span></span> <span data-ttu-id="19e22-120">Las directivas comunes se vinculan a las instrucciones de configuración asociadas en [el artículo Identidad común y directivas de acceso a dispositivos.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="19e22-120">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="19e22-121">Nivel de protección</span><span class="sxs-lookup"><span data-stu-id="19e22-121">Protection level</span></span>|<span data-ttu-id="19e22-122">Directivas</span><span class="sxs-lookup"><span data-stu-id="19e22-122">Policies</span></span>|<span data-ttu-id="19e22-123">Más información</span><span class="sxs-lookup"><span data-stu-id="19e22-123">More information</span></span>|
|---|---|---|
|<span data-ttu-id="19e22-124">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="19e22-124">**Baseline**</span></span>|[<span data-ttu-id="19e22-125">Requerir MFA cuando el riesgo de inicio de sesión *es medio* o *alto*</span><span class="sxs-lookup"><span data-stu-id="19e22-125">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="19e22-126">Incluir SharePoint en la asignación de aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="19e22-126">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="19e22-127">Bloquear a los clientes que no sean compatibles con la autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="19e22-127">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|<span data-ttu-id="19e22-128">Incluir SharePoint en la asignación de aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="19e22-128">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="19e22-129">Aplicar directivas de protección de datos de APP</span><span class="sxs-lookup"><span data-stu-id="19e22-129">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="19e22-130">Asegúrate de que todas las aplicaciones recomendadas estén incluidas en la lista de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="19e22-130">Be sure all recommended apps are included in the list of apps.</span></span> <span data-ttu-id="19e22-131">Asegúrate de actualizar la directiva para cada plataforma (iOS, Android, Windows).</span><span class="sxs-lookup"><span data-stu-id="19e22-131">Be sure to update the policy for each platform (iOS, Android, Windows).</span></span>|
||[<span data-ttu-id="19e22-132">Exigir equipos PC compatibles</span><span class="sxs-lookup"><span data-stu-id="19e22-132">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="19e22-133">Incluir SharePoint en la lista de aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="19e22-133">Include SharePoint in list of cloud apps.</span></span>|
||[<span data-ttu-id="19e22-134">Usar restricciones aplicadas por la aplicación en SharePoint</span><span class="sxs-lookup"><span data-stu-id="19e22-134">Use app enforced restrictions in SharePoint</span></span>](#use-app-enforced-restrictions-in-sharepoint)|<span data-ttu-id="19e22-135">Agregue esta nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="19e22-135">Add this new policy.</span></span> <span data-ttu-id="19e22-136">Esto indica a Azure Active Directory (Azure AD) que use la configuración especificada en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="19e22-136">This tells Azure Active Directory (Azure AD) to use the settings specified in SharePoint.</span></span> <span data-ttu-id="19e22-137">Esta directiva se aplica a todos los usuarios, pero solo afecta al acceso a los sitios incluidos en las directivas de acceso de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="19e22-137">This policy applies to all users, but only affects access to sites included in SharePoint access policies.</span></span>|
|<span data-ttu-id="19e22-138">**Confidencial**</span><span class="sxs-lookup"><span data-stu-id="19e22-138">**Sensitive**</span></span>|[<span data-ttu-id="19e22-139">Requerir MFA cuando el riesgo de inicio de sesión *es bajo,* *medio* o *alto*</span><span class="sxs-lookup"><span data-stu-id="19e22-139">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="19e22-140">Incluir SharePoint en las asignaciones de aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="19e22-140">Include SharePoint in the assignments of cloud apps.</span></span>|
||[<span data-ttu-id="19e22-141">Requerir equipos y *dispositivos* móviles compatibles</span><span class="sxs-lookup"><span data-stu-id="19e22-141">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="19e22-142">Incluir SharePoint en la lista de aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="19e22-142">Include SharePoint in the list of cloud apps.</span></span>|
||<span data-ttu-id="19e22-143">[Directiva de control de acceso de SharePoint:](#sharepoint-access-control-policies)permitir el acceso de solo explorador a sitios específicos de SharePoint desde dispositivos no administrados.</span><span class="sxs-lookup"><span data-stu-id="19e22-143">[SharePoint access control policy](#sharepoint-access-control-policies): Allow browser-only access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="19e22-144">Esto evita la edición y descarga de archivos.</span><span class="sxs-lookup"><span data-stu-id="19e22-144">This prevents edit and download of files.</span></span> <span data-ttu-id="19e22-145">Use PowerShell para especificar sitios.</span><span class="sxs-lookup"><span data-stu-id="19e22-145">Use PowerShell to specify sites.</span></span>|
|<span data-ttu-id="19e22-146">**Extremadamente regulado**</span><span class="sxs-lookup"><span data-stu-id="19e22-146">**Highly regulated**</span></span>|[<span data-ttu-id="19e22-147">*Requerir* siempre MFA</span><span class="sxs-lookup"><span data-stu-id="19e22-147">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="19e22-148">Incluir SharePoint en la asignación de aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="19e22-148">Include SharePoint in the assignment of cloud apps.</span></span>|
||<span data-ttu-id="19e22-149">[Directiva de control de acceso de SharePoint:](#use-app-enforced-restrictions-in-sharepoint)bloquear el acceso a sitios específicos de SharePoint desde dispositivos no administrados.</span><span class="sxs-lookup"><span data-stu-id="19e22-149">[SharePoint access control policy](#use-app-enforced-restrictions-in-sharepoint): Block access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="19e22-150">Use PowerShell para especificar sitios.</span><span class="sxs-lookup"><span data-stu-id="19e22-150">Use PowerShell to specify sites.</span></span>|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a><span data-ttu-id="19e22-151">Usar restricciones aplicadas por la aplicación en SharePoint</span><span class="sxs-lookup"><span data-stu-id="19e22-151">Use app-enforced restrictions in SharePoint</span></span>

<span data-ttu-id="19e22-152">Si implementa controles de acceso en SharePoint, debe crear esta directiva de acceso condicional en Azure AD para que le diga a Azure AD que aplique las directivas que configure en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="19e22-152">If you implement access controls in SharePoint, you must create this Conditional Access policy in Azure AD to tell Azure AD to enforce the policies you configure in SharePoint.</span></span> <span data-ttu-id="19e22-153">Esta directiva se aplica a todos los usuarios, pero solo afecta al acceso a los sitios que especifique con PowerShell al crear los controles de acceso en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="19e22-153">This policy applies to all users, but only affects access to the sites you specify using PowerShell when you create the access controls in SharePoint.</span></span>

<span data-ttu-id="19e22-154">Para configurar esta directiva, vea "Bloquear o limitar el acceso a determinadas colecciones de sitios de SharePoint o cuentas de OneDrive" en Control access [from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span><span class="sxs-lookup"><span data-stu-id="19e22-154">To configure this policy see "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="sharepoint-access-control-policies"></a><span data-ttu-id="19e22-155">Directivas de control de acceso de SharePoint</span><span class="sxs-lookup"><span data-stu-id="19e22-155">SharePoint access control policies</span></span>

<span data-ttu-id="19e22-156">Microsoft recomienda proteger el contenido de los sitios de SharePoint con contenido confidencial y altamente regulado con controles de acceso a dispositivos.</span><span class="sxs-lookup"><span data-stu-id="19e22-156">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="19e22-157">Para ello, cree una directiva que especifique el nivel de protección y los sitios a los que aplicar la protección.</span><span class="sxs-lookup"><span data-stu-id="19e22-157">You do this by creating a policy that specifies the level of protection and the sites to apply the protection to.</span></span>

- <span data-ttu-id="19e22-158">Sitios confidenciales: permitir el acceso solo del explorador.</span><span class="sxs-lookup"><span data-stu-id="19e22-158">Sensitive sites: Allow browser-only access.</span></span> <span data-ttu-id="19e22-159">Esto impide que los usuarios editen y descarguen archivos.</span><span class="sxs-lookup"><span data-stu-id="19e22-159">This prevents users from editing and downloading files.</span></span>
- <span data-ttu-id="19e22-160">Sitios altamente regulados: bloquear el acceso desde dispositivos no administrados.</span><span class="sxs-lookup"><span data-stu-id="19e22-160">Highly regulated sites: Block access from unmanaged devices.</span></span>

<span data-ttu-id="19e22-161">Vea "Bloquear o limitar el acceso a colecciones de sitios de SharePoint específicas o cuentas de OneDrive" en [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span><span class="sxs-lookup"><span data-stu-id="19e22-161">See "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="how-these-policies-work-together"></a><span data-ttu-id="19e22-162">Cómo funcionan conjuntamente estas directivas</span><span class="sxs-lookup"><span data-stu-id="19e22-162">How these policies work together</span></span>

<span data-ttu-id="19e22-163">Es importante comprender que los permisos de sitio de SharePoint suelen basarse en la necesidad empresarial de acceso a los sitios.</span><span class="sxs-lookup"><span data-stu-id="19e22-163">It's important to understand that SharePoint site permissions are typically based on business need for access to sites.</span></span> <span data-ttu-id="19e22-164">Estos permisos los administran los propietarios del sitio y pueden ser altamente dinámicos.</span><span class="sxs-lookup"><span data-stu-id="19e22-164">These permissions are managed by site owners and can be highly dynamic.</span></span> <span data-ttu-id="19e22-165">El uso de directivas de acceso a dispositivos de SharePoint garantiza la protección de estos sitios, independientemente de si los usuarios están asignados a un grupo de Azure AD asociado con la protección de línea base, confidencial o altamente regulada.</span><span class="sxs-lookup"><span data-stu-id="19e22-165">Using SharePoint device access policies ensures protection to these sites, regardless of whether users are assigned to an Azure AD group associated with baseline, sensitive, or highly regulated protection.</span></span>

<span data-ttu-id="19e22-166">En la siguiente ilustración se proporciona un ejemplo de cómo las directivas de acceso a dispositivos de SharePoint protegen el acceso a los sitios de un usuario.</span><span class="sxs-lookup"><span data-stu-id="19e22-166">The following illustration provides an example of how SharePoint device access policies protect access to sites for a user.</span></span>

<span data-ttu-id="19e22-167">[![Ejemplo de cómo las directivas de acceso a dispositivos de SharePoint protegen los sitios](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span><span class="sxs-lookup"><span data-stu-id="19e22-167">[![Example of how SharePoint device access policies protect sites](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span></span>

[<span data-ttu-id="19e22-168">Ver una versión más grande de esta imagen</span><span class="sxs-lookup"><span data-stu-id="19e22-168">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

<span data-ttu-id="19e22-169">James tiene asignadas directivas de acceso condicional de línea base, pero se le puede dar acceso a sitios de SharePoint con protección confidencial o altamente regulada.</span><span class="sxs-lookup"><span data-stu-id="19e22-169">James has baseline Conditional Access policies assigned, but he can be given access to SharePoint sites with sensitive or highly-regulated protection.</span></span>

- <span data-ttu-id="19e22-170">Si James tiene acceso a un sitio confidencial o altamente regulado, es miembro del uso de su equipo, su acceso se concede siempre que su EQUIPO cumpla con las normas.</span><span class="sxs-lookup"><span data-stu-id="19e22-170">If James accesses a sensitive or highly-regulated site he is a member of using his PC, his access is granted as long as his PC is compliant.</span></span>
- <span data-ttu-id="19e22-171">Si James tiene acceso a un sitio confidencial, es miembro del uso de su teléfono no administrado, que está permitido para los usuarios de línea base, recibirá acceso de solo explorador al sitio confidencial debido a la directiva de acceso de dispositivos configurada para este sitio.</span><span class="sxs-lookup"><span data-stu-id="19e22-171">If James accesses a sensitive site he is a member of using his unmanaged phone, which is allowed for baseline users, he will receive browser-only access to the sensitive site due to the device access policy configured for this site.</span></span>
- <span data-ttu-id="19e22-172">Si James tiene acceso a un sitio altamente regulado, es miembro del uso de su teléfono no administrado, se bloqueará debido a la directiva de acceso configurada para este sitio.</span><span class="sxs-lookup"><span data-stu-id="19e22-172">If James accesses a highly regulated site he is a member of using his unmanaged phone, he will be blocked due to the access policy configured for this site.</span></span> <span data-ttu-id="19e22-173">Solo puede acceder a este sitio con su equipo administrado y compatible.</span><span class="sxs-lookup"><span data-stu-id="19e22-173">He can only access this site using his managed and compliant PC.</span></span>

## <a name="next-step"></a><span data-ttu-id="19e22-174">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="19e22-174">Next step</span></span>

![Paso 4: Directivas para aplicaciones en la nube de Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="19e22-176">Configurar directivas de acceso condicional para:</span><span class="sxs-lookup"><span data-stu-id="19e22-176">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="19e22-177">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="19e22-177">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="19e22-178">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="19e22-178">Exchange Online</span></span>](secure-email-recommended-policies.md)