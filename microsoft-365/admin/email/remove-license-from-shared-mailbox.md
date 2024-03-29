---
title: Quitar la licencia de un buzón compartido
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
ms.reviewer: nicholak
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_licensing
search.appverid:
- BCS160
- MET150
- MOE150
description: 'Quite la licencia de un buzón compartido para asignarla a otro usuario. '
ms.openlocfilehash: d552cfb77ff0ab2853939c6cb25fd4737f8c17d3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537588"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a>Quitar la licencia de un buzón compartido

Los buzones compartidos normalmente no requieren una licencia. Siga estas instrucciones para quitar una licencia de un buzón compartido para que pueda asignarla a un usuario o devolver la licencia para que no pague una licencia que no necesite.

> [!NOTE]
>
> Se requiere una licencia en los siguientes escenarios:
>
> 1. El buzón compartido tiene más de 50 GB de almacenamiento en uso.
> 2. El buzón compartido usa archivado local.
> 3. El buzón compartido se coloca en retención por juicio.
> 4. El buzón compartido tiene asignada una licencia de Microsoft Defender.

## <a name="remove-the-license"></a>Quitar la licencia

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end

   > [!NOTE]
   > Debe quitar la licencia de la página Usuarios activos. No puede quitar la licencia de la página Buzón compartido porque las licencias son configuraciones de usuario.
  
2. Seleccione el buzón compartido.

3. Una de **las pestañas Licencias y Aplicaciones,** expanda **Licencias** y desactive la casilla de la licencia que desea quitar.

4. Seleccione **Guardar cambios**.

5. Cuando vuelva a la **página Usuarios activos,** el estado del buzón compartido será **Sin licencia.**

6. Sigue pagando por la licencia. Para dejar de pagar por ella, [quite la licencia de la suscripción](../../commerce/licenses/buy-licenses.md).

## <a name="related-articles"></a>Artículos relacionados

[Acerca de los buzones compartidos](about-shared-mailboxes.md)

[Crear un buzón compartido](create-a-shared-mailbox.md)

[Configurar un buzón compartido](configure-a-shared-mailbox.md)

[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md)

[Resolver problemas con los buzones compartidos](resolve-issues-with-shared-mailboxes.md)
