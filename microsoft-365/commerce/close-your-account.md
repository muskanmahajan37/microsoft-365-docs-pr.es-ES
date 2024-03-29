---
title: Cerrar la cuenta
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
- commerce_subscription
search.appverid: MET150
description: Al cerrar su cuenta con Microsoft, se elimina toda la información relacionada con su cuenta, incluidas las licencias, los usuarios y los datos de usuario.
ms.date: 04/02/2021
ms.openlocfilehash: b212911707b5d6a967ab833a5a06bc76f5ceeb3b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624330"
---
# <a name="close-your-account"></a>Cerrar la cuenta

Al cerrar la cuenta de Microsoft, se elimina toda la información relacionada con su cuenta. Esta información incluye suscripciones, licencias, métodos de pago, usuarios y datos de usuario.

## <a name="before-you-begin"></a>Antes de empezar

Antes de iniciar este proceso, asegúrese de realizar una copia de seguridad de los datos que desea conservar.

Para poder realizar las tareas de este artículo, debe ser un administrador global o de facturación. Para más información, vea [Sobre los roles de administrador](../admin/add-users/about-admin-roles.md).

## <a name="step-1-delete-users"></a>Paso 1: Eliminar usuarios

Elimine todos los usuarios excepto un administrador global. El administrador global completa los pasos para cerrar la cuenta. Antes de poder eliminar el directorio al final de este proceso, debe eliminar todos los demás usuarios.

Si los usuarios se sincronizan desde local, desactive primero la sincronización y, a continuación, elimine los usuarios del directorio en la nube mediante Azure Portal o Azure PowerShell cmdlets.

Para eliminar usuarios, vea [User management admin: Delete one or more users](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365).

También puede usar el cmdlet [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) de PowerShell para eliminar usuarios en masa.

Si su organización usa Active Directory que se sincroniza con Microsoft Azure Active Directory (Azure AD), elimine la cuenta de usuario de Active Directory en su lugar. Para obtener instrucciones, vea [Bulk delete users in Azure Active Directory](/azure/active-directory/users-groups-roles/users-bulk-delete).

## <a name="step-2-cancel-all-active-subscriptions"></a>Paso 2: Cancelar todas las suscripciones activas

1. En el centro de administración, vaya a la página de **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
2. En la **pestaña Productos,** busque una suscripción activa. Seleccione los tres puntos (más acciones) y, después, seleccione **Cancelar suscripción**.
3. En el panel **Cancelar suscripción**, seleccione una razón por la que cancela. Opcionalmente, proporcione algún comentario.
4. Seleccione **Guardar**.
5. Repita los pasos del 1 al 4 para cancelar todas las suscripciones activas.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Paso 3: Eliminar todas las suscripciones deshabilitadas

1. En el centro de administración, vaya a la página de **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
2. En la **pestaña Productos,** seleccione una suscripción deshabilitada.
3. En la página detalles de la suscripción, en la sección Configuración de **suscripción y pago,** seleccione **Eliminar suscripción**.
4. En el **panel Eliminar suscripción,** seleccione **Eliminar suscripción**.
5. En el **cuadro de diálogo** Eliminar suscripción, seleccione **Sí**.
6. Para cada suscripción deshabilitada, repita los pasos del 3 al 5 hasta que se eliminen todas las suscripciones.

> [!NOTE]
> Si no puede eliminar inmediatamente una suscripción deshabilitada, póngase [en contacto con el soporte técnico](../business-video/get-help-support.md).

## <a name="step-4-disable-multi-factor-authentication"></a>Paso 4: Deshabilitar la autenticación multifactor

1. Inicie sesión en el Centro de administración con una cuenta de administrador global. Para comprobar qué roles tiene, vea [Comprobar roles de administrador en la organización](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).
2. Vaya a la **página Usuarios**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">usuarios activos.</a>
3. Elija **Autenticación multifactor**.
4. En la página autenticación multifactor, deshabilite todas las cuentas excepto la cuenta de administrador global que está usando actualmente.

También puede usar [PowerShell para deshabilitar la autenticación multifactor para varios usuarios.](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell)


## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Paso 5: Eliminar el directorio en Azure Active Directory

1. Inicie sesión en el <a href="https://aad.portal.azure.com/" target="_blank">Centro de administración de Azure AD</a> con una cuenta de administrador global.
2. Seleccione **Azure Active Directory**.
3. Cambie a la organización que desea eliminar.
4. Seleccione **Eliminar inquilino**.
5. Si su organización falla una o más comprobaciones, verá un vínculo a más información sobre cómo pasar las comprobaciones. Después de pasar todas las comprobaciones, **seleccione Eliminar** para completar el proceso.

Después de completar este paso final, la cuenta con Microsoft se cierra y elimina.

## <a name="related-content"></a>Contenido relacionado 

[Comprender la factura o factura de Microsoft 365 para empresas](./billing-and-payments/understand-your-invoice2.md) (artículo)\
[Cancelar la suscripción](./subscriptions/cancel-your-subscription.md) (artículo)

