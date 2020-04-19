---
title: Exportar y descargar contenido de un caso de eDiscovery principal
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: En este artículo se describe cómo exportar y descargar contenido desde un caso de exhibición de documentos electrónicos principal.
ms.openlocfilehash: e0d4315c48a0d0878b8052265ff8663cd1987169
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551479"
---
# <a name="export-content-from-a-core-ediscovery-case"></a><span data-ttu-id="225be-103">Exportar contenido de un caso de eDiscovery principal</span><span class="sxs-lookup"><span data-stu-id="225be-103">Export content from a Core eDiscovery case</span></span>

<span data-ttu-id="225be-104">Una vez ejecutada correctamente la búsqueda, puede exportar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="225be-104">After a search is successfully run, you can export the search results.</span></span> <span data-ttu-id="225be-105">Al exportar los resultados de la búsqueda, los elementos del buzón se descargan en archivos PST o como mensajes individuales.</span><span class="sxs-lookup"><span data-stu-id="225be-105">When you export search results, mailbox items are downloaded in PST files or as individual messages.</span></span> <span data-ttu-id="225be-106">Al exportar contenido de sitios de SharePoint y OneDrive para la empresa, se exportan copias de documentos nativos de Office y otros documentos.</span><span class="sxs-lookup"><span data-stu-id="225be-106">When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported.</span></span> <span data-ttu-id="225be-107">También se exporta un archivo Results. csv que contiene información sobre todos los elementos que se exportan y un archivo de manifiesto (en formato XML) que contiene información sobre cada resultado de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="225be-107">A Results.csv file that contains information about every item that's exported and a manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
<span data-ttu-id="225be-108">Puede exportar los resultados de una [sola búsqueda asociada a un caso](#export-the-results-of-a-single-search) o puede exportar los resultados de [varias búsquedas asociadas a un caso](#export-the-results-of-multiple-searches).</span><span class="sxs-lookup"><span data-stu-id="225be-108">You can export the results of a [single search associated with a case](#export-the-results-of-a-single-search) or you can export the results of [multiple searches associated with a case](#export-the-results-of-multiple-searches).</span></span>
  
## <a name="export-the-results-of-a-single-search"></a><span data-ttu-id="225be-109">Exportar los resultados de una búsqueda única</span><span class="sxs-lookup"><span data-stu-id="225be-109">Export the results of a single search</span></span>

1. <span data-ttu-id="225be-110">Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) e inicie sesión con las credenciales de la cuenta de usuario a la que se le han asignado los permisos de eDiscovery adecuados.</span><span class="sxs-lookup"><span data-stu-id="225be-110">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="225be-111">En el panel de navegación izquierdo del centro de cumplimiento de Microsoft 365, haga clic en **Mostrar todos**y, a continuación, en **eDiscovery > Core**.</span><span class="sxs-lookup"><span data-stu-id="225be-111">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="225be-112">En la página **principal de eDiscovery** , seleccione el caso desde el que desea exportar los resultados de la búsqueda y, a continuación, haga clic en **abrir caso**.</span><span class="sxs-lookup"><span data-stu-id="225be-112">On the **Core eDiscovery** page, select the case that you want to export search results from, and then click **Open case**.</span></span>

4. <span data-ttu-id="225be-113">En la página **principal** del caso, haga clic en la ficha **búsquedas** .</span><span class="sxs-lookup"><span data-stu-id="225be-113">On the **Home** page for the case, click the **Searches** tab.</span></span>

5. <span data-ttu-id="225be-114">En la lista de búsquedas del caso, haga clic en la búsqueda desde la que desea exportar los resultados de la búsqueda y, a continuación, haga clic en **exportar resultados** en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="225be-114">In the list of searches for the case, click the search that you want to export search results from, and then click **Export results** on the flyout.</span></span>

    <span data-ttu-id="225be-115">Se mostrará la página resultados de la **exportación** .</span><span class="sxs-lookup"><span data-stu-id="225be-115">The **Export results** page is displayed.</span></span> 

    ![Página de resultados de la exportación](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    <span data-ttu-id="225be-117">El flujo de trabajo para exportar los resultados de una búsqueda asociada a un caso de exhibición de documentos electrónicos principal es el mismo que para exportar los resultados de búsqueda para una búsqueda en la página **búsqueda de contenido** .</span><span class="sxs-lookup"><span data-stu-id="225be-117">The workflow to export the results of a search associated with a Core eDiscovery case is that same as exporting the search results for a search on the **Content search** page.</span></span> <span data-ttu-id="225be-118">Para obtener instrucciones paso a paso, consulte [exportar resultados](export-search-results.md)de la búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="225be-118">For step-by-step instructions, see [Export content search results](export-search-results.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="225be-119">Al exportar los resultados de búsqueda, tiene la opción de habilitar la desduplicación para que solo se exporte una copia de un mensaje de correo electrónico, aunque se hayan encontrado varias instancias del mismo mensaje en los buzones en los que se realizó la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="225be-119">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched.</span></span> <span data-ttu-id="225be-120">Para obtener más información acerca de la desduplicación y cómo se identifican los elementos duplicados, vea [desduplicación en resultados de la búsqueda de exhibición](de-duplication-in-ediscovery-search-results.md)de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="225be-120">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

    <span data-ttu-id="225be-121">Después de iniciar la exportación, los resultados de la búsqueda se preparan para la descarga, lo que significa que se cargan en una ubicación de almacenamiento de Azure proporcionada por Microsoft en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="225be-121">After you start the export, the search results are prepared for downloading, which means they are uploaded to a Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>
  
6. <span data-ttu-id="225be-122">Haga clic en la pestaña **exportar** para mostrar la lista de trabajos de exportación del caso.</span><span class="sxs-lookup"><span data-stu-id="225be-122">Click the **Export** tab to display the list of export jobs for the case.</span></span>
  
    <span data-ttu-id="225be-123">Puede que tenga que hacer clic en **Actualizar** para actualizar la lista de trabajos de exportación para que muestre el trabajo de exportación que ha creado.</span><span class="sxs-lookup"><span data-stu-id="225be-123">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="225be-124">Los trabajos de exportación tienen el mismo nombre que la búsqueda correspondiente con **_Export** anexado al nombre de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="225be-124">Export jobs have the same name as the corresponding search with **_Export** appended to the search name.</span></span>

7. <span data-ttu-id="225be-125">Haga clic en el trabajo de exportación que ha creado para mostrar la información de estado en la página flotante.</span><span class="sxs-lookup"><span data-stu-id="225be-125">Click the export job you created to display status information on the flyout page.</span></span> <span data-ttu-id="225be-126">Esta información incluye el porcentaje de elementos que se han transferido a la ubicación de almacenamiento de Azure.</span><span class="sxs-lookup"><span data-stu-id="225be-126">This information includes the percentage of items that have been transferred to the Azure Storage location.</span></span>

8. <span data-ttu-id="225be-127">Una vez transferidos todos los elementos, haga clic en **Descargar resultados** para descargar los resultados de la búsqueda en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="225be-127">After all items have been transferred, click **Download results** to download the search results to your local computer.</span></span> <span data-ttu-id="225be-128">Para obtener más información sobre cómo descargar resultados de búsqueda, vea el paso 2 en [exportar resultados](export-search-results.md#step-2-download-the-search-results) de la búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="225be-128">For more information downloading search results, see Step 2 in [Export content search results](export-search-results.md#step-2-download-the-search-results)</span></span>

## <a name="export-the-results-of-multiple-searches"></a><span data-ttu-id="225be-129">Exportar los resultados de varias búsquedas</span><span class="sxs-lookup"><span data-stu-id="225be-129">Export the results of multiple searches</span></span>

<span data-ttu-id="225be-130">Como alternativa a la exportación de los resultados de una sola búsqueda asociada a un caso, puede exportar los resultados de varias búsquedas desde el mismo caso en un solo trabajo de exportación.</span><span class="sxs-lookup"><span data-stu-id="225be-130">As an alternative to exporting the results of a single search associated with a case, you can export the results of multiple searches from the same case in a single export job.</span></span> <span data-ttu-id="225be-131">Exportar los resultados de varias búsquedas es más rápido y sencillo que exportar los resultados una búsqueda cada vez.</span><span class="sxs-lookup"><span data-stu-id="225be-131">Exporting the results of multiple searches is faster and easier than exporting the results one search at a time.</span></span>
  
> [!NOTE]
> <span data-ttu-id="225be-132">No puede exportar los resultados de varias búsquedas si una de esas búsquedas se configuró para buscar ubicaciones en suspensión.</span><span class="sxs-lookup"><span data-stu-id="225be-132">You can't export the results of multiple searches if one of those searches was configured to search locations on hold.</span></span>

1. <span data-ttu-id="225be-133">Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) e inicie sesión con las credenciales de la cuenta de usuario a la que se le han asignado los permisos de eDiscovery adecuados.</span><span class="sxs-lookup"><span data-stu-id="225be-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="225be-134">En el panel de navegación izquierdo del centro de cumplimiento de Microsoft 365, haga clic en **Mostrar todos**y, a continuación, en **eDiscovery > Core**.</span><span class="sxs-lookup"><span data-stu-id="225be-134">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="225be-135">En la página **principal de eDiscovery** , seleccione el caso desde el que desea exportar los resultados de la búsqueda y, a continuación, haga clic en **abrir caso**.</span><span class="sxs-lookup"><span data-stu-id="225be-135">On the **Core eDiscovery** page, select the case that you want to export search results from, and then click **Open case**.</span></span>

4. <span data-ttu-id="225be-136">En la página **principal** del caso, haga clic en la ficha **búsquedas** .</span><span class="sxs-lookup"><span data-stu-id="225be-136">On the **Home** page for the case, click the **Searches** tab.</span></span>
    
5. <span data-ttu-id="225be-137">En la lista de búsquedas del caso, active la casilla de verificación situada junto a dos o más búsquedas de las que desee exportar resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="225be-137">In the list of searches for the case, select the checkbox next to two or more searches you want to export search results from.</span></span> 

   <span data-ttu-id="225be-138">Aparece la página flotante **acciones en masa** .</span><span class="sxs-lookup"><span data-stu-id="225be-138">The **Bulk actions** flyout page appears.</span></span> 

    ![En la página acciones en masa, haga clic en exportar resultados](../media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
6. <span data-ttu-id="225be-140">Haga clic en **exportar resultados**.</span><span class="sxs-lookup"><span data-stu-id="225be-140">Click **Export results**.</span></span>

   <span data-ttu-id="225be-141">Se mostrará la página resultados de la **exportación** .</span><span class="sxs-lookup"><span data-stu-id="225be-141">The **Export results** page is displayed.</span></span> 

    ![Página de resultados de la exportación](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    <span data-ttu-id="225be-143">En este momento, el flujo de trabajo para exportar los resultados de varias búsquedas asociadas a un caso de exhibición de documentos electrónicos principal es el mismo que exportar los resultados de la búsqueda para una sola búsqueda.</span><span class="sxs-lookup"><span data-stu-id="225be-143">At this point, the workflow to export the results of multiple searches associated with a Core eDiscovery case is that same as exporting the search results for a single search.</span></span> <span data-ttu-id="225be-144">Consulte el paso 5 de la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="225be-144">See step 5 in the previous section.</span></span>

### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a><span data-ttu-id="225be-145">Más información sobre cómo exportar los resultados de varias búsquedas</span><span class="sxs-lookup"><span data-stu-id="225be-145">More information about exporting the results of multiple searches</span></span>

- <span data-ttu-id="225be-146">Cuando se exportan los resultados de varias búsquedas, las consultas de búsqueda de todas las búsquedas se combinan mediante operadores **or** y, a continuación, se inicia la búsqueda combinada.</span><span class="sxs-lookup"><span data-stu-id="225be-146">When you export the results of multiple searches, the search queries from all the searches are combined by using **OR** operators, and then the combined search is started.</span></span> <span data-ttu-id="225be-147">Los resultados estimados de la búsqueda combinada se muestran en la página de flotante del trabajo de exportación seleccionado.</span><span class="sxs-lookup"><span data-stu-id="225be-147">The estimated results of the combined search are displayed in the flyout page of the selected export job.</span></span> <span data-ttu-id="225be-148">A continuación, los resultados de la búsqueda se copian en la ubicación de almacenamiento de Azure en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="225be-148">The search results are then copied to the Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="225be-149">El estado del trabajo de copia también se muestra en la página de flotante.</span><span class="sxs-lookup"><span data-stu-id="225be-149">The status of the copy job is also displayed on the flyout page.</span></span> <span data-ttu-id="225be-150">Como se indicó anteriormente, una vez que se han copiado todos los resultados de la búsqueda, puede descargarlos en un equipo local.</span><span class="sxs-lookup"><span data-stu-id="225be-150">As previously stated, after all the search results have been copied, you can download them to a local computer.</span></span>

- <span data-ttu-id="225be-151">El número máximo de palabras clave de las consultas para todas las búsquedas que desea exportar es de 500.</span><span class="sxs-lookup"><span data-stu-id="225be-151">The maximum number of keywords from queries for all searches that you want to export is 500.</span></span> <span data-ttu-id="225be-152">Se trata del mismo límite para una sola búsqueda.</span><span class="sxs-lookup"><span data-stu-id="225be-152">This is the same limit for a single search.</span></span> <span data-ttu-id="225be-153">Esto se debe a que el trabajo de exportación combina todas las consultas de búsqueda mediante el operador **or** .</span><span class="sxs-lookup"><span data-stu-id="225be-153">That's because the export job combines all the search queries by using the **OR** operator.</span></span> <span data-ttu-id="225be-154">Si supera este límite, se devolverá un error.</span><span class="sxs-lookup"><span data-stu-id="225be-154">If you exceed this limit, an error will be returned.</span></span> <span data-ttu-id="225be-155">En este caso, tiene que exportar los resultados de menos búsquedas o simplificar las consultas de búsqueda de las búsquedas originales que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="225be-155">In this case, you have to export the results from fewer searches or simplify the search queries of the original searches that you want to export.</span></span>

- <span data-ttu-id="225be-156">Los resultados de la búsqueda que se exportan están organizados por la ubicación del contenido en la que se encontró el elemento.</span><span class="sxs-lookup"><span data-stu-id="225be-156">The search results that are exported are organized by the content location the item was found in.</span></span> <span data-ttu-id="225be-157">Esto significa que una ubicación de contenido en los resultados de la exportación puede tener elementos devueltos por búsquedas diferentes.</span><span class="sxs-lookup"><span data-stu-id="225be-157">That means a content location in the export results may have items returned by different searches.</span></span> <span data-ttu-id="225be-158">Por ejemplo, si decide exportar los mensajes de correo electrónico de un archivo PST para cada buzón, el archivo PST podría tener resultados de varias búsquedas.</span><span class="sxs-lookup"><span data-stu-id="225be-158">For example, if you choose to export email messages in one PST file for each mailbox, the PST file might have results from multiple searches.</span></span>

- <span data-ttu-id="225be-159">Si más de una de las búsquedas que se exportan devuelven el mismo documento o elemento de correo electrónico de la misma ubicación de contenido, solo se exportará una copia del elemento.</span><span class="sxs-lookup"><span data-stu-id="225be-159">If the same email item or document from the same content location is returned by more than one of the searches that you export, only one copy of the item will be exported.</span></span>

- <span data-ttu-id="225be-160">No puede editar una exportación para varias búsquedas después de crearla.</span><span class="sxs-lookup"><span data-stu-id="225be-160">You can't edit an export for multiple searches after you create it.</span></span> <span data-ttu-id="225be-161">Por ejemplo, no puede Agregar o quitar búsquedas del trabajo de exportación.</span><span class="sxs-lookup"><span data-stu-id="225be-161">For example, you can't add or remove searches from the export job.</span></span> <span data-ttu-id="225be-162">Tiene que crear un trabajo de exportación para cambiar los resultados de la búsqueda que se van a exportar.</span><span class="sxs-lookup"><span data-stu-id="225be-162">You have to create an export job to change which search results are exported.</span></span> <span data-ttu-id="225be-163">Después de crear un trabajo de exportación, solo puede descargar los resultados en un equipo, reiniciar la exportación o eliminar el trabajo de exportación.</span><span class="sxs-lookup"><span data-stu-id="225be-163">After an export job is created, you only can download the results to a computer, restart the export, or delete the export job.</span></span>

- <span data-ttu-id="225be-164">Si reinicia la exportación, los cambios en las consultas de las búsquedas que componen el trabajo de exportación no afectarán a los resultados de la búsqueda que se recuperan.</span><span class="sxs-lookup"><span data-stu-id="225be-164">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that are retrieved.</span></span> <span data-ttu-id="225be-165">Cuando se reinicia una exportación, se ejecutará de nuevo el mismo trabajo de consulta de búsqueda combinado que se ejecutó al crear el trabajo de exportación.</span><span class="sxs-lookup"><span data-stu-id="225be-165">When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>

- <span data-ttu-id="225be-166">Además, si reinicia una exportación, los resultados de la búsqueda que se copian en la ubicación de almacenamiento de Azure sobrescribirán los resultados anteriores.</span><span class="sxs-lookup"><span data-stu-id="225be-166">Also, if you restart an export, the search results that are copied to the Azure Storage location overwrites the previous results.</span></span> <span data-ttu-id="225be-167">Los resultados anteriores que se han copiado no estarán disponibles para su descarga.</span><span class="sxs-lookup"><span data-stu-id="225be-167">The previous results that were copied won't be available to be downloaded.</span></span>

- <span data-ttu-id="225be-168">La preparación de los resultados de varias búsquedas para el análisis en la exhibición avanzada de documentos electrónicos (Classic) no está disponible.</span><span class="sxs-lookup"><span data-stu-id="225be-168">Preparing the results of multiple searches for analysis in Advanced eDiscovery (classic) isn't available.</span></span> <span data-ttu-id="225be-169">Solo puede preparar los resultados de una sola búsqueda para el análisis en la exhibición avanzada de documentos electrónicos (Classic).</span><span class="sxs-lookup"><span data-stu-id="225be-169">You can only prepare the results of a single search for analysis in Advanced eDiscovery (classic).</span></span>