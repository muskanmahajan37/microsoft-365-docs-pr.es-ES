---
title: Preguntas más frecuentes sobre detección de dispositivos
description: Buscar respuestas a preguntas más frecuentes (preguntas frecuentes) sobre la detección de dispositivos
keywords: detección de dispositivos, detección, pasiva, proactiva, red, visibilidad, servidor, estación de trabajo, incorporación, dispositivos no administrados
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
ms.openlocfilehash: b3fef3479fa2d36806e6657b31f5152c54b9251f
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765004"
---
# <a name="device-discovery-frequently-asked-questions"></a><span data-ttu-id="2d346-104">Preguntas más frecuentes sobre detección de dispositivos</span><span class="sxs-lookup"><span data-stu-id="2d346-104">Device discovery frequently asked questions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2d346-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2d346-105">**Applies to:**</span></span>
- [<span data-ttu-id="2d346-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2d346-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="2d346-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2d346-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="2d346-108">Encuentre respuestas a las preguntas más frecuentes (preguntas frecuentes) sobre la detección de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2d346-108">Find answers to frequently asked questions (FAQs) about device discovery.</span></span>

## <a name="what-is-basic-discovery-mode"></a><span data-ttu-id="2d346-109">¿Qué es el modo de detección básico?</span><span class="sxs-lookup"><span data-stu-id="2d346-109">What is Basic discovery mode?</span></span>
<span data-ttu-id="2d346-110">Este modo permite que todos los dispositivos integrados de Microsoft Defender para Endpoint recopile datos de red y detecte dispositivos vecinos.</span><span class="sxs-lookup"><span data-stu-id="2d346-110">This mode allows every Microsoft Defender for Endpoint onboarded device to collect network data and discover neighboring devices.</span></span> <span data-ttu-id="2d346-111">Los puntos de conexión incorporados recopilan eventos de la red de forma pasiva y extraen información del dispositivo de ellos.</span><span class="sxs-lookup"><span data-stu-id="2d346-111">Onboarded endpoints passively collect events in the network and extract device information from them.</span></span> <span data-ttu-id="2d346-112">No se iniciará tráfico de red.</span><span class="sxs-lookup"><span data-stu-id="2d346-112">No network traffic will be initiated.</span></span> <span data-ttu-id="2d346-113">Los puntos de conexión incorporados simplemente extraerán datos de cada tráfico de red que ve un dispositivo incorporado.</span><span class="sxs-lookup"><span data-stu-id="2d346-113">Onboarded endpoints will simply extract data from every network traffic that is seen by an onboarded device.</span></span> <span data-ttu-id="2d346-114">Estos datos se usan para enumerar dispositivos no administrados en la red.</span><span class="sxs-lookup"><span data-stu-id="2d346-114">This data used to list unmanaged devices in your network.</span></span>

## <a name="can-i-disable-basic-discovery"></a><span data-ttu-id="2d346-115">¿Puedo deshabilitar la detección básica?</span><span class="sxs-lookup"><span data-stu-id="2d346-115">Can I disable Basic discovery?</span></span>
<span data-ttu-id="2d346-116">Tienes la opción de desactivar la detección de dispositivos a través de la [página Características avanzadas.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="2d346-116">You have the option to turn off device discovery through the [Advanced features](advanced-features.md) page.</span></span> <span data-ttu-id="2d346-117">Sin embargo, perderás visibilidad en dispositivos no administrados en la red.</span><span class="sxs-lookup"><span data-stu-id="2d346-117">However, you will lose visibility on unmanaged devices in your network.</span></span> 

## <a name="what-is-standard-discovery-mode"></a><span data-ttu-id="2d346-118">¿Qué es el modo de detección estándar?</span><span class="sxs-lookup"><span data-stu-id="2d346-118">What is Standard discovery mode?</span></span>
 <span data-ttu-id="2d346-119">En este modo, los puntos de conexión incorporados a Microsoft Defender para Endpoint pueden sondear activamente los dispositivos observados en la red para enriquecer los datos recopilados (con una cantidad insignificante de tráfico de red).</span><span class="sxs-lookup"><span data-stu-id="2d346-119">In this mode endpoints onboarded to Microsoft Defender for Endpoint can actively probe observed devices in the network to enrich collected data (with negligible amount of network traffic).</span></span> <span data-ttu-id="2d346-120">Este modo es muy recomendable para crear un inventario de dispositivos confiable y coherente.</span><span class="sxs-lookup"><span data-stu-id="2d346-120">This mode is highly recommended for building a reliable and coherent device inventory.</span></span> <span data-ttu-id="2d346-121">Si decide deshabilitar este modo y seleccionar el modo de detección básico, es probable que solo obtenga una visibilidad limitada de los puntos de conexión no administrados en la red.</span><span class="sxs-lookup"><span data-stu-id="2d346-121">If you choose to disable this mode, and select Basic discovery mode, you will likely only gain limited visibility of unmanaged endpoints in your network.</span></span>

## <a name="can-i-control-which-devices-perform-standard-discovery"></a><span data-ttu-id="2d346-122">¿Puedo controlar qué dispositivos realizan la detección estándar?</span><span class="sxs-lookup"><span data-stu-id="2d346-122">Can I control which devices perform Standard discovery?</span></span>
 <span data-ttu-id="2d346-123">Puedes personalizar la lista de dispositivos que se usan para realizar la detección estándar.</span><span class="sxs-lookup"><span data-stu-id="2d346-123">You can customize the list of devices that are used to perform Standard discovery.</span></span> <span data-ttu-id="2d346-124">Puedes habilitar la detección estándar en todos los dispositivos incorporados que también admiten esta funcionalidad (actualmente solo dispositivos Windows 10) o seleccionar un subconjunto o subconjuntos de los dispositivos especificando sus etiquetas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2d346-124">You can either enable Standard discovery on all the onboarded devices that also support this capability (currently Windows 10 devices only) or select a subset or subsets of your devices by specifying their device tags.</span></span> <span data-ttu-id="2d346-125">En este caso, todos los demás dispositivos se configurarán para ejecutar solo la detección básica.</span><span class="sxs-lookup"><span data-stu-id="2d346-125">In this case, all other devices will be configured to run Basic discovery only.</span></span> <span data-ttu-id="2d346-126">La configuración está disponible en la página configuración de detección de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2d346-126">The configuration is available in the device discovery settings page.</span></span>

## <a name="which-onboarded-devices-can-perform-discovery"></a><span data-ttu-id="2d346-127">¿Qué dispositivos incorporados pueden realizar la detección?</span><span class="sxs-lookup"><span data-stu-id="2d346-127">Which onboarded devices can perform discovery?</span></span>
 <span data-ttu-id="2d346-128">Los dispositivos incorporados que se ejecutan en Windows 10 versión 1809 o posterior pueden realizar la detección.</span><span class="sxs-lookup"><span data-stu-id="2d346-128">Onboarded devices running on Windows 10 version 1809 or later can perform discovery.</span></span>

## <a name="what-happens-if-my-onboarded-devices-is-connected-to-my-home-network-or-to-public-access-point"></a><span data-ttu-id="2d346-129">¿Qué sucede si mis dispositivos incorporados están conectados a mi red doméstica o al punto de acceso público?</span><span class="sxs-lookup"><span data-stu-id="2d346-129">What happens if my onboarded devices is connected to my home network, or to public access point?</span></span>
 <span data-ttu-id="2d346-130">El motor de detección distingue entre los eventos de red que se reciben en la red corporativa frente a fuera de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="2d346-130">The discovery engine distinguishes between network events that are received in the corporate network versus outside of the corporate network.</span></span> <span data-ttu-id="2d346-131">Al correlacionar los identificadores de red entre todos los clientes del inquilino, los eventos se diferencian entre los que se recibieron de redes privadas y redes corporativas.</span><span class="sxs-lookup"><span data-stu-id="2d346-131">By correlating network identifiers across all tenant's clients, events are differentiated between ones that were received from private networks and corporate networks.</span></span> <span data-ttu-id="2d346-132">Los dispositivos de red privada no aparecerán en el inventario y no se sondearán activamente.</span><span class="sxs-lookup"><span data-stu-id="2d346-132">Private network devices will not be listed in the inventory and will not be actively probed.</span></span>

## <a name="what-protocols-are-you-capturing-and-analyzing"></a><span data-ttu-id="2d346-133">¿Qué protocolos está capturando y analizando?</span><span class="sxs-lookup"><span data-stu-id="2d346-133">What protocols are you capturing and analyzing?</span></span>
 <span data-ttu-id="2d346-134">De forma predeterminada, todos los dispositivos incorporados que se ejecutan en Windows 10 versión 1809 o posterior capturan y analizan los siguientes protocolos: ARP, CDP, DHCP, DHCPv6, IP (encabezados), LLDP, LLMNR, mDNS, MNDP, NBNS, SSDP, TCP (encabezados), UDP (encabezados), WSD</span><span class="sxs-lookup"><span data-stu-id="2d346-134">By default, all onboarded devices running on Windows 10 version 1809 or later are capturing and analyzing the following protocols: ARP, CDP, DHCP, DHCPv6, IP (headers), LLDP, LLMNR, mDNS, MNDP, NBNS, SSDP, TCP (headers), UDP (headers), WSD</span></span>

## <a name="which-protocols-do-you-use-for-active-probing-in-standard-discovery"></a><span data-ttu-id="2d346-135">¿Qué protocolos usa para el sondeo activo en la detección estándar?</span><span class="sxs-lookup"><span data-stu-id="2d346-135">Which protocols do you use for active probing in Standard discovery?</span></span>
 <span data-ttu-id="2d346-136">Cuando un dispositivo está configurado para ejecutar la detección estándar, los servicios expuestos se sondean mediante los siguientes protocolos: ARP, FTP, HTTP, ICMP, LLMNR, NBNS, RDP, SIP, SMTP, SNMP, SSH, Telnet, UPNP, WSD, SMB, NBSS, IPP, PJL</span><span class="sxs-lookup"><span data-stu-id="2d346-136">When a device is configured to run Standard discovery, exposed services are being probed by using the following protocols: ARP, FTP, HTTP, ICMP, LLMNR, NBNS, RDP, SIP, SMTP, SNMP, SSH, Telnet, UPNP, WSD, SMB, NBSS, IPP, PJL</span></span>

## <a name="how-can-i-exclude-targets-from-being-probed-with-standard-discovery"></a><span data-ttu-id="2d346-137">¿Cómo puedo excluir los destinos de ser sondeados con la detección estándar?</span><span class="sxs-lookup"><span data-stu-id="2d346-137">How can I exclude targets from being probed with Standard discovery?</span></span>
 <span data-ttu-id="2d346-138">Si hay dispositivos en la red que no deben ser sondeados activamente, también puedes definir una lista de exclusiones para evitar que se puedan examinar.</span><span class="sxs-lookup"><span data-stu-id="2d346-138">If there are devices on your network which should not be actively probed, you can also define a list of exclusions to prevent them from being scanned.</span></span> <span data-ttu-id="2d346-139">La configuración está disponible en la página configuración de detección de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2d346-139">The configuration is available in the device discovery settings page.</span></span>

## <a name="can-i-exclude-devices-from-being-discovered"></a><span data-ttu-id="2d346-140">¿Puedo excluir los dispositivos para que no se descubran?</span><span class="sxs-lookup"><span data-stu-id="2d346-140">Can I exclude devices from being discovered?</span></span>
 <span data-ttu-id="2d346-141">Como la detección de dispositivos usa métodos pasivos para detectar dispositivos en la red, cualquier dispositivo que se comunique con los dispositivos incorporados en la red corporativa se puede detectar y enumerar en el inventario.</span><span class="sxs-lookup"><span data-stu-id="2d346-141">As device discovery uses passive methods to discover devices in the network, any device that communicates with your onboarded devices in the corporate network can be discovered and listed in the inventory.</span></span> <span data-ttu-id="2d346-142">Solo puedes excluir dispositivos del sondeo activo.</span><span class="sxs-lookup"><span data-stu-id="2d346-142">You can exclude devices from active probing only.</span></span>

## <a name="how-frequent-is-the-active-probing"></a><span data-ttu-id="2d346-143">¿Qué frecuencia tiene el sondeo activo?</span><span class="sxs-lookup"><span data-stu-id="2d346-143">How frequent is the active probing?</span></span>
 <span data-ttu-id="2d346-144">Los dispositivos se sondearán activamente cuando se observan cambios en las características del dispositivo (cada 1 a 3 semanas) para asegurarse de que la información existente esté actualizada.</span><span class="sxs-lookup"><span data-stu-id="2d346-144">Devices will actively be probed when changes in device characteristics are observed (every 1 to 3 weeks) to make sure the existing information is up-to-date.</span></span>

## <a name="my-security-tool-raised-alert-on-unicastscannerps1-or-port-scanning-activity-initiated-by-it-what-should-i-do"></a><span data-ttu-id="2d346-145">Mi herramienta de seguridad ha creado una alerta UnicastScanner.ps1 actividad de detección de puertos iniciada por ella, ¿qué debo hacer?</span><span class="sxs-lookup"><span data-stu-id="2d346-145">My security tool raised alert on UnicastScanner.ps1 or port scanning activity initiated by it, what should I do?</span></span>
 <span data-ttu-id="2d346-146">Microsoft firma los scripts de sondeo activos y son seguros.</span><span class="sxs-lookup"><span data-stu-id="2d346-146">The active probing scripts are signed by Microsoft and are safe.</span></span> <span data-ttu-id="2d346-147">Puede agregar la siguiente ruta de acceso a la lista de exclusión: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`</span><span class="sxs-lookup"><span data-stu-id="2d346-147">You can add the following path to your exclusion list: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`</span></span>


## <a name="what-is-the-amount-of-traffic-being-generated-by-the-standard-discovery-active-probe"></a><span data-ttu-id="2d346-148">¿Cuál es la cantidad de tráfico que genera el sondeo activo de detección estándar?</span><span class="sxs-lookup"><span data-stu-id="2d346-148">What is the amount of traffic being generated by the Standard discovery active probe?</span></span>
 <span data-ttu-id="2d346-149">El sondeo activo puede generar hasta 5K de tráfico entre el dispositivo incorporado y el dispositivo sondeado, cada intento de sondeo</span><span class="sxs-lookup"><span data-stu-id="2d346-149">Active probing can generate up to 5K of traffic between the onboarded device and the probed device, every probing attempt</span></span>

## <a name="why-is-there-a-discrepancy-between-can-be-onboarded-devices-in-the-device-inventory-and-the-number-of-devices-to-onboard-in-the-dashboard-tile"></a><span data-ttu-id="2d346-150">¿Por qué hay una discrepancia entre los dispositivos "se pueden incorporar" en el inventario de dispositivos y el número de "dispositivos que se incorporarán" en el icono del panel?</span><span class="sxs-lookup"><span data-stu-id="2d346-150">Why is there a discrepancy between "can be onboarded" devices in the device inventory, and the number of "devices to onboard" in the dashboard tile?</span></span>
<span data-ttu-id="2d346-151">Es posible que observes diferencias entre el número de dispositivos enumerados en "se puede incorporar" en el inventario de dispositivos, la recomendación de seguridad "incorporación a Microsoft Defender para endpoint" y el widget de panel "dispositivos para incorporar".</span><span class="sxs-lookup"><span data-stu-id="2d346-151">You may notice differences between the number of listed devices under "can be onboarded" in the device inventory, "onboard to Microsoft Defender for Endpoint" security recommendation, and "devices to onboard" dashboard widget.</span></span>

 <span data-ttu-id="2d346-152">La recomendación de seguridad y el widget de panel son para dispositivos estables en la red; excluyendo dispositivos efímeros, dispositivos invitados y otros.</span><span class="sxs-lookup"><span data-stu-id="2d346-152">The security recommendation and the dashboard widget are for devices that are stable in the network; excluding ephemeral devices, guest devices and others.</span></span> <span data-ttu-id="2d346-153">La idea es recomendar en dispositivos persistentes, lo que también implica en la puntuación de seguridad general de la organización.</span><span class="sxs-lookup"><span data-stu-id="2d346-153">The idea is to recommend on persistent devices, that also imply on the overall security score of the organization.</span></span>

## <a name="can-i-onboard-unmanaged-devices-that-were-found"></a><span data-ttu-id="2d346-154">¿Puedo incorporar dispositivos no administrados que se encontraron?</span><span class="sxs-lookup"><span data-stu-id="2d346-154">Can I onboard unmanaged devices that were found?</span></span>
 <span data-ttu-id="2d346-155">Sí.</span><span class="sxs-lookup"><span data-stu-id="2d346-155">Yes.</span></span> <span data-ttu-id="2d346-156">Los puntos de conexión no administrados de la red introducen vulnerabilidades y riesgos en la red.</span><span class="sxs-lookup"><span data-stu-id="2d346-156">Unmanaged endpoints in your network introduce vulnerabilities and risks to your network.</span></span> <span data-ttu-id="2d346-157">Incorporarlos al servicio puede aumentar la visibilidad de seguridad en ellos.</span><span class="sxs-lookup"><span data-stu-id="2d346-157">Onboarding them to the service can increase the security visibility on them.</span></span> 

