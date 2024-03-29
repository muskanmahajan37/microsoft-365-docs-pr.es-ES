---
title: Obtener una actividad de corrección por id.
description: Devuelve información sobre la actividad de corrección especificada.
keywords: apis, remediation, remediation api, get, remediation tasks, remediation by ID,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e0f68e8a28b302f0ae1ca06a2f892fea38a219b2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244448"
---
# <a name="get-one-remediation-activity-by-id"></a>Obtener una actividad de corrección por id.

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Devuelve información sobre la actividad de corrección especificada. Presenta las mismas columnas que [Obtener toda](get-remediation-all-activities.md)la actividad de corrección ", pero devuelve resultados solo para la actividad _de corrección especificada_.

[Obtenga más información sobre las actividades de corrección](tvm-remediation.md).

## <a name="list-a-specified-remediation-activity-for-id"></a>Enumerar una actividad de corrección especificada para (id)

**DIRECCIÓN URL:** GET: /api/remediationTasks/ \{ id\}

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API para obtener más información.](apis-intro.md)

Tipo de permiso | Permiso | Nombre para mostrar de permisos
:---|:---|:---
Aplicación | RemediationTask.Read.All | \'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'
Delegado (cuenta profesional o educativa) | RemediationTask.Read.Read | \'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'

## <a name="properties"></a>Propiedades

Propiedad (id) | Tipo de datos | Descripción | Ejemplo de un valor devuelto
:---|:---|:---|:---
categoría | Cadena | Categoría de la actividad de corrección (configuración software/seguridad) | Software
completerEmail | Cadena | Si alguien completó manualmente la actividad de corrección, esta columna contiene su correo electrónico | nulo
completerId | Cadena | Si alguien completó la actividad de corrección manualmente, esta columna contiene su identificador de objeto | nulo
completionMethod | Cadena | Una actividad de corrección se puede completar "automáticamente" (si todos los dispositivos están parcheados) o "manualmente" por una persona que selecciona "marcar como completada" | Automático
createdOn | DateTime | Hora en que se creó esta actividad de corrección | 2021-01-12T18:54:11.5499478Z
description | Cadena | Descripción de esta actividad de corrección | Actualiza Microsoft Silverlight a una versión posterior para mitigar las vulnerabilidades conocidas que afectan a los dispositivos.
dueOn | DateTime | Fecha de vencimiento que el creador estableció para esta actividad de corrección | 2021-01-13T00:00:00Z
fixedDevices |  | Número de dispositivos que se han corregido | 2
id | Cadena | Identificador de esta actividad de corrección | 097d9735-5479-4899-b1b7-77398899df92
nameId | Cadena | Nombre del producto relacionado | Microsoft Silverlight
priority | Cadena | Prioridad del conjunto de creadores para esta actividad de corrección (High\Medium\Low) | Alto
productId | Cadena | Id. de producto relacionado | microsoft-_-silverlight
productivityImpactRemediationType | Cadena | Solo se podrían solicitar algunos cambios de configuración para dispositivos sin impacto del usuario. Este valor indica la selección entre "todos los dispositivos expuestos" o "solo dispositivos sin impacto del usuario". | AllExposedAssets
rbacGroupNames | Cadena | Nombres de grupo de dispositivos relacionados | [ "Windows servidores", "Windows 10" ]
recommendedProgram | Cadena | Programa recomendado para actualizar a | nulo
recommendedVendor | Cadena | Proveedor recomendado para actualizar a | nulo
recommendedVersion | Cadena | Versión recomendada para actualizar o actualizar a | nulo
relatedComponent | Cadena | Componente relacionado de esta actividad de corrección (similar al componente relacionado para una recomendación de seguridad) | Microsoft Microsoft Silverlight
requesterEmail | Cadena | Dirección de correo electrónico del creador | globaladmin@UserName.contoso.com
requesterId | Cadena | Id. de objeto Creator | r647211f-2e16-43f2-a480-16ar3a2a796r
requesterNotes | Cadena | Las notas (texto libre) que el creador agregó para esta actividad de corrección | nulo
scid | Cadena | SCID de la recomendación de seguridad relacionada | nulo
status | Cadena | Estado de la actividad de corrección (Activo/Completado) | Activo
statusLastModifiedOn | DateTime | Fecha en la que se actualizó el campo de estado | 2021-01-12T18:54:11.5499487Z
targetDevices | Long | Número de dispositivos expuestos a los que se aplica esta corrección | 43
title | Cadena | Título de esta actividad de corrección | Microsoft Silverlight
type | Cadena | Tipo de corrección | Update
vendorId | Cadena | Nombre de proveedor relacionado | Microsoft

## <a name="example"></a>Ejemplo

### <a name="request-example"></a>Ejemplo de solicitud

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

### <a name="response-example"></a>Ejemplo de respuesta

```json
{ 
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks/$entity", 
    "id": "03942ef5-aecb-4c6e-b555-d6a97013844c", 
    "title": "Update Microsoft Silverlight", 
    "createdOn": "2021-02-10T13:20:36.4718166Z", 
    "requesterId": "65548a1d-efo0-4a7a-8d19-1b967b5c36f4", 
    "requesterEmail": "user1@contoso.com", 
    "status": "Active", 
    "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z", 
    "description": "Update Silverlight to a later version to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ", 
    "relatedComponent": "Microsoft Silverlight", 
    "targetDevices": 18511, 
    "rbacGroupNames": [ 
        "UnassignedGroup", 
        "hhh" 
    ], 
    "fixedDevices": 2866, 
    "requesterNotes": "test", 
    "dueOn": "2021-02-11T00:00:00Z", 
    "category": "Software", 
    "productivityImpactRemediationType": null, 
    "priority": "Medium", 
    "completionMethod": null, 
    "completerId": null, 
    "completerEmail": null, 
    "scid": null, 
    "type": "Update", 
    "productId": "microsoft-_-silverlight", 
    "vendorId": "microsoft", 
    "nameId": "silverlight", 
    "recommendedVersion": null, 
    "recommendedVendor": null, 
    "recommendedProgram": null 
} 
```

## <a name="see-also"></a>Vea también

- [Propiedades y métodos de corrección](get-remediation-methods-properties.md)

- [Enumerar todas las actividades de corrección](get-remediation-all-activities.md)

- [Lista de dispositivos expuestos de una actividad de corrección](get-remediation-exposed-devices-activities.md)

- [Amenazas basadas en riesgos & administración de vulnerabilidades](next-gen-threat-and-vuln-mgt.md)

- [Vulnerabilidades de la organización](tvm-weaknesses.md)
