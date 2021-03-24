---
title: Crear y administrar reglas de detección personalizadas en Microsoft 365 Defender
description: Obtenga información sobre cómo crear y administrar reglas de detecciones personalizadas basadas en consultas avanzadas de búsqueda
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, detecciones personalizadas, reglas, esquema, kusto, microsoft 365, Protección contra amenazas de Microsoft, RBAC, permisos, ATP de Microsoft Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9699b5e2bc2e33b94795b7c23bd3f34f0383a8cc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068981"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="c4892-104">Crear y administrar reglas de detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="c4892-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c4892-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c4892-105">**Applies to:**</span></span>
- <span data-ttu-id="c4892-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4892-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c4892-107">Las reglas de detección personalizadas son reglas que puedes diseñar y ajustar [con](advanced-hunting-overview.md) consultas avanzadas de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c4892-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="c4892-108">Estas reglas le permiten supervisar proactivamente varios eventos y estados del sistema, incluidos la actividad de infracción sospechosa y los extremos mal configurados.</span><span class="sxs-lookup"><span data-stu-id="c4892-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="c4892-109">Puede configurarlos para que se ejecuten a intervalos regulares, generando alertas y llevando a cabo acciones de respuesta siempre que haya coincidencias.</span><span class="sxs-lookup"><span data-stu-id="c4892-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="c4892-110">Permisos necesarios para administrar detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="c4892-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="c4892-111">Para administrar detecciones personalizadas, debe tener asignado uno de estos roles:</span><span class="sxs-lookup"><span data-stu-id="c4892-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="c4892-112">**Administrador de** seguridad: los usuarios con este rol [de Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) pueden administrar la configuración de seguridad en el Centro de seguridad de Microsoft 365 y otros portales y servicios.</span><span class="sxs-lookup"><span data-stu-id="c4892-112">**Security administrator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="c4892-113">**Operador de** seguridad: los usuarios con este rol de [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) pueden administrar alertas y tener acceso global de solo lectura a características relacionadas con la seguridad, incluida toda la información del Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4892-113">**Security operator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="c4892-114">Este rol es suficiente para administrar detecciones personalizadas solo si el control de acceso basado en roles (RBAC) está desactivado en Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="c4892-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="c4892-115">Si tiene RBAC configurado, también necesita el permiso administrar la configuración **de seguridad** para Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="c4892-115">If you have RBAC configured, you also need the **manage security settings** permission for Defender for Endpoint.</span></span>

<span data-ttu-id="c4892-116">Para administrar los permisos necesarios, un **administrador global** puede:</span><span class="sxs-lookup"><span data-stu-id="c4892-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="c4892-117">Asigne el **rol de administrador de seguridad** o operador de seguridad en el Centro de administración de Microsoft [365](https://admin.microsoft.com/) en **Roles** Security   >  **admin**.</span><span class="sxs-lookup"><span data-stu-id="c4892-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="c4892-118">Compruebe la configuración de RBAC para Microsoft Defender para Endpoint en El Centro de seguridad [de Microsoft Defender](https://securitycenter.windows.com/) en **Configuración**  >  **Permisos**  >  **Roles**.</span><span class="sxs-lookup"><span data-stu-id="c4892-118">Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="c4892-119">Seleccione el rol correspondiente para asignar el **permiso administrar la configuración de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="c4892-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="c4892-120">Para administrar detecciones personalizadas,  los operadores de seguridad necesitarán el permiso administrar la configuración de seguridad en Microsoft Defender para endpoint si RBAC está activado. </span><span class="sxs-lookup"><span data-stu-id="c4892-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender for Endpoint if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="c4892-121">Crear una regla de detección personalizada</span><span class="sxs-lookup"><span data-stu-id="c4892-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="c4892-122">1. Prepare la consulta.</span><span class="sxs-lookup"><span data-stu-id="c4892-122">1. Prepare the query.</span></span>

<span data-ttu-id="c4892-123">En el Centro de seguridad de Microsoft 365, vaya a **Búsqueda avanzada** y seleccione una consulta existente o cree una nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="c4892-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="c4892-124">Al usar una nueva consulta, ejecute la consulta para identificar errores y comprender los posibles resultados.</span><span class="sxs-lookup"><span data-stu-id="c4892-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="c4892-125">Para evitar que el servicio devuelva demasiadas alertas, cada regla se limita a generar solo 100 alertas cada vez que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="c4892-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="c4892-126">Antes de crear una regla, ajusta la consulta para evitar alertas de actividad normal del día a día.</span><span class="sxs-lookup"><span data-stu-id="c4892-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="c4892-127">Columnas necesarias en los resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="c4892-127">Required columns in the query results</span></span>
<span data-ttu-id="c4892-128">Para crear una regla de detección personalizada, la consulta debe devolver las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="c4892-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="c4892-129">`Timestamp`— se usa para establecer la marca de tiempo de las alertas generadas</span><span class="sxs-lookup"><span data-stu-id="c4892-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="c4892-130">`ReportId`: habilita las búsquedas de los registros originales</span><span class="sxs-lookup"><span data-stu-id="c4892-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="c4892-131">Una de las siguientes columnas que identifican dispositivos, usuarios o buzones específicos:</span><span class="sxs-lookup"><span data-stu-id="c4892-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="c4892-132">`SenderFromAddress` (remitente de sobre o Return-Path dirección)</span><span class="sxs-lookup"><span data-stu-id="c4892-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="c4892-133">`SenderMailFromAddress` (dirección de remitente mostrada por el cliente de correo electrónico)</span><span class="sxs-lookup"><span data-stu-id="c4892-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="c4892-134">Se agregará compatibilidad con entidades adicionales a medida que se agregan nuevas tablas al [esquema de búsqueda avanzada.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="c4892-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="c4892-135">Las consultas simples, como las que no usan el operador or para personalizar o agregar resultados, normalmente `project` `summarize` devuelven estas columnas comunes.</span><span class="sxs-lookup"><span data-stu-id="c4892-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="c4892-136">Hay varias maneras de garantizar que las consultas más complejas devuelvan estas columnas.</span><span class="sxs-lookup"><span data-stu-id="c4892-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="c4892-137">Por ejemplo, si prefiere agregar y contar por entidad debajo de una columna como , todavía puede devolver y obtenerlo del evento más reciente que implica cada `DeviceId` `Timestamp` único `ReportId` `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="c4892-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="c4892-138">La consulta de ejemplo siguiente cuenta el número de dispositivos únicos ( ) con detecciones antivirus y usa este recuento para buscar solo los dispositivos con más `DeviceId` de cinco detecciones.</span><span class="sxs-lookup"><span data-stu-id="c4892-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="c4892-139">Para devolver el último `Timestamp` y el correspondiente , usa el operador con la `ReportId` `summarize` `arg_max` función.</span><span class="sxs-lookup"><span data-stu-id="c4892-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="c4892-140">Para obtener un mejor rendimiento de consulta, establezca un filtro de tiempo que coincida con la frecuencia de ejecución prevista para la regla.</span><span class="sxs-lookup"><span data-stu-id="c4892-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="c4892-141">Dado que la ejecución menos frecuente es _cada 24 horas,_ el filtrado del último día cubrirá todos los datos nuevos.</span><span class="sxs-lookup"><span data-stu-id="c4892-141">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="c4892-142">2. Cree una nueva regla y proporcione detalles de alerta.</span><span class="sxs-lookup"><span data-stu-id="c4892-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="c4892-143">Con la consulta en el editor de consultas, seleccione **Crear regla de detección** y especifique los siguientes detalles de alerta:</span><span class="sxs-lookup"><span data-stu-id="c4892-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="c4892-144">**Nombre de detección**: nombre de la regla de detección</span><span class="sxs-lookup"><span data-stu-id="c4892-144">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="c4892-145">**Frecuencia:** intervalo para ejecutar la consulta y realizar acciones.</span><span class="sxs-lookup"><span data-stu-id="c4892-145">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="c4892-146">Vea instrucciones adicionales a continuación</span><span class="sxs-lookup"><span data-stu-id="c4892-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="c4892-147">**Título de alerta:** título que se muestra con alertas desencadenadas por la regla</span><span class="sxs-lookup"><span data-stu-id="c4892-147">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="c4892-148">**Gravedad:** riesgo potencial del componente o actividad identificado por la regla</span><span class="sxs-lookup"><span data-stu-id="c4892-148">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="c4892-149">**Categoría**: componente de amenaza o actividad identificada por la regla</span><span class="sxs-lookup"><span data-stu-id="c4892-149">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="c4892-150">**MITRE ATT&técnicas de CK**: una o más técnicas de ataque identificadas por la regla como documentadas en el marco de&[CK de MITRE ATT](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="c4892-150">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="c4892-151">Esta sección está oculta para determinadas categorías de alertas, como malware, ransomware, actividad sospechosa y software no deseado</span><span class="sxs-lookup"><span data-stu-id="c4892-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="c4892-152">**Descripción:** más información sobre el componente o la actividad identificada por la regla</span><span class="sxs-lookup"><span data-stu-id="c4892-152">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="c4892-153">**Acciones recomendadas:** acciones adicionales que los respondedores pueden realizar en respuesta a una alerta</span><span class="sxs-lookup"><span data-stu-id="c4892-153">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="c4892-154">Frecuencia de regla</span><span class="sxs-lookup"><span data-stu-id="c4892-154">Rule frequency</span></span>
<span data-ttu-id="c4892-155">Al guardar o editar una nueva regla, se ejecuta y comprueba las coincidencias de los últimos 30 días de datos.</span><span class="sxs-lookup"><span data-stu-id="c4892-155">When you save or edit a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="c4892-156">A continuación, la regla se ejecuta de nuevo a intervalos fijos, aplicando una duración de devolución basada en la frecuencia que elija:</span><span class="sxs-lookup"><span data-stu-id="c4892-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="c4892-157">**Cada 24 horas:** se ejecuta cada 24 horas, comprobando los datos de los últimos 30 días</span><span class="sxs-lookup"><span data-stu-id="c4892-157">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="c4892-158">**Cada 12 horas:** se ejecuta cada 12 horas, comprobando los datos de las últimas 24 horas</span><span class="sxs-lookup"><span data-stu-id="c4892-158">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="c4892-159">**Cada 3 horas:** se ejecuta cada 3 horas, comprobando los datos de las últimas 6 horas</span><span class="sxs-lookup"><span data-stu-id="c4892-159">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="c4892-160">**Cada hora:** se ejecuta cada hora, comprobando los datos de las últimas 2 horas</span><span class="sxs-lookup"><span data-stu-id="c4892-160">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

>[!TIP]
> <span data-ttu-id="c4892-161">Coincide con los filtros de tiempo de la consulta con la duración de la devolución.</span><span class="sxs-lookup"><span data-stu-id="c4892-161">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="c4892-162">Se omiten los resultados fuera de la duración de la devolución.</span><span class="sxs-lookup"><span data-stu-id="c4892-162">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="c4892-163">Seleccione la frecuencia que coincida con la que desea supervisar las detecciones.</span><span class="sxs-lookup"><span data-stu-id="c4892-163">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="c4892-164">Tenga en cuenta la capacidad de su organización para responder a las alertas.</span><span class="sxs-lookup"><span data-stu-id="c4892-164">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="c4892-165">3. Elija las entidades afectadas.</span><span class="sxs-lookup"><span data-stu-id="c4892-165">3. Choose the impacted entities.</span></span>
<span data-ttu-id="c4892-166">Identifique las columnas de los resultados de la consulta en las que espera encontrar la entidad principal afectada o afectada.</span><span class="sxs-lookup"><span data-stu-id="c4892-166">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="c4892-167">Por ejemplo, una consulta puede devolver direcciones de remitente ( `SenderFromAddress` o ) y destinatario ( `SenderMailFromAddress` `RecipientEmailAddress` ).</span><span class="sxs-lookup"><span data-stu-id="c4892-167">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="c4892-168">La identificación de cuál de estas columnas representa la entidad afectada principal ayuda al servicio a agregar alertas relevantes, correlacionar incidentes y acciones de respuesta de destino.</span><span class="sxs-lookup"><span data-stu-id="c4892-168">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="c4892-169">Solo puede seleccionar una columna para cada tipo de entidad (buzón, usuario o dispositivo).</span><span class="sxs-lookup"><span data-stu-id="c4892-169">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="c4892-170">Las columnas que la consulta no devuelve no se pueden seleccionar.</span><span class="sxs-lookup"><span data-stu-id="c4892-170">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="c4892-171">4. Especifique acciones.</span><span class="sxs-lookup"><span data-stu-id="c4892-171">4. Specify actions.</span></span>
<span data-ttu-id="c4892-172">La regla de detección personalizada puede realizar automáticamente acciones en dispositivos, archivos o usuarios devueltos por la consulta.</span><span class="sxs-lookup"><span data-stu-id="c4892-172">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="c4892-173">Acciones en dispositivos</span><span class="sxs-lookup"><span data-stu-id="c4892-173">Actions on devices</span></span>
<span data-ttu-id="c4892-174">Estas acciones se aplican a los dispositivos de la `DeviceId` columna de los resultados de la consulta:</span><span class="sxs-lookup"><span data-stu-id="c4892-174">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="c4892-175">**Aislar dispositivo:** usa Microsoft Defender para Endpoint para aplicar aislamiento total de red, lo que impide que el dispositivo se conecte a cualquier aplicación o servicio.</span><span class="sxs-lookup"><span data-stu-id="c4892-175">**Isolate device**—uses Microsoft Defender for Endpoint to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="c4892-176">Más información sobre el aislamiento de la máquina de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="c4892-176">Learn more about Microsoft Defender for Endpoint machine isolation</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="c4892-177">**Recopilar paquete de investigación:** recopila información del dispositivo en un archivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="c4892-177">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="c4892-178">Obtenga más información sobre el paquete de investigación de Microsoft Defender para endpoints</span><span class="sxs-lookup"><span data-stu-id="c4892-178">Learn more about the Microsoft Defender for Endpoint investigation package</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="c4892-179">**Ejecutar examen antivirus:** realiza un examen completo Windows Defender antivirus en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="c4892-179">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="c4892-180">**Iniciar investigación:** inicia una [investigación automatizada](m365d-autoir.md) en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="c4892-180">**Initiate investigation**—initiates an [automated investigation](m365d-autoir.md) on the device</span></span>
- <span data-ttu-id="c4892-181">**Restringir la ejecución de** aplicaciones: establece restricciones en el dispositivo para permitir que solo se ejecuten los archivos que están firmados con un certificado emitido por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c4892-181">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="c4892-182">Más información sobre las restricciones de la aplicación con Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="c4892-182">Learn more about app restrictions with Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="c4892-183">Acciones en archivos</span><span class="sxs-lookup"><span data-stu-id="c4892-183">Actions on files</span></span>
<span data-ttu-id="c4892-184">Cuando se selecciona, puede optar por aplicar la acción Archivo **de** cuarentena en los archivos de `SHA1` la columna , , o de los `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="c4892-184">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="c4892-185">Esta acción elimina el archivo de su ubicación actual y coloca una copia en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="c4892-185">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="c4892-186">Acciones en usuarios</span><span class="sxs-lookup"><span data-stu-id="c4892-186">Actions on users</span></span>
<span data-ttu-id="c4892-187">Cuando se selecciona, la acción Marcar **al usuario como** comprometida se toma en los usuarios de la columna , o de los `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="c4892-187">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="c4892-188">Esta acción establece el nivel de riesgo de los usuarios en "alto" en Azure Active Directory, desencadenando las directivas de [protección de identidades correspondientes.](/azure/active-directory/identity-protection/overview-identity-protection)</span><span class="sxs-lookup"><span data-stu-id="c4892-188">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="c4892-189">La acción permitir o bloquear para reglas de detección personalizadas actualmente no se admite en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="c4892-189">The allow or block action for custom detection rules is currently not supported on Microsoft 365 Defender.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="c4892-190">5. Establezca el ámbito de regla.</span><span class="sxs-lookup"><span data-stu-id="c4892-190">5. Set the rule scope.</span></span>
<span data-ttu-id="c4892-191">Establezca el ámbito para especificar los dispositivos cubiertos por la regla.</span><span class="sxs-lookup"><span data-stu-id="c4892-191">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="c4892-192">El ámbito influye en las reglas que comprueban los dispositivos y no afectan a las reglas que solo comprueban buzones y cuentas de usuario o identidades.</span><span class="sxs-lookup"><span data-stu-id="c4892-192">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="c4892-193">Al establecer el ámbito, puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="c4892-193">When setting the scope, you can select:</span></span>

- <span data-ttu-id="c4892-194">Todos los dispositivos</span><span class="sxs-lookup"><span data-stu-id="c4892-194">All devices</span></span>
- <span data-ttu-id="c4892-195">Grupos de dispositivos específicos</span><span class="sxs-lookup"><span data-stu-id="c4892-195">Specific device groups</span></span>

<span data-ttu-id="c4892-196">Solo se consultarán los datos de dispositivos en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="c4892-196">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="c4892-197">Además, las acciones solo se realizarán en esos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c4892-197">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="c4892-198">6. Revise y active la regla.</span><span class="sxs-lookup"><span data-stu-id="c4892-198">6. Review and turn on the rule.</span></span>
<span data-ttu-id="c4892-199">Después de revisar la regla, seleccione **Crear** para guardarla.</span><span class="sxs-lookup"><span data-stu-id="c4892-199">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="c4892-200">La regla de detección personalizada se ejecuta inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="c4892-200">The custom detection rule immediately runs.</span></span> <span data-ttu-id="c4892-201">Se ejecuta de nuevo en función de la frecuencia configurada para buscar coincidencias, generar alertas y realizar acciones de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c4892-201">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>


>[!Important] 
><span data-ttu-id="c4892-202">Las detecciones personalizadas deben revisarse periódicamente para obtener eficacia y eficacia.</span><span class="sxs-lookup"><span data-stu-id="c4892-202">Custom detections should be regularly reviewed for efficiency and effectiveness.</span></span> <span data-ttu-id="c4892-203">Para asegurarse de que está creando detecciones que desencadenan alertas verdaderas, dedícalse a revisar las detecciones personalizadas existentes siguiendo los pasos descritos en Administrar reglas de detección [personalizadas existentes.](#manage-existing-custom-detection-rules)</span><span class="sxs-lookup"><span data-stu-id="c4892-203">To make sure you are creating detections that trigger true alerts, take time to review your existing custom detections by following the steps in [Manage existing custom detection rules](#manage-existing-custom-detection-rules).</span></span> <br>  
<span data-ttu-id="c4892-204">Se mantiene el control sobre la generalidad o especificidad de las detecciones personalizadas, por lo que cualquier alerta falsa generada por detecciones personalizadas puede indicar la necesidad de modificar determinados parámetros de las reglas.</span><span class="sxs-lookup"><span data-stu-id="c4892-204">You maintain control over the broadness or specificity of your custom detections so any false alerts generated by custom detections might indicate a need to modify certain parameters of the rules.</span></span>


## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="c4892-205">Administrar reglas de detección personalizadas existentes</span><span class="sxs-lookup"><span data-stu-id="c4892-205">Manage existing custom detection rules</span></span>
<span data-ttu-id="c4892-206">Puede ver la lista de reglas de detección personalizadas existentes, comprobar sus ejecuciones anteriores y revisar las alertas que han desencadenado.</span><span class="sxs-lookup"><span data-stu-id="c4892-206">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="c4892-207">También puede ejecutar una regla a petición y modificarla.</span><span class="sxs-lookup"><span data-stu-id="c4892-207">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="c4892-208">Ver reglas existentes</span><span class="sxs-lookup"><span data-stu-id="c4892-208">View existing rules</span></span>

<span data-ttu-id="c4892-209">Para ver todas las reglas de detección personalizadas existentes, vaya a **Buscar**  >  **detecciones personalizadas**.</span><span class="sxs-lookup"><span data-stu-id="c4892-209">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="c4892-210">La página enumera todas las reglas con la siguiente información de ejecución:</span><span class="sxs-lookup"><span data-stu-id="c4892-210">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="c4892-211">**Última ejecución:** cuando se ejecuta por última vez una regla para comprobar si hay coincidencias de consulta y generar alertas</span><span class="sxs-lookup"><span data-stu-id="c4892-211">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="c4892-212">**Estado de la última ejecución:** si una regla se ejecutó correctamente</span><span class="sxs-lookup"><span data-stu-id="c4892-212">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="c4892-213">**Siguiente ejecución**: la siguiente ejecución programada</span><span class="sxs-lookup"><span data-stu-id="c4892-213">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="c4892-214">**Estado:** si se ha activado o desactivado una regla</span><span class="sxs-lookup"><span data-stu-id="c4892-214">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="c4892-215">Ver detalles de regla, modificar regla y ejecutar regla</span><span class="sxs-lookup"><span data-stu-id="c4892-215">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="c4892-216">Para ver información completa acerca de una regla de detección personalizada, vaya a **Buscar** detecciones personalizadas y, a continuación,  >   seleccione el nombre de la regla.</span><span class="sxs-lookup"><span data-stu-id="c4892-216">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="c4892-217">A continuación, puede ver información general sobre la regla, incluida la información sobre su estado de ejecución y su ámbito.</span><span class="sxs-lookup"><span data-stu-id="c4892-217">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="c4892-218">La página también proporciona la lista de alertas y acciones desencadenadas.</span><span class="sxs-lookup"><span data-stu-id="c4892-218">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="c4892-219">![Página de detalles de regla de detección personalizada](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="c4892-219">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="c4892-220">*Detalles de la regla de detección personalizada*</span><span class="sxs-lookup"><span data-stu-id="c4892-220">*Custom detection rule details*</span></span>

<span data-ttu-id="c4892-221">También puede realizar las siguientes acciones en la regla desde esta página:</span><span class="sxs-lookup"><span data-stu-id="c4892-221">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="c4892-222">**Ejecutar**: ejecute la regla inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="c4892-222">**Run**—run the rule immediately.</span></span> <span data-ttu-id="c4892-223">Esto también restablece el intervalo de la siguiente ejecución.</span><span class="sxs-lookup"><span data-stu-id="c4892-223">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="c4892-224">**Editar**: modificar la regla sin cambiar la consulta</span><span class="sxs-lookup"><span data-stu-id="c4892-224">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="c4892-225">**Modificar consulta**: editar la consulta en búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="c4892-225">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="c4892-226">**Activar**  /  **Desactivar :** habilitar la regla o impedir que se ejecute</span><span class="sxs-lookup"><span data-stu-id="c4892-226">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="c4892-227">**Eliminar**: desactivar la regla y quitarla</span><span class="sxs-lookup"><span data-stu-id="c4892-227">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="c4892-228">Ver y administrar alertas desencadenadas</span><span class="sxs-lookup"><span data-stu-id="c4892-228">View and manage triggered alerts</span></span>

<span data-ttu-id="c4892-229">En la pantalla de detalles de la regla (**Buscar** detecciones personalizadas [Nombre de regla] ), vaya a Alertas desencadenadas , que enumera las alertas generadas por  >  **coincidencias**  >  con la regla. </span><span class="sxs-lookup"><span data-stu-id="c4892-229">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="c4892-230">Seleccione una alerta para ver información detallada al respecto y realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="c4892-230">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="c4892-231">Administrar la alerta estableciendo su estado y clasificación (alerta verdadera o falsa)</span><span class="sxs-lookup"><span data-stu-id="c4892-231">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="c4892-232">Vincular la alerta a un incidente</span><span class="sxs-lookup"><span data-stu-id="c4892-232">Link the alert to an incident</span></span>
- <span data-ttu-id="c4892-233">Ejecutar la consulta que desencadenó la alerta en la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="c4892-233">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="c4892-234">Revisar acciones</span><span class="sxs-lookup"><span data-stu-id="c4892-234">Review actions</span></span>
<span data-ttu-id="c4892-235">En la pantalla de detalles de la regla (**Buscar** detecciones personalizadas [Nombre de regla] ), vaya a Acciones desencadenadas , que enumera las acciones realizadas en función de las  >  **coincidencias**  >  con la regla. </span><span class="sxs-lookup"><span data-stu-id="c4892-235">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="c4892-236">Para ver rápidamente la información y realizar acciones en un elemento de una tabla, use la columna de selección [&#10003;] a la izquierda de la tabla.</span><span class="sxs-lookup"><span data-stu-id="c4892-236">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4892-237">Ver también</span><span class="sxs-lookup"><span data-stu-id="c4892-237">See also</span></span>
- [<span data-ttu-id="c4892-238">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="c4892-238">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="c4892-239">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="c4892-239">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c4892-240">Conozca el lenguaje de consulta de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="c4892-240">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c4892-241">Migrar consultas de búsqueda avanzada desde Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="c4892-241">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)