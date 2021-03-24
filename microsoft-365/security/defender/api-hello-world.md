---
title: Hello World para api de REST de Microsoft 365 Defender
description: Obtenga información sobre cómo crear una aplicación y usar un token para obtener acceso a las API de Microsoft 365 Defender
keywords: app, token, access, aad, app, application registration, powershell, script, global administrator, permission, microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ffdcf91da6b5def7d63e5fdb8ff51ddbdb1ec550
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072755"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="a1595-104">Hello World para api de REST de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1595-104">Hello World for Microsoft 365 Defender REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a1595-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a1595-105">**Applies to:**</span></span>

- <span data-ttu-id="a1595-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1595-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1595-107">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="a1595-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a1595-108">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="a1595-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="a1595-109">Obtener incidentes con un script de PowerShell simple</span><span class="sxs-lookup"><span data-stu-id="a1595-109">Get incidents using a simple PowerShell script</span></span>

<span data-ttu-id="a1595-110">Este proyecto debe tardar entre 5 y 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="a1595-110">It should take 5 to 10 minutes to complete this project.</span></span> <span data-ttu-id="a1595-111">Esta estimación de tiempo incluye registrar la aplicación y aplicar el código desde el script de ejemplo de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a1595-111">This time estimate includes registering the application, and applying the code from the PowerShell sample script.</span></span>

### <a name="register-an-app-in-azure-active-directory"></a><span data-ttu-id="a1595-112">Registrar una aplicación en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a1595-112">Register an app in Azure Active Directory</span></span>

1. <span data-ttu-id="a1595-113">Inicie sesión en [Azure](https://portal.azure.com) como usuario con el **rol De administrador** global.</span><span class="sxs-lookup"><span data-stu-id="a1595-113">Sign in to [Azure](https://portal.azure.com) as a user with the **Global administrator** role.</span></span>

2. <span data-ttu-id="a1595-114">Vaya a **Azure Active Directory** App  >  **registrations** New  >  **registration**.</span><span class="sxs-lookup"><span data-stu-id="a1595-114">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Imagen de Microsoft Azure y navegación al registro de aplicaciones](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="a1595-116">En el formulario de registro, elija un nombre para la aplicación y, a continuación, **seleccione Registrar**.</span><span class="sxs-lookup"><span data-stu-id="a1595-116">In the registration form, choose a name for your application, then select **Register**.</span></span> <span data-ttu-id="a1595-117">Seleccionar un URI de redireccionamiento es opcional.</span><span class="sxs-lookup"><span data-stu-id="a1595-117">Selecting a redirect URI is optional.</span></span> <span data-ttu-id="a1595-118">No necesitará uno para completar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a1595-118">You won't need one to complete this example.</span></span>

4. <span data-ttu-id="a1595-119">En la página de la aplicación, seleccione **Permisos** de API Agregar API de permisos que mi organización usa  >    >   >, escriba Protección contra amenazas de Microsoft y seleccione **Protección contra** amenazas de Microsoft .</span><span class="sxs-lookup"><span data-stu-id="a1595-119">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="a1595-120">La aplicación ahora puede acceder a Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="a1595-120">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="a1595-121">*Microsoft Threat Protection* es un nombre antiguo de Microsoft 365 Defender y no aparecerá en la lista original.</span><span class="sxs-lookup"><span data-stu-id="a1595-121">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="a1595-122">Debe empezar a escribir su nombre en el cuadro de texto para verlo aparecer.</span><span class="sxs-lookup"><span data-stu-id="a1595-122">You need to start writing its name in the text box to see it appear.</span></span>
   <span data-ttu-id="a1595-123">![Imagen de selección de permisos de API](../../media/apis-in-my-org-tab.PNG)</span><span class="sxs-lookup"><span data-stu-id="a1595-123">![Image of API permission selection](../../media/apis-in-my-org-tab.PNG)</span></span>

   - <span data-ttu-id="a1595-124">Elija **Permisos de aplicación**  >  **Incident.Read.All** y seleccione Agregar **permisos**.</span><span class="sxs-lookup"><span data-stu-id="a1595-124">Choose **Application permissions** > **Incident.Read.All** and select **Add permissions**.</span></span>

   ![Imagen de acceso a api y selección de API](../../media/request-api-permissions.PNG)

5. <span data-ttu-id="a1595-126">Seleccione **Conceder consentimiento de administrador**.</span><span class="sxs-lookup"><span data-stu-id="a1595-126">Select **Grant admin consent**.</span></span> <span data-ttu-id="a1595-127">Cada vez que agregue un permiso, debe seleccionar Conceder consentimiento **de administrador** para que su efecto.</span><span class="sxs-lookup"><span data-stu-id="a1595-127">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Imagen de concesión de permisos](../../media/grant-consent.PNG)

6. <span data-ttu-id="a1595-129">Agregue un secreto a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1595-129">Add a secret to the application.</span></span> <span data-ttu-id="a1595-130">Seleccione **Certificados & secretos,** agregue una descripción al secreto y, a continuación, **seleccione Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a1595-130">Select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="a1595-131">Después de seleccionar **Agregar**, seleccione **copiar el valor secreto generado**.</span><span class="sxs-lookup"><span data-stu-id="a1595-131">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="a1595-132">No podrá recuperar el valor secreto después de salir.</span><span class="sxs-lookup"><span data-stu-id="a1595-132">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Imagen de crear clave de aplicación](../../media/webapp-create-key2.png)

7. <span data-ttu-id="a1595-134">Registre el identificador de la aplicación y el identificador de inquilino en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="a1595-134">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="a1595-135">Aparecen en Información **general en** la página de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1595-135">They're listed under **Overview** on your application page.</span></span>

   ![Imagen del identificador de aplicación creado](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a><span data-ttu-id="a1595-137">Obtener un token con la aplicación y usar el token para obtener acceso a la API</span><span class="sxs-lookup"><span data-stu-id="a1595-137">Get a token using the app and use the token to access the API</span></span>

<span data-ttu-id="a1595-138">Para obtener más información sobre los tokens de Azure Active Directory, consulte el [tutorial de Azure AD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="a1595-138">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1595-139">Aunque el ejemplo de esta aplicación de demostración te anima a  pegar el valor secreto con fines de prueba, nunca debes codificar los secretos en una aplicación que se ejecute en producción.</span><span class="sxs-lookup"><span data-stu-id="a1595-139">Although the example in this demo app encourage you to paste in your secret value for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="a1595-140">Un tercero podría usar el secreto para obtener acceso a los recursos.</span><span class="sxs-lookup"><span data-stu-id="a1595-140">A third party could use your secret to access resources.</span></span> <span data-ttu-id="a1595-141">Puedes ayudar a proteger los secretos de la aplicación con [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span><span class="sxs-lookup"><span data-stu-id="a1595-141">You can help keep your app's secrets secure by using [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="a1595-142">Para obtener un ejemplo práctico de cómo proteger la aplicación, consulta Administrar secretos en las aplicaciones de servidor [con Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span><span class="sxs-lookup"><span data-stu-id="a1595-142">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

1. <span data-ttu-id="a1595-143">Copie el script siguiente y péguelo en el editor de texto favorito.</span><span class="sxs-lookup"><span data-stu-id="a1595-143">Copy the script below and paste it into your favorite text editor.</span></span> <span data-ttu-id="a1595-144">Guardar como **Get-Token.ps1**.</span><span class="sxs-lookup"><span data-stu-id="a1595-144">Save as **Get-Token.ps1**.</span></span> <span data-ttu-id="a1595-145">También puede ejecutar el código tal como está en PowerShell ISE, pero debe guardarlo, ya que tendremos que volver a ejecutarlo cuando usemos el script de captura de incidentes en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="a1595-145">You can also run the code as-is in PowerShell ISE, but you should save it, because we'll need to run it again when we use the incident-fetching script in the next section.</span></span>

    <span data-ttu-id="a1595-146">Este script generará un token y lo guardará en la carpeta de trabajo bajo el nombre, *Latest-token.txt*.</span><span class="sxs-lookup"><span data-stu-id="a1595-146">This script will generate a token and save it in the working folder under the name, *Latest-token.txt*.</span></span>

    ```PowerShell
    # This script gets the app context token and saves it to a file named "Latest-token.txt" under the current directory.
    # Paste in your tenant ID, client ID and app secret (App key).

    $tenantId = '' # Paste your directory (tenant) ID here
    $clientId = '' # Paste your application (client) ID here
    $appSecret = '' # # Paste your own app secret here to test, then store it in a safe place!

    $resourceAppIdUri = 'https://api.security.microsoft.com'
    $oAuthUri = "https://login.windows.net/$tenantId/oauth2/token"
    $authBody = [Ordered] @{
      resource = $resourceAppIdUri
      client_id = $clientId
      client_secret = $appSecret
      grant_type = 'client_credentials'
    }
    $authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
    $token = $authResponse.access_token
    Out-File -FilePath "./Latest-token.txt" -InputObject $token
    return $token
    ```

#### <a name="validate-the-token"></a><span data-ttu-id="a1595-147">Validar el token</span><span class="sxs-lookup"><span data-stu-id="a1595-147">Validate the token</span></span>

1. <span data-ttu-id="a1595-148">Copie y pegue el token que recibió en [JWT](https://jwt.ms) para descodificarlo.</span><span class="sxs-lookup"><span data-stu-id="a1595-148">Copy and paste the token you received into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="a1595-149">*JWT* significa *token web JSON*.</span><span class="sxs-lookup"><span data-stu-id="a1595-149">*JWT* stands for *JSON Web Token*.</span></span> <span data-ttu-id="a1595-150">El token descodificado contendrá una serie de notificaciones o elementos con formato JSON.</span><span class="sxs-lookup"><span data-stu-id="a1595-150">The decoded token will contain a number of JSON-formatted items or claims.</span></span> <span data-ttu-id="a1595-151">Asegúrese de que la notificación *de roles* dentro del token descodificado contiene los permisos deseados.</span><span class="sxs-lookup"><span data-stu-id="a1595-151">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

    <span data-ttu-id="a1595-152">En la siguiente imagen, puedes ver un token descodificado adquirido desde una aplicación, con ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` y ```AdvancedHunting.Read.All``` permisos:</span><span class="sxs-lookup"><span data-stu-id="a1595-152">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

    ![Imagen jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a><span data-ttu-id="a1595-154">Obtener una lista de incidentes recientes</span><span class="sxs-lookup"><span data-stu-id="a1595-154">Get a list of recent incidents</span></span>

<span data-ttu-id="a1595-155">El script siguiente **usará** Get-Token.ps1para obtener acceso a la API.</span><span class="sxs-lookup"><span data-stu-id="a1595-155">The script below will use **Get-Token.ps1** to access the API.</span></span> <span data-ttu-id="a1595-156">A continuación, recupera una lista de incidentes que se actualizaron por última vez en las últimas 48 horas y guarda la lista como un archivo JSON.</span><span class="sxs-lookup"><span data-stu-id="a1595-156">It then retrieves a list of incidents that were last updated within the past 48 hours, and saves the list as a JSON file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1595-157">Guarde este script en la misma carpeta que **guardóGet-Token.ps1**.</span><span class="sxs-lookup"><span data-stu-id="a1595-157">Save this script in the same folder you saved **Get-Token.ps1**.</span></span>

```PowerShell
# This script returns incidents last updated within the past 48 hours.

$token = ./Get-Token.ps1

# Get incidents from the past 48 hours.
# The script may appear to fail if you don't have any incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# This URL contains the type of query and the time filter we created above.
# Note that `$filter` does not refer to a local variable in our script --
# it's actually an OData operator and part of the API's syntax.
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the webrequest headers
$headers = @{
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the request and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results.
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get a string containing the execution time. We concatenate that string to the name 
# of the output file to avoid overwriting the file on consecutive runs of the script.
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"

Out-File -FilePath $outputJsonPath -InputObject $incidents
```

<span data-ttu-id="a1595-158">¡Ya ha terminado!</span><span class="sxs-lookup"><span data-stu-id="a1595-158">You're all done!</span></span> <span data-ttu-id="a1595-159">Ha realizado correctamente lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a1595-159">You've successfully:</span></span>

- <span data-ttu-id="a1595-160">Creó y registró una aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1595-160">Created and registered an application.</span></span>
- <span data-ttu-id="a1595-161">Se ha concedido permiso para que esa aplicación lea alertas.</span><span class="sxs-lookup"><span data-stu-id="a1595-161">Granted permission for that application to read alerts.</span></span>
- <span data-ttu-id="a1595-162">Conectado a la API.</span><span class="sxs-lookup"><span data-stu-id="a1595-162">Connected to the API.</span></span>
- <span data-ttu-id="a1595-163">Se usó un script de PowerShell para devolver incidentes actualizados en las últimas 48 horas.</span><span class="sxs-lookup"><span data-stu-id="a1595-163">Used a PowerShell script to return incidents updated in the past 48 hours.</span></span>

## <a name="related-articles"></a><span data-ttu-id="a1595-164">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="a1595-164">Related articles</span></span>

- [<span data-ttu-id="a1595-165">Introducción a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1595-165">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="a1595-166">Obtener acceso a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1595-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="a1595-167">Crear una aplicación para tener acceso a Microsoft 365 Defender sin un usuario</span><span class="sxs-lookup"><span data-stu-id="a1595-167">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="a1595-168">Crear una aplicación para tener acceso a las API de Microsoft 365 Defender en nombre de un usuario</span><span class="sxs-lookup"><span data-stu-id="a1595-168">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="a1595-169">Crear una aplicación con acceso de asociado multiinquilino a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1595-169">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="a1595-170">Administrar secretos en las aplicaciones de servidor con Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="a1595-170">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="a1595-171">Autorización de OAuth 2.0 para el inicio de sesión de usuario y el acceso a la API</span><span class="sxs-lookup"><span data-stu-id="a1595-171">OAuth 2.0 Authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)