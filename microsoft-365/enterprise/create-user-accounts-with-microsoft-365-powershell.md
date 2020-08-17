---
title: Crear cuentas de usuario 365 de Microsoft con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: En este artículo, aprenderá a usar PowerShell para crear cuentas de usuario o varias cuentas de usuario de Microsoft 365.
ms.openlocfilehash: 53077352862b6d0df6bb569300e2d8bc2475df91
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693999"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a>Crear cuentas de usuario 365 de Microsoft con PowerShell

*Este artículo se aplica tanto a Microsoft 365 Enterprise como a Office 365 Enterprise.*

Puede usar PowerShell para Microsoft 365 para crear de forma eficaz cuentas de usuario, especialmente varias cuentas de usuario. Al crear cuentas de usuario en PowerShell, siempre son necesarias determinadas propiedades de la cuenta. Otras propiedades no son necesarias para crear la cuenta, pero aun así son importantes. Estas propiedades se describen en la tabla siguiente:
  
|**Nombre de propiedad**|**Obligatorio**|**Descripción**|
|:-----|:-----|:-----|
|**DisplayName** <br/> |Sí  <br/> |Este es el nombre para mostrar que se usa en los servicios de Microsoft 365. Por ejemplo, Caleb Sills.  <br/> |
|**UserPrincipalName** <br/> |Sí  <br/> |Este es el nombre de cuenta que se usa para iniciar sesión en los servicios de Microsoft 365. Por ejemplo, CalebS@contoso.onmicrosoft.com.  <br/> |
|**FirstName** <br/> |No  <br/> ||
|**Apellidos** <br/> |No  <br/> ||
|**LicenseAssignment** <br/> |No  <br/> |Se trata del plan de licencias (también conocido como el plan de licencia o SKU) desde el que se asigna una licencia disponible a la cuenta de usuario. La licencia define los servicios de Microsoft 365 que están disponibles para la cuenta. No es necesario asignar una licencia a un usuario cuando se crea la cuenta, pero la cuenta requiere una licencia para obtener acceso a los servicios de Microsoft 365. Dispone de 30 días para conceder una licencia a la cuenta de usuario después de crearla. |
|**Password** <br/> |No  <br/> | Si no especifica una contraseña, se asignará una aleatoria a la cuenta de usuario y esta será visible en los resultados del comando. Si especifica una contraseña, debe tener entre 8 y 16 caracteres ASCII de cualquiera de los siguientes tipos: letras minúsculas, letras mayúsculas, números y símbolos. <br/> |
|**UsageLocation** <br/> |No  <br/> |Se trata de un código de país válido ISO 3166-1 alpha-2. Por ejemplo, US para Estados Unidos y FR para Francia. Es importante proporcionar este valor, ya que algunos servicios de Microsoft 365 no están disponibles en determinados países, por lo que no puede asignar una licencia a una cuenta de usuario a menos que la cuenta tenga este valor configurado. Para obtener más información, consulte [Sobre las restricciones de licencia](https://go.microsoft.com/fwlink/p/?LinkId=691730).  <br/> |
   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use el módulo de PowerShell Azure Active Directory para Graph

En primer lugar, [Conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

Después de haberse conectado, use la sintaxis siguiente para crear una cuenta individual:
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

En este ejemplo se crea una cuenta para el usuario de Estados Unidos llamado Caleb Sills:
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use el Módulo Microsoft Azure Active Directory para Windows PowerShell

En primer lugar, [Conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="create-an-individual-user-account"></a>Cree una cuenta de usuario individual

Para crear una cuenta individual, use la sintaxis siguiente:
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
>PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre. Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.
>

Para obtener una lista de los nombres de planes de licencias disponibles, use este comando:

````powershell
Get-MsolAccountSku
````

En este ejemplo se crea una cuenta para el usuario de Estados Unidos llamado Caleb Sills y se asigna una licencia desde el plan de licencias `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3).
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a>Crear varias cuentas de usuario

1. Cree un archivo de valores separados por comas (CSV) que contenga la información necesaria de la cuenta de usuario. Por ejemplo:
    
  ```powershell
  UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
  ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
  LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
  ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
  ```

 > [!NOTE]
>Los nombres de columna y su orden en la primera fila del archivo CSV son arbitrarios, pero asegúrese de que los datos del resto del archivo coinciden con el orden de los nombres de columna y use los nombres de columna para los valores de parámetro en el comando PowerShell para Microsoft 365.
    
2. Utilice la sintaxis siguiente:
    
  ```powershell
  Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
  ```

En este ejemplo se crean las cuentas de usuario a partir del archivo denominado C:\My Documents\NewAccounts.csv y se registran los resultados en el archivo denominado C:\My Documents\NewAccountResults.csv.
    
  ```powershell
  Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
  ```

3. Revise el archivo de salida para ver los resultados. No se especificaron contraseñas, por lo que las contraseñas aleatorias generadas por Microsoft 365 son visibles en el archivo de salida.
    
## <a name="see-also"></a>Recursos adicionales

[Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)