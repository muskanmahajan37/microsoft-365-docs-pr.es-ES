---
title: Definir cómo se actualizan los dispositivos móviles mediante Antivirus de Microsoft Defender
description: Administrar la forma en que los dispositivos móviles, como los portátiles, deben actualizarse con las actualizaciones de protección antivirus de Microsoft Defender.
keywords: actualizaciones, protección, actualizaciones de programación, batería, dispositivo móvil, portátil, bloc de notas, opt-in, microsoft update, wsus, override
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
ms.openlocfilehash: 826e1456de2aadf4031a91e30925a1e771d44f70
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765592"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a><span data-ttu-id="74ccb-104">Administrar actualizaciones para dispositivos móviles y máquinas virtuales (VM)</span><span class="sxs-lookup"><span data-stu-id="74ccb-104">Manage updates for mobile devices and virtual machines (VMs)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="74ccb-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="74ccb-105">**Applies to:**</span></span>

- [<span data-ttu-id="74ccb-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="74ccb-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="74ccb-107">Es posible que los dispositivos móviles y las máquinas virtuales requieran más configuración para garantizar que las actualizaciones no afectan al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="74ccb-107">Mobile devices and VMs may require more configuration to ensure performance is not impacted by updates.</span></span>

<span data-ttu-id="74ccb-108">Hay dos opciones de configuración que son útiles para estos dispositivos:</span><span class="sxs-lookup"><span data-stu-id="74ccb-108">There are two settings that are useful for these devices:</span></span>

- <span data-ttu-id="74ccb-109">Participar en Microsoft Update en equipos móviles sin conexión WSUS</span><span class="sxs-lookup"><span data-stu-id="74ccb-109">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>
- <span data-ttu-id="74ccb-110">Impedir actualizaciones de inteligencia de seguridad al ejecutarse con batería</span><span class="sxs-lookup"><span data-stu-id="74ccb-110">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="74ccb-111">Los artículos siguientes también pueden ser útiles en estas situaciones:</span><span class="sxs-lookup"><span data-stu-id="74ccb-111">The following articles may also be useful in these situations:</span></span>
- [<span data-ttu-id="74ccb-112">Configuración de exámenes programados y de actualización</span><span class="sxs-lookup"><span data-stu-id="74ccb-112">Configuring scheduled and catch-up scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="74ccb-113">Administrar actualizaciones de puntos de conexión que están des actualizadas</span><span class="sxs-lookup"><span data-stu-id="74ccb-113">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="74ccb-114">Guía de implementación para Antivirus de Microsoft Defender en un entorno de infraestructura de escritorio virtual (VDI)</span><span class="sxs-lookup"><span data-stu-id="74ccb-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a><span data-ttu-id="74ccb-115">Participar en Microsoft Update en equipos móviles sin conexión WSUS</span><span class="sxs-lookup"><span data-stu-id="74ccb-115">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>

<span data-ttu-id="74ccb-116">Puedes usar Microsoft Update para mantener actualizada la inteligencia de seguridad en dispositivos móviles que ejecutan Antivirus de Microsoft Defender cuando no están conectados a la red corporativa o si no tienen una conexión WSUS.</span><span class="sxs-lookup"><span data-stu-id="74ccb-116">You can use Microsoft Update to keep Security intelligence on mobile devices running Microsoft Defender Antivirus up to date when they are not connected to the corporate network or don't otherwise have a WSUS connection.</span></span> 

<span data-ttu-id="74ccb-117">Esto significa que las actualizaciones de protección se pueden entregar a dispositivos (a través de Microsoft Update) incluso si has establecido WSUS para invalidar Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="74ccb-117">This means that protection updates can be delivered to devices (via Microsoft Update) even if you have set WSUS to override Microsoft Update.</span></span>

<span data-ttu-id="74ccb-118">Puedes participar en Microsoft Update en el dispositivo móvil de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="74ccb-118">You can opt in to Microsoft Update on the mobile device in one of the following ways:</span></span>

- <span data-ttu-id="74ccb-119">Cambie la configuración con la directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="74ccb-119">Change the setting with Group Policy.</span></span>
- <span data-ttu-id="74ccb-120">Use un VBScript para crear un script y, a continuación, ejecutarlo en cada equipo de la red.</span><span class="sxs-lookup"><span data-stu-id="74ccb-120">Use a VBScript to create a script, then run it on each computer in your network.</span></span>
- <span data-ttu-id="74ccb-121">Opte manualmente por todos los equipos de la red a través del **menú** Configuración.</span><span class="sxs-lookup"><span data-stu-id="74ccb-121">Manually opt in every computer on your network through the **Settings** menu.</span></span>

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a><span data-ttu-id="74ccb-122">Usar la directiva de grupo para participar en Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="74ccb-122">Use Group Policy to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="74ccb-123">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y **seleccione Editar**.</span><span class="sxs-lookup"><span data-stu-id="74ccb-123">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="74ccb-124">En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**</span><span class="sxs-lookup"><span data-stu-id="74ccb-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="74ccb-125">Seleccione **Directivas y,** **a continuación, Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="74ccb-125">Select **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="74ccb-126">Expande el árbol a **Componentes de Windows** Actualizaciones de firma de Antivirus  >  de Microsoft **Defender.**  >  </span><span class="sxs-lookup"><span data-stu-id="74ccb-126">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**.</span></span>

5. <span data-ttu-id="74ccb-127">Establezca **Permitir actualizaciones de inteligencia de seguridad de Microsoft Update** en **Habilitado** y, a continuación, seleccione  **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="74ccb-127">Set **Allow security intelligence updates from Microsoft Update** to **Enabled**, and then select  **OK**.</span></span>


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a><span data-ttu-id="74ccb-128">Usar un VBScript para participar en Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="74ccb-128">Use a VBScript to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="74ccb-129">Use las instrucciones del artículo de MSDN [Opt-In to Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) para crear vbscript.</span><span class="sxs-lookup"><span data-stu-id="74ccb-129">Use the instructions in the MSDN article [Opt-In to Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) to create the VBScript.</span></span>

2. <span data-ttu-id="74ccb-130">Ejecute el VBScript que creó en cada equipo de la red.</span><span class="sxs-lookup"><span data-stu-id="74ccb-130">Run the VBScript you created on each computer in your network.</span></span>

### <a name="manually-opt-in-to-microsoft-update"></a><span data-ttu-id="74ccb-131">Participar manualmente en Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="74ccb-131">Manually opt in to Microsoft Update</span></span>

1. <span data-ttu-id="74ccb-132">Abre **Windows Update** en Update & configuración **de** seguridad en el equipo en el que quieras participar.</span><span class="sxs-lookup"><span data-stu-id="74ccb-132">Open **Windows Update** in **Update & security** settings on the computer you want to opt in.</span></span>

2. <span data-ttu-id="74ccb-133">Seleccione **Opciones** avanzadas.</span><span class="sxs-lookup"><span data-stu-id="74ccb-133">Select **Advanced** options.</span></span>

3. <span data-ttu-id="74ccb-134">Active la casilla **Deme actualizaciones para otros productos de Microsoft cuando actualice Windows**.</span><span class="sxs-lookup"><span data-stu-id="74ccb-134">Select the checkbox for **Give me updates for other Microsoft products when I update Windows**.</span></span>

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a><span data-ttu-id="74ccb-135">Impedir actualizaciones de inteligencia de seguridad al ejecutarse con batería</span><span class="sxs-lookup"><span data-stu-id="74ccb-135">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="74ccb-136">Puede configurar Antivirus de Microsoft Defender para que solo descargue actualizaciones de protección cuando el equipo esté conectado a una fuente de alimentación por cable.</span><span class="sxs-lookup"><span data-stu-id="74ccb-136">You can configure Microsoft Defender Antivirus to only download protection updates when the PC is connected to a wired power source.</span></span> 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a><span data-ttu-id="74ccb-137">Usar la directiva de grupo para evitar actualizaciones de inteligencia de seguridad en la batería</span><span class="sxs-lookup"><span data-stu-id="74ccb-137">Use Group Policy to prevent security intelligence updates on battery power</span></span>

1.  <span data-ttu-id="74ccb-138">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))elija el objeto de directiva de grupo que desea configurar y ábralo para su edición.</span><span class="sxs-lookup"><span data-stu-id="74ccb-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), choose the Group Policy Object you want to configure, and open it for editing.</span></span>

2.  <span data-ttu-id="74ccb-139">En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**</span><span class="sxs-lookup"><span data-stu-id="74ccb-139">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3.  <span data-ttu-id="74ccb-140">Seleccione **Directivas y,** **a continuación, Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="74ccb-140">Select **Policies** then **Administrative templates**.</span></span>

4.  <span data-ttu-id="74ccb-141">Expande el árbol a **Componentes de Windows** Actualizaciones de firma de Antivirus de Microsoft Defender y, a continuación, establece Permitir actualizaciones de inteligencia de seguridad al ejecutar la batería en  >    >   **Deshabilitado.** </span><span class="sxs-lookup"><span data-stu-id="74ccb-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**, and then set **Allow security intelligence updates when running on battery power** to **Disabled**.</span></span> <span data-ttu-id="74ccb-142">A continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="74ccb-142">Then select **OK**.</span></span> 

<span data-ttu-id="74ccb-143">Esta acción impide que las actualizaciones de protección se descarguen cuando el equipo está en batería.</span><span class="sxs-lookup"><span data-stu-id="74ccb-143">This action prevents protection updates from downloading when the PC is on battery power.</span></span>

## <a name="related-articles"></a><span data-ttu-id="74ccb-144">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="74ccb-144">Related articles</span></span>

- [<span data-ttu-id="74ccb-145">Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar líneas base</span><span class="sxs-lookup"><span data-stu-id="74ccb-145">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="74ccb-146">Actualizar y administrar antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="74ccb-146">Update and manage Microsoft Defender Antivirus in Windows 10</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)