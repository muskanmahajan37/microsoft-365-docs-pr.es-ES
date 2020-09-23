---
title: Acceso a las API de Microsoft Threat Protection
description: Obtenga información sobre cómo acceder a las API de Microsoft Threat Protection
keywords: acceso, API, contexto de aplicación, contexto de usuario, aplicación AAD, token de acceso
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bccf36f46121caceeb6dc6d97c126f48149d9426
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197886"
---
# <a name="access-the-microsoft-threat-protection-apis"></a><span data-ttu-id="f1137-104">Acceso a las API de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f1137-104">Access the Microsoft Threat Protection APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f1137-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f1137-105">**Applies to:**</span></span>
- <span data-ttu-id="f1137-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="f1137-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="f1137-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="f1137-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f1137-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="f1137-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


 <span data-ttu-id="f1137-109">Microsoft Threat Protection expone gran parte de sus datos y acciones a través de un conjunto de API de programación.</span><span class="sxs-lookup"><span data-stu-id="f1137-109">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="f1137-110">Estas API le permitirán automatizar flujos de trabajo y innovar en función de las capacidades de Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="f1137-110">Those APIs will enable you to automate workflows and innovate based on  Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="f1137-111">El acceso a la API requiere la autenticación OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="f1137-111">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="f1137-112">Para obtener más información, vea [flujo de código de autorización de OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="f1137-112">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>


<span data-ttu-id="f1137-113">En general, deberá realizar los siguientes pasos para usar las API:</span><span class="sxs-lookup"><span data-stu-id="f1137-113">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="f1137-114">Crear una aplicación de AAD</span><span class="sxs-lookup"><span data-stu-id="f1137-114">Create an AAD application</span></span>
- <span data-ttu-id="f1137-115">Obtener un token de acceso con esta aplicación</span><span class="sxs-lookup"><span data-stu-id="f1137-115">Get an access token using this application</span></span>
- <span data-ttu-id="f1137-116">Usar el token para acceder a la API de protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="f1137-116">Use the token to access  Microsoft Threat Protection API</span></span>


<span data-ttu-id="f1137-117">Puede tener acceso a la API de Microsoft Threat Protection con **contexto de aplicación** o **contexto de usuario**.</span><span class="sxs-lookup"><span data-stu-id="f1137-117">You can access  Microsoft Threat Protection API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="f1137-118">**Contexto de aplicación: (recomendado)**</span><span class="sxs-lookup"><span data-stu-id="f1137-118">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="f1137-119">Lo usan las aplicaciones que se ejecutan sin la presencia de un usuario que ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="f1137-119">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="f1137-120">por ejemplo, aplicaciones que se ejecutan como daemons o servicios en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="f1137-120">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="f1137-121">Pasos que se deben seguir para acceder a la API de Microsoft Threat Protection con el contexto de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="f1137-121">Steps that need to be taken to access  Microsoft Threat Protection API with application context:</span></span>

  1. <span data-ttu-id="f1137-122">Cree una aplicación Web de AAD.</span><span class="sxs-lookup"><span data-stu-id="f1137-122">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="f1137-123">Asigne el permiso deseado a applicationFor example, **Incident. Read. All**, **AdvancedHunting. Read. All**.</span><span class="sxs-lookup"><span data-stu-id="f1137-123">Assign the desired permission to the applicationFor example, **Incident.Read.All**, **AdvancedHunting.Read.All**.</span></span> 
  3. <span data-ttu-id="f1137-124">Cree una clave para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="f1137-124">Create a key for this Application.</span></span>
  4. <span data-ttu-id="f1137-125">Obtiene el token mediante la aplicación con su clave.</span><span class="sxs-lookup"><span data-stu-id="f1137-125">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="f1137-126">Usar el token para acceder a la API de protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="f1137-126">Use the token to access  Microsoft Threat Protection API</span></span>

     <span data-ttu-id="f1137-127">Para obtener más información, vea [Get Access with Application context](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="f1137-127">For more information, see [Get access with application context](api-create-app-web.md).</span></span>


- <span data-ttu-id="f1137-128">**Contexto de usuario:**</span><span class="sxs-lookup"><span data-stu-id="f1137-128">**User Context:**</span></span> <br>
    <span data-ttu-id="f1137-129">Se usa para realizar acciones en la API en nombre de un usuario.</span><span class="sxs-lookup"><span data-stu-id="f1137-129">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="f1137-130">Pasos que se deben realizar para acceder a la API de Microsoft Threat Protection con el contexto de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="f1137-130">Steps that needs to be taken to access  Microsoft Threat Protection API with application context:</span></span>
  1. <span data-ttu-id="f1137-131">Cree una aplicación nativa de AAD.</span><span class="sxs-lookup"><span data-stu-id="f1137-131">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="f1137-132">Asigne el permiso deseado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f1137-132">Assign the desired permission to the application.</span></span> <span data-ttu-id="f1137-133">Por ejemplo, **Incident. Read**, **AdvancedHunting. Read**.</span><span class="sxs-lookup"><span data-stu-id="f1137-133">For example, **Incident.Read**, **AdvancedHunting.Read**.</span></span>
  3. <span data-ttu-id="f1137-134">Obtiene el token mediante la aplicación con las credenciales de usuario.</span><span class="sxs-lookup"><span data-stu-id="f1137-134">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="f1137-135">Usar el token para acceder a la API de protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="f1137-135">Use the token to access  Microsoft Threat Protection API</span></span>

     <span data-ttu-id="f1137-136">Para obtener más información, vea [obtener acceso con contexto de usuario](api-create-app-user-context.md).</span><span class="sxs-lookup"><span data-stu-id="f1137-136">For more information, see [Get access with user context](api-create-app-user-context.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="f1137-137">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f1137-137">Related topics</span></span>
- [<span data-ttu-id="f1137-138">API de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f1137-138">Microsoft Threat Protection APIs</span></span>](api-supported.md)
- [<span data-ttu-id="f1137-139">Acceso a Microsoft Threat Protection con contexto de aplicación</span><span class="sxs-lookup"><span data-stu-id="f1137-139">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="f1137-140">Acceso a Microsoft Threat Protection con contexto de usuario</span><span class="sxs-lookup"><span data-stu-id="f1137-140">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)