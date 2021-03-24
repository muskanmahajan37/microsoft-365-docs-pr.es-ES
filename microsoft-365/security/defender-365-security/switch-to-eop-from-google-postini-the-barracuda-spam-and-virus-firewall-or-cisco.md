---
title: Cambiar a EOP desde otro servicio de protección
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
ms.custom:
- seo-marvel-apr2020
description: En este artículo, aprenderá a cambiar a Exchange Online Protection (EOP) desde un dispositivo de higiene de correo electrónico local o un servicio de protección basado en la nube.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e1a5df0b11c258ebe633868bb5abca5b20552a33
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071195"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a><span data-ttu-id="03fe5-103">Cambiar a EOP desde Google Postini, Barracuda Spam y Virus Firewall o Cisco IronPort</span><span class="sxs-lookup"><span data-stu-id="03fe5-103">Switch to EOP from Google Postini, the Barracuda Spam and Virus Firewall, or Cisco IronPort</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="03fe5-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="03fe5-104">**Applies to**</span></span>
- [<span data-ttu-id="03fe5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="03fe5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="03fe5-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="03fe5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="03fe5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03fe5-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

 <span data-ttu-id="03fe5-p101">El objetivo de este tema consiste en proporcionar los detalles sobre el proceso para cambiar a Protección en línea de Exchange (EOP) desde una aplicación de higiene de correo electrónico local o desde un servicio de protección basado en la nube, así como suministrar los recursos de ayuda necesarios para comenzar. Existen muchas soluciones de filtrado de correo no deseado, aunque el proceso para cambiar a EOP es similar en la mayoría de los casos.</span><span class="sxs-lookup"><span data-stu-id="03fe5-p101">The purpose of this topic is to help you understand the process for switching to Exchange Online Protection (EOP) from an on-premises email hygiene appliance or cloud-based protection service, and then to provide you with help resources to get started. There are many spam-filtering solutions, but the process for switching to EOP is similar in most cases.</span></span>

<span data-ttu-id="03fe5-110">Si es nuevo en EOP y desea leer una introducción a sus características antes de decidir cambiar, comience con el tema Información general de [Exchange Online Protection.](exchange-online-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="03fe5-110">If you are new to EOP and you want to read an overview of its features before you decide to switch, start with the [Exchange Online Protection overview](exchange-online-protection-overview.md) topic.</span></span>

<span data-ttu-id="03fe5-p102">Antes de cambiarse a EOP, es importante que piense si desea hospedar los buzones de correo protegidos por EOP en la nube, con Exchange Online, de forma local o en un escenario híbrido. (Por "híbrido" se entiende que algunos buzones de correo están hospedados de forma local y otros en Exchange Online). Los pasos de configuración necesarios para cada uno de estos escenarios de hospedaje (en la nube, en local o híbrido) pueden ser diferentes. Estas son algunas consideraciones que le pueden ayudar a elegir la implementación adecuada:</span><span class="sxs-lookup"><span data-stu-id="03fe5-p102">Before you switch to EOP, it's important to think about whether you want to host your EOP-protected mailboxes in the cloud, with Exchange Online, on-premises, or in a hybrid scenario. (Hybrid means that you have some mailboxes hosted on-premises and another portion hosted with Exchange Online.) Each of these hosting scenarios: cloud, on-premises, and hybrid, is possible, but the setup steps can vary. Here are a few considerations to help you choose the appropriate deployment:</span></span>

- <span data-ttu-id="03fe5-114">Protección **de EOP** con buzones locales: este escenario es adecuado si tiene una infraestructura de hospedaje de correo existente que desea usar o tiene requisitos empresariales para mantener los buzones locales y desea usar EOP como protección de correo electrónico basada en la nube.</span><span class="sxs-lookup"><span data-stu-id="03fe5-114">**EOP protection with on-premises mailboxes**: This scenario is appropriate if you have existing mail-hosting infrastructure you want to use, or you have business requirements to keep mailboxes on-premises, and you want to use EOP as your cloud-based email protection.</span></span> <span data-ttu-id="03fe5-115">En [Cambiar a EOP independiente](#switch-to-eop-standalone) se describe este escenario con más detalle.</span><span class="sxs-lookup"><span data-stu-id="03fe5-115">[Switch to EOP standalone](#switch-to-eop-standalone) describes this scenario in more detail.</span></span>

- <span data-ttu-id="03fe5-116">**Protección de EOP con** buzones de Exchange Online: este escenario es adecuado si desea la protección de EOP y todos los buzones hospedados en la nube.</span><span class="sxs-lookup"><span data-stu-id="03fe5-116">**EOP protection with Exchange Online mailboxes**: This scenario is appropriate if you want EOP protection and all of your mailboxes hosted in the cloud.</span></span> <span data-ttu-id="03fe5-117">Además, le ayudará a reducir la complejidad, ya que no es necesario mantener servidores de mensajería locales.</span><span class="sxs-lookup"><span data-stu-id="03fe5-117">It can help you reduce complexity, because you don't have to maintain on-premises messaging servers.</span></span> <span data-ttu-id="03fe5-118">Este escenario se describe en [Cambiar a Exchange Online](#switch-to-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="03fe5-118">[Switch to Exchange Online](#switch-to-exchange-online) describes this scenario.</span></span>

- <span data-ttu-id="03fe5-119">**Protección de EOP con** buzones híbridos: quizás quiera buzones en la nube, pero debe mantener los buzones de algunos usuarios locales.</span><span class="sxs-lookup"><span data-stu-id="03fe5-119">**EOP protection with hybrid mailboxes**: Perhaps you want cloud mailboxes, but you need to keep mailboxes for some users on-premises.</span></span> <span data-ttu-id="03fe5-120">Elija este escenario si desea hospedar algunos buzones de correo en local y otros en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="03fe5-120">Choose this scenario if you want some mailboxes hosted on-premises and another portion hosted with Exchange Online.</span></span> <span data-ttu-id="03fe5-121">En [Cambiar a una solución híbrida](#switch-to-a-hybrid-solution) se describe este escenario.</span><span class="sxs-lookup"><span data-stu-id="03fe5-121">[Switch to a hybrid solution](#switch-to-a-hybrid-solution) describes this scenario.</span></span>

## <a name="switch-to-eop-standalone"></a><span data-ttu-id="03fe5-122">Cambiar a EOP independiente</span><span class="sxs-lookup"><span data-stu-id="03fe5-122">Switch to EOP standalone</span></span>

<span data-ttu-id="03fe5-p106">Si actualmente hospeda sus buzones de correo en local y usa una aplicación de protección local o un servicio de protección de mensajería en la nube, puede cambiar a EOP para beneficiarse de sus características de protección y disponibilidad. Para configurar EOP en un escenario independiente, es decir, para hospedar los buzones de correo de forma local y usar EOP para proteger el correo electrónico, siga los pasos detallados en [Configurar un servicio de EOP](set-up-your-eop-service.md). En este tema se describen los pasos que hay que seguir para configurar la protección EOP. Entre ellos se incluye registrarse, agregar el dominio y configurar el flujo del correo con conectores.</span><span class="sxs-lookup"><span data-stu-id="03fe5-p106">If you currently host your mailboxes on premises and use an on-premises protection appliance or a cloud messaging-protection service, you can switch to EOP to take advantage of its protection features and availability. To set up EOP in a standalone scenario, which means you host your mailboxes on premises and use EOP to provide email protection, you can follow the steps outlined in [Set up your EOP service](set-up-your-eop-service.md). The topic outlines the steps for setting up EOP protection, which include sign up, adding your domain, and setting up mail flow with connectors.</span></span>

## <a name="switch-to-exchange-online"></a><span data-ttu-id="03fe5-126">Cambiar a Exchange Online</span><span class="sxs-lookup"><span data-stu-id="03fe5-126">Switch to Exchange Online</span></span>

<span data-ttu-id="03fe5-127">Tal vez tenga buzones locales protegidos por una aplicación local y desee saltar a buzones hospedados en la nube de Exchange Online y protección EOP para aprovechar las características de protección y mensajería en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="03fe5-127">Perhaps you have on-premises mailboxes protected by an on-premises appliance, and you want to jump to Exchange Online cloud-hosted mailboxes and EOP protection to take advantage of Microsoft 365 cloud messaging and protection features.</span></span> <span data-ttu-id="03fe5-128">Para empezar, puede registrarse en Microsoft 365 y agregar su dominio.</span><span class="sxs-lookup"><span data-stu-id="03fe5-128">To get started, you can sign up for Microsoft 365 and add your domain.</span></span> <span data-ttu-id="03fe5-129">Este escenario no requiere configurar conectores, ya que no hay ningún enrutamiento a buzones locales.</span><span class="sxs-lookup"><span data-stu-id="03fe5-129">This scenario doesn't require you to set up connectors, because there isn't any routing to on-premises mailboxes.</span></span> <span data-ttu-id="03fe5-130">Comience en [Obtener las últimas características avanzadas con Microsoft 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) para registrarse y familiarizarse con sus características.</span><span class="sxs-lookup"><span data-stu-id="03fe5-130">Begin at [Get the latest advanced features with Microsoft 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) to sign-up and get familiar with its features.</span></span>

<span data-ttu-id="03fe5-131">Durante el proceso de instalación de Microsoft 365, creará los usuarios de buzones basados en la nube.</span><span class="sxs-lookup"><span data-stu-id="03fe5-131">During the Microsoft 365 setup process, you will create your cloud-based mailbox users.</span></span>

## <a name="switch-to-a-hybrid-solution"></a><span data-ttu-id="03fe5-132">Cambiar a una solución híbrida</span><span class="sxs-lookup"><span data-stu-id="03fe5-132">Switch to a hybrid solution</span></span>

<span data-ttu-id="03fe5-p108">Puede que desee mover solo una parte de los buzones de correo a la nube debido a los requisitos de su compañía o a consideraciones reglamentarias. Al implementar un escenario híbrido, los buzones de correo se pueden mover a la nube en función de las necesidades del negocio. La migración a un escenario híbrido con la protección EOP resulta más complicada que cambiar a un escenario en la nube. No obstante, Microsoft ofrece diversos recursos y un completo soporte para escenarios híbridos a fin de facilitar la conversión.</span><span class="sxs-lookup"><span data-stu-id="03fe5-p108">You may want to move only a portion of your mailboxes to the cloud because of business requirements or regulatory considerations. When you deploy a hybrid scenario, you can move mailboxes to the cloud as your business requirements dictate. Migrating to a hybrid scenario with EOP protection is more complicated than moving to an all-cloud scenario, but Microsoft provides full hybrid support and ample resources to make the move to hybrid easier.</span></span>

<span data-ttu-id="03fe5-136">El mejor lugar para empezar, si está considerando una implementación híbrida, es Exchange Server [implementaciones híbridas.](/exchange/exchange-hybrid)</span><span class="sxs-lookup"><span data-stu-id="03fe5-136">The best place to start, if you are considering a hybrid deployment, is [Exchange Server hybrid deployments](/exchange/exchange-hybrid).</span></span> <span data-ttu-id="03fe5-137">Además, es importante comprender las diversas formas de enrutar el correo en un escenario híbrido.</span><span class="sxs-lookup"><span data-stu-id="03fe5-137">Additionally, there are a few different ways you can route mail in a hybrid scenario that are important to understand.</span></span> <span data-ttu-id="03fe5-138">[El enrutamiento de transporte en implementaciones híbridas de Exchange](/exchange/transport-routing) explica cada tipo, por lo que puede elegir el mejor escenario de enrutamiento, en función de los requisitos empresariales.</span><span class="sxs-lookup"><span data-stu-id="03fe5-138">[Transport Routing in Exchange hybrid deployments](/exchange/transport-routing) explains each type, so you can choose the best routing scenario, based on your business requirements.</span></span>

## <a name="migration-planning"></a><span data-ttu-id="03fe5-139">Diseño de la migración</span><span class="sxs-lookup"><span data-stu-id="03fe5-139">Migration planning</span></span>

<span data-ttu-id="03fe5-140">Cuando decida cambiar a EOP, asegúrese de considerar las siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="03fe5-140">When you decide to switch to EOP, make sure you give special consideration to the following areas:</span></span>

- <span data-ttu-id="03fe5-141">**Reglas de** filtrado personalizadas: si tiene reglas de filtrado personalizadas o directivas empresariales para detectar correo no deseado específico, le recomendamos que pruebe EOP con la configuración predeterminada durante un período de tiempo antes de migrar las reglas.</span><span class="sxs-lookup"><span data-stu-id="03fe5-141">**Custom Filtering Rules**: If you have custom filtering or business-policy rules to catch specific spam, we recommend that you try EOP with the default settings for a period of time before you migrate your rules.</span></span> <span data-ttu-id="03fe5-142">EOP ofrece protección contra correo no deseado a nivel empresarial con la configuración predeterminada, por lo que quizá no sea necesario migrar todas sus reglas a EOP.</span><span class="sxs-lookup"><span data-stu-id="03fe5-142">EOP offers enterprise-level spam protection with the default settings, it may turn out that you don't need to migrate some of your rules to EOP.</span></span> <span data-ttu-id="03fe5-143">Evidentemente, si tiene reglas que ejecutan ciertas directivas empresariales personalizadas, podrá crearlas.</span><span class="sxs-lookup"><span data-stu-id="03fe5-143">Of course, if you have rules in place that enforce specific custom business policies, you can create those.</span></span> <span data-ttu-id="03fe5-144">[Las reglas de flujo de correo (reglas de transporte) de Exchange Online Protection](mail-flow-rules-transport-rules-0.md) proporcionan instrucciones detalladas para crear reglas de flujo de correo en EOP.</span><span class="sxs-lookup"><span data-stu-id="03fe5-144">[Mail flow rules (transport rules) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md) provides detailed instructions for creating mail flow rules in EOP.</span></span>

- <span data-ttu-id="03fe5-145">**Listas de** direcciones IP permitidos y listas de direcciones IP bloqueados: si tiene listas de permisos por usuario y listas de bloqueo, espere un poco de tiempo para copiar las listas en EOP como parte del proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="03fe5-145">**IP allow lists and IP block lists**: If you have per-user allow lists and block lists, allow some time to copy the lists to EOP as part of your setup process.</span></span> <span data-ttu-id="03fe5-146">Para obtener más información acerca de la lista de direcciones IP permitidos y la lista de direcciones IP bloqueados, vea [Configure the connection filter policy](configure-the-connection-filter-policy.md).</span><span class="sxs-lookup"><span data-stu-id="03fe5-146">For more information about the IP Allow List and IP Block List, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="03fe5-147">**Comunicación segura:** si tiene un partner que requiere mensajería cifrada, le recomendamos que lo configure en el Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="03fe5-147">**Secure Communication**: If you have a partner that requires encrypted messaging, we recommend that you set this up in the Exchange admin center.</span></span> <span data-ttu-id="03fe5-148">Para configurar este escenario, vea Configurar conectores para el flujo de [correo seguro con una organización asociada.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)</span><span class="sxs-lookup"><span data-stu-id="03fe5-148">To configure this scenario, see [Set up connectors for secure mail flow with a partner organization](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner).</span></span>

> [!TIP]
> <span data-ttu-id="03fe5-149">Al cambiar de una aplicación local a EOP, se puede dejar la aplicación o un servidor para que realice las comprobaciones de reglas de negocio.</span><span class="sxs-lookup"><span data-stu-id="03fe5-149">When you switch from an on-premises appliance to EOP, it is possible to leave your appliance or a server in place that performs business rule checks.</span></span> <span data-ttu-id="03fe5-150">Por ejemplo, si el dispositivo realiza un filtrado personalizado en el correo saliente y desea que siga haciéndolo, puede configurar EOP para que envíe correo directamente al dispositivo para filtrarlo adicionalmente antes de enrutar a Internet.</span><span class="sxs-lookup"><span data-stu-id="03fe5-150">For instance, if your appliance performs custom filtering on outbound mail, and you want it to continue doing so, you can configure EOP to send mail directly to the appliance for additional filtering, before it is routed to the internet.</span></span>