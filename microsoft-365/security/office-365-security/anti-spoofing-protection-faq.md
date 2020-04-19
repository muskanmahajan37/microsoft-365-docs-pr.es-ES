---
title: Preguntas más frecuentes sobre protección contra la suplantación de identidad
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Preguntas más frecuentes y respuestas para administradores acerca de la protección contra la suplantación de identidad en Exchange Online y Exchange Online Protection (EOP) independiente.
ms.openlocfilehash: b39e48fd57b899e6296d40ab10aac265cb4165a3
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "43529892"
---
# <a name="anti-spoofing-protection-faq-in-office-365"></a><span data-ttu-id="f1273-103">Preguntas más frecuentes sobre protección contra la suplantación de identidad en Office 365</span><span class="sxs-lookup"><span data-stu-id="f1273-103">Anti-spoofing protection FAQ in Office 365</span></span>

<span data-ttu-id="f1273-104">En este tema se proporcionan preguntas frecuentes y respuestas sobre la protección contra la suplantación de identidad para los clientes de Office 365 con buzones en Exchange online o los clientes independientes de Exchange Online Protection (EOP) sin buzones de correo de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f1273-104">This topic provides frequently asked questions and answers about anti-spoofing protection for Office 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes.</span></span>

<span data-ttu-id="f1273-105">Para preguntas y respuestas sobre la protección contra correo no deseado, consulte [preguntas más frecuentes sobre protección contra correo no deseado](anti-spam-protection-faq.md).</span><span class="sxs-lookup"><span data-stu-id="f1273-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="f1273-106">Para obtener preguntas y respuestas sobre la protección antimalware, consulte [preguntas más frecuentes sobre la protección contra malware en Office 365](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="f1273-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ in Office 365](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="f1273-107">¿Por qué eligió Microsoft el correo electrónico no deseado sin autenticar?</span><span class="sxs-lookup"><span data-stu-id="f1273-107">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="f1273-108">Debido al impacto de los ataques de suplantación de identidad (phishing) y debido a que la autenticación de correo electrónico ha estado por encima de los 15 años, Microsoft cree que el riesgo de continuar permitiendo el correo entrante no autenticado es mayor que el riesgo de perder correo entrante.</span><span class="sxs-lookup"><span data-stu-id="f1273-108">Because of the impact of phishing attacks, and because email authentication has been around for over 15 years, Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="f1273-109">¿El correo electrónico entrante no autenticado no está autenticado hacer que el correo electrónico legítimo se marque como correo no deseado?</span><span class="sxs-lookup"><span data-stu-id="f1273-109">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="f1273-110">Cuando Microsoft habilitaba esta característica en 2018, se han producido algunos falsos positivos (los mensajes correctos se marcaron como no válidos).</span><span class="sxs-lookup"><span data-stu-id="f1273-110">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="f1273-111">Sin embargo, con el tiempo, los remitentes ajustados a los nuevos requisitos de autenticación del remitente y el número de mensajes que se identificaron de forma insignificante como falsificado se convirtió en despreciable en la mayoría de las rutas de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f1273-111">However, over time, senders adjusted to the new sender authentication requirements, and the number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="f1273-112">Microsoft ha adoptado primero los nuevos requisitos de autenticación de correo electrónico varias semanas antes de implementarlos para los clientes.</span><span class="sxs-lookup"><span data-stu-id="f1273-112">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="f1273-113">Aunque hubo complicaciones al principio, se fueron reduciendo gradualmente.</span><span class="sxs-lookup"><span data-stu-id="f1273-113">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-office-365-customers-without-atp"></a><span data-ttu-id="f1273-114">¿Está disponible inteligencia de suplantación de identidad para los clientes de Office 365 sin ATP?</span><span class="sxs-lookup"><span data-stu-id="f1273-114">Is spoof intelligence available to Office 365 customers without ATP?</span></span>

<span data-ttu-id="f1273-115">Sí.</span><span class="sxs-lookup"><span data-stu-id="f1273-115">Yes.</span></span> <span data-ttu-id="f1273-116">A partir del 2018 de octubre, la inteligencia de identidad está disponible para todas las organizaciones con buzones de correo de Exchange Online y organizaciones independientes de EOP sin buzones de correo de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f1273-116">As of October 2018, spoof intelligence is available to all organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="f1273-117">La tecnología contra la suplantación de identidad se implementó inicialmente en organizaciones que tenían suscripciones de Office 365 Enterprise E5 o el complemento de protección contra amenazas avanzada (ATP) de Office 365 para su suscripción.</span><span class="sxs-lookup"><span data-stu-id="f1273-117">Anti-spoofing technology was initially deployed to organizations that had Office 365 Enterprise E5 subscriptions or the Office 365 Advanced Threat Protection (ATP) add-on for their subscription.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="f1273-118">¿Cómo señalar mensajes de correo no deseado o correo deseado a Microsoft?</span><span class="sxs-lookup"><span data-stu-id="f1273-118">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="f1273-119">Consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="f1273-119">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="f1273-120">Soy Administrador y no conozco todos los orígenes de los mensajes de mi dominio de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f1273-120">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="f1273-121">Ve [que no conoces todos los orígenes de tu correo electrónico](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span><span class="sxs-lookup"><span data-stu-id="f1273-121">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="f1273-122">¿Qué sucede si se deshabilita la protección contra la suplantación de identidad para mi organización?</span><span class="sxs-lookup"><span data-stu-id="f1273-122">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="f1273-123">Esto no se recomienda porque estará expuesto a más intentos de mensajes de phishing y spam.</span><span class="sxs-lookup"><span data-stu-id="f1273-123">We do not recommend this because you will be exposed to more missed phishing and spam messages.</span></span> <span data-ttu-id="f1273-124">No todos los casos de phishing son spoofing y no todos los spoofing pasarán sin detectarse.</span><span class="sxs-lookup"><span data-stu-id="f1273-124">Not all phishing is spoofing, and not all spoofs will be missed.</span></span> <span data-ttu-id="f1273-125">Pero, el riesgo será mayor que para un cliente que habilita la protección contra la suplantación.</span><span class="sxs-lookup"><span data-stu-id="f1273-125">However, your risk will be higher than a customer who enables anti-spoofing.</span></span>

<span data-ttu-id="f1273-126">Ahora que hay disponible un [filtrado mejorado para los conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) , ya no se recomienda desactivar la protección contra la suplantación de identidad si el registro MX apunta a otro servidor o servicio antes de entregar el correo electrónico a EOP.</span><span class="sxs-lookup"><span data-stu-id="f1273-126">Now that [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended that you turn off anti-spoofing protection if your MX record points to another server or service before delivering email to EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="f1273-127">¿La protección contra la suplantación de identidad supone que estoy protegido contra la suplantación de identidad (phishing)?</span><span class="sxs-lookup"><span data-stu-id="f1273-127">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="f1273-128">Lamentablemente, no.</span><span class="sxs-lookup"><span data-stu-id="f1273-128">Unfortunately, no.</span></span> <span data-ttu-id="f1273-129">Los atacantes se adaptarán a usar otras técnicas (por ejemplo, cuentas o cuentas comprometidas en los servicios de correo electrónico gratuitos).</span><span class="sxs-lookup"><span data-stu-id="f1273-129">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="f1273-130">Sin embargo, la protección contra suplantación de identidad funciona mucho mejor para detectar estos otros tipos de métodos de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="f1273-130">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="f1273-131">Las capas de protección de Office 365 están diseñadas y se compilan de forma conjunta.</span><span class="sxs-lookup"><span data-stu-id="f1273-131">The protection layers in Office 365 are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="f1273-132">¿Otros servicios de correo electrónico grandes bloquean el correo electrónico entrante no autenticado?</span><span class="sxs-lookup"><span data-stu-id="f1273-132">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="f1273-133">Casi todos los servicios de correo electrónico grandes implementan las comprobaciones tradicionales de SPF, DKIM y DMARC.</span><span class="sxs-lookup"><span data-stu-id="f1273-133">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="f1273-134">Algunos servicios tienen otras comprobaciones más estrictas, pero pocos van tan lejos de Office 365 para bloquear el correo no autenticado y tratarlos como mensajes falsificados.</span><span class="sxs-lookup"><span data-stu-id="f1273-134">Some services have other, more strict checks, but few go as far as Office 365 to block unauthenticated email and treat them as as spoofed messages.</span></span> <span data-ttu-id="f1273-135">Sin embargo, la industria está cada vez más consciente de los problemas con el correo no autenticado, especialmente debido al problema de la suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="f1273-135">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="f1273-136">¿Necesito habilitar la configuración avanzada de filtro de correo no deseado "registro SPF: error grave" (_MarkAsSpamSpfRecordHardFail_) si habilito la suplantación de identidad (phishing)?</span><span class="sxs-lookup"><span data-stu-id="f1273-136">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) if I enable anti-spoofing?</span></span>

<span data-ttu-id="f1273-137">No.</span><span class="sxs-lookup"><span data-stu-id="f1273-137">No.</span></span> <span data-ttu-id="f1273-138">Esta configuración de ASF ya no es necesaria porque la suplantación de identidad no solo considera un error de disco duro SPF, sino un conjunto mucho más amplio de criterios.</span><span class="sxs-lookup"><span data-stu-id="f1273-138">This ASF setting no longer required because anti-spoofing not only considers SPF hard fails, but a much wider set of criteria.</span></span> <span data-ttu-id="f1273-139">Si habilita la protección contra la suplantación y la opción de **Registro de SPF: error grave** (_MarkAsSpamSpfRecordHardFail_), es probable que reciba más falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="f1273-139">If you have anti-spoofing enabled and the **SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="f1273-140">Le recomendamos que deshabilite esta característica ya que proporciona casi ninguna ventaja para detectar correo no deseado o de suplantación de identidad (phishing) y, en cambio, generará principalmente falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="f1273-140">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="f1273-141">Para obtener más información, consulte [Configuración del filtro de correo no deseado avanzado (ASF) en Office 365](advanced-spam-filtering-asf-options.md).</span><span class="sxs-lookup"><span data-stu-id="f1273-141">For more information, see [Advanced Spam Filter (ASF) settings in Office 365](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="f1273-142">¿Ayuda el esquema de reescritura de remitentes a corregir el correo electrónico reenviado?</span><span class="sxs-lookup"><span data-stu-id="f1273-142">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="f1273-143">SRS solo soluciona parcialmente el problema del correo electrónico reenviado.</span><span class="sxs-lookup"><span data-stu-id="f1273-143">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="f1273-144">Al volver a escribir el **correo SMTP desde**, SRS puede asegurarse de que el mensaje reenviado pasa SPF en el siguiente destino.</span><span class="sxs-lookup"><span data-stu-id="f1273-144">By rewriting the SMTP **MAIL FROM**, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="f1273-145">Sin embargo, como la suplantación de identidad se basa en la dirección **from** en combinación con el dominio **de firma de correo** electrónico o de firma DKIM (u otras señales), no es suficiente evitar que el correo electrónico reenviado por SRS se marque como falso.</span><span class="sxs-lookup"><span data-stu-id="f1273-145">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>