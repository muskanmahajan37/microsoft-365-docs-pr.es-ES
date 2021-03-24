---
title: Tabla AlertInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de generación de alertas en la tabla AlertInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AlertInfo, alerta, gravedad, categoría, MITRE, ATT&CK, ATP de Microsoft Defender, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS y AZURE ATP
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
ms.openlocfilehash: bc81c9c8406a6e70df6ec38e3896ef9977a120e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071643"
---
# <a name="alertinfo"></a><span data-ttu-id="4dcad-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="4dcad-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4dcad-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="4dcad-105">**Applies to:**</span></span>
- <span data-ttu-id="4dcad-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4dcad-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="4dcad-107">La tabla del esquema de búsqueda avanzada contiene información sobre alertas de `AlertInfo` Microsoft Defender para endpoint, Microsoft Defender para Office 365, Microsoft Cloud App Security y Microsoft Defender para Identity. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4dcad-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="4dcad-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="4dcad-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="4dcad-109">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="4dcad-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="4dcad-110">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="4dcad-110">Column name</span></span> | <span data-ttu-id="4dcad-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="4dcad-111">Data type</span></span> | <span data-ttu-id="4dcad-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4dcad-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="4dcad-113">datetime</span><span class="sxs-lookup"><span data-stu-id="4dcad-113">datetime</span></span> | <span data-ttu-id="4dcad-114">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="4dcad-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="4dcad-115">string</span><span class="sxs-lookup"><span data-stu-id="4dcad-115">string</span></span> | <span data-ttu-id="4dcad-116">Identificador único de alerta.</span><span class="sxs-lookup"><span data-stu-id="4dcad-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="4dcad-117">cadena</span><span class="sxs-lookup"><span data-stu-id="4dcad-117">string</span></span> | <span data-ttu-id="4dcad-118">Título de la alerta.</span><span class="sxs-lookup"><span data-stu-id="4dcad-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="4dcad-119">cadena</span><span class="sxs-lookup"><span data-stu-id="4dcad-119">string</span></span> | <span data-ttu-id="4dcad-120">Tipo de indicador de amenazas o actividad de vulneración identificada por la alerta</span><span class="sxs-lookup"><span data-stu-id="4dcad-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="4dcad-121">cadena</span><span class="sxs-lookup"><span data-stu-id="4dcad-121">string</span></span> | <span data-ttu-id="4dcad-122">El indicador de amenazas indica el posible impacto (alto, medio o bajo) de las actividades de vulneración identificadas por la alerta.</span><span class="sxs-lookup"><span data-stu-id="4dcad-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="4dcad-123">cadena</span><span class="sxs-lookup"><span data-stu-id="4dcad-123">string</span></span> | <span data-ttu-id="4dcad-124">Producto o servicio que proporcionó la información de alerta</span><span class="sxs-lookup"><span data-stu-id="4dcad-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="4dcad-125">string</span><span class="sxs-lookup"><span data-stu-id="4dcad-125">string</span></span> | <span data-ttu-id="4dcad-126">Tecnología de detección o sensor que identificó el componente o actividad notables</span><span class="sxs-lookup"><span data-stu-id="4dcad-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="4dcad-127">string</span><span class="sxs-lookup"><span data-stu-id="4dcad-127">string</span></span> | <span data-ttu-id="4dcad-128">MITRE ATT&técnicas de CK asociadas con la actividad que desencadenó la alerta</span><span class="sxs-lookup"><span data-stu-id="4dcad-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="4dcad-129">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4dcad-129">Related topics</span></span>
- [<span data-ttu-id="4dcad-130">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="4dcad-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4dcad-131">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="4dcad-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4dcad-132">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="4dcad-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="4dcad-133">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="4dcad-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="4dcad-134">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="4dcad-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4dcad-135">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="4dcad-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)