---
title: 'Directivas recomendadas de correo electrónico seguro: Microsoft 365 para empresas | Microsoft Docs'
description: Describe las directivas recomendadas por Microsoft para aplicar directivas y configuraciones de correo electrónico.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: c5f5837f4e4069a67bc080178fefd10bd2a08629
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599856"
---
# <a name="policy-recommendations-for-securing-email"></a>Recomendaciones de directivas para proteger el correo electrónico

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

En este artículo se describe cómo implementar las directivas de identidad y acceso a dispositivos recomendadas para proteger los clientes de correo electrónico y correo electrónico de la organización que admiten la autenticación moderna y el acceso condicional. Esta guía se basa en las directivas comunes de identidad y acceso a [dispositivos](identity-access-policies.md) y también incluye algunas recomendaciones adicionales.

Estas recomendaciones se basan en tres niveles diferentes de seguridad y protección que se pueden aplicar en función de la granularidad de sus necesidades: **línea** **base,** confidencial y **altamente regulado.** Puede aprender más sobre estos niveles de seguridad y los sistemas operativos de cliente recomendados, a los que hacen referencia estas recomendaciones, en la [introducción a las directivas y configuraciones de seguridad recomendadas](microsoft-365-policies-configurations.md).

Estas recomendaciones requieren que los usuarios usen clientes de correo electrónico modernos, incluidos Outlook para iOS y Android en dispositivos móviles. Outlook para iOS y Android admite las mejores características de Office 365. Estas aplicaciones móviles de Outlook también están diseñadas con capacidades de seguridad que admiten el uso móvil y funcionan junto con otras capacidades de seguridad en la nube de Microsoft. Para obtener más información, vea Preguntas más frecuentes [de Outlook para iOS y Android.](/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)

## <a name="update-common-policies-to-include-email"></a>Actualizar directivas comunes para incluir correo electrónico

Para proteger el correo electrónico, en el siguiente diagrama se muestran las directivas que se actualizarán a partir de las directivas comunes de acceso a dispositivos y identidades.

[![Resumen de las actualizaciones de directivas para proteger el acceso a Teams y sus servicios dependientes](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

Tenga en cuenta la adición de una nueva directiva para Que Exchange Online bloquee los clientes de ActiveSync. Esto fuerza el uso de Outlook mobile.

Si incluyó Exchange Online y Outlook en el ámbito de las directivas al configurarlas, solo necesita crear la nueva directiva para bloquear los clientes de ActiveSync. Revise las directivas enumeradas en la tabla siguiente y realice las adiciones recomendadas o confirme que ya están incluidas. Cada directiva se vincula a las instrucciones de configuración asociadas [en Identidad común y directivas de acceso a dispositivos](identity-access-policies.md).

|Nivel de protección|Directivas|Más información|
|---|---|---|
|**Baseline**|[Requerir MFA cuando el riesgo de inicio de sesión *es medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir Exchange Online en la asignación de aplicaciones en la nube|
||[Bloquear a los clientes que no sean compatibles con la autenticación moderna](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Incluir Exchange Online en la asignación de aplicaciones en la nube|
||[Aplicar directivas de protección de datos de APP](identity-access-policies.md#apply-app-data-protection-policies)|Asegúrese de que Outlook está incluido en la lista de aplicaciones. Asegúrese de actualizar la directiva para cada plataforma (iOS, Android, Windows)|
||[Requerir aplicaciones aprobadas y protección de APLICACIONES](identity-access-policies.md#require-approved-apps-and-app-protection)|Incluir Exchange Online en la lista de aplicaciones en la nube|
||[Exigir equipos PC compatibles](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Incluir Exchange Online en la lista de aplicaciones en la nube|
||[Bloquear clientes de ActiveSync](#block-activesync-clients)|Agregar esta nueva directiva|
|**Confidencial**|[Requerir MFA cuando el riesgo de inicio de sesión *es bajo,* *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir Exchange Online en la asignación de aplicaciones en la nube|
||[Requerir equipos y *dispositivos* móviles compatibles](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Incluir Exchange Online en la lista de aplicaciones en la nube|
|**Extremadamente regulado**|[*Requerir* siempre MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir Exchange Online en la asignación de aplicaciones en la nube|
|

## <a name="block-activesync-clients"></a>Bloquear clientes de ActiveSync

Esta directiva impide que los clientes de ActiveSync omitan otras directivas de acceso condicional. La configuración de directiva solo se aplica a los clientes de ActiveSync. Al seleccionar Requerir **[directiva de protección de aplicaciones,](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** esta directiva bloquea los clientes de ActiveSync. Los detalles sobre cómo crear esta directiva se pueden encontrar en Requerir directiva de protección de aplicaciones para el acceso a aplicaciones en la nube [con acceso condicional.](/azure/active-directory/conditional-access/app-protection-based-conditional-access)

- Siga el "Paso 2: Configurar una directiva de acceso condicional de Azure AD para Exchange Online con ActiveSync (EAS)" en el escenario 1: Las aplicaciones de [Office 365](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)requieren aplicaciones aprobadas con directivas de protección de aplicaciones, lo que impide Exchange ActiveSync que los clientes que aprovechan la autenticación básica se conecten a Exchange Online.

También puede usar directivas de autenticación para [deshabilitar la autenticación básica,](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)lo que fuerza a todas las solicitudes de acceso de cliente a usar la autenticación moderna.

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>Limitar el acceso a Exchange Online desde Outlook en la web

Puede restringir la capacidad de los usuarios para descargar datos adjuntos de Outlook en la web en dispositivos umnanaged. Los usuarios de estos dispositivos pueden ver y editar estos archivos con Office Online sin tener que filtrar y almacenar los archivos en el dispositivo. También puedes impedir que los usuarios vean datos adjuntos en un dispositivo no administrado.

Estos son los pasos:

1. [Conectarse a una sesión remota de PowerShell de Exchange Online](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).
2. Si aún no tiene una directiva de buzón de OWA, cree una con el cmdlet [New-OwaMailboxPolicy.](/powershell/module/exchange/new-owamailboxpolicy)
3. Si desea permitir la visualización de datos adjuntos pero no descargarlos, use este comando:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. Si desea bloquear datos adjuntos, use este comando:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. En Azure Portal, cree una nueva directiva de acceso condicional con esta configuración:

   **Asignaciones** \> **Usuarios y grupos:** seleccione los usuarios y grupos adecuados para incluir y excluir.

   **Asignaciones** \> **Acciones o aplicaciones en la nube** \> **Aplicaciones en la nube** \> **Incluir** \> **Seleccionar aplicaciones:** Seleccione **Office 365 Exchange Online**

   **Controles de acceso** \> **Sesión:** seleccione **Usar restricciones aplicadas por la aplicación**

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>Requerir que los dispositivos iOS y Android deben usar Outlook

Para asegurarse de que los usuarios de dispositivos iOS y Android solo pueden acceder a contenido laboral o educativo mediante Outlook para iOS y Android, necesita una directiva de acceso condicional dirigida a esos usuarios potenciales.

Vea los pasos para configurar esta directiva en [Manage messaging collaboration access by using Outlook for iOS and Android](/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access).

## <a name="set-up-message-encryption"></a>Configurar el cifrado de mensajes

Con las nuevas capacidades de cifrado de mensajes (OME) de Office 365, que aprovechan las características de protección de Azure Information Protection, su organización puede compartir fácilmente correo electrónico protegido con cualquier persona en cualquier dispositivo. Los usuarios pueden enviar y recibir mensajes protegidos con otras organizaciones de Microsoft 365, así como con no clientes mediante Outlook.com, Gmail y otros servicios de correo electrónico.

Para obtener más información, vea [Set up new Office 365 Message Encryption capabilities](../../compliance/set-up-new-message-encryption-capabilities.md).

## <a name="next-steps"></a>Pasos siguientes

![Paso 4: Directivas para aplicaciones en la nube de Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configurar directivas de acceso condicional para:

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
