---
title: Programar actualizaciones de protección antivirus de Microsoft Defender
description: Programar el día, la hora y el intervalo para el momento en que se deben descargar las actualizaciones de protección
keywords: actualizaciones, líneas base de seguridad, actualizaciones de programación
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 327974c4db4166301820cf148811aceda1700513
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765352"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a><span data-ttu-id="91e11-104">Administrar la programación de cuándo deben descargarse y aplicarse las actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="91e11-104">Manage the schedule for when protection updates should be downloaded and applied</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="91e11-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="91e11-105">**Applies to:**</span></span>

- [<span data-ttu-id="91e11-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="91e11-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="91e11-107">Antivirus de Microsoft Defender te permite determinar cuándo debe buscar y descargar actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="91e11-107">Microsoft Defender Antivirus lets you determine when it should look for and download updates.</span></span>

<span data-ttu-id="91e11-108">Puede programar actualizaciones para los puntos de conexión mediante:</span><span class="sxs-lookup"><span data-stu-id="91e11-108">You can schedule updates for your endpoints by:</span></span> 

- <span data-ttu-id="91e11-109">Especificar el día de la semana para comprobar si hay actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="91e11-109">Specifying the day of the week to check for protection updates</span></span> 
- <span data-ttu-id="91e11-110">Especificación del intervalo para comprobar si hay actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="91e11-110">Specifying the interval to check for protection updates</span></span>
- <span data-ttu-id="91e11-111">Especificar el tiempo para comprobar si hay actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="91e11-111">Specifying the time to check for protection updates</span></span>

<span data-ttu-id="91e11-112">También puede aleatorizar las horas en las que cada extremo comprueba y descarga actualizaciones de protección.</span><span class="sxs-lookup"><span data-stu-id="91e11-112">You can also randomize the times when each endpoint checks and downloads protection updates.</span></span> <span data-ttu-id="91e11-113">Vea el [tema Programar exámenes](scheduled-catch-up-scans-microsoft-defender-antivirus.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="91e11-113">See the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="use-configuration-manager-to-schedule-protection-updates"></a><span data-ttu-id="91e11-114">Usar Configuration Manager para programar actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="91e11-114">Use Configuration Manager to schedule protection updates</span></span>

1.  <span data-ttu-id="91e11-115">En la consola de Microsoft Endpoint Manager, abra la  directiva de antimalware que desea cambiar (haga clic en Activos y cumplimiento en el panel de navegación de la izquierda y, a continuación, expanda el árbol a **Overview**  >  **Endpoint Protection**  >  **Antimalware Policies**)</span><span class="sxs-lookup"><span data-stu-id="91e11-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="91e11-116">Vaya a la **sección Actualizaciones de inteligencia de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="91e11-116">Go to the **Security intelligence updates** section.</span></span>

3. <span data-ttu-id="91e11-117">Para comprobar y descargar actualizaciones en un momento determinado:</span><span class="sxs-lookup"><span data-stu-id="91e11-117">To check and download updates at a certain time:</span></span>
      1. <span data-ttu-id="91e11-118">Establezca **Comprobar las actualizaciones de inteligencia de seguridad de Endpoint Protection en un intervalo específico...** en **0**.</span><span class="sxs-lookup"><span data-stu-id="91e11-118">Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to **0**.</span></span>
      2. <span data-ttu-id="91e11-119">Establezca Comprobar las actualizaciones de inteligencia de seguridad de Endpoint Protection diariamente **en...** en el momento en que deben comprobarse las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="91e11-119">Set **Check for Endpoint Protection security intelligence updates daily at...** to the time when updates should be checked.</span></span>
      <span data-ttu-id="91e11-120">3</span><span class="sxs-lookup"><span data-stu-id="91e11-120">3</span></span>
4. <span data-ttu-id="91e11-121">Para comprobar y descargar actualizaciones en un intervalo continuo, establezca Comprobar las actualizaciones de inteligencia de seguridad de Endpoint Protection en un intervalo **específico...** en el número de horas que deben producirse entre actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="91e11-121">To check and download updates on a continual interval, Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to the number of hours that should occur between updates.</span></span>

5.  <span data-ttu-id="91e11-122">[Implemente la directiva actualizada como de costumbre.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="91e11-122">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="use-group-policy-to-schedule-protection-updates"></a><span data-ttu-id="91e11-123">Usar la directiva de grupo para programar actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="91e11-123">Use Group Policy to schedule protection updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="91e11-124">De forma predeterminada, Antivirus de Microsoft Defender buscará una actualización 15 minutos antes de la hora de los exámenes programados.</span><span class="sxs-lookup"><span data-stu-id="91e11-124">By default, Microsoft Defender Antivirus will check for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="91e11-125">Si se habilita esta configuración, se invalidará el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="91e11-125">Enabling these settings will override that default.</span></span>

1.  <span data-ttu-id="91e11-126">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="91e11-126">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="91e11-127">En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**</span><span class="sxs-lookup"><span data-stu-id="91e11-127">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="91e11-128">Haga clic **en Directivas** **y, a continuación, en Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="91e11-128">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="91e11-129">Expande el árbol a **Componentes de Windows** Actualizaciones de inteligencia de firma de Antivirus de  >  **Microsoft Defender**  >   y configura las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="91e11-129">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Intelligence Updates** and configure the following settings:</span></span>

    1. <span data-ttu-id="91e11-130">Haga doble clic en **la opción Especificar el día de la** semana para comprobar si hay actualizaciones de inteligencia de seguridad y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="91e11-130">Double-click the **Specify the day of the week to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="91e11-131">Escriba el día de la semana para buscar actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="91e11-131">Enter the day of the week to check for updates.</span></span> <span data-ttu-id="91e11-132">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="91e11-132">Click **OK**.</span></span>
    2. <span data-ttu-id="91e11-133">Haga doble clic en **la opción Especificar el intervalo para comprobar si** hay actualizaciones de inteligencia de seguridad y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="91e11-133">Double-click the **Specify the interval to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="91e11-134">Escriba el número de horas entre actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="91e11-134">Enter the number of hours between updates.</span></span> <span data-ttu-id="91e11-135">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="91e11-135">Click **OK**.</span></span>
    3. <span data-ttu-id="91e11-136">Haga doble clic en **la opción Especificar la hora para comprobar si** hay actualizaciones de inteligencia de seguridad y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="91e11-136">Double-click the **Specify the time to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="91e11-137">Escriba la hora en la que deben comprobarse las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="91e11-137">Enter the time when updates should be checked.</span></span> <span data-ttu-id="91e11-138">La hora se basa en la hora local del extremo.</span><span class="sxs-lookup"><span data-stu-id="91e11-138">The time is based on the local time of the endpoint.</span></span> <span data-ttu-id="91e11-139">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="91e11-139">Click **OK**.</span></span>


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a><span data-ttu-id="91e11-140">Usar cmdlets de PowerShell para programar actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="91e11-140">Use PowerShell cmdlets to schedule protection updates</span></span>

<span data-ttu-id="91e11-141">Use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="91e11-141">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

<span data-ttu-id="91e11-142">Consulte [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="91e11-142">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a><span data-ttu-id="91e11-143">Usar Windows Management Instruction (WMI) para programar actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="91e11-143">Use Windows Management Instruction (WMI) to schedule protection updates</span></span>

<span data-ttu-id="91e11-144">Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="91e11-144">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

<span data-ttu-id="91e11-145">Vea lo siguiente para obtener más información y parámetros permitidos:</span><span class="sxs-lookup"><span data-stu-id="91e11-145">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="91e11-146">Windows Defender API WMIv2</span><span class="sxs-lookup"><span data-stu-id="91e11-146">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a><span data-ttu-id="91e11-147">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="91e11-147">Related articles</span></span>

- [<span data-ttu-id="91e11-148">Implementar antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="91e11-148">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="91e11-149">Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar líneas base</span><span class="sxs-lookup"><span data-stu-id="91e11-149">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="91e11-150">Administrar actualizaciones de puntos de conexión que están des actualizadas</span><span class="sxs-lookup"><span data-stu-id="91e11-150">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="91e11-151">Administrar actualizaciones forzadas basadas en eventos</span><span class="sxs-lookup"><span data-stu-id="91e11-151">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="91e11-152">Administrar actualizaciones para dispositivos móviles y máquinas virtuales (VM)</span><span class="sxs-lookup"><span data-stu-id="91e11-152">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="91e11-153">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="91e11-153">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)