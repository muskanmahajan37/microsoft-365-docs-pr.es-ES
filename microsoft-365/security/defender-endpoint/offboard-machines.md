---
title: Dispositivos offboard del servicio ATP de Microsoft Defender
description: Incorporación de dispositivos Windows 10, servidores y dispositivos que no son windows desde el servicio ATP de Microsoft Defender
keywords: offboarding, Microsoft Defender para el offboarding de puntos de conexión, windows atp offboarding
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: db22a19da58ba70ff09af781ca56e0b3c0d88dfd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069216"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="76d52-104">Dispositivos offboard del servicio Microsoft Defender para endpoints</span><span class="sxs-lookup"><span data-stu-id="76d52-104">Offboard devices from the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="76d52-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="76d52-105">**Applies to:**</span></span>
- [<span data-ttu-id="76d52-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="76d52-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="76d52-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="76d52-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="76d52-108">**Plataformas**</span><span class="sxs-lookup"><span data-stu-id="76d52-108">**Platforms**</span></span>
- <span data-ttu-id="76d52-109">macOS</span><span class="sxs-lookup"><span data-stu-id="76d52-109">macOS</span></span>
- <span data-ttu-id="76d52-110">Linux</span><span class="sxs-lookup"><span data-stu-id="76d52-110">Linux</span></span>
- <span data-ttu-id="76d52-111">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="76d52-111">Windows Server 2012 R2</span></span>
- <span data-ttu-id="76d52-112">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="76d52-112">Windows Server 2016</span></span>

><span data-ttu-id="76d52-113">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="76d52-113">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="76d52-114">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="76d52-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

<span data-ttu-id="76d52-115">Siga las instrucciones correspondientes según el método de implementación preferido.</span><span class="sxs-lookup"><span data-stu-id="76d52-115">Follow the corresponding instructions depending on your preferred deployment method.</span></span>

>[!NOTE]
> <span data-ttu-id="76d52-116">El estado de un dispositivo se cambia a [Inactivo](fix-unhealthy-sensors.md#inactive-devices) 7 días después de la salida.</span><span class="sxs-lookup"><span data-stu-id="76d52-116">The status of a device will be switched to [Inactive](fix-unhealthy-sensors.md#inactive-devices) 7 days after offboarding.</span></span> <br> <span data-ttu-id="76d52-117">Los datos de los dispositivos no incluidos (como escala de tiempo, alertas, vulnerabilidades, etc.) permanecerán en el portal hasta que expire el período [de](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) retención configurado.</span><span class="sxs-lookup"><span data-stu-id="76d52-117">Offboarded devices' data (such as Timeline, Alerts, Vulnerabilities, etc.) will remain in the portal until the configured [retention period](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) expires.</span></span> <br>
> <span data-ttu-id="76d52-118">El perfil del dispositivo (sin datos) [](machines-view-overview.md) permanecerá en la lista de dispositivos durante no más de 180 días.</span><span class="sxs-lookup"><span data-stu-id="76d52-118">The device's profile (without data) will remain in the [Devices List](machines-view-overview.md) for no longer than 180 days.</span></span>
> <span data-ttu-id="76d52-119">Además, los dispositivos que no están activos en los últimos 30 días no se tienen [](tvm-exposure-score.md) en cuenta en los datos que reflejan la puntuación de exposición a la administración de amenazas y vulnerabilidades de la organización y la puntuación de Microsoft Secure Score para dispositivos.</span><span class="sxs-lookup"><span data-stu-id="76d52-119">In addition, devices that are not active in the last 30 days are not factored in on the data that reflects your organization's threat and vulnerability management [exposure score](tvm-exposure-score.md) and Microsoft Secure Score for Devices.</span></span> <br>
> <span data-ttu-id="76d52-120">Para ver solo los dispositivos activos, puede filtrar por estado [de](machines-view-overview.md#health-state)mantenimiento, [etiquetas de dispositivo](machine-tags.md) o grupos de [máquinas.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="76d52-120">To view only active devices, you can filter by [health state](machines-view-overview.md#health-state), [device tags](machine-tags.md) or [machine groups](machine-groups.md).</span></span> 

## <a name="offboard-windows-10-devices"></a><span data-ttu-id="76d52-121">Dispositivos con Windows 10 fuera de la pantalla</span><span class="sxs-lookup"><span data-stu-id="76d52-121">Offboard Windows 10 devices</span></span>
- [<span data-ttu-id="76d52-122">Dispositivos offboard con un script local</span><span class="sxs-lookup"><span data-stu-id="76d52-122">Offboard devices using a local script</span></span>](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [<span data-ttu-id="76d52-123">Dispositivos offboard con directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="76d52-123">Offboard devices using Group Policy</span></span>](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [<span data-ttu-id="76d52-124">Dispositivos offboard con herramientas de administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="76d52-124">Offboard devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a><span data-ttu-id="76d52-125">Servidores offboard</span><span class="sxs-lookup"><span data-stu-id="76d52-125">Offboard Servers</span></span>
- [<span data-ttu-id="76d52-126">Servidores offboard</span><span class="sxs-lookup"><span data-stu-id="76d52-126">Offboard servers</span></span>](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="76d52-127">Dispositivos offboard que no son Windows</span><span class="sxs-lookup"><span data-stu-id="76d52-127">Offboard non-Windows devices</span></span>
- [<span data-ttu-id="76d52-128">Dispositivos offboard que no son Windows</span><span class="sxs-lookup"><span data-stu-id="76d52-128">Offboard non-Windows devices</span></span>](configure-endpoints-non-windows.md#offboard-non-windows-devices)
