---
title: Investigar una cuenta de usuario en ATP de Microsoft Defender
description: Investigue una cuenta de usuario para obtener credenciales potencialmente comprometidas o pivote en la cuenta de usuario asociada durante una investigación.
keywords: investigar, cuenta, usuario, entidad de usuario, alerta, atp de Microsoft Defender
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: e994069220d8f88f1b8910413ad86da399c4a8f3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072331"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="23143-104">Investigar una cuenta de usuario en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="23143-104">Investigate a user account in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="23143-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="23143-105">**Applies to:**</span></span>
- [<span data-ttu-id="23143-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="23143-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="23143-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23143-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="23143-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="23143-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="23143-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="23143-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a><span data-ttu-id="23143-110">Investigar entidades de cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="23143-110">Investigate user account entities</span></span>

<span data-ttu-id="23143-111">Identifique las cuentas de usuario con las alertas más activas (mostradas en el panel como "Usuarios en riesgo") e investigue casos de credenciales potencialmente comprometidas, o pivote en la cuenta de usuario asociada al investigar una alerta o dispositivo para identificar posibles movimientos laterales entre dispositivos con esa cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="23143-111">Identify user accounts with the most active alerts (displayed on dashboard as "Users at risk") and investigate cases of potential compromised credentials, or pivot on the associated user account when investigating an alert or device to identify possible lateral movement between devices with that user account.</span></span>

<span data-ttu-id="23143-112">Puede encontrar información de cuenta de usuario en las siguientes vistas:</span><span class="sxs-lookup"><span data-stu-id="23143-112">You can find user account information in the following views:</span></span>

- <span data-ttu-id="23143-113">Panel</span><span class="sxs-lookup"><span data-stu-id="23143-113">Dashboard</span></span>
- <span data-ttu-id="23143-114">Cola de alertas</span><span class="sxs-lookup"><span data-stu-id="23143-114">Alert queue</span></span>
- <span data-ttu-id="23143-115">Página de detalles del dispositivo</span><span class="sxs-lookup"><span data-stu-id="23143-115">Device details page</span></span>

<span data-ttu-id="23143-116">En estas vistas hay disponible un vínculo de cuenta de usuario en el que se puede hacer clic, que le llevará a la página de detalles de la cuenta de usuario donde se muestran más detalles sobre la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="23143-116">A clickable user account link is available in these views, that will take you to the user account details page where more details about the user account are shown.</span></span>

<span data-ttu-id="23143-117">Cuando investigue una entidad de cuenta de usuario, verá:</span><span class="sxs-lookup"><span data-stu-id="23143-117">When you investigate a user account entity, you'll see:</span></span>

- <span data-ttu-id="23143-118">Detalles de la cuenta de usuario, alertas de Azure Advanced Threat Protection (Azure ATP) y dispositivos, rol, tipo de inicio de sesión y otros detalles</span><span class="sxs-lookup"><span data-stu-id="23143-118">User account details, Azure Advanced Threat Protection (Azure ATP) alerts, and logged on devices, role, logon type, and other details</span></span>
- <span data-ttu-id="23143-119">Información general sobre los incidentes y los dispositivos del usuario</span><span class="sxs-lookup"><span data-stu-id="23143-119">Overview of the incidents and user's devices</span></span>
- <span data-ttu-id="23143-120">Alertas relacionadas con este usuario</span><span class="sxs-lookup"><span data-stu-id="23143-120">Alerts related to this user</span></span>
- <span data-ttu-id="23143-121">Observado en la organización (dispositivos que iniciaron sesión en)</span><span class="sxs-lookup"><span data-stu-id="23143-121">Observed in organization (devices logged on to)</span></span>

![Imagen de la página de detalles de la entidad de la cuenta de usuario](images/atp-user-details-view.png)

### <a name="user-details"></a><span data-ttu-id="23143-123">Detalles del usuario</span><span class="sxs-lookup"><span data-stu-id="23143-123">User details</span></span>

<span data-ttu-id="23143-124">El  panel de detalles del usuario a la izquierda proporciona información sobre el usuario, como incidentes abiertos relacionados, alertas activas, nombre SAM, SID, alertas de ATP de Azure, número de dispositivos en los que el usuario ha iniciado sesión, cuándo se ha visto por primera vez y por última vez, tipos de rol e inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="23143-124">The **User details** pane on left provides information about the user, such as related open incidents, active alerts, SAM name, SID, Azure ATP alerts, number of devices the user is logged on to, when the user was first and last seen, role, and logon types.</span></span> <span data-ttu-id="23143-125">Dependiendo de las características de integración que haya habilitado, verá otros detalles.</span><span class="sxs-lookup"><span data-stu-id="23143-125">Depending on the integration features you've enabled, you'll see other details.</span></span> <span data-ttu-id="23143-126">Por ejemplo, si habilita la integración de Skype Empresarial, podrá ponerse en contacto con el usuario desde el portal.</span><span class="sxs-lookup"><span data-stu-id="23143-126">For example, if you enable the Skype for business integration, you'll be able to contact the user from the portal.</span></span> <span data-ttu-id="23143-127">La **sección Alertas de ATP** de Azure contiene un vínculo que le llevará a la página de ATP de Azure, si ha habilitado la característica de ATP de Azure y hay alertas relacionadas con el usuario.</span><span class="sxs-lookup"><span data-stu-id="23143-127">The **Azure ATP alerts** section contains a link that will take you to the Azure ATP page, if you have enabled the Azure ATP feature, and there are alerts related to the user.</span></span> <span data-ttu-id="23143-128">La página DE ATP de Azure proporcionará más información sobre las alertas.</span><span class="sxs-lookup"><span data-stu-id="23143-128">The Azure ATP page will provide more information about the alerts.</span></span>

>[!NOTE]
><span data-ttu-id="23143-129">Tendrás que habilitar la integración en Azure ATP y Defender para endpoint para usar esta característica.</span><span class="sxs-lookup"><span data-stu-id="23143-129">You'll need to enable the integration on both Azure ATP and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="23143-130">En Defender para endpoint, puedes habilitar esta característica en características avanzadas.</span><span class="sxs-lookup"><span data-stu-id="23143-130">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="23143-131">Para obtener más información sobre cómo habilitar características avanzadas, vea [Activar características avanzadas.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="23143-131">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

<span data-ttu-id="23143-132">Overview, Alerts y Observed in organization son pestañas diferentes que muestran varios atributos sobre la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="23143-132">The Overview, Alerts, and Observed in organization are different tabs that display various attributes about the user account.</span></span>

### <a name="overview"></a><span data-ttu-id="23143-133">Información general</span><span class="sxs-lookup"><span data-stu-id="23143-133">Overview</span></span>

<span data-ttu-id="23143-134">La **pestaña** Información general muestra los detalles de incidentes y una lista de los dispositivos en los que el usuario ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="23143-134">The **Overview** tab shows the incidents details and a list of the devices that the user has logged on to.</span></span> <span data-ttu-id="23143-135">Puedes expandir estos para ver detalles de los eventos de inicio de sesión para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="23143-135">You can expand these to see details of the log-on events for each device.</span></span>

### <a name="alerts"></a><span data-ttu-id="23143-136">Alertas</span><span class="sxs-lookup"><span data-stu-id="23143-136">Alerts</span></span>

<span data-ttu-id="23143-137">La **pestaña** Alertas proporciona una lista de alertas asociadas con la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="23143-137">The **Alerts** tab provides a list of alerts that are associated with the user account.</span></span> <span data-ttu-id="23143-138">Esta lista es una [](alerts-queue.md)vista filtrada de la cola de alertas y muestra alertas en las que el contexto del usuario es la cuenta de usuario seleccionada, la fecha en que se detectó la última actividad, una breve descripción de la alerta, el dispositivo asociado a la alerta, la gravedad de la alerta, el estado de la alerta en la cola y quién tiene asignada la alerta.</span><span class="sxs-lookup"><span data-stu-id="23143-138">This list is a filtered view of the [Alert queue](alerts-queue.md), and shows alerts where the user context is the selected user account, the date when the last activity was detected, a short description of the alert, the device associated with the alert, the alert's severity, the alert's status in the queue, and who is assigned the alert.</span></span>

### <a name="observed-in-organization"></a><span data-ttu-id="23143-139">Observado en la organización</span><span class="sxs-lookup"><span data-stu-id="23143-139">Observed in organization</span></span>

<span data-ttu-id="23143-140">La pestaña **Observed in organization** te permite especificar un intervalo de fechas para ver una lista de dispositivos en los que se observó que este usuario inició sesión, la cuenta de usuario más frecuente y menos frecuente para cada uno de estos dispositivos y el total de usuarios observados en cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="23143-140">The **Observed in organization** tab allows you to specify a date range to see a list of devices where this user was observed logged on to, the most frequent and least frequent logged on user account for each of these devices, and total observed users on each device.</span></span>

<span data-ttu-id="23143-141">Al seleccionar un elemento en la tabla Observado en la organización, se expandirá el elemento, lo que revelará más detalles sobre el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="23143-141">Selecting an item on the Observed in organization table will expand the item, revealing more details about the device.</span></span> <span data-ttu-id="23143-142">Si selecciona directamente un vínculo dentro de un elemento, se le enviará a la página correspondiente.</span><span class="sxs-lookup"><span data-stu-id="23143-142">Directly selecting a link within an item will send you to the corresponding page.</span></span>

## <a name="search-for-specific-user-accounts"></a><span data-ttu-id="23143-143">Buscar cuentas de usuario específicas</span><span class="sxs-lookup"><span data-stu-id="23143-143">Search for specific user accounts</span></span>

1. <span data-ttu-id="23143-144">Seleccione **Usuario** en el **menú** desplegable Barra de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="23143-144">Select **User** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="23143-145">Escriba la cuenta de usuario en el **campo** Búsqueda.</span><span class="sxs-lookup"><span data-stu-id="23143-145">Enter the user account in the **Search** field.</span></span>
3. <span data-ttu-id="23143-146">Haga clic en el icono de búsqueda o presione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="23143-146">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="23143-147">Se muestra una lista de usuarios que coinciden con el texto de la consulta.</span><span class="sxs-lookup"><span data-stu-id="23143-147">A list of users matching the query text is displayed.</span></span> <span data-ttu-id="23143-148">Verás el dominio y el nombre de la cuenta de usuario, cuando se vio por última vez la cuenta de usuario y el número total de dispositivos en los que se observó que inició sesión en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="23143-148">You'll see the user account's domain and name, when the user account was last seen, and the total number of devices it was observed logged on to in the last 30 days.</span></span>

<span data-ttu-id="23143-149">Puede filtrar los resultados por los siguientes períodos de tiempo:</span><span class="sxs-lookup"><span data-stu-id="23143-149">You can filter the results by the following time periods:</span></span>

- <span data-ttu-id="23143-150">1 día</span><span class="sxs-lookup"><span data-stu-id="23143-150">1 day</span></span>
- <span data-ttu-id="23143-151">3 días</span><span class="sxs-lookup"><span data-stu-id="23143-151">3 days</span></span>
- <span data-ttu-id="23143-152">7 días</span><span class="sxs-lookup"><span data-stu-id="23143-152">7 days</span></span>
- <span data-ttu-id="23143-153">30 días</span><span class="sxs-lookup"><span data-stu-id="23143-153">30 days</span></span>
- <span data-ttu-id="23143-154">6 meses</span><span class="sxs-lookup"><span data-stu-id="23143-154">6 months</span></span>

## <a name="related-topics"></a><span data-ttu-id="23143-155">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="23143-155">Related topics</span></span>

- [<span data-ttu-id="23143-156">Ver y organizar la cola de Alertas de punto de conexión de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="23143-156">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="23143-157">Administrar alertas de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="23143-157">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="23143-158">Investigar alertas de punto de conexión de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="23143-158">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="23143-159">Investigar un archivo asociado a una alerta de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="23143-159">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="23143-160">Investigar dispositivos en la lista Defender para dispositivos de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="23143-160">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="23143-161">Investigar una dirección IP asociada a una alerta de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="23143-161">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="23143-162">Investigar un dominio asociado a una alerta de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="23143-162">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)