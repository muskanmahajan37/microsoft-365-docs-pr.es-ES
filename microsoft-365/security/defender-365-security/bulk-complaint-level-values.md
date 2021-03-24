---
title: Valores de nivel de queja masiva
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre los valores de nivel de cumplimiento masivo (BCL) que se usan en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d85dca6e18ebdad4d8f2a5c5f6c5b613c23b47d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073480"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="5ba68-103">Nivel de queja masiva (BCL) en EOP</span><span class="sxs-lookup"><span data-stu-id="5ba68-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5ba68-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="5ba68-104">**Applies to**</span></span>
- [<span data-ttu-id="5ba68-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5ba68-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5ba68-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="5ba68-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5ba68-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ba68-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="5ba68-108">En organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP asigna un nivel de cumplimiento masivo (BCL) a los mensajes entrantes de los buzones masivos.</span><span class="sxs-lookup"><span data-stu-id="5ba68-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="5ba68-109">El BCL se agrega al mensaje en un encabezado X y es similar al nivel de confianza de correo no deseado [(SCL)](spam-confidence-levels.md) que se usa para identificar mensajes como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="5ba68-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="5ba68-110">Un BCL más alto indica que un mensaje masivo es más probable que genere quejas (y, por lo tanto, es más probable que sea correo no deseado).</span><span class="sxs-lookup"><span data-stu-id="5ba68-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="5ba68-111">Microsoft usa orígenes internos y de terceros para identificar el correo masivo y determinar el BCL adecuado.</span><span class="sxs-lookup"><span data-stu-id="5ba68-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="5ba68-112">Los remitentes masivos varían en sus patrones de envío, creación de contenido y prácticas de adquisición de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="5ba68-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="5ba68-113">Los buenos carteros masivos envían mensajes deseados con contenido relevante a sus suscriptores.</span><span class="sxs-lookup"><span data-stu-id="5ba68-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="5ba68-114">Estos mensajes generan pocas quejas por parte de los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="5ba68-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="5ba68-115">Otros troyanos de envío masivo de correo electrónico envían mensajes no solicitados muy similares al correo no deseado y generan muchas quejas por parte de los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="5ba68-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="5ba68-116">Los mensajes de un correo masivo se conocen como correo masivo o correo gris.</span><span class="sxs-lookup"><span data-stu-id="5ba68-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="5ba68-117">El filtrado de  correo no deseado marca los mensajes como correo electrónico masivo en función del umbral BCL (el valor predeterminado o un valor que especifique) y realiza la acción especificada en el mensaje (la acción predeterminada es entregar el mensaje a la carpeta correo no deseado del destinatario).</span><span class="sxs-lookup"><span data-stu-id="5ba68-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="5ba68-118">Para obtener más información, vea [Configure anti-spam policies](configure-your-spam-filter-policies.md) y [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="5ba68-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="5ba68-119">Los umbrales BCL se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="5ba68-119">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="5ba68-120">BCL</span><span class="sxs-lookup"><span data-stu-id="5ba68-120">BCL</span></span>|<span data-ttu-id="5ba68-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ba68-121">Description</span></span>|
|:---:|---|
|<span data-ttu-id="5ba68-122">0</span><span class="sxs-lookup"><span data-stu-id="5ba68-122">0</span></span>|<span data-ttu-id="5ba68-123">El mensaje no es de un remitente de correo masivo.</span><span class="sxs-lookup"><span data-stu-id="5ba68-123">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="5ba68-124">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="5ba68-124">1, 2, 3</span></span>|<span data-ttu-id="5ba68-125">El mensaje proviene de un remitente de correo masivo que genera pocas quejas.</span><span class="sxs-lookup"><span data-stu-id="5ba68-125">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="5ba68-126">4, 5, 6, 7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5ba68-126">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="5ba68-127">El mensaje proviene de un remitente de correo masivo que genera un número mixto de quejas.</span><span class="sxs-lookup"><span data-stu-id="5ba68-127">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="5ba68-128">8, 9</span><span class="sxs-lookup"><span data-stu-id="5ba68-128">8, 9</span></span>|<span data-ttu-id="5ba68-129">El mensaje es de un remitente masivo que genera un gran número de quejas.</span><span class="sxs-lookup"><span data-stu-id="5ba68-129">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="5ba68-130"><sup>\*</sup> Este es el valor de umbral predeterminado que se usa en las directivas contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="5ba68-130"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>