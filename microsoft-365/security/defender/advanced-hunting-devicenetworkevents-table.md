---
title: Tabla DeviceNetworkEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de conexión de red que puede consultar en la tabla DeviceNetworkEvents del esquema de búsqueda avanzado
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, devicenetworkevents, NetworkCommunicationEvents, conexión de red, ip remota, ip local
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
ms.openlocfilehash: 3e09ace7130e5a58d3c386a57951dbf2ea5f5f2a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071555"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="0c6b5-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="0c6b5-104">DeviceNetworkEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0c6b5-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0c6b5-105">**Applies to:**</span></span>
- <span data-ttu-id="0c6b5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c6b5-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="0c6b5-107">La `DeviceNetworkEvents` tabla del esquema de [búsqueda](advanced-hunting-overview.md) avanzada contiene información sobre conexiones de red y eventos relacionados.</span><span class="sxs-lookup"><span data-stu-id="0c6b5-107">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="0c6b5-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="0c6b5-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="0c6b5-109">Para obtener información detallada acerca de los tipos de eventos ( valores) admitidos por una tabla, use la referencia de esquema integrada `ActionType` disponible en el centro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0c6b5-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="0c6b5-110">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="0c6b5-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0c6b5-111">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="0c6b5-111">Column name</span></span> | <span data-ttu-id="0c6b5-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="0c6b5-112">Data type</span></span> | <span data-ttu-id="0c6b5-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c6b5-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0c6b5-114">datetime</span><span class="sxs-lookup"><span data-stu-id="0c6b5-114">datetime</span></span> | <span data-ttu-id="0c6b5-115">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="0c6b5-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="0c6b5-116">cadena</span><span class="sxs-lookup"><span data-stu-id="0c6b5-116">string</span></span> | <span data-ttu-id="0c6b5-117">Identificador único para el equipo en servicio</span><span class="sxs-lookup"><span data-stu-id="0c6b5-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="0c6b5-118">cadena</span><span class="sxs-lookup"><span data-stu-id="0c6b5-118">string</span></span> | <span data-ttu-id="0c6b5-119">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="0c6b5-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="0c6b5-120">cadena</span><span class="sxs-lookup"><span data-stu-id="0c6b5-120">string</span></span> | <span data-ttu-id="0c6b5-121">Tipo de actividad que desencadenó el evento.</span><span class="sxs-lookup"><span data-stu-id="0c6b5-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="0c6b5-122">Vea la [referencia de esquema en el portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obtener más información</span><span class="sxs-lookup"><span data-stu-id="0c6b5-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `RemoteIP` | <span data-ttu-id="0c6b5-123">cadena</span><span class="sxs-lookup"><span data-stu-id="0c6b5-123">string</span></span> | <span data-ttu-id="0c6b5-124">Dirección IP a la que se ha conectado</span><span class="sxs-lookup"><span data-stu-id="0c6b5-124">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="0c6b5-125">Entero</span><span class="sxs-lookup"><span data-stu-id="0c6b5-125">int</span></span> | <span data-ttu-id="0c6b5-126">Puerto TCP en el dispositivo remoto al que se estaba conectando</span><span class="sxs-lookup"><span data-stu-id="0c6b5-126">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="0c6b5-127">cadena</span><span class="sxs-lookup"><span data-stu-id="0c6b5-127">string</span></span> | <span data-ttu-id="0c6b5-128">La dirección URL o el nombre de dominio completo (FQDN, según sus siglas en inglés) en el cual se ha estado conectado.</span><span class="sxs-lookup"><span data-stu-id="0c6b5-128">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="0c6b5-129">cadena</span><span class="sxs-lookup"><span data-stu-id="0c6b5-129">string</span></span> | <span data-ttu-id="0c6b5-130">Dirección IP asignada al equipo local usado durante la comunicación</span><span class="sxs-lookup"><span data-stu-id="0c6b5-130">IP address assigned to the local machine used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="0c6b5-131">Entero</span><span class="sxs-lookup"><span data-stu-id="0c6b5-131">int</span></span> | <span data-ttu-id="0c6b5-132">Puerto TCP en el equipo local usado durante la comunicación</span><span class="sxs-lookup"><span data-stu-id="0c6b5-132">TCP port on the local machine used during communication</span></span> |
| `Protocol` | <span data-ttu-id="0c6b5-133">string</span><span class="sxs-lookup"><span data-stu-id="0c6b5-133">string</span></span> | <span data-ttu-id="0c6b5-134">Protocolo usado durante la comunicación</span><span class="sxs-lookup"><span data-stu-id="0c6b5-134">Protocol used during the communication</span></span> |
| `LocalIPType` | <span data-ttu-id="0c6b5-135">string</span><span class="sxs-lookup"><span data-stu-id="0c6b5-135">string</span></span> | <span data-ttu-id="0c6b5-136">Tipo de dirección IP, por ejemplo Public, Private, Reserved, Loopback, Teredo, FourToSixMapping y Broadcast</span><span class="sxs-lookup"><span data-stu-id="0c6b5-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="0c6b5-137">string</span><span class="sxs-lookup"><span data-stu-id="0c6b5-137">string</span></span> | <span data-ttu-id="0c6b5-138">Tipo de dirección IP, por ejemplo Public, Private, Reserved, Loopback, Teredo, FourToSixMapping y Broadcast</span><span class="sxs-lookup"><span data-stu-id="0c6b5-138">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="0c6b5-139">string</span><span class="sxs-lookup"><span data-stu-id="0c6b5-139">string</span></span> | <span data-ttu-id="0c6b5-140">SHA-1 del proceso (archivo de imagen) que inició el evento</span><span class="sxs-lookup"><span data-stu-id="0c6b5-140">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="0c6b5-141">string</span><span class="sxs-lookup"><span data-stu-id="0c6b5-141">string</span></span> | <span data-ttu-id="0c6b5-142">SHA-256 del proceso (archivo de imagen) que inició el evento.</span><span class="sxs-lookup"><span data-stu-id="0c6b5-142">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="0c6b5-143">Este campo no suele estar rellenado; use la columna SHA1 cuando se encuentre disponible.</span><span class="sxs-lookup"><span data-stu-id="0c6b5-143">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="0c6b5-144">cadena</span><span class="sxs-lookup"><span data-stu-id="0c6b5-144">string</span></span> | <span data-ttu-id="0c6b5-145">Hash MD5 del proceso (archivo de imagen) que inició el evento</span><span class="sxs-lookup"><span data-stu-id="0c6b5-145">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="0c6b5-146">string</span><span class="sxs-lookup"><span data-stu-id="0c6b5-146">string</span></span> | <span data-ttu-id="0c6b5-147">Nombre del proceso que inició el evento</span><span class="sxs-lookup"><span data-stu-id="0c6b5-147">Name of the process that initiated the event</span></span> |
| `InitiatingProcessFileSize` | <span data-ttu-id="0c6b5-148">largo</span><span class="sxs-lookup"><span data-stu-id="0c6b5-148">long</span></span> | <span data-ttu-id="0c6b5-149">Tamaño del archivo que ejecutó el proceso responsable del evento</span><span class="sxs-lookup"><span data-stu-id="0c6b5-149">Size of the file that ran the process responsible for the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="0c6b5-150">Entero</span><span class="sxs-lookup"><span data-stu-id="0c6b5-150">int</span></span> | <span data-ttu-id="0c6b5-151">Identificador de proceso (PID) del proceso que inició el evento</span><span class="sxs-lookup"><span data-stu-id="0c6b5-151">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="0c6b5-152">string</span><span class="sxs-lookup"><span data-stu-id="0c6b5-152">string</span></span> | <span data-ttu-id="0c6b5-153">Línea de comandos usada para ejecutar el proceso que inició el evento</span><span class="sxs-lookup"><span data-stu-id="0c6b5-153">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="0c6b5-154">datetime</span><span class="sxs-lookup"><span data-stu-id="0c6b5-154">datetime</span></span> | <span data-ttu-id="0c6b5-155">Fecha y hora en que se inició el proceso que inició el evento</span><span class="sxs-lookup"><span data-stu-id="0c6b5-155">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="0c6b5-156">string</span><span class="sxs-lookup"><span data-stu-id="0c6b5-156">string</span></span> | <span data-ttu-id="0c6b5-157">Carpeta que contiene el proceso (archivo de imagen) que inició el evento</span><span class="sxs-lookup"><span data-stu-id="0c6b5-157">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="0c6b5-158">string</span><span class="sxs-lookup"><span data-stu-id="0c6b5-158">string</span></span> | <span data-ttu-id="0c6b5-159">Nombre del proceso primario que generó el proceso responsable del evento</span><span class="sxs-lookup"><span data-stu-id="0c6b5-159">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="0c6b5-160">Entero</span><span class="sxs-lookup"><span data-stu-id="0c6b5-160">int</span></span> | <span data-ttu-id="0c6b5-161">Identificador de proceso (PID) del proceso primario que generó el proceso responsable del evento</span><span class="sxs-lookup"><span data-stu-id="0c6b5-161">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="0c6b5-162">datetime</span><span class="sxs-lookup"><span data-stu-id="0c6b5-162">datetime</span></span> | <span data-ttu-id="0c6b5-163">Fecha y hora en que se inició el elemento primario del proceso responsable del evento</span><span class="sxs-lookup"><span data-stu-id="0c6b5-163">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="0c6b5-164">string</span><span class="sxs-lookup"><span data-stu-id="0c6b5-164">string</span></span> | <span data-ttu-id="0c6b5-165">Dominio de la cuenta que ejecutó el proceso responsable del evento</span><span class="sxs-lookup"><span data-stu-id="0c6b5-165">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="0c6b5-166">string</span><span class="sxs-lookup"><span data-stu-id="0c6b5-166">string</span></span> | <span data-ttu-id="0c6b5-167">Nombre de usuario de la cuenta que ejecutó el proceso responsable del evento</span><span class="sxs-lookup"><span data-stu-id="0c6b5-167">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="0c6b5-168">string</span><span class="sxs-lookup"><span data-stu-id="0c6b5-168">string</span></span> | <span data-ttu-id="0c6b5-169">Identificador de seguridad (SID) de la cuenta que ejecutó el proceso responsable del evento</span><span class="sxs-lookup"><span data-stu-id="0c6b5-169">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountUpn` | <span data-ttu-id="0c6b5-170">string</span><span class="sxs-lookup"><span data-stu-id="0c6b5-170">string</span></span> | <span data-ttu-id="0c6b5-171">Nombre principal de usuario (UPN) de la cuenta que ejecutó el proceso responsable del evento</span><span class="sxs-lookup"><span data-stu-id="0c6b5-171">User principal name (UPN) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="0c6b5-172">string</span><span class="sxs-lookup"><span data-stu-id="0c6b5-172">string</span></span> | <span data-ttu-id="0c6b5-173">Nivel de integridad del proceso que inició el evento.</span><span class="sxs-lookup"><span data-stu-id="0c6b5-173">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="0c6b5-174">Windows asigna niveles de integridad a procesos basados en determinadas características, como si se iniciaron desde una descarga de Internet.</span><span class="sxs-lookup"><span data-stu-id="0c6b5-174">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="0c6b5-175">Estos niveles de integridad influyen en los permisos de los recursos</span><span class="sxs-lookup"><span data-stu-id="0c6b5-175">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="0c6b5-176">string</span><span class="sxs-lookup"><span data-stu-id="0c6b5-176">string</span></span> | <span data-ttu-id="0c6b5-177">Tipo de token que indica la presencia o ausencia de elevación de privilegios del Control de acceso de usuario (UAC) aplicada al proceso que inició el evento</span><span class="sxs-lookup"><span data-stu-id="0c6b5-177">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="0c6b5-178">largo</span><span class="sxs-lookup"><span data-stu-id="0c6b5-178">long</span></span> | <span data-ttu-id="0c6b5-179">Identificador de eventos basado en un contador de repetición.</span><span class="sxs-lookup"><span data-stu-id="0c6b5-179">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="0c6b5-180">Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp</span><span class="sxs-lookup"><span data-stu-id="0c6b5-180">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="0c6b5-181">string</span><span class="sxs-lookup"><span data-stu-id="0c6b5-181">string</span></span> | <span data-ttu-id="0c6b5-182">Identificador del contenedor virtualizado usado por Application Guard para aislar la actividad del explorador</span><span class="sxs-lookup"><span data-stu-id="0c6b5-182">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |
| `AdditionalFields` | <span data-ttu-id="0c6b5-183">string</span><span class="sxs-lookup"><span data-stu-id="0c6b5-183">string</span></span> | <span data-ttu-id="0c6b5-184">Información adicional sobre el evento en formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="0c6b5-184">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0c6b5-185">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0c6b5-185">Related topics</span></span>
- [<span data-ttu-id="0c6b5-186">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="0c6b5-186">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0c6b5-187">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="0c6b5-187">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0c6b5-188">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="0c6b5-188">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0c6b5-189">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="0c6b5-189">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0c6b5-190">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="0c6b5-190">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0c6b5-191">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="0c6b5-191">Apply query best practices</span></span>](advanced-hunting-best-practices.md)