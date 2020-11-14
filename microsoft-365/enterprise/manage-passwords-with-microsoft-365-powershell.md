---
title: Administración de contraseñas con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: Obtenga información sobre cómo usar PowerShell para administrar contraseñas.
ms.openlocfilehash: ac0a47edb4ccbed93c1a3b88df083d463784b4a4
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073217"
---
# <a name="manage-passwords-with-powershell"></a><span data-ttu-id="759e9-103">Administración de contraseñas con PowerShell</span><span class="sxs-lookup"><span data-stu-id="759e9-103">Manage passwords with PowerShell</span></span>

<span data-ttu-id="759e9-104">*Este artículo se aplica tanto a Microsoft 365 Enterprise como a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="759e9-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="759e9-105">Puede usar PowerShell para Microsoft 365 como una alternativa al centro de administración de Microsoft 365 para administrar contraseñas en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="759e9-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage passwords in Microsoft 365.</span></span> 

<span data-ttu-id="759e9-106">Cuando un bloque de comandos de este artículo requiere que especifique valores de variables, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="759e9-106">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="759e9-107">Copie el bloque de comandos en el portapapeles y péguelo en el Bloc de notas o en el entorno de scripting integrado (ISE) de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="759e9-107">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="759e9-108">Rellene los valores de la variable y quite los caracteres "<" y ">".</span><span class="sxs-lookup"><span data-stu-id="759e9-108">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="759e9-109">Ejecute los comandos en la ventana de PowerShell o en PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="759e9-109">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="759e9-110">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="759e9-110">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="759e9-111">En primer lugar, [Conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="759e9-111">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="759e9-112">Establecer una contraseña</span><span class="sxs-lookup"><span data-stu-id="759e9-112">Set a password</span></span>

<span data-ttu-id="759e9-113">Use estos comandos para especificar una contraseña para una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="759e9-113">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="759e9-114">Obligar a un usuario a cambiar su contraseña</span><span class="sxs-lookup"><span data-stu-id="759e9-114">Force a user to change their password</span></span>

<span data-ttu-id="759e9-115">Use estos comandos para establecer una contraseña y obligar a un usuario a cambiar la nueva contraseña.</span><span class="sxs-lookup"><span data-stu-id="759e9-115">Use these commands to set a password and force a user to change their new password.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

<span data-ttu-id="759e9-116">Use estos comandos para establecer una contraseña y obligar a un usuario a cambiar su nueva contraseña la próxima vez que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="759e9-116">Use these commands to set a password and force a user to change their new password the next time they sign in.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="759e9-117">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="759e9-117">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="759e9-118">En primer lugar, [Conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="759e9-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="759e9-119">Establecer una contraseña</span><span class="sxs-lookup"><span data-stu-id="759e9-119">Set a password</span></span>

<span data-ttu-id="759e9-120">Use estos comandos para especificar una contraseña para una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="759e9-120">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="759e9-121">Obligar a un usuario a cambiar su contraseña</span><span class="sxs-lookup"><span data-stu-id="759e9-121">Force a user to change their password</span></span>

<span data-ttu-id="759e9-122">Use estos comandos para obligar a un usuario a cambiar su contraseña.</span><span class="sxs-lookup"><span data-stu-id="759e9-122">Use these commands to force a user to change their password.</span></span>

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a><span data-ttu-id="759e9-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="759e9-123">See also</span></span>

[<span data-ttu-id="759e9-124">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="759e9-124">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="759e9-125">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="759e9-125">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="759e9-126">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="759e9-126">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
