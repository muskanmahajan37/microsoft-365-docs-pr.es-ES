---
title: Conectarse a Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: Conéctese a su espacio empresarial de Microsoft 365 mediante PowerShell para que Microsoft 365 realice tareas del Centro de administración desde la línea de comandos.
ms.openlocfilehash: d1e347a13ca5c587fa544ef80a8e289a8dec0a59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693978"
---
# <a name="connect-to-microsoft-365-with-powershell"></a>Conectarse a Microsoft 365 con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

PowerShell para Microsoft 365 le permite administrar la configuración de Microsoft 365 desde la línea de comandos. Conectarse a PowerShell es un proceso sencillo que consiste en instalar el software necesario y conectarse a su organización de Microsoft 365. 

Hay dos versiones del módulo de PowerShell que puede usar para conectarse a Microsoft 365 y administrar cuentas de usuario, grupos y licencias:

- Azure Active Directory PowerShell para Graph (los cmdlets incluyen **AzureAD** en su nombre)
- Módulo Microsoft Azure Active Directory para Windows PowerShell (los cmdlets incluyen **MSol** en su nombre) 

En la fecha de este artículo, el Módulo MAzure Active Directory para Graph no reemplaza completamente la funcionalidad de los cmdlets del Módulo Microsoft Azure Active Directory para Windows PowerShell para la administración de usuarios, grupos y licencias. En algunos casos, deberá usar ambas versiones. Puede instalar ambas versiones de forma segura en el mismo equipo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

Puede usar las siguientes versiones de Windows:
    
  - Windows 10, Windows 8.1, Windows 8 o Windows 7 Service Pack 1 (SP1) 
    
  - Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 o Windows Server 2008 R2 SP1

    > [!NOTE]
    > Para el Módulo Azure Active Directory PowerShell para Graph, debe usar la versión 5.1 o posterior de PowerShell. Para el Módulo Microsoft Azure Active Directory para Windows PowerShell, debe usar la versión 5.1 o posterior de PowerShell hasta la versión 6. No puede usar la versión 7 de PowerShell. Para Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 y Windows Server 2008 R2 SP1, descargue e instale [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616). 
    
    > [!NOTE]
    > Use una versión de 64 bits de Windows. La compatibilidad con la versión de 32 bits de Módulo de Microsoft Azure Active Directory para Windows PowerShell se descontinuó en octubre de 2014.
    
Estos procedimientos están diseñados para los usuarios que sean miembros de un rol de administrador de Microsoft 365. Para obtener más información, vea [Asignar roles de administrador](https://go.microsoft.com/fwlink/p/?LinkId=532367).


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a>Conéctese al módulo de PowerShell de Azure Active Directory para Graph

Los comandos del módulo PowerShell Azure Active Directory para Graph incluyen **AzureAD** en su nombre de cmdlet. Puede instalar el módulo [Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory) o [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-3.6.1).

Para los procedimientos que necesitan los nuevos cmdlets del módulo de PowerShell Azure Active Directory para Graph, siga estos pasos para instalar el módulo y conectarse a su suscripción a Microsoft 365.

>[!Note]
>Vea [Módulo de PowerShell Azure Active Directory para Graph](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory) para obtener información sobre la compatibilidad con diferentes versiones de Microsoft Windows.
>

### <a name="step-1-install-required-software"></a>Paso 1: Instalar el software necesario

Estos pasos son necesarios una sola vez en el equipo, no cada vez que se conecta. Sin embargo, probablemente necesitará instalar las versiones más recientes de software periódicamente.
  
1. Abra un símbolo del sistema de Windows PowerShell con privilegios elevados (ejecute Windows PowerShell como administrador).
    
2. En la ventana de comandos **Administrador: Windows PowerShell**, ejecute este comando:
    
  ```powershell
  Install-Module -Name AzureAD
  ```

Si se le pregunta si quiere instalar un módulo desde un repositorio que no es de confianza, escriba **Y** y presione ENTRAR.

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Paso 2: Conectarse a Azure AD para la suscripción de Microsoft 365

Para conectarse a Azure AD para la suscripción de Microsoft 365 con un nombre de cuenta y contraseña o con la autenticación multifactor (MFA), ejecute uno de estos comandos desde un símbolo del sistema de Windows PowerShell (no tiene que ser elevado).

| Nube de Office 365 | Comando |
|:-------|:-----|
| Office 365 Worldwide (+GCC) | `Connect-AzureAD` |
| Office 365 ofrecido por 21Vianet | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| Office 365 Germany | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| Office 365 U.S. Government DoD y Office 365 U.S. Government GCC High | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

En el cuadro de diálogo **Inicie sesión**, escriba su nombre de usuario y contraseña de la cuenta profesional o educativa de Microsoft 365 y haga clic en **Aceptar**.

Si usa MFA, siga las instrucciones en los cuadros de diálogo adicionales para proporcionar más información de autenticación, como un código de comprobación.

Después de conectar, puede usar los cmdlets para el módulo [PowerShell de Azure Active Directory para](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory).
  

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Conectar con el Módulo Microsoft Azure Active Directory para Windows PowerShell

Los comandos del Módulo Microsoft Azure Active Directory para Windows PowerShell tienen **Msol** en el nombre de su cmdlet.

La versión 7 de PowerShell no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre. Para la versión 7 de PowerShell y versiones posteriores, debe usar el Módulo Azure Active Directory Powershell para Graph o Azure PowerShell.

PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre. Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell. 
    
### <a name="step-1-install-required-software"></a>Paso 1: Instalar el software necesario

Estos pasos son necesarios una sola vez en el equipo, no cada vez que se conecta. Sin embargo, probablemente necesitará instalar las versiones más recientes de software periódicamente.
  
1.  Si no ejecuta Windows 10, instale la versión de 64 bits de Microsoft Online Services - Ayudante para el inicio de sesión: [Ayudante para el inicio de sesión de Microsoft Online Services para profesionales de TI (RTW)](https://go.microsoft.com/fwlink/p/?LinkId=286152).
    
2. Instale el Módulo Microsoft Azure Active Directory para Windows PowerShell siguiendo estos pasos:
    
  - Abra un símbolo del sistema de Windows PowerShell con privilegios elevados (ejecute Windows PowerShell como administrador).
  - Ejecute el comando **Install-Module MSOnline**.
  - Si se le pide que instale el proveedor de NuGet, escriba **Y** y presione ENTRAR.
  - Si se le pide que instale el módulo desde PSGallery, escriba **Y** y presione ENTRAR.
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Paso 2: Conectarse a Azure AD para la suscripción de Microsoft 365

Para conectarse a Azure AD para la suscripción de Microsoft 365 con un nombre de cuenta y contraseña o con la autenticación multifactor (MFA), ejecute uno de estos comandos desde un símbolo del sistema de Windows PowerShell (no tiene que ser elevado).

| Nube de Office 365 | Comando |
|:-------|:-----|
| Office 365 Worldwide (+GCC) | `Connect-MsolService` |
| Office 365 ofrecido por 21Vianet | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| Office 365 Germany | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| Office 365 U.S. Government DoD y Office 365 U.S. Government GCC High | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

En el cuadro de diálogo **Inicie sesión**, escriba su nombre de usuario y contraseña de la cuenta profesional o educativa de Microsoft 365 y haga clic en **Aceptar**.

Si usa MFA, siga las instrucciones en los cuadros de diálogo adicionales para proporcionar más información de autenticación, como un código de comprobación.

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Si no se muestra ningún error, la conexión se habrá establecido correctamente. Para hacer una prueba rápida, ejecute un cmdlet de Microsoft 365, como **Get-MsolUser**, y vea los resultados.
  
Si surgen errores, compruebe los siguientes requisitos:
  
- **Un problema habitual es una contraseña incorrecta**. Vuelva a realizar el paso 2. y preste especial atención al nombre de usuario y la contraseña que escriba.
    
- **El Módulo de Microsoft Azure Active Directory para Windows PowerShell requiere que la característica Microsoft .NET Framework 3.5.* x* esté habilitada en el equipo**. Es probable que el equipo tenga instalada una versión más reciente (por ejemplo, 4 o 4.5. *x*), pero sea posible habilitar o deshabilitar la compatibilidad con versiones anteriores de .NET Framework. Para obtener más información al respecto, consulte los temas siguientes:
    
  - Para Windows Server 2012 o Windows Server 2012 R2, vea [Habilitar .NET Framework 3.5 con el Asistente para agregar roles y características](https://go.microsoft.com/fwlink/p/?LinkId=532368).
    
  - Para Windows 7 o Windows Server 2008 R2, vea [No puede abrir el Módulo de Azure Active Directory para Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370).

  - Para Windows 10, Windows 8.1 y Windows 8, vea [Instalar .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)

  
- **Puede que su versión de Módulo de Microsoft Azure Active Directory para Windows PowerShell esté obsoleta.** Para comprobarlo, ejecute el siguiente comando en PowerShell para Microsoft 365 o el Módulo de Microsoft Azure Active Directory para Windows PowerShell:
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    Si el número de versión devuelto es menor que el valor 1.0.8070.2, desinstale el Módulo de Microsoft Azure Active Directory para Windows PowerShell e instale de nuevo siguiendo el Paso 1, que encontrará arriba.

- **Si recibe un error de conexión, vea este tema:** [Error “Connect-MsolService: Se produjo una excepción de tipo”](https://go.microsoft.com/fwlink/p/?LinkId=532377).
    
- **Si recibe un mensaje de error "Obtener elemento: No se encontró la ruta de acceso", utilice este comando:** 

```powershell
  (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
```

## <a name="see-also"></a>Consulte también

- [Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)
- [Conectarse a todos los servicios de Microsoft 365 en una sola ventana de Windows PowerShell](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)