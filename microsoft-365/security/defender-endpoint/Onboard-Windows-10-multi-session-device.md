---
title: Incorporación de dispositivos multi sesión de Windows 10 en Windows Virtual Desktop
description: Lee más en este artículo sobre la incorporación de dispositivos multi-sesión de Windows 10 en Windows Virtual Desktop
keywords: Windows Virtual Desktop, WVD, microsoft defender, endpoint, onboard
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.date: 09/10/2020
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 30e664aed74ed01944c67b139e6268fc3340ada4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069859"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a><span data-ttu-id="94659-104">Incorporación de dispositivos multi sesión de Windows 10 en Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="94659-104">Onboard Windows 10 multi-session devices in Windows Virtual Desktop</span></span> 
<span data-ttu-id="94659-105">6 minutos para leer</span><span class="sxs-lookup"><span data-stu-id="94659-105">6 minutes to read</span></span> 

<span data-ttu-id="94659-106">Se aplica a:</span><span class="sxs-lookup"><span data-stu-id="94659-106">Applies to:</span></span> 
- <span data-ttu-id="94659-107">Windows 10 multi-session que se ejecuta en Windows Virtual Desktop (WVD)</span><span class="sxs-lookup"><span data-stu-id="94659-107">Windows 10 multi-session running on Windows Virtual Desktop (WVD)</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="94659-108">Bienvenido a Microsoft Defender para Endpoint, el nuevo nombre de Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="94659-108">Welcome to Microsoft Defender for Endpoint, the new name for Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="94659-109">Obtenga más información sobre esta y otras actualizaciones aquí.</span><span class="sxs-lookup"><span data-stu-id="94659-109">Read more about this and other updates here.</span></span> <span data-ttu-id="94659-110">Los nombres de los productos y los documentos se actualizarán en un futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="94659-110">We'll be updating names in products and in the docs in the near future.</span></span>

> [!WARNING]
> <span data-ttu-id="94659-111">La compatibilidad de Microsoft Defender para puntos de conexión para escenarios de varias sesiones de Escritorio virtual de Windows está actualmente en versión preliminar y está limitada hasta 25 sesiones simultáneas por host/VM.</span><span class="sxs-lookup"><span data-stu-id="94659-111">Microsoft Defender for Endpoint support for Windows Virtual Desktop multi-session scenarios is currently in Preview and limited up to 25 concurrent sessions per host/VM.</span></span> <span data-ttu-id="94659-112">Sin embargo, los escenarios de sesión única en Windows Virtual Desktop son totalmente compatibles.</span><span class="sxs-lookup"><span data-stu-id="94659-112">However, single session scenarios on Windows Virtual Desktop are fully supported.</span></span>

<span data-ttu-id="94659-113">Microsoft Defender para endpoint admite la supervisión tanto de VDI como de sesiones de Escritorio virtual de Windows.</span><span class="sxs-lookup"><span data-stu-id="94659-113">Microsoft Defender for Endpoint supports monitoring both VDI as well as Windows Virtual Desktop sessions.</span></span> <span data-ttu-id="94659-114">Según las necesidades de la organización, es posible que deba implementar sesiones de VDI o Windows Virtual Desktop para ayudar a los empleados a tener acceso a datos corporativos y aplicaciones desde un dispositivo no administrado, una ubicación remota o un escenario similar.</span><span class="sxs-lookup"><span data-stu-id="94659-114">Depending on your organization's needs, you might need to implement VDI or Windows Virtual Desktop sessions to help your employees access corporate data and apps from an unmanaged device, remote location, or similar scenario.</span></span> <span data-ttu-id="94659-115">Con Microsoft Defender para endpoint, puede supervisar estas máquinas virtuales en busca de actividad anómala.</span><span class="sxs-lookup"><span data-stu-id="94659-115">With Microsoft Defender for Endpoint, you can monitor these virtual machines for anomalous activity.</span></span>

 ## <a name="before-you-begin"></a><span data-ttu-id="94659-116">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="94659-116">Before you begin</span></span>
<span data-ttu-id="94659-117">Familiarícese con las [consideraciones para VDI no persistente.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)</span><span class="sxs-lookup"><span data-stu-id="94659-117">Familiarize yourself with the [considerations for non-persistent VDI](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span> <span data-ttu-id="94659-118">Aunque [Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview) no proporciona opciones de no persistencia, sí proporciona formas de usar una imagen dorada de Windows que se puede usar para aprovisionar nuevos hosts y volver a implementar máquinas.</span><span class="sxs-lookup"><span data-stu-id="94659-118">While [Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview) does not provide non-persistence options, it does provide ways to use a golden Windows image that can be used to provision new hosts and redeploy machines.</span></span> <span data-ttu-id="94659-119">Esto aumenta la inestabilidad en el entorno y, por lo tanto, afecta a las entradas que se crean y mantienen en el portal de Microsoft Defender para endpoints, lo que potencialmente reduce la visibilidad de los analistas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="94659-119">This increases volatility in the environment and thus impacts what entries are created and maintained in the Microsoft Defender for Endpoint portal, potentially reducing visibility for your security analysts.</span></span>

> [!NOTE]
> <span data-ttu-id="94659-120">Según la elección del método de incorporación, los dispositivos pueden aparecer en el portal de Microsoft Defender para endpoints como:</span><span class="sxs-lookup"><span data-stu-id="94659-120">Depending on your choice of onboarding method, devices can appear in Microsoft Defender for Endpoint portal as either:</span></span> 
> - <span data-ttu-id="94659-121">Entrada única para cada escritorio virtual</span><span class="sxs-lookup"><span data-stu-id="94659-121">Single entry for each virtual desktop</span></span> 
> - <span data-ttu-id="94659-122">Varias entradas para cada escritorio virtual</span><span class="sxs-lookup"><span data-stu-id="94659-122">Multiple entries for each virtual desktop</span></span> 

<span data-ttu-id="94659-123">Microsoft recomienda incorporar Windows Virtual Desktop como una sola entrada por escritorio virtual.</span><span class="sxs-lookup"><span data-stu-id="94659-123">Microsoft recommends onboarding Windows Virtual Desktop as a single entry per virtual desktop.</span></span> <span data-ttu-id="94659-124">Esto garantiza que la experiencia de investigación en el portal de puntos de conexión de Microsoft Defender se encuentra en el contexto de un dispositivo basado en el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="94659-124">This ensures that the investigation experience in the Microsoft Defender Endpoint portal is in the context of one device based on the machine name.</span></span> <span data-ttu-id="94659-125">Las organizaciones que eliminan e implementan hosts WVD con frecuencia deben considerar encarecidamente el uso de este método, ya que impide que se cree varios objetos para la misma máquina en el portal de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="94659-125">Organizations that frequently delete and re-deploy WVD hosts should strongly consider using this method as it prevents multiple objects for the same machine from being created in the Microsoft Defender for Endpoint portal.</span></span> <span data-ttu-id="94659-126">Esto puede provocar confusión al investigar incidentes.</span><span class="sxs-lookup"><span data-stu-id="94659-126">This can lead to confusion when investigating incidents.</span></span> <span data-ttu-id="94659-127">Para entornos de prueba o no volátiles, puede optar por elegir de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="94659-127">For test or non-volatile environments, you may opt to choose differently.</span></span> 

<span data-ttu-id="94659-128">Microsoft recomienda agregar el script de incorporación de Microsoft Defender para endpoint a la imagen dorada de WVD.</span><span class="sxs-lookup"><span data-stu-id="94659-128">Microsoft recommends adding the Microsoft Defender for Endpoint onboarding script to the WVD golden image.</span></span> <span data-ttu-id="94659-129">De esta forma, puede asegurarse de que este script de incorporación se ejecute inmediatamente al primer arranque.</span><span class="sxs-lookup"><span data-stu-id="94659-129">This way, you can be sure that this onboarding script runs immediately at first boot.</span></span> <span data-ttu-id="94659-130">Se ejecuta como un script de inicio en el primer arranque en todas las máquinas WVD que se aprovisionan desde la imagen dorada de WVD.</span><span class="sxs-lookup"><span data-stu-id="94659-130">It is executed as a startup script at first boot on all the WVD machines that are provisioned from the WVD golden image.</span></span> <span data-ttu-id="94659-131">Sin embargo, si usa una de las imágenes de la galería sin modificaciones, coloque el script en una ubicación compartida y llámelo desde una directiva de grupo local o de dominio.</span><span class="sxs-lookup"><span data-stu-id="94659-131">However, if you are using one of the gallery images without modification, place the script in a shared location and call it from either local or domain group policy.</span></span> 

> [!NOTE]
> <span data-ttu-id="94659-132">La ubicación y configuración del script de inicio de incorporación de VDI en la imagen dorada de WVD lo configura como un script de inicio que se ejecuta cuando se inicia WVD.</span><span class="sxs-lookup"><span data-stu-id="94659-132">The placement and configuration of the VDI onboarding startup script on the WVD golden image configures it as a startup script that runs when the WVD starts.</span></span> <span data-ttu-id="94659-133">NO se recomienda incorporar la imagen dorada de WVD real.</span><span class="sxs-lookup"><span data-stu-id="94659-133">It is NOT recommended to onboard the actual WVD golden image.</span></span> <span data-ttu-id="94659-134">Otra consideración es el método usado para ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="94659-134">Another consideration is the method used to run the script.</span></span> <span data-ttu-id="94659-135">Debe ejecutarse lo antes posible en el proceso de inicio o aprovisionamiento para reducir el tiempo entre la máquina que está disponible para recibir sesiones y la incorporación del dispositivo al servicio.</span><span class="sxs-lookup"><span data-stu-id="94659-135">It should run as early in the startup/provisioning process as possible to reduce the time between the machine being available to receive sessions and the device onboarding to the service.</span></span> <span data-ttu-id="94659-136">En los escenarios siguientes, 1 & 2 tienen esto en cuenta.</span><span class="sxs-lookup"><span data-stu-id="94659-136">Below scenarios 1 & 2 take this into account.</span></span>

### <a name="scenarios"></a><span data-ttu-id="94659-137">Escenarios</span><span class="sxs-lookup"><span data-stu-id="94659-137">Scenarios</span></span>
<span data-ttu-id="94659-138">Hay varias formas de incorporar un equipo host WVD:</span><span class="sxs-lookup"><span data-stu-id="94659-138">There are several ways to onboard a WVD host machine:</span></span>

- <span data-ttu-id="94659-139">Ejecute el script en la imagen dorada (o desde una ubicación compartida) durante el inicio.</span><span class="sxs-lookup"><span data-stu-id="94659-139">Run the script in the golden image (or from a shared location) during startup.</span></span>
- <span data-ttu-id="94659-140">Use una herramienta de administración para ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="94659-140">Use a management tool to run the script.</span></span>

#### <a name="scenario-1-using-local-group-policy"></a><span data-ttu-id="94659-141">*Escenario 1: Uso de la directiva de grupo local*</span><span class="sxs-lookup"><span data-stu-id="94659-141">*Scenario 1: Using local group policy*</span></span>
<span data-ttu-id="94659-142">Este escenario requiere colocar el script en una imagen dorada y usa la directiva de grupo local para ejecutarse al principio del proceso de arranque.</span><span class="sxs-lookup"><span data-stu-id="94659-142">This scenario requires placing the script in a golden image and uses local group policy to run early in the boot process.</span></span>

<span data-ttu-id="94659-143">Use las instrucciones de [Incorporación de dispositivos VDI de](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)infraestructura de escritorio virtual no persistente.</span><span class="sxs-lookup"><span data-stu-id="94659-143">Use the instructions in [Onboard non-persistent virtual desktop infrastructure VDI devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span>

<span data-ttu-id="94659-144">Siga las instrucciones de una sola entrada para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="94659-144">Follow the instructions for a single entry for each device.</span></span>

#### <a name="scenario-2-using-domain-group-policy"></a><span data-ttu-id="94659-145">*Escenario 2: Uso de la directiva de grupo de dominio*</span><span class="sxs-lookup"><span data-stu-id="94659-145">*Scenario 2: Using domain group policy*</span></span>
<span data-ttu-id="94659-146">Este escenario usa un script ubicado centralmente y lo ejecuta mediante una directiva de grupo basada en dominio.</span><span class="sxs-lookup"><span data-stu-id="94659-146">This scenario uses a centrally located script and runs it using a domain-based group policy.</span></span> <span data-ttu-id="94659-147">También puede colocar el script en la imagen dorada y ejecutarlo de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="94659-147">You can also place the script in the golden image and run it in the same way.</span></span>

<span data-ttu-id="94659-148">**Descargue el archivo WindowsDefenderATPOnboardingPackage.zip desde el Centro Windows Defender seguridad**</span><span class="sxs-lookup"><span data-stu-id="94659-148">**Download the WindowsDefenderATPOnboardingPackage.zip file from the Windows Defender Security Center**</span></span>
1. <span data-ttu-id="94659-149">Abra el archivo .zip del paquete de configuración VDI (WindowsDefenderATPOnboardingPackage.zip)</span><span class="sxs-lookup"><span data-stu-id="94659-149">Open the VDI configuration package .zip file (WindowsDefenderATPOnboardingPackage.zip)</span></span>  
    - <span data-ttu-id="94659-150">En el panel de navegación del Centro de seguridad de Microsoft Defender, seleccione **Configuración**  >  **incorporación**.</span><span class="sxs-lookup"><span data-stu-id="94659-150">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Onboarding**.</span></span> 
    - <span data-ttu-id="94659-151">Selecciona Windows 10 como sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="94659-151">Select Windows 10 as the operating system.</span></span> 
    - <span data-ttu-id="94659-152">En el **campo Método de** implementación, seleccione Scripts de incorporación de VDI para puntos de conexión no persistentes.</span><span class="sxs-lookup"><span data-stu-id="94659-152">In the **Deployment method** field, select VDI onboarding scripts for non-persistent endpoints.</span></span> 
    - <span data-ttu-id="94659-153">Haga **clic en Descargar paquete** y guarde el archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="94659-153">Click **Download package** and save the .zip file.</span></span> 
2. <span data-ttu-id="94659-154">Extrae el contenido del archivo .zip en una ubicación compartida de solo lectura a la que pueda tener acceso el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="94659-154">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="94659-155">Debe tener una carpeta denominada **OptionalParamsPolicy** y los archivos **WindowsDefenderATPOnboardingScript.cmd** **yOnboard-NonPersistentMachine.ps1**.</span><span class="sxs-lookup"><span data-stu-id="94659-155">You should have a folder called **OptionalParamsPolicy** and the files **WindowsDefenderATPOnboardingScript.cmd** and **Onboard-NonPersistentMachine.ps1**.</span></span>

<span data-ttu-id="94659-156">**Usar la consola de administración de directivas de grupo para ejecutar el script cuando se inicia la máquina virtual**</span><span class="sxs-lookup"><span data-stu-id="94659-156">**Use Group Policy management console to run the script when the virtual machine starts**</span></span>
1. <span data-ttu-id="94659-157">Abra la Consola de administración de directivas de grupo (GPMC), haga clic con el botón secundario en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="94659-157">Open the Group Policy Management Console (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>
1. <span data-ttu-id="94659-158">En el Editor de administración de directivas de grupo, vaya a **Configuración** del equipo Preferencias \>  \> **configuración Configuración del panel de control .**</span><span class="sxs-lookup"><span data-stu-id="94659-158">In the Group Policy Management Editor, go to **Computer configuration** \> **Preferences** \> **Control panel settings**.</span></span> 
1. <span data-ttu-id="94659-159">Haz clic con el **botón secundario en Tareas programadas,** haz clic en **Nuevo** y, a continuación, haz clic en **Tarea inmediata** (al menos Windows 7).</span><span class="sxs-lookup"><span data-stu-id="94659-159">Right-click **Scheduled tasks**, click **New**, and then click **Immediate Task** (At least Windows 7).</span></span> 
1. <span data-ttu-id="94659-160">En la ventana Tarea que se abre, vaya a la **pestaña General.** En **Opciones de seguridad,** **haga clic en Cambiar usuario o grupo** y escriba SISTEMA.</span><span class="sxs-lookup"><span data-stu-id="94659-160">In the Task window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM.</span></span> <span data-ttu-id="94659-161">Haga **clic en Comprobar nombres** y, a continuación, en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="94659-161">Click **Check Names** and then click OK.</span></span> <span data-ttu-id="94659-162">NT AUTHORITY\SYSTEM aparece como la cuenta de usuario en la que se ejecutará la tarea.</span><span class="sxs-lookup"><span data-stu-id="94659-162">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span> 
1. <span data-ttu-id="94659-163">Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla Ejecutar con **privilegios** más altos.</span><span class="sxs-lookup"><span data-stu-id="94659-163">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span> 
1. <span data-ttu-id="94659-164">Vaya a la **pestaña Acciones** y haga clic **en Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="94659-164">Go to the **Actions** tab and click **New**.</span></span> <span data-ttu-id="94659-165">Asegúrese de **que Iniciar un programa** está seleccionado en el campo Acción.</span><span class="sxs-lookup"><span data-stu-id="94659-165">Ensure that **Start a program** is selected in the Action field.</span></span> <span data-ttu-id="94659-166">Especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="94659-166">Enter the following:</span></span> 

> <span data-ttu-id="94659-167">Action = "Start a program"</span><span class="sxs-lookup"><span data-stu-id="94659-167">Action = "Start a program"</span></span> <br>
> <span data-ttu-id="94659-168">Programa/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe</span><span class="sxs-lookup"><span data-stu-id="94659-168">Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe</span></span> <br>
> <span data-ttu-id="94659-169">Add Arguments (opcional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"</span><span class="sxs-lookup"><span data-stu-id="94659-169">Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"</span></span>

<span data-ttu-id="94659-170">Haga **clic en Aceptar** y cierre las ventanas GPMC abiertas.</span><span class="sxs-lookup"><span data-stu-id="94659-170">Click **OK** and close any open GPMC windows.</span></span>

#### <a name="scenario-3-onboarding-using-management-tools"></a><span data-ttu-id="94659-171">*Escenario 3: Incorporación con herramientas de administración*</span><span class="sxs-lookup"><span data-stu-id="94659-171">*Scenario 3: Onboarding using management tools*</span></span>

<span data-ttu-id="94659-172">Si planea administrar las máquinas con una herramienta de administración, puede incorporar dispositivos con Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="94659-172">If you plan to manage your machines using a management tool, you can onboard devices with Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="94659-173">Para obtener más información, consulta: [Incorporación de dispositivos Windows 10 con Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)</span><span class="sxs-lookup"><span data-stu-id="94659-173">For more information, see: [Onboard Windows 10 devices using Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)</span></span> 

> [!WARNING]
> <span data-ttu-id="94659-174">Si tienes previsto usar reglas de reducción de Superficie de [ataque,](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)ten en cuenta que la regla " Bloquear creaciones de procesos originadas a partir de comandos[PSExec](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction#block-process-creations-originating-from-psexec-and-wmi-commands)y WMI " no debe usarse, ya que es incompatible con la administración a través de Microsoft Endpoint Configuration Manager porque esta regla bloquea los comandos WMI que el cliente de Configuration Manager usa para funcionar correctamente.</span><span class="sxs-lookup"><span data-stu-id="94659-174">If you plan to use [Attack Surface reduction Rules](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction), please note that rule “[Block process creations originating from PSExec and WMI commands](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction#block-process-creations-originating-from-psexec-and-wmi-commands)" should not be used as it is incompatible with management through Microsoft Endpoint Configuration Manager because this rule blocks WMI commands the Configuration Manager client uses to function correctly.</span></span> 

> [!TIP]
> <span data-ttu-id="94659-175">Después de incorporar el dispositivo, puedes elegir ejecutar una prueba de detección para comprobar que el dispositivo está correctamente incorporado al servicio.</span><span class="sxs-lookup"><span data-stu-id="94659-175">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="94659-176">Para obtener más información, consulta [Ejecutar una prueba de detección en un dispositivo de Microsoft Defender para endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test)recién incorporado.</span><span class="sxs-lookup"><span data-stu-id="94659-176">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test).</span></span> 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a><span data-ttu-id="94659-177">Etiquetar las máquinas al crear la imagen dorada</span><span class="sxs-lookup"><span data-stu-id="94659-177">Tagging your machines when building your golden image</span></span> 

<span data-ttu-id="94659-178">Como parte de la incorporación, es posible que quieras establecer una etiqueta de máquina para poder diferenciar las máquinas WVD más fácilmente en el Centro de seguridad de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="94659-178">As part of your onboarding, you may want to consider setting a machine tag to be able to differentiate WVD machines more easily in the Microsoft Security Center.</span></span> <span data-ttu-id="94659-179">Para obtener más información, consulta [Agregar etiquetas de dispositivo estableciendo un valor de clave del Registro.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags#add-device-tags-by-setting-a-registry-key-value)</span><span class="sxs-lookup"><span data-stu-id="94659-179">For more information, see [Add device tags by setting a registry key value](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags#add-device-tags-by-setting-a-registry-key-value).</span></span> 

#### <a name="other-recommended-configuration-settings"></a><span data-ttu-id="94659-180">Otras opciones de configuración recomendadas</span><span class="sxs-lookup"><span data-stu-id="94659-180">Other recommended configuration settings</span></span> 

<span data-ttu-id="94659-181">Al crear la imagen dorada, es posible que también quieras configurar la configuración de protección inicial.</span><span class="sxs-lookup"><span data-stu-id="94659-181">When building your golden image, you may want to configure initial protection settings as well.</span></span> <span data-ttu-id="94659-182">Para obtener más información, vea [Otras opciones de configuración recomendadas.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp#other-recommended-configuration-settings)</span><span class="sxs-lookup"><span data-stu-id="94659-182">For more information, see [Other recommended configuration settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp#other-recommended-configuration-settings).</span></span> 

<span data-ttu-id="94659-183">Además, si usa perfiles de usuario FSlogix, se recomienda excluir los siguientes archivos de la protección siempre en uso:</span><span class="sxs-lookup"><span data-stu-id="94659-183">In addition, if you are using FSlogix user profiles, we recommend you exclude the following files from always-on protection:</span></span> 

<span data-ttu-id="94659-184">**Excluir archivos:**</span><span class="sxs-lookup"><span data-stu-id="94659-184">**Exclude Files:**</span></span> 

> <span data-ttu-id="94659-185">%ProgramFiles%\FSLogix\Apps\frxdrv.sys</span><span class="sxs-lookup"><span data-stu-id="94659-185">%ProgramFiles%\FSLogix\Apps\frxdrv.sys</span></span> <br>
> <span data-ttu-id="94659-186">%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys</span><span class="sxs-lookup"><span data-stu-id="94659-186">%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys</span></span> <br>
> <span data-ttu-id="94659-187">%ProgramFiles%\FSLogix\Apps\frxccd.sys</span><span class="sxs-lookup"><span data-stu-id="94659-187">%ProgramFiles%\FSLogix\Apps\frxccd.sys</span></span> <br>
> <span data-ttu-id="94659-188">%TEMP% \* . VHD</span><span class="sxs-lookup"><span data-stu-id="94659-188">%TEMP%\*.VHD</span></span> <br>
> <span data-ttu-id="94659-189">%TEMP% \* . VHDX</span><span class="sxs-lookup"><span data-stu-id="94659-189">%TEMP%\*.VHDX</span></span> <br>
> <span data-ttu-id="94659-190">%Windir%\TEMP \* . VHD</span><span class="sxs-lookup"><span data-stu-id="94659-190">%Windir%\TEMP\*.VHD</span></span> <br>
> <span data-ttu-id="94659-191">%Windir%\TEMP \* . VHDX</span><span class="sxs-lookup"><span data-stu-id="94659-191">%Windir%\TEMP\*.VHDX</span></span> <br>
> <span data-ttu-id="94659-192">\\storageaccount.file.core.windows.net\share \* \* . VHD</span><span class="sxs-lookup"><span data-stu-id="94659-192">\\storageaccount.file.core.windows.net\share\*\*.VHD</span></span> <br>
> <span data-ttu-id="94659-193">\\storageaccount.file.core.windows.net\share \* \* . VHDX</span><span class="sxs-lookup"><span data-stu-id="94659-193">\\storageaccount.file.core.windows.net\share\*\*.VHDX</span></span> <br>

<span data-ttu-id="94659-194">**Excluir procesos:**</span><span class="sxs-lookup"><span data-stu-id="94659-194">**Exclude Processes:**</span></span>

> <span data-ttu-id="94659-195">%ProgramFiles%\FSLogix\Apps\frxccd.exe</span><span class="sxs-lookup"><span data-stu-id="94659-195">%ProgramFiles%\FSLogix\Apps\frxccd.exe</span></span> <br>
> <span data-ttu-id="94659-196">%ProgramFiles%\FSLogix\Apps\frxccds.exe</span><span class="sxs-lookup"><span data-stu-id="94659-196">%ProgramFiles%\FSLogix\Apps\frxccds.exe</span></span> <br>
> <span data-ttu-id="94659-197">%ProgramFiles%\FSLogix\Apps\frxsvc.exe</span><span class="sxs-lookup"><span data-stu-id="94659-197">%ProgramFiles%\FSLogix\Apps\frxsvc.exe</span></span> <br>

#### <a name="licensing-requirements"></a><span data-ttu-id="94659-198">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="94659-198">Licensing requirements</span></span> 

<span data-ttu-id="94659-199">Windows 10 Multi-session es un sistema operativo cliente.</span><span class="sxs-lookup"><span data-stu-id="94659-199">Windows 10 Multi-session is a client OS.</span></span> <span data-ttu-id="94659-200">Los requisitos de licencia para Microsoft Defender para el punto de conexión se pueden encontrar en: [Requisitos de licencias](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="94659-200">Licensing requirements for Microsoft Defender for endpoint can be found at: [Licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>