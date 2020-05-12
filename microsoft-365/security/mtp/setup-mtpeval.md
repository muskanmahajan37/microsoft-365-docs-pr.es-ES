---
title: Configurar el entorno de laboratorio de prueba de Microsoft Threat Protection
description: Obtener acceso al centro de seguridad 365 de Microsoft después de configurar el entorno de laboratorio de prueba de Microsoft Threat Protection
keywords: Instalación de prueba de Microsoft Threat Protection, pruebe Microsoft Threat Protection, instalación del laboratorio de evaluación de la protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 50557b0824999f0220af4d12b906b0274db4471e
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049620"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="7b7a5-104">Configurar el entorno de laboratorio de prueba de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7b7a5-104">Set up your Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="7b7a5-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7b7a5-105">**Applies to:**</span></span>
- <span data-ttu-id="7b7a5-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7b7a5-106">Microsoft Threat Protection</span></span> 


<span data-ttu-id="7b7a5-107">La creación de un entorno de laboratorio de prueba de Microsoft Threat Protection y su implementación es un proceso de tres fases:</span><span class="sxs-lookup"><span data-stu-id="7b7a5-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Preparar el laboratorio de evaluación de Microsoft Threat Protection" />
      <br/><span data-ttu-id="7b7a5-109">Fase 1: preparación</a></span><span class="sxs-lookup"><span data-stu-id="7b7a5-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Configurar el laboratorio de evaluación de Microsoft Threat Protection" />
      <br/><span data-ttu-id="7b7a5-111">Fase 2: configuración</a></span><span class="sxs-lookup"><span data-stu-id="7b7a5-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
Configurar cada pilar de protección contra amenazas de Microsoft para el entorno de prueba de la protección contra amenazas de Microsoft y incorporar los puntos de conexión" />
      <br/><span data-ttu-id="7b7a5-113">Fase 3: configurar & incorporado</a></span><span class="sxs-lookup"><span data-stu-id="7b7a5-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="7b7a5-114">Actualmente se encuentra en la fase de configuración.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-114">You are currently in the set up phase.</span></span> <span data-ttu-id="7b7a5-115">Realice los pasos iniciales para acceder al centro de seguridad 365 de Microsoft y, a continuación, configure el entorno de laboratorio de prueba.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-115">Take the initial steps to access Microsoft 365 Security Center then setup your trial lab environment.</span></span>

<span data-ttu-id="7b7a5-116">Regístrese para obtener una suscripción de Office 365 o Azure Active Directory para generar un inquilino *. onmicrosoft.com* que puede usar para registrarse en su licencia de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-116">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="7b7a5-117">Si ya tiene una suscripción a Office 365 o Azure Active Directory existente, puede omitir los pasos de creación de inquilinos de prueba de Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-117">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

<span data-ttu-id="7b7a5-118">En esta fase, se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="7b7a5-118">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="7b7a5-119">Crear un inquilino de prueba de Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="7b7a5-119">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="7b7a5-120">Habilitar la suscripción de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b7a5-120">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="7b7a5-121">Crear un inquilino de prueba de Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="7b7a5-121">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="7b7a5-122">Si ya tiene una suscripción a Office 365 o Azure Active Directory existente, puede omitir los pasos de creación de inquilinos de prueba de Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-122">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="7b7a5-123">Vaya al [portal de producto de Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) y seleccione **prueba gratuita**.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-123">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>
<span data-ttu-id="7b7a5-124">![Of_page de imagen](../../media/mtp-eval-9.png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-124">![Image of_page](../../media/mtp-eval-9.png)</span></span> <br>
  
2. <span data-ttu-id="7b7a5-125">Para completar el registro de prueba, escriba su dirección de correo electrónico (personal o Corporate).</span><span class="sxs-lookup"><span data-stu-id="7b7a5-125">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="7b7a5-126">Haga clic en **configurar cuenta**.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-126">Click **Set up account**.</span></span>
<span data-ttu-id="7b7a5-127">![Of_page de imagen](../../media/mtp-eval-10.png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-127">![Image of_page](../../media/mtp-eval-10.png)</span></span> <br> 

3. <span data-ttu-id="7b7a5-128">Escriba su nombre, apellidos, número de teléfono del trabajo, nombre de la compañía, tamaño de la compañía y país o región.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-128">Fill in your first name, last name, business phone number, company name, company size and country or region.</span></span>  
<br>![Of_page de imagen](../../media/mtp-eval-11.png) <br>
>[!NOTE]
><span data-ttu-id="7b7a5-130">El país o la región que establezca aquí determina la región del centro de datos donde se hospedará Office 365.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-130">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="7b7a5-131">Elija su preferencia de comprobación: mediante un mensaje de texto o una llamada.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-131">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="7b7a5-132">Haga clic en **Enviar código de verificación**.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-132">Click **Send Verification Code**.</span></span> 
<span data-ttu-id="7b7a5-133">![Of_page de imagen](../../media/mtp-eval-12.png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-133">![Image of_page](../../media/mtp-eval-12.png)</span></span> <br>

5. <span data-ttu-id="7b7a5-134">Establezca el nombre de dominio personalizado para el inquilino y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-134">Set the custom domain name for your tenant, then click **Next**.</span></span>
<br><span data-ttu-id="7b7a5-135">![Of_page de imagen](../../media/mtp-eval-13.png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-135">![Image of_page](../../media/mtp-eval-13.png)</span></span> <br>
 
6. <span data-ttu-id="7b7a5-136">Configure la primera identidad que será un administrador global del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-136">Set up the first identity which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="7b7a5-137">Escriba un **nombre** y una **contraseña**.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-137">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="7b7a5-138">Haga clic en **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-138">Click **Sign up**.</span></span>
<span data-ttu-id="7b7a5-139">![Of_page de imagen](../../media/mtp-eval-14.png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-139">![Image of_page](../../media/mtp-eval-14.png)</span></span> <br>
<span data-ttu-id="7b7a5-140">c</span><span class="sxs-lookup"><span data-stu-id="7b7a5-140">c</span></span>
7. <span data-ttu-id="7b7a5-141">Haga clic en **ir al programa de instalación** para completar el aprovisionamiento de inquilino de prueba de Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-141">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>
<br><span data-ttu-id="7b7a5-142">![Of_page de imagen](../../media/mtp-eval-15.png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-142">![Image of_page](../../media/mtp-eval-15.png)</span></span> <br>

8. <span data-ttu-id="7b7a5-143">Conecte el dominio corporativo al inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-143">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="7b7a5-144">Opcional Elija **conectar un dominio que ya posee** y escriba el nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-144">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="7b7a5-145">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-145">Click **Next**.</span></span>
<br><span data-ttu-id="7b7a5-146">![Of_page de imagen](../../media/mtp-eval-16.png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-146">![Image of_page](../../media/mtp-eval-16.png)</span></span> <br>
 
9. <span data-ttu-id="7b7a5-147">Tendrá que agregar un registro TXT o MX para validar la propiedad del dominio.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-147">You will need to add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="7b7a5-148">Una vez que haya agregado el registro TXT o MX a su dominio, seleccione **comprobar**.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-148">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>
<br><span data-ttu-id="7b7a5-149">![Of_page de imagen](../../media/mtp-eval-17.png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-149">![Image of_page](../../media/mtp-eval-17.png)</span></span> <br>
 
10. <span data-ttu-id="7b7a5-150">Opcional Cree más cuentas de usuario para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-150">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="7b7a5-151">Puede omitir este paso haciendo clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-151">You can skip this step by clicking **Next**.</span></span>
<span data-ttu-id="7b7a5-152">![Of_page de imagen](../../media/mtp-eval-18.png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-152">![Image of_page](../../media/mtp-eval-18.png)</span></span> <br>
 
11. <span data-ttu-id="7b7a5-153">Opcional Descargue las aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-153">[Optional] Download Office apps.</span></span> <span data-ttu-id="7b7a5-154">Haga clic en **siguiente** para omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-154">Click **Next** to skip this step.</span></span> 
<br><span data-ttu-id="7b7a5-155">![Of_page de imagen](../../media/mtp-eval-19.png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-155">![Image of_page](../../media/mtp-eval-19.png)</span></span> <br>

12. <span data-ttu-id="7b7a5-156">Opcional Migrar mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-156">[Optional] Migrate email messages.</span></span> <span data-ttu-id="7b7a5-157">De nuevo, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-157">Again, you can skip this step.</span></span>
<br><span data-ttu-id="7b7a5-158">![Of_page de imagen](../../media/mtp-eval-20.png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-158">![Image of_page](../../media/mtp-eval-20.png)</span></span> <br>
 
13. <span data-ttu-id="7b7a5-159">Elija servicios en línea.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-159">Choose online services.</span></span> <span data-ttu-id="7b7a5-160">Seleccione **Exchange** y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-160">Select **Exchange** and click **Next**.</span></span> 
<br><span data-ttu-id="7b7a5-161">![Of_page de imagen](../../media/mtp-eval-21.png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-161">![Image of_page](../../media/mtp-eval-21.png)</span></span> <br>

14. <span data-ttu-id="7b7a5-162">Agregue los registros MX, CNAME y TXT a su dominio.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-162">Add MX, CNAME and TXT records to your domain.</span></span> <span data-ttu-id="7b7a5-163">Una vez completada, seleccione **comprobar**.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-163">When completed, select **Verify**.</span></span>
<br><span data-ttu-id="7b7a5-164">![Of_page de imagen](../../media/mtp-eval-22.png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-164">![Image of_page](../../media/mtp-eval-22.png)</span></span> <br>
 
15. <span data-ttu-id="7b7a5-165">Enhorabuena, ha completado el aprovisionamiento de su inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-165">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>
<br><span data-ttu-id="7b7a5-166">![Of_page de imagen](../../media/mtp-eval-23.png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-166">![Image of_page](../../media/mtp-eval-23.png)</span></span> <br>

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="7b7a5-167">Habilitar la suscripción de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b7a5-167">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="7b7a5-168">Al registrarse para obtener una prueba, se le da 25 licencias de usuario para usarla durante un mes.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-168">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="7b7a5-169">Consulte [probar o comprar una suscripción a M365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-169">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="7b7a5-170">En [centro de administración de 365 de Microsoft](https://admin.microsoft.com/), haga clic en **facturación** y navegue a **servicios de compra**.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-170">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="7b7a5-171">Seleccione **Microsoft 365 E5** y haga clic en **iniciar prueba gratuita**.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-171">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 
<span data-ttu-id="7b7a5-172">![Of_page de imagen](../../media/mtp-eval-24.png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-172">![Image of_page](../../media/mtp-eval-24.png)</span></span> <br>

3. <span data-ttu-id="7b7a5-173">Elija su preferencia de comprobación: mediante un mensaje de texto o una llamada.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-173">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="7b7a5-174">Una vez que haya decidido, escriba el número de teléfono, seleccione **texto me** o **llámeme** en función de la selección.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-174">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>
<span data-ttu-id="7b7a5-175">![Of_page de imagen](../../media/mtp-eval-25.png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-175">![Image of_page](../../media/mtp-eval-25.png)</span></span> <br>
 
4. <span data-ttu-id="7b7a5-176">Escriba el código de verificación y haga clic en **iniciar la versión de prueba gratuita**.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-176">Enter the verification code and click **Start your free trial**.</span></span> 
<br><span data-ttu-id="7b7a5-177">![Of_page de imagen](../../media/mtp-eval-26.png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-177">![Image of_page](../../media/mtp-eval-26.png)</span></span> <br>

5. <span data-ttu-id="7b7a5-178">Haga clic en **probar ahora** para confirmar la prueba de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-178">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>
<br><span data-ttu-id="7b7a5-179">![Of_page de imagen](../../media/mtp-eval-27.png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-179">![Image of_page](../../media/mtp-eval-27.png)</span></span> <br>
 
6. <span data-ttu-id="7b7a5-180">Vaya a**los usuarios** > **activos**del **Centro** > de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-180">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="7b7a5-181">Seleccione su cuenta de usuario, seleccione **administrar licencias de producto**y, a continuación, intercambie la licencia de Office 365 E5 a **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-181">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="7b7a5-182">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-182">Click **Save**.</span></span>
<span data-ttu-id="7b7a5-183">![Of_page de imagen](../../media/mtp-eval-28.png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-183">![Image of_page](../../media/mtp-eval-28.png)</span></span> <br>
 
7. <span data-ttu-id="7b7a5-184">Seleccione la cuenta de administrador global de nuevo y haga clic en **administrar nombre de usuario**.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-184">Select the global administrator account again then click **Manage username**.</span></span>
<br><span data-ttu-id="7b7a5-185">![Of_page de imagen](../../media/mtp-eval-29.png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-185">![Image of_page](../../media/mtp-eval-29.png)</span></span> <br>

8. <span data-ttu-id="7b7a5-186">Opcional Cambie el dominio de *onmicrosoft.com* a su propio dominio, en función de lo que elija en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-186">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="7b7a5-187">Haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-187">Click **Save changes**.</span></span>
<br><span data-ttu-id="7b7a5-188">![Of_page de imagen](../../media/mtp-eval-30.png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-188">![Image of_page](../../media/mtp-eval-30.png)</span></span> <br>



## <a name="next-step"></a><span data-ttu-id="7b7a5-189">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="7b7a5-189">Next step</span></span>
<span data-ttu-id="7b7a5-190">||| |:-------|:-----| config-onboard. png)</span><span class="sxs-lookup"><span data-stu-id="7b7a5-190">||| |:-------|:-----|config-onboard.png)</span></span> <br><span data-ttu-id="7b7a5-191">[Fase 3: configuración & incorporada](config-mtpeval.md) | Configure cada pilar de protección contra amenazas de Microsoft para el entorno de prueba de la protección contra amenazas de Microsoft y incorpore los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="7b7a5-191">[Phase 3: Configure & Onboard](config-mtpeval.md) | Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints.</span></span>