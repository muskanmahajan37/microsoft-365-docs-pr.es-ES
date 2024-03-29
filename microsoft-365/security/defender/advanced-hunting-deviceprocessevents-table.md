---
title: Tabla DeviceProcessEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de generación o creación de procesos en DeviceProcessEventstable del esquema de búsqueda avanzado
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, processcreationevents, DeviceProcessEvents, id. de proceso, línea de comandos, DeviceProcessEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b5e57fec83217c8df00d333bb4c71f375cac23bb
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024270"
---
# <a name="deviceprocessevents"></a>DeviceProcessEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión



La `DeviceProcessEvents` tabla del esquema de [búsqueda](advanced-hunting-overview.md) avanzada contiene información sobre la creación de procesos y los eventos relacionados. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!TIP]
> Para obtener información detallada acerca de los tipos de eventos ( valores) admitidos por una tabla, use la referencia de esquema integrada `ActionType` disponible en el centro de seguridad.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `DeviceId` | cadena | Identificador único para el equipo en servicio |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `ActionType` | cadena | Tipo de actividad que desencadenó el evento. Vea la [referencia de esquema en el portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obtener más información |
| `FileName` | cadena | Nombre del archivo donde se aplicó la acción registrada |
| `FolderPath` | cadena | Carpeta que contiene el archivo al que se aplicó la acción grabada |
| `SHA1` | cadena | SHA-1 del archivo donde fue aplicada la acción registrada |
| `SHA256` | cadena | SHA-256 del archivo donde se aplicó la acción registrada. Este campo no suele estar rellenado; use la columna SHA1 cuando se encuentre disponible. |
| `MD5` | cadena | Hash MD5 del archivo al que se aplicó la acción grabada |
| `FileSize` | largo | Tamaño del archivo en bytes |
| `ProcessVersionInfoCompanyName` | string | Nombre de la compañía a partir de la información de versión del proceso recién creado |
| `ProcessVersionInfoProductName` | string | Nombre del producto de la información de versión del proceso recién creado |
| `ProcessVersionInfoProductVersion` | string | Versión del producto a partir de la información de versión del proceso recién creado |
| `ProcessVersionInfoInternalFileName` | string | Nombre de archivo interno de la información de versión del proceso recién creado |
| `ProcessVersionInfoOriginalFileName` | string | Nombre de archivo original de la información de versión del proceso recién creado |
| `ProcessVersionInfoFileDescription` | string | Descripción de la información de versión del proceso recién creado |
| `ProcessId` | Entero | Identificador de proceso (PID) del proceso recién creado |
| `ProcessCommandLine` | string | Línea de comandos usada para crear el nuevo proceso |
| `ProcessIntegrityLevel` | string | Nivel de integridad del proceso recién creado. Windows asigna niveles de integridad a procesos basados en determinadas características, como si se iniciaron desde una descarga de Internet. Estos niveles de integridad influyen en los permisos de los recursos |
| `ProcessTokenElevation` | string | Indica el tipo de elevación de token aplicada al proceso recién creado. Valores posibles: TokenElevationTypeLimited (restringido), TokenElevationTypeDefault (estándar) y TokenElevationTypeFull (elevado) |
| `ProcessCreationTime` | datetime | Fecha y hora en que se creó el proceso |
| `AccountDomain` | string | Dominio de la cuenta |
| `AccountName` | string | Nombre de usuario de la cuenta |
| `AccountSid` | string | Identificador de seguridad (SID) de la cuenta |
| `AccountUpn` | string | Nombre principal de usuario (UPN) de la cuenta |
| `AccountObjectId` | string | Identificador único de la cuenta en Azure AD |
| `LogonId` | string | Identificador de una sesión de inicio de sesión. Este identificador es único en el mismo equipo solo entre reinicios |
| `InitiatingProcessAccountDomain` | string | Dominio de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountName` | string | Nombre de usuario de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountSid` | string | Identificador de seguridad (SID) de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountUpn` | string | Nombre principal de usuario (UPN) de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountObjectId` | string | Identificador de objeto de Azure AD de la cuenta de usuario que ejecutó el proceso responsable del evento |
| `InitiatingProcessLogonId` | string | Identificador de una sesión de inicio de sesión del proceso que inició el evento. Este identificador es único en el mismo equipo solo entre reinicios. |
| `InitiatingProcessIntegrityLevel` | string | Nivel de integridad del proceso que inició el evento. Windows asigna niveles de integridad a procesos basados en determinadas características, como si se iniciaron desde una descarga de Internet. Estos niveles de integridad influyen en los permisos de los recursos |
| `InitiatingProcessTokenElevation` | string | Tipo de token que indica la presencia o ausencia de elevación de privilegios del Control de acceso de usuario (UAC) aplicada al proceso que inició el evento |
| `InitiatingProcessSHA1` | string | SHA-1 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessSHA256` | string | SHA-256 del proceso (archivo de imagen) que inició el evento. Este campo no suele estar rellenado; use la columna SHA1 cuando se encuentre disponible. |
| `InitiatingProcessMD5` | cadena | Hash MD5 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessFileName` | string | Nombre del proceso que inició el evento |
| `InitiatingProcessFileSize` | largo | Tamaño del archivo que ejecutó el proceso responsable del evento |
| `InitiatingProcessVersionInfoCompanyName` | string | Nombre de la compañía a partir de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessVersionInfoProductName` | string | Nombre del producto de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessVersionInfoProductVersion` | string | Versión del producto de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessVersionInfoInternalFileName` | string | Nombre de archivo interno de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessVersionInfoOriginalFileName` | string | Nombre de archivo original de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessVersionInfoFileDescription` | string | Descripción de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessId` | Entero | Identificador de proceso (PID) del proceso que inició el evento |
| `InitiatingProcessCommandLine` | string | Línea de comandos usada para ejecutar el proceso que inició el evento |
| `InitiatingProcessCreationTime` | datetime | Fecha y hora en que se inició el proceso que inició el evento |
| `InitiatingProcessFolderPath` | string | Carpeta que contiene el proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessParentId` | Entero | Identificador de proceso (PID) del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentFileName` | string | Nombre del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentCreationTime` | datetime | Fecha y hora en que se inició el elemento primario del proceso responsable del evento |
| `InitiatingProcessSignerType` | string | Tipo de firmante de archivos del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessSignatureStatus` | string | Información sobre el estado de firma del proceso (archivo de imagen) que inició el evento |
| `ReportId` | largo | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp |
| `AppGuardContainerId` | string | Identificador del contenedor virtualizado usado por Application Guard para aislar la actividad del explorador |
| `AdditionalFields` | string | Información adicional sobre el evento en formato de matriz JSON |


## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
