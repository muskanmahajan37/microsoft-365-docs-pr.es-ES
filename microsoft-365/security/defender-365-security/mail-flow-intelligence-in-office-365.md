---
title: Inteligencia de flujo de correo
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Los administradores pueden obtener información sobre los códigos de error asociados con la entrega de mensajes mediante conectores (también conocidos como inteligencia de flujo de correo).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2cb52e5865415440b3b2924a3ebcc96a7f8e17e5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071363"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="c20d2-103">Inteligencia de flujo de correo en EOP</span><span class="sxs-lookup"><span data-stu-id="c20d2-103">Mail flow intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c20d2-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="c20d2-104">**Applies to**</span></span>
- [<span data-ttu-id="c20d2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c20d2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c20d2-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c20d2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c20d2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c20d2-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c20d2-108">En las organizaciones de Microsoft 365 con buzones en Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, normalmente se usa un conector para enrutar mensajes de correo electrónico de EOP a su entorno de correo electrónico local.</span><span class="sxs-lookup"><span data-stu-id="c20d2-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="c20d2-109">También puede usar un conector para enrutar mensajes de Microsoft 365 a una organización asociada.</span><span class="sxs-lookup"><span data-stu-id="c20d2-109">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="c20d2-110">Cuando Microsoft 365 no puede entregar estos mensajes a través del conector, se ponen en cola en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c20d2-110">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="c20d2-111">Microsoft 365 seguirá reintentiendo la entrega de cada mensaje durante 24 horas.</span><span class="sxs-lookup"><span data-stu-id="c20d2-111">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="c20d2-112">Después de 24 horas, el mensaje en cola expirará y el mensaje se devolverá al remitente original en un informe de no entrega (también conocido como NDR o mensaje de devolución).</span><span class="sxs-lookup"><span data-stu-id="c20d2-112">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="c20d2-113">Microsoft 365 genera un error cuando no se puede entregar un mensaje mediante un conector.</span><span class="sxs-lookup"><span data-stu-id="c20d2-113">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="c20d2-114">Los errores más comunes y sus soluciones se describen en este artículo.</span><span class="sxs-lookup"><span data-stu-id="c20d2-114">The most common errors and their solutions are described in this article.</span></span> <span data-ttu-id="c20d2-115">Colectivamente, los errores de cola y notificación de mensajes no entregados enviados a través de conectores se conocen como inteligencia de _flujo de correo_.</span><span class="sxs-lookup"><span data-stu-id="c20d2-115">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="c20d2-116">Código de error: error en la consulta DNS 4.4.312</span><span class="sxs-lookup"><span data-stu-id="c20d2-116">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="c20d2-117">Normalmente, este error significa que Microsoft 365 intentó conectarse al host inteligente especificado en el conector, pero la consulta DNS para encontrar las direcciones IP del host inteligente produjo un error.</span><span class="sxs-lookup"><span data-stu-id="c20d2-117">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="c20d2-118">Las causas posibles de este error son:</span><span class="sxs-lookup"><span data-stu-id="c20d2-118">The possible causes for this error are:</span></span>

- <span data-ttu-id="c20d2-119">Hay un problema con el servicio de hospedaje DNS de su dominio (la parte que mantiene los servidores de nombres autoritativo para su dominio).</span><span class="sxs-lookup"><span data-stu-id="c20d2-119">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="c20d2-120">El dominio ha expirado recientemente, por lo que no se puede recuperar el registro MX.</span><span class="sxs-lookup"><span data-stu-id="c20d2-120">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="c20d2-121">El registro MX del dominio ha cambiado recientemente y los servidores DNS aún tienen información de DNS almacenada previamente en caché para el dominio.</span><span class="sxs-lookup"><span data-stu-id="c20d2-121">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="c20d2-122">¿Cómo se corrige el código de error 450 4.4.312?</span><span class="sxs-lookup"><span data-stu-id="c20d2-122">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="c20d2-123">Trabaje con el servicio de hospedaje DNS para identificar y solucionar el problema con su dominio.</span><span class="sxs-lookup"><span data-stu-id="c20d2-123">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="c20d2-124">Si el error es de su organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), póngase en contacto con su partner para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="c20d2-124">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="c20d2-125">Código de error: 450 4.4.315 Tiempo de espera de conexión</span><span class="sxs-lookup"><span data-stu-id="c20d2-125">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="c20d2-126">Normalmente, esto significa que Microsoft 365 no puede conectarse al servidor de correo electrónico de destino.</span><span class="sxs-lookup"><span data-stu-id="c20d2-126">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="c20d2-127">Los detalles del error explicarán el problema.</span><span class="sxs-lookup"><span data-stu-id="c20d2-127">The error details will explain the problem.</span></span> <span data-ttu-id="c20d2-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c20d2-128">For example:</span></span>

- <span data-ttu-id="c20d2-129">El servidor de correo electrónico local no está disponible.</span><span class="sxs-lookup"><span data-stu-id="c20d2-129">Your on-premises email server is down.</span></span>

- <span data-ttu-id="c20d2-130">Hay un error en la configuración de host inteligente del conector, por lo que Microsoft 365 está intentando conectarse a la dirección IP incorrecta.</span><span class="sxs-lookup"><span data-stu-id="c20d2-130">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="c20d2-131">¿Cómo se corrige el código de error 450 4.4.315?</span><span class="sxs-lookup"><span data-stu-id="c20d2-131">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="c20d2-132">Descubra qué escenario se aplica a usted y realice las correcciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="c20d2-132">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="c20d2-133">Por ejemplo, si el flujo de correo ha funcionado correctamente y no ha cambiado la configuración del conector, debe comprobar el entorno de correo electrónico local para ver si el servidor está abajo o si ha habido cambios en la infraestructura de red (por ejemplo, ha cambiado los proveedores de servicios de Internet, por lo que ahora tiene diferentes direcciones IP).</span><span class="sxs-lookup"><span data-stu-id="c20d2-133">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="c20d2-134">Si el error es de su organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), póngase en contacto con su partner para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="c20d2-134">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="c20d2-135">Código de error: 450 4.4.316 Conexión rechazada</span><span class="sxs-lookup"><span data-stu-id="c20d2-135">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="c20d2-136">Normalmente, este error significa que Microsoft 365 encontró un error de conexión cuando intentó conectarse al servidor de correo electrónico de destino.</span><span class="sxs-lookup"><span data-stu-id="c20d2-136">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="c20d2-137">Una causa probable de este error es que el firewall bloquea las conexiones de direcciones IP de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c20d2-137">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="c20d2-138">O bien, este error puede deberse al diseño si ha migrado completamente el sistema de correo electrónico local a Microsoft 365 y ha apagado el entorno de correo electrónico local.</span><span class="sxs-lookup"><span data-stu-id="c20d2-138">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="c20d2-139">¿Cómo se corrige el código de error 450 4.4.316?</span><span class="sxs-lookup"><span data-stu-id="c20d2-139">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="c20d2-140">Si tiene buzones en el entorno local, debe modificar la configuración del firewall para permitir conexiones de direcciones IP de Microsoft 365 en el puerto TCP 25 a los servidores de correo electrónico locales.</span><span class="sxs-lookup"><span data-stu-id="c20d2-140">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="c20d2-141">Para obtener una lista de las direcciones IP de Microsoft 365, vea Direcciones URL e [intervalos de direcciones IP de Microsoft 365](../../enterprise/urls-and-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="c20d2-141">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](../../enterprise/urls-and-ip-address-ranges.md).</span></span>

- <span data-ttu-id="c20d2-142">Si no se deben entregar más mensajes en  el entorno local, haga clic en Corregir ahora en la alerta para que Microsoft 365 pueda rechazar inmediatamente los mensajes con destinatarios no válidos.</span><span class="sxs-lookup"><span data-stu-id="c20d2-142">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="c20d2-143">Esto reducirá el riesgo de exceder la cuota de la organización para destinatarios no válidos, lo que podría afectar a la entrega normal de mensajes.</span><span class="sxs-lookup"><span data-stu-id="c20d2-143">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="c20d2-144">O bien, puede usar las siguientes instrucciones para solucionar manualmente el problema:</span><span class="sxs-lookup"><span data-stu-id="c20d2-144">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="c20d2-145">En el [Centro de administración de Exchange (EAC),](/Exchange/exchange-admin-center)deshabilite o elimine el conector que entrega correo electrónico de Microsoft 365 a su entorno de correo electrónico local:</span><span class="sxs-lookup"><span data-stu-id="c20d2-145">In the [Exchange admin center (EAC)](/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="c20d2-146">En el EAC, vaya a **Flujo de correo** \> **Conectores**.</span><span class="sxs-lookup"><span data-stu-id="c20d2-146">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="c20d2-147">Seleccione el conector con el valor **De** de  **Office 365** y el valor **Para** del servidor de correo electrónico de su organización y siga uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c20d2-147">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="c20d2-148">Para eliminar el conector, haga clic **en Eliminar** ![ icono Quitar](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="c20d2-148">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="c20d2-149">Para deshabilitar el conector, **haga clic en Editar** icono editar y desactive ![ ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) **Activar**.</span><span class="sxs-lookup"><span data-stu-id="c20d2-149">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and clearing **Turn it on**.</span></span>

  - <span data-ttu-id="c20d2-150">Cambie el dominio aceptado en Microsoft 365 asociado al entorno de correo electrónico local de **Retransmisión interna** a **Autoritativo.**</span><span class="sxs-lookup"><span data-stu-id="c20d2-150">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="c20d2-151">Para obtener instrucciones, vea [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="c20d2-151">For instructions, see [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="c20d2-152">**Nota:** Estos cambios suelen tardar entre 30 minutos y una hora en tener efecto.</span><span class="sxs-lookup"><span data-stu-id="c20d2-152">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="c20d2-153">Después de una hora, compruebe que ya no recibe el error.</span><span class="sxs-lookup"><span data-stu-id="c20d2-153">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="c20d2-154">Si el error es de su organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), debe ponerse en contacto con su partner para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="c20d2-154">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="c20d2-155">Código de error: 450 4.4.317 No se puede conectar al servidor remoto</span><span class="sxs-lookup"><span data-stu-id="c20d2-155">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="c20d2-156">Normalmente, este error significa Microsoft 365 conectado al servidor de correo electrónico de destino, pero el servidor respondió con un error inmediato o no cumple los requisitos de conexión.</span><span class="sxs-lookup"><span data-stu-id="c20d2-156">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="c20d2-157">Los detalles del error explicarán el problema.</span><span class="sxs-lookup"><span data-stu-id="c20d2-157">The error details will explain the problem.</span></span> <span data-ttu-id="c20d2-158">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c20d2-158">For example:</span></span>

- <span data-ttu-id="c20d2-159">El servidor de correo electrónico de destino respondió con un error "Servicio no disponible", que indica que el servidor no puede mantener la comunicación con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c20d2-159">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>

- <span data-ttu-id="c20d2-160">El conector está configurado para requerir TLS, pero el servidor de correo electrónico de destino no admite TLS.</span><span class="sxs-lookup"><span data-stu-id="c20d2-160">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="c20d2-161">¿Cómo se corrige el código de error 450 4.4.317?</span><span class="sxs-lookup"><span data-stu-id="c20d2-161">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="c20d2-162">Compruebe la configuración de TLS y los certificados en los servidores de correo electrónico locales y la configuración de TLS en el conector.</span><span class="sxs-lookup"><span data-stu-id="c20d2-162">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="c20d2-163">Si el error es de su organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), debe ponerse en contacto con su partner para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="c20d2-163">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="c20d2-164">Código de error: 450 4.4.318 Connection se cerró abruptamente</span><span class="sxs-lookup"><span data-stu-id="c20d2-164">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="c20d2-165">Normalmente, este error significa que Microsoft 365 tiene dificultades para comunicarse con el entorno de correo electrónico local, por lo que se ha descartado la conexión.</span><span class="sxs-lookup"><span data-stu-id="c20d2-165">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="c20d2-166">Las causas posibles de este error son:</span><span class="sxs-lookup"><span data-stu-id="c20d2-166">The possible causes for this error are:</span></span>

- <span data-ttu-id="c20d2-167">El firewall usa reglas de examen de paquete SMTP y esas reglas no funcionan correctamente.</span><span class="sxs-lookup"><span data-stu-id="c20d2-167">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="c20d2-168">El servidor de correo electrónico local no funciona correctamente (por ejemplo, el servicio se bloquea, se bloquea o tiene pocos recursos del sistema), lo que hace que el servidor de tiempo de espera y cierre la conexión a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c20d2-168">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>

- <span data-ttu-id="c20d2-169">Hay problemas de red entre el entorno local y Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c20d2-169">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="c20d2-170">¿Cómo se corrige el código de error 450 4.4.318?</span><span class="sxs-lookup"><span data-stu-id="c20d2-170">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="c20d2-171">Descubra qué escenario se aplica a usted y realice las correcciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="c20d2-171">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="c20d2-172">Si el problema se debe a problemas de red entre el entorno local y Microsoft 365, póngase en contacto con el equipo de red para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="c20d2-172">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="c20d2-173">Si el error es de su organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), debe ponerse en contacto con su partner para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="c20d2-173">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="c20d2-174">Código de error: error en la validación del certificado 4.7.320 450</span><span class="sxs-lookup"><span data-stu-id="c20d2-174">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="c20d2-175">Normalmente, este error significa que Microsoft 365 encontró un error al intentar validar el certificado del servidor de correo electrónico de destino.</span><span class="sxs-lookup"><span data-stu-id="c20d2-175">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="c20d2-176">Los detalles del error explicarán el error.</span><span class="sxs-lookup"><span data-stu-id="c20d2-176">The error details will explain the error.</span></span> <span data-ttu-id="c20d2-177">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c20d2-177">For example:</span></span>

- <span data-ttu-id="c20d2-178">Certificado expirado</span><span class="sxs-lookup"><span data-stu-id="c20d2-178">Certificate expired</span></span>

- <span data-ttu-id="c20d2-179">Error de coincidencia del asunto del certificado</span><span class="sxs-lookup"><span data-stu-id="c20d2-179">Certificate subject mismatch</span></span>

- <span data-ttu-id="c20d2-180">El certificado ya no es válido</span><span class="sxs-lookup"><span data-stu-id="c20d2-180">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="c20d2-181">¿Cómo se corrige el código de error 450 4.7.320?</span><span class="sxs-lookup"><span data-stu-id="c20d2-181">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="c20d2-182">Corrija el certificado o la configuración del conector para que se puedan entregar los mensajes en cola en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c20d2-182">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>

- <span data-ttu-id="c20d2-183">Si el error es de su organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), debe ponerse en contacto con su partner para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="c20d2-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="c20d2-184">Otros códigos de error</span><span class="sxs-lookup"><span data-stu-id="c20d2-184">Other error codes</span></span>

<span data-ttu-id="c20d2-185">Microsoft 365 tiene dificultades para entregar mensajes a su servidor de correo electrónico local o asociado.</span><span class="sxs-lookup"><span data-stu-id="c20d2-185">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="c20d2-186">Use la **información del servidor** de destino en el error para examinar el problema en el entorno o modificar el conector si hay un error de configuración.</span><span class="sxs-lookup"><span data-stu-id="c20d2-186">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="c20d2-187">Si el error es de su organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), debe ponerse en contacto con su partner para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="c20d2-187">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>