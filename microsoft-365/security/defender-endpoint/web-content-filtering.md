---
title: Filtrado de contenido web
description: Use el filtrado de contenido web en ATP de Microsoft Defender para realizar un seguimiento y regular el acceso a sitios web en función de sus categorías de contenido.
keywords: protección web, protección contra amenazas web, exploración web, supervisión, informes, tarjetas, lista de dominios, seguridad, phishing, malware, exploit, sitios web, protección de red, Edge, Internet Explorer, Chrome, Firefox, explorador web
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: dd1b21b306d40ab03fa518f48c8a0bc985191f69
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071760"
---
# <a name="web-content-filtering"></a><span data-ttu-id="00b07-104">Filtrado de contenido web</span><span class="sxs-lookup"><span data-stu-id="00b07-104">Web content filtering</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="00b07-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="00b07-105">**Applies to:**</span></span>
- [<span data-ttu-id="00b07-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="00b07-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="00b07-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="00b07-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="00b07-108">**El filtrado de contenido web está actualmente en versión preliminar pública**</span><span class="sxs-lookup"><span data-stu-id="00b07-108">**Web content filtering is currently in public preview**</span></span><br>
> <span data-ttu-id="00b07-109">Esta versión preliminar se proporciona sin un contrato de nivel de servicio y no se recomienda para cargas de trabajo de producción.</span><span class="sxs-lookup"><span data-stu-id="00b07-109">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="00b07-110">Es posible que algunas características no sean compatibles o que tengan capacidades limitadas.</span><span class="sxs-lookup"><span data-stu-id="00b07-110">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="00b07-111">Para obtener más información, vea Características de vista previa [de Microsoft Defender para endpoint](preview.md).</span><span class="sxs-lookup"><span data-stu-id="00b07-111">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

><span data-ttu-id="00b07-112">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="00b07-112">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="00b07-113">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="00b07-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="00b07-114">El filtrado de contenido web forma parte de [las funciones de protección web](web-protection-overview.md) en Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="00b07-114">Web content filtering is part of [Web protection](web-protection-overview.md) capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="00b07-115">Permite a la organización realizar un seguimiento y regular el acceso a sitios web en función de sus categorías de contenido.</span><span class="sxs-lookup"><span data-stu-id="00b07-115">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="00b07-116">Muchos de estos sitios web, aunque no son malintencionados, pueden ser problemáticos debido a las normativas de cumplimiento, el uso del ancho de banda u otras preocupaciones.</span><span class="sxs-lookup"><span data-stu-id="00b07-116">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

<span data-ttu-id="00b07-117">Configure directivas en los grupos de dispositivos para bloquear determinadas categorías.</span><span class="sxs-lookup"><span data-stu-id="00b07-117">Configure policies across your device groups to block certain categories.</span></span> <span data-ttu-id="00b07-118">El bloqueo de una categoría impide que los usuarios de grupos de dispositivos especificados tengan acceso a direcciones URL asociadas a la categoría.</span><span class="sxs-lookup"><span data-stu-id="00b07-118">Blocking a category prevents users within specified device groups from accessing URLs associated with the category.</span></span> <span data-ttu-id="00b07-119">Para cualquier categoría que no está bloqueada, las direcciones URL se auditan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="00b07-119">For any category that's not blocked, the URLs are automatically audited.</span></span> <span data-ttu-id="00b07-120">Los usuarios pueden acceder a las direcciones URL sin interrupciones y recopilará estadísticas de acceso para ayudar a crear una decisión de directiva más personalizada.</span><span class="sxs-lookup"><span data-stu-id="00b07-120">Your users can access the URLs without disruption, and you'll gather access statistics to help create a more custom policy decision.</span></span> <span data-ttu-id="00b07-121">Los usuarios verán una notificación de bloqueo si un elemento de la página que están viendo está realizando llamadas a un recurso bloqueado.</span><span class="sxs-lookup"><span data-stu-id="00b07-121">Your users will see a block notification if an element on the page they're viewing is making calls to a blocked resource.</span></span>

<span data-ttu-id="00b07-122">El filtrado de contenido web está disponible en los principales exploradores web, con bloques realizados por Windows Defender SmartScreen (Microsoft Edge) y Network Protection (Chrome, Firefox, Brave y Opera).</span><span class="sxs-lookup"><span data-stu-id="00b07-122">Web content filtering is available on the major web browsers, with blocks performed by Windows Defender SmartScreen (Microsoft Edge) and Network Protection (Chrome, Firefox, Brave and Opera).</span></span> <span data-ttu-id="00b07-123">Para obtener más información acerca de la compatibilidad con exploradores, consulte la sección requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="00b07-123">For more information about browser support, see the prerequisites section.</span></span>

<span data-ttu-id="00b07-124">Resumen de las ventajas:</span><span class="sxs-lookup"><span data-stu-id="00b07-124">Summarizing the benefits:</span></span>

- <span data-ttu-id="00b07-125">Se impide que los usuarios accedan a sitios web en categorías bloqueadas, ya sea que estén explorando localmente o lejos</span><span class="sxs-lookup"><span data-stu-id="00b07-125">Users are prevented from accessing websites in blocked categories, whether they're browsing on-premises or away</span></span>
- <span data-ttu-id="00b07-126">Implementar directivas para grupos de usuarios que usan grupos de dispositivos definidos en [Microsoft Defender para la](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac) configuración de control de acceso basado en roles de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="00b07-126">Conveniently deploy policies to groups of users using device groups defined in [Microsoft Defender for Endpoint role-based access control settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)</span></span>
- <span data-ttu-id="00b07-127">Acceder a informes web en la misma ubicación central, con visibilidad sobre los bloques reales y el uso web</span><span class="sxs-lookup"><span data-stu-id="00b07-127">Access web reports in the same central location, with visibility over actual blocks and web usage</span></span>

## <a name="user-experience"></a><span data-ttu-id="00b07-128">Experiencia del usuario</span><span class="sxs-lookup"><span data-stu-id="00b07-128">User experience</span></span>

<span data-ttu-id="00b07-129">La protección de red proporciona la experiencia de bloqueo de los exploradores compatibles con terceros, que proporciona una notificación del sistema que notifica al usuario de una conexión bloqueada.</span><span class="sxs-lookup"><span data-stu-id="00b07-129">The blocking experience for 3rd party supported browsers is provided by Network Protection, which provides a system-level toast notifying the user of a blocked connection.</span></span> 

<span data-ttu-id="00b07-130">Para una experiencia más fácil de usar en el explorador, considere el uso de Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="00b07-130">For a more user-friendly in-browser experience, consider using Microsoft Edge.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="00b07-131">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="00b07-131">Prerequisites</span></span>

<span data-ttu-id="00b07-132">Antes de probar esta característica, asegúrese de que tiene los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="00b07-132">Before trying out this feature, make sure you have the following requirements:</span></span>

- <span data-ttu-id="00b07-133">Licencia de Windows 10 Enterprise E5 O Complemento de seguridad de Microsoft 365 E3 + Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="00b07-133">Windows 10 Enterprise E5 license OR Microsoft 365 E3 + Microsoft 365 E5 Security add-on.</span></span>
- <span data-ttu-id="00b07-134">Acceso al portal del Centro de seguridad de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="00b07-134">Access to Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="00b07-135">Dispositivos que ejecutan Windows 10 Anniversary Update (versión 1607) o posterior con la última actualización de MoCAMP.</span><span class="sxs-lookup"><span data-stu-id="00b07-135">Devices running Windows 10 Anniversary Update (version 1607) or later with the latest MoCAMP update.</span></span>

<span data-ttu-id="00b07-136">Si Windows Defender SmartScreen no está activado, Protección de red asumirá el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="00b07-136">If Windows Defender SmartScreen isn't turned on, Network Protection will take over the blocking.</span></span> <span data-ttu-id="00b07-137">Requiere habilitar [la protección de red](enable-network-protection.md) en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="00b07-137">It requires [enabling Network Protection](enable-network-protection.md) on the device.</span></span> <span data-ttu-id="00b07-138">Chrome, Firefox, Brave y Opera son actualmente exploradores de terceros en los que esta característica está habilitada.</span><span class="sxs-lookup"><span data-stu-id="00b07-138">Chrome, Firefox, Brave, and Opera are currently 3rd party browsers in which this feature is enabled.</span></span>

## <a name="data-handling"></a><span data-ttu-id="00b07-139">Tratamiento de datos</span><span class="sxs-lookup"><span data-stu-id="00b07-139">Data handling</span></span>

<span data-ttu-id="00b07-140">Seguiremos la región que haya elegido usar como parte de la configuración de administración de datos de [Microsoft Defender para endpoint.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="00b07-140">We will follow whichever region you have elected to use as part of your [Microsoft Defender for Endpoint data handling settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/data-storage-privacy).</span></span> <span data-ttu-id="00b07-141">Los datos no abandonarán el centro de datos en esa región.</span><span class="sxs-lookup"><span data-stu-id="00b07-141">Your data will not leave the data center in that region.</span></span> <span data-ttu-id="00b07-142">Además, sus datos no se compartirán con terceros, incluidos nuestros proveedores de datos.</span><span class="sxs-lookup"><span data-stu-id="00b07-142">In addition, your data will not be shared with any third-parties, including our data providers.</span></span>

## <a name="turn-on-web-content-filtering"></a><span data-ttu-id="00b07-143">Activar el filtrado de contenido web</span><span class="sxs-lookup"><span data-stu-id="00b07-143">Turn on web content filtering</span></span>

<span data-ttu-id="00b07-144">En el menú de navegación izquierdo, seleccione **Configuración > General > Características avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="00b07-144">From the left-hand navigation menu, select **Settings > General > Advanced Features**.</span></span> <span data-ttu-id="00b07-145">Desplácese hacia abajo hasta que vea la entrada para el filtrado **de contenido web**.</span><span class="sxs-lookup"><span data-stu-id="00b07-145">Scroll down until you see the entry for **Web content filtering**.</span></span> <span data-ttu-id="00b07-146">Cambie la alternancia a **Las preferencias Activar** **y Guardar**.</span><span class="sxs-lookup"><span data-stu-id="00b07-146">Switch the toggle to **On** and **Save preferences**.</span></span>

### <a name="configure-web-content-filtering-policies"></a><span data-ttu-id="00b07-147">Configurar directivas de filtrado de contenido web</span><span class="sxs-lookup"><span data-stu-id="00b07-147">Configure web content filtering policies</span></span>

<span data-ttu-id="00b07-148">Las directivas de filtrado de contenido web especifican qué categorías de sitio están bloqueadas en qué grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="00b07-148">Web content filtering policies specify which site categories are blocked on which device groups.</span></span> <span data-ttu-id="00b07-149">Para administrar las directivas, vaya **a Configuración > reglas > filtrado de contenido web**.</span><span class="sxs-lookup"><span data-stu-id="00b07-149">To manage the policies, go to **Settings > Rules > Web content filtering**.</span></span>

<span data-ttu-id="00b07-150">Usa el filtro para buscar directivas que contengan determinadas categorías bloqueadas o que se apliquen a grupos de dispositivos específicos.</span><span class="sxs-lookup"><span data-stu-id="00b07-150">Use the filter to locate policies that contain certain blocked categories or are applied to specific device groups.</span></span>

### <a name="create-a-policy"></a><span data-ttu-id="00b07-151">Crear una directiva</span><span class="sxs-lookup"><span data-stu-id="00b07-151">Create a policy</span></span>

<span data-ttu-id="00b07-152">Para agregar una nueva directiva:</span><span class="sxs-lookup"><span data-stu-id="00b07-152">To add a new policy:</span></span>

1. <span data-ttu-id="00b07-153">Seleccione **Agregar directiva en** la página Filtrado de **contenido** web en **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="00b07-153">Select **Add policy** on the **Web content filtering** page in **Settings**.</span></span>
2. <span data-ttu-id="00b07-154">Especifique un nombre.</span><span class="sxs-lookup"><span data-stu-id="00b07-154">Specify a name.</span></span>
3. <span data-ttu-id="00b07-155">Seleccione las categorías que desea bloquear.</span><span class="sxs-lookup"><span data-stu-id="00b07-155">Select the categories to block.</span></span> <span data-ttu-id="00b07-156">Use el icono expandir para expandir completamente cada categoría principal y seleccionar categorías de contenido web específicas.</span><span class="sxs-lookup"><span data-stu-id="00b07-156">Use the expand icon to fully expand each parent category and select specific web content categories.</span></span>
4. <span data-ttu-id="00b07-157">Especifique el ámbito de directiva.</span><span class="sxs-lookup"><span data-stu-id="00b07-157">Specify the policy scope.</span></span> <span data-ttu-id="00b07-158">Selecciona los grupos de dispositivos para especificar dónde aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="00b07-158">Select the device groups to specify where to apply the policy.</span></span> <span data-ttu-id="00b07-159">Solo se impedirá el acceso a los sitios web de los grupos de dispositivos seleccionados en las categorías seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="00b07-159">Only devices in the selected device groups will be prevented from accessing websites in the selected categories.</span></span>
5. <span data-ttu-id="00b07-160">Revise el resumen y guarde la directiva.</span><span class="sxs-lookup"><span data-stu-id="00b07-160">Review the summary and save the policy.</span></span> <span data-ttu-id="00b07-161">La actualización de la directiva puede tardar hasta 2 horas en aplicarse a los dispositivos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="00b07-161">The policy refresh may take up to 2 hours to apply to your selected devices.</span></span>

<span data-ttu-id="00b07-162">Sugerencia: Puedes implementar una directiva sin seleccionar ninguna categoría en un grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="00b07-162">Tip: You can deploy a policy without selecting any category on a device group.</span></span> <span data-ttu-id="00b07-163">Esta acción creará una directiva de solo auditoría para ayudarle a comprender el comportamiento de los usuarios antes de crear una directiva de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="00b07-163">This action will create an audit only policy, to help you understand user behavior before creating a block policy.</span></span>

>[!NOTE]
><span data-ttu-id="00b07-164">Si quita una directiva o cambia los grupos de dispositivos al mismo tiempo, esto puede provocar un retraso en la implementación de directivas.</span><span class="sxs-lookup"><span data-stu-id="00b07-164">If you are removing a policy or changing device groups at the same time, this might cause a delay in policy deployment.</span></span>

>[!IMPORTANT]
><span data-ttu-id="00b07-165">El bloqueo de la categoría "Uncategorized" puede provocar resultados inesperados y no deseados.</span><span class="sxs-lookup"><span data-stu-id="00b07-165">Blocking the "Uncategorized" category may lead to unexpected and undesired results.</span></span>  

### <a name="allow-specific-websites"></a><span data-ttu-id="00b07-166">Permitir sitios web específicos</span><span class="sxs-lookup"><span data-stu-id="00b07-166">Allow specific websites</span></span>

<span data-ttu-id="00b07-167">Es posible invalidar la categoría bloqueada en el filtrado de contenido web para permitir un solo sitio mediante la creación de una directiva de indicador personalizada.</span><span class="sxs-lookup"><span data-stu-id="00b07-167">It's possible to override the blocked category in web content filtering to allow a single site by creating a custom indicator policy.</span></span> <span data-ttu-id="00b07-168">La directiva de indicador personalizado reemplazará la directiva de filtrado de contenido web cuando se aplique al grupo de dispositivos en cuestión.</span><span class="sxs-lookup"><span data-stu-id="00b07-168">The custom indicator policy will supersede the web content filtering policy when it's applied to the device group in question.</span></span>

1. <span data-ttu-id="00b07-169">Para crear un indicador personalizado en el Centro de seguridad de Microsoft Defender, vaya a **Dirección** URL de  >  **indicadores** de  >  **configuración/Elemento de**  >  **adición de dominio**</span><span class="sxs-lookup"><span data-stu-id="00b07-169">Create a custom indicator in the Microsoft Defender Security Center by going to **Settings** > **Indicators** > **URL/Domain** > **Add Item**</span></span>
2. <span data-ttu-id="00b07-170">Escriba el dominio del sitio</span><span class="sxs-lookup"><span data-stu-id="00b07-170">Enter the domain of the site</span></span>
3. <span data-ttu-id="00b07-171">Establezca la acción de directiva en **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="00b07-171">Set the policy action to **Allow**.</span></span>  

### <a name="reporting-inaccuracies"></a><span data-ttu-id="00b07-172">Imprecisiones de informes</span><span class="sxs-lookup"><span data-stu-id="00b07-172">Reporting inaccuracies</span></span>

<span data-ttu-id="00b07-173">Si encuentra un dominio que se ha categorizado incorrectamente, puede notificar imprecisiones directamente desde la página De informes de filtrado de contenido web.</span><span class="sxs-lookup"><span data-stu-id="00b07-173">If you encounter a domain that has been incorrectly categorized, you can report inaccuracies directly to us from the Web Content Filtering reports page.</span></span> <span data-ttu-id="00b07-174">Esta característica solo está disponible en el nuevo centro de seguridad de Microsoft 365 (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="00b07-174">This feature is available only in the new Microsoft 365 security center (security.microsoft.com).</span></span>

<span data-ttu-id="00b07-175">Para notificar una imprecisión, vaya a **Informes > protección web**> detalles de filtrado de contenido web > dominios .</span><span class="sxs-lookup"><span data-stu-id="00b07-175">To report an inaccuracy, navigate to **Reports > Web protection > Web Content Filtering Details > Domains**.</span></span> <span data-ttu-id="00b07-176">En la pestaña dominios de nuestros informes de filtrado de contenido web, verá puntos suspensivos junto a cada uno de los dominios.</span><span class="sxs-lookup"><span data-stu-id="00b07-176">On the domains tab of our Web Content Filtering reports, you will see an ellipsis beside each of the domains.</span></span> <span data-ttu-id="00b07-177">Mantenga el puntero sobre estos puntos suspensivos y seleccione **Error de informe**.</span><span class="sxs-lookup"><span data-stu-id="00b07-177">Hover over this ellipsis and select **Report Inaccuracy**.</span></span>

<span data-ttu-id="00b07-178">Se abrirá un panel donde puede seleccionar la prioridad y agregar detalles adicionales, como la categoría sugerida para volver a categorizar.</span><span class="sxs-lookup"><span data-stu-id="00b07-178">A panel will open where you can select the priority and add additional details such as the suggested category for re-categorization.</span></span> <span data-ttu-id="00b07-179">Una vez completado el formulario, seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="00b07-179">Once you complete the form, select **Submit**.</span></span> <span data-ttu-id="00b07-180">Nuestro equipo revisará la solicitud en un plazo de un día laborable.</span><span class="sxs-lookup"><span data-stu-id="00b07-180">Our team will review the request within one business day.</span></span> <span data-ttu-id="00b07-181">Para desbloquear inmediatamente, cree un [indicador de permitir personalizado](indicator-ip-domain.md).</span><span class="sxs-lookup"><span data-stu-id="00b07-181">For immediate unblocking, create a [custom allow indicator](indicator-ip-domain.md).</span></span>

## <a name="web-content-filtering-cards-and-details"></a><span data-ttu-id="00b07-182">Detalles y tarjetas de filtrado de contenido web</span><span class="sxs-lookup"><span data-stu-id="00b07-182">Web content filtering cards and details</span></span>

<span data-ttu-id="00b07-183">Seleccione **Informes > protección web para** ver tarjetas con información sobre el filtrado de contenido web y la protección contra amenazas web.</span><span class="sxs-lookup"><span data-stu-id="00b07-183">Select **Reports > Web protection** to view cards with information about web content filtering and web threat protection.</span></span> <span data-ttu-id="00b07-184">Las siguientes tarjetas proporcionan información resumida sobre el filtrado de contenido web.</span><span class="sxs-lookup"><span data-stu-id="00b07-184">The following cards provide summary information about web content filtering.</span></span>

### <a name="web-activity-by-category"></a><span data-ttu-id="00b07-185">Actividad web por categoría</span><span class="sxs-lookup"><span data-stu-id="00b07-185">Web activity by category</span></span>

<span data-ttu-id="00b07-186">Esta tarjeta enumera las categorías de contenido web principales con el mayor aumento o disminución en el número de intentos de acceso.</span><span class="sxs-lookup"><span data-stu-id="00b07-186">This card lists the parent web content categories with the largest increase or decrease in the number of access attempts.</span></span> <span data-ttu-id="00b07-187">Comprenda los cambios drásticos en los patrones de actividad web de la organización de los últimos 30 días, 3 meses o 6 meses.</span><span class="sxs-lookup"><span data-stu-id="00b07-187">Understand drastic changes in web activity patterns in your organization from last 30 days, 3 months, or 6 months.</span></span> <span data-ttu-id="00b07-188">Seleccione un nombre de categoría para ver más información.</span><span class="sxs-lookup"><span data-stu-id="00b07-188">Select a category name to view more information.</span></span>

<span data-ttu-id="00b07-189">En los primeros 30 días de uso de esta característica, es posible que la organización no tenga suficientes datos para mostrar esta información.</span><span class="sxs-lookup"><span data-stu-id="00b07-189">In the first 30 days of using this feature, your organization might not have enough data to display this information.</span></span>

![Imagen de la actividad web por tarjeta de categoría](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a><span data-ttu-id="00b07-191">Tarjeta de resumen de filtrado de contenido web</span><span class="sxs-lookup"><span data-stu-id="00b07-191">Web content filtering  summary card</span></span>

<span data-ttu-id="00b07-192">Esta tarjeta muestra la distribución de los intentos de acceso bloqueado en las diferentes categorías de contenido web primario.</span><span class="sxs-lookup"><span data-stu-id="00b07-192">This card displays the distribution of blocked access attempts across the different parent web content categories.</span></span> <span data-ttu-id="00b07-193">Seleccione una de las barras de color para ver más información sobre una categoría web primaria específica.</span><span class="sxs-lookup"><span data-stu-id="00b07-193">Select one of the colored bars to view more information about a specific parent web category.</span></span>

![Imagen de la tarjeta de resumen de filtrado de contenido web](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a><span data-ttu-id="00b07-195">Tarjeta de resumen de actividad web</span><span class="sxs-lookup"><span data-stu-id="00b07-195">Web activity summary card</span></span>

<span data-ttu-id="00b07-196">Esta tarjeta muestra el número total de solicitudes de contenido web en todas las direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="00b07-196">This card displays the total number of requests for web content in all URLs.</span></span>

![Imagen de la tarjeta de resumen de actividad web](images/web-activity-summary.png)

### <a name="view-card-details"></a><span data-ttu-id="00b07-198">Ver detalles de la tarjeta</span><span class="sxs-lookup"><span data-stu-id="00b07-198">View card details</span></span>

<span data-ttu-id="00b07-199">Para obtener acceso a los **detalles del informe** para cada tarjeta, seleccione una fila de tabla o una barra coloreada en el gráfico de la tarjeta.</span><span class="sxs-lookup"><span data-stu-id="00b07-199">You can access the **Report details** for each card by selecting a table row or colored bar from the chart in the card.</span></span> <span data-ttu-id="00b07-200">La página de detalles del informe para cada tarjeta contiene amplios datos estadísticos sobre categorías de contenido web, dominios de sitio web y grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="00b07-200">The report details page for each card contains extensive statistical data about web content categories, website domains, and device groups.</span></span>

![Imagen de los detalles del informe de protección web](images/web-protection-report-details.png)

- <span data-ttu-id="00b07-202">**Categorías web:** enumera las categorías de contenido web que han tenido intentos de acceso en su organización.</span><span class="sxs-lookup"><span data-stu-id="00b07-202">**Web categories**: Lists the web content categories that have had access attempts in your organization.</span></span> <span data-ttu-id="00b07-203">Seleccione una categoría específica para abrir un menú desplegable de resumen.</span><span class="sxs-lookup"><span data-stu-id="00b07-203">Select a specific category to open a summary flyout.</span></span>

- <span data-ttu-id="00b07-204">**Dominios:** enumera los dominios web a los que se ha accedido o bloqueado en la organización.</span><span class="sxs-lookup"><span data-stu-id="00b07-204">**Domains**: Lists the web domains that have been accessed or blocked in your organization.</span></span> <span data-ttu-id="00b07-205">Seleccione un dominio específico para ver información detallada sobre ese dominio.</span><span class="sxs-lookup"><span data-stu-id="00b07-205">Select a specific domain to view detailed information about that domain.</span></span>

- <span data-ttu-id="00b07-206">**Grupos de dispositivos:** enumera todos los grupos de dispositivos que han generado actividad web en la organización</span><span class="sxs-lookup"><span data-stu-id="00b07-206">**Device groups**: Lists all the device groups that have generated web activity in your organization</span></span>

<span data-ttu-id="00b07-207">Use el filtro de intervalo de tiempo en la parte superior izquierda de la página para seleccionar un período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="00b07-207">Use the time range filter at the top left of the page to select a time period.</span></span> <span data-ttu-id="00b07-208">También puede filtrar la información o personalizar las columnas.</span><span class="sxs-lookup"><span data-stu-id="00b07-208">You can also filter the information or customize the columns.</span></span> <span data-ttu-id="00b07-209">Seleccione una fila para abrir un panel desplegable con más información sobre el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="00b07-209">Select a row to open a flyout pane with even more information about the selected item.</span></span>

## <a name="errors-and-issues"></a><span data-ttu-id="00b07-210">Errores y problemas</span><span class="sxs-lookup"><span data-stu-id="00b07-210">Errors and issues</span></span>

### <a name="limitations-and-known-issues-in-this-preview"></a><span data-ttu-id="00b07-211">Limitaciones y problemas conocidos en esta versión preliminar</span><span class="sxs-lookup"><span data-stu-id="00b07-211">Limitations and known issues in this preview</span></span>

- <span data-ttu-id="00b07-212">Solo se admite Microsoft Edge si la configuración del sistema operativo del dispositivo es Server (cmd > Systeminfo > configuración del sistema operativo).</span><span class="sxs-lookup"><span data-stu-id="00b07-212">Only Microsoft Edge is supported if your device's OS configuration is Server (cmd > Systeminfo > OS Configuration).</span></span> <span data-ttu-id="00b07-213">La protección de red solo se admite en el modo Inspeccionar en dispositivos de servidor, que es responsable de proteger el tráfico en los exploradores de terceros compatibles.</span><span class="sxs-lookup"><span data-stu-id="00b07-213">Network Protection is only supported in Inspect mode on Server devices, which is responsible for securing traffic across supported 3rd party browsers.</span></span>

- <span data-ttu-id="00b07-214">Los dispositivos sinsignar tendrán datos incorrectos que se mostrarán en el informe.</span><span class="sxs-lookup"><span data-stu-id="00b07-214">Unassigned devices will have incorrect data shown within the report.</span></span> <span data-ttu-id="00b07-215">En el pivot Detalles del > grupos de dispositivos, es posible que veas una fila con un campo Grupo de dispositivos en blanco.</span><span class="sxs-lookup"><span data-stu-id="00b07-215">In the Report details > Device groups pivot, you may see a row with a blank Device Group field.</span></span> <span data-ttu-id="00b07-216">Este grupo contiene los dispositivos sinsignación antes de que se coloquen en el grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="00b07-216">This group contains your unassigned devices before they get put into your specified group.</span></span> <span data-ttu-id="00b07-217">Es posible que el informe de esta fila no contenga un recuento preciso de dispositivos o recuentos de acceso.</span><span class="sxs-lookup"><span data-stu-id="00b07-217">The report for this row may not contain an accurate count of devices or access counts.</span></span>

## <a name="related-topics"></a><span data-ttu-id="00b07-218">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="00b07-218">Related topics</span></span>

- [<span data-ttu-id="00b07-219">Introducción a la protección web</span><span class="sxs-lookup"><span data-stu-id="00b07-219">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="00b07-220">Protección contra amenazas web</span><span class="sxs-lookup"><span data-stu-id="00b07-220">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="00b07-221">Supervisar la seguridad web</span><span class="sxs-lookup"><span data-stu-id="00b07-221">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="00b07-222">Responder a amenazas web</span><span class="sxs-lookup"><span data-stu-id="00b07-222">Respond to web threats</span></span>](web-protection-response.md)