---
title: Usar reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a usar reglas de flujo de correo (también conocidas como reglas de transporte) para recibir copias de los mensajes que los usuarios informan a Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e6428a228ae64562f0b529f6aa90ddc3be46fdc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069936"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="08df3-103">Usar reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft</span><span class="sxs-lookup"><span data-stu-id="08df3-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="08df3-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="08df3-104">**Applies to**</span></span>
- [<span data-ttu-id="08df3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="08df3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="08df3-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="08df3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="08df3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="08df3-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="08df3-108">En las organizaciones de Microsoft 365 con buzones en Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, hay varias maneras de que los usuarios informen mensajes a Microsoft para su análisis, tal como se describe en Notificar mensajes y archivos a [Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="08df3-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="08df3-109">Puede crear una regla de flujo de correo (también conocida como regla de transporte) que busca los mensajes que los usuarios notifican a Microsoft y puede configurar destinatarios CCO para que reciban copias de estos mensajes notificados.</span><span class="sxs-lookup"><span data-stu-id="08df3-109">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="08df3-110">Puede crear la regla de flujo de correo en el Centro de administración de Exchange (EAC) y PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell EOP independiente para organizaciones sin buzones de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="08df3-110">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="08df3-111">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="08df3-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="08df3-112">Debe tener asignados permisos en Exchange Online o Exchange Online Protection antes de poder realizar los procedimientos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="08df3-112">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="08df3-113">En concreto, necesita el rol **Reglas** de transporte, que se asigna a los grupos de roles **Administración** de la **organización,** Administración de cumplimiento (administradores globales) y Administración **de** registros de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="08df3-113">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="08df3-114">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="08df3-114">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="08df3-115">Permisos de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="08df3-115">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="08df3-116">Permisos en EOP independiente</span><span class="sxs-lookup"><span data-stu-id="08df3-116">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="08df3-117">Usar el EAC modificar la lista de miembros en grupos de roles</span><span class="sxs-lookup"><span data-stu-id="08df3-117">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="08df3-118">Para abrir el EAC en Exchange Online, vea [Centro de administración de Exchange en Exchange Online](/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="08df3-118">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="08df3-119">Para abrir el EAC en EOP independiente, vea Centro de [administración de Exchange en EOP independiente.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="08df3-119">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="08df3-120">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="08df3-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="08df3-121">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="08df3-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="08df3-122">Para obtener más información acerca de las reglas de flujo de correo en Exchange Online y EOP independiente, consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="08df3-122">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>
  - [<span data-ttu-id="08df3-123">Reglas de flujo de correo (reglas de transporte) en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="08df3-123">Mail flow rules (transport rules) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [<span data-ttu-id="08df3-124">Condiciones y excepciones de reglas de flujo de correo (predicados) en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="08df3-124">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [<span data-ttu-id="08df3-125">Acciones de regla de flujo de correo en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="08df3-125">Mail flow rule actions in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="08df3-126">Usar el EAC para crear una regla de flujo de correo para recibir copias de mensajes notificados</span><span class="sxs-lookup"><span data-stu-id="08df3-126">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="08df3-127">En el EAC, vaya a **Flujo de correo** \> **Reglas**.</span><span class="sxs-lookup"><span data-stu-id="08df3-127">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="08df3-128">Haga **clic en** Agregar icono Agregar ![ ](../../media/ITPro-EAC-AddIcon.png) **y, a continuación, seleccione Crear una nueva regla.**</span><span class="sxs-lookup"><span data-stu-id="08df3-128">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="08df3-129">En la ventana **Nueva regla** que se abre, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="08df3-129">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="08df3-130">**Nombre:** escriba un nombre descriptivo único para la regla.</span><span class="sxs-lookup"><span data-stu-id="08df3-130">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="08df3-131">Por ejemplo, Mensajes CCO notificados a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="08df3-131">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="08df3-132">Haga clic en **Más opciones**.</span><span class="sxs-lookup"><span data-stu-id="08df3-132">Click **More Options**.</span></span>

   - <span data-ttu-id="08df3-133">**Aplique** esta regla si : **Seleccione** La dirección del destinatario incluye cualquiera de estas palabras: en el cuadro de diálogo Especificar palabras o frases que aparece, escriba uno de los siguientes valores, haga clic en Agregar icono y repita hasta que haya escrito todos los \>    ![ ](../../media/ITPro-EAC-AddIcon.png) valores.</span><span class="sxs-lookup"><span data-stu-id="08df3-133">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     <span data-ttu-id="08df3-134">Para editar una entrada, selecciónelo y haga clic **en Editar** icono ![ Editar ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="08df3-134">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="08df3-135">Para quitar una entrada, selecciónelo y haga clic **en Quitar** icono ![ Quitar ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="08df3-135">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="08df3-136">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="08df3-136">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="08df3-137">**Haga lo siguiente:** Seleccione **Agregar destinatarios** \> **al cuadro CCO**.</span><span class="sxs-lookup"><span data-stu-id="08df3-137">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="08df3-138">En el cuadro de diálogo que aparece, busque y seleccione los destinatarios que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="08df3-138">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="08df3-139">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="08df3-139">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="08df3-140">Puede realizar selecciones adicionales para auditar la regla, probarla, activarla durante un período de tiempo específico y otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="08df3-140">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="08df3-141">Se recomienda probar la regla antes de aplicarla.</span><span class="sxs-lookup"><span data-stu-id="08df3-141">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="08df3-142">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="08df3-142">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="08df3-143">Usar PowerShell para crear una regla de flujo de correo para recibir copias de mensajes notificados</span><span class="sxs-lookup"><span data-stu-id="08df3-143">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="08df3-144">En este ejemplo se crea una nueva regla de flujo de correo denominada Mensajes CCO notificados a Microsoft que busca mensajes de correo electrónico notificados a Microsoft mediante los métodos descritos en este artículo y agrega los usuarios laura@contoso.com y julia@contoso.com como destinatarios CCO.</span><span class="sxs-lookup"><span data-stu-id="08df3-144">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this article, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="08df3-145">Para obtener información detallada acerca de la sintaxis y los parámetros, vea [New-TransportRule](/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="08df3-145">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="08df3-146">¿Cómo saber si el proceso se completó correctamente?</span><span class="sxs-lookup"><span data-stu-id="08df3-146">How do you know this worked?</span></span>

<span data-ttu-id="08df3-147">Para comprobar que ha configurado una regla de flujo de correo para recibir copias de los mensajes notificados, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="08df3-147">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="08df3-148">En el EAC, vaya a **Flujo** de correo Reglas seleccione la regla haga clic en \>  \> \> **Editar** icono Editar y compruebe ![ la ](../../media/ITPro-EAC-EditIcon.png) configuración.</span><span class="sxs-lookup"><span data-stu-id="08df3-148">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="08df3-149">En PowerShell, ejecute el siguiente comando para comprobar la configuración:</span><span class="sxs-lookup"><span data-stu-id="08df3-149">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="08df3-150">Enviar mensajes de prueba a una de las direcciones de correo electrónico de informes y comprobar los resultados.</span><span class="sxs-lookup"><span data-stu-id="08df3-150">Send a test messages to one of the reporting email addresses and verify the results.</span></span>