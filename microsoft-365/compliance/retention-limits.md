---
title: Límites de directivas de retención y directivas de etiqueta de retención.
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Obtener información sobre el número máximo de directivas y elementos por directiva para directivas de retención y directivas de etiquetas de retención
ms.openlocfilehash: 547c6396fa9bfcba6dbd271f09a7ea59f9acf170
ms.sourcegitcommit: a9ac702c9efc9defded3bfa65618b94bac00c237
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2021
ms.locfileid: "50261595"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a>Límites de directivas de retención y directivas de etiqueta de retención.

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Al usar [directivas de retención y directivas de etiqueta de retención](retention.md#retention-policies-and-retention-labels) para conservar o eliminar automáticamente datos de su organización, debe conocer ciertos límites.

## <a name="maximum-number-of-policies-per-tenant"></a>Número máximo de directivas por espacio empresarial

Un solo espacio empresarial puede tener un máximo de 10 000 directivas (cualquier configuración). Este número máximo incluye las diferentes directivas de retención y otras directivas de cumplimiento, como las directivas DLP.

Número máximo de directivas para la retención por carga de trabajo:

- Exchange Online (cualquier configuración): 1800
- SharePoint o OneDrive (se incluyen automáticamente todos los sitios): 13
- SharePoint o OneDrive (ubicaciones específicas incluidas o excluidas): 2600

## <a name="maximum-number-of-items-per-policy"></a>Número máximo de elementos por directiva

Deben tenerse en cuenta ciertos límites por directiva si usa la configuración opcional para definir el ámbito de la configuración de retención para usuarios específicos, grupos específicos de Microsoft 365 o determinados sitios: 

Número máximo de elementos por directiva para la retención:

  - 1000 buzones de correo (buzones de usuario o de grupo)
  - Grupos de Microsoft 365 1 000.
  - 1 000 usuarios para chats privados de Teams
  - 100 sitios (OneDrive o SharePoint)

Estas limitaciones son por directiva, por lo que si necesita usar inclusiones o exclusiones específicas por las que se superan estos números, puede crear otras directivas de retención con la misma configuración de retención. Vea la siguiente sección con [algunos escenarios de ejemplo y soluciones](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) que usan varias directivas de retención por este motivo.

Sin embargo, tener varias directivas generan más sobrecargas administrativas, por lo que siempre debe confirmar si necesita realmente inclusiones y exclusiones. Recuerde que la configuración predeterminada que se aplica a toda la ubicación no tiene ninguna limitación y esta opción de configuración puede ser una solución mejor que la creación y el mantenimiento de varias directivas.

> [!TIP]
> Si necesita crear y mantener varias directivas para este escenario, plantéese usar [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) para una configuración más eficaz.

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a>Ejemplos de uso de varias directivas para evitar superar los límites máximos

Los ejemplos siguientes proporcionan algunas soluciones de diseño para cuando no pueda especificar solo la ubicación de una directiva de retención y debe tener en cuenta el máximo número de elementos documentados en la sección anterior.

Ejemplo de Exchange:

- **Requisito**: en una organización con más de 40.000 buzones de usuario, la mayoría de los usuarios deben tener su correo electrónico retenido durante 7 años, pero un subconjunto de usuarios identificados (425) debe tener su correo electrónico retenido solo durante 5 años.

- **Solución**: cree una directiva de retención para el correo electrónico de Exchange con un período de retención de 7 años y excluya el subconjunto de usuarios. Luego, cree una segunda directiva de retención para el correo electrónico de Exchange con un período de retención de 5 años e incluya el subconjunto de usuarios. 
    
    En ambos casos, el número de inclusiones y exclusiones se encuentra por debajo del número máximo de buzones especificados para una sola directiva, y el subconjunto de usuarios tiene que excluirse explícitamente de la primera directiva, ya que tiene un período de retención [más largo](retention.md#the-principles-of-retention-or-what-takes-precedence) que la segunda directiva. Si el subconjunto de usuarios necesita una directiva de retención más larga, no tendrá que excluirlos de la primera directiva.
     
    Con esta solución, si alguien nuevo se une a la organización, su buzón se incluirá automáticamente en la primera directiva durante 7 años y no hay ningún impacto en el número máximo de admitidos. Pero los nuevos usuarios que requieran el período de retención de 5 años se agregarán a los números de inclusiones y exclusiones, cuyo límite es 1000.

Ejemplo de SharePoint:

- **Requisito**: una organización tiene varios miles de sitios de SharePoint, pero solo 2000 sitios requieren un período de retención de 10 años y 8000 requieren un período de retención de 4 años.

- **Solución**: cree 20 directivas de retención para SharePoint con un período de retención de 10 años que incluya 100 sitios específicos y cree 80 directivas de retención para SharePoint con un período de retención de 4 años que incluya 100 sitios específicos.
    
    Como es necesario retener todos los sitios de SharePoint, debe crear directivas de retención que especifiquen los sitios específicos. Como una directiva de retención no admite más de 100 sitios específicos, debe crear varias directivas para los dos períodos de retención. Estas directivas de retención tienen el número máximo de sitios incluidos, por lo que el siguiente sitio nuevo que necesita retenerse requerirá una nueva directiva de retención, independientemente del periodo de retención.
