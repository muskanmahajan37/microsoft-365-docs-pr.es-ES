---
title: Configurar la detección de dispositivos
description: Obtenga información sobre cómo configurar la detección de dispositivos en Microsoft 365 Defender mediante la detección básica o estándar
keywords: básico, estándar, configurar la detección de puntos de conexión, la detección de dispositivos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 0d722b4f4bef5b4d178edc5f2142c887690d4c63
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765256"
---
# <a name="configure-device-discovery"></a><span data-ttu-id="c1a37-104">Configurar la detección de dispositivos</span><span class="sxs-lookup"><span data-stu-id="c1a37-104">Configure device discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c1a37-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c1a37-105">**Applies to:**</span></span>
- [<span data-ttu-id="c1a37-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c1a37-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="c1a37-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c1a37-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="c1a37-108">La detección se puede configurar para que esté en modo estándar o básico.</span><span class="sxs-lookup"><span data-stu-id="c1a37-108">Discovery can be configured to be on standard or basic mode.</span></span> <span data-ttu-id="c1a37-109">Usa la opción estándar para buscar activamente dispositivos en tu red, lo que garantizará mejor la detección de puntos de conexión y proporcionará una clasificación de dispositivos más enriquecte.</span><span class="sxs-lookup"><span data-stu-id="c1a37-109">Use the standard option to actively find devices in your network, which will better guarantee the discovery of endpoints and provide richer device classification.</span></span> 

<span data-ttu-id="c1a37-110">Puedes personalizar la lista de dispositivos que se usan para realizar la detección estándar.</span><span class="sxs-lookup"><span data-stu-id="c1a37-110">You can customize the list of devices that are used to perform standard discovery.</span></span> <span data-ttu-id="c1a37-111">Puedes habilitar la detección estándar en todos los dispositivos incorporados que también admiten esta funcionalidad (actualmente solo dispositivos Windows 10) o seleccionar un subconjunto o subconjuntos de los dispositivos especificando sus etiquetas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c1a37-111">You can either enable standard discovery on all the onboarded devices that also support this capability (currently - Windows 10 devices only) or select a subset or subsets of your devices by specifying their device tags.</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="c1a37-112">Para obtener una vista previa, primero tendrás que activar las características de vista previa en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c1a37-112">For preview, you'll first need to turn on the Preview features in Microsoft Defender Security Center.</span></span>
> <span data-ttu-id="c1a37-113">A continuación, puedes acceder a la configuración de detección de dispositivos en el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1a37-113">You can then access the device discovery configuration in Microsoft 365 security center.</span></span> <span data-ttu-id="c1a37-114">La lista de dispositivos no administrados y recomendaciones de seguridad estará disponible tanto en el Centro de seguridad de Microsoft Defender como en el Centro de seguridad de Microsoft 365, mientras que los iconos del panel solo estarán disponibles en el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1a37-114">The list of unmanaged devices and security recommendations will be available in both Microsoft Defender Security Center and Microsoft 365 security center, while the dashboard tiles will only be available in Microsoft 365 security center.</span></span>


<span data-ttu-id="c1a37-115">Siga los siguientes pasos de configuración en el Centro de seguridad de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="c1a37-115">Take the following configuration steps in Microsoft 365 security center:</span></span>

1.  <span data-ttu-id="c1a37-116">Vaya a **Configuración > Detección de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="c1a37-116">Navigate to **Settings > Device discovery**.</span></span>
2.  <span data-ttu-id="c1a37-117">Selecciona el modo de detección que quieres usar en los dispositivos integrados.</span><span class="sxs-lookup"><span data-stu-id="c1a37-117">Select the discovery mode to use on your onboarded devices.</span></span> 
3.  <span data-ttu-id="c1a37-118">Si has seleccionado usar la detección estándar, selecciona qué dispositivos usar para el sondeo activo: todos los dispositivos o en un subconjunto especificando sus etiquetas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c1a37-118">If you've selected to use standard discovery, select which devices to use for active probing: all devices or on a subset by specifying their device tags.</span></span>
4. <span data-ttu-id="c1a37-119">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c1a37-119">Click **Save**.</span></span>


## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a><span data-ttu-id="c1a37-120">Excluir dispositivos de ser sondeados activamente en la detección estándar</span><span class="sxs-lookup"><span data-stu-id="c1a37-120">Exclude devices from being actively probed in standard discovery</span></span>
<span data-ttu-id="c1a37-121">Si hay dispositivos en la red que no deben examinarse activamente (por ejemplo, dispositivos usados como almacenes de miel para otra herramienta de seguridad), también puede definir una lista de exclusiones para evitar que se puedan examinar.</span><span class="sxs-lookup"><span data-stu-id="c1a37-121">If there are devices on your network which should not be actively scanned (for example, devices used as honeypots for another security tool), you can also define a list of exclusions to prevent them from being scanned.</span></span> <span data-ttu-id="c1a37-122">Ten en cuenta que los dispositivos aún se pueden detectar mediante el modo de detección básico.</span><span class="sxs-lookup"><span data-stu-id="c1a37-122">Note that devices can still be discovered using Basic discovery mode.</span></span> <span data-ttu-id="c1a37-123">Esos dispositivos se detectarán pasivamente, pero no se sondean activamente.</span><span class="sxs-lookup"><span data-stu-id="c1a37-123">Those devices will be passively discovered but won't be actively probed.</span></span> 

## <a name="select-networks-to-monitor"></a><span data-ttu-id="c1a37-124">Seleccionar redes para supervisar</span><span class="sxs-lookup"><span data-stu-id="c1a37-124">Select networks to monitor</span></span>
 <span data-ttu-id="c1a37-125">Microsoft Defender para endpoint analiza una red y determina si es una red corporativa que debe supervisarse o una red no corporativa que se puede ignorar.</span><span class="sxs-lookup"><span data-stu-id="c1a37-125">Microsoft Defender for Endpoint analyzes a network and determines if it is a corporate network that needs to be monitored or a non-corporate network that can be ignored.</span></span> <span data-ttu-id="c1a37-126">Las redes corporativas suelen elegirse para supervisarse.</span><span class="sxs-lookup"><span data-stu-id="c1a37-126">Corporate networks are typically chosen to be monitored.</span></span> <span data-ttu-id="c1a37-127">Sin embargo, puedes invalidar esta decisión si eliges supervisar redes no corporativas donde se encuentran dispositivos incorporados.</span><span class="sxs-lookup"><span data-stu-id="c1a37-127">However, you can override this decision by choosing to monitor non-corporate networks where onboarded devices are found.</span></span> 

<span data-ttu-id="c1a37-128">Puedes configurar dónde se puede realizar la detección de dispositivos especificando qué redes supervisar.</span><span class="sxs-lookup"><span data-stu-id="c1a37-128">You can configure where device discovery can be performed by specifying which networks to monitor.</span></span> <span data-ttu-id="c1a37-129">Cuando se supervisa una red, se puede realizar la detección de dispositivos en ella.</span><span class="sxs-lookup"><span data-stu-id="c1a37-129">When a network is monitored, device discovery can be performed on it.</span></span> 

<span data-ttu-id="c1a37-130">En la página Redes supervisadas se muestra una lista de redes en las que se puede realizar la detección **de** dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c1a37-130">A list of networks where device discovery can be performed is shown in the **Monitored networks** page.</span></span> 


>[!NOTE]
> <span data-ttu-id="c1a37-131">Solo las 50 redes principales (según el número de dispositivos asociados) estarán disponibles en la lista de red.</span><span class="sxs-lookup"><span data-stu-id="c1a37-131">Only top 50 networks (according to the number of associated devices) will be available in the network list.</span></span> 


<span data-ttu-id="c1a37-132">La lista de redes supervisadas se ordena en función del número total de dispositivos vistos en la red en los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="c1a37-132">The list of monitored networks is sorted based upon the total number of devices seen on the network in the last 7 days.</span></span>


<span data-ttu-id="c1a37-133">Puede aplicar un filtro para ver cualquiera de los siguientes estados de detección de red:</span><span class="sxs-lookup"><span data-stu-id="c1a37-133">You can apply a filter to view any of the following network discovery states:</span></span>

- <span data-ttu-id="c1a37-134">**Redes supervisadas:** redes donde se realiza la detección de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c1a37-134">**Monitored networks** - Networks where device discovery is performed.</span></span>
- <span data-ttu-id="c1a37-135">**Redes ignoradas:** se omitirá esta red y no se realizará la detección de dispositivos en ella.</span><span class="sxs-lookup"><span data-stu-id="c1a37-135">**Ignored networks** - This network will be ignored and device discovery will not be performed on it.</span></span>
- <span data-ttu-id="c1a37-136">**All:** se mostrarán las redes supervisadas e ignoradas.</span><span class="sxs-lookup"><span data-stu-id="c1a37-136">**All** - Both monitored and ignored networks will be displayed.</span></span> 


### <a name="configure-the-network-monitor-state"></a><span data-ttu-id="c1a37-137">Configurar el estado del monitor de red</span><span class="sxs-lookup"><span data-stu-id="c1a37-137">Configure the network monitor state</span></span>
<span data-ttu-id="c1a37-138">Controlas dónde se realiza la detección de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c1a37-138">You control where device discovery takes place.</span></span> <span data-ttu-id="c1a37-139">Las redes supervisadas es donde se realizará la detección de dispositivos y normalmente son redes corporativas.</span><span class="sxs-lookup"><span data-stu-id="c1a37-139">Monitored networks is where device discovery will be performed and are typically corporate networks.</span></span> <span data-ttu-id="c1a37-140">También puede elegir omitir las redes o seleccionar la clasificación de detección inicial después de modificar un estado.</span><span class="sxs-lookup"><span data-stu-id="c1a37-140">You can also choose to ignore networks or select the initial discovery classification after modifying a state.</span></span> 

<span data-ttu-id="c1a37-141">Elegir la clasificación de detección inicial significa aplicar el estado predeterminado del monitor de red hecho por el sistema.</span><span class="sxs-lookup"><span data-stu-id="c1a37-141">Choosing the initial discovery classification means applying the default system-made network monitor state.</span></span> <span data-ttu-id="c1a37-142">Seleccionar el estado predeterminado del monitor de red hecho por el sistema significa que las redes que se identificaron como corporativas, se supervisarán y las identificadas como no corporativas se omitirán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c1a37-142">Selecting the default system-made network monitor state means that networks that were identified to be corporate, will be monitored, and ones identified as non-corporate, will be ignored automatically.</span></span>
 
1. <span data-ttu-id="c1a37-143">Seleccione **Configuración > Detección de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="c1a37-143">Select **Settings > Device discovery**.</span></span>
2. <span data-ttu-id="c1a37-144">Seleccione **Redes supervisadas**.</span><span class="sxs-lookup"><span data-stu-id="c1a37-144">Select **Monitored networks**.</span></span> 
3. <span data-ttu-id="c1a37-145">Ver la lista de redes.</span><span class="sxs-lookup"><span data-stu-id="c1a37-145">View the list of networks.</span></span> 
4. <span data-ttu-id="c1a37-146">Seleccione los tres puntos junto al nombre de red.</span><span class="sxs-lookup"><span data-stu-id="c1a37-146">Select the three dots next to the network name.</span></span> 
5. <span data-ttu-id="c1a37-147">Elija si desea supervisar, omitir o usar la clasificación de detección inicial.</span><span class="sxs-lookup"><span data-stu-id="c1a37-147">Choose whether you want to monitor, ignore, or use the initial discovery classification.</span></span> 
    
    > [!WARNING]
    >- <span data-ttu-id="c1a37-148">La elección de supervisar una red que no se identificó por Microsoft Defender para Endpoint como una red corporativa puede provocar la detección de dispositivos fuera de la red corporativa y, por lo tanto, detectar dispositivos hogareños u otros dispositivos no corporativos.</span><span class="sxs-lookup"><span data-stu-id="c1a37-148">Choosing to monitor a network that was not identified by Microsoft Defender for Endpoint as a corporate network can cause device discovery outside of your corporate network, and may therefore detect home or other non-corporate devices.</span></span> 
    > - <span data-ttu-id="c1a37-149">Si se elige omitir una red, se dejará de supervisar y detectar dispositivos en esa red.</span><span class="sxs-lookup"><span data-stu-id="c1a37-149">Choosing to ignore a network will stop monitoring and discovering devices in that network.</span></span> <span data-ttu-id="c1a37-150">Los dispositivos que ya se detectaron no se quitarán del inventario, pero ya no se actualizarán y los detalles se conservarán hasta que expire el período de retención de datos de Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="c1a37-150">Devices that were already discovered will not be removed from the inventory, but will no longer be updated, and details will be retained until the data retention period of the Defender for Endpoint expires.</span></span>
    > - <span data-ttu-id="c1a37-151">Antes de elegir supervisar redes no corporativas, debe asegurarse de que tiene permiso para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="c1a37-151">Before choosing to monitor non-corporate networks, you must ensure you have permission to do so.</span></span> <br>


6. <span data-ttu-id="c1a37-152">Confirme que desea realizar el cambio.</span><span class="sxs-lookup"><span data-stu-id="c1a37-152">Confirm that you want to make the change.</span></span> 




## <a name="see-also"></a><span data-ttu-id="c1a37-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1a37-153">See also</span></span>
- [<span data-ttu-id="c1a37-154">Introducción a la detección de dispositivos</span><span class="sxs-lookup"><span data-stu-id="c1a37-154">Device discovery overview</span></span>](device-discovery.md)
- [<span data-ttu-id="c1a37-155">Preguntas frecuentes sobre detección de dispositivos</span><span class="sxs-lookup"><span data-stu-id="c1a37-155">Device discovery FAQs</span></span>](device-discovery-faq.md)