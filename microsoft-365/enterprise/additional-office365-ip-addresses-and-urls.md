---
title: Los puntos de conexión adicionales no incluidos en el servicio web de URL ni en la dirección IP de Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/19/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: ''
description: 'Resumen: los nuevos servicios web de puntos de conexión no incluyen un número reducido de puntos de conexión para escenarios específicos.'
hideEdit: true
ms.openlocfilehash: 6c545b6060b44ebe234baaebd3ae1eb2fdb0fb89
ms.sourcegitcommit: 76f3c75413cc960289489d0ca29efadb8a9a5b31
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "51887214"
---
# <a name="additional-endpoints-not-included-in-the-office-365-ip-address-and-url-web-service"></a>Los puntos de conexión adicionales no incluidos en el servicio web de URL ni en la dirección IP de Office 365

Algunos puntos de conexión de red se han publicado anteriormente y no se han incluido en los [servicios web de URL y de dirección IP de Office 365](microsoft-365-ip-web-service.md). El ámbito de los servicios web son los puntos de conexión de red necesarios para la conectividad de un usuario final de Office 365 en una red perimetral empresarial. Actualmente no se incluyen:

1. Conectividad de red que pueda ser requerida por un centro de datos de Microsoft a una red de cliente (tráfico de red de servidor de entrada híbrido)
2. Conectividad de red desde servidores en una red de cliente en todo el perímetro de la empresa (tráfico de red de servidor saliente).
3. Escenarios poco comunes para requisitos de conectividad de red de un usuario.
4. Requisito de conectividad de resolución DNS (no se muestra a continuación).
5. Sitios de confianza de Internet Explorer o Microsoft Edge.

Aparte de DNS, estos son opcionales para la mayor parte de los clientes, salvo que necesite el escenario específico que se describe.

| Fila | Objetivo | Destino | Tipo |
|:-----|:-----|:-----|:-----|
| 1  | [Servicio de importación](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) para la ingesta de PST y de archivos | Consulte el [Servicio de importación](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) para ver los requisitos adicionales. | Escenario de salida poco común |
| 2  | [Asistente para soporte y recuperación de Office 365 de Microsoft](https://diagnostics.office.com/#/)  | https<span>://</span>autodiscover.outlook.com <BR> <span>https://</span>officecdn.microsoft.com <BR> <span>https://</span>api.diagnostics.office.com <BR> <span>https://</span>apibasic.diagnostics.office.com <BR> <span>https://</span>autodiscover-s.outlook.com <BR> <span>https://</span>cloudcheckenabler.azurewebsites.net <BR> <span>https://</span>login.live.com <BR> <span>https://</span>login.microsoftonline.com <BR> <span>https://</span>login.windows.net <BR> <span>https://</span>o365diagtelemetry.trafficmanager.net <BR> <span>https://</span>odc.officeapps.live.com <BR> <span>https://</span>offcatedge.azureedge.net <BR> <span>https://</span>officeapps.live.com <BR> <span>https://</span>outlook.office365.com <BR> <span>https://</span>outlookdiagnostics.azureedge.net | Tráfico de servidor saliente |
| 3  | Azure AD Connect (con SSO opcional): WinRM y PowerShell remoto | Entorno de STS de cliente (servidor AD FS y Proxy AD FS) \| Puertos TCP 80 y 443 | Tráfico de servidor entrante |
| 4   | STS como servidores proxy de AD FS (solo para clientes federados) | STS de cliente (como proxy de AD FS) \| Puertos TCP 443 o TCP 49443 con TLS de cliente | Tráfico de servidor entrante |
| 5   | [Mensajería unificada de Exchange Online/Integración de SBC](/exchange/voice-mail-unified-messaging/telephone-system-integration-with-um/configuration-notes-for-session-border-controllers) | Bidireccional entre el controlador de borde de sesión local y *.um.outlook.com | Solo tráfico de servidor saliente |
| 6   | Migración de buzones. Cuando se inicia la migración de buzones local de [Exchange híbrido](/exchange/exchange-deployment-assistant) a Office 365, Office 365 se conecta a su servidor publicado de Exchange Web Services (EWS) o de servicios de replicación de buzones (MRS). Si necesita las direcciones IP de NAT utilizadas por los servidores de Exchange Online para restringir las conexiones de entrada de intervalos de IP de origen específicos, se muestran en [URL de Office 365 y rangos de IP](urls-and-ip-address-ranges.md) en el área de servicio "Exchange Online". Debe tener cuidado para asegurarse de que el acceso a los extremos de EWS publicados como OWA no se ve afectado, para ello asegúrese de que el proxy MRS resulta en un FQDN y una dirección IP pública independientes antes de restringir las conexiones TCP 443 de intervalos IP de origen específicos. | Proxy EWS o MRS local de cliente<br> Puerto TCP 443 | Tráfico de servidor entrante |
| 7   | Funciones de coexistencia de [Exchange híbrido](/exchange/exchange-deployment-assistant), como el uso compartido de disponibilidad. | Servidor de Exchange local de cliente | Tráfico de servidor entrante |
| 8   | Autenticación de proxy de [Exchange híbrido](/exchange/exchange-deployment-assistant) | STS local de cliente | Tráfico de servidor entrante |
| 9   | Se usa para configurar[Exchange híbrido](/exchange/exchange-deployment-assistant) mediante el [Asistente de configuración híbrida de Exchange](/exchange/hybrid-configuration-wizard). <br> Nota: Estos puntos de conexión solo son necesarios para configurar la implementación híbrida de Exchange  | domains.live.com en los puertos TCP 80 y 443, solo son necesarios para el Asistente de configuración híbrida de Exchange 2010 SP3<BR> <BR> Direcciones IP de DoD y GCC High: 40.118.209.192/32; 168.62.190.41/32 <BR> <BR> Global Commercial & GCC: *.store.core.windows.net; asl.configure.office.com; tds.configure.office.com; mshybridservice.trafficmanager.net ; <BR> aka.ms/hybridwizard; <BR> shcwreleaseprod.blob.core.windows.net/shcw/ \* ;<BR>  | Solo tráfico de servidor saliente |
| 10    | El servicio Detección automática se usa en escenarios de [Exchange híbrido](/exchange/exchange-deployment-assistant) con [Autenticación moderna híbrida con Outlook para iOS y Android](/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) <BR> <BR> ```*.acompli.net``` <BR> <BR> ```*.outlookmobile.com``` <BR> <BR> ```*.outlookmobile.us``` <BR> <BR> ```52.125.128.0/20``` <BR> ```52.127.96.0/23``` <BR> | Servidor de Exchange local de cliente en TCP 443 | Tráfico de servidor entrante |
| 11  | Autenticación híbrida de Azure AD de Exchange | *.msappproxy.net | Tráfico de solo servidor saliente TCP |
| 12   | Skype Empresarial en Office 2016 incluye el uso compartido de pantalla basado en vídeo que usa los puertos UDP. Los clientes anteriores de Skype Empresarial de Office 2013 y versiones anteriores usaban RDP mediante un puerto TCP 443. | Puerto TCP 443 abierto para 52.112.0.0/14 | Versiones de cliente anteriores de Skype Empresarial en Office 2013 y versiones anteriores |
| 13  | Conectividad de servidor local híbrido de Skype Empresarial para Skype Empresarial Online | 13.107.64.0/18, 52.112.0.0/14  <BR> Puertos UDP 50,000-59,999 <BR>  Puertos TCP 50,000-59,999; 5061 | Conectividad de salida de servidor local de Skype Empresarial |
| 14   | RTC en la nube con conectividad híbrida local requiere la conectividad de red abierta para los host locales Para más información acerca de las configuraciones híbridas de Skype Empresarial Online,  | Consulte [Planear la conectividad híbrida entre Skype Empresarial Server y Office 365](/skypeforbusiness/hybrid/plan-hybrid-connectivity) | Skype Empresarial híbrido local entrante |
| 15   | **FQDN de autenticación e identidad** <br> Para que funcione, el FQDN ```secure.aadcdn.microsoftonline-p.com``` debe estar en el Internet Explorer (IE) del cliente o en su zona de sitios de confianza de Microsoft Edge. |  | Sitios de confianza |
| 16   |  **FQDN de Microsoft Teams** <br> Si usa Internet Explorer o Microsoft Edge, debe habilitar las cookies propias y de terceros y agregar los FQDN para Teams a los sitios de confianza. Esto es complementario a los FQDN de todo el conjunto de aplicaciones, los CDN y la telemetría enumerados en la fila 14. Para obtener más información, vea [Problemas conocidos de Microsoft Teams](/microsoftteams/known-issues). |  | Sitios de confianza |
| 17   |  **FQDN de SharePoint Online y OneDrive para la Empresa** <br> Todos los FQDN '.sharepoint.com' con "\<tenant>" en el FQDN deben estar en la zona de sitios de confianza de Internet Explorer o Microsoft Edge del cliente para que funcionen. Además de los FQDN de todo el conjunto de aplicaciones, los CDN y la telemetría enumerados en la fila 14, necesitará agregar también estos puntos de conexión. |  | Sitios de confianza |
| 18   | **Yammer**  <br> Yammer solo está disponible en el explorador y requiere que el usuario autenticado pase por un proxy. Para que funcionen, todos los FQDN de Yammer deben estar en el Internet Explorer del cliente o en su zona de sitios de confianza de Microsoft Edge.
 |  | Sitios de confianza |
| 19  | Use [Azure AD Connect](/azure/active-directory/hybrid/) para sincronizar las cuentas de usuarios locales con Azure AD. | Vea [Puertos y protocolos necesarios para la identidad híbrida,](/azure/active-directory/hybrid/reference-connect-ports) [Solución de problemas de conectividad de Azure AD](/azure/active-directory/hybrid/tshoot-connect-connectivity) e [Instalación del Agente de Azure AD Connect Health](/azure/active-directory/hybrid/how-to-connect-health-agent-install#outbound-connectivity-to-the-azure-service-endpoints). | Solo tráfico de servidor saliente |
| 20  | [Azure AD Connect](/azure/active-directory/hybrid/) con 21 ViaNet en China para sincronizar cuentas de usuario locales con Azure AD. | \*.digicert.com:80 <BR> \*.entrust.net:80 <BR> \*.chinacloudapi.cn:443 <BR> secure.aadcdn.partner.microsoftonline-p.cn:443 <BR>*.partner.microsoftonline.cn:443 <BR> <BR>Consulte también [Solución de problemas de entrada con problemas de conectividad de Azure AD](https://docs.azure.cn/zh-cn/active-directory/hybrid/tshoot-connect-connectivity). | Solo tráfico de servidor saliente |
|  21  | Microsoft Stream (necesita el token de usuario de Azure AD). <BR> Office 365 mundial (incluido GCC) | \*.cloudapp.net <BR> \*.api.microsoftstream.com <BR> \*.notification.api.microsoftstream.com <BR> amp.azure.net <BR> api.microsoftstream.com <BR> az416426.vo.msecnd.net <BR> s0.assets-yammer.com <BR> vortex.data.microsoft.com <BR> web.microsoftstream.com <BR> Puerto TCP 443  | Tráfico de servidor entrante |
| 22  | Use el servidor MFA para las solicitudes de autenticación multifactor, tanto las nuevas instalaciones del servidor como su configuración con Servicios de dominio de Active Directory (AD DS). | Consulte Introducción al servidor de [autenticación multifactor de Azure AD](/azure/active-directory/authentication/howto-mfaserver-deploy#plan-your-deployment).  | Solo tráfico de servidor saliente |
| 23  | Notificaciones de cambios en Microsoft Graph | Los desarrolladores pueden aprovechar las [notificaciones de cambios](/graph/webhooks?context=graph%2fapi%2f1.0&view=graph-rest-1.0) para suscribirse a eventos en Microsoft Graph. | *.cloudapp.net<BR> 104.43.130.21, 137.116.169.230, 13.79.38.63, 104.214.39.228, Public Cloud: 168.63.250.205, 52.161.9.202, 40.68.103.62, 13.89.60.223, 23.100.95.104, 40.113.95.219, 104.214.32.10, 168.63.237.145, 52.161.110.176, 52.174.177.183, 13.85.192.59, 13.85.192.123, 13.86.37.15, 13.89.108.233, 13.89.104.147, 20.44.210.83, 20.44.210.146, 40.76.162.99, 40.76.162.42, 40.74.203.28, 40.74.203.27, 51.104.159.213, 51.104.159.181, 51.124.75.43, 51.124.73.177, 51.138.90.7, 51.138.90.52, 52.139.153.222, 52.139.170.157, 52.139.170.47, 52.142.114.29, 52.142.115.31, 52.147.213.251, 52.147.213.181, 52.148.24.136, 52.148.27.39, 52.148.115.48, 52.148.114.238, 52.154.246.238, 52.159.23.209, 52.159.17.84, 52.184.94.140 <BR> Microsoft Cloud for US Government: 52.244.231.173, 52.238.76.151, 52.244.250.211, 52.238.78.108, 52.243.147.249, 52.243.148.19, 52.243.157.104, 52.243.157.105, 52.244.33.45, 52.244.35.174, 52.244.111.156, 52.244.111.170 <BR> Microsoft Cloud Germany: 51.4.231.136, 51.5.243.223, 51.4.226.154, 51.5.244.215, 51.4.150.206, 51.4.150.235, 51.5.147.130, 51.5.148.1033 <BR> Microsoft Cloud China operado por 21Vianet: 139.219.15.33, 42.159.154.223, 42.159.88.79, 42.159.155.77, 40.72.155.199, 40.72.155.216, 40.125.138.23, 40.125.136.69, 42.159.72.35, 42.159.72.47, 42.159.180.55, 42.159.180.566<BR> Puerto TCP 443 <BR> Nota: los desarrolladores pueden especificar puertos diferentes al crear las suscripciones.  | Tráfico de servidor entrante |
|||||

## <a name="related-topics"></a>Temas relacionados

[Administrar puntos de conexión de Office 365](managing-office-365-endpoints.md)
  
[Supervisar la conectividad de Microsoft 365](./monitor-connectivity.md)
  
[Conectividad de clientes](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[Redes de entrega de contenido](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Intervalos IP de Azure y etiquetas de servicio: nube pública](https://www.microsoft.com/download/details.aspx?id=56519)

[Azure IP Ranges and Service Tags: Us Government Cloud](https://www.microsoft.com/download/details.aspx?id=57063)

[Intervalos IP de Azure y etiquetas de servicio: Germany Cloud](https://www.microsoft.com/download/details.aspx?id=57064)

[Intervalos IP de Azure y etiquetas de servicio: China Cloud](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Espacio IP público de Microsoft](https://www.microsoft.com/download/details.aspx?id=53602)