---
title: Informe de no entrega en el panel flujo de correo
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar el informe de detalles de no entrega en el panel flujo de correo del Centro de cumplimiento de seguridad de & para supervisar los códigos de error encontrados con más frecuencia en los informes de no entrega (también conocidos como NDR o mensajes de rebote) de los remitentes de su organización.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01d25f11051606139c2ee8b88cade18963de599d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071235"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="bbfe4-103">Informe de no entrega en el Centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="bbfe4-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bbfe4-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="bbfe4-104">**Applies to**</span></span>
- [<span data-ttu-id="bbfe4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bbfe4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="bbfe4-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="bbfe4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="bbfe4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bbfe4-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="bbfe4-108">El  informe de no [](mail-flow-insights-v2.md) entrega en el panel flujo de correo del Centro de seguridad y cumplimiento de [&](https://protection.office.com) muestra los códigos de error más encontrados en los informes de no entrega (también conocidos como NDR o mensajes de rebote) para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="bbfe4-108">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="bbfe4-109">Este informe muestra los detalles de las NDR para que pueda solucionar problemas de entrega de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="bbfe4-109">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![Widget de informe de no entrega en el panel Flujo de correo del Centro de & cumplimiento](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="bbfe4-111">Vista Informe para el informe de no entrega</span><span class="sxs-lookup"><span data-stu-id="bbfe4-111">Report view for the Non-delivery report</span></span>

<span data-ttu-id="bbfe4-112">Al hacer clic en el widget **Informe de no** entrega, se le llevará al informe de no **entrega.**</span><span class="sxs-lookup"><span data-stu-id="bbfe4-112">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="bbfe4-113">De forma predeterminada, se muestra la actividad de todos los códigos de error.</span><span class="sxs-lookup"><span data-stu-id="bbfe4-113">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="bbfe4-114">Si hace clic **en Mostrar datos para**, puede seleccionar un código de error específico en el desplegable.</span><span class="sxs-lookup"><span data-stu-id="bbfe4-114">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="bbfe4-115">Si mantiene el mouse sobre un color específico (código de error) en un día específico del gráfico, verá el número total de mensajes del error.</span><span class="sxs-lookup"><span data-stu-id="bbfe4-115">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![Vista Informe en el informe de dominio no aceptado](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="bbfe4-117">Vista de tabla Detalles del informe de no entrega</span><span class="sxs-lookup"><span data-stu-id="bbfe4-117">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="bbfe4-118">Si hace clic **en Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="bbfe4-118">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="bbfe4-119">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="bbfe4-119">**Date**</span></span>
- <span data-ttu-id="bbfe4-120">**Código de informe de no entrega**</span><span class="sxs-lookup"><span data-stu-id="bbfe4-120">**Non-delivery report code**</span></span>
- <span data-ttu-id="bbfe4-121">**Count**</span><span class="sxs-lookup"><span data-stu-id="bbfe4-121">**Count**</span></span>
- <span data-ttu-id="bbfe4-122">**Mensajes de** ejemplo: los IDs de mensaje de una muestra de mensajes afectados.</span><span class="sxs-lookup"><span data-stu-id="bbfe4-122">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="bbfe4-123">Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con Fecha de **inicio** y Fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="bbfe4-123">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="bbfe4-124">Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o varios destinatarios, haga clic en **Solicitar descarga**.</span><span class="sxs-lookup"><span data-stu-id="bbfe4-124">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="bbfe4-125">Al seleccionar una fila de la tabla, aparece un menú desplegable con la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="bbfe4-125">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="bbfe4-126">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="bbfe4-126">**Date**</span></span>
- <span data-ttu-id="bbfe4-127">**Código de informe de no** entrega: puede hacer clic en el vínculo para obtener más información sobre las causas y soluciones del código de error específico.</span><span class="sxs-lookup"><span data-stu-id="bbfe4-127">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="bbfe4-128">**Count**</span><span class="sxs-lookup"><span data-stu-id="bbfe4-128">**Count**</span></span>
- <span data-ttu-id="bbfe4-129">**Mensajes de** ejemplo: puede hacer clic **en Ver mensajes de ejemplo** para ver los resultados del seguimiento de mensajes de una muestra de los mensajes afectados. [](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="bbfe4-129">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![El menú desplegable de detalles después de seleccionar una fila en la vista Tabla de detalles en el informe de no entrega](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="bbfe4-131">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bbfe4-131">Related topics</span></span>

<span data-ttu-id="bbfe4-132">Para obtener información acerca de otras perspectivas en el panel flujo de correo, vea [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="bbfe4-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>