---
title: Incidentes en Microsoft 365 Defender
description: Investigar incidentes vistos en dispositivos, usuarios y buzones en el Microsoft 365 de seguridad.
keywords: incidentes, alertas, investigar, analizar, respuesta, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365, respuesta a incidentes, ciberataque
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: cc2fcd7410c2f3122fb3ce49a40e93bfa0767331
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539028"
---
# <a name="incidents-in-microsoft-365-defender"></a>Incidentes en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

> ¿Quiere experimentar Microsoft 365 Defender? Puede [evaluarlo en un entorno de pruebas](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o bien [ejecutar el proyecto piloto en producción](m365d-pilot.md?ocid=cx-evalpilot).
>

Un incidente en Microsoft 365 Defender es una colección de alertas correlacionadas y datos asociados que son la historia de un ataque. 

Microsoft 365 servicios y aplicaciones crean alertas cuando detectan un evento o actividad sospechosos o malintencionados. Las alertas individuales proporcionan pistas valiosas sobre un ataque completado o en curso. Sin embargo, los ataques suelen emplear varias técnicas en distintos tipos de entidades, como dispositivos, usuarios y buzones. El resultado son varias alertas para varias entidades del espacio empresarial. 

Dado que unir las alertas individuales para obtener información sobre un ataque puede ser un desafío y un consumo de tiempo, Microsoft 365 Defender agrega automáticamente las alertas y su información asociada a un incidente.

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Cómo Microsoft 365 Defender correlaciona eventos de entidades en un incidente":::

Vea esta breve introducción a los incidentes en Microsoft 365 Defender (4 minutos).

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

La agrupación de alertas relacionadas en un incidente le ofrece una vista completa de un ataque. Por ejemplo, puede ver:

- Donde se inició el ataque.
- Qué tácticas se usaron.
- Cuánto ha llegado el ataque a su inquilino.
- El ámbito del ataque, como el número de dispositivos, usuarios y buzones de correo afectados. 
- Todos los datos asociados con el ataque.

Si [está habilitado,](m365d-enable.md)Microsoft 365 Defender puede [investigar y](m365d-autoir.md) resolver alertas automáticamente a través de la automatización y la inteligencia artificial. También puedes realizar pasos de corrección adicionales para resolver el ataque. 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a>Incidentes y alertas en el centro Microsoft 365 seguridad

Puede administrar incidentes de **incidentes & alertas > incidentes en** el inicio rápido del centro de seguridad de Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)). Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="La página Incidentes en el centro de Microsoft 365 seguridad":::

Al seleccionar un nombre de incidente, se muestra un resumen del incidente y se proporciona acceso a las pestañas con información adicional.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Ejemplo de la página Resumen de un incidente en el centro Microsoft 365 seguridad":::

Las pestañas adicionales para un incidente son:

- Alertas 

  Todas las alertas relacionadas con el incidente y su información.

- Dispositivos

  Todos los dispositivos que se han identificado para formar parte o relacionados con el incidente.

- Usuarios

  Todos los usuarios identificados para formar parte del incidente o relacionados con ellos.

- Buzones

  Todos los buzones que se han identificado para formar parte o relacionados con el incidente.

- Investigaciones

  Todas las [investigaciones automatizadas desencadenadas](m365d-autoir.md) por alertas en el incidente.

- Evidencia y respuesta

  Todos los eventos admitidos y las entidades sospechosas en las alertas del incidente.

- Graph (en versión preliminar)

  Una figura que muestra la conexión de alertas a los activos afectados de la organización.

Esta es la relación entre un incidente y sus datos y las pestañas de un incidente en el centro Microsoft 365 seguridad.

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="La relación de un incidente y sus datos con las pestañas de un incidente en el centro Microsoft 365 seguridad":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>Flujo de trabajo de respuesta a incidentes de ejemplo para Microsoft 365 Defender

Este es un flujo de trabajo de ejemplo para responder a incidentes en Microsoft 365 con el centro Microsoft 365 seguridad.

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Ejemplo de flujo de trabajo de respuesta a incidentes para Microsoft 365":::

De forma continua, identifique los incidentes de mayor prioridad para el análisis y la resolución en la cola de incidentes y prepárese para la respuesta. Esta es una combinación de:

- [Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.
- [Administrar](manage-incidents.md) incidentes modificando su título, asignándolos a un analista y agregando etiquetas y comentarios.

1. Para cada incidente, inicie una investigación y análisis de [ataques y alertas:](investigate-incidents.md)
 
   a. Vea el resumen del incidente para comprender su ámbito y gravedad y qué entidades se ven afectadas (la **pestaña Resumen).**

   b. Comience a analizar las alertas para comprender su origen, ámbito y gravedad (la **pestaña** Alertas).

   c. Según sea necesario, recopila información sobre dispositivos, usuarios y buzones afectados (las pestañas **Dispositivos,** **Usuarios** y **Buzones).**

   d. Vea cómo Microsoft 365 Defender ha [resuelto automáticamente algunas](m365d-autoir.md) alertas (la pestaña **Investigaciones).**
   
   e. Según sea necesario, use la información del conjunto de datos para el incidente para obtener más información (la **pestaña Evidencia y** respuesta).

2. Después o durante el análisis, realice la contención para reducir cualquier impacto adicional del ataque y la eliminación de la amenaza de seguridad.

3. En la medida de lo posible, recuperándose del ataque restaurando los recursos del espacio empresarial al estado en el que se encontraban antes del incidente.

4. [Resuelva](manage-incidents.md#resolve-an-incident) el incidente y tome tiempo para aprender después del incidente a:

   - Comprender el tipo de ataque y su impacto.
   - Investigue el ataque en [Análisis de amenazas](threat-analytics.md) y la comunidad de seguridad para obtener una tendencia de ataque de seguridad.
   - Recuerde el flujo de trabajo que usó para resolver el incidente y actualice los flujos de trabajo, procesos, directivas y libros de reproducción estándar según sea necesario.
   - Determine si es necesario realizar cambios en la configuración de seguridad e implementarlos.

Si es nuevo en el [](incidents-overview.md) análisis de seguridad, vea la introducción para responder al primer incidente para obtener información adicional y para pasar por un incidente de ejemplo.

## <a name="example-security-operations-for-microsoft-365-defender"></a>Operaciones de seguridad de ejemplo para Microsoft 365 Defender

Este es un ejemplo de operaciones de seguridad para Microsoft 365 Defender.

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Un ejemplo de operaciones de seguridad para Microsoft 365 Defender":::

Las tareas diarias pueden incluir:

- [Administración](manage-incidents.md) de incidentes
- Revisión [de acciones de investigación y respuesta automatizadas (AIR)](m365d-action-center.md) en el Centro de acciones
- Revisión de los análisis [de amenazas más recientes](threat-analytics.md)
- [Responder a](investigate-incidents.md) incidentes

Las tareas mensuales pueden incluir:

- Revisión de [la configuración de AIR](m365d-configure-auto-investigation-response.md)
- Revisión [de la puntuación segura](microsoft-secure-score-improvement-actions.md) y la administración & [vulnerabilidades](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- Informes en la cadena de administración de seguridad de IT

Las tareas trimestrales pueden incluir un informe y un informe de los resultados de seguridad al director de seguridad de la información (CISO).

Las tareas anuales pueden incluir llevar a cabo un ejercicio importante de incidentes o infracciones para probar el personal, los sistemas y los procesos. 

Las tareas diarias, mensuales, trimestrales y anuales se pueden usar para actualizar o refinar procesos, directivas y configuraciones de seguridad.

## <a name="next-steps"></a>Pasos siguientes

**Si es nuevo en el análisis** de seguridad y la respuesta a incidentes:

- Consulte [el](first-incident-overview.md) tutorial Responder a su primer incidente para obtener una visita guiada de un proceso típico de análisis, corrección y revisión posterior al incidente en el centro de seguridad de Microsoft 365 con un ejemplo de un ataque.

**Si tiene experiencia con el análisis** de seguridad y la respuesta a incidentes:

- Introducción a la cola de incidentes desde la **página Incidentes** del centro Microsoft 365 seguridad. Desde ahí, puede hacer lo siguiente:

  - Vea qué incidentes deben [priorizarse en](incident-queue.md) función de la gravedad y otros factores. 

  - [Administrar incidentes, que](manage-incidents.md)incluye cambiar el nombre, la asignación, clasificar y agregar etiquetas y comentarios en función del flujo de trabajo de administración de incidentes.

  - Realizar [investigaciones](investigate-incidents.md) de incidentes.

- Consulta estos [libros de reproducción de respuesta a](https://docs.microsoft.com/security/compass/incident-response-playbooks) incidentes para obtener instrucciones detalladas sobre los ataques de suplantación de identidad (phishing), el uso de contraseñas y la concesión de consentimiento de la aplicación.

