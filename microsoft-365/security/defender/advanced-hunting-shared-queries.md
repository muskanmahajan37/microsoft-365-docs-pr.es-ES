---
title: Usar consultas compartidas en la búsqueda avanzada de Microsoft 365 Defender
description: Inicie inmediatamente la protección contra amenazas a través de las consultas predefinidas y compartidas. Comparta sus consultas con el público o con su organización.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, repositorio de github, mis consultas, consultas compartidas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f153e438465d4cacf5293cd6e834e85783601c89
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069005"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="bd0d4-105">Utilice las consultas compartidas en la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="bd0d4-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bd0d4-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="bd0d4-106">**Applies to:**</span></span>
- <span data-ttu-id="bd0d4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd0d4-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="bd0d4-108">Las consultas en la [búsqueda avanzada](advanced-hunting-overview.md) pueden ser compartidas entre usuarios de la misma organización.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="bd0d4-109">También puede buscar las consultas compartidas de forma pública en GitHub.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="bd0d4-110">Estas consultas le permitirán seguir rápidamente los escenarios específicos de búsqueda contra amenazas sin tener que escribir las consultas desde cero.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Imagen de las consultas compartidas](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="bd0d4-112">Guardar, modificar y compartir la consulta</span><span class="sxs-lookup"><span data-stu-id="bd0d4-112">Save, modify, and share a query</span></span>
<span data-ttu-id="bd0d4-113">Puede guardar una consulta nueva o existente para que sólo sea accesible para usted o compartida con otros usuarios en su organización.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="bd0d4-114">Crear o modificar una consulta.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="bd0d4-115">Haga clic en **Euardar consulta** en el botón desplegable y seleccione **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="bd0d4-116">Escriba un nombre para la consulta.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-116">Enter a name for the query.</span></span> 

   ![Imagen de una consulta guardada](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="bd0d4-118">Seleccione la carpeta en la que desea guardar la consulta.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="bd0d4-119">**Consultas compartidas** — compartidas con todos los usuarios de su organización</span><span class="sxs-lookup"><span data-stu-id="bd0d4-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="bd0d4-120">**Mis consultas** — accesibles sólo para usted.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="bd0d4-121">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="bd0d4-122">Eliminar o cambiar el nombre de la consulta</span><span class="sxs-lookup"><span data-stu-id="bd0d4-122">Delete or rename a query</span></span>
1. <span data-ttu-id="bd0d4-123">Haga clic con el botón derecho en la consulta que desee cambiar o eliminar el nombre.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-123">Right-click on a query you want to rename or delete.</span></span>

    ![Imagen de una consulta eliminada](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="bd0d4-125">Seleccione **Eliminar** y confirme su eliminación.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="bd0d4-126">O seleccione **Cambiar el nombre** y proporcione un nombre nuevo para la consulta.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="bd0d4-127">Crear un vínculo directo a una consulta</span><span class="sxs-lookup"><span data-stu-id="bd0d4-127">Create a direct link to a query</span></span>
<span data-ttu-id="bd0d4-128">Para generar un vínculo que abra la consulta directamente en el editor de consultas de búsqueda avanzada, finalizar la consulta y seleccionar **Compartir vínculo**.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-128">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="bd0d4-129">Acceder a las consultas en el repositorio de GitHub</span><span class="sxs-lookup"><span data-stu-id="bd0d4-129">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="bd0d4-130">Los investigadores de la seguridad de Microsoft comparten regularmente las consultas de búsquedas avanzadas en un [repositorio público designado en GitHub](https://aka.ms/hunting-queries).</span><span class="sxs-lookup"><span data-stu-id="bd0d4-130">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://aka.ms/hunting-queries).</span></span> <span data-ttu-id="bd0d4-131">Este repositorio está abierto a contribuciones.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-131">This repository is open to contributions.</span></span> <span data-ttu-id="bd0d4-132">Para contribuir, [únete a GitHub gratis](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="bd0d4-132">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="bd0d4-133">Los investigadores de la seguridad de Microsoft también proporcionan búsquedas avanzadas que puede ser utilizadas para buscar actividades e indicadores asociados a las amenazas emergentes.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-133">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="bd0d4-134">Estas consultas son proporcionadas en los informes del [análisis de amenazas](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="bd0d4-134">These queries are provided as part of the [threat analytics](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bd0d4-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bd0d4-135">Related topics</span></span>
- [<span data-ttu-id="bd0d4-136">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="bd0d4-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bd0d4-137">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="bd0d4-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bd0d4-138">Trabajar con resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="bd0d4-138">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="bd0d4-139">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="bd0d4-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="bd0d4-140">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="bd0d4-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="bd0d4-141">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="bd0d4-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)