---
title: Propiedades y métodos de software
description: Recupera las alertas más recientes.
keywords: apis, api de gráficos, api admitidas, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9bfec2c4e65a390189556c14347eaf17236fb95e
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187306"
---
# <a name="software-resource-type"></a>Tipo de recurso software

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methods

Método |Tipo de valor devuelto |Descripción
:---|:---|:---
[Enumerar software](get-software.md) | Colección de software | Enumerar el inventario de software de la organización.
[Obtener software por identificador](get-software-by-id.md) | Software | Obtener un software específico por su identificador de software.
[Enumerar distribución de versiones de software](get-software-ver-distribution.md)| Colección de distribución | Enumerar la distribución de la versión de software por identificador de software.
[Enumerar máquinas por software](get-machines-by-software.md)| Colección MachineRef | Recupera una lista de dispositivos asociados con el identificador de software.
[Enumerar vulnerabilidades por software](get-vuln-by-software.md) | [Colección Vulnerability](vulnerability.md) | Recupera una lista de vulnerabilidades asociadas con el identificador de software.
[Obtener KBs que faltan](get-missing-kbs-software.md) | Colección KB | Obtener una lista de KBs que faltan asociados con el identificador de software

## <a name="properties"></a>Propiedades

Propiedad |   Tipo   |   Descripción
:---|:---|:---
id | Cadena | Id. de software
Nombre | Cadena | Nombre del software
Proveedor | Cadena | Nombre del proveedor de software
Debilidades | Long | Número de vulnerabilidades detectadas
publicExploit | Booleano | Existe vulnerabilidad pública para algunas de las vulnerabilidades
activeAlert | Booleano | La alerta activa está asociada con este software
exposedMachines | Long | Número de dispositivos expuestos
impactScore | Doble | Impacto de la puntuación de exposición de este software
