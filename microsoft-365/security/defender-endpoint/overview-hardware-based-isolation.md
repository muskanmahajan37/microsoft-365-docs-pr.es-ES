---
title: Aislamiento basado en hardware (Windows 10)
ms.reviewer: ''
description: Obtén información sobre cómo el aislamiento basado en hardware en Windows 10 ayuda a combatir el malware.
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.author: macapara
ms.date: 09/07/2018
ms.technology: mde
ms.openlocfilehash: b31db39e03ed23698e71c4b38fb0937d2ba59727
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069080"
---
# <a name="hardware-based-isolation-in-windows-10"></a><span data-ttu-id="c3729-103">Aislamiento basado en hardware en Windows 10</span><span class="sxs-lookup"><span data-stu-id="c3729-103">Hardware-based isolation in Windows 10</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c3729-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c3729-104">**Applies to:**</span></span>
- [<span data-ttu-id="c3729-105">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c3729-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="c3729-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3729-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c3729-107">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="c3729-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c3729-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="c3729-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="c3729-109">El aislamiento basado en hardware ayuda a proteger la integridad del sistema en Windows 10 y se integra con Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="c3729-109">Hardware-based isolation helps protect system integrity in Windows 10 and is integrated with Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="c3729-110">Característica</span><span class="sxs-lookup"><span data-stu-id="c3729-110">Feature</span></span> | <span data-ttu-id="c3729-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3729-111">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="c3729-112">Protección de aplicaciones de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="c3729-112">Windows Defender Application Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | <span data-ttu-id="c3729-113">Protección de aplicaciones protege el dispositivo de ataques avanzados mientras te mantiene productivo.</span><span class="sxs-lookup"><span data-stu-id="c3729-113">Application Guard protects your device from advanced attacks while keeping you productive.</span></span> <span data-ttu-id="c3729-114">Con un enfoque de aislamiento basado en hardware único, el objetivo es aislar sitios web y documentos PDF que no son de confianza dentro de un contenedor ligero que está separado del sistema operativo a través del Hipervisor nativo de Windows.</span><span class="sxs-lookup"><span data-stu-id="c3729-114">Using a unique hardware-based isolation approach, the goal is to isolate untrusted websites and PDF documents inside a lightweight container that is separated from the operating system via the native Windows Hypervisor.</span></span> <span data-ttu-id="c3729-115">Si un sitio o documento PDF que no es de confianza resulta ser malintencionado, sigue estando contenido en el contenedor seguro de Application Guard, manteniendo el equipo de escritorio protegido y el atacante alejado de los datos de la empresa.</span><span class="sxs-lookup"><span data-stu-id="c3729-115">If an untrusted site or PDF document turns out to be malicious, it still remains contained within Application Guard’s secure container, keeping the desktop PC protected and the attacker away from your enterprise data.</span></span> |
| [<span data-ttu-id="c3729-116">Windows Defender System Guard</span><span class="sxs-lookup"><span data-stu-id="c3729-116">Windows Defender System Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows.md) | <span data-ttu-id="c3729-117">System Guard protege y mantiene la integridad del sistema cuando se inicia y después de que se ejecuta, y valida la integridad del sistema mediante atestación.</span><span class="sxs-lookup"><span data-stu-id="c3729-117">System Guard protects and maintains the integrity of the system as it starts and after it's running, and validates system integrity by using attestation.</span></span>  |
