---
title: Configurar IRM para usar un servidor de AD RMS local
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo configurar Information Rights Management (IRM) en Exchange Online usar un servidor de Active Directory Rights Management Service (AD RMS).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5e430f9c6ad5d377b568d22e9de53ab79d19165a
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876125"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a>Configurar IRM para usar un servidor de AD RMS local
  
Para su uso con implementaciones locales, Information Rights Management (IRM) en Exchange Online usa Active Directory Rights Management Services (AD RMS), una tecnología de protección de la información en Windows Server 2008 y versiones posteriores. La protección de IRM se implanta en el correo electrónico mediante la aplicación de una plantilla de directiva de permisos de AD RMS a un mensaje de correo electrónico. Los derechos se adjuntan al propio mensaje para que la protección se produzca en línea y sin conexión y dentro y fuera del firewall de la organización.
  
En este tema se muestra cómo configurar IRM para usar un servidor de AD RMS. Para obtener información acerca del uso de las nuevas funcionalidades para Cifrado de mensajes de Office 365 con Azure Active Directory y Azure Rights Management, vea las [preguntas Cifrado de mensajes de Office 365 preguntas más frecuentes.](./ome-faq.yml)
  
Para obtener más información sobre IRM en Exchange Online, consulte [Information Rights Management en Exchange Online](information-rights-management-in-exchange-online.md).
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Tiempo estimado para finalizar esta tarea: 30 minutos

- Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "Information Rights Management" en el tema [Messaging policy and compliance permissions](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions). 

- El servidor AD RMS debe estar ejecutando Windows Server 2008 o posterior. Para obtener información detallada sobre cómo implementar AD RMS, vea [Instalación de un clúster de AD RMS](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11)).

- Para obtener información detallada sobre cómo instalar y configurar Windows PowerShell y conectarlo al servicio, vea [Conectarse a Exchange Online mediante PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell).

- Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, vea [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> ¿Tiene algún problema? Solicite ayuda en los foros de Exchange. Visite los foros en [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="how-do-you-do-this"></a>¿Cómo debe hacer esto?
<a name="sectionSection1"> </a>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a>Paso 1: Use la consola AD RMS para exportar un dominio de publicación de confianza (TPD) desde un servidor AD RMS

El primer paso es exportar un dominio de publicación de confianza (TPD) del servidor local AD RMS a un archivo XML. El dominio de publicación de confianza contiene las siguientes opciones de configuración que se necesitan para usar características RMS:
  
- El certificado emisor de licencias de servidor (SLC) utilizado para firmar y cifrar certificados y licencias

- Las direcciones URL utilizadas para emitir licencias y publicar

- Las plantillas de directiva de permisos de AD RMS que se crearon con el certificado emisor de licencias de servidor específico para ese dominio de publicación de confianza

Al importar el dominio de publicación de confianza, se almacena y se protege en Exchange Online.
  
1. Abra la consola de Active Directory Rights Management Services y, a continuación, expanda el clúster AD RMS.

2. En el árbol de consola, expanda **Directivas de confianza** y, a continuación, haga clic en **Dominios de publicación de confianza**.

3. En el panel de resultados, seleccione el certificado para el dominio que desea exportar.

4. En el panel **Acciones**, haga clic en **Exportar dominio de publicación de confianza**.

5. En el cuadro **Archivo de dominio de publicación**, haga clic en **Guardar como** para guardar el archivo en una ubicación concreta del equipo local. Escriba un nombre de archivo, asegúrese de especificar la extensión de nombre de archivo  `.xml` y haga clic en **Guardar**.

6. En los cuadros **Contraseña** y **Confirmar contraseña**, escriba una contraseña segura que se va a usar para cifrar el archivo de dominio de publicación de confianza. Tendrá que especificar esta contraseña al importar el dominio de publicación de confianza a su organización de correo electrónico basada en nube. 

### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a>Paso 2: use el Shell de administración de Exchange para importar el dominio de publicación de confianza a Exchange Online

Una vez exportado el dominio de publicación de confianza a un archivo XML, tiene que importarlo a Exchange Online. Cuando se importa el dominio de publicación de confianza, también se importan las plantillas AD RMS. Cuando se importa el primer dominio de publicación de confianza, se convierte en el dominio de publicación de confianza predeterminado para su organización basada en nube. Si importa otro TPD, puede utilizar el parámetro **Predeterminado** para convertirlo en el TPD predeterminado disponible para los usuarios. 
  
Para importar el TPD, ejecute el comando siguiente en Windows PowerShell:
  
```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

Puede obtener los valores para los parámetros  _ExtranetLicensingUrl_ e  _IntranetLicensingUrl_ en la consola de Active Directory Rights Management Services. Seleccione el clúster AD RMS en el árbol de consola. Las direcciones URL de emisión de licencias aparecen en el panel de resultados. Los clientes de correo electrónico utilizan estas direcciones URL cuando el contenido tiene que ser descifrado y cuando Exchange Online necesita determinar qué dominio de publicación de confianza utilizar.
  
Al ejecutar este comando, se solicita una contraseña. Escriba la contraseña que especificó cuando exportó el TPD desde su servidor AD RMS.
  
Por ejemplo, el siguiente comando importa el dominio de publicación de confianza, denominado Exported TPD, utilizando el archivo XML que exportó desde su servidor AD RMS y guardó en el escritorio de la cuenta de Administrador. El parámetro Name se utiliza para especificar un nombre para el dominio de publicación de confianza.
  
```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain).
  
#### <a name="how-do-you-know-this-step-worked"></a>¿Cómo sabe si este paso funcionó?

Para comprobar que el dominio de publicación de confianza se haya importado correctamente, ejecute el cmdlet **Get-RMSTrustedPublishingDomain** para recuperar los dominios de publicación de confianza de su organización de Exchange Online. Para obtener detalles, consulte los ejemplos en [Get-RMSTrustedPublishingDomain](/powershell/module/exchange/get-rmstrustedpublishingdomain).
  
### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a>Paso 3: use el Shell de administración de Exchange para distribuir una plantilla de directiva de permisos AD RMS

Después de importar el dominio de publicación de confianza, debe asegurarse de que la plantilla de directiva de permisos AD RMS esté distribuida. Una plantilla distribuida es visible para Outlook usuarios web (anteriormente conocidos como Outlook Web App), que pueden aplicar las plantillas a un mensaje de correo electrónico.
  
Para obtener una lista de todas las plantillas que incluye el TPD predeterminado, ejecute el comando siguiente:
  
```powershell
Get-RMSTemplate -Type All | fl
```

Si el valor del parámetro  _Type_ es  `Archived`, la plantilla no está visible para los usuarios. Solo las plantillas distribuidas en el TPD predeterminado están disponibles en Outlook en la web.
  
Para distribuir una plantilla, ejecute el comando siguiente:
  
```powershell
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

Por ejemplo, el siguiente comando importa la plantilla Company Confidential.
  
```powershell
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

Para obtener más información acerca de la sintaxis y los parámetros, consulte [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) y [Set-RMSTemplate](/powershell/module/exchange/set-rmstemplate).
  
**Plantilla No reenviar**
  
Cuando importa el dominio de publicación de confianza predeterminado desde la organización local en Exchange Online, se importa una plantilla de directiva de permisos AD RMS denominada **No reenviar**. De manera predeterminada, esta plantilla se distribuye al importar el dominio de publicación de confianza predeterminado. No puede usar el cmdlet **Set-RMSTemplate** para modificar la plantilla **No reenviar**. 
  
Cuando se aplica la plantilla **No reenviar** a un mensaje, solo los destinatarios del mensaje pueden leerlo. Además, los destinatarios no pueden hacer lo siguiente:
  
- Reenviar el mensaje a otra persona.

- Copiar el contenido del mensaje.

- Imprimir el mensaje.

> [!IMPORTANT]
> La plantilla **No reenviar** no puede evitar que la información de un mensaje se copie con programas de captura de pantalla de otros fabricantes, con cámaras o que los usuarios transcriban la información manualmente. 
  
Puede crear plantillas de directiva de permisos AD RMS adicionales en el servidor de AD RMS de la organización local a fin de cumplir con los requisitos de protección de IRM. Si crea plantillas de directiva de permisos AD RMS adicionales, tiene que exportar de nuevo el dominio de publicación de confianza desde el servidor local AD RMS y actualizarlo en la organización de correo electrónico basada en nube.
  
#### <a name="how-do-you-know-this-step-worked"></a>¿Cómo sabe si este paso funcionó?

Para comprobar que una plantilla de directiva de permisos AD RMS se distribuyó correctamente, ejecute el cmdlet **Get-RMSTemplate** para comprobar las propiedades de la plantilla. Para obtener detalles, consulte los ejemplos en [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate).
  
### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a>Paso 4: use el Shell de administración de Exchange para habilitar IRM

Después de importar el dominio de publicación de confianza y distribuir una plantilla de directiva de permisos AD RMS, ejecute el siguiente comando para habilitar IRM para la organización de correo electrónico basada en nube.
  
```powershell
Set-IRMConfiguration -InternalLicensingEnabled $true
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration).
  
#### <a name="how-do-you-know-this-step-worked"></a>¿Cómo sabe si este paso funcionó?

Para comprobar que IRM se haya habilitado correctamente, ejecute el cmdlet [Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration) para comprobar la configuración de IRM en la organización de Exchange Online.
  
## <a name="how-do-you-know-this-task-worked"></a>¿Cómo sabe si esta tarea funcionó?
<a name="sectionSection2"> </a>

Para comprobar si ha importado el TPD y ha habilitado IRM correctamente, haga lo siguiente:
  
- Use el cmdlet **Test-IRMConfiguration** para probar si IRM funciona. Para obtener más información, vea "Ejemplo 1" en [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).

- Redacte un nuevo mensaje Outlook en la web y protéjalo mediante la selección de la opción Establecer permisos en el menú extendido ( Icono Más opciones  ![ ](../media/ITPro-EAC-MoreOptionsIcon.gif) ).