---
title: Configurar un conector para archivar datos de una base de datos de MS SQL
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Los administradores pueden configurar un conector para importar y archivar datos de MS SQL Database. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar las características de cumplimiento, como directivas de retención legal, búsqueda de contenido y retención para administrar datos de terceros.
ms.openlocfilehash: 6e3a4a79845539745bec233acbfaeff22f4ad4a9
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002853"
---
# <a name="set-up-a-connector-to-archive-data-from-ms-sql-database-preview"></a><span data-ttu-id="26e16-105">Configurar un conector para archivar datos de una base de datos de MS SQL (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="26e16-105">Set up a connector to archive data from MS SQL Database (preview)</span></span>

<span data-ttu-id="26e16-106">Use un conector de Globanet en el centro de cumplimiento de Microsoft 365 para importar y archivar datos de MS SQL Database en buzones de usuario de la organización 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="26e16-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from MS SQL Database to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="26e16-107">Globanet proporciona un conector de importador de bases de datos MS SQL que está configurado para capturar elementos de una base de datos mediante un archivo de configuración XML e importar dichos elementos a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26e16-107">Globanet provides you with an MS SQL Database Importer connector that's configured to capture items from a database using an XML configuration file and import those items to Microsoft 365.</span></span> <span data-ttu-id="26e16-108">El conector convierte el contenido de la base de datos MS SQL a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a los buzones de usuario en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26e16-108">The connector converts content from MS SQL Database to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="26e16-109">Después de que el contenido de la base de datos de MS SQL se almacenó en buzones de usuario, puede aplicar las características de cumplimiento de Microsoft 365, como retención por juicio, eDiscovery, directivas de retención y etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="26e16-109">After content from MS SQL Database stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels.</span></span> <span data-ttu-id="26e16-110">El uso de un conector de base de datos MS SQL para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y regulatorias.</span><span class="sxs-lookup"><span data-stu-id="26e16-110">Using an MS SQL Database connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-the-ms-sql-data"></a><span data-ttu-id="26e16-111">Información general sobre el archivado de los datos de MS SQL</span><span class="sxs-lookup"><span data-stu-id="26e16-111">Overview of archiving the MS SQL data</span></span>

<span data-ttu-id="26e16-112">En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de MS SQL en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26e16-112">The following overview explains the process of using a connector to archive MS SQL data in Microsoft 365.</span></span>

![Flujo de trabajo de archivado para datos de MS SQL](../media/MSSQLDatabaseConnectorWorkflow.png)

1. <span data-ttu-id="26e16-114">La organización trabaja con un proveedor de bases de datos MS SQL para instalar y configurar un sitio de base de datos MS SQL.</span><span class="sxs-lookup"><span data-stu-id="26e16-114">Your organization works with an MS SQL Database provider to set up and configure an MS SQL Database site.</span></span>

2. <span data-ttu-id="26e16-115">Una vez cada 24 horas, los elementos de la base de datos MS SQL se copian en el sitio Merge1 de Globanet.</span><span class="sxs-lookup"><span data-stu-id="26e16-115">Once every 24 hours, MS SQL Database items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="26e16-116">El conector también convierte este contenido a un formato de mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="26e16-116">The connector also converts this content to an email message format.</span></span>

3. <span data-ttu-id="26e16-117">El conector de importador de bases de datos de MS SQL que se crea en el centro de cumplimiento de Microsoft 365, se conecta al sitio de Globanet Merge1 todos los días y transfiere los mensajes a una ubicación de almacenamiento seguro de Azure en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="26e16-117">The MS SQL Database Importer connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="26e16-118">El conector importa los elementos convertidos de la base de datos MS SQL a los buzones de usuarios específicos mediante el valor de la propiedad *email* de la asignación automática de usuarios, como se describe en el [paso 3](#step-3-map-users-and-complete-the-connector-setup).</span><span class="sxs-lookup"><span data-stu-id="26e16-118">The connector imports the converted MS SQL Database items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="26e16-119">Se crea una subcarpeta de la carpeta Bandeja de entrada denominada **MS SQL Database Importer** en los buzones de usuario y los elementos se importan a esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="26e16-119">A subfolder in the Inbox folder named **MS SQL Database Importer** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="26e16-120">El conector determina a qué buzón se importarán los elementos mediante el valor de la propiedad *email* .</span><span class="sxs-lookup"><span data-stu-id="26e16-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="26e16-121">Cada elemento de la base de datos de MS SQL contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.</span><span class="sxs-lookup"><span data-stu-id="26e16-121">Every item from the MS SQL Database contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="26e16-122">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="26e16-122">Before you begin</span></span>

- <span data-ttu-id="26e16-123">Cree una cuenta de Globanet Merge1 para Microsoft Connectors.</span><span class="sxs-lookup"><span data-stu-id="26e16-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="26e16-124">Para crear una cuenta, póngase en contacto [con el soporte técnico de Globanet](https://globanet.com/contact-us/).</span><span class="sxs-lookup"><span data-stu-id="26e16-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="26e16-125">Debe iniciar sesión en esta cuenta cuando cree el conector en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="26e16-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="26e16-126">El usuario que crea el conector de Microsoft SQL Database Importer en el paso 1 (y lo completa en el paso 3) debe asignarse a la función importación y exportación de buzones de correo en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="26e16-126">The user who creates the MS SQL Database Importer connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="26e16-127">Este rol es necesario para agregar conectores en la página conectores de datos del centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26e16-127">This role is required to add connectors on the Data connectors page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="26e16-128">De forma predeterminada, este rol no está asignado a ningún grupo de roles en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="26e16-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="26e16-129">Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="26e16-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="26e16-130">O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros.</span><span class="sxs-lookup"><span data-stu-id="26e16-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="26e16-131">Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="26e16-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-ms-sql-database-importer-connector"></a><span data-ttu-id="26e16-132">Paso 1: configurar el conector del importador de bases de datos de MS SQL</span><span class="sxs-lookup"><span data-stu-id="26e16-132">Step 1: Set up the MS SQL Database Importer connector</span></span>

<span data-ttu-id="26e16-133">El primer paso es obtener acceso a la página **conectores de datos** en el centro de cumplimiento de Microsoft365 y crear un conector para la base de datos de MS SQL.</span><span class="sxs-lookup"><span data-stu-id="26e16-133">The first step is to access to the **Data Connectors** page in the Microsoft365 compliance center and create a connector for the MS SQL Database.</span></span>

1. <span data-ttu-id="26e16-134">Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y, a continuación, haga clic en **conectores de datos**  >  **MS SQL Database Importer**.</span><span class="sxs-lookup"><span data-stu-id="26e16-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** > **MS SQL Database Importer**.</span></span>

2. <span data-ttu-id="26e16-135">En la página Descripción del producto del **importador de bases de datos MS SQL** , haga clic en **Agregar nuevo conector**.</span><span class="sxs-lookup"><span data-stu-id="26e16-135">On the **MS SQL Database Importer** product description page, click **Add new connector**.</span></span>

3. <span data-ttu-id="26e16-136">En la página **condiciones de servicio** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="26e16-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="26e16-137">Escriba un nombre único que identifique el conector y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="26e16-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="26e16-138">Inicie sesión en su cuenta de Merge1 para configurar el conector.</span><span class="sxs-lookup"><span data-stu-id="26e16-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-ms-sql-database-importer-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="26e16-139">Paso 2: configurar el conector del importador de bases de datos de MS SQL en el sitio de Merge1 de Globanet</span><span class="sxs-lookup"><span data-stu-id="26e16-139">Step 2: Configure the MS SQL Database Importer connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="26e16-140">El segundo paso consiste en configurar el conector del importador de bases de datos MS SQL en el sitio Merge1.</span><span class="sxs-lookup"><span data-stu-id="26e16-140">The second step is to configure the MS SQL Database Importer connector on the Merge1 site.</span></span> <span data-ttu-id="26e16-141">Para obtener información acerca de cómo configurar el importador de bases de datos de MS SQL, consulte [Guía del usuario de conectores de terceros de Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf).</span><span class="sxs-lookup"><span data-stu-id="26e16-141">For information about how to configure the MS SQL Database Importer, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="26e16-142">Después de hacer clic en **guardar & finalizar** , se muestra la página **asignación de usuarios** en el Asistente para conectores del centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26e16-142">After you click **Save & Finish** , the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="26e16-143">Paso 3: asignar usuarios y completar la configuración del conector</span><span class="sxs-lookup"><span data-stu-id="26e16-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="26e16-144">Para asignar usuarios y completar la configuración del conector, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="26e16-144">To map users and complete the connector setup, follow these steps:</span></span>

1. <span data-ttu-id="26e16-145">En la página **asignar usuarios del importador de bases de datos MS SQL a usuarios de Microsoft 365** , habilite la asignación automática de usuarios.</span><span class="sxs-lookup"><span data-stu-id="26e16-145">On the **Map MS SQL Database Importer users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="26e16-146">Los elementos de la base de datos MS SQL incluyen una propiedad denominada *email* , que contiene las direcciones de correo electrónico de los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="26e16-146">The MS SQL Database items include a property called *Email* , which contains email addresses for users in your organization.</span></span> <span data-ttu-id="26e16-147">Si el conector puede asociar esta dirección con un usuario de Microsoft 365, los elementos se importan al buzón de correo del usuario.</span><span class="sxs-lookup"><span data-stu-id="26e16-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="26e16-148">En la página **consentimiento del administrador** , haga clic en el botón **proporcionar consentimiento** .</span><span class="sxs-lookup"><span data-stu-id="26e16-148">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="26e16-149">Se le redirigirá al sitio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="26e16-149">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="26e16-150">Haga clic en **Aceptar** para proporcionar el consentimiento.</span><span class="sxs-lookup"><span data-stu-id="26e16-150">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="26e16-151">La organización debe permitir que el servicio de importación de Office 365 obtenga acceso a los datos de buzones de la organización.</span><span class="sxs-lookup"><span data-stu-id="26e16-151">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="26e16-152">Para proporcionar el consentimiento del administrador, debe haber iniciado sesión con las credenciales de un administrador global de Microsoft 365 y aceptar la solicitud de consentimiento.</span><span class="sxs-lookup"><span data-stu-id="26e16-152">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="26e16-153">Si no ha iniciado sesión como administrador global, puede ir a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e iniciar sesión con las credenciales de administrador global para aceptar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="26e16-153">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="26e16-154">Haga clic en **siguiente** , revise la configuración y vaya a la página **conectores de datos** para ver el progreso del proceso de importación del nuevo conector.</span><span class="sxs-lookup"><span data-stu-id="26e16-154">Click **Next** , review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-ms-sql-database-importer-connector"></a><span data-ttu-id="26e16-155">Paso 4: supervisar el conector del importador de bases de datos de MS SQL</span><span class="sxs-lookup"><span data-stu-id="26e16-155">Step 4: Monitor the MS SQL Database Importer connector</span></span>

<span data-ttu-id="26e16-156">Después de crear el conector del importador de bases de datos MS SQL, puede ver el estado del conector en el centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26e16-156">After you create the MS SQL Database Importer connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="26e16-157">Vaya a <https://compliance.microsoft.com/> y haga clic en **conectores de datos** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="26e16-157">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="26e16-158">Haga clic en la ficha **conectores** y, a continuación, seleccione el conector del **importador** de **bases de datos MS SQL** para mostrar la página de flotante, que contiene las propiedades y la información sobre el conector.</span><span class="sxs-lookup"><span data-stu-id="26e16-158">Click the **Connectors** tab and then select the **MS SQL Database** **Importer** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="26e16-159">En **Estado del conector con origen** , haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector.</span><span class="sxs-lookup"><span data-stu-id="26e16-159">Under **Connector status with source** , click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="26e16-160">Este registro contiene datos que se han importado a la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="26e16-160">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="26e16-161">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26e16-161">Known issues</span></span>

- <span data-ttu-id="26e16-162">En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB.</span><span class="sxs-lookup"><span data-stu-id="26e16-162">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="26e16-163">La compatibilidad con elementos más grandes estará disponible en una fecha posterior.</span><span class="sxs-lookup"><span data-stu-id="26e16-163">Support for larger items will be available at a later date.</span></span>