---
title: Buscar contenido en un caso de exhibición de documentos electrónicos principal
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
description: Puede buscar contenido que pueda ser relevante para un caso de exhibición de documentos electrónicos principal.
ms.openlocfilehash: b8aa090094dc2699ee774a9b662da17fefde1188
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551488"
---
# <a name="search-for-content-in-a-core-ediscovery-case"></a><span data-ttu-id="dd1f6-103">Buscar contenido en un caso de exhibición de documentos electrónicos principal</span><span class="sxs-lookup"><span data-stu-id="dd1f6-103">Search for content in a Core eDiscovery case</span></span>

<span data-ttu-id="dd1f6-104">Una vez que se crea un caso de exhibición de documentos electrónicos principal y se colocan en suspensión personas de interés en el caso, puede crear y ejecutar una o más búsquedas para el contenido relevante para el caso.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-104">After a Core eDiscovery case is created and people of interest in the case are placed on hold, you can create and run one or more searches for content relevant to the case.</span></span> <span data-ttu-id="dd1f6-105">Las búsquedas asociadas a un caso de eDiscovery principal no aparecen en la página **búsqueda de contenido** en el centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-105">Searches associated with a Core eDiscovery case aren't listed on the **Content search** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="dd1f6-106">Estas búsquedas se enumeran en la página **búsquedas** del núcleo eDiscover caso en el que se asocian las búsquedas.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-106">These searches are listed on the **Searches** page of the Core eDiscover case the searches are associated with.</span></span> <span data-ttu-id="dd1f6-107">Esto también significa que solo se puede tener acceso a las búsquedas asociadas a un caso por los miembros de case.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-107">This also means that searches associated with a case can only be accessed by case members.</span></span>

<span data-ttu-id="dd1f6-108">Para crear una búsqueda de exhibición de documentos electrónicos principal:</span><span class="sxs-lookup"><span data-stu-id="dd1f6-108">To create a Core eDiscovery search:</span></span>
  
1. <span data-ttu-id="dd1f6-109">Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) e inicie sesión con las credenciales de la cuenta de usuario a la que se le han asignado los permisos de eDiscovery adecuados.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-109">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="dd1f6-110">En el panel de navegación izquierdo del centro de cumplimiento de Microsoft 365, haga clic en **Mostrar todos**y, a continuación, en **eDiscovery > Core**.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-110">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="dd1f6-111">En la página **principal de eDiscovery** , seleccione el caso en el que desea crear una búsqueda asociada y, a continuación, haga clic en **abrir caso**.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-111">On the **Core eDiscovery** page, select the case that you want to create an associated search, and then click **Open case**.</span></span>

4. <span data-ttu-id="dd1f6-112">En la página **principal** del caso, haga clic en la ficha **búsquedas** .</span><span class="sxs-lookup"><span data-stu-id="dd1f6-112">On the **Home** page for the case, click the **Searches** tab.</span></span>
  
5. <span data-ttu-id="dd1f6-113">En la página **Buscar** , haga clic en **nueva búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-113">On the **Search** page, click **New search**.</span></span>

6. <span data-ttu-id="dd1f6-114">En la página **Nueva búsqueda**, puede agregar palabras clave y condiciones para crear la consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-114">On the **New search** page, you can add keywords and conditions to create the search query.</span></span> 

    ![Nueva búsqueda](../media/0e9954e7-c0ea-4e05-820b-e4b81dc5f81d.png)
  
   <span data-ttu-id="dd1f6-116">a.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-116">a.</span></span> <span data-ttu-id="dd1f6-117">Puede especificar palabras clave, propiedades del mensaje, como las fechas de envío y recepción, o propiedades del documento, como nombres de archivo o la fecha en que se modificó por última vez un documento.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-117">You can specify keywords, message properties, such as sent and received dates, or document properties, such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="dd1f6-118">Puede usar consultas más complejas que usen un operador booleano, como **and**, **or**, **Not**, **Near**o **ONEAR**.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-118">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, **NEAR**, or **ONEAR**.</span></span> <span data-ttu-id="dd1f6-119">Además, puede buscar información confidencial (como los números de la seguridad social) en documentos o buscar en documentos que se han compartido de forma externa.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-119">You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally.</span></span> <span data-ttu-id="dd1f6-120">Si deja vacío el cuadro palabra clave, todo el contenido ubicado en las ubicaciones de contenido especificadas se incluirá en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-120">If you leave the keyword box empty, all content located in the specified content locations will be included in the search results.</span></span>

   <span data-ttu-id="dd1f6-121">b.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-121">b.</span></span> <span data-ttu-id="dd1f6-122">Puede hacer clic en la casilla **Mostrar lista de palabras clave** y escribir una palabra clave en cada fila.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-122">You can click the **Show keyword list** check box and the type a keyword in each row.</span></span> <span data-ttu-id="dd1f6-123">Si hace esto, las palabras clave de cada fila están conectadas mediante el operador **or** en la consulta de búsqueda que se crea.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-123">If you do this, the keywords on each row are connected by the **OR** operator in the search query that's created.</span></span> <span data-ttu-id="dd1f6-124">Puede escribir un máximo de 20 palabras clave en la lista.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-124">You can enter a maximum of 20 keywords to the list.</span></span>

    ![Lista de palabras clave](../media/29cceb5d-2817-4fc4-b91a-ced1c5824a17.png)
  
    <span data-ttu-id="dd1f6-126">¿Por qué usar la lista de palabras clave?</span><span class="sxs-lookup"><span data-stu-id="dd1f6-126">Why use the keyword list?</span></span> <span data-ttu-id="dd1f6-127">Puede obtener estadísticas que muestran cuántos elementos coinciden con cada palabra clave.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-127">You can get statistics that show how many items match each keyword.</span></span> <span data-ttu-id="dd1f6-128">Esto le ayudará a identificar rápidamente las palabras clave más (y menos) efectivas.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-128">This can help you quickly identify which keywords are the most (and least) effective.</span></span> <span data-ttu-id="dd1f6-129">También puede usar una frase de palabras clave (entre paréntesis) en una fila.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-129">You can also use a keyword phrase (surrounded by parentheses) in a row.</span></span> <span data-ttu-id="dd1f6-130">Para saber más sobre las estadísticas de búsqueda, consulte [Ver estadísticas de palabras clave para resultados de búsqueda de contenido](view-keyword-statistics-for-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="dd1f6-130">For more information about search statistics, see [View keyword statistics for Content Search results](view-keyword-statistics-for-content-search.md).</span></span>

    <span data-ttu-id="dd1f6-131">Para obtener más información acerca del uso de la lista de palabras clave, vea [Building a Search Query](content-search.md#building-a-search-query).</span><span class="sxs-lookup"><span data-stu-id="dd1f6-131">For more information about using the keywords list, see [Building a search query](content-search.md#building-a-search-query).</span></span>

   <span data-ttu-id="dd1f6-132">c.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-132">c.</span></span> <span data-ttu-id="dd1f6-133">Puede hacer clic en **condiciones** y agregar condiciones en una consulta de búsqueda para restringir una búsqueda y devolver un conjunto de resultados más refinado.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-133">You can click **Conditions** and add conditions to a search query to narrow a search and return a more refined set of results.</span></span> <span data-ttu-id="dd1f6-134">Con cada condición, se agrega una cláusula a la consulta de búsqueda KQL que se crea y se ejecuta al iniciar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-134">Each condition adds a clause to the KQL search query that is created and run when you start the search.</span></span> <span data-ttu-id="dd1f6-135">Una condición está conectada de forma lógica con la consulta por palabra clave (especificada en el cuadro de palabra clave) mediante el operador **AND**.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-135">A condition is logically connected to the keyword query (specified in the keyword box) by the **AND** operator.</span></span> <span data-ttu-id="dd1f6-136">Esto significa que los elementos deben cumplir con la consulta de palabras clave y cada condición que se va a incluir en los resultados.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-136">That means that items have to satisfy both the keyword query and each condition to be included in the results.</span></span> <span data-ttu-id="dd1f6-137">De esta manera, las condiciones permiten restringir los resultados.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-137">This is how conditions help to narrow your results.</span></span>

    <span data-ttu-id="dd1f6-138">Para obtener más información sobre cómo crear una consulta de búsqueda y el uso de las condiciones, consulte [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="dd1f6-138">For more information about creating a search query and using conditions, see [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).</span></span>

7. <span data-ttu-id="dd1f6-139">En **ubicaciones: ubicaciones en espera**, elija las ubicaciones de contenido en las que desea realizar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-139">Under **Locations: locations on hold**, choose the content locations that you want to search.</span></span> <span data-ttu-id="dd1f6-140">Puede buscar buzones de correo, sitios y carpetas públicas en la misma búsqueda.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-140">You can search mailboxes, sites, and public folders in the same search.</span></span>

    ![Ubicaciones, ubicaciones en suspensión](../media/d56398aa-0b20-4500-8e26-494eab92a99f.png)
  
    - <span data-ttu-id="dd1f6-142">**Todas las ubicaciones**.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-142">**All locations**.</span></span> <span data-ttu-id="dd1f6-143">Seleccione esta opción para buscar en todas las ubicaciones de contenido de la organización.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-143">Select this option to search all content locations in your organization.</span></span> <span data-ttu-id="dd1f6-144">Si selecciona esta opción, puede elegir buscar todos los buzones de Exchange (que incluye los buzones de todos los grupos de Microsoft Teams, Yammer y Office 365), todos los sitios de SharePoint y OneDrive para la empresa (que incluye los sitios de todos los grupos de Microsoft Teams, Yammer y Office 365) y todas las carpetas públicas.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-144">When you select this option, you can choose to search all Exchange mailboxes (which includes the mailboxes for all Microsoft Teams, Yammer Groups, and Office 365 Groups), all SharePoint and OneDrive for Business sites (which includes the sites for all Microsoft Teams, Yammer Groups, and Office 365 Groups), and all public folders.</span></span>
    
    - <span data-ttu-id="dd1f6-145">**Todas las ubicaciones en espera**.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-145">**All locations on hold**.</span></span> <span data-ttu-id="dd1f6-146">Seleccione esta opción para buscar en todas las ubicaciones de contenido que se han colocado en la suspensión de exhibición de documentos electrónicos en el caso.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-146">Select this option to search all the content locations that have been placed on eDiscovery hold in the case.</span></span> <span data-ttu-id="dd1f6-147">Si el caso contiene varias suspensiones, se buscará en las ubicaciones de contenido de todas las suspensiones.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-147">If the case contains multiple holds, the content locations from all holds will be searched.</span></span> <span data-ttu-id="dd1f6-148">Además, si se colocó una ubicación de contenido en una suspensión basada en consulta, solo se buscará en los elementos que están en espera cuando ejecute la búsqueda de contenido que está creando en este paso.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-148">Additionally, if a content location was placed on a query-based hold, only the items that are on hold will be searched when you run the content search that you're creating in this step.</span></span> <span data-ttu-id="dd1f6-149">Por ejemplo, si un usuario se colocó en la suspensión de casos basada en consultas y conserva los elementos que se enviaron o se crearon antes de una fecha específica, sólo se buscará en esos elementos.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-149">For example, if a user was placed on query-based case hold that preserves items that were sent or created before a specific date, only those items would be searched.</span></span> <span data-ttu-id="dd1f6-150">Esto se logra conectando la consulta de suspensión de casos y la consulta de búsqueda de contenido por un operador **and** .</span><span class="sxs-lookup"><span data-stu-id="dd1f6-150">This is accomplished by connecting the case hold query and the content search query by an **AND** operator.</span></span> <span data-ttu-id="dd1f6-151">Para obtener más información, vea [ubicaciones de búsqueda en la retención de exhibición de](create-ediscovery-holds.md#search-locations-on-ediscovery-hold)documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-151">For more information, see [Search locations on eDiscovery hold](create-ediscovery-holds.md#search-locations-on-ediscovery-hold).</span></span>
    
    - <span data-ttu-id="dd1f6-152">**Ubicaciones específicas**.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-152">**Specific locations**.</span></span> <span data-ttu-id="dd1f6-153">Seleccione esta opción para seleccionar los buzones y sitios en los que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-153">Select this option to select the mailboxes and sites that you want to search.</span></span> <span data-ttu-id="dd1f6-154">Cuando seleccione esta opción y haga clic en **modificar**, aparecerá una lista de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-154">When you select this option and click **Modify**, a list of locations appears.</span></span> <span data-ttu-id="dd1f6-155">Puede elegir buscar en cualquiera o todos los usuarios, grupos, equipos o ubicaciones de sitio.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-155">You can choose to search any or all users, groups, teams, or site locations.</span></span> <span data-ttu-id="dd1f6-156">También puede buscar en las carpetas públicas de su organización.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-156">You can also search the public folders in your organization.</span></span>
    
      ![Seleccionar ubicaciones específicas](../media/97469b15-7be1-4aee-be27-f8343636152c.png)
  
     <span data-ttu-id="dd1f6-158">Si selecciona esta opción y busca en cualquier ubicación de contenido que esté en espera, las consultas de una suspensión de casos basada en consultas no se aplicarán a la consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-158">If you select this option and search any content location that's on hold, any query from a query-based case hold won't be applied to the search query.</span></span> <span data-ttu-id="dd1f6-159">En otras palabras, se busca en todo el contenido, no solo en el contenido que conserva una retención de casos basada en la consulta.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-159">In other words, all content is searched, not just the content that's preserved by a query-based case hold.</span></span>

8. <span data-ttu-id="dd1f6-160">Una vez seleccionadas las ubicaciones de contenido para buscar, haga clic en **listo** y, a continuación, en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-160">After you select the content locations to search, click **Done** and then click **Save**.</span></span>

9. <span data-ttu-id="dd1f6-161">En la página **nueva búsqueda** , haga clic en **Guardar & ejecutar** y, a continuación, escriba un nombre para la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-161">On the **New search** page, click **Save & run** and then type a name for the search.</span></span> <span data-ttu-id="dd1f6-162">Las búsquedas asociadas a un caso de eDiscovery principal deben tener nombres únicos en la organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-162">Searches associated with a Core eDiscovery case must have names that are unique within your Office 365 organization.</span></span>

10. <span data-ttu-id="dd1f6-163">Haga clic en **Guardar** para guardar la configuración de la búsqueda e iniciar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-163">Click **Save** to save the search settings and start the search.</span></span>

  <span data-ttu-id="dd1f6-164">Una vez finalizada la búsqueda, puede obtener una vista previa de los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-164">After the search is completed, you can preview the search results.</span></span> <span data-ttu-id="dd1f6-165">Si es necesario, haga clic en **Actualizar** en la página **búsquedas** para mostrar la búsqueda que ha creado en la lista.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-165">If necessary, click **Refresh** on the **Searches** page to display the search you created in the list.</span></span>

11. <span data-ttu-id="dd1f6-166">Haga clic en la búsqueda para mostrar la página de flotante, que contiene estadísticas sobre la búsqueda y realizar otras tareas, como ver estadísticas de búsqueda y exportar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-166">Click the search to display the flyout page, which contains statistics about the search and to perform other tasks such as viewing search statistics and exporting the search results.</span></span>

## <a name="more-information-about-searching-content-locations"></a><span data-ttu-id="dd1f6-167">Más información sobre la búsqueda de ubicaciones de contenido</span><span class="sxs-lookup"><span data-stu-id="dd1f6-167">More information about searching content locations</span></span>

- <span data-ttu-id="dd1f6-168">Al hacer clic en **elegir usuarios, grupos o equipos** para especificar los buzones en los que se va a buscar, el selector de buzones que se muestra está vacío.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-168">When you click **Choose users, groups, or teams** to specify mailboxes to search, the mailbox picker that's displayed is empty.</span></span> <span data-ttu-id="dd1f6-169">Esto se ha diseñado así para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-169">This is by design to enhance performance.</span></span> <span data-ttu-id="dd1f6-170">Para agregar destinatarios a esta lista, haga clic en **elegir usuarios, grupos o equipos**, escriba un nombre (un mínimo de 3 caracteres) en el cuadro de búsqueda, active la casilla de verificación situada junto al nombre y, a continuación, haga clic en **elegir**.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-170">To add recipients to this list, click **Choose users, groups, or teams**, type a name (a minimum of 3 characters) in the search box, select the check box next to the name, and then click **Choose**.</span></span>

- <span data-ttu-id="dd1f6-171">Puede Agregar buzones inactivos, Microsoft Teams, grupos de Yammer, grupos de Office 365 y grupos de distribución a la lista de buzones de correo para la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-171">You can add inactive mailboxes, Microsoft Teams, Yammer Groups, Office 365 Groups, and distribution groups to the list of mailboxes to search.</span></span> <span data-ttu-id="dd1f6-172">No se admiten grupos de distribución dinámicos.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-172">Dynamic distribution groups aren't supported.</span></span> <span data-ttu-id="dd1f6-173">Si agrega Microsoft Teams, grupos de Yammer o grupos de Office 365, se busca en el buzón de grupo o de equipo; no se busca en los buzones de los miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-173">If you add Microsoft Teams, Yammer Groups, or Office 365 Groups, the group or team mailbox is searched; the mailboxes of the group members aren't searched.</span></span>

- <span data-ttu-id="dd1f6-174">Para agregar sitios, haga clic en **elegir sitios**, haga clic en **elegir sitios** de nuevo y, a continuación, escriba la dirección URL de cada sitio que desee buscar.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-174">To add sites click **Choose sites**, click **Choose sites** again, and then type the URL for each site that you want to search.</span></span> <span data-ttu-id="dd1f6-175">También puede Agregar la dirección URL del sitio de SharePoint para un equipo de Microsoft, un grupo de Yammer o un grupo de Office 365.</span><span class="sxs-lookup"><span data-stu-id="dd1f6-175">You can also add the URL for the SharePoint site for a Microsoft Team, a Yammer Group, or an Office 365 Group.</span></span>