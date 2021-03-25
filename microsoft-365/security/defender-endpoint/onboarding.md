---
title: Incorporación al servicio ATP de Microsoft Defender
description: Obtenga información sobre cómo incorporar puntos de conexión al servicio ATP de Microsoft Defender
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 56645553c43289995012d53d7caf879874e65c8a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186934"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a>Incorporación al servicio microsoft defender para puntos de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Obtenga información sobre las distintas fases de implementación de Microsoft Defender para endpoint y cómo configurar las funcionalidades de la solución. 

La implementación de Defender for Endpoint es un proceso de tres fases:

| [![fase de implementación: preparar](images/phase-diagrams/prepare.png)](prepare-deployment.md)<br>[Fase 1: Preparar](prepare-deployment.md) | [![fase de implementación: configuración](images/phase-diagrams/setup.png)](production-deployment.md)<br>[Fase 2: Configuración](production-deployment.md) | ![fase de implementación: incorporación](images/phase-diagrams/onboard.png)<br>Fase 3: Incorporación |
| ----- | ----- | ----- |
| | |*¡Estás aquí!*|

Actualmente se encuentra en la fase de incorporación.

Estos son los pasos que debe seguir para implementar Defender for Endpoint:

- Paso 1: Incorporar puntos de conexión al servicio 
- Paso 2: Configurar capacidades 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Paso 1: Incorporar puntos de conexión con cualquiera de las herramientas de administración admitidas
En [el tema Plan deployment](deployment-strategy.md) se describen los pasos generales que debe seguir para implementar Defender for Endpoint.  


Vea este vídeo para obtener una introducción rápida al proceso de incorporación y obtenga información sobre las herramientas y métodos disponibles.
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



Después de identificar la arquitectura, deberá decidir qué método de implementación usar. La herramienta de implementación que elija influye en la forma en que incorpora puntos de conexión al servicio. 

### <a name="onboarding-tool-options"></a>Opciones de la herramienta de incorporación

En la tabla siguiente se enumeran las herramientas disponibles en función del extremo que necesita incorporar.

| Extremo     | Opciones de herramientas                       |
|--------------|------------------------------------------|
| **Windows**  |  [Script local (hasta 10 dispositivos)](configure-endpoints-script.md) <br>  [Directiva de grupo](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/Mobile Device Manager](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [Scripts VDI](configure-endpoints-vdi.md)   |
| **macOS**    | [Scripts locales](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Administración de dispositivos móviles](mac-install-with-other-mdm.md) |
| **Servidor Linux** | [Script local](linux-install-manually.md) <br> [Puppet](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [Basado en aplicaciones](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a>Paso 2: Configurar capacidades
Después de incorporar los puntos de conexión, configurarás las distintas funcionalidades, como la detección y respuesta de puntos de conexión, la protección de próxima generación y la reducción de superficie de ataque. 


## <a name="example-deployments"></a>Implementaciones de ejemplo
En esta guía de implementación, le guiaremos a través del uso de dos herramientas de implementación para incorporar puntos de conexión y cómo configurar las capacidades.

Las herramientas de las implementaciones de ejemplo son:
- [Incorporación con Microsoft Endpoint Configuration Manager](onboarding-endpoint-configuration-manager.md)
- [Incorporación con Microsoft Endpoint Manager](onboarding-endpoint-manager.md)

Con las herramientas de implementación mencionadas anteriormente, se le guiará en la configuración de las siguientes funcionalidades de Defender for Endpoint:
- Detección de extremos y configuración de respuesta
- Configuración de protección de última generación
- Configuración de reducción de superficie de ataque

## <a name="related-topics"></a>Temas relacionados
- [Incorporación con Microsoft Endpoint Configuration Manager](onboarding-endpoint-configuration-manager.md)
- [Incorporación con Microsoft Endpoint Manager](onboarding-endpoint-manager.md)