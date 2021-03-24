---
title: Solucionar problemas de alertas o eventos que faltan para ATP de Microsoft Defender para Linux
description: Solucionar problemas de alertas o eventos que faltan en ATP de Microsoft Defender para Linux.
keywords: microsoft, defender, atp, linux, eventos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e489d5bece292065ad2e82a7eb9011747733b4f6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073744"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="bfafd-104">Solucionar problemas de alertas o eventos que faltan para Microsoft Defender para Endpoint para Linux</span><span class="sxs-lookup"><span data-stu-id="bfafd-104">Troubleshoot missing events or alerts issues for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bfafd-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="bfafd-105">**Applies to:**</span></span>

- [<span data-ttu-id="bfafd-106">Microsoft Defender para endpoint para Linux</span><span class="sxs-lookup"><span data-stu-id="bfafd-106">Microsoft Defender for Endpoint for Linux</span></span>](microsoft-defender-endpoint-linux.md)

<span data-ttu-id="bfafd-107">En este artículo se proporcionan algunos pasos generales para mitigar los eventos o alertas que faltan en el portal [del centro de](https://securitycenter.windows.com/) seguridad.</span><span class="sxs-lookup"><span data-stu-id="bfafd-107">This article provides some general steps to mitigate missing events or alerts in the [security center](https://securitycenter.windows.com/) portal.</span></span>

<span data-ttu-id="bfafd-108">Una **vez que Microsoft Defender para endpoint** se  haya instalado correctamente en un dispositivo, se generará una página de dispositivo en el portal.</span><span class="sxs-lookup"><span data-stu-id="bfafd-108">Once **Microsoft Defender for Endpoint** has been installed properly on a device, a _device page_ will be generated in the portal.</span></span> <span data-ttu-id="bfafd-109">Puedes revisar todos los eventos registrados en la pestaña escala de tiempo de la página del dispositivo o en la página de búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="bfafd-109">You can review all recorded events in the timeline tab in the device page, or in advanced hunting page.</span></span> <span data-ttu-id="bfafd-110">En esta sección se soluciona el caso de que faltan algunos o todos los eventos esperados.</span><span class="sxs-lookup"><span data-stu-id="bfafd-110">This section troubleshoots the case of some or all expected events are missing.</span></span>
<span data-ttu-id="bfafd-111">Por ejemplo, si faltan todos los eventos _CreatedFile._</span><span class="sxs-lookup"><span data-stu-id="bfafd-111">For instance, if all _CreatedFile_ events are missing.</span></span>

## <a name="missing-network-and-login-events"></a><span data-ttu-id="bfafd-112">Faltan eventos de red e inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="bfafd-112">Missing network and login events</span></span>

<span data-ttu-id="bfafd-113">Microsoft Defender para endpoint utilizó `audit` el marco de linux para realizar un seguimiento de la actividad de red e inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="bfafd-113">Microsoft Defender for Endpoint utilized `audit` framework from linux to track network and login activity.</span></span>

1. <span data-ttu-id="bfafd-114">Asegúrese de que el marco de auditoría funciona.</span><span class="sxs-lookup"><span data-stu-id="bfafd-114">Make sure audit framework is working.</span></span>

    ```bash
    service auditd status
    ```

    <span data-ttu-id="bfafd-115">salida esperada:</span><span class="sxs-lookup"><span data-stu-id="bfafd-115">expected output:</span></span>

    ```output
    ● auditd.service - Security Auditing Service
    Loaded: loaded (/usr/lib/systemd/system/auditd.service; enabled; vendor preset: enabled)
    Active: active (running) since Mon 2020-12-21 10:48:02 IST; 2 weeks 0 days ago
        Docs: man:auditd(8)
            https://github.com/linux-audit/audit-documentation
    Process: 16689 ExecStartPost=/sbin/augenrules --load (code=exited, status=1/FAILURE)
    Process: 16665 ExecStart=/sbin/auditd (code=exited, status=0/SUCCESS)
    Main PID: 16666 (auditd)
        Tasks: 25
    CGroup: /system.slice/auditd.service
            ├─16666 /sbin/auditd
            ├─16668 /sbin/audispd
            ├─16670 /usr/sbin/sedispatch
            └─16671 /opt/microsoft/mdatp/sbin/mdatp_audisp_plugin -d
    ```

2. <span data-ttu-id="bfafd-116">Si `auditd` está marcado como detenido, indábalo.</span><span class="sxs-lookup"><span data-stu-id="bfafd-116">If `auditd` is marked as stopped, start it.</span></span>

    ```bash
    service auditd start
    ```

<span data-ttu-id="bfafd-117">**En los sistemas SLES,** la auditoría de SYSCALL puede deshabilitarse de forma predeterminada y puede tenerse en cuenta si faltan `auditd` eventos.</span><span class="sxs-lookup"><span data-stu-id="bfafd-117">**On SLES** systems, SYSCALL auditing in `auditd` might be disabled by default and can be accounted for missing events.</span></span>

1. <span data-ttu-id="bfafd-118">Para validar que la auditoría de SYSCALL no está deshabilitada, enumere las reglas de auditoría actuales:</span><span class="sxs-lookup"><span data-stu-id="bfafd-118">To validate that SYSCALL auditing is not disabled, list the current audit rules:</span></span>

    ```bash
    sudo auditctl -l
    ```

    <span data-ttu-id="bfafd-119">si la siguiente línea está presente, quítela o edite para permitir que Microsoft Defender for Endpoint realice un seguimiento de syscalls específicos.</span><span class="sxs-lookup"><span data-stu-id="bfafd-119">if the following line is present, remove it or edit it to enable Microsoft Defender for Endpoint to track specific SYSCALLs.</span></span>

    ```output
    -a task, never
    ```

    <span data-ttu-id="bfafd-120">las reglas de auditoría se encuentran en `/etc/audit/rules.d/audit.rules` .</span><span class="sxs-lookup"><span data-stu-id="bfafd-120">audit rules are located at `/etc/audit/rules.d/audit.rules`.</span></span>

## <a name="missing-file-events"></a><span data-ttu-id="bfafd-121">Eventos de archivo que faltan</span><span class="sxs-lookup"><span data-stu-id="bfafd-121">Missing file events</span></span>

<span data-ttu-id="bfafd-122">Los eventos de archivo se recopilan con `fanotify` framework.</span><span class="sxs-lookup"><span data-stu-id="bfafd-122">File events are collected with `fanotify` framework.</span></span> <span data-ttu-id="bfafd-123">En caso de que falte alguno o todos los eventos de archivo, asegúrese de que está habilitado en el dispositivo y de que el `fanotify` sistema de archivos es [compatible.](microsoft-defender-endpoint-linux.md#system-requirements)</span><span class="sxs-lookup"><span data-stu-id="bfafd-123">In case some or all file events are missing, make sure `fanotify` is enabled on the device and that the file system is [supported](microsoft-defender-endpoint-linux.md#system-requirements).</span></span>

<span data-ttu-id="bfafd-124">Enumere los sistemas de archivos del equipo con:</span><span class="sxs-lookup"><span data-stu-id="bfafd-124">List the filesystems on the machine with:</span></span>

```bash
df -Th
```