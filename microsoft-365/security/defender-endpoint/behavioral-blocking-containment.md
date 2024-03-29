---
title: Bloqueo y contención de comportamientos
description: Obtenga información sobre las capacidades de contención y bloqueo de comportamiento en Microsoft Defender para endpoint
keywords: Microsoft Defender para endpoint, EDR en modo de bloqueo, bloqueo de modo pasivo
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: fdaa4d7cbc24ae2ebe28d0856b413f4982fe6b01
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51929054"
---
# <a name="behavioral-blocking-and-containment"></a>Bloqueo y contención de comportamientos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Información general

El panorama de amenazas actual está saturado por [malware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats) sin archivos y que vive fuera de la tierra, amenazas altamente polimórficas que mutan más rápido que las soluciones tradicionales pueden mantenerse al día y ataques operados por humanos que se adaptan a lo que los adversarios encuentran en dispositivos en peligro. Las soluciones de seguridad tradicionales no son suficientes para detener estos ataques; necesitas capacidades de respaldo de inteligencia artificial (IA) y aprendizaje de dispositivos (ML), como el bloqueo y la contención del comportamiento, incluidos [en Defender for Endpoint](https://docs.microsoft.com/windows/security). 

Las capacidades de bloqueo y contención del comportamiento pueden ayudar a identificar y detener las amenazas, en función de sus comportamientos y de los árboles de proceso incluso cuando la amenaza ha comenzado a ejecutarse. Las características y los componentes de protección de última generación, EDR y Defender para endpoint funcionan juntos en las capacidades de contención y bloqueo de comportamiento. 

:::image type="content" source="images/mdatp-next-gen-EDR-behavblockcontain.png" alt-text="Bloqueo y contención de comportamientos":::

Las capacidades de bloqueo de comportamiento y contención funcionan con varios componentes y características de Defender para endpoint para detener los ataques inmediatamente e impedir que los ataques progresen.

- [La protección de última](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) generación (que incluye Antivirus de Microsoft Defender) puede detectar amenazas mediante el análisis de comportamientos y detener las amenazas que se han empezado a ejecutar.

- [La detección y respuesta de puntos](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) de conexión (EDR) recibe señales de seguridad en toda la red, los dispositivos y el comportamiento del kernel. A medida que se detectan las amenazas, se crean alertas. Varias alertas del mismo tipo se agregan a incidentes, lo que facilita al equipo de operaciones de seguridad investigar y responder.

- [Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) tiene una amplia gama de ópticas entre identidades, correo electrónico, datos y aplicaciones, además de las señales de comportamiento de red, punto de conexión y kernel recibidas a través de EDR. Un componente de [Microsoft 365 Defender,](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)Defender para endpoint procesa y correlaciona estas señales, genera alertas de detección y conecta alertas relacionadas en incidentes.

Con estas capacidades, se pueden evitar o bloquear más amenazas, incluso si comienzan a ejecutarse. Cada vez que se detecta un comportamiento sospechoso, se contiene la amenaza, se crean alertas y se detienen las amenazas en sus seguimientos. 

En la siguiente imagen se muestra un ejemplo de una alerta que se desencadenó mediante funciones de bloqueo de comportamiento y contención:

:::image type="content" source="images/blocked-behav-alert.png" alt-text="Ejemplo de alerta mediante bloqueo de comportamiento y contención":::

## <a name="components-of-behavioral-blocking-and-containment"></a>Componentes del bloqueo y la contención del comportamiento

- Reglas de reducción de superficie de **[ataques](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)** controladas por directivas en el cliente Los comportamientos de ataque comunes predefinidos no se pueden ejecutar, de acuerdo con las reglas de reducción de superficie de ataque. Cuando estos comportamientos intentan ejecutarse, se pueden ver en el Centro de seguridad de Microsoft Defender [https://securitycenter.windows.com](https://securitycenter.windows.com) como alertas informativos. (Las reglas de reducción de superficie de ataque no están habilitadas de forma predeterminada; se configuran las directivas en el Centro de seguridad de Microsoft Defender).

- **[Bloqueo de comportamiento del cliente](client-behavioral-blocking.md)** Las amenazas en los puntos de conexión se detectan a través del aprendizaje automático y, a continuación, se bloquean y corrigen automáticamente. (El bloqueo de comportamiento del cliente está habilitado de forma predeterminada). 

- **[Bloqueo de bucle de comentarios](feedback-loop-blocking.md)** (también denominado protección rápida) Las detecciones de amenazas se observan a través de la inteligencia de comportamiento. Las amenazas se detienen e impiden que se ejecuten en otros puntos de conexión. (El bloqueo de bucle de comentarios está habilitado de forma predeterminada). 

- **[Detección y respuesta de extremos (EDR) en modo de bloqueo](edr-in-block-mode.md)** Los artefactos o comportamientos malintencionados que se observan a través de la protección posterior a la infracción se bloquean y contienen. EDR en modo de bloqueo funciona incluso si Antivirus de Microsoft Defender no es la solución antivirus principal. (EDR en modo de bloqueo no está habilitado de forma predeterminada; se activa en el Centro de seguridad de Microsoft Defender). 

Espere más en el área del bloqueo y la contención del comportamiento, ya que Microsoft sigue mejorando las características y capacidades de protección contra amenazas. Para ver lo que se planea y se está implementando ahora, visite la guía básica [de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).

## <a name="examples-of-behavioral-blocking-and-containment-in-action"></a>Ejemplos de bloqueo de comportamiento y contención en la acción

Las capacidades de contención y bloqueo de comportamiento han bloqueado técnicas de atacante, como las siguientes:

- Volcado de credenciales desde LSASS
- Inyección entre procesos
- Acobado de procesos
- Omisión del control de cuentas de usuario
- Manipulación de antivirus (como deshabilitarlo o agregar el malware como exclusión)
- Ponerse en contacto con el comando y el control (C&C) para descargar cargas
- Minería de monedas
- Modificación del registro de arranque
- Ataques pass-the-hash
- Instalación del certificado raíz
- Intento de explotación para varias vulnerabilidades

A continuación se muestran dos ejemplos reales de bloqueo y contención del comportamiento en acción.

### <a name="example-1-credential-theft-attack-against-100-organizations"></a>Ejemplo 1: Ataque de robo de credenciales contra 100 organizaciones

Como se describe en In [hot pursuit of elusive threats: AI-driven behavior-based blocking stops attacks in their tracks](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks), a credential theft attack against 100 organizations around the world was stopped by behavioral blocking and containment capabilities. Los mensajes de correo electrónico de suplantación de identidad (phishing) que contenían un documento de señuelo se enviaron a las organizaciones de destino. Si un destinatario abrió los datos adjuntos, un documento remoto relacionado pudo ejecutar código en el dispositivo del usuario y cargar malware Lokibot, que robaba credenciales, exfiltró datos robados y esperaba instrucciones adicionales de un servidor de comandos y control. 

Los modelos de aprendizaje de dispositivos basados en comportamiento en Defender for Endpoint capturaron y detuvieron las técnicas del atacante en dos puntos de la cadena de ataques:
- La primera capa de protección detectó el comportamiento de vulnerabilidad. Los clasificadores de aprendizaje de dispositivos en la nube identificaron correctamente la amenaza e indicaron inmediatamente al dispositivo cliente que bloqueara el ataque.
- La segunda capa de protección, que ayudó a detener los casos en los que el ataque se atravó más allá de la primera capa, detectó el vacío del proceso, detuvo ese proceso y quitó los archivos correspondientes (como Lokibot). 

Mientras se detectó y detuvo el ataque, las alertas, como una "alerta inicial de acceso", se desencadenaron y aparecieron en el Centro de seguridad de Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ):

:::image type="content" source="images/behavblockcontain-initialaccessalert.png" alt-text="Alerta de acceso inicial en el Centro de seguridad de Microsoft Defender":::

En este ejemplo se muestra cómo los modelos de aprendizaje de dispositivos basados en comportamientos en la nube agregan nuevas capas de protección contra ataques, incluso después de que se han empezado a ejecutar.

### <a name="example-2-ntlm-relay---juicy-potato-malware-variant"></a>Ejemplo 2: retransmisión NTLM: variante de malware de la camote jugosa

Tal como se describe en la entrada de blog reciente, Bloqueo y contención del comportamiento: Transformar la óptica en protección , en enero de 2020, Defender for Endpoint detectó una actividad de escalamiento de [privilegios](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection)en un dispositivo de una organización. Se desencadenó una alerta denominada "Posible escalada de privilegios mediante retransmisión NTLM".

:::image type="content" source="images/NTLMalertjuicypotato.png" alt-text="Alerta NTLM para malware juicy potato":::

La amenaza resultó ser malware; era una nueva variante no vista antes de una herramienta de piratería notoria llamada Juicy Potato, que los atacantes usan para obtener la escalación de privilegios en un dispositivo. 

Minutos después de que se desencadenó la alerta, se analizó el archivo y se confirmó que era malintencionado. Su proceso se detuvo y bloqueó, como se muestra en la siguiente imagen:

:::image type="content" source="images/Artifactblockedjuicypotato.png" alt-text="Artefacto bloqueado":::

Unos minutos después de que se bloqueó el artefacto, se bloquearon varias instancias del mismo archivo en el mismo dispositivo, lo que impedía que otros atacantes u otro malware se implementara en el dispositivo. 

En este ejemplo se muestra que, con las capacidades de contención y bloqueo de comportamiento, las amenazas se detectan, contienen y bloquean automáticamente. 

## <a name="next-steps"></a>Siguientes pasos

- [Más información sobre Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)

- [Configurar las reglas de reducción de superficie de ataque](attack-surface-reduction.md)

- [Habilitar EDR en modo de bloqueo](edr-in-block-mode.md)

- [Ver la actividad de amenazas globales reciente](https://www.microsoft.com/wdsi/threats)

- [Obtener información general sobre Microsoft 365 Defender ](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)
