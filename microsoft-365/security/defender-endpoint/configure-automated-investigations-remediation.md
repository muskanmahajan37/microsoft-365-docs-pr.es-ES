---
title: Configurar capacidades automatizadas de investigación y corrección
description: Configure las capacidades automatizadas de investigación y corrección en Microsoft Defender para endpoint.
keywords: configure, setup, automated, investigation, detection, alerts, remediation, response
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: 23d6c8c87a6cbcc7b8060440ba2c0cae6182767d
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274549"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a>Configurar las capacidades automatizadas de investigación y corrección en Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Si su organización usa [Microsoft Defender para](https://docs.microsoft.com/windows/security/threat-protection/) endpoint (Defender para endpoint), las capacidades automatizadas de investigación y corrección pueden ahorrar tiempo y esfuerzo al equipo de operaciones de seguridad. [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) Como se describe en [esta entrada de blog,](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)estas capacidades imitan los pasos ideales que un analista de seguridad realiza para investigar y corregir amenazas. [Obtenga más información sobre la investigación automatizada y la corrección](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations). 

Para configurar la investigación y corrección automatizadas,
1. [Activar las características](#turn-on-automated-investigation-and-remediation); y 
2. [Configurar grupos de dispositivos](#set-up-device-groups).

## <a name="turn-on-automated-investigation-and-remediation"></a>Activar la investigación y corrección automatizadas

1. Como administrador global o administrador de seguridad, vaya al Centro de seguridad de Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) e inicie sesión.
2. En el panel de navegación, elija **Configuración**.
3. En la **sección General,** seleccione **Características avanzadas**.
4. Active la investigación **automatizada y** resuelva automáticamente **las alertas**.

## <a name="set-up-device-groups"></a>Configurar grupos de dispositivos

1. En el Centro de seguridad de Microsoft Defender ( ), en la página [https://securitycenter.windows.com](https://securitycenter.windows.com) Configuración, en **Permisos**, seleccione **Grupos de dispositivos**. 
2. Seleccione **+ Agregar grupo de dispositivos**.
3. Crea al menos un grupo de dispositivos de la siguiente manera:
   - Especifica un nombre y una descripción para el grupo de dispositivos.
   - En la **lista Nivel de automatización,** seleccione un nivel, como **Full – remediar las amenazas automáticamente.** El nivel de automatización determina si las acciones de corrección se toman automáticamente o solo tras la aprobación. Para obtener más información, vea [Automation levels in automated investigation and remediation](automation-levels.md).
   - En la **sección Miembros,** use una o más condiciones para identificar e incluir dispositivos.
   - En la **pestaña Acceso de** usuario, seleccione los grupos de Azure Active [Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) que deben tener acceso al grupo de dispositivos que está creando.
4. Selecciona **Listo** cuando termines de configurar el grupo de dispositivos.

## <a name="next-steps"></a>Pasos siguientes

- [Visite el Centro de acciones para ver las acciones de corrección pendientes y completadas](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [Revisar y aprobar acciones pendientes](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a>Vea también

- [Abordar falsos positivos/negativos en Microsoft Defender para punto de conexión](defender-endpoint-false-positives-negatives.md)
