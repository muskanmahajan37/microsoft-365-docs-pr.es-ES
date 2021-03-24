---
title: Usar reglas de flujo de correo para filtrar correo masivo
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
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a usar reglas de flujo de correo (reglas de transporte) para identificar y filtrar el correo masivo (correo gris) en Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c86f229d6c7371854878a67937cc38374ed00961
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069888"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="8b27d-103">Usar reglas de flujo de correo para filtrar correo electrónico masivo en EOP</span><span class="sxs-lookup"><span data-stu-id="8b27d-103">Use mail flow rules to filter bulk email in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8b27d-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="8b27d-104">**Applies to**</span></span>
- [<span data-ttu-id="8b27d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8b27d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8b27d-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="8b27d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8b27d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b27d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="8b27d-108">En organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP usa directivas contra correo no deseado (también conocidas como directivas de filtro de correo no deseado o directivas de filtro de contenido) para examinar mensajes entrantes en busca de correo no deseado y correo masivo (también conocido como correo gris).</span><span class="sxs-lookup"><span data-stu-id="8b27d-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="8b27d-109">Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8b27d-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="8b27d-110">Si desea más opciones para filtrar el correo masivo, puede crear reglas de flujo de correo (también conocidas como reglas de transporte) para buscar patrones de texto o frases que se encuentran con frecuencia en el correo masivo y marcar esos mensajes como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="8b27d-110">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="8b27d-111">Para obtener más información acerca del correo masivo, vea ¿Cuál es la diferencia entre el correo no deseado y el correo [masivo?](what-s-the-difference-between-junk-email-and-bulk-email.md) y Nivel de queja masiva [(BCL) en EOP](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="8b27d-111">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="8b27d-112">En este tema se explica cómo crear estas reglas de flujo de correo en el Centro de administración de Exchange (EAC) y PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="8b27d-112">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8b27d-113">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="8b27d-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8b27d-114">Debe tener asignados permisos en Exchange Online o Exchange Online Protection antes de poder realizar los procedimientos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="8b27d-114">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="8b27d-115">En concreto, necesita el rol **Reglas** de transporte, que se asigna a los grupos de roles **Administración** de la **organización,** Administración de cumplimiento (administradores globales) y Administración **de** registros de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8b27d-115">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="8b27d-116">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="8b27d-116">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="8b27d-117">Permisos de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8b27d-117">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="8b27d-118">Permisos en EOP independiente</span><span class="sxs-lookup"><span data-stu-id="8b27d-118">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="8b27d-119">Usar el EAC modificar la lista de miembros en grupos de roles</span><span class="sxs-lookup"><span data-stu-id="8b27d-119">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="8b27d-120">Para abrir el EAC en Exchange Online, vea [Centro de administración de Exchange en Exchange Online](/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="8b27d-120">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="8b27d-121">Para abrir el EAC en EOP independiente, vea Centro de [administración de Exchange en EOP independiente.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="8b27d-121">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="8b27d-122">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="8b27d-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="8b27d-123">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="8b27d-123">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="8b27d-124">Para obtener más información acerca de las reglas de flujo de correo en Exchange Online y EOP independiente, consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="8b27d-124">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="8b27d-125">Reglas de flujo de correo (reglas de transporte) en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8b27d-125">Mail flow rules (transport rules) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="8b27d-126">Condiciones y excepciones de reglas de flujo de correo (predicados) en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8b27d-126">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="8b27d-127">Acciones de regla de flujo de correo en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8b27d-127">Mail flow rule actions in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="8b27d-128">La lista de palabras y patrones de texto que se usan para identificar el correo masivo en los ejemplos no son exhaustivas; puede agregar y quitar entradas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="8b27d-128">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="8b27d-129">Sin embargo, son un buen punto de partida.</span><span class="sxs-lookup"><span data-stu-id="8b27d-129">However, they are a good starting point.</span></span>

- <span data-ttu-id="8b27d-p107">La búsqueda de palabras o patrones de texto en el asunto u otros campos del encabezado del mensaje ocurre *después* de que el mensaje se haya decodificado desde el método de codificación de transferencia de contenido MIME que se usó para transmitir el mensaje binario entre los servidores SMTP en texto ASCII. No puede usar condiciones ni excepciones para buscar los valores codificados sin formato (normalmente, Base64) del asunto o de otros campos del encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="8b27d-p107">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="8b27d-132">Los siguientes procedimientos marcan un mensaje masivo como correo no deseado para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="8b27d-132">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="8b27d-133">Sin embargo, puede agregar otra condición para aplicar estas reglas solo a destinatarios específicos, por lo que puede usar el filtrado agresivo en unos pocos usuarios altamente dirigidos, mientras que el resto de los usuarios (que en su mayoría reciben el correo electrónico masivo con el que se han registrado) no se ve afectado.</span><span class="sxs-lookup"><span data-stu-id="8b27d-133">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="8b27d-134">Usar el EAC para crear reglas de flujo de correo que filtran correo masivo</span><span class="sxs-lookup"><span data-stu-id="8b27d-134">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="8b27d-135">En el EAC, vaya a **Flujo de correo** \> **Reglas**.</span><span class="sxs-lookup"><span data-stu-id="8b27d-135">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="8b27d-136">Haga **clic en** Agregar icono Agregar ![ ](../../media/ITPro-EAC-AddIcon.png) **y, a continuación, seleccione Crear una nueva regla.**</span><span class="sxs-lookup"><span data-stu-id="8b27d-136">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="8b27d-137">En la ventana **Nueva regla** que se abre, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="8b27d-137">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="8b27d-138">**Nombre:** escriba un nombre descriptivo único para la regla.</span><span class="sxs-lookup"><span data-stu-id="8b27d-138">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="8b27d-139">Haga clic en **Más opciones**.</span><span class="sxs-lookup"><span data-stu-id="8b27d-139">Click **More Options**.</span></span>

   - <span data-ttu-id="8b27d-140">**Aplique esta regla si:** configure una de las siguientes opciones para buscar contenido en mensajes con expresiones regulares (RegEx) o palabras o frases:</span><span class="sxs-lookup"><span data-stu-id="8b27d-140">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="8b27d-141">**El asunto o el cuerpo** \> **asunto o cuerpo** coincide con estos  patrones de texto: en el cuadro de diálogo Especificar palabras o frases que aparece, escriba uno de los siguientes valores, haga clic en **Agregar** icono y repita hasta que haya escrito todos los ![ ](../../media/ITPro-EAC-AddIcon.png) valores.</span><span class="sxs-lookup"><span data-stu-id="8b27d-141">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? src=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      <span data-ttu-id="8b27d-142">Para editar una entrada, selecciónelo y haga clic **en Editar** icono ![ Editar ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="8b27d-142">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="8b27d-143">Para quitar una entrada, selecciónelo y haga clic **en Quitar** icono ![ Quitar ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="8b27d-143">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="8b27d-144">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8b27d-144">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="8b27d-145">**El asunto o el cuerpo** \> **asunto o cuerpo** incluye cualquiera de  estas palabras: en el cuadro de diálogo Especificar  palabras o frases que aparece, escriba uno de los siguientes valores, haga clic en Agregar icono y repita hasta que haya escrito todos los ![ ](../../media/ITPro-EAC-AddIcon.png) valores.</span><span class="sxs-lookup"><span data-stu-id="8b27d-145">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `to change your preferences or unsubscribe`
       - `Modify email preferences or unsubscribe`
       - `This is a promotional email`
       - `You are receiving this email because you requested a subscription`
       - `click here to unsubscribe`
       - `You have received this email because you are subscribed`
       - `If you no longer wish to receive our email newsletter`
       - `to unsubscribe from this newsletter`
       - `If you have trouble viewing this email`
       - `This is an advertisement`
       - `you would like to unsubscribe or change your`
       - `view this email as a webpage`
       - `You are receiving this email because you are subscribed`

      <span data-ttu-id="8b27d-146">Para editar una entrada, selecciónelo y haga clic **en Editar** icono ![ Editar ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="8b27d-146">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="8b27d-147">Para quitar una entrada, selecciónelo y haga clic **en Quitar** icono ![ Quitar ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="8b27d-147">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="8b27d-148">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8b27d-148">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="8b27d-149">**Haga lo siguiente:** Seleccione **Modificar las propiedades del mensaje** para establecer el nivel de confianza de correo no deseado \> **(SCL).**</span><span class="sxs-lookup"><span data-stu-id="8b27d-149">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="8b27d-150">En el cuadro de diálogo Especificar **SCL** que aparece, configure una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="8b27d-150">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="8b27d-151">Para marcar los mensajes **como correo no** deseado, seleccione **6**.</span><span class="sxs-lookup"><span data-stu-id="8b27d-151">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="8b27d-152">La acción que ha  configurado para los veredictos de filtrado de correo no deseado en las directivas contra correo no deseado se aplica a los mensajes (el valor predeterminado es Mover mensaje a la carpeta **correo no deseado**).</span><span class="sxs-lookup"><span data-stu-id="8b27d-152">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="8b27d-153">Para marcar los mensajes como **correo no deseado de confianza alta,** seleccione **9**.</span><span class="sxs-lookup"><span data-stu-id="8b27d-153">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="8b27d-154">La acción que ha configurado para los veredictos de filtrado de **correo** no deseado de elevada confianza en las directivas contra correo no deseado se aplica a los mensajes (el valor predeterminado es Mover mensaje a la carpeta correo **no deseado**).</span><span class="sxs-lookup"><span data-stu-id="8b27d-154">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="8b27d-155">Para obtener más información acerca de los valores de SCL, vea Nivel de confianza de [correo no deseado (SCL) en EOP](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8b27d-155">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="8b27d-156">Cuando haya terminado, haga clic en **Guardar**</span><span class="sxs-lookup"><span data-stu-id="8b27d-156">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="8b27d-157">Usar PowerShell para crear reglas de flujo de correo que filtran el correo electrónico masivo</span><span class="sxs-lookup"><span data-stu-id="8b27d-157">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="8b27d-158">Use la sintaxis siguiente para crear una o ambas reglas de flujo de correo (expresiones regulares frente a palabras):</span><span class="sxs-lookup"><span data-stu-id="8b27d-158">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="8b27d-159">En este ejemplo se crea una nueva regla denominada "Filtrado masivo de correo electrónico - RegEx" que usa la misma lista de expresiones regulares de anteriormente en el tema para establecer mensajes como **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="8b27d-159">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="8b27d-160">En este ejemplo se crea una nueva regla denominada "Filtrado masivo de correo electrónico: palabras" que usa la misma lista de palabras de anteriormente en el tema para establecer mensajes como correo no deseado **de elevada confianza.**</span><span class="sxs-lookup"><span data-stu-id="8b27d-160">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="8b27d-161">Para obtener información detallada acerca de la sintaxis y los parámetros, vea [New-TransportRule](/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="8b27d-161">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="8b27d-162">¿Cómo saber si el proceso se completó correctamente?</span><span class="sxs-lookup"><span data-stu-id="8b27d-162">How do you know this worked?</span></span>

<span data-ttu-id="8b27d-163">Para comprobar que ha configurado reglas de flujo de correo para filtrar correo masivo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8b27d-163">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="8b27d-164">En el EAC, vaya a **Flujo** de correo Reglas seleccione la regla haga clic en \>  \> \> **Editar** icono Editar y compruebe ![ la ](../../media/ITPro-EAC-EditIcon.png) configuración.</span><span class="sxs-lookup"><span data-stu-id="8b27d-164">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="8b27d-165">En PowerShell, reemplace por el nombre de la regla y \<Rule Name\> ejecute el siguiente comando para comprobar la configuración:</span><span class="sxs-lookup"><span data-stu-id="8b27d-165">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="8b27d-166">Desde una cuenta externa, envíe un mensaje de prueba a un destinatario afectado que contenga una de las frases o patrones de texto y compruebe los resultados.</span><span class="sxs-lookup"><span data-stu-id="8b27d-166">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>