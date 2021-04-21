---
title: Habilitar y configurar las características de protección antivirus de Microsoft Defender
description: Habilite la protección heurística, heurística y en tiempo real en av. de Microsoft Defender.
keywords: heuristic, machine-learning, behavior monitor, real-time protection, always-on, Microsoft Defender Antivirus, antimalware, security, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 9fc51682b659670a21c3c293ea8996beb228802a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765076"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a><span data-ttu-id="2ac06-104">Configurar la protección de comportamiento, heurística y en tiempo real</span><span class="sxs-lookup"><span data-stu-id="2ac06-104">Configure behavioral, heuristic, and real-time protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2ac06-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2ac06-105">**Applies to:**</span></span>

- [<span data-ttu-id="2ac06-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2ac06-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="2ac06-107">Antivirus de Microsoft Defender usa varios métodos para proporcionar protección contra amenazas:</span><span class="sxs-lookup"><span data-stu-id="2ac06-107">Microsoft Defender Antivirus uses several methods to provide threat protection:</span></span>

- <span data-ttu-id="2ac06-108">Protección entregada en la nube para la detección casi instantánea y el bloqueo de amenazas nuevas y emergentes</span><span class="sxs-lookup"><span data-stu-id="2ac06-108">Cloud-delivered protection for near-instant detection and blocking of new and emerging threats</span></span>
- <span data-ttu-id="2ac06-109">Análisis siempre en tiempo real, con supervisión del comportamiento de archivos y procesos y otra heurística (también conocida como "protección en tiempo real")</span><span class="sxs-lookup"><span data-stu-id="2ac06-109">Always-on scanning, using file and process behavior monitoring and other heuristics (also known as "real-time protection")</span></span>
- <span data-ttu-id="2ac06-110">Actualizaciones de protección dedicadas que se basan en el aprendizaje automático, los análisis humanos y automatizados de macrodatos y el estudio detallado de la resistencia ante amenazas.</span><span class="sxs-lookup"><span data-stu-id="2ac06-110">Dedicated protection updates based on machine-learning, human and automated big-data analysis, and in-depth threat resistance research</span></span>

<span data-ttu-id="2ac06-111">Puede configurar el modo en que Antivirus de Microsoft Defender usa estos métodos con la directiva de grupo, administración de configuración de System Center, cmdlets de PowerShell e Instrumental de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="2ac06-111">You can configure how Microsoft Defender Antivirus uses these methods with Group Policy, System Center Configuration Manage, PowerShell cmdlets, and Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="2ac06-112">En esta sección se describe la configuración del análisis siempre en marcha, incluido cómo detectar y bloquear aplicaciones que se consideran no seguras, pero que no se pueden detectar como malware.</span><span class="sxs-lookup"><span data-stu-id="2ac06-112">This section covers configuration for always-on scanning, including how to detect and block apps that are deemed unsafe, but may not be detected as malware.</span></span>

<span data-ttu-id="2ac06-113">Consulta [Usar tecnologías antivirus](cloud-protection-microsoft-defender-antivirus.md) de Microsoft Defender de última generación a través de la protección entregada en la nube para obtener información sobre cómo habilitar y configurar la protección en la nube de Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="2ac06-113">See [Use next-gen Microsoft Defender Antivirus technologies through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for how to enable and configure Microsoft Defender Antivirus cloud-delivered protection.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2ac06-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2ac06-114">In this section</span></span>

 <span data-ttu-id="2ac06-115">Tema</span><span class="sxs-lookup"><span data-stu-id="2ac06-115">Topic</span></span> | <span data-ttu-id="2ac06-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ac06-116">Description</span></span>
---|---
[<span data-ttu-id="2ac06-117">Detectar y bloquear aplicaciones potencialmente no deseadas</span><span class="sxs-lookup"><span data-stu-id="2ac06-117">Detect and block potentially unwanted applications</span></span>](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | <span data-ttu-id="2ac06-118">Detectar y bloquear aplicaciones que pueden no ser deseadas en la red, como el software publicitario, modificadores de explorador y barras de herramientas, y aplicaciones antivirus falsas o falsas</span><span class="sxs-lookup"><span data-stu-id="2ac06-118">Detect and block apps that may be unwanted in your network, such as adware, browser modifiers and toolbars, and rogue or fake antivirus apps</span></span>
[<span data-ttu-id="2ac06-119">Habilitar y configurar las capacidades de protección de Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2ac06-119">Enable and configure Microsoft Defender Antivirus protection capabilities</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md) | <span data-ttu-id="2ac06-120">Habilitar y configurar la protección en tiempo real, la heurística y otras características de supervisión de Antivirus de Microsoft Defender siempre activas</span><span class="sxs-lookup"><span data-stu-id="2ac06-120">Enable and configure real-time protection, heuristics, and other always-on Microsoft Defender Antivirus monitoring features</span></span>