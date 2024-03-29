---
title: Deshabilitar el acceso a los servicios de Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/27/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- PowerShell
- LIL_Placement
- seo-marvel-apr2020
ms.assetid: 264f4f0d-e2cd-44da-a9d9-23bef250a720
description: En este artículo, obtenga información sobre cómo usar PowerShell para deshabilitar el acceso a los servicios de Microsoft 365 para los usuarios.
ms.openlocfilehash: 292bda3b380b9ce3947b2427288da4f16198bb51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693848"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a>Deshabilitar el acceso a los servicios de Microsoft 365 con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Cuando se asigna una licencia de un plan de licencias a una cuenta de Microsoft 365, los servicios de Microsoft 365 están disponibles para el usuario desde esa licencia. Sin embargo, puede controlar los servicios de Microsoft 365 a los que puede tener acceso el usuario. Por ejemplo, aunque la licencia permita el acceso al servicio de SharePoint Online, puede deshabilitar el acceso a él. Puede usar PowerShell para deshabilitar el acceso a cualquier número de servicios para un plan de licencias específico para:

- Una cuenta individual.
- Un grupo de cuentas.
- Todas las cuentas de su organización.

>[!Note]
>Hay dependencias de servicio de Microsoft 365 que pueden impedir que se deshabilite un servicio especificado cuando otros servicios dependen de él.
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use el Módulo Microsoft Azure Active Directory para Windows PowerShell

En primer [lugar, conéctese a su inquilino de Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

A continuación, use este comando para ver los planes de licencias disponibles, también conocidos como AccountSkuIds:

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
>PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre. Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.
>

Para obtener más información, vea [Ver licencias y servicios con PowerShell.](view-licenses-and-services-with-microsoft-365-powershell.md)
    
Para ver los resultados antes y después de los procedimientos de este tema, vea Ver detalles de servicio y licencia de cuenta [con PowerShell.](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
Hay un script de PowerShell que automatiza los procedimientos descritos en este tema. En concreto, el script le permite ver y deshabilitar servicios en su organización de Microsoft 365, incluido Sway. Para obtener más información, vea [Deshabilitar el acceso a Sway con PowerShell.](disable-access-to-sway-with-microsoft-365-powershell.md)
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a>Deshabilitar servicios específicos de Microsoft 365 para usuarios específicos para un plan de licencias específico
  
Para deshabilitar un conjunto específico de servicios de Microsoft 365 para los usuarios para un plan de licencias específico, siga estos pasos:
  
#### <a name="step-1-identify-the-undesirable-services-in-the-licensing-plan-by-using-the-following-syntax"></a>Paso 1: Identifique los servicios no deseados en el plan de licencias mediante la siguiente sintaxis:
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesirableService1>", "<UndesirableService2>"...
```

En el siguiente ejemplo se crea un objeto **LicenseOptions** que deshabilita los servicios de Office y SharePoint Online en el plan de licencias denominado `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3).
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a>Paso 2: Use el **objeto LicenseOptions** del paso 1 en uno o más usuarios.
    
Para crear una nueva cuenta con los servicios deshabilitados, use la sintaxis siguiente:
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

En el siguiente ejemplo se crea una nueva cuenta para Allie Bellew que asigna la licencia y deshabilita los servicios descritos en el paso 1.
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

Para obtener más información acerca de la creación de cuentas de usuario en PowerShell para Microsoft 365, vea Crear cuentas [de usuario con PowerShell.](create-user-accounts-with-microsoft-365-powershell.md)
    
Para deshabilitar los servicios para un usuario con licencia existente, use la siguiente sintaxis:
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

En este ejemplo se deshabilitan los servicios para el usuario BelindaN@litwareinc.com.
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

Para deshabilitar los servicios descritos en el paso 1 para todos los usuarios con licencia existentes, especifique el nombre de su plan de Microsoft 365 en la presentación del cmdlet **Get-MsolAccountSku** (como **litwareinc:ENTERPRISEPACK)** y, a continuación, ejecute los siguientes comandos:
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 Si usa el cmdlet **Get-MsolUser** sin usar el parámetro _All,_ solo se devuelven las primeras 500 cuentas de usuario.

Para deshabilitar los servicios para un grupo de usuarios existentes, use cualquiera de los métodos siguientes para identificar a los usuarios:
    
**Método 1. Filtrar las cuentas en función de un atributo de cuenta existente** 

Para ello, utilice la siguiente sintaxis:
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

En el siguiente ejemplo se deshabilitan los servicios para los usuarios del departamento de ventas de Estados Unidos.
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

**Método 2: Usar una lista de cuentas específicas** 

Para ello, siga estos pasos:
    
1. Cree un archivo de texto que contenga una cuenta en cada línea como en el ejemplo:
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   En este ejemplo, el archivo de texto es C: \\ Mis documentos \\Accounts.txt.
    
2. Ejecute el siguiente comando:
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

Si desea deshabilitar el acceso a servicios para varios planes de licencias, repita las instrucciones anteriores para cada plan de licencias, asegurándose de que:

- Se ha asignado el plan de licencias a las cuentas de usuario.
- Los servicios que se van a deshabilitar están disponibles en el plan de licencias.

Para deshabilitar los servicios de Microsoft 365 para los usuarios mientras los asigna a un plan de licencias, vea Deshabilitar el acceso a los servicios al asignar licencias [de usuario.](disable-access-to-services-while-assigning-user-licenses.md)

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a>Asignar todos los servicios de un plan de licencias a una cuenta de usuario

Para las cuentas de usuario que tienen servicios deshabilitados, puede habilitar todos los servicios para un plan de licencias específico con estos comandos:

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a>Tema relacionado

[Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)
