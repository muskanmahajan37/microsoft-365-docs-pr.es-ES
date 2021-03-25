---
title: Incorporación de dispositivos que no son de Windows al servicio de Microsoft Defender para puntos de conexión
description: Configura dispositivos que no son de Windows para que puedan enviar datos del sensor al servicio ATP de Microsoft Defender.
keywords: incorporar dispositivos que no son windows, macos, linux, administración de dispositivos, configurar dispositivos de Windows ATP, configurar Microsoft Defender para dispositivos de punto de conexión
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
ms.openlocfilehash: c292c57c179a832728b03a7fc94fb7085d3ea0ec
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166082"
---
# <a name="onboard-non-windows-devices"></a>Incorporación de dispositivos que no son de Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plataformas**
- macOS
- Linux

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

Defender for Endpoint proporciona una experiencia de operaciones de seguridad centralizada para Windows, así como para plataformas que no son de Windows. Podrás ver alertas de varios sistemas operativos compatibles (SO) en el Centro de seguridad de Microsoft Defender y proteger mejor la red de la organización. 

Deberá conocer las versiones exactas de Linux distros y macOS que son compatibles con Defender for Endpoint para que la integración funcione. Para más información, vea:
- [Requisitos del sistema de Microsoft Defender para Endpoint para Linux](microsoft-defender-endpoint-linux.md#system-requirements)  
- [Requisitos del sistema de Microsoft Defender para Endpoint para Mac](microsoft-defender-endpoint-mac.md#system-requirements).

## <a name="onboarding-non-windows-devices"></a>Incorporación de dispositivos que no son de Windows
Tendrás que seguir los siguientes pasos para incorporar dispositivos que no son windows:
1. Seleccione el método de incorporación preferido:

   - Para dispositivos macOS, puedes elegir incorporarlo a través de ATP de Microsoft Defender o a través de una solución de terceros. Para obtener más información, vea [Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac).
   - Para otros dispositivos que no son de Windows, elija Incorporar dispositivos que no son de Windows a **través de la integración de terceros.**   
       
     1. En el panel de navegación, seleccione **Socios de**  >  **interoperabilidad**. Asegúrese de que la solución de terceros aparece en la lista.

        2. En la **pestaña Aplicaciones de** partners, selecciona el partner que admita los dispositivos que no son windows.

        3. Seleccione **Abrir página de socio** para abrir la página del partner. Siga las instrucciones proporcionadas en la página.

        4. Después de crear una cuenta o suscribirse a la solución de partners, debe llegar a una fase en la que se pida a un administrador global de inquilinos de la organización que acepte una solicitud de permiso de la aplicación asociada. Lea atentamente la solicitud de permiso para asegurarse de que está alineada con el servicio que necesita. 

        
2. Ejecute una prueba de detección siguiendo las instrucciones de la solución de terceros.

## <a name="offboard-non-windows-devices"></a>Dispositivos offboard que no son Windows

1. Siga la documentación del tercero para desconectar la solución de terceros de Microsoft Defender para endpoint.

2. Quite los permisos de la solución de terceros en el inquilino de Azure AD.
   1. Inicie sesión en el [Azure Portal](https://portal.azure.com).
   2. Seleccione **Azure Active Directory > Enterprise Applications**.
   3. Selecciona la aplicación que quieras quitar.
   4. Seleccione el **botón** Eliminar.


## <a name="related-topics"></a>Temas relacionados
- [Incorporación de dispositivos Windows 10](configure-endpoints.md)
- [Servidores integrados](configure-server-endpoints.md)
- [Configuración de proxy y conectividad a Internet](configure-proxy-internet.md)
- [Solución de problemas de incorporación de Microsoft Defender para puntos de conexión](troubleshoot-onboarding.md)