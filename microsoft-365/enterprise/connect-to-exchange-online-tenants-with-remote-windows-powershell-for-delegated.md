---
title: Conectarse a los inquilinos de Exchange Online con Windows PowerShell remoto para asociados de DAP
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: ae5f1a87-8b77-4f93-a1b8-56f800aeb283
description: 'Resumen: use el modo remoto de Windows PowerShell para conectarse a Exchange Online con el valor DelegatedOrg.'
ms.openlocfilehash: 1351a6a6d19fac408b673796c1179bca0ede9c9f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693979"
---
# <a name="connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Conectarse a los inquilinos de Exchange Online con el modo remoto de Windows PowerShell para asociados con permiso de acceso delegado (DAP)

*Este artículo se aplica tanto a Microsoft 365 Enterprise como a Office 365 Enterprise.*

> [!IMPORTANT]
> Los procedimientos descritos en este tema son solo para partners con permiso de acceso delegado (DAP). Si no es un partner con DAP, no use los procedimientos descritos en este tema. 
  
Los asociados con DAP son asociados de proveedor de soluciones en la nube (CSP) y redifusión web. Generalmente son proveedores de red o de telecomunicaciones para otras compañías. Agrupan las suscripciones en sus ofertas de servicio para sus clientes. Poseen un arrendamiento de Partners al que se conceden automáticamente permisos de administración en nombre de (AOBO) para los arrendamientos de clientes de Microsoft 365 para que puedan administrar y informar sobre todos los arrendamientos de clientes.

Los asociados de DAP pueden usar Exchange Online PowerShell para administrar la configuración de Exchange online de clientes y obtener los informes de Microsoft 365 desde la línea de comandos. Use la sesión de Windows PowerShell en su equipo local para crear una sesión remota de PowerShell en Exchange Online. Se trata de un proceso de tres pasos sencillo donde se escriben las credenciales, se proporcionan las opciones de conexión necesarias y, a continuación, se importan los cmdlets de Exchange Online a la sesión local de Windows PowerShell para que se puedan usar.

> [!NOTE]
> Los partners con DAP no pueden usar los procedimientos descritos en [Conectarse a Exchange Online PowerShell con la autenticación multifactor](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell) para conectarse a sus organizaciones de espacios empresariales de clientes en Exchange Online PowerShell. MFA y el módulo remoto Exchange Online PowerShell no funcionan con la autenticación delegada.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Tiempo estimado para finalizar: 5 minutos

- Puede usar las siguientes versiones de Windows:
    
  - Windows 10

  - Windows 8.1

  - Windows Server 2016

  - Windows Server 2012 o Windows Server 2012 R2

  - Windows 7 Service Pack 1 (SP1)<sup>*</sup>

  - Windows Server 2008 R2 SP1<sup>*</sup>

    <sup>*</sup> Para versiones anteriores de Windows, deberá instalar Microsoft.NET Framework 4.5 o una versión posterior y, a continuación, una versión actualizada de Windows Management Framework: 3.0, 4.0 o 5.1 (solamente uno). Para obtener más información, vea [Instalación de .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757), [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344) y [Windows Management Framework 5.1](https://aka.ms/wmf5download).

- Windows PowerShell se debe configurar para ejecutar scripts y, por defecto, no lo está. Obtendrá el siguiente error al intentar conectar:

  `Files cannot be loaded because running scripts is disabled on this system. Provide a valid certificate with which to sign the files.`

  Para requerir que todos los scripts de PowerShell que se descargue de internet sean de publicadores de confianza, ejecute el siguiente comando en una ventana de Windows PowerShell con permisos elevados (o sea, una ventana de Windows PowerShell que se abre seleccionando **Ejecutar como administrador**):

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

  Esta opción se configura una sola vez en el equipo, y no cada vez que se conecte.

- Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [Métodos abreviados de teclado en el Centro de administración de Exchange](https://go.microsoft.com/fwlink/p/?LinkId=534017).

## <a name="connect-to-exchange-online-for-customer-organizations"></a>Conectarse a Exchange Online para organizaciones de cliente

1. En el equipo local, abra Windows PowerShell y ejecute el siguiente comando.
    
    ```
    $UserCredential = Get-Credential
    ```

    En el cuadro de diálogo **Solicitud de credenciales para Windows PowerShell**, escriba su nombre de usuario de administrador DAP y contraseña y, a continuación, haga clic en **Aceptar**.
    
2. Reemplace _\<customer tenant domain name\>_ por el nombre del dominio del inquilino al que desea conectarse y ejecute el siguiente comando:
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid?DelegatedOrg=<customer tenant domain name> -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

    El paso clave de este comando es especificar a qué cliente tiene acceso para obtener información sobre los informes. Esto se hace en el parámetro  _ConnectionURI_ , donde se proporciona el FQDN del nombre de dominio inicial como valor de `?DelegatedOrg=` . Este valor indica el punto de conexión de PowerShell de Exchange Online correcto al que se va a conectar. PowerShell remoto debe conectarse a los informes de Microsoft 365 en el contexto de un cliente específico cada vez que se ejecuta un informe. Después de conectarse a Exchange Online PowerShell, todos los comandos siguientes se ejecutan en el contexto del cliente, lo que le proporciona acceso a todos los informes disponibles para el cliente.
    
3. Ejecute el comando siguiente.
    
    ```
    Import-PSSession $Session
    ```

> [!NOTE]
> Hay un límite de tres sesiones simultáneas que se pueden ejecutar en una cuenta. Asegúrese de desconectarse de la sesión remota de PowerShell cuando haya finalizado. Si cierra la ventana de Windows PowerShell sin desconectar la sesión, podría agotar todas las sesiones de PowerShell remotas que tenga disponibles y deberá esperar a que las sesiones expiren. Ejecute el siguiente comando para desconectar la sesión remota de PowerShell:

```
Remove-PSSession $Session
```
  
## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Después del paso 3, los cmdlets de Exchange Online se importan a la sesión local de Windows PowerShell, como se indica en una barra de progreso. Si no aparece ningún error, la conexión se habrá establecido correctamente. Una prueba rápida es ejecutar un cmdlet de Exchange Online (por ejemplo, **Get-Mailbox**) y ver los resultados.
  
Si surgen errores, compruebe los siguientes requisitos:
  
- Un problema habitual es una contraseña incorrecta. Vuelva a realizar los tres pasos y preste especial atención al nombre de usuario y contraseña que escriba en el paso 1.
    
- La cuenta que use para conectarse a Exchange Online debe estar habilitada para PowerShell remoto. Para más información consulte [Activar o desactivar el acceso a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534018).
    
- Debe abrir el tráfico del puerto TCP 80 entre su equipo local y Exchange Online. Probablemente esté abierta, pero es un aspecto que se debe tener en cuenta si la directiva de acceso a Internet de su organización es restrictiva.
    
## <a name="call-the-cmdlet-directly-with-invoke-command"></a>Llamar directamente al cmdlet con Invoke-Command

Importar una sesión remota de PowerShell (paso 3) puede ser un proceso largo, ya que incorpora _todos_ los cmdlets de Exchange Online. Esto puede ser un problema para el procesamiento por lotes (por ejemplo, cuando se ejecutan informes o se realizan cambios masivos para diferentes inquilinos). Como alternativa al uso de **Import-PSSession**, puede llamar a los cmdlets que desea usar directamente con **Invoke-Command**. Por ejemplo, para llamar al cmdlet **Get-Milbox**, reemplace esta sintaxis por el comando `Import-PSSession $Session` del paso 3:
  
```
Invoke-Command -Session $Session -ScriptBlock {Get-Mailbox}
```

## <a name="more-reporting-cmdlets"></a>Más cmdlets de informes

Los cmdlets que se usan en este tema son cmdlets de Windows PowerShell. Para obtener más información sobre estos cmdlets, consulte los siguientes temas:
  
- [Get-Credential](https://go.microsoft.com/fwlink/p/?LinkId=389618)
    
- [New-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389621)
    
- [Import-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389619)
    
- [Remove-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389620)
    
- [Set-ExecutionPolicy](https://go.microsoft.com/fwlink/p/?LinkId=389623)
    
