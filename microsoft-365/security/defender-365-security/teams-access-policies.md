---
title: 'Directivas recomendadas de Teams: Microsoft 365 para empresas | Microsoft Docs'
description: Describe las directivas para las recomendaciones de Microsoft sobre cómo proteger la comunicación de Teams y el acceso a archivos.
author: MicrosoftHeidi
manager: serdars
ms.prod: m365-security
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 09/30/2020
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 51dec80c541cd77a1d4813505d82429487e8381c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071123"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a><span data-ttu-id="3d8c0-103">Recomendaciones de directiva para proteger chats, grupos y archivos de Teams</span><span class="sxs-lookup"><span data-stu-id="3d8c0-103">Policy recommendations for securing Teams chats, groups, and files</span></span>

<span data-ttu-id="3d8c0-104">En este artículo se describe cómo implementar las directivas de identidad y acceso a dispositivos recomendadas para proteger los chats, grupos y contenido de Microsoft Teams, como archivos y calendarios.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-104">This article describes how to implement the recommended identity and device-access policies to protect Microsoft Teams chats, groups, and content such as files and calendars.</span></span> <span data-ttu-id="3d8c0-105">Esta guía se basa en [las](identity-access-policies.md)directivas comunes de acceso a dispositivos y identidades, con información adicional específica de Teams.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md), with additional information that's Teams-specific.</span></span> <span data-ttu-id="3d8c0-106">Dado que Teams se integra con nuestros otros productos, vea también Recomendaciones de directiva para proteger sitios y archivos de [SharePoint](sharepoint-file-access-policies.md) y Recomendaciones de directiva [para proteger el correo electrónico.](secure-email-recommended-policies.md)</span><span class="sxs-lookup"><span data-stu-id="3d8c0-106">Because Teams integrates with our other products, also see [Policy recommendations for securing SharePoint sites and files](sharepoint-file-access-policies.md) and [Policy recommendations for securing email](secure-email-recommended-policies.md).</span></span>

<span data-ttu-id="3d8c0-107">Estas recomendaciones se basan en tres niveles diferentes de seguridad y protección para Teams que se pueden aplicar en función de la granularidad de sus necesidades: línea base, confidencial y altamente regulado.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-107">These recommendations are based on three different tiers of security and protection for Teams that can be applied based on the granularity of your needs: baseline, sensitive, and highly regulated.</span></span> <span data-ttu-id="3d8c0-108">Puedes obtener más información sobre estos niveles de seguridad y las directivas recomendadas a las que hacen referencia estas recomendaciones en las configuraciones de acceso a [dispositivos](microsoft-365-policies-configurations.md)y identidades.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-108">You can learn more about these security tiers and the recommended policies referenced by these recommendations in the [Identity and device access configurations](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="3d8c0-109">En este artículo se incluyen más recomendaciones específicas para la implementación de Teams para cubrir circunstancias de autenticación específicas, incluidos los usuarios de fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-109">More recommendations specific to Teams deployment are included in this article to cover specific authentication circumstances, including for users outside your organization.</span></span> <span data-ttu-id="3d8c0-110">Deberá seguir estas instrucciones para obtener una experiencia de seguridad completa.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-110">You will need to follow this guidance for a complete security experience.</span></span>

## <a name="getting-started-with-teams-before-other-dependent-services"></a><span data-ttu-id="3d8c0-111">Introducción a Teams antes de otros servicios dependientes</span><span class="sxs-lookup"><span data-stu-id="3d8c0-111">Getting started with Teams before other dependent services</span></span>

<span data-ttu-id="3d8c0-112">No es necesario habilitar los servicios dependientes para empezar a trabajar con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-112">You don't need to enable dependent services to get started with Microsoft Teams.</span></span> <span data-ttu-id="3d8c0-113">Todos estos servicios "solo funcionarán".</span><span class="sxs-lookup"><span data-stu-id="3d8c0-113">These services will all "just work."</span></span> <span data-ttu-id="3d8c0-114">Sin embargo, debe estar preparado para administrar los siguientes elementos relacionados con el servicio:</span><span class="sxs-lookup"><span data-stu-id="3d8c0-114">However, you do need to be prepared to manage the following service-related elements:</span></span>

- <span data-ttu-id="3d8c0-115">Grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3d8c0-115">Microsoft 365 groups</span></span>
- <span data-ttu-id="3d8c0-116">Sitios de grupo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="3d8c0-116">SharePoint team sites</span></span>
- <span data-ttu-id="3d8c0-117">OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="3d8c0-117">OneDrive for Business</span></span>
- <span data-ttu-id="3d8c0-118">Buzones de Exchange</span><span class="sxs-lookup"><span data-stu-id="3d8c0-118">Exchange mailboxes</span></span>
- <span data-ttu-id="3d8c0-119">Transmitir vídeos y planes de Planner (si estos servicios están habilitados)</span><span class="sxs-lookup"><span data-stu-id="3d8c0-119">Stream videos and Planner plans (if these services are enabled)</span></span>

## <a name="updating-common-policies-to-include-teams"></a><span data-ttu-id="3d8c0-120">Actualización de directivas comunes para incluir Teams</span><span class="sxs-lookup"><span data-stu-id="3d8c0-120">Updating common policies to include Teams</span></span>

<span data-ttu-id="3d8c0-121">Para proteger el chat, los grupos y el contenido de Teams, en el siguiente diagrama se muestran las directivas que se actualizarán a partir de las directivas comunes de acceso a dispositivos y identidades.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-121">To protect chat, groups and content in Teams, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span> <span data-ttu-id="3d8c0-122">Para que cada directiva se actualice, asegúrese de que Teams y los servicios dependientes se incluyan en la asignación de aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-122">For each policy to update, make sure that Teams and dependent services are included in the assignment of cloud apps.</span></span>

<span data-ttu-id="3d8c0-123">[![Resumen de las actualizaciones de directivas para proteger el acceso a Teams y sus servicios dependientes](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)</span><span class="sxs-lookup"><span data-stu-id="3d8c0-123">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)</span></span>

<span data-ttu-id="3d8c0-124">Estos servicios son los servicios dependientes que se deben incluir en la asignación de aplicaciones en la nube para Teams:</span><span class="sxs-lookup"><span data-stu-id="3d8c0-124">These services are the dependent services to include in the assignment of cloud apps for Teams:</span></span>

- <span data-ttu-id="3d8c0-125">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3d8c0-125">Microsoft Teams</span></span>
- <span data-ttu-id="3d8c0-126">SharePoint y OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="3d8c0-126">SharePoint and OneDrive for Business</span></span>
- <span data-ttu-id="3d8c0-127">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3d8c0-127">Exchange Online</span></span>
- <span data-ttu-id="3d8c0-128">Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="3d8c0-128">Skype for Business Online</span></span>
- <span data-ttu-id="3d8c0-129">Microsoft Stream (grabaciones de reuniones)</span><span class="sxs-lookup"><span data-stu-id="3d8c0-129">Microsoft Stream (meeting recordings)</span></span>
- <span data-ttu-id="3d8c0-130">Microsoft Planner (tareas de Planner y datos del plan)</span><span class="sxs-lookup"><span data-stu-id="3d8c0-130">Microsoft Planner (Planner tasks and plan data)</span></span>

<span data-ttu-id="3d8c0-131">En esta tabla se enumeran las directivas que deben [](identity-access-policies.md)revisarse y los vínculos a cada directiva en las directivas comunes de identidad y acceso a dispositivos, que tiene el conjunto de directivas más amplio para todas las aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-131">This table lists the policies that need to be revisited and links to each policy in the [common identity and device access policies](identity-access-policies.md), which has the wider policy set for all Office applications.</span></span>

|<span data-ttu-id="3d8c0-132">Nivel de protección</span><span class="sxs-lookup"><span data-stu-id="3d8c0-132">Protection level</span></span>|<span data-ttu-id="3d8c0-133">Directivas</span><span class="sxs-lookup"><span data-stu-id="3d8c0-133">Policies</span></span>|<span data-ttu-id="3d8c0-134">Más información sobre la implementación de Teams</span><span class="sxs-lookup"><span data-stu-id="3d8c0-134">Further information for Teams implementation</span></span>|
|---|---|---|
|<span data-ttu-id="3d8c0-135">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="3d8c0-135">**Baseline**</span></span>|[<span data-ttu-id="3d8c0-136">Requerir MFA cuando el riesgo de inicio de sesión *es medio* o *alto*</span><span class="sxs-lookup"><span data-stu-id="3d8c0-136">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="3d8c0-137">Asegúrese de que Teams y los servicios dependientes se incluyen en la lista de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-137">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="3d8c0-138">Teams también tiene reglas de acceso de invitado y de acceso externo que debe tener en cuenta, más adelante encontrará más información sobre estas reglas en este artículo.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-138">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these rules later in this article.</span></span>|
||[<span data-ttu-id="3d8c0-139">Bloquear a los clientes que no sean compatibles con la autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="3d8c0-139">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|<span data-ttu-id="3d8c0-140">Incluya Teams y servicios dependientes en la asignación de aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-140">Include Teams and dependent services in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="3d8c0-141">Los usuarios de riesgo alto tienen que cambiar la contraseña</span><span class="sxs-lookup"><span data-stu-id="3d8c0-141">High risk users must change password</span></span>](identity-access-policies.md#high-risk-users-must-change-password)|<span data-ttu-id="3d8c0-142">Fuerza a los usuarios de Teams a cambiar su contraseña al iniciar sesión si se detecta actividad de alto riesgo para su cuenta.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-142">Forces Teams users to change their password when signing in if high-risk activity is detected for their account.</span></span> <span data-ttu-id="3d8c0-143">Asegúrese de que Teams y los servicios dependientes se incluyen en la lista de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-143">Be sure Teams and dependent services are included in the list of apps.</span></span>|
||[<span data-ttu-id="3d8c0-144">Aplicar directivas de protección de datos de APP</span><span class="sxs-lookup"><span data-stu-id="3d8c0-144">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="3d8c0-145">Asegúrese de que Teams y los servicios dependientes se incluyen en la lista de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-145">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="3d8c0-146">Actualiza la directiva para cada plataforma (iOS, Android, Windows).</span><span class="sxs-lookup"><span data-stu-id="3d8c0-146">Update the policy for each platform (iOS, Android, Windows).</span></span>|
||[<span data-ttu-id="3d8c0-147">Definir directivas de cumplimiento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="3d8c0-147">Define device compliance policies</span></span>](identity-access-policies.md#define-device-compliance-policies)|<span data-ttu-id="3d8c0-148">Incluya Teams y servicios dependientes en esta directiva.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-148">Include Teams and dependent services in this policy.</span></span>|
||[<span data-ttu-id="3d8c0-149">Exigir equipos PC compatibles</span><span class="sxs-lookup"><span data-stu-id="3d8c0-149">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="3d8c0-150">Incluya Teams y servicios dependientes en esta directiva.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-150">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="3d8c0-151">**Confidencial**</span><span class="sxs-lookup"><span data-stu-id="3d8c0-151">**Sensitive**</span></span>|[<span data-ttu-id="3d8c0-152">Requerir MFA cuando el riesgo de inicio de sesión *es bajo,* *medio* o *alto*</span><span class="sxs-lookup"><span data-stu-id="3d8c0-152">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="3d8c0-153">Teams también tiene reglas de acceso de invitado y de acceso externo que debe tener en cuenta, más adelante encontrará más información sobre estas reglas en este artículo.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-153">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these rules later in this article.</span></span> <span data-ttu-id="3d8c0-154">Incluya Teams y servicios dependientes en esta directiva.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-154">Include Teams and dependent services in this policy.</span></span>|
||[<span data-ttu-id="3d8c0-155">Requerir equipos y *dispositivos* móviles compatibles</span><span class="sxs-lookup"><span data-stu-id="3d8c0-155">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="3d8c0-156">Incluya Teams y servicios dependientes en esta directiva.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-156">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="3d8c0-157">**Extremadamente regulado**</span><span class="sxs-lookup"><span data-stu-id="3d8c0-157">**Highly regulated**</span></span>|[<span data-ttu-id="3d8c0-158">*Requerir* siempre MFA</span><span class="sxs-lookup"><span data-stu-id="3d8c0-158">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="3d8c0-159">Independientemente de la identidad de usuario, su organización usará MFA.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-159">Regardless of user identity, MFA will be used by your organization.</span></span> <span data-ttu-id="3d8c0-160">Incluya Teams y servicios dependientes en esta directiva.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-160">Include Teams and dependent services in this policy.</span></span> |
|

## <a name="teams-dependent-services-architecture"></a><span data-ttu-id="3d8c0-161">Arquitectura de servicios dependientes de Teams</span><span class="sxs-lookup"><span data-stu-id="3d8c0-161">Teams dependent services architecture</span></span>

<span data-ttu-id="3d8c0-162">Como referencia, el siguiente diagrama ilustra los servicios en los que se basa Teams.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-162">For reference, the following diagram illustrates the services Teams relies on.</span></span> <span data-ttu-id="3d8c0-163">Para obtener más información e ilustraciones, vea Microsoft Teams y los servicios de productividad relacionados en [Microsoft 365 para arquitectos de TI.](../../solutions/productivity-illustrations.md)</span><span class="sxs-lookup"><span data-stu-id="3d8c0-163">For more information and illustrations, see [Microsoft Teams and related productivity services in Microsoft 365 for IT architects](../../solutions/productivity-illustrations.md).</span></span>

<span data-ttu-id="3d8c0-164">[![Diagrama que muestra las dependencias de Teams en SharePoint, OneDrive para la Empresa y Exchange](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)</span><span class="sxs-lookup"><span data-stu-id="3d8c0-164">[![Diagram showing Teams dependencies on SharePoint, OneDrive for Business, and Exchange](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)</span></span>

[<span data-ttu-id="3d8c0-165">Ver una versión más grande de esta imagen</span><span class="sxs-lookup"><span data-stu-id="3d8c0-165">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a><span data-ttu-id="3d8c0-166">Acceso externo y invitado para Teams</span><span class="sxs-lookup"><span data-stu-id="3d8c0-166">Guest and external access for Teams</span></span>

<span data-ttu-id="3d8c0-167">Microsoft Teams define los siguientes tipos de acceso:</span><span class="sxs-lookup"><span data-stu-id="3d8c0-167">Microsoft Teams defines the following access types:</span></span>

- <span data-ttu-id="3d8c0-168">**El acceso** de invitado usa una cuenta B2B de Azure AD para un usuario invitado o externo que se puede agregar como miembro de un equipo y tener acceso con permiso a la comunicación y los recursos del equipo.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-168">**Guest access** uses an Azure AD B2B account for a guest or external user that can be added as a member of a team and have all permissioned access to the communication and resources of the team.</span></span>

- <span data-ttu-id="3d8c0-169">**El acceso** externo es para un usuario externo que no tiene una cuenta B2B de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-169">**External access** is for an external user that does not have an Azure AD B2B account.</span></span> <span data-ttu-id="3d8c0-170">El acceso externo puede incluir invitaciones y participación en llamadas, chats y reuniones, pero no incluye la pertenencia al equipo ni el acceso a los recursos del equipo.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-170">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="3d8c0-171">Las directivas de acceso condicional solo se aplican al acceso de invitado en Teams porque hay una cuenta B2B de Azure AD correspondiente.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-171">Conditional Access policies only apply to guest access in Teams because there is a corresponding Azure AD B2B account.</span></span>

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

<span data-ttu-id="3d8c0-172">Para ver las directivas recomendadas para permitir el acceso a usuarios invitados y externos con una cuenta B2B de Azure AD, consulte [Policies for allowing guest and external B2B account access](identity-access-policies-guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="3d8c0-172">For recommended policies to allow access for guest and external users with an Azure AD B2B account, see [Policies for allowing guest and external B2B account access](identity-access-policies-guest-access.md).</span></span>

### <a name="guest-access-in-teams"></a><span data-ttu-id="3d8c0-173">Acceso de invitado a Teams</span><span class="sxs-lookup"><span data-stu-id="3d8c0-173">Guest access in Teams</span></span>

<span data-ttu-id="3d8c0-174">Además de las directivas para los usuarios internos de su empresa u organización, los administradores pueden habilitar el acceso de invitado para permitir que, de forma individual, las personas externas a su empresa u organización puedan acceder a los recursos de Teams e interactuar con personas internas para cosas como conversaciones de grupo, chat y reuniones.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-174">In addition to the policies for users who are internal to your business or organization, administrators may enable guest access to allow, on a user-by-user basis, people who are external to your business or organization to access Teams resources and interact with internal people for things like group conversations, chat, and meetings.</span></span>

<span data-ttu-id="3d8c0-175">Para obtener más información sobre el acceso de invitados y cómo implementarlo, vea  [Acceso de invitado de Teams](/microsoftteams/guest-access).</span><span class="sxs-lookup"><span data-stu-id="3d8c0-175">For more information about guest access and how to implement it, see  [Teams guest access](/microsoftteams/guest-access).</span></span>

### <a name="external-access-in-teams"></a><span data-ttu-id="3d8c0-176">Acceso externo en Teams</span><span class="sxs-lookup"><span data-stu-id="3d8c0-176">External access in Teams</span></span>

<span data-ttu-id="3d8c0-177">El acceso externo a veces se confunde con el acceso de invitado, por lo que es importante tener claro que estos dos mecanismos de acceso no internos son diferentes tipos de acceso.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-177">External access is sometimes confused with guest access, so it's important to be clear that these two non-internal access mechanisms are different types of access.</span></span>

<span data-ttu-id="3d8c0-178">El acceso externo es una forma de que los usuarios de Teams de un dominio externo completo puedan buscar, llamar, chatear y configurar reuniones con los usuarios de Teams.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-178">External access is a way for Teams users from an entire external domain to find, call, chat, and set up meetings with your users in Teams.</span></span> <span data-ttu-id="3d8c0-179">Los administradores de Teams configuran el acceso externo en el nivel de la organización.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-179">Teams administrators configure external access at the organization level.</span></span> <span data-ttu-id="3d8c0-180">Para obtener más información, vea [Manage external access in Microsoft Teams](/microsoftteams/manage-external-access).</span><span class="sxs-lookup"><span data-stu-id="3d8c0-180">For more information, see [Manage external access in Microsoft Teams](/microsoftteams/manage-external-access).</span></span>

<span data-ttu-id="3d8c0-181">Los usuarios de acceso externo tienen menos acceso y funcionalidad que una persona que se ha agregado a través del acceso de invitado.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-181">External access users have less access and functionality than an individual who's been added via guest access.</span></span> <span data-ttu-id="3d8c0-182">Por ejemplo, los usuarios de acceso externo pueden chatear con los usuarios internos con Teams, pero no pueden acceder a canales de equipo, archivos u otros recursos.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-182">For example, external access users can chat with your internal users with Teams but cannot access team channels, files, or other resources.</span></span>

<span data-ttu-id="3d8c0-183">El acceso externo no usa cuentas de usuario B2B de Azure AD y, por lo tanto, no usa directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-183">External access does not use Azure AD B2B user accounts and therefore does not use Conditional Access policies.</span></span>

## <a name="teams-policies"></a><span data-ttu-id="3d8c0-184">Directivas de Teams</span><span class="sxs-lookup"><span data-stu-id="3d8c0-184">Teams policies</span></span>

<span data-ttu-id="3d8c0-185">Fuera de las directivas comunes enumeradas anteriormente, hay directivas específicas de Teams que pueden y deben configurarse para administrar diversas funcionalidades de Teams.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-185">Outside of the common policies listed above, there are Teams-specific policies that can and should be configured to manage various Teams functionalities.</span></span>

### <a name="teams-and-channels-policies"></a><span data-ttu-id="3d8c0-186">Directivas de teams y canales</span><span class="sxs-lookup"><span data-stu-id="3d8c0-186">Teams and channels policies</span></span>

<span data-ttu-id="3d8c0-187">Teams y canales son dos elementos que se usan con frecuencia en Microsoft Teams y hay directivas que puede establecer para controlar lo que los usuarios pueden y no pueden hacer al usar equipos y canales.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-187">Teams and channels are two commonly used elements in Microsoft Teams, and there are policies you can put in place to control what users can and cannot do when using teams and channels.</span></span> <span data-ttu-id="3d8c0-188">Aunque puede crear un equipo global, si su organización tiene 5000 usuarios o menos, es probable que le sea útil tener equipos y canales más pequeños para fines específicos, en línea con las necesidades de la organización.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-188">While you can create a global team, if your organization has 5000 users or less, you are likely to find it helpful to have smaller teams and channels for specific purposes, in-line with your organizational needs.</span></span>

<span data-ttu-id="3d8c0-189">Se recomienda cambiar la directiva predeterminada o crear directivas personalizadas y puede obtener más información sobre cómo administrar las directivas en este vínculo: Administrar directivas de equipos [en Microsoft Teams](/microsoftteams/teams-policies).</span><span class="sxs-lookup"><span data-stu-id="3d8c0-189">Changing the default policy or creating custom policies would be recommended, and you can learn more about managing your policies at this link: [Manage teams policies in Microsoft Teams](/microsoftteams/teams-policies).</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="3d8c0-190">Directivas de mensajería</span><span class="sxs-lookup"><span data-stu-id="3d8c0-190">Messaging policies</span></span>

<span data-ttu-id="3d8c0-191">La mensajería o el chat también se pueden administrar a través de la directiva global predeterminada o a través de directivas personalizadas, lo que puede ayudar a los usuarios a comunicarse entre sí de una forma adecuada para su organización.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-191">Messaging, or chat, can also be managed through the default global policy, or through custom policies, and this can help your users communicate with one another in a way that's appropriate for your organization.</span></span> <span data-ttu-id="3d8c0-192">Esta información se puede revisar en [Managing messaging policies in Teams](/microsoftteams/messaging-policies-in-teams).</span><span class="sxs-lookup"><span data-stu-id="3d8c0-192">This information can be reviewed at [Managing messaging policies in Teams](/microsoftteams/messaging-policies-in-teams).</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="3d8c0-193">Directivas de reunión</span><span class="sxs-lookup"><span data-stu-id="3d8c0-193">Meeting policies</span></span>

<span data-ttu-id="3d8c0-194">No se completaría ninguna discusión sobre Teams sin planear e implementar directivas en torno a las reuniones de Teams.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-194">No discussion of Teams would be complete without planning and implementing policies around Teams meetings.</span></span> <span data-ttu-id="3d8c0-195">Las reuniones son un componente esencial de Teams, que permite a los usuarios reunirse y presentarse formalmente a muchos usuarios a la vez y compartir contenido relevante para la reunión.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-195">Meetings are an essential component of Teams, allowing people to formally meet and present to many users at once, and to share content relevant to the meeting.</span></span> <span data-ttu-id="3d8c0-196">Es esencial establecer las directivas adecuadas para su organización en torno a las reuniones.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-196">Setting the right policies for your organization around meetings is essential.</span></span>

<span data-ttu-id="3d8c0-197">Para obtener más información, consulte [Administrar directivas de reunión en Teams](/microsoftteams/meeting-policies-in-teams).</span><span class="sxs-lookup"><span data-stu-id="3d8c0-197">For more information, review [Manage meeting policies in Teams](/microsoftteams/meeting-policies-in-teams).</span></span>

### <a name="app-permission-policies"></a><span data-ttu-id="3d8c0-198">Directivas de permisos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3d8c0-198">App permission policies</span></span>

<span data-ttu-id="3d8c0-199">Teams también te permite usar aplicaciones en varios lugares, como canales o chats personales.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-199">Teams also allows you to use apps in various places, such as channels or personal chats.</span></span> <span data-ttu-id="3d8c0-200">Tener directivas en torno a qué aplicaciones se pueden agregar y usar, y dónde, es esencial para mantener un entorno rico en contenido que también sea seguro.</span><span class="sxs-lookup"><span data-stu-id="3d8c0-200">Having policies around what apps can be added and used, and where, is essential to maintaining a content-rich environment that is also secure.</span></span>

<span data-ttu-id="3d8c0-201">Para obtener más información acerca de las directivas de permisos de aplicaciones, consulte [Administrar directivas de permisos de aplicaciones en Microsoft Teams](/microsoftteams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="3d8c0-201">For more reading about App Permission Policies, check out [Manage app permission policies in Microsoft Teams](/microsoftteams/teams-app-permission-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="3d8c0-202">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3d8c0-202">Next steps</span></span>

![Paso 4: Directivas para aplicaciones en la nube de Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="3d8c0-204">Configurar directivas de acceso condicional para:</span><span class="sxs-lookup"><span data-stu-id="3d8c0-204">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="3d8c0-205">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3d8c0-205">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="3d8c0-206">SharePoint</span><span class="sxs-lookup"><span data-stu-id="3d8c0-206">SharePoint</span></span>](sharepoint-file-access-policies.md)