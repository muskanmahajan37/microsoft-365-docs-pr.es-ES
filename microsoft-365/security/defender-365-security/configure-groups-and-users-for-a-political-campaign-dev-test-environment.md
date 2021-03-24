---
title: 'Configurar grupos y usuarios: desarrollo de campañas políticas/entorno de prueba'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 0e22bcf3-bad3-42a4-b44f-276e0cf4790f
description: 'Resumen: Cree suscripciones de evaluación de Office 365 y Enterprise Mobility + Security (EMS) que incluyan usuarios y grupos en un entorno de desarrollo y prueba para una campaña política.'
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2e21cdfb0aabbdb10397d6d16c879756449a498e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073416"
---
# <a name="configure-groups-and-users-for-a-political-campaign-devtest-environment"></a><span data-ttu-id="001fa-103">Configurar grupos y usuarios en un entorno de desarrollo y prueba de campaña política</span><span class="sxs-lookup"><span data-stu-id="001fa-103">Configure groups and users for a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="001fa-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="001fa-104">**Applies to**</span></span>
- [<span data-ttu-id="001fa-105">Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="001fa-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

 <span data-ttu-id="001fa-106">**Resumen:** Cree suscripciones de evaluación de Office 365 y Enterprise Mobility + Security (EMS) que incluyan usuarios y grupos en un entorno de desarrollo y prueba para una campaña política.</span><span class="sxs-lookup"><span data-stu-id="001fa-106">**Summary:** Create Office 365 and Enterprise Mobility + Security (EMS) trial subscriptions with users and groups for a political campaign dev/test environment.</span></span>

<span data-ttu-id="001fa-107">Siga las instrucciones de este artículo para crear un entorno de desarrollo y prueba que incluya cuentas de usuario simplificadas y grupos para la solución de [Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md).</span><span class="sxs-lookup"><span data-stu-id="001fa-107">Use the instructions in this article to create a dev/test environment that includes simplified user accounts and groups for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution.</span></span>

## <a name="phase-1-create-your-office-365-devtest-environment"></a><span data-ttu-id="001fa-108">Fase 1: Crear el entorno de desarrollo y prueba de Office 365</span><span class="sxs-lookup"><span data-stu-id="001fa-108">Phase 1: Create your Office 365 dev/test environment</span></span>

<span data-ttu-id="001fa-109">En esta fase se obtienen suscripciones de evaluación para Office 365 E5 y Enterprise Mobility + Security (EMS) E5 para una organización ficticia que representa una campaña política.</span><span class="sxs-lookup"><span data-stu-id="001fa-109">In this phase, you obtain trial subscriptions for Office 365 E5 and Enterprise Mobility + Security (EMS) E5 for a fictional organization that represents a political campaign.</span></span>

<span data-ttu-id="001fa-110">Primero, siga las instrucciones en la **Fase 2** de [la configuración de base ligera](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="001fa-110">First, follow the instructions in **Phase 2** of [The lightweight base configuration](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>

<span data-ttu-id="001fa-111">Después, inscríbase en la suscripción de evaluación de EMS E5 y la agregará a la misma organización de la suscripción de evaluación.</span><span class="sxs-lookup"><span data-stu-id="001fa-111">Next, sign up for the EMS E5 trial subscription and add it to the same organization as your trial subscription.</span></span>

1. <span data-ttu-id="001fa-112">Si es necesario, inicie sesión en el centro de administración con las credenciales de la cuenta de administrador global de la suscripción de evaluación.</span><span class="sxs-lookup"><span data-stu-id="001fa-112">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="001fa-113">Para obtener ayuda, consulte [Dónde iniciar sesión](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="001fa-113">For help, see [Where to sign in](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="001fa-114">Haga clic en el icono **Administración**.</span><span class="sxs-lookup"><span data-stu-id="001fa-114">Click the **Admin** tile.</span></span>

3. <span data-ttu-id="001fa-115">En la pestaña del explorador **Centro de administración de Microsoft 365**, situada a la izquierda, haga clic en **Facturación > Servicios de compra**.</span><span class="sxs-lookup"><span data-stu-id="001fa-115">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Billing > Purchase services**.</span></span>

4. <span data-ttu-id="001fa-p102">En la página **Servicios de compra**, busque el elemento **Enterprise Mobility + Security E5**. Mantenga el puntero del mouse sobre ese elemento y haga clic en **Iniciar prueba gratuita**.</span><span class="sxs-lookup"><span data-stu-id="001fa-p102">On the **Purchase services** page, find the **Enterprise Mobility + Security E5** item. Hover your mouse pointer over it and click **Start free trial**.</span></span>

5. <span data-ttu-id="001fa-118">En la página **Confirmar pedido**, haga clic en **Probar ahora**.</span><span class="sxs-lookup"><span data-stu-id="001fa-118">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="001fa-119">En la página **Recibo del pedido**, haga clic en **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="001fa-119">On the **Order receipt** page, click **Continue**.</span></span>

<span data-ttu-id="001fa-120">Después, habilite la licencia de EMS E5 para la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="001fa-120">Next, enable the EMS E5 license for your global administrator account.</span></span>

1. <span data-ttu-id="001fa-121">En la pestaña **Centro de administración de Microsoft 365** del explorador, en el panel de navegación izquierdo, haga clic en **Usuarios > Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="001fa-121">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Users > Active users**.</span></span>

2. <span data-ttu-id="001fa-122">Haga clic en la cuenta de administrador global y, después, en **Editar** para **Licencias de productos**.</span><span class="sxs-lookup"><span data-stu-id="001fa-122">Click your global administrator account, and then click **Edit** for **Product licenses**.</span></span>

3. <span data-ttu-id="001fa-123">En el panel **Licencias de productos**, cambie la licencia del producto de **Enterprise Mobility + Security E5** a **Activada**, seleccione **Guardar** y, después, haga clic en **Cerrar** dos veces.</span><span class="sxs-lookup"><span data-stu-id="001fa-123">On the **Product licenses** pane, turn the product license for **Enterprise Mobility + Security E5** to **On**, click **Save,** and then click **Close** twice.</span></span>

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups"></a><span data-ttu-id="001fa-124">Fase 2: Crear y configurar los grupos de Azure Active Directory (AD)</span><span class="sxs-lookup"><span data-stu-id="001fa-124">Phase 2: Create and configure your Azure Active Directory (AD) groups</span></span>

<span data-ttu-id="001fa-125">En esta fase se crean y configuran los grupos de Azure AD para la campaña.</span><span class="sxs-lookup"><span data-stu-id="001fa-125">In this phase, you create and configure the Azure AD groups for your campaign.</span></span>

<span data-ttu-id="001fa-126">En primer lugar, cree un conjunto de grupos para una campaña política típica en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="001fa-126">First, create a set of groups for a typical political campaign with the Azure portal.</span></span>

1. <span data-ttu-id="001fa-127">En una pestaña aparte en el explorador, ve a Azure Portal en <https://portal.azure.com>.</span><span class="sxs-lookup"><span data-stu-id="001fa-127">On a separate tab in your browser, go to the Azure portal at <https://portal.azure.com>.</span></span> <span data-ttu-id="001fa-128">Si es necesario, inicie sesión con las credenciales de la cuenta de administrador global de la suscripción de evaluación de Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="001fa-128">If needed, sign in with the credentials of the global administrator account for your Office 365 E5 trial subscription.</span></span>

2. <span data-ttu-id="001fa-129">En Azure Portal, haga clic en **Azure Active Directory > Usuarios y grupos > Todos los grupos**.</span><span class="sxs-lookup"><span data-stu-id="001fa-129">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>

3. <span data-ttu-id="001fa-130">Siga estos pasos para cada nombre de grupo de la lista:</span><span class="sxs-lookup"><span data-stu-id="001fa-130">Do the following steps for each group name in this list:</span></span>

   - <span data-ttu-id="001fa-131">Personal directivo y estratégico</span><span class="sxs-lookup"><span data-stu-id="001fa-131">Senior and strategic staff</span></span>

   - <span data-ttu-id="001fa-132">Personal de TI</span><span class="sxs-lookup"><span data-stu-id="001fa-132">IT staff</span></span>

   - <span data-ttu-id="001fa-133">Personal de Análisis</span><span class="sxs-lookup"><span data-stu-id="001fa-133">Analytics staff</span></span>

   - <span data-ttu-id="001fa-134">Personal básico de plantilla</span><span class="sxs-lookup"><span data-stu-id="001fa-134">Regular core staff</span></span>

   - <span data-ttu-id="001fa-135">Personal de Operaciones</span><span class="sxs-lookup"><span data-stu-id="001fa-135">Operations staff</span></span>

   - <span data-ttu-id="001fa-136">Personal de campo</span><span class="sxs-lookup"><span data-stu-id="001fa-136">Field staff</span></span>

1. <span data-ttu-id="001fa-137">En la hoja **Todos los grupos**, haga clic en **+ Nuevo grupo**.</span><span class="sxs-lookup"><span data-stu-id="001fa-137">On the **All groups** blade, click **+ New group**.</span></span>

2. <span data-ttu-id="001fa-138">Escriba el nombre del grupo de la lista en **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="001fa-138">Type the group name from the list in **Name**.</span></span>

3. <span data-ttu-id="001fa-139">Seleccione **Usuario dinámico** en **Pertenencia**.</span><span class="sxs-lookup"><span data-stu-id="001fa-139">Select **Dynamic user** in **Membership**.</span></span>

4. <span data-ttu-id="001fa-140">Haga clic en **Sí** en **¿Quiere habilitar las características de Office?**</span><span class="sxs-lookup"><span data-stu-id="001fa-140">Click **Yes** for **Enable Office features**.</span></span>

5. <span data-ttu-id="001fa-141">Haga clic en **Agregar una consulta dinámica**.</span><span class="sxs-lookup"><span data-stu-id="001fa-141">Click **Add dynamic query**.</span></span>

6. <span data-ttu-id="001fa-142">En **Add users where** (Agregar usuarios donde), seleccione **departamento**.</span><span class="sxs-lookup"><span data-stu-id="001fa-142">In **Add users where**, select **department**.</span></span>

7. <span data-ttu-id="001fa-143">En el siguiente campo, seleccione **Es igual a**.</span><span class="sxs-lookup"><span data-stu-id="001fa-143">In the next field, select **Equals**.</span></span>

8. <span data-ttu-id="001fa-144">En el siguiente campo, escriba el nombre del grupo de la lista.</span><span class="sxs-lookup"><span data-stu-id="001fa-144">In the next field, type the group name from the list.</span></span>

9. <span data-ttu-id="001fa-145">Haga clic en **Agregar consulta** luego en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="001fa-145">Click **Add query**, and then click **Create**.</span></span>

10. <span data-ttu-id="001fa-146">Haga clic en **Users and groups - All groups** (Usuarios y grupos - Todos los grupos).</span><span class="sxs-lookup"><span data-stu-id="001fa-146">Click **Users and groups - All groups**.</span></span>

<span data-ttu-id="001fa-147">Después, configure los grupos para que a los miembros se les asignen automáticamente licencias de Office 365 E5 y EMS E5.</span><span class="sxs-lookup"><span data-stu-id="001fa-147">Next, you configure the groups so that members are automatically assigned Office 365 E5 and EMS E5 licenses.</span></span>

1. <span data-ttu-id="001fa-148">En Azure Portal, haga clic en **Azure Active Directory > Licencias > Todos los productos**.</span><span class="sxs-lookup"><span data-stu-id="001fa-148">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>

2. <span data-ttu-id="001fa-149">En la lista, seleccione **Enterprise Mobility + Security E5** y **Office 365 Enterprise E5** y haga clic en **+ Asignar**.</span><span class="sxs-lookup"><span data-stu-id="001fa-149">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **+ Assign**.</span></span>

3. <span data-ttu-id="001fa-150">En la hoja **Asignar licencia**, haga clic en **Usuarios y grupos**.</span><span class="sxs-lookup"><span data-stu-id="001fa-150">In the **Assign license** blade, click **Users and groups**.</span></span>

4. <span data-ttu-id="001fa-151">En la lista de grupos, seleccione los siguientes:</span><span class="sxs-lookup"><span data-stu-id="001fa-151">In the list of groups, select the following:</span></span>

   - <span data-ttu-id="001fa-152">Personal de Análisis</span><span class="sxs-lookup"><span data-stu-id="001fa-152">Analytics staff</span></span>

   - <span data-ttu-id="001fa-153">Personal de campo</span><span class="sxs-lookup"><span data-stu-id="001fa-153">Field staff</span></span>

   - <span data-ttu-id="001fa-154">Personal de TI</span><span class="sxs-lookup"><span data-stu-id="001fa-154">IT staff</span></span>

   - <span data-ttu-id="001fa-155">Personal de Operaciones</span><span class="sxs-lookup"><span data-stu-id="001fa-155">Operations staff</span></span>

   - <span data-ttu-id="001fa-156">Personal básico de plantilla</span><span class="sxs-lookup"><span data-stu-id="001fa-156">Regular core staff</span></span>

   - <span data-ttu-id="001fa-157">Personal directivo y estratégico</span><span class="sxs-lookup"><span data-stu-id="001fa-157">Senior and strategic staff</span></span>

5. <span data-ttu-id="001fa-158">Haga clic en **Seleccionar** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="001fa-158">Click **Select**, and then click **Assign**.</span></span>

6. <span data-ttu-id="001fa-159">Cierre la pestaña Azure Portal del explorador.</span><span class="sxs-lookup"><span data-stu-id="001fa-159">Close the Azure portal tab in your browser.</span></span>

## <a name="phase-3-add-your-user-accounts"></a><span data-ttu-id="001fa-160">Fase 3: Agregar las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="001fa-160">Phase 3: Add your user accounts</span></span>

<span data-ttu-id="001fa-161">En esta fase se agregan las cuentas de usuario de ejemplo para la campaña política.</span><span class="sxs-lookup"><span data-stu-id="001fa-161">In this phase, you add the example user accounts for your political campaign.</span></span>

<span data-ttu-id="001fa-162">Primero, [Conéctese al módulo de PowerShell de Azure Active Directory para Graph](../../enterprise/connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="001fa-162">First, you [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="001fa-163">Después, rellene el nombre de la organización, su ubicación y una contraseña común y, luego, ejecute estos comandos en el entorno de script integrado (ISE) o el símbolo del sistema de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="001fa-163">Next, you fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE):</span></span>

```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$deptName="Senior and strategic staff"
$userNames=@("Candidate","ChiefOfStaff","Strategic1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Analytics staff"
$userNames=@("DataScientist1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Regular core staff"
$userNames=@("Regular1","Regular2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Operations staff"
$userNames=@("Operations1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Field staff"
$userNames=@("FieldConsultant1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
```

> [!IMPORTANT]
> <span data-ttu-id="001fa-p104">Se usa una contraseña común para automatizar y facilitar la configuración de un entorno de desarrollo y prueba. Nos se recomienda hacerlo con suscripciones de producción. Cuando inicie sesión con cada una de estas nuevas cuentas de usuario, se le pedirá que cambie la contraseña.</span><span class="sxs-lookup"><span data-stu-id="001fa-p104">The use of a common password here is for automation and ease of configuration for a dev/test environment. This is not recommended for production subscriptions. As you sign in with each of these new user accounts, you will be prompted to change the password.</span></span>

<span data-ttu-id="001fa-167">Siga estos pasos para comprobar que las licencias basadas en grupos y la pertenencia dinámica a grupos funcionan correctamente.</span><span class="sxs-lookup"><span data-stu-id="001fa-167">Use these steps to verify that dynamic group membership and group-based licensing are working correctly.</span></span>

1. <span data-ttu-id="001fa-168">En la pestaña **Inicio de Microsoft Office** del explorador, haga clic en el icono **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="001fa-168">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>

2. <span data-ttu-id="001fa-169">En la nueva pestaña **Centro de administración de Microsoft 365** del explorador, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="001fa-169">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>

3. <span data-ttu-id="001fa-170">En la lista de usuarios, haga clic en **Candidato**.</span><span class="sxs-lookup"><span data-stu-id="001fa-170">In the list of users, click **Candidate**.</span></span>

4. <span data-ttu-id="001fa-171">En el panel que muestra las propiedades de la cuenta de usuario **Candidato**, compruebe que:</span><span class="sxs-lookup"><span data-stu-id="001fa-171">In the pane that lists the properties of the **Candidate** user account, verify that:</span></span>

   - <span data-ttu-id="001fa-172">Es un miembro del grupo **Personal directivo y estratégico** (en **Pertenencia a grupos**).</span><span class="sxs-lookup"><span data-stu-id="001fa-172">It is a member of the **Senior and strategic staff** group (in **Group memberships**).</span></span>

   - <span data-ttu-id="001fa-173">Se le han asignado las licencias de **Enterprise Mobility + Security E5** y **Office 365 Enterprise E5** (en **Licencias de productos**).</span><span class="sxs-lookup"><span data-stu-id="001fa-173">It has been assigned the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses (in **Product licenses**).</span></span>

5. <span data-ttu-id="001fa-174">Cierre el panel de la cuenta de usuario **Candidato**.</span><span class="sxs-lookup"><span data-stu-id="001fa-174">Close the **Candidate** user account pane.</span></span>

## <a name="record-values-for-future-reference"></a><span data-ttu-id="001fa-175">Registrar valores para referencia futura</span><span class="sxs-lookup"><span data-stu-id="001fa-175">Record values for future reference</span></span>

<span data-ttu-id="001fa-176">Registre estos valores para trabajar con las suscripciones de prueba de Office 365 y EMS en este entorno de desarrollo y pruebas:</span><span class="sxs-lookup"><span data-stu-id="001fa-176">Record these values for working with the Office 365 and EMS trial subscriptions for this dev/test environment:</span></span>

- <span data-ttu-id="001fa-177">Nombre de la organización de la suscripción de prueba:</span><span class="sxs-lookup"><span data-stu-id="001fa-177">Your trial subscription organization name:</span></span> ![Subrayado](../../media/Common-Images/TableLine.png)

  <span data-ttu-id="001fa-179">Por ejemplo, en el nombre de dominio de la suscripción de prueba de contoso.onmicrosoft.com, el nombre de la organización es “contoso”.</span><span class="sxs-lookup"><span data-stu-id="001fa-179">For example, for the trial subscription domain name of contoso.onmicrosoft.com, the organization name is "contoso".</span></span>

- <span data-ttu-id="001fa-180">El nombre del administrador global:</span><span class="sxs-lookup"><span data-stu-id="001fa-180">The global administrator name:</span></span> ![Subrayado](../../media/Common-Images/TableLine.png)<span data-ttu-id="001fa-182">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="001fa-182">.onmicrosoft.com</span></span>

  <span data-ttu-id="001fa-183">Registre la contraseña de esta cuenta y la contraseña inicial común de las demás cuentas de usuario en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="001fa-183">Record the password for this account and the common initial password for the other user accounts in a secure location.</span></span>

## <a name="next-step"></a><span data-ttu-id="001fa-184">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="001fa-184">Next step</span></span>

<span data-ttu-id="001fa-185">Cree los cuatro tipos distintos de sitios de grupo de SharePoint Online en este entorno de desarrollo y pruebas con [Crear sitios de grupo en un entorno de desarrollo y prueba de campaña política](create-team-sites-in-a-political-campaign-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="001fa-185">Build the four different types of SharePoint Online team sites in this dev/test environment with [Create team sites in a political campaign dev/test environment](create-team-sites-in-a-political-campaign-dev-test-environment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="001fa-186">Vea también</span><span class="sxs-lookup"><span data-stu-id="001fa-186">See also</span></span>

[<span data-ttu-id="001fa-187">Guía de seguridad de Microsoft para campañas políticas, ONG y otras organizaciones ágiles</span><span class="sxs-lookup"><span data-stu-id="001fa-187">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="001fa-188">Crear sitios de grupo en un entorno de desarrollo y prueba de campaña política</span><span class="sxs-lookup"><span data-stu-id="001fa-188">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="001fa-189">Guías del entorno de pruebas de adopción de la nube (TLG)</span><span class="sxs-lookup"><span data-stu-id="001fa-189">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="001fa-190">Adopción de la nube y soluciones híbridas</span><span class="sxs-lookup"><span data-stu-id="001fa-190">Cloud adoption and hybrid solutions</span></span>](/office365/enterprise/cloud-adoption-and-hybrid-solutions)