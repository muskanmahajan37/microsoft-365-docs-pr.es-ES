---
title: Inicio rápido de la Red de entrega de contenido (CDN) de Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Inicio rápido de la Red de entrega de contenido (CDN) de Office 365
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921599"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Inicio rápido de la Red de entrega de contenido (CDN) de Office 365

Puede usar la red de entrega de contenido (CDN) integrada de **Office 365** para hospedar activos estáticos (imágenes, JavaScript, hojas de estilos, archivos WOFF) para proporcionar un mejor rendimiento para las páginas de SharePoint Online. La CDN de Office 365 mejora el rendimiento al almacenamiento en caché los archivos estáticos más cerca de los exploradores que los solicitan, lo que ayuda a acelerar descargas y reducir la latencia. Además, la red CDN de Office 365 usa el protocolo HTTP/2 para mejorar la compresión y la canalización HTTP. La red CDN de Office 365 se incluye como parte de la suscripción a SharePoint Online.

Para obtener instrucciones más detalladas, vea [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).

>[!NOTE]
>La red CDN de Office 365 solo está disponible para los inquilinos en la nube de producción (en todo el mundo). Actualmente, los inquilinos de las nubes de Estados Unidos, China y Alemania no admiten la red CDN de Office 365.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>Usar la herramienta Diagnóstico de página para SharePoint para identificar elementos que no están en la red CDN

Puede usar la extensión del explorador de herramientas diagnósticos de página para **SharePoint** para enumerar fácilmente los activos de las páginas de SharePoint Online que se pueden agregar a un origen de red CDN.

La herramienta Diagnóstico de página para **SharePoint** es una extensión de explorador para los nuevos exploradores Microsoft Edge ( y Chrome que analizan tanto el portal moderno de SharePoint Online como las páginas de sitio de publicación https://www.microsoft.com/edge) clásicas. La herramienta le ofrece un informe para cada página analizada en el que se muestra el rendimiento de la página respecto a un conjunto definido de criterios de rendimiento. Para instalar e informarse de la herramienta Diagnóstico de página de SharePoint, visite [Usar la herramienta Diagnóstico de página para SharePoint Online](./page-diagnostics-for-spo.md).

Al ejecutar la herramienta Diagnóstico de página para SharePoint en una  página de SharePoint Online, puede hacer clic en la pestaña Pruebas de diagnóstico para ver una lista de activos que no se hospedan en la red CDN. Estos activos aparecerán bajo la comprobación de la Red de entrega de contenido **(CDN)** del título, tal como se muestra en la captura de pantalla siguiente.

![Diagnósticos de página](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>La herramienta de Diagnóstico de páginas solo funciona para SharePoint Online y no se puede usar en una página del sistema de SharePoint. 

## <a name="cdn-overview"></a>Introducción a la red CDN

La red CDN de Office 365 está diseñada para optimizar el rendimiento de los usuarios mediante la distribución de objetos a los que se accede con frecuencia, como imágenes y archivos javascript, a través de una red global de alta velocidad, lo que reduce el tiempo de carga de las páginas y proporciona acceso a objetos hospedados lo más cerca posible para el usuario. La red CDN recupera los activos de una ubicación denominada _origen_. Un origen puede ser un sitio de SharePoint, una biblioteca de documentos o una carpeta a la que una dirección URL puede tener acceso.

La red CDN de Office 365 está separada en dos tipos básicos:

- **La red CDN** pública está diseñada para usarse para JS (JavaScript), CSS (StyleSheets), archivo de fuente web (WOFF, WOFF2) e imágenes no propietarias como logotipos de la empresa.
- **La red CDN** privada está diseñada para usarse para imágenes (PNG, JPG, JPEG, etc.).

Puede elegir tener orígenes públicos o privados para su organización. La mayoría de las organizaciones elegirán implementar una combinación de las dos. Las opciones públicas y privadas proporcionan ganancias de rendimiento similares, pero cada una tiene atributos y ventajas únicos. Para obtener más información acerca de los orígenes de CDN públicos y privados, vea [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>Cómo habilitar la RED CDN pública y privada con la configuración predeterminada
Antes de realizar cambios en la configuración de la red CDN del inquilino, debe comprobar que cumple las directivas de cumplimiento, seguridad y privacidad de su organización.

Para obtener opciones de configuración más detalladas, o si ya ha habilitado la red CDN y desea agregar ubicaciones adicionales (orígenes), consulte la sección Configurar y configurar la red CDN de [Office 365](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell) mediante el Shell de administración de SharePoint Online

Conéctese al espacio empresarial mediante el Shell de administración de SharePoint Online:

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

Para permitir que la organización use orígenes públicos y privados con la configuración predeterminada, escriba el siguiente comando:

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

El resultado de estos cmdlets debe tener el siguiente aspecto:

![Salida de Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a>Vea también

[Usar la herramienta diagnóstico de página para SharePoint Online](./page-diagnostics-for-spo.md)

[Uso de la red de entrega de contenido (CDN) de Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Redes de entrega de contenido](./content-delivery-networks.md)

[Planeamiento de red y ajuste del rendimiento para Office 365](./network-planning-and-performance.md)

[Serie de rendimiento de SharePoint: serie de vídeo cdn de Office 365](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)