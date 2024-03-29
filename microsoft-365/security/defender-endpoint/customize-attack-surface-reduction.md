---
title: Personalizar las reglas de la reducción de superficie expuesta a ataques
description: Establecer reglas individualmente en los modos de auditoría, bloquear o deshabilitados, y agregar archivos y carpetas que deben excluirse de las reglas de reducción de superficie de ataque
keywords: Reducción de superficie de ataque, hips, sistema de prevención de intrusiones de host, reglas de protección, antiexploit, exploit, prevención de infecciones, personalizar, configurar, excluir
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 52a51b1035f1aa0fb152cf17dc9561cce378d59d
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570356"
---
# <a name="customize-attack-surface-reduction-rules"></a>Personalizar las reglas de la reducción de superficie expuesta a ataques

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

[Las reglas de reducción de superficie de](enable-attack-surface-reduction.md) ataque ayudan a evitar comportamientos de software que a menudo se abusan para poner en peligro el dispositivo o la red. Por ejemplo, un atacante puede intentar ejecutar un script sin signo desde una unidad USB o hacer que una macro de un documento de Office realice llamadas directamente a la API de Win32. Las reglas de reducción de superficie de ataque pueden restringir estos tipos de comportamientos de riesgo y mejorar la posición defensiva de la organización.

Aprende a personalizar las reglas [](#exclude-files-and-folders) de reducción [](#customize-the-notification) de superficie de ataques excluyendo archivos y carpetas o agregando texto personalizado a la alerta de notificación que aparece en el equipo de un usuario.

Puedes establecer reglas de reducción de superficie de ataque para dispositivos que ejecuten cualquiera de las siguientes ediciones y versiones de Windows:
- Windows 10 Pro, [versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) o posterior
- Windows 10 Enterprise, [versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) o posterior
- Windows Server, [versión 1803 (canal semianual)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) o posterior
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19) Puede usar la directiva de grupo, PowerShell y los proveedores de servicios de configuración (CSP) de Administración de dispositivos móviles (MDM) para configurar estas opciones.

## <a name="exclude-files-and-folders"></a>Excluir archivos y carpetas

Puedes excluir archivos y carpetas para que no se evalúen mediante reglas de reducción de superficie de ataque. Una vez excluido, el archivo no se bloqueará para que se ejecute incluso si una regla de reducción de superficie de ataque detecta que el archivo contiene un comportamiento malintencionado.

> [!WARNING]
> Esto podría permitir que los archivos no seguros se ejecuten e infecten los dispositivos. Excluir archivos o carpetas puede reducir gravemente la protección proporcionada por las reglas de reducción de superficie de ataque. Los archivos que se habrían bloqueado por una regla podrán ejecutarse y no se registrará ningún informe o evento.

Una exclusión se aplica a todas las reglas que permiten exclusiones. Puede especificar un archivo individual, una ruta de acceso de carpeta o el nombre de dominio completo para un recurso. Sin embargo, no se puede limitar una exclusión a una regla específica.

Solo se aplica una exclusión cuando se inicia la aplicación o servicio excluidos. Por ejemplo, si agrega una exclusión para un servicio de actualización que ya se está ejecutando, el servicio de actualización seguirá desencadenando eventos hasta que el servicio se detenga y reinicie.

La reducción de superficie de ataque admite variables de entorno y caracteres comodín. Para obtener información acerca del uso de caracteres comodín, vea usar caracteres comodín en las listas de exclusión de extensión o ruta de acceso de [carpeta y nombre de archivo.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)
Si tiene problemas con las reglas que detectan archivos que cree que no deben detectarse, use el modo de auditoría [para probar la regla](evaluate-attack-surface-reduction.md).

Descripción de la regla | GUID
-|-|-
Impedir que todas las aplicaciones de Office creen procesos secundarios | D4F940AB-401B-4EFC-AADC-AD5F3C50688A
Bloquear la ejecución de scripts potencialmente ofuscados | 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC
Bloquear llamadas a la API de Win32 desde la macro de Office | 92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B
Impedir que las aplicaciones de Office creen contenido ejecutable | 3B576869-A4EC-4529-8536-B80A7769E899
Impedir que las aplicaciones de Office inyecten código en otros procesos | 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84
Impedir que JavaScript o VBScript inicien contenido ejecutable descargado | D3E037E1-3EB8-44C8-A917-57927947596D
Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web | BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550
Bloquear la ejecución de archivos ejecutables a menos que cumplan con criterios de prevalencia, antigüedad o lista de confianza | 01443614-cd74-433a-b99e-2ecdc07bfc25
Usar protección avanzada contra ransomware | c1db55ab-c21a-4637-bb3f-a12568109d35
Bloquear el robo de credenciales del subsistema de autoridad de seguridad local de Windows (lsass.exe) | 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2
Bloquear creaciones de proceso que se originen en comandos PSExec y WMI | d1e49aac-8f56-4280-b9ba-993a6d77406c
Bloquear procesos que no son de confianza y sin firma que se ejecutan desde USB | b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4
Impedir que las aplicaciones de comunicación de Office creen procesos secundarios | 26190899-1602-49e8-8b27-eb1d0a1ce869
Impedir que Adobe Reader cree procesos secundarios | 7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c
Bloquear la persistencia a través de la suscripción de eventos WMI | e6db77e5-3df2-4cf1-b95a-636979351e5b

Consulta el tema [de reducción de](attack-surface-reduction.md) superficie de ataque para obtener más información sobre cada regla.

### <a name="use-group-policy-to-exclude-files-and-folders"></a>Usar la directiva de grupo para excluir archivos y carpetas

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](https://technet.microsoft.com/library/cc731212.aspx)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y **seleccione Editar**.

2. En el **Editor de administración de directivas de** grupo, vaya a Configuración del equipo **y** haga clic en **Plantillas administrativas.**

3. Expande el árbol a **Componentes de Windows** Antivirus de Microsoft Defender Windows Defender reducción de superficie de ataque de Protección contra  >    >    >  **vulnerabilidades.**

4. Haga doble clic en la **configuración Excluir archivos y rutas** de acceso de las reglas de reducción de superficie de ataque y establezca la opción en **Habilitado**. Seleccione **Mostrar** e introduzca cada archivo o carpeta en la **columna Nombre de** valor. Escriba **0 en** la **columna Valor** de cada elemento.

> [!WARNING]
> No use comillas, ya que no son compatibles con la columna **Nombre de** valor o la **columna** Valor.

### <a name="use-powershell-to-exclude-files-and-folders"></a>Usar PowerShell para excluir archivos y carpetas

1. Escriba **powershell** en el menú Inicio, haga clic con el Windows PowerShell **y** seleccione Ejecutar como **administrador**
2. Escriba el siguiente cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

Siga usando para `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` agregar más carpetas a la lista.

> [!IMPORTANT]
> Se `Add-MpPreference` usa para anexar o agregar aplicaciones a la lista. El `Set-MpPreference` uso del cmdlet sobrescribirá la lista existente.

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a>Usar CSP mdm para excluir archivos y carpetas

Use [el proveedor ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) para agregar exclusiones.

## <a name="customize-the-notification"></a>Personalizar la notificación

Puedes personalizar la notificación para cuando se desencadena una regla y bloquea una aplicación o archivo. Consulta el [artículo Seguridad de Windows.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center)

## <a name="related-topics"></a>Temas relacionados

* [Reducir superficies de ataque con reglas de reducción de superficie de ataque](attack-surface-reduction.md)
* [Habilitar las reglas de la reducción de superficie expuesta a ataques](enable-attack-surface-reduction.md)
* [Evaluar las reglas de la reducción de la superficie expuesta a ataques](evaluate-attack-surface-reduction.md)
* [Preguntas más frecuentes sobre la reducción de la superficie expuesta a ataques](attack-surface-reduction.md)
