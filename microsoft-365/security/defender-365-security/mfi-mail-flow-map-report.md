---
title: Mapa de flujo de correo
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
description: Los administradores pueden aprender a usar el mapa de flujo de correo en el panel flujo de correo del Centro de seguridad y cumplimiento de & para visualizar y realizar un seguimiento de cómo fluye el correo hacia y desde su organización a través de conectores y sin usar conectores.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e806dde2e6f3ddde5cce3b61c85fe0b024ba2fe
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071304"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="578e7-103">Mapa de flujo de correo en el Centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="578e7-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="578e7-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="578e7-104">**Applies to**</span></span>
- [<span data-ttu-id="578e7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="578e7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="578e7-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="578e7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="578e7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="578e7-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="578e7-108">El **mapa de flujo de correo** en el panel [Flujo](mail-flow-insights-v2.md) de correo del Centro de seguridad [& cumplimiento](https://protection.office.com) proporciona información sobre cómo fluye el correo a través de la organización.</span><span class="sxs-lookup"><span data-stu-id="578e7-108">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="578e7-109">Puede usar esta información para aprender patrones, identificar anomalías y solucionar problemas a medida que se producen.</span><span class="sxs-lookup"><span data-stu-id="578e7-109">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Widget de mapa de flujo de correo en el panel Flujo de correo del Centro de seguridad & cumplimiento](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="578e7-111">De forma predeterminada, el widget muestra el patrón de flujo de correo del día anterior en un gráfico conocido como diagrama *de Sankey.*</span><span class="sxs-lookup"><span data-stu-id="578e7-111">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="578e7-112">Puede usar la flecha izquierda flecha izquierda y flecha derecha flecha ![ derecha para mostrar información de diferentes ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) días.</span><span class="sxs-lookup"><span data-stu-id="578e7-112">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="578e7-113">Cada color diferente representa el flujo de correo sobre un conector entrante o saliente diferente (o sin conectores).</span><span class="sxs-lookup"><span data-stu-id="578e7-113">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="578e7-114">Si mantiene el mouse sobre un color específico, se muestra el número de mensajes para ese tipo de conector.</span><span class="sxs-lookup"><span data-stu-id="578e7-114">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="578e7-115">Vista Informe para el mapa de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="578e7-115">Report view for the Mail flow map</span></span>

<span data-ttu-id="578e7-116">Hacer clic en el widget **Mapa de flujo de** correo le llevará al informe de mapa de flujo **de** correo.</span><span class="sxs-lookup"><span data-stu-id="578e7-116">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="578e7-117">Los gráficos siguientes están disponibles en la vista informe:</span><span class="sxs-lookup"><span data-stu-id="578e7-117">The following charts are available in the report view:</span></span>

- <span data-ttu-id="578e7-118">**Mostrar datos para: Información general:** Se trata básicamente de una vista más grande del widget.</span><span class="sxs-lookup"><span data-stu-id="578e7-118">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="578e7-119">Si mantiene el mouse sobre un color específico, se muestra el número de mensajes para ese tipo de conector.</span><span class="sxs-lookup"><span data-stu-id="578e7-119">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Vista introducción en el informe de mapa de flujo de correo](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="578e7-121">**Mostrar datos para: Detalle:** esta vista muestra detalles sobre los conectores y los dominios de destino.</span><span class="sxs-lookup"><span data-stu-id="578e7-121">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="578e7-122">Los dominios principales de remitente y destinatario se enumeran y el resto se ponen en **Otros**.</span><span class="sxs-lookup"><span data-stu-id="578e7-122">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="578e7-123">Si mantiene el mouse sobre un color y una sección específicos, se muestra el número de mensajes.</span><span class="sxs-lookup"><span data-stu-id="578e7-123">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Vista de detalles en el informe de mapa de flujo de correo](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="578e7-125">Si hace clic **en Filtros** en una vista de informe, puede especificar un intervalo de fechas con Fecha **de inicio** y Fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="578e7-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="578e7-126">Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o varios destinatarios, haga clic en **Solicitar descarga**.</span><span class="sxs-lookup"><span data-stu-id="578e7-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="578e7-127">Los conocimientos relacionados se muestran debajo del mapa de flujo de correo si están disponibles (por ejemplo, [fix possible mail loop insight](mfi-mail-loop-insight.md)).</span><span class="sxs-lookup"><span data-stu-id="578e7-127">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="578e7-128">Vista de tabla Detalles para el mapa de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="578e7-128">Details table view for the Mail flow map</span></span>

<span data-ttu-id="578e7-129">Si hace clic **en Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="578e7-129">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="578e7-130">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="578e7-130">**Date**</span></span>
- <span data-ttu-id="578e7-131">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="578e7-131">**Category**</span></span>
- <span data-ttu-id="578e7-132">**Conector /proveedor de servicios de terceros**</span><span class="sxs-lookup"><span data-stu-id="578e7-132">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="578e7-133">**Dominio de remitente/destinatario**</span><span class="sxs-lookup"><span data-stu-id="578e7-133">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="578e7-134">**Recuento de mensajes**</span><span class="sxs-lookup"><span data-stu-id="578e7-134">**Message count**</span></span>

<span data-ttu-id="578e7-135">Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con Fecha de **inicio** y Fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="578e7-135">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="578e7-136">Si selecciona una fila, se muestran detalles similares en un menú desplegable:</span><span class="sxs-lookup"><span data-stu-id="578e7-136">If you select a row, similar details are shown in a flyout:</span></span>

![Control desplegable de detalles de la tabla de detalles en el mapa de flujo de correo](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="578e7-138">Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o varios destinatarios, haga clic en **Solicitar descarga**.</span><span class="sxs-lookup"><span data-stu-id="578e7-138">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="578e7-139">Para volver a la vista informes, haga clic **en Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="578e7-139">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="578e7-140">Ver también</span><span class="sxs-lookup"><span data-stu-id="578e7-140">See also</span></span>

<span data-ttu-id="578e7-141">Para obtener información acerca de otras perspectivas en el panel flujo de correo, vea [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="578e7-141">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>