---
title: Usar identidad, dispositivo y protección contra amenazas para la normativa de privacidad de datos
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: Evite las violaciones de datos personales con los servicios de identidad, dispositivos y protección contra amenazas de Microsoft 365.
ms.openlocfilehash: 74894037ef2fe56aeb5bc44340cd8a946863baff
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695084"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Usar identidad, dispositivo y protección contra amenazas para la normativa de privacidad de datos

Microsoft 365 proporciona una serie de capacidades de identidad, dispositivo y protección contra amenazas que las organizaciones pueden emplear para ayudar a cumplir con las regulaciones de cumplimiento de datos relacionadas con la privacidad de datos. En este artículo se describe lo que los reglamentos de privacidad de datos requieren en estas áreas y se proporciona una lista de características y servicios de Microsoft 365 con vínculos a información adicional que le ayudarán a abordar los requisitos de implementación.

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Cómo se relacionan la protección de identidades, dispositivos y amenazas con la normativa de privacidad de datos

Aunque las regulaciones de privacidad de datos varían en su especificidad, la esencia de lo que llaman se expresa en el artículo 5 de RGPD (1) (f), que establece que: 

- Los datos personales se procesarán de manera que se garantice la seguridad adecuada de los datos personales, incluida la protección contra el procesamiento no autorizado o ilegal y contra la pérdida, destrucción o daños accidentales, mediante las medidas técnicas o organizacionales adecuadas (integridad y confidencialidad).

Debido a que las infracciones de datos personales suelen deberse a la intromisión de cuentas de usuarios finales o administrativos y al acceso malintencionado al sistema. Por ejemplo, una cuenta de administrador pirata puede dar como resultado la exfiltración de números de tarjeta de crédito de clientes u otra información personal. Se deben implementar todos los requisitos generales de identidad, dispositivo y protección contra amenazas disponibles con Microsoft 365 potencialmente, que se reflejarán en la puntuación de cumplimiento.

## <a name="using-the-results-of-your-assessment-work-and-compliance-score"></a>Uso de los resultados del trabajo de evaluación y la puntuación de cumplimiento

La puntuación de cumplimiento incluye la protección contra amenazas, dispositivos y identidades mediante estas categorías:

- La identidad corresponde a la categoría de **acceso de control**
- El dispositivo corresponde a la categoría **administrar dispositivos**
- La protección contra amenazas corresponde a la categoría **protección contra amenazas**
 
Si se seleccionan en todo el conjunto de ejemplo de cuatro normativas de privacidad de datos principales, la puntuación de cumplimiento especifica 90 acciones de mejora, la mayoría de las cuales se puntuan como "27". Como un número tan elevado se denomina por puntuación de cumplimiento para estas categorías, algunos de los más comunes se enumeran aquí, como referencia.

Use [Azure Active Directory (Azure ad)](https://azure.microsoft.com/services/active-directory/) para la identidad y la categoría de **acceso de control** , con la que puede:

- Implementación de la autenticación resistente a la reproducción (para evitar ataques "Man in the Middle")
- Bloquear la autenticación heredada.
- Configure los riesgos de usuario y las directivas de riesgo de inicio de sesión del usuario.
- Habilitar el acceso condicional y la autenticación multifactor (MFA) para administradores y no administradores.
- Configurar y aplicar directivas de contraseñas.
- Restrinja el acceso a las cuentas con privilegios con Azure AD privileged Identity Management.
- Deshabilitar el acceso al terminar.
- Auditar las cuentas de usuario y los cambios de estado.
- Revise los cambios administrativos y de grupo de funciones.

Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) para dispositivos y la categoría **administrar dispositivos** , con la que puede:

- Bloquee los dispositivos móviles con jailbreak y Rooting.
- Configurar Intune para la administración de dispositivos móviles.
- Cree directivas de cumplimiento para dispositivos Android, iOS, macOS y Windows.
- Cree un perfil de configuración de dispositivo para dispositivos Android, iOS, macOS y Windows.
- Cree directivas de protección de aplicaciones para iOS y Windows.
- Ocultar información con la pantalla de bloqueo.
- Implemente directivas de contraseñas para dispositivos móviles.
- Requerir que los dispositivos móviles se bloqueen al inactividad.
- Requerir que los dispositivos móviles se borren en varios errores de inicio de sesión.

Use [Exchange Online Protection y Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md) para la categoría **proteger contra amenazas** , con la que puede:

- Habilitar la autenticación de remitente (SPF, DMARC y DKIM).
- Configurar las directivas de protección contra suplantación de identidad (ATP) de Office 365 Advanced Threat Protection.
- Implementar datos adjuntos seguros de ATP.
- Implementar vínculos seguros de ATP.
- Implementar directivas de detección y respuesta de malware.
- Implemente directivas de correo no deseado salientes y entrantes.

### <a name="references"></a>Referencias

- [Directivas comunes de acceso a dispositivos e identidades](../enterprise/identity-access-policies.md)
- [Protección contra amenazas en Office 365](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [Datos adjuntos seguros ATP](../security/office-365-security/atp-safe-attachments.md)
- [Vínculos seguros de ATP](../security/office-365-security/atp-safe-links.md)
- [Documentos seguros de ATP](../security/office-365-security/safe-docs.md)