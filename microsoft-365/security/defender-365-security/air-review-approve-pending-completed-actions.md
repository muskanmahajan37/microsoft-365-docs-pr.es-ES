---
title: Revisar y administrar acciones de corrección en Microsoft Defender para Office 365
keywords: AIR, autoIR, ATP, automated, investigation, response, remediation, threats, advanced, threat, protection
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Obtenga información sobre las acciones de corrección en las capacidades automatizadas de investigación y respuesta en Microsoft Defender para Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: 61e9df45419cc73dae27b86dad47e1938183593d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073656"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="3d3e7-104">Revisar y administrar acciones de corrección en Office 365</span><span class="sxs-lookup"><span data-stu-id="3d3e7-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="3d3e7-105">A medida que las investigaciones automatizadas en el &  contenido de colaboración resultan en veredictos, como malintencionados o sospechosos, se crean determinadas acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-105">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="3d3e7-106">En Microsoft Defender para Office 365, las acciones de corrección pueden incluir:</span><span class="sxs-lookup"><span data-stu-id="3d3e7-106">In Microsoft Defender for Office 365, remediation actions can include:</span></span>
- <span data-ttu-id="3d3e7-107">Bloqueo de una dirección URL (hora de hacer clic)</span><span class="sxs-lookup"><span data-stu-id="3d3e7-107">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="3d3e7-108">Eliminación de mensajes de correo electrónico o clústeres</span><span class="sxs-lookup"><span data-stu-id="3d3e7-108">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="3d3e7-109">Quarantining email or email attachments</span><span class="sxs-lookup"><span data-stu-id="3d3e7-109">Quarantining email or email attachments</span></span>
- <span data-ttu-id="3d3e7-110">Desactivar el reenvío de correo externo</span><span class="sxs-lookup"><span data-stu-id="3d3e7-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="3d3e7-111">Estas acciones de corrección no se toman a menos que el equipo de operaciones de seguridad las apruebe.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="3d3e7-112">Se recomienda revisar y aprobar las acciones pendientes tan pronto como sea posible para que las investigaciones automatizadas se completen de forma oportuna.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="3d3e7-113">En algunos casos, puede deshacer una acción de corrección.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-113">In some cases, you can undo a remediation action.</span></span>

<span data-ttu-id="3d3e7-114">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="3d3e7-114">**Applies to**</span></span>
- [<span data-ttu-id="3d3e7-115">Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="3d3e7-115">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3d3e7-116">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3d3e7-116">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="3d3e7-117">Aprobar (o rechazar) acciones pendientes</span><span class="sxs-lookup"><span data-stu-id="3d3e7-117">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="3d3e7-118">Vaya al Centro de seguridad de Microsoft 365 ( <https://security.microsoft.com> ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-118">Go to the Microsoft 365 security center (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="3d3e7-119">En el panel de navegación, seleccione **Centro de acciones**.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-119">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="3d3e7-120">En la **pestaña** Pendiente, revise la lista de acciones que están a la espera de su aprobación.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-120">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="3d3e7-121">Seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-121">Select an item in the list.</span></span> <span data-ttu-id="3d3e7-122">Se abre el panel desplegable.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-122">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="3d3e7-123">Revise la información del panel desplegable y, a continuación, siga uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3d3e7-123">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="3d3e7-124">Seleccione **Abrir página de investigación** para ver más detalles sobre la investigación.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-124">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="3d3e7-125">Seleccione **Aprobar** para iniciar una acción pendiente.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-125">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="3d3e7-126">Seleccione **Rechazar** para evitar que se haga una acción pendiente.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-126">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="3d3e7-127">Deshacer una acción de corrección</span><span class="sxs-lookup"><span data-stu-id="3d3e7-127">Undo one remediation action</span></span>

1. <span data-ttu-id="3d3e7-128">Vaya al Centro de acciones ( <https://security.microsoft.com/action-center> ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-128">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="3d3e7-129">En la **pestaña** Historial, seleccione una acción que desee deshacer.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-129">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="3d3e7-130">En el panel de la parte derecha de la pantalla, seleccione **Deshacer**.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-130">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="3d3e7-131">Deshacer varias acciones de corrección</span><span class="sxs-lookup"><span data-stu-id="3d3e7-131">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="3d3e7-132">Vaya al Centro de acciones ( <https://security.microsoft.com/action-center> ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-132">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="3d3e7-133">En la **pestaña** Historial, seleccione las acciones que desea deshacer.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-133">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="3d3e7-134">Asegúrese de seleccionar los elementos que tienen el mismo tipo de acción.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-134">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="3d3e7-135">Se abre un panel desplegable.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-135">A flyout pane opens.</span></span>
3. <span data-ttu-id="3d3e7-136">En el panel desplegable, seleccione Deshacer.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-136">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="3d3e7-137">Para quitar un archivo de la cuarentena en varios dispositivos</span><span class="sxs-lookup"><span data-stu-id="3d3e7-137">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="3d3e7-138">Vaya al Centro de acciones ( <https://security.microsoft.com/action-center> ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-138">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="3d3e7-139">En la **pestaña** Historial, seleccione un archivo que tenga el tipo de acción **Archivo de cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-139">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="3d3e7-140">En el panel de la parte derecha de la pantalla, seleccione **Aplicar a X más** instancias de este archivo y, a continuación, seleccione **Deshacer**.</span><span class="sxs-lookup"><span data-stu-id="3d3e7-140">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3d3e7-141">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3d3e7-141">Next steps</span></span>

- [<span data-ttu-id="3d3e7-142">Usar el Explorador de amenazas</span><span class="sxs-lookup"><span data-stu-id="3d3e7-142">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="3d3e7-143">Cómo notificar falsos positivos/negativos en capacidades automatizadas de investigación y respuesta</span><span class="sxs-lookup"><span data-stu-id="3d3e7-143">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="3d3e7-144">Ver también</span><span class="sxs-lookup"><span data-stu-id="3d3e7-144">See also</span></span>

- [<span data-ttu-id="3d3e7-145">Ver detalles y resultados de una investigación automatizada en Office 365</span><span class="sxs-lookup"><span data-stu-id="3d3e7-145">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)