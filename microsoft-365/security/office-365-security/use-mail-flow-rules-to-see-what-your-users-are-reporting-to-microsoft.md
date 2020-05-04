---
title: Usar reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a usar reglas de flujo de correo (también conocidas como reglas de transporte) para recibir copias de mensajes que los usuarios notifican a Microsoft.
ms.openlocfilehash: 2b1e82ece936551c48e5617955f546cf851a8913
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939504"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Usar reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft

Hay varias formas de que los usuarios informen de los mensajes a Microsoft para su análisis, como se describe en [mensajes de informes y archivos de Microsoft](report-junk-email-messages-to-microsoft.md).

Puede crear una regla de flujo de correo (también denominada regla de transporte) que busque mensajes que los usuarios notifican a Microsoft y puede configurar destinatarios de CCO para recibir copias de estos mensajes notificados.

Puede crear la regla de flujo de correo en el centro de administración de Exchange (EAC) y PowerShell (Exchange Online PowerShell para los clientes de Microsoft 365; Exchange Online Protection PowerShell para clientes independientes de EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Debe tener asignados permisos en Exchange online o EOP para poder realizar estos procedimientos. En concreto, debe tener asignado el rol **reglas de transporte** , que se asigna a las **funciones administración**de la organización, **Administración del cumplimiento**y administración de **registros** de forma predeterminada. Para obtener más información, consulte[Administrar grupos de roles en Exchange en línea](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Para abrir el EAC, consulte [centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) o [Exchange admin Center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Para conectarse a Exchange Online Protection PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Para obtener más información acerca de las reglas de flujo de correo en Exchange Online y EOP independiente, consulte los siguientes temas:

  - [Reglas de flujo de correo (reglas de transporte) en Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Excepciones (predicados) y condiciones de reglas de flujo de correo en Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Acciones de las reglas de flujo de correo en Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Usar el EAC para crear una regla de flujo de correo para recibir copias de mensajes notificados

1. En el EAC, vaya a **Flujo de correo** \> **Reglas**.

2. Haga **Add** ![clic en agregar](../../media/ITPro-EAC-AddIcon.png) icono Agregar y, a continuación, seleccione **crear una nueva regla**.

3. En la ventana **Nueva regla** que se abre, configure las siguientes opciones:

   - **Name**: escriba un nombre único y descriptivo para la regla. Por ejemplo, los mensajes CCO que se notifican a Microsoft.

   - Haga clic en **Más opciones**.

   - **Aplicar esta regla si**: seleccione **la dirección del destinatario** \> **incluye cualquiera de estas palabras**: en el cuadro de diálogo **especificar palabras o frases** que aparece, escriba uno de los siguientes valores, haga](../../media/ITPro-EAC-AddIcon.png)clic en **Agregar** ![icono Agregar y repita el procedimiento hasta que haya introducido todos los valores.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     Para editar una entrada, selecciónela y haga clic en **Editar** ![icono](../../media/ITPro-EAC-EditIcon.png)de edición. Para quitar una entrada, selecciónela y haga clic en **quitar** ![icono](../../media/ITPro-EAC-DeleteIcon.png)quitar.

     Cuando haya terminado, haga clic en **Aceptar**.

   - **Haga lo siguiente**: seleccione **agregar destinatarios** \> **en el cuadro CCO**. En el cuadro de diálogo que aparece, busque y seleccione los destinatarios que desea agregar. Cuando haya terminado, haga clic en **Aceptar**.

4. Puede realizar selecciones adicionales para auditar la regla, probarla, activar la regla durante un período de tiempo específico y otras opciones de configuración. Se recomienda probar la regla antes de aplicarla.

5. Cuando haya terminado, haga clic en **Guardar**.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Usar PowerShell para crear una regla de flujo de correo para recibir copias de mensajes notificados

En este ejemplo se crea una nueva regla de flujo de correo denominada BCC mensajes enviados a Microsoft que busca mensajes de correo electrónico que se notifican a Microsoft mediante los métodos descritos en este tema y agrega los usuarios laura@contoso.com y julia@contoso.com como destinatarios CCO.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Para obtener información detallada acerca de la sintaxis y los parámetros, vea [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se completó correctamente?

Para comprobar que ha configurado una regla de flujo de correo para recibir copias de mensajes enviados, siga uno de estos pasos:

- En el EAC, vaya a **Mail flow** \> **reglas** \> de flujo de correo Seleccione \> la regla haga clic](../../media/ITPro-EAC-EditIcon.png)en **Editar** ![icono de edición y Compruebe la configuración.

- En PowerShell, ejecute el siguiente comando para comprobar la configuración:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Envíe mensajes de prueba a una de las direcciones de correo electrónico de informes y compruebe los resultados.