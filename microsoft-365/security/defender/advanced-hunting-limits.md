---
title: Cuotas de búsqueda avanzadas y parámetros de uso en Microsoft 365 Defender
description: Comprender varias cuotas y parámetros de uso (límites de servicio) que mantienen la capacidad de respuesta del servicio de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, esquema, kusto, límite de CPU, límite de consulta, recursos, resultados máximos, cuota, parámetros, asignación
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 19606b06ff1a1369614bab533a949bc383c90ad3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072771"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="1a213-104">Cuotas de búsqueda avanzada y parámetros de uso</span><span class="sxs-lookup"><span data-stu-id="1a213-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1a213-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="1a213-105">**Applies to:**</span></span>
- <span data-ttu-id="1a213-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1a213-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1a213-107">Para mantener el servicio con rendimiento y capacidad de respuesta, la búsqueda avanzada establece varias cuotas y parámetros de uso (también conocidos como "límites de servicio").</span><span class="sxs-lookup"><span data-stu-id="1a213-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="1a213-108">Estas cuotas y parámetros se aplican a las consultas que se ejecutan manualmente y mediante reglas [de detección personalizadas.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="1a213-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="1a213-109">Los clientes que ejecutan varias consultas con regularidad deben realizar un seguimiento del consumo y aplicar los [procedimientos recomendados de optimización](advanced-hunting-best-practices.md) para minimizar las interrupciones.</span><span class="sxs-lookup"><span data-stu-id="1a213-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="1a213-110">Consulte la tabla siguiente para comprender las cuotas existentes y los parámetros de uso.</span><span class="sxs-lookup"><span data-stu-id="1a213-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="1a213-111">Cuota o parámetro</span><span class="sxs-lookup"><span data-stu-id="1a213-111">Quota or parameter</span></span> | <span data-ttu-id="1a213-112">Size</span><span class="sxs-lookup"><span data-stu-id="1a213-112">Size</span></span> | <span data-ttu-id="1a213-113">Ciclo de actualización</span><span class="sxs-lookup"><span data-stu-id="1a213-113">Refresh cycle</span></span> | <span data-ttu-id="1a213-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="1a213-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="1a213-115">Rango de datos</span><span class="sxs-lookup"><span data-stu-id="1a213-115">Data range</span></span> | <span data-ttu-id="1a213-116">30 días</span><span class="sxs-lookup"><span data-stu-id="1a213-116">30 days</span></span> | <span data-ttu-id="1a213-117">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="1a213-117">Every query</span></span> | <span data-ttu-id="1a213-118">Cada consulta puede buscar datos desde los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="1a213-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="1a213-119">Conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="1a213-119">Result set</span></span> | <span data-ttu-id="1a213-120">10.000 filas</span><span class="sxs-lookup"><span data-stu-id="1a213-120">10,000 rows</span></span> | <span data-ttu-id="1a213-121">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="1a213-121">Every query</span></span> | <span data-ttu-id="1a213-122">Cada consulta puede devolver hasta 10 000 registros.</span><span class="sxs-lookup"><span data-stu-id="1a213-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="1a213-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="1a213-123">Timeout</span></span> | <span data-ttu-id="1a213-124">10 minutos</span><span class="sxs-lookup"><span data-stu-id="1a213-124">10 minutes</span></span> | <span data-ttu-id="1a213-125">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="1a213-125">Every query</span></span> | <span data-ttu-id="1a213-126">Cada consulta puede ejecutarse durante un máximo de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="1a213-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="1a213-127">Si no se completa en 10 minutos, el servicio muestra un error.</span><span class="sxs-lookup"><span data-stu-id="1a213-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="1a213-128">Recursos de CPU</span><span class="sxs-lookup"><span data-stu-id="1a213-128">CPU resources</span></span> | <span data-ttu-id="1a213-129">En función del tamaño del espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="1a213-129">Based on tenant size</span></span> | <span data-ttu-id="1a213-130">- En la hora y, a continuación, cada 15 minutos</span><span class="sxs-lookup"><span data-stu-id="1a213-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="1a213-131">- Diario a las 12 medianoche</span><span class="sxs-lookup"><span data-stu-id="1a213-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="1a213-132">El servicio aplica la cuota diaria y la cuota de 15 minutos por separado.</span><span class="sxs-lookup"><span data-stu-id="1a213-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="1a213-133">Por cada cuota, el [portal muestra](advanced-hunting-errors.md) un error cada vez que se ejecuta una consulta y el inquilino ha consumido más del 10 % de los recursos asignados.</span><span class="sxs-lookup"><span data-stu-id="1a213-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="1a213-134">Las consultas se bloquean si el inquilino ha alcanzado el 100 % hasta después del siguiente ciclo diario o de 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="1a213-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="1a213-135">Se aplica un conjunto independiente de cuotas y parámetros a las consultas de búsqueda avanzadas realizadas a través de la API.</span><span class="sxs-lookup"><span data-stu-id="1a213-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="1a213-136">Leer acerca de las API de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="1a213-136">Read about advanced hunting APIs</span></span>](./api-advanced-hunting.md)

## <a name="related-topics"></a><span data-ttu-id="1a213-137">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1a213-137">Related topics</span></span>

- [<span data-ttu-id="1a213-138">Procedimientos recomendados de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="1a213-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="1a213-139">Controlar errores de búsqueda avanzados</span><span class="sxs-lookup"><span data-stu-id="1a213-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="1a213-140">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="1a213-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1a213-141">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="1a213-141">Custom detections overview</span></span>](custom-detections-overview.md)