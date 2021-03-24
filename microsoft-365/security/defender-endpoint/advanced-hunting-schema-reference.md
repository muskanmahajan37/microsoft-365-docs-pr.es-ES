---
title: Referencia de esquema de búsqueda avanzada
description: Obtenga información sobre las tablas del esquema de búsqueda avanzada para comprender los datos en los que puede ejecutar consultas de búsqueda de amenazas.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, atp de microsoft defender, búsqueda de wdatp, consulta, telemetría, referencia de esquema, kusto, tabla, datos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: 7516744b72bc86bbf8f776adde690d75f057efd5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073152"
---
# <a name="understand-the-advanced-hunting-schema"></a><span data-ttu-id="26e62-104">Descripción del esquema de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="26e62-104">Understand the advanced hunting schema</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="26e62-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="26e62-105">**Applies to:**</span></span>
- [<span data-ttu-id="26e62-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="26e62-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="26e62-107">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="26e62-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="26e62-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="26e62-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="26e62-109">El [esquema de búsqueda](advanced-hunting-overview.md) avanzada está hecho de varias tablas que proporcionan información de eventos o información sobre dispositivos y otras entidades.</span><span class="sxs-lookup"><span data-stu-id="26e62-109">The [advanced hunting](advanced-hunting-overview.md) schema is made up of multiple tables that provide either event information or information about devices and other entities.</span></span> <span data-ttu-id="26e62-110">Para crear consultas eficaces que abarquen varias tablas, debe comprender las tablas y las columnas del esquema de búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="26e62-110">To effectively build queries that span multiple tables, you need to understand the tables and the columns in the advanced hunting schema.</span></span>

## <a name="get-schema-information-in-the-security-center"></a><span data-ttu-id="26e62-111">Obtener información de esquema en el centro de seguridad</span><span class="sxs-lookup"><span data-stu-id="26e62-111">Get schema information in the security center</span></span>
<span data-ttu-id="26e62-112">Al crear consultas, use la referencia de esquema integrado para obtener rápidamente la siguiente información sobre cada tabla del esquema:</span><span class="sxs-lookup"><span data-stu-id="26e62-112">While constructing queries, use the built-in schema reference to quickly get the following information about each table in the schema:</span></span>

- <span data-ttu-id="26e62-113">**Descripción de tablas:** tipo de datos contenidos en la tabla y el origen de los datos.</span><span class="sxs-lookup"><span data-stu-id="26e62-113">**Tables description**—type of data contained in the table and the source of that data.</span></span>
- <span data-ttu-id="26e62-114">**Columnas**: todas las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="26e62-114">**Columns**—all the columns in the table.</span></span>
- <span data-ttu-id="26e62-115">**Tipos de acción:** valores posibles en la `ActionType` columna que representan los tipos de evento admitidos por la tabla.</span><span class="sxs-lookup"><span data-stu-id="26e62-115">**Action types**—possible values in the `ActionType` column representing the event types supported by the table.</span></span> <span data-ttu-id="26e62-116">Esto solo se proporciona para tablas que contienen información de eventos.</span><span class="sxs-lookup"><span data-stu-id="26e62-116">This is provided only for tables that contain event information.</span></span>
- <span data-ttu-id="26e62-117">**Consulta de** ejemplo: consultas de ejemplo que ofrecen cómo se puede usar la tabla.</span><span class="sxs-lookup"><span data-stu-id="26e62-117">**Sample query**—example queries that feature how the table can be utilized.</span></span>

### <a name="access-the-schema-reference"></a><span data-ttu-id="26e62-118">Obtener acceso a la referencia de esquema</span><span class="sxs-lookup"><span data-stu-id="26e62-118">Access the schema reference</span></span>
<span data-ttu-id="26e62-119">Para obtener acceso rápidamente a la referencia de esquema, seleccione la acción **Ver** referencia junto al nombre de tabla en la representación del esquema.</span><span class="sxs-lookup"><span data-stu-id="26e62-119">To quickly access the schema reference, select the **View reference** action next to the table name in the schema representation.</span></span> <span data-ttu-id="26e62-120">También puede seleccionar Referencia **de esquema para** buscar una tabla.</span><span class="sxs-lookup"><span data-stu-id="26e62-120">You can also select **Schema reference** to search for a table.</span></span>

![Imagen que muestra cómo obtener acceso a la referencia de esquema en el portal](images/ah-reference.png)

## <a name="learn-the-schema-tables"></a><span data-ttu-id="26e62-122">Obtenga información sobre las tablas de esquema</span><span class="sxs-lookup"><span data-stu-id="26e62-122">Learn the schema tables</span></span>

<span data-ttu-id="26e62-123">En la siguiente referencia se enumeran todas las tablas del esquema de búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="26e62-123">The following reference lists all the tables in the advanced hunting schema.</span></span> <span data-ttu-id="26e62-124">Cada nombre de tabla está vinculado a una página donde se describen los nombres de las columnas de esa tabla.</span><span class="sxs-lookup"><span data-stu-id="26e62-124">Each table name links to a page describing the column names for that table.</span></span>

<span data-ttu-id="26e62-125">Los nombres de tabla y columna también se enumeran en el Centro de seguridad de Microsoft Defender, en la representación del esquema en la pantalla de búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="26e62-125">Table and column names are also listed within the Microsoft Defender Security Center, in the schema representation on the advanced hunting screen.</span></span>

| <span data-ttu-id="26e62-126">Nombre de tabla</span><span class="sxs-lookup"><span data-stu-id="26e62-126">Table name</span></span> | <span data-ttu-id="26e62-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="26e62-127">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="26e62-128">**[DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="26e62-128">**[DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)**</span></span> | <span data-ttu-id="26e62-129">Alertas en el Centro de seguridad de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="26e62-129">Alerts on Microsoft Defender Security Center</span></span> |
| <span data-ttu-id="26e62-130">**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="26e62-130">**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**</span></span> | <span data-ttu-id="26e62-131">Información del dispositivo, incluida la información del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="26e62-131">Device information, including OS information</span></span> |
| <span data-ttu-id="26e62-132">**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="26e62-132">**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**</span></span> | <span data-ttu-id="26e62-133">Propiedades de red de dispositivos, incluidos adaptadores, direcciones IP y MAC, así como redes y dominios conectados</span><span class="sxs-lookup"><span data-stu-id="26e62-133">Network properties of devices, including adapters, IP and MAC addresses, as well as connected networks and domains</span></span> |
| <span data-ttu-id="26e62-134">**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="26e62-134">**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**</span></span> | <span data-ttu-id="26e62-135">Creación de procesos y eventos relacionados</span><span class="sxs-lookup"><span data-stu-id="26e62-135">Process creation and related events</span></span> |
| <span data-ttu-id="26e62-136">**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="26e62-136">**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**</span></span> | <span data-ttu-id="26e62-137">Conexión de red y eventos relacionados</span><span class="sxs-lookup"><span data-stu-id="26e62-137">Network connection and related events</span></span> |
| <span data-ttu-id="26e62-138">**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="26e62-138">**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**</span></span> | <span data-ttu-id="26e62-139">Creación y modificación de archivos y otros eventos del sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="26e62-139">File creation, modification, and other file system events</span></span> |
| <span data-ttu-id="26e62-140">**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="26e62-140">**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**</span></span> | <span data-ttu-id="26e62-141">Creación y modificación de entradas de registro</span><span class="sxs-lookup"><span data-stu-id="26e62-141">Creation and modification of registry entries</span></span> |
| <span data-ttu-id="26e62-142">**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="26e62-142">**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**</span></span> | <span data-ttu-id="26e62-143">Inicios de sesión y otros eventos de autenticación</span><span class="sxs-lookup"><span data-stu-id="26e62-143">Sign-ins and other authentication events</span></span> |
| <span data-ttu-id="26e62-144">**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="26e62-144">**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**</span></span> | <span data-ttu-id="26e62-145">Eventos de carga de DLL</span><span class="sxs-lookup"><span data-stu-id="26e62-145">DLL loading events</span></span> |
| <span data-ttu-id="26e62-146">**[DeviceEvents](advanced-hunting-deviceevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="26e62-146">**[DeviceEvents](advanced-hunting-deviceevents-table.md)**</span></span> | <span data-ttu-id="26e62-147">Varios tipos de eventos, incluidos los eventos desencadenados por controles de seguridad como antivirus de Microsoft Defender y protección contra vulnerabilidades de seguridad</span><span class="sxs-lookup"><span data-stu-id="26e62-147">Multiple event types, including events triggered by security controls such as Microsoft Defender Antivirus and exploit protection</span></span> |
| <span data-ttu-id="26e62-148">**[DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="26e62-148">**[DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)**</span></span> | <span data-ttu-id="26e62-149">Información de certificado de archivos firmados obtenidos de eventos de comprobación de certificados en puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="26e62-149">Certificate information of signed files obtained from certificate verification events on endpoints</span></span> |
| <span data-ttu-id="26e62-150">**[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)**</span><span class="sxs-lookup"><span data-stu-id="26e62-150">**[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)**</span></span> | <span data-ttu-id="26e62-151">Inventario de software instalado en dispositivos, incluida la información de versión y el estado de fin de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="26e62-151">Inventory of software installed on devices, including their version information and end-of-support status</span></span> |
| <span data-ttu-id="26e62-152">**[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)**</span><span class="sxs-lookup"><span data-stu-id="26e62-152">**[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)**</span></span> | <span data-ttu-id="26e62-153">Vulnerabilidades de software encontradas en dispositivos y la lista de actualizaciones de seguridad disponibles que abordan cada vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="26e62-153">Software vulnerabilities found on devices and the list of available security updates that address each vulnerability</span></span> |
| <span data-ttu-id="26e62-154">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)**</span><span class="sxs-lookup"><span data-stu-id="26e62-154">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)**</span></span> | <span data-ttu-id="26e62-155">La base de conocimiento de vulnerabilidades de la que se ha informado públicamente, incluyendo si el código que aprovecha la vulnerabilidad está disponible para el público</span><span class="sxs-lookup"><span data-stu-id="26e62-155">Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available</span></span> |
| <span data-ttu-id="26e62-156">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)**</span><span class="sxs-lookup"><span data-stu-id="26e62-156">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)**</span></span> | <span data-ttu-id="26e62-157">Eventos de evaluación de administración de amenazas y vulnerabilidades, donde se indica el estado de las distintas configuraciones de seguridad de los dispositivos</span><span class="sxs-lookup"><span data-stu-id="26e62-157">Threat & Vulnerability Management assessment events, indicating the status of various security configurations on devices</span></span> |
| <span data-ttu-id="26e62-158">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)**</span><span class="sxs-lookup"><span data-stu-id="26e62-158">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)**</span></span> | <span data-ttu-id="26e62-159">Base de conocimiento de las configuraciones de seguridad utilizadas por la administración de amenazas y vulnerabilidades para evaluar dispositivos, incluidas las asignaciones a diferentes estándares y criterios de referencia</span><span class="sxs-lookup"><span data-stu-id="26e62-159">Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span> |


## <a name="related-topics"></a><span data-ttu-id="26e62-160">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="26e62-160">Related topics</span></span>
- [<span data-ttu-id="26e62-161">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="26e62-161">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="26e62-162">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="26e62-162">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="26e62-163">Trabajar con resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="26e62-163">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="26e62-164">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="26e62-164">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="26e62-165">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="26e62-165">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="26e62-166">Cambios avanzados del esquema de datos de búsqueda</span><span class="sxs-lookup"><span data-stu-id="26e62-166">Advanced hunting data schema changes</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/advanced-hunting-data-schema-changes/ba-p/1043914)