---
title: Fase 3 de autenticación federada de alta disponibilidad Configurar servidores de AD FS
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 202b76ff-74a6-4486-ada1-a9bf099dab8f
description: Obtenga información sobre cómo crear y configurar los servidores de AD FS para la autenticación federada de alta disponibilidad para Microsoft 365 en Microsoft Azure.
ms.openlocfilehash: 388a99aa496c4ecd9145759d4dfb1b9441b4fb2c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909803"
---
# <a name="high-availability-federated-authentication-phase-3-configure-ad-fs-servers"></a>Fase 3 de la autenticación federada de alta disponibilidad: Configurar servidores de AD FS

En esta fase de implementación de alta disponibilidad para la autenticación federada de Microsoft 365 en los servicios de infraestructura de Azure, se crea un equilibrador de carga interno y dos servidores de AD FS.
  
Debe completar esta fase antes de pasar a [fase 4: Configurar](high-availability-federated-authentication-phase-4-configure-web-application-pro.md)servidores proxy de aplicación web . Consulte Implementar la autenticación federada de alta disponibilidad [para Microsoft 365 en Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) para todas las fases.
  
## <a name="create-the-ad-fs-server-virtual-machines-in-azure"></a>Crear las máquinas virtuales del servidor de AD FS en Azure

Use el siguiente bloque de comandos de PowerShell para crear las máquinas virtuales de los dos servidores de AD FS. En este conjunto de comandos de PowerShell se usan valores de las tablas siguientes:
  
- Tabla N, para las máquinas virtuales
    
- Tabla R, para los grupos de recursos
    
- Tabla V, para la configuración de la red virtual
    
- Tabla S, para las subredes
    
- Tabla I, para las direcciones IP estáticas
    
- Tabla A, para los conjuntos de disponibilidad
    
Recuerde que ha definido la tabla M en la fase [2:](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) Configurar controladores de dominio y tablas R, V, S, I y A en la fase [1: Configurar Azure](high-availability-federated-authentication-phase-1-configure-azure.md).
  
> [!NOTE]
> Los siguientes conjuntos de comandos utilizan la última versión de Azure PowerShell. Consulte [Introducción a Azure PowerShell](/powershell/azure/get-started-azureps). 
  
Primero, cree un equilibrador de carga interno de Azure para los dos servidores de AD FS. Especifique los valores de las variables, quitando los \< and > caracteres. Después de especificar todos los valores correctos, ejecute el bloque resultante en el símbolo del sistema de Azure PowerShell o en PowerShell ISE.
  
> [!TIP]
> Para generar bloques de comandos de PowerShell listos para ejecutarse en función de la configuración personalizada, use este libro [de configuración de Microsoft Excel](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx). 

```powershell
# Set up key variables
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 2 - Subnet name column>"
$privIP="<Table I - Item 4 - Value column>"
$rgName=<Table R - Item 4 - Resource group name column>"

$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName

$frontendIP=New-AzLoadBalancerFrontendIpConfig -Name "ADFSServers-LBFE" -PrivateIPAddress $privIP -Subnet $subnet
$beAddressPool=New-AzLoadBalancerBackendAddressPoolConfig -Name "ADFSServers-LBBE"

$healthProbe=New-AzLoadBalancerProbeConfig -Name WebServersProbe -Protocol "TCP" -Port 443 -IntervalInSeconds 15 -ProbeCount 2
$lbrule=New-AzLoadBalancerRuleConfig -Name "HTTPSTraffic" -FrontendIpConfiguration $frontendIP -BackendAddressPool $beAddressPool -Probe $healthProbe -Protocol "TCP" -FrontendPort 443 -BackendPort 443
New-AzLoadBalancer -ResourceGroupName $rgName -Name "ADFSServers" -Location $locName -LoadBalancingRule $lbrule -BackendAddressPool $beAddressPool -Probe $healthProbe -FrontendIpConfiguration $frontendIP
```

Después, cree las máquinas virtuales del servidor de AD FS.
  
Después de especificar todos los valores correctos, ejecute el bloque resultante en el símbolo del sistema de Azure PowerShell o en PowerShell ISE.
  
```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 2 - Subnet name column>"
$avName="<Table A - Item 2 - Availability set name column>"
$rgNameTier="<Table R - Item 2 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName
$backendSubnet=Get-AzVirtualNetworkSubnetConfig -Name $subnetName -VirtualNetwork $vnet
$webLB=Get-AzLoadBalancer -ResourceGroupName $rgName -Name "ADFSServers"

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName

# Create the first ADFS server virtual machine
$vmName="<Table M - Item 4 - Virtual machine name column>"
$vmSize="<Table M - Item 4 - Minimum size column>"
$staticIP="<Table I - Item 5 - Value column>"
$diskStorageType="<Table M - Item 4 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first AD FS server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second AD FS virtual machine
$vmName="<Table M - Item 5 - Virtual machine name column>"
$vmSize="<Table M - Item 5 - Minimum size column>"
$staticIP="<Table I - Item 6 - Value column>"
$diskStorageType="<Table M - Item 5 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName  -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second AD FS server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

```

> [!NOTE]
> Como estas máquinas virtuales son para una aplicación de intranet, no se les asigna una dirección IP pública ni una etiqueta de nombre de dominio DNS, ni se exponen a Internet. Pero esto también quiere decir que no podrá conectarse a estas desde Azure Portal. La opción **Conectar** no estará disponible al ver las propiedades de la máquina virtual. Use la herramienta Conexión a Escritorio remoto u otra herramienta de Escritorio remoto para conectarse a la máquina virtual con su dirección IP privada o con el nombre DNS de la intranet.
  
Por cada máquina virtual, use el cliente de Escritorio remoto que prefiera y cree una conexión a Escritorio remoto. Use el nombre DNS de la intranet o el nombre de equipo y las credenciales de la cuenta de administrador local.
  
Para cada máquina virtual, únase al dominio de servicios de dominio de Active Directory (AD DS) adecuado con estos comandos en el Windows PowerShell usuario.
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

Esta es la configuración completada después de la finalización correcta de esta fase, con los nombres de equipo de marcadores de posición.
  
**Fase 3: Equilibrador de carga interno y servidores de AD FS para la infraestructura de autenticación federada de alta disponibilidad en Azure**

![Fase 3 de la infraestructura de autenticación federada de Microsoft 365 de alta disponibilidad en Azure con los servidores de AD FS](../media/f39b2d2f-8a5b-44da-b763-e1f943fcdbc4.png)
  
## <a name="next-step"></a>Paso siguiente

Use [phase 4: Configure web application proxies](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) to continue configuring this workload.
  
## <a name="see-also"></a>Consulta también

[Implementar la autenticación federada de alta disponibilidad para Microsoft 365 en Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Identidad federada para el entorno de desarrollo y pruebas de Microsoft 365](federated-identity-for-your-microsoft-365-dev-test-environment.md)