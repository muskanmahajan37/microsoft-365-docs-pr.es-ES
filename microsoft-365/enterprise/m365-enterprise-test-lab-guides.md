---
title: Guías de laboratorio para pruebas de Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Utilice estas guías de laboratorio de pruebas para configurar una demostración, prueba de concepto o entornos de desarrollo/prueba en Microsoft 365 para empresas.
ms.openlocfilehash: a006f549d0ac68562faee9c935df7f15161b2f12
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909603"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a>Guías de laboratorio para pruebas de Microsoft 365 para empresas

*Esto se aplica tanto a Microsoft 365 para empresas como a Office 365 Enterprise.*

Las Guías del laboratorio de pruebas (TLG) le ayudan a obtener información rápidamente sobre productos de Microsoft. Proporcionan instrucciones prescriptivas para configurar entornos de pruebas representativos pero simplificados. Puede usar estos entornos para la demostración, la personalización o la creación de pruebas de concepto complejas durante el tiempo que dure una suscripción de prueba o de pago.

Los TLG están diseñados para ser modulares. Se crean entre sí para crear varias configuraciones que coincidan más estrechamente con sus necesidades de configuración de aprendizaje o prueba. La experiencia práctica "Lo construí yo mismo y funciona", le ayuda a comprender los requisitos de implementación de un nuevo producto o escenario, de modo que pueda planear mejor su hospedaje en producción.

También puede usar tlgs para crear entornos representativos para desarrollar y probar aplicaciones, también conocidas como entornos de desarrollo y prueba.
  
![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

Para obtener un mapa visual de todos los artículos de la pila guía del laboratorio de pruebas de Microsoft 365 para empresas, expanda el siguiente gráfico o vaya a [Microsoft 365 para](../downloads/Microsoft365EnterpriseTLGStack.pdf)enterprise Test Lab Guide Stack .

[![Pila de guías de laboratorio para pruebas de Microsoft 365 Enterprise](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="base-configuration"></a>Configuración básica

En primer lugar, cree un entorno de prueba [para Microsoft 365 para empresas.](/microsoft-365-enterprise/) Puede crear dos tipos diferentes de configuraciones base:

- [Configuración base ligera:](lightweight-base-configuration-microsoft-365-enterprise.md) use esta opción cuando desee configurar y demostrar las características y capacidades de Microsoft 365 para empresas en un entorno solo en la nube, que no incluye componentes locales.

- [Configuración base](simulated-ent-base-configuration-microsoft-365-enterprise.md) de empresa simulada: use esta opción cuando desee configurar y demostrar las características y capacidades de Microsoft 365 para empresas en un entorno de nube híbrida, que usa componentes locales, como un dominio de Servicios de dominio de Active Directory (AD DS).

También puede crear entornos de prueba para Office 365 E5 al no agregar la licencia de Microsoft 365 E5 a su prueba o entorno de prueba de producción.
    
## <a name="identity"></a>Identidad

Para mostrar características y funciones relacionadas con identidades, vea:

- [Sincronización de hash de contraseñas](password-hash-sync-m365-ent-test-environment.md)
  
   Habilite y pruebe la sincronización de directorios basada en hash de contraseñas desde un controlador de dominio AD DS.

- [Autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md)
  
   Habilite y pruebe la autenticación de paso a un controlador de dominio AD DS.

- [Autenticación federada](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
   Habilite y pruebe la autenticación federada a un controlador de dominio AD DS.

- [Inicio de sesión único de conexión directa de Azure AD](single-sign-on-m365-ent-test-environment.md)
  
   Habilitar y probar el inicio de sesión único de Azure AD Seamless (SSO de conexión directa) con un controlador de dominio de AD DS.

- [Autenticación multifactor](multi-factor-authentication-microsoft-365-test-environment.md)
  
   Habilite y pruebe la autenticación multifactor basada en teléfono inteligente para una cuenta de usuario determinada.

- [Proteger las cuentas de administrador global](protect-global-administrator-accounts-microsoft-365-test-environment.md)

   Bloquear sus cuentas de administrador global con directivas de acceso condicional.

- [Reescritura de contraseña](password-writeback-m365-ent-test-environment.md)

   Usar una escritura diferida de contraseñas para cambiar la contraseña de su cuenta de usuario de AD DS de Azure AD.

- [Restablecimiento de contraseña](password-reset-m365-ent-test-environment.md)

   Use el restablecimiento de contraseñas de autoservicio para restablecer la contraseña.

- [Licencias automáticas y pertenencia a grupos](automate-licenses-group-membership-microsoft-365-test-environment.md)

   Haga que administrar nuevas cuentas sea más fácil que nunca con licencias automáticas y pertenencia a grupos dinámica.

- [Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md)

   Examine sus cuentas actuales de usuarios en busca de vulnerabilidades.

- [Acceso de dispositivos e identidades](identity-device-access-m365-test-environment.md)

   Crear un entorno para probar la identidad recomendada y configuraciones de acceso de dispositivo y directivas de acceso condicional.

## <a name="mobile-device-management"></a>Administración de dispositivos móviles

Para mostrar funcionalidades y características relacionadas con la administración de dispositivos móviles, vea:

- [Directivas de cumplimiento de dispositivos](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   Cree un grupo de usuarios y una directiva de cumplimiento de dispositivos para dispositivos con Windows 10.
    
- [Inscribir dispositivos iOS y Android](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   Inscriba los dispositivos Android o iOS y adminístrelos de forma remota.

## <a name="information-protection"></a>Protección de la información

Para demostrar características y funciones de la información relacionadas con la protección, vea:

- [Aumentar la seguridad de Microsoft 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   Configure las opciones para aumentar la seguridad de Microsoft 365 y analizar las herramientas de seguridad integrada.
  
- [Clasificación de datos](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   Configure y aplique etiquetas a un documento en un sitio de grupo de SharePoint Online.
    
- [Administración del acceso con privilegios](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   Configure la administración del acceso con privilegios para habilitar el acceso puntual a tareas elevadas o con privilegios en su organización.