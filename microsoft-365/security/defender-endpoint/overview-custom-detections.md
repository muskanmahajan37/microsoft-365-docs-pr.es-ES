---
title: Información general sobre las detecciones personalizadas en ATP de Microsoft Defender
ms.reviewer: ''
description: Comprender cómo puede usar la búsqueda avanzada para crear detecciones personalizadas y generar alertas
keywords: detecciones personalizadas, alertas, reglas de detección, búsqueda avanzada, búsqueda, consulta, acciones de respuesta, intervalo, mdatp, atp de microsoft defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6c9befcc4b1224cacb2ab4eb8530e30a397aab49
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069050"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="f8e22-104">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="f8e22-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f8e22-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f8e22-105">**Applies to:**</span></span>
- [<span data-ttu-id="f8e22-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="f8e22-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="f8e22-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8e22-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f8e22-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="f8e22-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f8e22-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="f8e22-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="f8e22-110">Con las detecciones personalizadas, puede supervisar proactivamente y responder a varios eventos y estados del sistema, incluidos la actividad de infracciones sospechosas y los dispositivos mal configurados.</span><span class="sxs-lookup"><span data-stu-id="f8e22-110">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="f8e22-111">Puedes hacerlo con reglas de detección personalizables que desencadenan automáticamente alertas y acciones de respuesta.</span><span class="sxs-lookup"><span data-stu-id="f8e22-111">You can do this with customizable detection rules that automatically trigger alerts and response actions.</span></span>

<span data-ttu-id="f8e22-112">Las detecciones personalizadas funcionan [con](advanced-hunting-overview.md)búsqueda avanzada, lo que proporciona un lenguaje de consulta eficaz y flexible que cubre un amplio conjunto de información de eventos e sistema de la red.</span><span class="sxs-lookup"><span data-stu-id="f8e22-112">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="f8e22-113">Puede configurarlos para que se ejecuten a intervalos regulares, generando alertas y llevando a cabo acciones de respuesta siempre que haya coincidencias.</span><span class="sxs-lookup"><span data-stu-id="f8e22-113">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="f8e22-114">Las detecciones personalizadas proporcionan:</span><span class="sxs-lookup"><span data-stu-id="f8e22-114">Custom detections provide:</span></span>
- <span data-ttu-id="f8e22-115">Alertas para detecciones basadas en reglas creadas a partir de consultas de búsqueda avanzadas</span><span class="sxs-lookup"><span data-stu-id="f8e22-115">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="f8e22-116">Acciones de respuesta automáticas que se aplican a archivos y dispositivos</span><span class="sxs-lookup"><span data-stu-id="f8e22-116">Automatic response actions that apply to files and devices</span></span>

## <a name="related-topics"></a><span data-ttu-id="f8e22-117">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f8e22-117">Related topics</span></span>
- [<span data-ttu-id="f8e22-118">Crear reglas de detección</span><span class="sxs-lookup"><span data-stu-id="f8e22-118">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="f8e22-119">Ver y administrar reglas de detección</span><span class="sxs-lookup"><span data-stu-id="f8e22-119">View and manage detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="f8e22-120">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="f8e22-120">Advanced hunting overview</span></span>](advanced-hunting-overview.md)