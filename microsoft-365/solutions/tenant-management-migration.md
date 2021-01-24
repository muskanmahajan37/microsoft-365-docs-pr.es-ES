---
title: Paso 4. Migración de los inquilinos de Microsoft 365 para empresas
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Migre los dispositivos Windows, las aplicaciones cliente de Office y los servidores de Office para los inquilinos de Microsoft 365.
ms.openlocfilehash: 3230f7e1087b573691f04b9335a15b4ad6d20b65
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908755"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a>Paso 4. Migración de los inquilinos de Microsoft 365 para empresas

La mayoría de las organizaciones empresariales tienen un entorno heterogéneo que incluye varias versiones de sistemas operativos, software cliente y software de servidor. Microsoft 365 para empresas incluye las versiones más seguras de los componentes clave de su infraestructura de TI. También incluye características de productividad diseñadas para aprovechar las tecnologías de la nube.

Para maximizar el valor empresarial del conjunto de productos integrados de Microsoft 365 para empresas, empiece a planear e implementar una estrategia para migrar estas versiones:

| From | To |
|:-------|:-----|
| Windows 7 y Windows 8.1 | Windows 10 Enterprise |
| Productos de cliente de Office instalados en los dispositivos de los trabajadores | Aplicaciones de Microsoft 365 para empresas |
| Productos de servidor de Office instalados en servidores locales | Sus servicios basados en la nube equivalentes en Microsoft 365 |
|  |  |

## <a name="migrating-to-windows-10"></a>Migrar a Windows 10

Cada licencia de Microsoft 365 para empresas incluye una licencia para Windows 10 Enterprise. Para migrar los dispositivos que ejecutan Windows 7 o Windows 8.1, puedes realizar una actualización local. El soporte técnico finalizó para Windows 7 *el 14 de enero de 2020.* 

Para obtener métodos adicionales para instalar Windows 10 Enterprise más allá de una actualización local, consulta escenarios de implementación [de Windows 10.](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios) También puede [planear la implementación de Windows 10](https://aka.ms/planforwin10deployment) por su cuenta.

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a>Migrar a Aplicaciones de Microsoft 365 para empresas

Microsoft 365 para empresas incluye Aplicaciones de Microsoft 365 para empresas, una versión de los productos de cliente de Office (Word, PowerPoint, Excel y Outlook) que se instala y actualiza desde la nube de Microsoft. Para obtener más información, vea [Acerca de aplicaciones de Microsoft 365 para empresas.](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps)

En lugar de mantener los equipos al día para Office 2019 o versiones anteriores, siga estos pasos:

1. Obtenga y asigne una licencia de Microsoft 365 para los usuarios.
2. Desinstale Office 2013 u Office 2016 en sus equipos.
3. Instale Aplicaciones de Microsoft 365 para empresas, ya sea individualmente o durante una implementación de TI. Para obtener más información, vea [la guía de implementación de Aplicaciones de Microsoft 365.](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

Aplicaciones de Microsoft 365 para empresas instala actualizaciones de seguridad y nuevas actualizaciones de características automáticamente y puede aprovechar los servicios basados en la nube en Microsoft 365 para mejorar la seguridad y la productividad.

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a>Migración de datos y servidores locales a Microsoft 365

Microsoft 365 para empresas incluye versiones basadas en la nube de los servicios de servidor de Office que usan algunas de las mismas herramientas que las versiones locales del software de servidor de Office, como exploradores web y el cliente de Outlook. Estos servicios basados en la nube se actualizan automáticamente para la seguridad y las nuevas características. Después de la migración, el departamento de TI puede ahorrar el tiempo necesario para mantener y actualizar los servidores locales.

Use los siguientes recursos para obtener información sobre la migración de usuarios y datos para cargas de trabajo específicas de Microsoft 365:

- [Mover buzones de correo de buzones locales Exchange Server a Exchange Online](https://docs.microsoft.com/exchange/hybrid-deployment/move-mailboxes)
- [Migrar datos de SharePoint de SharePoint Server a SharePoint Online](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)
- [Migrar Skype Empresarial Online a Microsoft Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a>Realizar la transición en toda la organización

Para obtener una mejor idea de cómo mover toda la organización a los productos y servicios de Microsoft 365 para empresas, descargue este póster de transición:

[![Imagen que muestra el póster Transición a Microsoft 365.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

Este póster de dos páginas es una forma rápida de hacer un inventario de la infraestructura existente. Úselo para obtener instrucciones para pasar a un producto o servicio en Microsoft 365 para empresas. Muestra los productos de Windows y Office y otros elementos de infraestructura y seguridad, como la administración de dispositivos, la protección de identidades y amenazas, y la protección y cumplimiento de la información.

## <a name="results-of-step-4"></a>Resultados del paso 4

Para la migración de su espacio empresarial de Microsoft 365, ha determinado:

- Qué dispositivos ejecutan Windows 7 o Windows 8.1 y el plan para actualizarlos a Windows 10 Enterprise.
- Qué dispositivos ejecutan las aplicaciones cliente de Office y el plan para actualizarlas a las aplicaciones de Microsoft 365 para empresas.
- Qué servicios de servidor de Office locales deben migrarse a su equivalente de Microsoft 365 y el plan para migrarlos y sus datos.

Este es un ejemplo de un inquilino con una migración completa de servidores locales.

![Ejemplo de un inquilino con una migración completa de servidores locales](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

En esta ilustración, la organización tiene:

- Migró sus buzones de correo Exchange Server locales a Exchange Online.
- Migró sus datos y sitios locales de SharePoint Server a SharePoint en Microsoft 365.

## <a name="ongoing-maintenance-for-migration"></a>Mantenimiento continuo para la migración

De forma continua, es posible que deba:

- Según el estado de la migración de buzones de Exchange, continúe implementando la transición a Exchange Online en su organización.
- Según el estado de la migración del sitio de SharePoint local, continúe implementando la transición a SharePoint en Microsoft 365 a su organización.

## <a name="next-step"></a>Paso siguiente

[![Paso 5. Implementar la administración de dispositivos y aplicaciones](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)

Continúa con la [administración de dispositivos y aplicaciones](tenant-management-device-management.md) para implementar la administración de dispositivos y aplicaciones.