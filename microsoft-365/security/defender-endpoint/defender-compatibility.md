---
title: Compatibilidad de soluciones antivirus con Defender para endpoint
description: Obtenga información sobre Windows Defender funciona con Microsoft Defender para Endpoint y cómo funciona cuando se usa un cliente antimalware de terceros.
keywords: Compatibilidad de windows Defender, defender, Microsoft Defender para endpoint, defender para endpoint, antivirus, mde
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
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: 84c523b721596d9c467f01cf6b8a0685b2091669
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274885"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>Compatibilidad de soluciones antivirus con Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

El agente de Microsoft Defender para endpoints depende del Antivirus de Microsoft Defender para algunas funcionalidades, como el examen de archivos.

>[!IMPORTANT]
>Defender for Endpoint no se adhiere a la configuración de exclusiones de Antivirus de Microsoft Defender. 

Debe configurar las actualizaciones de inteligencia de seguridad en los dispositivos defender para puntos de conexión, independientemente de si Antivirus de Microsoft Defender es el antimalware activo o no. Para obtener más información, vea [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md).

Si un dispositivo incorporado está protegido por un cliente antimalware de terceros, antivirus de Microsoft Defender en ese punto de conexión entrará en modo pasivo.

Antivirus de Microsoft Defender seguirá recibiendo actualizaciones y el proceso *demspeng.exe* aparecerá como un servicio en ejecución, pero no realizará exámenes y no reemplazará al cliente antimalware de terceros en ejecución.

La interfaz de Antivirus de Microsoft Defender se deshabilitará y los usuarios del dispositivo no podrán usar Antivirus de Microsoft Defender para realizar exámenes a petición ni configurar la mayoría de las opciones.

Para obtener más información, vea el tema [de compatibilidad de Microsoft Defender Antivirus y Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).
