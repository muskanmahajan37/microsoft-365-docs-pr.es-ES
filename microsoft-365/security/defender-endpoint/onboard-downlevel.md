---
title: Incorporación de versiones anteriores de Windows en Microsoft Defender para endpoint
description: Incorporación de versiones anteriores compatibles de dispositivos Windows para que puedan enviar datos del sensor al sensor de Microsoft Defender para endpoint
keywords: onboard, windows, 7, 81, oms, sp1, enterprise, pro, down level
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 945645e0f20f316c094f746adb6ba193f6806f86
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861364"
---
# <a name="onboard-previous-versions-of-windows"></a>Incorporar versiones anteriores de Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plataformas**
- Windows 7 SP1 Enterprise
- Windows 7 SP1 Pro
- Windows 8.1 Pro
- Windows 8.1 Enterprise


>¿Desea experimentar Defender for Endpoint? [Registrarse para obtener una versión de prueba gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).

Defender for Endpoint amplía la compatibilidad para incluir sistemas operativos de nivel inferior, lo que proporciona capacidades avanzadas de detección de ataques e investigación en versiones compatibles de Windows.

Para incorporar puntos de conexión de cliente de Windows de nivel inferior a Defender for Endpoint, tendrás que:
- Configurar y actualizar clientes de System Center Endpoint Protection.
- Instale y configure Microsoft Monitoring Agent (MMA) para informar de los datos del sensor a Defender for Endpoint como se indica a continuación.

> [!TIP]
> Después de incorporar el dispositivo, puedes elegir ejecutar una prueba de detección para comprobar que está correctamente incorporado al servicio. Para obtener más información, vea [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>Configurar y actualizar clientes de System Center Endpoint Protection
> [!IMPORTANT]
> Este paso solo es necesario si su organización usa System Center Endpoint Protection (SCEP).

Defender for Endpoint se integra con System Center Endpoint Protection para proporcionar visibilidad a las detecciones de malware y detener la propagación de un ataque en la organización mediante la prohibición de archivos potencialmente malintencionados o malware sospechoso. 

Se requieren los siguientes pasos para habilitar esta integración: 
- Instalar la actualización de la plataforma antimalware de enero de [2017 para clientes de Endpoint Protection](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie) 
- Configurar la pertenencia del servicio de protección en la nube del cliente SCEP a la **configuración** Avanzada
- Configure la red para permitir conexiones a la nube de Antivirus de Microsoft Defender. Para obtener más información, vea [Allow connections to the Microsoft Defender Antivirus cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>Instalar y configurar Microsoft Monitoring Agent (MMA) para informar de los datos del sensor a Microsoft Defender para endpoint

### <a name="before-you-begin"></a>Antes de empezar
Revise los siguientes detalles para comprobar los requisitos mínimos del sistema:
- Instalar el paquete acumulativo de actualizaciones [mensuales de febrero de 2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
  
  > [!NOTE]
  > Solo se aplica a Windows 7 SP1 Enterprise y Windows 7 SP1 Pro. 

- Instalar la actualización [para la experiencia del cliente y telemetría de diagnóstico](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

- Instalar [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o posterior) o [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

    > [!NOTE]
    > Solo se aplica a Windows 7 SP1 Enterprise y Windows 7 SP1 Pro.
    > No instales .NET Framework 4.0.x, ya que anulará la instalación anterior.

- Cumpla los requisitos mínimos del sistema del agente de Azure Log Analytics. Para obtener más información, vea [Recopilar datos de equipos en su entorno con Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)



1. Descargue el archivo de instalación del agente: agente de [Windows 64 bits](https://go.microsoft.com/fwlink/?LinkId=828603) o agente de [Windows 32 bits](https://go.microsoft.com/fwlink/?LinkId=828604).

2. Obtenga el identificador del área de trabajo:
   - En el panel de navegación Defender para endpoint, seleccione **Configuración > Administración de dispositivos > incorporación**
   - Seleccionar **Windows 7 SP1 y 8.1** como sistema operativo
   - Copiar el identificador del área de trabajo y la clave del área de trabajo

3. Con el identificador de área de trabajo y la clave Área de trabajo, elija cualquiera de los siguientes métodos de instalación para instalar el agente:
    - [Instale manualmente el agente mediante el programa de instalación](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard). <br>
      En la **página Opciones de configuración del agente,** seleccione Conectar el agente a Azure Log Analytics **(OMS)**
    - [Instale el agente mediante la línea de comandos](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).
    - [Configure el agente mediante un script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).

   > [!NOTE]
   > Si es cliente de [Us Government](gov.md), en "Azure Cloud" tendrá que elegir "Azure US Government" si usa el asistente para la instalación, o si usa una línea de comandos o un script: establezca el parámetro "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" en 1.

4. Si usa un proxy para conectarse a Internet, consulte la sección Configurar opciones de proxy.

Una vez completado, debería ver puntos de conexión incorporados en el portal en una hora.

### <a name="configure-proxy-and-internet-connectivity-settings"></a>Configurar las opciones del proxy y de conectividad a Internet
 
- Cada extremo de Windows debe poder conectarse a Internet mediante HTTPS. Esta conexión puede ser directa, mediante un proxy o a través de la puerta [de enlace OMS](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway).
- Si un proxy o firewall bloquea todo el tráfico de forma predeterminada y permite solo dominios específicos a través o el examen HTTPS (inspección SSL) está habilitado, asegúrese de habilitar el acceso a las direcciones URL del servicio [defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)para puntos de conexión .

## <a name="offboard-client-endpoints"></a>Extremos de cliente offboard
To offboard, you can uninstall the MMA agent from the endpoint or detach it from reporting to your Defender for Endpoint workspace. Después de salir del agente, el punto de conexión ya no enviará datos del sensor a Defender para Endpoint. 

> ¿Desea experimentar Defender for Endpoint? [Registrarse para obtener una versión de prueba gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).

