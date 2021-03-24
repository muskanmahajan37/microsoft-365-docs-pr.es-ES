---
title: Solucionar cuentas de usuario comprometidas con investigación y respuesta automatizadas
keywords: AIR, autoIR, ATP, automated, investigation, response, remediation, threats, advanced, threat, protection, compromised
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Obtenga información sobre cómo acelerar el proceso de detección y tratamiento de cuentas de usuario comprometidas con capacidades automatizadas de investigación y respuesta en Microsoft Defender para Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2428cc2c1f82b4f2b881433fde991dd04b268d6e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073712"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="05a22-104">Solucionar cuentas de usuario comprometidas con investigación y respuesta automatizadas</span><span class="sxs-lookup"><span data-stu-id="05a22-104">Address compromised user accounts with automated investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="05a22-105">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="05a22-105">**Applies to**</span></span>
- [<span data-ttu-id="05a22-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="05a22-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="05a22-107">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="05a22-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="05a22-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="05a22-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)


<span data-ttu-id="05a22-109">[El Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) incluye potentes capacidades de investigación y respuesta [automatizadas](office-365-air.md) (AIR).</span><span class="sxs-lookup"><span data-stu-id="05a22-109">[Microsoft Defender for Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="05a22-110">Estas capacidades pueden ahorrarle mucho tiempo y esfuerzo al equipo de operaciones de seguridad que se ocupa de las amenazas.</span><span class="sxs-lookup"><span data-stu-id="05a22-110">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="05a22-111">Microsoft sigue mejorando las capacidades de seguridad.</span><span class="sxs-lookup"><span data-stu-id="05a22-111">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="05a22-112">Recientemente, las capacidades de AIR se han mejorado para incluir un libro de juegos de seguridad de usuario en peligro (actualmente en versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="05a22-112">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="05a22-113">Lea este artículo para obtener más información sobre el libro de juegos de seguridad del usuario en peligro.</span><span class="sxs-lookup"><span data-stu-id="05a22-113">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="05a22-114">Vea la entrada de blog Acelerar el tiempo para detectar y responder a los compromisos del usuario y limitar el ámbito de infracción con [Microsoft Defender para Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="05a22-114">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![Investigación automatizada para un usuario en peligro](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="05a22-116">El libro de juegos de seguridad de usuario comprometido permite al equipo de seguridad de la organización:</span><span class="sxs-lookup"><span data-stu-id="05a22-116">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="05a22-117">Acelerar la detección de cuentas de usuario comprometidas;</span><span class="sxs-lookup"><span data-stu-id="05a22-117">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="05a22-118">Limitar el ámbito de una infracción cuando una cuenta está en peligro; y</span><span class="sxs-lookup"><span data-stu-id="05a22-118">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="05a22-119">Responda a los usuarios en peligro de forma más eficaz y eficaz.</span><span class="sxs-lookup"><span data-stu-id="05a22-119">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="05a22-120">Alertas de usuario comprometidas</span><span class="sxs-lookup"><span data-stu-id="05a22-120">Compromised user alerts</span></span>

<span data-ttu-id="05a22-121">Cuando una cuenta de usuario está en peligro, se producen comportamientos atípicos o anómalos.</span><span class="sxs-lookup"><span data-stu-id="05a22-121">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="05a22-122">Por ejemplo, los mensajes de suplantación de identidad y correo no deseado pueden enviarse internamente desde una cuenta de usuario de confianza.</span><span class="sxs-lookup"><span data-stu-id="05a22-122">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="05a22-123">Defender para Office 365 puede detectar estas anomalías en los patrones de correo electrónico y la actividad de colaboración dentro de Office 365.</span><span class="sxs-lookup"><span data-stu-id="05a22-123">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="05a22-124">Cuando esto sucede, se desencadenan alertas y comienza el proceso de mitigación de amenazas.</span><span class="sxs-lookup"><span data-stu-id="05a22-124">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="05a22-125">Por ejemplo, esta es una alerta que se desencadenó debido al envío de correo electrónico sospechoso:</span><span class="sxs-lookup"><span data-stu-id="05a22-125">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![Alerta activada debido al envío de correo electrónico sospechoso](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="05a22-127">Y este es un ejemplo de una alerta que se desencadenó cuando se alcanzó un límite de envío para un usuario:</span><span class="sxs-lookup"><span data-stu-id="05a22-127">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![Alerta desencadenada por el límite de envío alcanzado](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="05a22-129">Investigar y responder a un usuario en peligro</span><span class="sxs-lookup"><span data-stu-id="05a22-129">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="05a22-130">Cuando una cuenta de usuario está en peligro, se desencadenan alertas.</span><span class="sxs-lookup"><span data-stu-id="05a22-130">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="05a22-131">Y en algunos casos, esa cuenta de usuario se bloquea e impide enviar más mensajes de correo electrónico hasta que el equipo de operaciones de seguridad de la organización resuelva el problema.</span><span class="sxs-lookup"><span data-stu-id="05a22-131">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="05a22-132">En otros casos, comienza una investigación automatizada que puede dar como resultado acciones recomendadas que el equipo de seguridad debe llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="05a22-132">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="05a22-133">Ver e investigar usuarios restringidos</span><span class="sxs-lookup"><span data-stu-id="05a22-133">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="05a22-134">Ver detalles sobre las investigaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="05a22-134">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="05a22-135">Debe tener los permisos adecuados para realizar las siguientes tareas.</span><span class="sxs-lookup"><span data-stu-id="05a22-135">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="05a22-136">Consulte [Permisos necesarios para usar las funcionalidades de AIR.](office-365-air.md#required-permissions-to-use-air-capabilities)</span><span class="sxs-lookup"><span data-stu-id="05a22-136">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="05a22-137">Ver e investigar usuarios restringidos</span><span class="sxs-lookup"><span data-stu-id="05a22-137">View and investigate restricted users</span></span>

<span data-ttu-id="05a22-138">Tiene algunas opciones para navegar a una lista de usuarios restringidos.</span><span class="sxs-lookup"><span data-stu-id="05a22-138">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="05a22-139">Por ejemplo, en el Centro de seguridad & cumplimiento, puede ir a **Administración** de amenazas \> **Revisar** \> **usuarios restringidos**.</span><span class="sxs-lookup"><span data-stu-id="05a22-139">For example, in the Security & Compliance Center, you can go to **Threat management** \> **Review** \> **Restricted Users**.</span></span> <span data-ttu-id="05a22-140">En el siguiente procedimiento se describe la navegación mediante el panel **de** alertas, que es una buena manera de ver varios tipos de alertas que podrían haber sido desencadenadas.</span><span class="sxs-lookup"><span data-stu-id="05a22-140">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="05a22-141">Vaya a <https://protection.office.com> e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="05a22-141">Go to <https://protection.office.com> and sign in.</span></span>

2. <span data-ttu-id="05a22-142">En el panel de navegación, elija **Panel de** \> **alertas**.</span><span class="sxs-lookup"><span data-stu-id="05a22-142">In the navigation pane, choose **Alerts** \> **Dashboard**.</span></span>

3. <span data-ttu-id="05a22-143">En el **widget Otras alertas,** elija **Usuarios restringidos**.</span><span class="sxs-lookup"><span data-stu-id="05a22-143">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![Widget Otras alertas](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="05a22-145">Esto abre la lista de usuarios restringidos.</span><span class="sxs-lookup"><span data-stu-id="05a22-145">This opens the list of restricted users.</span></span>

   ![Usuarios restringidos en Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="05a22-147">Seleccione una cuenta de usuario en la lista para ver detalles y tomar medidas, como liberar [el usuario restringido](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="05a22-147">Select a user account in the list to view details and take action, such as [releasing the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="05a22-148">Ver detalles sobre las investigaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="05a22-148">View details about automated investigations</span></span>

<span data-ttu-id="05a22-149">Cuando se inicia una investigación automatizada, puede ver sus detalles y resultados en el Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="05a22-149">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="05a22-150">Vaya  a \> **Investigaciones de administración de** amenazas y, a continuación, seleccione una investigación para ver sus detalles.</span><span class="sxs-lookup"><span data-stu-id="05a22-150">Go to **Threat management** \> **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="05a22-151">Para obtener más información, [vea Ver detalles de una investigación](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="05a22-151">To learn more, see [View details of an investigation](air-view-investigation-results.md).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="05a22-152">Tenga en cuenta los siguientes puntos</span><span class="sxs-lookup"><span data-stu-id="05a22-152">Keep the following points in mind</span></span>

- <span data-ttu-id="05a22-153">**Mantenerse al tanto de las alertas**.</span><span class="sxs-lookup"><span data-stu-id="05a22-153">**Stay on top of your alerts**.</span></span> <span data-ttu-id="05a22-154">Como sabe, cuanto más tiempo no se detecte un compromiso, mayor será el potencial de impacto y costo generalizado para su organización, clientes y socios.</span><span class="sxs-lookup"><span data-stu-id="05a22-154">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="05a22-155">La detección temprana y la respuesta oportuna son fundamentales para mitigar las amenazas, especialmente cuando la cuenta de un usuario está en peligro.</span><span class="sxs-lookup"><span data-stu-id="05a22-155">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="05a22-156">**La automatización ayuda, pero no reemplaza, al equipo de operaciones de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="05a22-156">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="05a22-157">Las capacidades automatizadas de investigación y respuesta pueden detectar un usuario en peligro desde el principio, pero es probable que el equipo de operaciones de seguridad necesite participar y realizar alguna investigación y corrección.</span><span class="sxs-lookup"><span data-stu-id="05a22-157">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="05a22-158">¿Necesita ayuda con esto?</span><span class="sxs-lookup"><span data-stu-id="05a22-158">Need some help with this?</span></span> <span data-ttu-id="05a22-159">Vea [Revisar y aprobar acciones](air-review-approve-pending-completed-actions.md).</span><span class="sxs-lookup"><span data-stu-id="05a22-159">See [Review and approve actions](air-review-approve-pending-completed-actions.md).</span></span>

- <span data-ttu-id="05a22-160">**No confíe en una alerta de inicio de sesión sospechosa como su único indicador**.</span><span class="sxs-lookup"><span data-stu-id="05a22-160">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="05a22-161">Cuando una cuenta de usuario está en peligro, es posible que desencadene o no una alerta de inicio de sesión sospechosa.</span><span class="sxs-lookup"><span data-stu-id="05a22-161">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="05a22-162">A veces es la serie de actividades que se producen después de que se pone en peligro una cuenta que desencadena una alerta.</span><span class="sxs-lookup"><span data-stu-id="05a22-162">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="05a22-163">¿Desea obtener más información sobre las alertas?</span><span class="sxs-lookup"><span data-stu-id="05a22-163">Want to know more about alerts?</span></span> <span data-ttu-id="05a22-164">Vea [Directivas de alerta](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="05a22-164">See [Alert policies](../../compliance/alert-policies.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="05a22-165">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="05a22-165">Next steps</span></span>

- [<span data-ttu-id="05a22-166">Revisar los permisos necesarios para usar las funcionalidades de AIR</span><span class="sxs-lookup"><span data-stu-id="05a22-166">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="05a22-167">Buscar e investigar correo electrónico malintencionado en Office 365</span><span class="sxs-lookup"><span data-stu-id="05a22-167">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="05a22-168">Obtenga información sobre AIR en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="05a22-168">Learn about AIR in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="05a22-169">Visite la guía básica de Microsoft 365 para ver lo que se está implementando próximamente</span><span class="sxs-lookup"><span data-stu-id="05a22-169">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)