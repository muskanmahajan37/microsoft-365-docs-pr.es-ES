---
title: Corrección de información de reglas de flujo de correo lento
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar la información corregir reglas de flujo de correo lento en el Centro de seguridad y cumplimiento de & para identificar y corregir reglas de flujo de correo ineficaces o rotas (también conocidas como reglas de transporte) en su organización.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 51ffa92402fd3e7c9e76115642426d3cce0a9e19
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070024"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="eca9d-103">Corregir la información de reglas de flujo de correo lento en el Centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="eca9d-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="eca9d-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="eca9d-104">**Applies to**</span></span>
- [<span data-ttu-id="eca9d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="eca9d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="eca9d-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="eca9d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="eca9d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eca9d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="eca9d-108">Las reglas de flujo de correo ineficaces (también conocidas como reglas de transporte) pueden provocar retrasos en el flujo de correo para su organización.</span><span class="sxs-lookup"><span data-stu-id="eca9d-108">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="eca9d-109">Esta información informa de las reglas de flujo de correo que tienen un impacto en el flujo de correo de la organización.</span><span class="sxs-lookup"><span data-stu-id="eca9d-109">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="eca9d-110">Algunos ejemplos de estos tipos de reglas son:</span><span class="sxs-lookup"><span data-stu-id="eca9d-110">Examples of these types of rules include:</span></span>

- <span data-ttu-id="eca9d-111">Condiciones de las que **se usa Is member of** for large groups.</span><span class="sxs-lookup"><span data-stu-id="eca9d-111">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="eca9d-112">Condiciones que usan coincidencias de patrones de expresión regular compleja (regex).</span><span class="sxs-lookup"><span data-stu-id="eca9d-112">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="eca9d-113">Condiciones que usan la comprobación de contenido en datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="eca9d-113">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="eca9d-114">La información **corregir** reglas de  flujo de correo [](mail-flow-insights-v2.md) lento en el área Recomendado para usted del panel flujo de correo en el Centro de seguridad y cumplimiento de [&](https://protection.office.com) le notifica cuándo una regla de flujo de correo tarda demasiado tiempo en completarse.</span><span class="sxs-lookup"><span data-stu-id="eca9d-114">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span>

<span data-ttu-id="eca9d-115">Esta información aparece solo después de que se detecte la condición (si no tiene bucles de correo, no verá la información).</span><span class="sxs-lookup"><span data-stu-id="eca9d-115">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="eca9d-116">Puede usar esta notificación para ayudarle a identificar y ajustar las reglas de flujo de correo para ayudar a reducir los retrasos en el flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="eca9d-116">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Corregir la información de reglas de flujo de correo lento en el área Recomendado para usted del panel flujo de correo](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="eca9d-118">Al hacer clic **en Ver detalles** en el widget, aparece un control flotante con más información:</span><span class="sxs-lookup"><span data-stu-id="eca9d-118">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="eca9d-119">**Regla:** puede pasar el puntero sobre el resumen para ver todas las condiciones, excepciones y acciones de la regla.</span><span class="sxs-lookup"><span data-stu-id="eca9d-119">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="eca9d-120">Puede hacer clic en el resumen para editar la regla en el Centro de administración de Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="eca9d-120">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="eca9d-121">**Número de mensajes evaluados:** puede hacer clic [](message-trace-scc.md) en Ver mensajes de ejemplo para ver los resultados del seguimiento de mensajes de una muestra de los mensajes que se vieron afectados por la regla. </span><span class="sxs-lookup"><span data-stu-id="eca9d-121">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="eca9d-122">**Tiempo promedio invertido en cada mensaje**</span><span class="sxs-lookup"><span data-stu-id="eca9d-122">**Average time spent on each message**</span></span>
- <span data-ttu-id="eca9d-123">**Mediana de tiempo invertido en un mensaje:** el valor intermedio que separa la mitad superior de los datos de la mitad inferior del tiempo.</span><span class="sxs-lookup"><span data-stu-id="eca9d-123">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![Control desplegable de detalles que aparece después de hacer clic en Ver detalles en la información sobre las reglas de flujo de correo lento fix](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="eca9d-125">Para obtener más información acerca de las condiciones y excepciones en las reglas de flujo de correo, vea Condiciones y excepciones de reglas de flujo de correo [(predicados) en Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span><span class="sxs-lookup"><span data-stu-id="eca9d-125">For more information about conditions and exceptions in mail flow rules, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="see-also"></a><span data-ttu-id="eca9d-126">Ver también</span><span class="sxs-lookup"><span data-stu-id="eca9d-126">See also</span></span>

<span data-ttu-id="eca9d-127">Para obtener información acerca de otras perspectivas en el panel flujo de correo, vea [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="eca9d-127">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>