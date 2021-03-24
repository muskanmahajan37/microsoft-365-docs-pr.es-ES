---
title: McAfee to Microsoft Defender for Endpoint - Prepare
description: Esta es la fase 1, Preparar, para migrar de McAfee a ATP de Microsoft Defender.
keywords: migración, protección contra amenazas avanzada de Windows Defender, atp, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-mcafeemigrate
- m365solution-scenario
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: c87ed20dd1d0c959a9af52fd766d0a34232747b2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069672"
---
# <a name="migrate-from-mcafee---phase-1-prepare-for-your-migration"></a><span data-ttu-id="7e348-104">Migrar desde McAfee: fase 1: preparar la migración</span><span class="sxs-lookup"><span data-stu-id="7e348-104">Migrate from McAfee - Phase 1: Prepare for your migration</span></span>

<span data-ttu-id="7e348-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7e348-105">**Applies to:**</span></span>
- [<span data-ttu-id="7e348-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="7e348-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="7e348-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7e348-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

|![Fase 1: Preparar](images/phase-diagrams/prepare.png)<br/><span data-ttu-id="7e348-109">Fase 1: Preparar</span><span class="sxs-lookup"><span data-stu-id="7e348-109">Phase 1: Prepare</span></span> |<span data-ttu-id="7e348-110">[![Fase 2: Configurar](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)</span><span class="sxs-lookup"><span data-stu-id="7e348-110">[![Phase 2: Set up](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)</span></span><br/>[<span data-ttu-id="7e348-111">Fase 2: Configurar</span><span class="sxs-lookup"><span data-stu-id="7e348-111">Phase 2: Set up</span></span>](mcafee-to-microsoft-defender-setup.md) |<span data-ttu-id="7e348-112">[![Fase 3: Incorporación](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)</span><span class="sxs-lookup"><span data-stu-id="7e348-112">[![Phase 3: Onboard](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)</span></span><br/>[<span data-ttu-id="7e348-113">Fase 3: Incorporación</span><span class="sxs-lookup"><span data-stu-id="7e348-113">Phase 3: Onboard</span></span>](mcafee-to-microsoft-defender-onboard.md) |
|--|--|--|
|<span data-ttu-id="7e348-114">*¡Estás aquí!*</span><span class="sxs-lookup"><span data-stu-id="7e348-114">*You are here!*</span></span>| | |


<span data-ttu-id="7e348-115">**Bienvenido a la fase de preparación de [la migración de McAfee Endpoint Security (McAfee) a Microsoft Defender para Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)**.</span><span class="sxs-lookup"><span data-stu-id="7e348-115">**Welcome to the Prepare phase of [migrating from McAfee Endpoint Security (McAfee) to Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)**.</span></span> 

<span data-ttu-id="7e348-116">Esta fase de migración incluye los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="7e348-116">This migration phase includes the following steps:</span></span>
1. [<span data-ttu-id="7e348-117">Obtener e implementar actualizaciones en los dispositivos de la organización</span><span class="sxs-lookup"><span data-stu-id="7e348-117">Get and deploy updates across your organization's devices</span></span>](#get-and-deploy-updates-across-your-organizations-devices)
2. <span data-ttu-id="7e348-118">[Obtener Microsoft Defender para endpoint](#get-microsoft-defender-for-endpoint).</span><span class="sxs-lookup"><span data-stu-id="7e348-118">[Get Microsoft Defender for Endpoint](#get-microsoft-defender-for-endpoint).</span></span>
3. <span data-ttu-id="7e348-119">[Conceder acceso al Centro de seguridad de Microsoft Defender](#grant-access-to-the-microsoft-defender-security-center).</span><span class="sxs-lookup"><span data-stu-id="7e348-119">[Grant access to the Microsoft Defender Security Center](#grant-access-to-the-microsoft-defender-security-center).</span></span>
4. <span data-ttu-id="7e348-120">[Configurar el proxy de dispositivo y la configuración de conectividad a Internet.](#configure-device-proxy-and-internet-connectivity-settings)</span><span class="sxs-lookup"><span data-stu-id="7e348-120">[Configure device proxy and internet connectivity settings](#configure-device-proxy-and-internet-connectivity-settings).</span></span>

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a><span data-ttu-id="7e348-121">Obtener e implementar actualizaciones en los dispositivos de la organización</span><span class="sxs-lookup"><span data-stu-id="7e348-121">Get and deploy updates across your organization's devices</span></span>

<span data-ttu-id="7e348-122">Como práctica recomendada, mantenga actualizados los dispositivos y los puntos de conexión de la organización.</span><span class="sxs-lookup"><span data-stu-id="7e348-122">As a best practice, keep your organization's devices and endpoints up to date.</span></span> <span data-ttu-id="7e348-123">Asegúrese de que la solución de McAfee Endpoint Security (McAfee) esté actualizada y de que los sistemas operativos y las aplicaciones de su organización también tengan las actualizaciones más recientes.</span><span class="sxs-lookup"><span data-stu-id="7e348-123">Make sure your McAfee Endpoint Security (McAfee) solution is up to date, and that the operating systems and apps your organization is also have the latest updates.</span></span> <span data-ttu-id="7e348-124">Hacerlo ahora puede ayudar a evitar problemas más adelante a medida que migras a Microsoft Defender para Endpoint y Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="7e348-124">Doing this now can help prevent problems later as you migrate to Microsoft Defender for Endpoint and Microsoft Defender Antivirus.</span></span>

### <a name="make-sure-your-mcafee-solution-is-up-to-date"></a><span data-ttu-id="7e348-125">Asegúrese de que la solución de McAfee esté actualizada</span><span class="sxs-lookup"><span data-stu-id="7e348-125">Make sure your McAfee solution is up to date</span></span>

<span data-ttu-id="7e348-126">Mantenga McAfee actualizado y asegúrese de que los dispositivos de su organización tienen las actualizaciones de seguridad más recientes.</span><span class="sxs-lookup"><span data-stu-id="7e348-126">Keep McAfee up to date, and make sure that your organization's devices have the latest security updates.</span></span> <span data-ttu-id="7e348-127">¿Necesita ayuda?</span><span class="sxs-lookup"><span data-stu-id="7e348-127">Need help?</span></span> <span data-ttu-id="7e348-128">Estos son algunos recursos de McAfee:</span><span class="sxs-lookup"><span data-stu-id="7e348-128">Here are some McAfee resources:</span></span>

- [<span data-ttu-id="7e348-129">Documentación del producto de McAfee Enterprise: cómo funciona Endpoint Security</span><span class="sxs-lookup"><span data-stu-id="7e348-129">McAfee Enterprise Product Documentation: How Endpoint Security Works</span></span>](https://docs.mcafee.com/bundle/endpoint-security-10.7.x-common-product-guide-windows/page/GUID-1207FF39-D1D2-481F-BBD9-E4079112A8DD.html)

- [<span data-ttu-id="7e348-130">Artículo técnico de McAfee Knowledge Center: Windows Security Center informa de forma incorrecta de que Endpoint Security está deshabilitado al ejecutarse en Windows 10</span><span class="sxs-lookup"><span data-stu-id="7e348-130">McAfee Knowledge Center Technical Article: Windows Security Center intermittently incorrectly reports that Endpoint Security is disabled when running on Windows 10</span></span>](https://kc.mcafee.com/corporate/index?page=content&id=KB91830) 

- [<span data-ttu-id="7e348-131">Artículo técnico de McAfee Knowledge Center: Windows Security Center informa de que Endpoint Security está deshabilitado cuando se ejecuta Endpoint Security</span><span class="sxs-lookup"><span data-stu-id="7e348-131">McAfee Knowledge Center Technical Article: Windows Security Center reports Endpoint Security is disabled when Endpoint Security is running</span></span>](https://kc.mcafee.com/corporate/index?page=content&id=KB91428)

- <span data-ttu-id="7e348-132">Su soporte técnico de McAfee ServicePortal ( [http://mysupport.mcafee.com](http://mysupport.mcafee.com) )</span><span class="sxs-lookup"><span data-stu-id="7e348-132">Your McAfee support ServicePortal ([http://mysupport.mcafee.com](http://mysupport.mcafee.com))</span></span>

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a><span data-ttu-id="7e348-133">Asegúrese de que los dispositivos de su organización estén actualizados</span><span class="sxs-lookup"><span data-stu-id="7e348-133">Make sure your organization's devices are up to date</span></span>

<span data-ttu-id="7e348-134">¿Necesita ayuda para actualizar los dispositivos de su organización?</span><span class="sxs-lookup"><span data-stu-id="7e348-134">Need help updating your organization's devices?</span></span> <span data-ttu-id="7e348-135">Vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="7e348-135">See the following resources:</span></span>

|<span data-ttu-id="7e348-136">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="7e348-136">OS</span></span> | <span data-ttu-id="7e348-137">Resource</span><span class="sxs-lookup"><span data-stu-id="7e348-137">Resource</span></span> |
|:--|:--|
|<span data-ttu-id="7e348-138">Windows</span><span class="sxs-lookup"><span data-stu-id="7e348-138">Windows</span></span> |[<span data-ttu-id="7e348-139">Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="7e348-139">Microsoft Update</span></span>](https://www.update.microsoft.com) |
|<span data-ttu-id="7e348-140">macOS</span><span class="sxs-lookup"><span data-stu-id="7e348-140">macOS</span></span> | [<span data-ttu-id="7e348-141">Cómo actualizar el software en tu Mac</span><span class="sxs-lookup"><span data-stu-id="7e348-141">How to update the software on your Mac</span></span>](https://support.apple.com/HT201541)|
|<span data-ttu-id="7e348-142">iOS</span><span class="sxs-lookup"><span data-stu-id="7e348-142">iOS</span></span> |[<span data-ttu-id="7e348-143">Actualizar el iPhone, iPad o iPod touch</span><span class="sxs-lookup"><span data-stu-id="7e348-143">Update your iPhone, iPad, or iPod touch</span></span>](https://support.apple.com/HT204204)|
|<span data-ttu-id="7e348-144">Android</span><span class="sxs-lookup"><span data-stu-id="7e348-144">Android</span></span> |[<span data-ttu-id="7e348-145">Comprobar & actualizar la versión de Android</span><span class="sxs-lookup"><span data-stu-id="7e348-145">Check & update your Android version</span></span>](https://support.google.com/android/answer/7680439) |
|<span data-ttu-id="7e348-146">Linux</span><span class="sxs-lookup"><span data-stu-id="7e348-146">Linux</span></span> | [<span data-ttu-id="7e348-147">Linux 101: actualizar el sistema</span><span class="sxs-lookup"><span data-stu-id="7e348-147">Linux 101: Updating Your System</span></span>](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a><span data-ttu-id="7e348-148">Obtener Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="7e348-148">Get Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="7e348-149">Ahora que ha actualizado los dispositivos de su organización, el siguiente paso es obtener Microsoft Defender para Endpoint, asignar licencias y asegurarse de que el servicio está aprovisionado.</span><span class="sxs-lookup"><span data-stu-id="7e348-149">Now that you've updated your organization's devices, the next step is to get Microsoft Defender for Endpoint, assign licenses, and make sure the service is provisioned.</span></span>

1. <span data-ttu-id="7e348-150">Compre o pruebe Microsoft Defender para Endpoint hoy mismo.</span><span class="sxs-lookup"><span data-stu-id="7e348-150">Buy or try Microsoft Defender for Endpoint today.</span></span> <span data-ttu-id="7e348-151">[Inicie una prueba gratuita o solicite una cotización](https://aka.ms/mdatp).</span><span class="sxs-lookup"><span data-stu-id="7e348-151">[Start a free trial or request a quote](https://aka.ms/mdatp).</span></span> 

2. <span data-ttu-id="7e348-152">Compruebe que las licencias están aprovisionadas correctamente.</span><span class="sxs-lookup"><span data-stu-id="7e348-152">Verify that your licenses are properly provisioned.</span></span> <span data-ttu-id="7e348-153">[Compruebe el estado de la licencia](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#check-license-state).</span><span class="sxs-lookup"><span data-stu-id="7e348-153">[Check your license state](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#check-license-state).</span></span>

3. <span data-ttu-id="7e348-154">Como administrador global o administrador de seguridad, configura la instancia de nube dedicada de Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="7e348-154">As a global administrator or security administrator, set up your dedicated cloud instance of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="7e348-155">Consulte [Configuración del punto de conexión de Microsoft Defender: Configuración del espacio empresarial](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#tenant-configuration).</span><span class="sxs-lookup"><span data-stu-id="7e348-155">See [Microsoft Defender for Endpoint setup: Tenant configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#tenant-configuration).</span></span>

4. <span data-ttu-id="7e348-156">Si los puntos de conexión (como dispositivos) de su organización usan un proxy para tener acceso a Internet, consulte Configuración de [Microsoft Defender para extremo: Configuración de red](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#network-configuration).</span><span class="sxs-lookup"><span data-stu-id="7e348-156">If endpoints (such as devices) in your organization use a proxy to access the internet, see [Microsoft Defender for Endpoint setup: Network configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#network-configuration).</span></span>
 
<span data-ttu-id="7e348-157">En este momento, está listo para conceder acceso a los administradores de seguridad y operadores de seguridad que usarán el Centro de seguridad de Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).</span><span class="sxs-lookup"><span data-stu-id="7e348-157">At this point, you are ready to grant access to your security administrators and security operators who will use the Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)).</span></span> 

> [!NOTE]
> <span data-ttu-id="7e348-158">El Centro de seguridad de Microsoft Defender a veces se conoce como el portal de Microsoft Defender para endpoints.</span><span class="sxs-lookup"><span data-stu-id="7e348-158">The Microsoft Defender Security Center is sometimes referred to as the Microsoft Defender for Endpoint portal.</span></span> 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a><span data-ttu-id="7e348-159">Conceder acceso al Centro de seguridad de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7e348-159">Grant access to the Microsoft Defender Security Center</span></span>

<span data-ttu-id="7e348-160">El Centro de seguridad de Microsoft Defender ( ) es donde tiene acceso y configura las características y [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) capacidades de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="7e348-160">The Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) is where you access and configure features and capabilities of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="7e348-161">Para obtener más información, vea [Overview of the Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use).</span><span class="sxs-lookup"><span data-stu-id="7e348-161">To learn more, see [Overview of the Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use).</span></span>

<span data-ttu-id="7e348-162">Los permisos del Centro de seguridad de Microsoft Defender se pueden conceder mediante permisos básicos o control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="7e348-162">Permissions to the Microsoft Defender Security Center can be granted by using either basic permissions or role-based access control (RBAC).</span></span> <span data-ttu-id="7e348-163">Se recomienda usar RBAC para que tenga un control más detallado sobre los permisos.</span><span class="sxs-lookup"><span data-stu-id="7e348-163">We recommend using RBAC so that you have more granular control over permissions.</span></span>

1. <span data-ttu-id="7e348-164">Planee los roles y permisos para los administradores de seguridad y los operadores de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7e348-164">Plan the roles and permissions for your security administrators and security operators.</span></span> <span data-ttu-id="7e348-165">Vea [Control de acceso basado en roles](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/prepare-deployment#role-based-access-control).</span><span class="sxs-lookup"><span data-stu-id="7e348-165">See [Role-based access control](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/prepare-deployment#role-based-access-control).</span></span>

2. <span data-ttu-id="7e348-166">Configurar y configurar RBAC.</span><span class="sxs-lookup"><span data-stu-id="7e348-166">Set up and configure RBAC.</span></span> <span data-ttu-id="7e348-167">Se recomienda usar [Intune para](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) configurar RBAC, especialmente si su organización usa una combinación de dispositivos Windows 10, macOS, iOS y Android.</span><span class="sxs-lookup"><span data-stu-id="7e348-167">We recommend using [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) to configure RBAC, especially if your organization is using a combination of Windows 10, macOS, iOS, and Android devices.</span></span> <span data-ttu-id="7e348-168">Consulta [configurar RBAC con Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).</span><span class="sxs-lookup"><span data-stu-id="7e348-168">See [setting up RBAC using Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).</span></span>

    <span data-ttu-id="7e348-169">Si su organización requiere un método distinto de Intune, elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="7e348-169">If your organization requires a method other than Intune, choose one of the following options:</span></span>
    - [<span data-ttu-id="7e348-170">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7e348-170">Configuration Manager</span></span>](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [<span data-ttu-id="7e348-171">Administración de directivas de grupo avanzadas</span><span class="sxs-lookup"><span data-stu-id="7e348-171">Advanced Group Policy Management</span></span>](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm)
    - [<span data-ttu-id="7e348-172">Centro de administración de Windows</span><span class="sxs-lookup"><span data-stu-id="7e348-172">Windows Admin Center</span></span>](https://docs.microsoft.com/windows-server/manage/windows-admin-center/overview)

3. <span data-ttu-id="7e348-173">Conceder acceso al Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="7e348-173">Grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="7e348-174">(¿Necesita ayuda?</span><span class="sxs-lookup"><span data-stu-id="7e348-174">(Need help?</span></span> <span data-ttu-id="7e348-175">Consulte [Manage portal access using RBAC](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)).</span><span class="sxs-lookup"><span data-stu-id="7e348-175">See [Manage portal access using RBAC](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)).</span></span>

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="7e348-176">Configurar el proxy de dispositivo y la configuración de conectividad a Internet</span><span class="sxs-lookup"><span data-stu-id="7e348-176">Configure device proxy and internet connectivity settings</span></span>

<span data-ttu-id="7e348-177">Para habilitar la comunicación entre los dispositivos y Microsoft Defender para endpoint, configure la configuración de proxy e Internet.</span><span class="sxs-lookup"><span data-stu-id="7e348-177">To enable communication between your devices and Microsoft Defender for Endpoint, configure proxy and internet settings.</span></span> <span data-ttu-id="7e348-178">En la tabla siguiente se incluyen vínculos a los recursos que puede usar para configurar el proxy y la configuración de Internet para varios sistemas operativos y capacidades:</span><span class="sxs-lookup"><span data-stu-id="7e348-178">The following table includes links to resources you can use to configure your proxy and internet settings for various operating systems and capabilities:</span></span>

|<span data-ttu-id="7e348-179">Capacidades</span><span class="sxs-lookup"><span data-stu-id="7e348-179">Capabilities</span></span>  | <span data-ttu-id="7e348-180">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="7e348-180">Operating System</span></span> | <span data-ttu-id="7e348-181">Recursos</span><span class="sxs-lookup"><span data-stu-id="7e348-181">Resources</span></span> |
|--|--|--|
|<span data-ttu-id="7e348-182">[Detección y respuesta de extremos](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR)</span><span class="sxs-lookup"><span data-stu-id="7e348-182">[Endpoint detection and response](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR)</span></span> |<span data-ttu-id="7e348-183">- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information)</span><span class="sxs-lookup"><span data-stu-id="7e348-183">- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information)</span></span> <br/><span data-ttu-id="7e348-184">- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)</span><span class="sxs-lookup"><span data-stu-id="7e348-184">- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)</span></span><br/><span data-ttu-id="7e348-185">- [Windows Server 1803 o posterior](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)</span><span class="sxs-lookup"><span data-stu-id="7e348-185">- [Windows Server 1803 or later](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)</span></span>  |[<span data-ttu-id="7e348-186">Configurar el proxy de máquina y la configuración de conectividad a Internet</span><span class="sxs-lookup"><span data-stu-id="7e348-186">Configure machine proxy and internet connectivity settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet) |
|<span data-ttu-id="7e348-187">EDR</span><span class="sxs-lookup"><span data-stu-id="7e348-187">EDR</span></span> |<span data-ttu-id="7e348-188">- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016)</span><span class="sxs-lookup"><span data-stu-id="7e348-188">- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016)</span></span> <br/><span data-ttu-id="7e348-189">- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)</span><span class="sxs-lookup"><span data-stu-id="7e348-189">- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)</span></span><br/><span data-ttu-id="7e348-190">- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)</span><span class="sxs-lookup"><span data-stu-id="7e348-190">- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)</span></span><br/><span data-ttu-id="7e348-191">- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)</span><span class="sxs-lookup"><span data-stu-id="7e348-191">- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)</span></span><br/><span data-ttu-id="7e348-192">- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)</span><span class="sxs-lookup"><span data-stu-id="7e348-192">- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)</span></span> |[<span data-ttu-id="7e348-193">Configuración de proxy y conectividad a Internet</span><span class="sxs-lookup"><span data-stu-id="7e348-193">Configure proxy and internet connectivity settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#configure-proxy-and-internet-connectivity-settings) |
|<span data-ttu-id="7e348-194">EDR</span><span class="sxs-lookup"><span data-stu-id="7e348-194">EDR</span></span>  |<span data-ttu-id="7e348-195">macOS:</span><span class="sxs-lookup"><span data-stu-id="7e348-195">macOS:</span></span> <br/><span data-ttu-id="7e348-196">- 10.15 (Catalina)</span><span class="sxs-lookup"><span data-stu-id="7e348-196">- 10.15 (Catalina)</span></span><br/><span data-ttu-id="7e348-197">- 10.14 (Mojave)</span><span class="sxs-lookup"><span data-stu-id="7e348-197">- 10.14 (Mojave)</span></span> <br/><span data-ttu-id="7e348-198">- 10.13 (Sierra Alta)</span><span class="sxs-lookup"><span data-stu-id="7e348-198">- 10.13 (High Sierra)</span></span>  |[<span data-ttu-id="7e348-199">Microsoft Defender para endpoint para Mac: conexiones de red</span><span class="sxs-lookup"><span data-stu-id="7e348-199">Microsoft Defender for Endpoint for Mac: Network connections</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|[<span data-ttu-id="7e348-200">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="7e348-200">Microsoft Defender Antivirus</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) |<span data-ttu-id="7e348-201">- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information)</span><span class="sxs-lookup"><span data-stu-id="7e348-201">- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information)</span></span> <br/><span data-ttu-id="7e348-202">- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)</span><span class="sxs-lookup"><span data-stu-id="7e348-202">- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)</span></span><br/><span data-ttu-id="7e348-203">- [Windows Server 1803 o posterior](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)</span><span class="sxs-lookup"><span data-stu-id="7e348-203">- [Windows Server 1803 or later](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)</span></span> <br/><span data-ttu-id="7e348-204">- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016)</span><span class="sxs-lookup"><span data-stu-id="7e348-204">- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016)</span></span> |[<span data-ttu-id="7e348-205">Configurar y validar las conexiones de red del Antivirus de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="7e348-205">Configure and validate Microsoft Defender Antivirus network connections</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)<br/> |
|<span data-ttu-id="7e348-206">Antivirus</span><span class="sxs-lookup"><span data-stu-id="7e348-206">Antivirus</span></span> |<span data-ttu-id="7e348-207">macOS:</span><span class="sxs-lookup"><span data-stu-id="7e348-207">macOS:</span></span> <br/><span data-ttu-id="7e348-208">- 10.15 (Catalina)</span><span class="sxs-lookup"><span data-stu-id="7e348-208">- 10.15 (Catalina)</span></span><br/><span data-ttu-id="7e348-209">- 10.14 (Mojave)</span><span class="sxs-lookup"><span data-stu-id="7e348-209">- 10.14 (Mojave)</span></span> <br/><span data-ttu-id="7e348-210">- 10.13 (Sierra Alta)</span><span class="sxs-lookup"><span data-stu-id="7e348-210">- 10.13 (High Sierra)</span></span> |[<span data-ttu-id="7e348-211">Microsoft Defender para endpoint para Mac: conexiones de red</span><span class="sxs-lookup"><span data-stu-id="7e348-211">Microsoft Defender for Endpoint for Mac: Network connections</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|<span data-ttu-id="7e348-212">Antivirus</span><span class="sxs-lookup"><span data-stu-id="7e348-212">Antivirus</span></span> |<span data-ttu-id="7e348-213">Linux:</span><span class="sxs-lookup"><span data-stu-id="7e348-213">Linux:</span></span> <br/><span data-ttu-id="7e348-214">- RHEL 7.2+</span><span class="sxs-lookup"><span data-stu-id="7e348-214">- RHEL 7.2+</span></span><br/><span data-ttu-id="7e348-215">- CentOS Linux 7.2+</span><span class="sxs-lookup"><span data-stu-id="7e348-215">- CentOS Linux 7.2+</span></span><br/><span data-ttu-id="7e348-216">- Ubuntu 16 LTS o LTS superior</span><span class="sxs-lookup"><span data-stu-id="7e348-216">- Ubuntu 16 LTS, or higher LTS</span></span><br/><span data-ttu-id="7e348-217">- SLES 12+</span><span class="sxs-lookup"><span data-stu-id="7e348-217">- SLES 12+</span></span><br/><span data-ttu-id="7e348-218">- Debian 9+</span><span class="sxs-lookup"><span data-stu-id="7e348-218">- Debian 9+</span></span><br/><span data-ttu-id="7e348-219">- Oracle Linux 7.2</span><span class="sxs-lookup"><span data-stu-id="7e348-219">- Oracle Linux 7.2</span></span> |[<span data-ttu-id="7e348-220">Microsoft Defender para endpoint para Linux: conexiones de red</span><span class="sxs-lookup"><span data-stu-id="7e348-220">Microsoft Defender for Endpoint for Linux: Network connections</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux#network-connections) 

## <a name="next-step"></a><span data-ttu-id="7e348-221">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="7e348-221">Next step</span></span>

<span data-ttu-id="7e348-222">**¡Enhorabuena!**</span><span class="sxs-lookup"><span data-stu-id="7e348-222">**Congratulations**!</span></span> <span data-ttu-id="7e348-223">Ha completado la fase **de preparación** de la migración [de McAfee a Microsoft Defender para Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)!</span><span class="sxs-lookup"><span data-stu-id="7e348-223">You have completed the **Prepare** phase of [migrating from McAfee to Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)!</span></span>

- <span data-ttu-id="7e348-224">[Continúe con la configuración de Microsoft Defender para endpoint](mcafee-to-microsoft-defender-setup.md).</span><span class="sxs-lookup"><span data-stu-id="7e348-224">[Proceed to set up Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-setup.md).</span></span>