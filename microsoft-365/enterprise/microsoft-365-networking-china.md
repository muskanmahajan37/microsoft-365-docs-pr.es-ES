---
title: Optimización del rendimiento global de inquilinos de Microsoft 365 para usuarios de China
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/17/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
search.appverid: MET150
f1.keywords:
- NOCSH
description: En este artículo se proporcionan instrucciones para optimizar el rendimiento de la red para los usuarios de China de los inquilinos globales de Microsoft 365.
ms.openlocfilehash: e330e892b584c805bded2228381e74e6a4fa615a
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615200"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Optimización del rendimiento global de inquilinos de Microsoft 365 para usuarios de China

>[!IMPORTANT]
>Esta guía es específica para escenarios de uso en los que los usuarios de **Microsoft 365** de empresa ubicados en China se conectan a un inquilino global de **Microsoft 365.** Esta guía no **se aplica** a los inquilinos de Office 365 operados por 21Vianet.

Para las empresas con inquilinos globales de Microsoft 365 y una presencia corporativa en China, el rendimiento del cliente de Microsoft 365 para usuarios basados en China puede ser complicado por factores exclusivos de la arquitectura de Internet de China Telco.

Los ISP de China han regulado conexiones offshore a Internet pública global que pasan por dispositivos perimetrales propensos a altos niveles de congestión de red transfronteriza. Esta congestión crea pérdida de paquetes y latencia para todo el tráfico de Internet que entra y sale de China.

![Tráfico de Microsoft 365 sin optimizar](../media/O365-networking/China-O365-unoptimized.png)

La pérdida de paquetes y la latencia son perjudiciales para el rendimiento de los servicios de red, especialmente los servicios que requieren grandes intercambios de datos (como transferencias de archivos grandes) o que requieren un rendimiento casi en tiempo real (aplicaciones de audio y vídeo).

El objetivo de este tema es proporcionar procedimientos recomendados para mitigar el impacto de la congestión de red transfronteriza de China en los servicios de Microsoft 365. En este tema no se abordan otros problemas comunes de rendimiento de última milla, como problemas de alta latencia de paquetes debido al enrutamiento complejo dentro de los operadores de China.

## <a name="corporate-network-best-practices"></a>Procedimientos recomendados de red corporativa

Muchas empresas con inquilinos y usuarios globales de Microsoft 365 en China han implementado redes privadas que transportan tráfico de red corporativa entre ubicaciones de oficinas de China y ubicaciones offshore en todo el mundo. Estas empresas pueden aprovechar esta infraestructura de red para evitar la congestión de red transfronteriza y optimizar el rendimiento del servicio de Microsoft 365 en China.

>[!IMPORTANT]
>Al igual que con todas las implementaciones de WAN privadas, siempre debe consultar los requisitos normativos de su país o región para asegurarse de que la configuración de red está en cumplimiento.

Como primer paso, es fundamental que siga nuestra guía de red comparativa en Planificación de red y ajuste del rendimiento [para Microsoft 365](./network-planning-and-performance.md). El objetivo principal debe ser evitar el acceso a los servicios globales de Microsoft 365 desde Internet en China si es posible.

- Aproveche la red privada existente para llevar el tráfico de red de Microsoft 365 entre las redes de oficina de China y las ubicaciones de alta mar que se encuentran fuera de China. Casi cualquier ubicación fuera de China proporcionará una ventaja clara. Los administradores de red pueden optimizar aún más la salida en áreas con una interconexión de baja latencia con la [red global de Microsoft.](https://docs.microsoft.com/azure/networking/microsoft-global-network) Hong Kong, Japón y Corea del Sur son ejemplos.
- Configure los dispositivos de usuario para que accedan a la red corporativa a través de una conexión VPN para permitir que el tráfico de Microsoft 365 transite el vínculo offshore privado de la red corporativa. Asegúrese de que los clientes VPN no estén configurados para usar túnel dividido o de que los dispositivos de usuario estén configurados para omitir el túnel dividido para el tráfico de Microsoft 365. Para obtener información adicional sobre cómo optimizar la conectividad VPN para Teams y el tráfico multimedia en tiempo real, vea [esta sección](#optimizing-microsoft-teams-meetings-network-performance-for-users-in-china).
- Configure la red para enrutar todo el tráfico de Microsoft 365 a través de su vínculo privado offshore. Si debe minimizar el volumen de tráfico en su vínculo privado, puede elegir enrutar  solo  los puntos de conexión en la categoría **Optimizar** y permitir que las solicitudes permitan que los puntos de conexión predeterminados transiten por Internet. Esto mejorará el rendimiento y minimizará el consumo de ancho de banda al limitar el tráfico optimizado a los servicios críticos que son más sensibles a la alta latencia y la pérdida de paquetes.
- Si es posible, usa UDP en lugar de TCP para el tráfico de streaming de medios en directo, como para Teams. UDP ofrece un mejor rendimiento de streaming de medios en directo que TCP.

Para obtener información sobre cómo enrutar selectivamente el tráfico de Microsoft 365, vea [Managing Office 365 endpoints](managing-office-365-endpoints.md). Para obtener una lista de todas las direcciones URL y direcciones IP de Office 365 en todo el mundo, vea Direcciones URL e intervalos de [direcciones IP de Office 365.](urls-and-ip-address-ranges.md)

![Tráfico de Microsoft 365: optimizado](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Procedimientos recomendados para el usuario

Los usuarios de China que se conectan a inquilinos globales de Microsoft 365 desde ubicaciones remotas como casas, cafeterías, hoteles y sucursales sin conexión a redes empresariales pueden experimentar un rendimiento de red deficiente porque el tráfico entre sus dispositivos y Microsoft 365 debe transitar por los circuitos de red transfronterizos congestionados de China.

Si las redes privadas transfronterizas o el acceso VPN a la red corporativa no son una opción, los problemas de rendimiento por usuario aún pueden mitigarse mediante la formación de los usuarios basados en China para que sigan estos procedimientos recomendados.

- Use clientes enriquecidos de Office que admitan el almacenamiento en caché (por ejemplo, Outlook, Teams, OneDrive, etc.) y eviten clientes basados en web. El almacenamiento en caché de clientes de Office y las características de acceso sin conexión pueden reducir considerablemente el impacto de la congestión y la latencia de la red.
- Si el inquilino de Microsoft 365 se ha configurado con la característica _de audioconferencia,_ los usuarios de Teams pueden unirse a reuniones a través de la red telefónica conmutada (RTC). Para obtener más información, [vea Audioconferencia en Office 365](/microsoftteams/audio-conferencing-in-office-365).
- Si los usuarios experimentan problemas de rendimiento de red, deben informar a su departamento de TI para solucionar problemas y escalar a soporte técnico de Microsoft si se sospecha que hay problemas con los servicios de Microsoft 365. No todos los problemas son causados por el rendimiento de la red transfronteriza.

## <a name="optimizing-microsoft-teams-meetings-network-performance-for-users-in-china"></a>Optimizar el rendimiento de la red de reuniones de Microsoft Teams para los usuarios en China  

Para las organizaciones con inquilinos globales de Microsoft 365 y una presencia en China, el rendimiento del cliente de Microsoft 365 para usuarios basados en China puede ser complicado por factores únicos de la arquitectura de Internet de China. Muchas empresas y escuelas han notificado buenos resultados siguiendo esta guía. Sin embargo, el ámbito se limita a las ubicaciones de red de usuario que están bajo control de la configuración de redes de TI, por ejemplo, ubicaciones de oficina o puntos de conexión hogar/móvil con conectividad VPN. Las llamadas y reuniones de Microsoft Teams suelen usarse desde ubicaciones externas, como oficinas en casa, ubicaciones móviles, en la calle y cafeterías. Dado que las llamadas y las reuniones dependen del tráfico multimedia en tiempo real, estas experiencias de Teams son especialmente sensibles a la congestión de la red.

Como resultado, Microsoft se ha asociado con proveedores de telecomunicaciones para llevar el tráfico de medios en tiempo real de Teams y Skype Empresarial Online mediante una ruta de red preferencial de mayor calidad entre las conexiones de Internet nacionales y públicas en China y los servicios de Teams y Skype en la nube global de Microsoft 365. Esta funcionalidad ha dado como resultado una mejora de más de diez veces en la pérdida de paquetes y otras métricas clave que afectan a la experiencia del usuario.

>[!IMPORTANT]
>Actualmente, estas mejoras no abordan la asistencia a reuniones de Eventos de Microsoft Live, como grandes reuniones de difusión o estilo "town hall" con Teams o Microsoft Stream. Para ver una reunión de eventos en directo, los usuarios en China deben usar una red privada o una solución SDWAN/VPN. Sin embargo, las mejoras de red beneficiarán a los usuarios que presenten o produzcan una reunión de live events, ya que esa experiencia actúa como una reunión regular de Teams para el productor o moderador.

### <a name="organization-network-best-practices-for-teams-meetings"></a>Procedimientos recomendados de red de organización para reuniones de Teams

Debe considerar cómo aprovechar estas mejoras de red, dado que las instrucciones anteriores para considerar una extensión de red privada para evitar la congestión de red transfronteriza. Hay dos opciones generales para las redes de oficina de la organización:

1.  No haga nada nuevo. Siga las instrucciones anteriores sobre la omisión de red privada para evitar la congestión transfronteriza. El tráfico multimedia en tiempo real de Teams aprovechará esa configuración, como antes.
2.  Implementar un patrón dividido/híbrido. 

  - Use las instrucciones anteriores para todo el tráfico marcado para la optimización excepto las reuniones de Teams y la llamada al tráfico multimedia en tiempo real.

  - Enruta la reunión de Teams y llama al tráfico multimedia en tiempo real a través de Internet público. Consulte la siguiente información para obtener información específica sobre cómo identificar el tráfico de red multimedia en tiempo real.

Enviar tráfico de audio y vídeo multimedia en tiempo real de Teams a través de Internet público, que usa la conectividad de mayor calidad, puede provocar un ahorro considerable de costos, ya que es gratuito frente a pagar enviar ese tráfico a través de una red privada. Puede haber ventajas adicionales similares si los usuarios también usan clientes SDWAN o VPN. Algunas organizaciones también pueden preferir que más de sus datos atraviesen conexiones públicas a Internet como práctica general.

Las mismas opciones podrían aplicarse a las configuraciones de SDWAN o VPN. Por ejemplo, un usuario usa sdwan o VPN para enrutar el tráfico de Microsoft 365 a la red corporativa y, a continuación, aprovechar la extensión privada de esa red para evitar la congestión transfronteriza. Sdwan o VPN del usuario ahora se pueden configurar para excluir el tráfico de reuniones y llamadas de Teams en tiempo real del enrutamiento VPN. Esta configuración de VPN se conoce como túnel dividido. Consulte [Túnel dividido de VPN para Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-implement-split-tunnel) para obtener más información.

También puedes seguir usando sdwan o VPN para todo el tráfico de Microsoft 365, incluido el tráfico en tiempo real de Microsoft Teams. Microsoft no tiene recomendaciones sobre el uso de soluciones SDWAN o VPN.

### <a name="home-mobile-and-user-network-best-practices-for-teams-meetings"></a>Procedimientos recomendados de red principal, móvil y de usuario para reuniones de Teams

Los usuarios de China pueden aprovechar estas mejoras simplemente conectándose al servicio público de Internet en China con una conexión fija o móvil. El tráfico de audio y vídeo multimedia en tiempo real de Teams en Internet público se beneficia directamente de una mejor conectividad y calidad.

Sin embargo, los datos de otros servicios de Microsoft 365 y otro tráfico en Teams, como chat o archivos, no se beneficiarán directamente de estas mejoras. Los usuarios fuera de la red de la organización aún pueden experimentar un rendimiento de red deficiente para este tráfico. Como se describe en este artículo, puede mitigar estos efectos mediante una VPN o SDWAN. También puede hacer que los usuarios usen clientes de escritorio enriquecidos a través de clientes web, que admiten el almacenamiento en caché desde la aplicación para mitigar problemas de red.

### <a name="identifying-teams-real-time-media-network-traffic"></a>Identificación del tráfico de red multimedia en tiempo real de Teams

Para configurar un dispositivo de red o una configuración de VPN/SDWAN, solo debes excluir el tráfico de audio y vídeo multimedia en tiempo real de Teams. Los detalles de tráfico se pueden encontrar para el identificador 11 en la lista oficial de direcciones URL e intervalos de [direcciones IP de Office 365.](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) Todas las demás configuraciones de red deben permanecer tal y como están.

Microsoft está trabajando continuamente para mejorar la experiencia del usuario de Microsoft 365 y el rendimiento de los clientes en la gama más amplia posible de arquitecturas y características de red. Visite la Comunidad técnica de redes de [Office 365]( https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking) para iniciar o unirse a una conversación, buscar recursos y enviar sugerencias y solicitudes de características

## <a name="related-topics"></a>Temas relacionados

[Planeamiento de red y ajuste del rendimiento para Microsoft 365](./network-planning-and-performance.md)

[Principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Administrar puntos de conexión de Office 365](managing-office-365-endpoints.md)

[Direcciones URL e intervalos de direcciones IP de Office 365](urls-and-ip-address-ranges.md)

[Red global de Microsoft](/azure/networking/microsoft-global-network)