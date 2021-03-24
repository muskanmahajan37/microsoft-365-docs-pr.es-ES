---
title: Priorizar incidentes en Microsoft 365 Defender
description: Obtenga información sobre cómo filtrar incidentes de la cola de incidentes en Microsoft 365 Defender
keywords: incidente, cola, información general, dispositivos, identidades, usuarios, buzón, correo electrónico, incidentes
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0683e0f2c9f4d46b3b644e2fec882a126aaab9b9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070059"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="a20de-104">Priorizar incidentes en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a20de-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a20de-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a20de-105">**Applies to:**</span></span>
- <span data-ttu-id="a20de-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a20de-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="a20de-107">Microsoft 365 Defender aplica análisis de correlación y agrega todas las alertas e investigaciones relacionadas de diferentes productos en un solo incidente.</span><span class="sxs-lookup"><span data-stu-id="a20de-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="a20de-108">Microsoft 365 Defender también desencadena alertas únicas en actividades que solo se pueden identificar como malintencionadas dada la visibilidad de extremo a extremo que Microsoft 365 Defender tiene en toda la propiedad y conjunto de productos.</span><span class="sxs-lookup"><span data-stu-id="a20de-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="a20de-109">Esta vista proporciona a su analista de operaciones de seguridad la historia de ataques más amplia, lo que les ayuda a comprender mejor y tratar las amenazas complejas en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="a20de-109">This view gives your security operations analyst the broader attack story, which helps them better understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="a20de-110">La **cola de incidentes** muestra un conjunto de incidentes que se han marcado desde diferentes dispositivos, usuarios y buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="a20de-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="a20de-111">Le ayuda a ordenar los incidentes para asignar prioridades y crear una decisión de respuesta de ciberseguridad fundamentada.</span><span class="sxs-lookup"><span data-stu-id="a20de-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Imagen de cola de incidentes](../../media/incidents-queue.png) 

<span data-ttu-id="a20de-113">De forma predeterminada, la cola del centro de seguridad de Microsoft 365 muestra incidentes vistos en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="a20de-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="a20de-114">El incidente más reciente está en la parte superior de la lista para que pueda verlo primero.</span><span class="sxs-lookup"><span data-stu-id="a20de-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="a20de-115">La cola de incidentes expone columnas personalizables que le dan visibilidad a diferentes características del incidente o las entidades contenidas.</span><span class="sxs-lookup"><span data-stu-id="a20de-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="a20de-116">Esto le ayuda a tomar una decisión fundamentada con respecto a la priorización de los incidentes que se deben controlar.</span><span class="sxs-lookup"><span data-stu-id="a20de-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="a20de-117">Para obtener visibilidad adicional de un vistazo, la nomenclatura automática de incidentes genera nombres de incidentes basados en atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías.</span><span class="sxs-lookup"><span data-stu-id="a20de-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="a20de-118">Esto le permite comprender rápidamente el ámbito del incidente.</span><span class="sxs-lookup"><span data-stu-id="a20de-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="a20de-119">Por ejemplo: *Incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*</span><span class="sxs-lookup"><span data-stu-id="a20de-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="a20de-120">Los incidentes que existían antes de la implementación de la nomenclatura automática de incidentes no tendrán su nombre cambiado.</span><span class="sxs-lookup"><span data-stu-id="a20de-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="a20de-121">La cola de incidentes también expone varias opciones de filtrado que, cuando se aplican, le permiten realizar un amplio barrido de todos los incidentes existentes en su entorno o decidir centrarse en un escenario o amenaza específicos.</span><span class="sxs-lookup"><span data-stu-id="a20de-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="a20de-122">Aplicar filtros en la cola de incidentes puede ayudar a determinar qué incidente requiere atención inmediata.</span><span class="sxs-lookup"><span data-stu-id="a20de-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="a20de-123">Filtros disponibles</span><span class="sxs-lookup"><span data-stu-id="a20de-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="a20de-124">Asignado a</span><span class="sxs-lookup"><span data-stu-id="a20de-124">Assigned to</span></span>
<span data-ttu-id="a20de-125">Puede elegir mostrar las alertas que se le han asignado o las que controla la automatización.</span><span class="sxs-lookup"><span data-stu-id="a20de-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="a20de-126">Categories</span><span class="sxs-lookup"><span data-stu-id="a20de-126">Categories</span></span>
<span data-ttu-id="a20de-127">Elija categorías para centrarse en tácticas, técnicas o componentes de ataque específicos vistos.</span><span class="sxs-lookup"><span data-stu-id="a20de-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="a20de-128">Clasificación</span><span class="sxs-lookup"><span data-stu-id="a20de-128">Classification</span></span>
<span data-ttu-id="a20de-129">Filtrar incidentes en función de las clasificaciones establecidas de las alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="a20de-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="a20de-130">Los valores incluyen alertas verdaderas, alertas falsas o no establecidas.</span><span class="sxs-lookup"><span data-stu-id="a20de-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="a20de-131">Confidencialidad de datos</span><span class="sxs-lookup"><span data-stu-id="a20de-131">Data sensitivity</span></span>
<span data-ttu-id="a20de-132">Algunos ataques tienen por objetivo extraer datos confidenciales o importantes.</span><span class="sxs-lookup"><span data-stu-id="a20de-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="a20de-133">Al aplicar un filtro para ver si hay datos confidenciales implicados en el incidente, puede determinar rápidamente si la información confidencial se ha visto comprometida y así dar prioridad a estos incidentes.</span><span class="sxs-lookup"><span data-stu-id="a20de-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="a20de-134">Solo se aplica si se ha activado Microsoft Information Protection. </span><span class="sxs-lookup"><span data-stu-id="a20de-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="a20de-135">Grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="a20de-135">Device group</span></span>
<span data-ttu-id="a20de-136">Filtrar por grupos de dispositivos definidos.</span><span class="sxs-lookup"><span data-stu-id="a20de-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="a20de-137">Estado de investigación</span><span class="sxs-lookup"><span data-stu-id="a20de-137">Investigation state</span></span>
<span data-ttu-id="a20de-138">Filtrar incidentes por el estado de la investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="a20de-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="a20de-139">Varias categorías</span><span class="sxs-lookup"><span data-stu-id="a20de-139">Multiple categories</span></span> 
<span data-ttu-id="a20de-140">Puede elegir ver solo incidentes que se han asignado a varias categorías y, por lo tanto, puede causar más daños.</span><span class="sxs-lookup"><span data-stu-id="a20de-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="a20de-141">Múltiples orígenes del servicio</span><span class="sxs-lookup"><span data-stu-id="a20de-141">Multiple service sources</span></span> 
<span data-ttu-id="a20de-142">Filtra para ver solo incidentes que contienen alertas de diferentes orígenes (Microsoft Defender para Endpoint, Microsoft Cloud App Security, Microsoft Defender para Identity, Microsoft Defender para Office 365).</span><span class="sxs-lookup"><span data-stu-id="a20de-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="a20de-143">Plataforma del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="a20de-143">OS platform</span></span>
<span data-ttu-id="a20de-144">Limitar la vista de cola de incidentes por sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a20de-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="a20de-145">Orígenes del servicio</span><span class="sxs-lookup"><span data-stu-id="a20de-145">Service sources</span></span>
<span data-ttu-id="a20de-146">Al elegir un origen específico, puede concentrarse en los incidentes que contienen al menos una alerta del origen seleccionado.</span><span class="sxs-lookup"><span data-stu-id="a20de-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="a20de-147">Severity</span><span class="sxs-lookup"><span data-stu-id="a20de-147">Severity</span></span>
<span data-ttu-id="a20de-148">La gravedad de un incidente indica el impacto que puede tener en los activos.</span><span class="sxs-lookup"><span data-stu-id="a20de-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="a20de-149">Cuanto mayor sea la gravedad, mayor será el impacto y, por lo general, se requiere la atención más inmediata.</span><span class="sxs-lookup"><span data-stu-id="a20de-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="a20de-150">Estado</span><span class="sxs-lookup"><span data-stu-id="a20de-150">Status</span></span>
<span data-ttu-id="a20de-151">Puede limitar la lista de incidentes que se muestra en función de su estado para ver cuáles están activos o resueltos.</span><span class="sxs-lookup"><span data-stu-id="a20de-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>




## <a name="next-steps"></a><span data-ttu-id="a20de-152">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="a20de-152">Next steps</span></span>
<span data-ttu-id="a20de-153">Una vez que haya determinado qué incidente tiene mayor prioridad, puede seguir investigando.</span><span class="sxs-lookup"><span data-stu-id="a20de-153">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="a20de-154">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="a20de-154">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="a20de-155">Ver también</span><span class="sxs-lookup"><span data-stu-id="a20de-155">See also</span></span>
- [<span data-ttu-id="a20de-156">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="a20de-156">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="a20de-157">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="a20de-157">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="a20de-158">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="a20de-158">Manage incidents</span></span>](manage-incidents.md)