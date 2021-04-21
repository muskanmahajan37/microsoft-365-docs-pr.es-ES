---
title: Configurar y validar las conexiones de red del Antivirus de Windows Defender
description: Configure y pruebe la conexión con el servicio de protección en la nube de Antivirus de Microsoft Defender.
keywords: antivirus, Antivirus de Microsoft Defender, antimalware, seguridad, defender, nube, agresividad, nivel de protección
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6218bc32690ca42c06b5606d8a3922f6fc5c7307
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765160"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a><span data-ttu-id="22659-104">Configurar y validar las conexiones de red del Antivirus de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="22659-104">Configure and validate Microsoft Defender Antivirus network connections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="22659-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="22659-105">**Applies to:**</span></span>

- [<span data-ttu-id="22659-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="22659-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="22659-107">Para asegurarse de que la protección en la nube de Antivirus de Microsoft Defender funciona correctamente, debe configurar la red para permitir conexiones entre los puntos de conexión y determinados servidores de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="22659-107">To ensure Microsoft Defender Antivirus cloud-delivered protection works properly, you need to configure your network to allow connections between your endpoints and certain Microsoft servers.</span></span>

<span data-ttu-id="22659-108">En este artículo se enumeran las conexiones que se deben permitir, como mediante reglas de firewall, y se proporcionan instrucciones para validar la conexión.</span><span class="sxs-lookup"><span data-stu-id="22659-108">This article lists the connections that must be allowed, such as by using firewall rules, and provides instructions for validating your connection.</span></span> <span data-ttu-id="22659-109">La configuración correcta de la protección ayuda a garantizar que recibe el mejor valor de los servicios de protección entregados en la nube.</span><span class="sxs-lookup"><span data-stu-id="22659-109">Configuring your protection properly helps ensure that you receive the best value from your cloud-delivered protection services.</span></span>

<span data-ttu-id="22659-110">Consulta la entrada de blog [Cambios importantes en el punto](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) de conexión de Microsoft Active Protection Services para obtener algunos detalles sobre la conectividad de red.</span><span class="sxs-lookup"><span data-stu-id="22659-110">See the blog post [Important changes to Microsoft Active Protection Services endpoint](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) for some details about network connectivity.</span></span>

>[!TIP]
><span data-ttu-id="22659-111">También puede visitar el sitio web de demostración de Microsoft Defender para endpoint [en demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que funcionan las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="22659-111">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
>
>- <span data-ttu-id="22659-112">Protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="22659-112">Cloud-delivered protection</span></span>
>- <span data-ttu-id="22659-113">Aprendizaje rápido (incluido el bloqueo a primera vista)</span><span class="sxs-lookup"><span data-stu-id="22659-113">Fast learning (including block at first sight)</span></span>
>- <span data-ttu-id="22659-114">Bloqueo de aplicaciones potencialmente no deseado</span><span class="sxs-lookup"><span data-stu-id="22659-114">Potentially unwanted application blocking</span></span>

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a><span data-ttu-id="22659-115">Permitir conexiones al servicio en la nube de Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="22659-115">Allow connections to the Microsoft Defender Antivirus cloud service</span></span>

<span data-ttu-id="22659-116">El servicio en la nube de Antivirus de Microsoft Defender proporciona una protección rápida y segura para los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="22659-116">The Microsoft Defender Antivirus cloud service provides fast, strong protection for your endpoints.</span></span> <span data-ttu-id="22659-117">Habilitar el servicio de protección entregado en la nube es opcional, pero es muy recomendable porque proporciona protección importante contra malware en los puntos de conexión y en toda la red.</span><span class="sxs-lookup"><span data-stu-id="22659-117">Enabling the cloud-delivered protection service is optional, however it's highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

>[!NOTE]
><span data-ttu-id="22659-118">El servicio en la nube de Antivirus de Microsoft Defender es un mecanismo para ofrecer protección actualizada a la red y los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="22659-118">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="22659-119">Aunque se denomina servicio en la nube, no es simplemente protección para los archivos almacenados en la nube, sino que usa recursos distribuidos y aprendizaje automático para ofrecer protección a los puntos de conexión a una velocidad mucho más rápida que las actualizaciones de inteligencia de seguridad tradicionales.</span><span class="sxs-lookup"><span data-stu-id="22659-119">Although it's called a cloud service, it's not simply protection for files stored in the cloud, rather it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="22659-120">Consulte [Enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) para obtener más información sobre cómo habilitar el servicio con Intune, Microsoft Endpoint Configuration Manager, directiva de grupo, cmdlets de PowerShell o en clientes individuales en la aplicación seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="22659-120">See [Enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) for details on enabling the service with Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, or on individual clients in the Windows Security app.</span></span> 

<span data-ttu-id="22659-121">Después de habilitar el servicio, es posible que deba configurar la red o firewall para permitir conexiones entre él y los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="22659-121">After you've enabled the service, you may need to configure your network or firewall to allow connections between it and your endpoints.</span></span>

<span data-ttu-id="22659-122">Dado que la protección es un servicio en la nube, los equipos deben tener acceso a Internet y llegar a los servicios de aprendizaje automático de Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="22659-122">Because your protection is a cloud service, computers must have access to the internet and reach the Microsoft Defender for Office 365 machine learning services.</span></span> <span data-ttu-id="22659-123">No excluya la dirección URL `*.blob.core.windows.net` de ningún tipo de inspección de red.</span><span class="sxs-lookup"><span data-stu-id="22659-123">Don't exclude the URL `*.blob.core.windows.net` from any kind of network inspection.</span></span> 

<span data-ttu-id="22659-124">En la tabla siguiente se enumeran los servicios y sus direcciones URL asociadas.</span><span class="sxs-lookup"><span data-stu-id="22659-124">The table below lists the services and their associated URLs.</span></span> <span data-ttu-id="22659-125">Asegúrese de que no hay reglas de filtrado de red o firewall que denieguen el acceso a estas direcciones URL, o puede que necesite crear una regla de permitido específicamente para ellas (excluyendo la dirección `*.blob.core.windows.net` URL).</span><span class="sxs-lookup"><span data-stu-id="22659-125">Make sure that there are no firewall or network filtering rules denying access to these URLs, or you may need to create an allow rule specifically for them (excluding the URL `*.blob.core.windows.net`).</span></span> <span data-ttu-id="22659-126">A continuación se menciona que las direcciones URL usan el puerto 443 para la comunicación.</span><span class="sxs-lookup"><span data-stu-id="22659-126">Below mention URLs are using port 443 for communication.</span></span>


| <span data-ttu-id="22659-127">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="22659-127">**Service**</span></span>| <span data-ttu-id="22659-128">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="22659-128">**Description**</span></span> |<span data-ttu-id="22659-129">**URL**</span><span class="sxs-lookup"><span data-stu-id="22659-129">**URL**</span></span> |
| :--: | :-- | :-- |
| <span data-ttu-id="22659-130">Servicio de protección entregado en la nube de Antivirus de Microsoft Defender, también conocido como Servicio de Protección activa de Microsoft (MAPS)</span><span class="sxs-lookup"><span data-stu-id="22659-130">Microsoft Defender Antivirus cloud-delivered protection service, also referred to as Microsoft Active Protection Service (MAPS)</span></span>|<span data-ttu-id="22659-131">Usado por Microsoft Defender Antivirus para proporcionar protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="22659-131">Used by Microsoft Defender Antivirus to provide cloud-delivered protection</span></span>|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| <span data-ttu-id="22659-132">Servicio de Microsoft Update (MU)</span><span class="sxs-lookup"><span data-stu-id="22659-132">Microsoft Update Service (MU)</span></span> <br/> <span data-ttu-id="22659-133">Servicio de Windows Update (WU)</span><span class="sxs-lookup"><span data-stu-id="22659-133">Windows Update Service (WU)</span></span>|  <span data-ttu-id="22659-134">Inteligencia de seguridad y actualizaciones de productos</span><span class="sxs-lookup"><span data-stu-id="22659-134">Security intelligence and product updates</span></span>   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> <span data-ttu-id="22659-135">Para obtener más [información, consulta Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span><span class="sxs-lookup"><span data-stu-id="22659-135">For details see [Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span></span>|
|<span data-ttu-id="22659-136">Actualizaciones de inteligencia de seguridad Ubicación alternativa de descarga (ADL)</span><span class="sxs-lookup"><span data-stu-id="22659-136">Security intelligence updates Alternate Download Location (ADL)</span></span>|   <span data-ttu-id="22659-137">Ubicación alternativa para las actualizaciones de inteligencia de Seguridad antivirus de Microsoft Defender si la inteligencia de seguridad instalada no está actualizada (7 o más días después)</span><span class="sxs-lookup"><span data-stu-id="22659-137">Alternate location for Microsoft Defender Antivirus Security intelligence updates if the installed Security intelligence is out of date (7 or more days behind)</span></span>|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| <span data-ttu-id="22659-138">Almacenamiento de envío de malware</span><span class="sxs-lookup"><span data-stu-id="22659-138">Malware submission storage</span></span>|<span data-ttu-id="22659-139">Ubicación de carga de los archivos enviados a Microsoft mediante el formulario de envío o el envío automático de ejemplo</span><span class="sxs-lookup"><span data-stu-id="22659-139">Upload location for files submitted to Microsoft via the Submission form or automatic sample submission</span></span>    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| <span data-ttu-id="22659-140">Lista de revocación de certificados (CRL)</span><span class="sxs-lookup"><span data-stu-id="22659-140">Certificate Revocation List (CRL)</span></span>|<span data-ttu-id="22659-141">Usado por Windows al crear la conexión SSL a MAPS para actualizar la CRL</span><span class="sxs-lookup"><span data-stu-id="22659-141">Used by Windows when creating the SSL connection to MAPS for updating the CRL</span></span>   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| <span data-ttu-id="22659-142">Almacén de símbolos</span><span class="sxs-lookup"><span data-stu-id="22659-142">Symbol Store</span></span>|<span data-ttu-id="22659-143">Usado por Microsoft Defender Antivirus para restaurar determinados archivos críticos durante los flujos de corrección</span><span class="sxs-lookup"><span data-stu-id="22659-143">Used by Microsoft Defender Antivirus to restore certain critical files during remediation flows</span></span>  | `https://msdl.microsoft.com/download/symbols` |
| <span data-ttu-id="22659-144">Cliente de telemetría universal</span><span class="sxs-lookup"><span data-stu-id="22659-144">Universal Telemetry Client</span></span>| <span data-ttu-id="22659-145">Usado por Windows para enviar datos de diagnóstico de cliente; Antivirus de Microsoft Defender usa telemetría con fines de supervisión de la calidad del producto</span><span class="sxs-lookup"><span data-stu-id="22659-145">Used by Windows to send client diagnostic data; Microsoft Defender Antivirus uses telemetry for product quality monitoring purposes</span></span>   | <span data-ttu-id="22659-146">La actualización usa SSL (puerto TCP 443) para descargar manifiestos y cargar datos de diagnóstico en Microsoft que usa los siguientes extremos DNS:   `vortex-win.data.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="22659-146">The update uses SSL (TCP Port 443) to download manifests and upload diagnostic data to Microsoft that uses the following DNS endpoints:   `vortex-win.data.microsoft.com`</span></span> <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a><span data-ttu-id="22659-147">Validar conexiones entre la red y la nube</span><span class="sxs-lookup"><span data-stu-id="22659-147">Validate connections between your network and the cloud</span></span>

<span data-ttu-id="22659-148">Después de permitir las direcciones URL enumeradas anteriormente, puede probar si está conectado al servicio en la nube de Antivirus de Microsoft Defender y está informando y recibiendo información correctamente para asegurarse de que está totalmente protegido.</span><span class="sxs-lookup"><span data-stu-id="22659-148">After allowing the URLs listed above, you can test if you're connected to the Microsoft Defender Antivirus cloud service and are correctly reporting and receiving information to ensure you're fully protected.</span></span>

<span data-ttu-id="22659-149">**Use la herramienta cmdline para validar la protección entregada en la nube:**</span><span class="sxs-lookup"><span data-stu-id="22659-149">**Use the cmdline tool to validate cloud-delivered protection:**</span></span>

<span data-ttu-id="22659-150">Use el siguiente argumento con la utilidad de línea de comandos antivirus de Microsoft Defender ( ) para comprobar que la red se puede comunicar con el servicio en la nube `mpcmdrun.exe` antivirus de Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="22659-150">Use the following argument with the Microsoft Defender Antivirus command-line utility (`mpcmdrun.exe`) to verify that your network can communicate with the Microsoft Defender Antivirus cloud service:</span></span>

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> <span data-ttu-id="22659-151">Debe abrir una versión de nivel de administrador del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="22659-151">You need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="22659-152">Haga clic con el botón secundario en el elemento del menú Inicio, haga clic **en Ejecutar como administrador** y haga clic en Sí **en** el símbolo del sistema de permisos.</span><span class="sxs-lookup"><span data-stu-id="22659-152">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span> <span data-ttu-id="22659-153">Este comando solo funcionará en Windows 10, versión 1703 o posterior.</span><span class="sxs-lookup"><span data-stu-id="22659-153">This command will only work on Windows 10, version 1703 or higher.</span></span>

<span data-ttu-id="22659-154">Para obtener más información, vea [Manage Microsoft Defender Antivirus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="22659-154">For more information, see [Manage Microsoft Defender Antivirus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="22659-155">**Intentar descargar un archivo de malware falso de Microsoft:**</span><span class="sxs-lookup"><span data-stu-id="22659-155">**Attempt to download a fake malware file from Microsoft:**</span></span>

<span data-ttu-id="22659-156">Puedes descargar un archivo de ejemplo que Antivirus de Microsoft Defender detectará y bloqueará si estás conectado correctamente a la nube.</span><span class="sxs-lookup"><span data-stu-id="22659-156">You can download a sample file that Microsoft Defender Antivirus will detect and block if you're properly connected to the cloud.</span></span>

<span data-ttu-id="22659-157">Descargue el archivo visitando [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .</span><span class="sxs-lookup"><span data-stu-id="22659-157">Download the file by visiting [https://aka.ms/ioavtest](https://aka.ms/ioavtest).</span></span>

>[!NOTE]
><span data-ttu-id="22659-158">Este archivo no es una parte real de malware.</span><span class="sxs-lookup"><span data-stu-id="22659-158">This file is not an actual piece of malware.</span></span> <span data-ttu-id="22659-159">Es un archivo falso que está diseñado para probar si estás conectado correctamente a la nube.</span><span class="sxs-lookup"><span data-stu-id="22659-159">It's a fake file that is designed to test if you're properly connected to the cloud.</span></span>

<span data-ttu-id="22659-160">Si estás conectado correctamente, verás una notificación de Antivirus de Microsoft Defender de advertencia.</span><span class="sxs-lookup"><span data-stu-id="22659-160">If you're properly connected, you'll see a warning Microsoft Defender Antivirus notification.</span></span>

<span data-ttu-id="22659-161">Si usa Microsoft Edge, también verá un mensaje de notificación:</span><span class="sxs-lookup"><span data-stu-id="22659-161">If you're using Microsoft Edge, you'll also see a notification message:</span></span>

![Microsoft Edge informando al usuario de que se encontró malware](images/defender/wdav-bafs-edge.png)

<span data-ttu-id="22659-163">Si usa Internet Explorer, se produce un mensaje similar:</span><span class="sxs-lookup"><span data-stu-id="22659-163">A similar message occurs if you're using Internet Explorer:</span></span>

![Notificación de Antivirus de Microsoft Defender que informa al usuario de que se encontró malware](images/defender/wdav-bafs-ie.png)

<span data-ttu-id="22659-165">También verás una detección en **Amenazas** en cuarentena en **la** sección Historial de análisis de la aplicación Seguridad de Windows:</span><span class="sxs-lookup"><span data-stu-id="22659-165">You'll also see a detection under **Quarantined threats** in the **Scan history** section in the Windows Security app:</span></span>

1. <span data-ttu-id="22659-166">Abre la aplicación Seguridad de Windows haciendo clic en el icono de escudo de la barra de tareas o buscando en el menú inicio de **Defender**.</span><span class="sxs-lookup"><span data-stu-id="22659-166">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="22659-167">Seleccione el **icono Protección contra &** virus (o el icono de escudo de la barra de menús izquierda) y, a continuación, la etiqueta Historial **de** análisis:</span><span class="sxs-lookup"><span data-stu-id="22659-167">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Scan history** label:</span></span>

    ![Captura de pantalla de la etiqueta Historial de análisis en la aplicación Seguridad de Windows](images/defender/wdav-history-wdsc.png)

3. <span data-ttu-id="22659-169">En la **sección Amenazas en** cuarentena, seleccione Ver historial **completo** para ver el malware falso detectado.</span><span class="sxs-lookup"><span data-stu-id="22659-169">Under the **Quarantined threats** section, select **See full history** to see the detected fake malware.</span></span>

   > [!NOTE]
   > <span data-ttu-id="22659-170">Las versiones de Windows 10 anteriores a la versión 1703 tienen una interfaz de usuario diferente.</span><span class="sxs-lookup"><span data-stu-id="22659-170">Versions of Windows 10 before version 1703 have a different user interface.</span></span> <span data-ttu-id="22659-171">Consulta [Antivirus de Microsoft Defender en la aplicación seguridad de Windows](microsoft-defender-security-center-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="22659-171">See [Microsoft Defender Antivirus in the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

   <span data-ttu-id="22659-172">El registro de eventos de Windows también mostrará Windows Defender [identificador de evento de cliente 1116](troubleshoot-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="22659-172">The Windows event log will also show [Windows Defender client event ID 1116](troubleshoot-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="22659-173">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="22659-173">Related articles</span></span>

- [<span data-ttu-id="22659-174">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="22659-174">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="22659-175">Habilitar la protección de entrega en la nube</span><span class="sxs-lookup"><span data-stu-id="22659-175">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="22659-176">Argumentos de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="22659-176">Command line arguments</span></span>](command-line-arguments-microsoft-defender-antivirus.md)

- [<span data-ttu-id="22659-177">Cambios importantes en el punto de conexión de Microsoft Active Protection Services</span><span class="sxs-lookup"><span data-stu-id="22659-177">Important changes to Microsoft Active Protection Services endpoint</span></span>](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)