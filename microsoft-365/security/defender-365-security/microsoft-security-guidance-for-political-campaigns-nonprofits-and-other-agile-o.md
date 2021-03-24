---
title: 'Guía de seguridad de Microsoft: campañas políticas y ONG'
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MET150
ms.custom:
- Strat_O365_Enterprise
- seo-marvel-apr2020
ms.assetid: 10d1004b-42b6-4e2b-aaa2-18ddd9118f64
description: 'Resumen: instrucciones de planeamiento e implementación para organizaciones rápidas con un mayor perfil de amenaza.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac278103caf5d4d70b303b50b73db1b4b3571e6b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069971"
---
# <a name="microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-organizations"></a><span data-ttu-id="5f8a9-103">Guía de seguridad de Microsoft para campañas políticas, ONG y otras organizaciones ágiles</span><span class="sxs-lookup"><span data-stu-id="5f8a9-103">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5f8a9-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="5f8a9-104">**Applies to**</span></span>
- [<span data-ttu-id="5f8a9-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5f8a9-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5f8a9-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="5f8a9-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)

 <span data-ttu-id="5f8a9-107">**Resumen:** instrucciones de planeamiento e implementación para organizaciones rápidas con un mayor perfil de amenaza.</span><span class="sxs-lookup"><span data-stu-id="5f8a9-107">**Summary:** Planning and implementation guidance for fast-moving organizations that have an increased threat profile.</span></span>

<span data-ttu-id="5f8a9-p101">Si su organización es ágil, tiene un pequeño equipo de TI y el perfil de amenaza es superior a la media, estas instrucciones están diseñadas para usted. Esta solución muestra cómo compilar rápidamente un entorno con servicios de nube esenciales que incluyen controles seguros desde el principio. Estas instrucciones incluyen recomendaciones de seguridad prescriptivas para proteger los datos, las identidades, el correo electrónico y el acceso desde dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="5f8a9-p101">If your organization is agile, you have a small IT team, and your threat profile is higher than average, this guidance is designed for you. This solution demonstrates how to quickly build an environment with essential cloud services that include secure controls from the start. This guidance includes prescriptive security recommendations for protecting data, identities, email, and access from mobile devices.</span></span>

## <a name="security-solution-guidance"></a><span data-ttu-id="5f8a9-111">Instrucciones de solución de seguridad</span><span class="sxs-lookup"><span data-stu-id="5f8a9-111">Security solution guidance</span></span>

<span data-ttu-id="5f8a9-p102">Estas instrucciones explican cómo implementar un entorno de nube seguro. Las instrucciones de solución se pueden usar en cualquier organización. Incluyen ayuda adicional para organizaciones ágiles con cuentas de acceso BYOD e invitado. Puede usarlas como un punto de partida para diseñar un entorno propio. Agradecemos sus comentarios en [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="5f8a9-p102">This guidance describes how to implement a secure cloud environment. The solution guidance can be used by any organization. It includes extra help for agile organizations with BYOD access and guest accounts. You can use this guidance as a starting-point for designing your own environment. We welcome your feedback at [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span></span>

****

|<span data-ttu-id="5f8a9-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="5f8a9-117">Item</span></span>|<span data-ttu-id="5f8a9-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f8a9-118">Description</span></span>|
|---|---|
|<span data-ttu-id="5f8a9-119">**Guía de seguridad de Microsoft para campañas políticas**</span><span class="sxs-lookup"><span data-stu-id="5f8a9-119">**Microsoft Security Guidance for Political Campaigns**</span></span> <br> <span data-ttu-id="5f8a9-120">[![Miniatura de conjunto de minipósteres.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span><span class="sxs-lookup"><span data-stu-id="5f8a9-120">[![Thumbnail for mini poster set.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span></span> <br> <span data-ttu-id="5f8a9-121">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf) \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span><span class="sxs-lookup"><span data-stu-id="5f8a9-121">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf) \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span></span>|<span data-ttu-id="5f8a9-p103">En esta guía, se usa una organización de campaña política como ejemplo. Use esta guía como punto inicial para cualquier entorno.</span><span class="sxs-lookup"><span data-stu-id="5f8a9-p103">This guidance uses a political campaign organization as an example. Use this guidance as a starting point for any environment.</span></span>|
|<span data-ttu-id="5f8a9-124">**Guía de seguridad de Microsoft para ONG**</span><span class="sxs-lookup"><span data-stu-id="5f8a9-124">**Microsoft Security Guidance for Nonprofits**</span></span> <br> <span data-ttu-id="5f8a9-125">[![Imagen en miniatura de archivo descargable](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span><span class="sxs-lookup"><span data-stu-id="5f8a9-125">[![Thumbnail image for downloadable file](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span></span> <br> <span data-ttu-id="5f8a9-126">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf) \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span><span class="sxs-lookup"><span data-stu-id="5f8a9-126">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf) \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span></span>|<span data-ttu-id="5f8a9-p104">Estas Instrucciones se han modificado ligeramente para las organizaciones sin ánimo de lucro. Por ejemplo, hacen referencia a los planes sin ánimo de lucro de Office 365. Las instrucciones técnicas son las mismas que las de campaña política.</span><span class="sxs-lookup"><span data-stu-id="5f8a9-p104">This guide is slightly revised for nonprofit organizations. For example, it references Office 365 Nonprofit plans. The technical guidance is the same as the political campaign solution guide.</span></span>|
|

## <a name="test-lab-guides"></a><span data-ttu-id="5f8a9-130">Guías del entorno de pruebas</span><span class="sxs-lookup"><span data-stu-id="5f8a9-130">Test Lab Guides</span></span>

<span data-ttu-id="5f8a9-131">Para crear un entorno de desarrollo y pruebas para esta solución, siga estas guías del entorno de pruebas:</span><span class="sxs-lookup"><span data-stu-id="5f8a9-131">To create a dev/test environment for this solution, use the following test lab guides:</span></span>

- [<span data-ttu-id="5f8a9-132">Configurar grupos y usuarios en un entorno de desarrollo y pruebas de campaña política</span><span class="sxs-lookup"><span data-stu-id="5f8a9-132">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="5f8a9-133">Cree suscripciones de prueba para Office 365 y EMS y, después, cree grupos y usuarios para una campaña política de un representante.</span><span class="sxs-lookup"><span data-stu-id="5f8a9-133">Create trial subscriptions for Office 365 and EMS and then create groups and users for a representative political campaign.</span></span>

- [<span data-ttu-id="5f8a9-134">Crear sitios de grupo en un entorno de desarrollo y pruebas de campaña política</span><span class="sxs-lookup"><span data-stu-id="5f8a9-134">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="5f8a9-135">Cree cuatro sitios de grupo de SharePoint Online con niveles de seguridad “Interno”, “Privado”, “Confidencial” y “Altamente confidencial”.</span><span class="sxs-lookup"><span data-stu-id="5f8a9-135">Create four SharePoint Online team sites with Internal, Private, Sensitive, and Highly Confidential levels of security.</span></span>

<span data-ttu-id="5f8a9-136">Para obtener características de seguridad adicionales como demostración o prueba de concepto, vea [Guías del entorno de pruebas de Office 365](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md).</span><span class="sxs-lookup"><span data-stu-id="5f8a9-136">For additional security features for demonstration or proof of concept, see [Office 365 Test Lab Guides](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5f8a9-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f8a9-137">See Also</span></span>

[<span data-ttu-id="5f8a9-138">Recursos de arquitectura de TI de Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="5f8a9-138">Microsoft Cloud IT architecture resources</span></span>](../../solutions/cloud-architecture-models.md)