---
title: Configurar **Búsqueda de Microsoft**
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 04/30/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar Búsqueda de Microsoft por primera vez.
ms.openlocfilehash: 703b9c6ab1213fa06f3d959a0e29a9b757e2b2c9
ms.sourcegitcommit: aeb44797427bd39c133fa899ab77277dd90fe47b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "33970134"
---
# <a name="set-up-microsoft-search"></a><span data-ttu-id="b8ced-103">Configurar Búsqueda de Microsoft</span><span class="sxs-lookup"><span data-stu-id="b8ced-103">Set up Microsoft Search</span></span>

<span data-ttu-id="b8ced-104">**Búsqueda de Microsoft** ofrece una interfaz intuitiva para ayudar a los usuarios a encontrar información como archivos y documentos, sitios internos y herramientas empresariales, personas y grupos, ubicaciones y direcciones, conversaciones y respuestas mediante un acceso seguro a todas las fuentes de datos, incluidos correos electrónicos, archivos, archivos de SharePoint, contenidos de OneDrive y otros recursos compartidos, así como de internet en la organización del usuario.</span><span class="sxs-lookup"><span data-stu-id="b8ced-104">**Microsoft Search** provides a user-friendly interface to help users find information, like files and documents, internal sites and business tools, people and groups, locations and directions, conversations and answers by securely accessing all data sources, including emails, files, SharePoint files, OneDrive content, and other shared resources as well as the internet in the user’s organization.</span></span>

<span data-ttu-id="b8ced-105">Para obtener más información sobre las características de **Búsqueda de Microsoft**, consulte [Introducción a Búsqueda de Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="b8ced-105">To learn more about **Microsoft Search** features, see [Microsoft Search Overview](overview-microsoft-search.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="b8ced-106">Introducción</span><span class="sxs-lookup"><span data-stu-id="b8ced-106">Get Started</span></span>

<span data-ttu-id="b8ced-107">**Búsqueda de Microsoft** está activado de forma predeterminada para todas las aplicaciones de Microsoft compatibles, como parte de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8ced-107">**Microsoft Search** is turned on by default for all Microsoft apps that supports it, as a part of Microsoft 365.</span></span> <span data-ttu-id="b8ced-108">Todo lo que un usuario debe hacer es iniciar sesión con una cuenta profesional o educativa y usar un explorador con Bing como proveedor de búsquedas predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b8ced-108">All a user needs to do is to sign-in with a work or school account and use a browser with Bing set as the default search provider.</span></span>

<span data-ttu-id="b8ced-109">Usted administra **Búsqueda de Microsoft** desde el **Centro de administración de Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="b8ced-109">You administer **Microsoft Search** from **Microsoft 365 admin center**.</span></span> <span data-ttu-id="b8ced-110">Inicie sesión con las credenciales de administrador, seleccione el icono **Administrador** en **Iniciador de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="b8ced-110">Sign in using your login with admin credentials, select **Admin** tile in **App launcher**.</span></span> <span data-ttu-id="b8ced-111">En el **Centro de administración de Microsoft 365**, seleccione **Búsqueda de Microsoft** en **Configuración** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="b8ced-111">In **Microsoft 365 admin center**, select **Microsoft Search** under **Settings** in the left navigation panel.</span></span> 

<span data-ttu-id="b8ced-112">**Nota:** si se muestra el portal de administración antiguo y quiere cambiar al nuevo centro de administración, active la opción **Probar la versión preliminar** en la esquina superior derecha del centro de administración.</span><span class="sxs-lookup"><span data-stu-id="b8ced-112">**Note:** If you are seeing the legacy admin portal and want to switch to the new admin center, turn on the **Try the preview** switch in the right top corner of admin center.</span></span> 

<span data-ttu-id="b8ced-113">Como administrador debe considerar algunas cosas que pueden hacer que la experiencia de **Búsqueda de Microsoft** en su organización sea eficiente e intuitiva.</span><span class="sxs-lookup"><span data-stu-id="b8ced-113">However, as an administrator you should consider a few things that can make the **Microsoft Search** experience efficient and user friendly in your organization.</span></span>

### <a name="step-1-check-access-level-of-your-users"></a><span data-ttu-id="b8ced-114">Paso 1: Compruebe el nivel de acceso de los usuarios</span><span class="sxs-lookup"><span data-stu-id="b8ced-114">Step 1: Check access level of your users</span></span>

<span data-ttu-id="b8ced-115">**Búsqueda de Microsoft** respeta la configuración de seguridad del origen de contenido.</span><span class="sxs-lookup"><span data-stu-id="b8ced-115">**Microsoft Search** respects security settings of the content source.</span></span> <span data-ttu-id="b8ced-116">Lo que los usuarios ven en los resultados de búsqueda depende de sus permisos y niveles de acceso.</span><span class="sxs-lookup"><span data-stu-id="b8ced-116">What users see in their search result depends on their permissions and access levels.</span></span> <span data-ttu-id="b8ced-117">Revise el nivel de acceso de los usuarios de su organización para asegurarse de que los usuarios solo encuentran el contenido al que tienen permiso para acceder.</span><span class="sxs-lookup"><span data-stu-id="b8ced-117">Review the access level of users in your organization to make sure that users only find content that they are allowed to access.</span></span>

<span data-ttu-id="b8ced-118">Obtenga más información sobre [planificación de permisos](https://docs.microsoft.com/es-ES/sharepoint/plan-your-permissions-strategy) y [crear niveles de permisos](https://docs.microsoft.com/es-ES/sharepoint/how-to-create-and-edit-permission-levels).</span><span class="sxs-lookup"><span data-stu-id="b8ced-118">Learn more about [planning permissions](https://docs.microsoft.com/es-ES/sharepoint/plan-your-permissions-strategy) and [creating permissions levels](https://docs.microsoft.com/es-ES/sharepoint/how-to-create-and-edit-permission-levels).</span></span>

### <a name="step-2-assign-search-admin-and-search-editor"></a><span data-ttu-id="b8ced-119">Paso 2: Asigne el Administrador de búsqueda y el Editor de búsqueda</span><span class="sxs-lookup"><span data-stu-id="b8ced-119">Step 2: Assign Search admin and Search editor</span></span>

<span data-ttu-id="b8ced-120">Hay dos nuevos roles en el **Centro de administración de Microsoft**: el Administrador de búsqueda y el Editor de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b8ced-120">There are two new roles in **Microsoft admin center** – Search administrator and Search editor.</span></span>  <span data-ttu-id="b8ced-121">El Administrador global, que tiene todos los privilegios, asigna roles de administrador a los usuarios, incluido el rol de Administrador de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b8ced-121">Global admin, who has full privileges, assigns admin roles to users including the role of Search administrator.</span></span> <span data-ttu-id="b8ced-122">Los Administradores de búsqueda pueden delegar los roles de Administrador de búsqueda y Editor de búsqueda a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="b8ced-122">Search administrators can delegate the Search administrator or Search editor roles to other users.</span></span> <span data-ttu-id="b8ced-123">Para obtener más información sobre los varios roles de administrador, vea [Roles de administrador de Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="b8ced-123">For more information on different admin roles, see [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span>

<span data-ttu-id="b8ced-124">**Nota:** estos dos roles nuevos, el Administrador de búsqueda y el Editor de búsqueda, están disponibles solo en el **Centro de administración de Microsoft 365**, no en el portal de administración antiguo.</span><span class="sxs-lookup"><span data-stu-id="b8ced-124">**Note:** These two new roles – Search admin and Search editor – are available in **Microsoft 365 admin center** only, not in the legacy admin portal.</span></span> 

<span data-ttu-id="b8ced-125">Los administradores de búsqueda influyen directamente en la experiencia de búsqueda para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="b8ced-125">Search administrators directly influence the search experience for end users.</span></span> <span data-ttu-id="b8ced-126">Esto incluye la elección de los tipos de resultados que quiere que se muestren a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b8ced-126">This includes choosing the types of results you want to surface to your users.</span></span> <span data-ttu-id="b8ced-127">Puede resultar difícil para una sola persona elegir y crear contenido relevante para los muchos y diferentes temas que los usuarios buscan en una organización.</span><span class="sxs-lookup"><span data-stu-id="b8ced-127">It may be difficult for one person to choose and create authoritative content on many different topics that users search for in an organization.</span></span> <span data-ttu-id="b8ced-128">Le recomendamos que aproveche la experiencia y los conocimientos de otros usuarios agregándolos como editores.</span><span class="sxs-lookup"><span data-stu-id="b8ced-128">We recommend that you leverage the expertise and knowledge of SMEs and other users by adding them as editors.</span></span> 

<span data-ttu-id="b8ced-129">En **Búsqueda de Microsoft**, puede administrar la configuración de búsqueda de su organización y contenido con dos nuevas funciones:</span><span class="sxs-lookup"><span data-stu-id="b8ced-129">In **Microsoft Search**, you can manage your organization’s search settings and content using two new roles:</span></span>
1. <span data-ttu-id="b8ced-130">**Administrador de búsqueda:** este rol puede crear y administrar el contenido de los resultados de búsqueda y definir la configuración de consulta para mejorar los resultados de búsqueda en la organización.</span><span class="sxs-lookup"><span data-stu-id="b8ced-130">**Search admin:** This role can create and manage search result content and define query settings for improved search results within the organization.</span></span> <span data-ttu-id="b8ced-131">El administrador de búsqueda controla la configuración de **Búsqueda de Microsoft** y designa a los Editores de búsqueda, que crean contenido.</span><span class="sxs-lookup"><span data-stu-id="b8ced-131">Search administrator manages the **Microsoft Search** configuration and designates Search editors to create content.</span></span>
2. <span data-ttu-id="b8ced-132">**Editor de búsqueda:** crea, administra y elimina el contenido de **Búsqueda de Microsoft** en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8ced-132">**Search editor:** Creates, manages, and deletes content for **Microsoft Search** in the Microsoft 365 admin center.</span></span> <span data-ttu-id="b8ced-133">Este rol puede crear y administrar contenido editorial como preguntas más frecuentes, lugares y ubicaciones importantes, lugares y ubicaciones frecuentemente buscados, sitios y aplicaciones frecuentemente buscados y usados, etc. Sin embargo, no tiene acceso a la administración de la configuración de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b8ced-133">This role can create and manage editorial content such as frequently asked questions and answers, important places and locations, frequently searched and used sites and apps, etc. They, however, do not have access to manage search settings.</span></span>

<span data-ttu-id="b8ced-134">Para asignar roles de administrador, consulte [Asignar derechos de administrador en Office 365 para empresas](https://docs.microsoft.com/en-us/office365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="b8ced-134">For assigning admin roles, see [Assign admin rights in Office 365 for business](https://docs.microsoft.com/en-us/office365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span></span>

### <a name="step-3-make-content-easy-to-find"></a><span data-ttu-id="b8ced-135">Paso 3: Haga el contenido fácil de encontrar</span><span class="sxs-lookup"><span data-stu-id="b8ced-135">Step 3: Make content easy to find</span></span> 

<span data-ttu-id="b8ced-136">**Búsqueda de Microsoft** proporciona a los administradores herramientas que pueden usar para crear una óptima experiencia de búsqueda para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b8ced-136">**Microsoft Search** provides administrators with tools that they can use to build a robust search experience for their users.</span></span> <span data-ttu-id="b8ced-137">En **Búsqueda de Microsoft**, los administradores tienen tres contenidos de búsqueda diferentes, que pueden crear para una mejor experiencia de búsqueda y mejorar la facilidad para encontrar contenido:</span><span class="sxs-lookup"><span data-stu-id="b8ced-137">In **Microsoft Search**, administrators have three different search contents that they can create for a better search experience and to improve the findability of content:</span></span>
- <span data-ttu-id="b8ced-138">**Marcador:** los marcadores son similares a los resultados promocionados en SharePoint y ayudan a aumentar los mejores resultados posibles para las consultas de sus usuarios en la parte superior de los resultados de búsqueda y facilitar a los usuarios encontrar sitios internos importantes.</span><span class="sxs-lookup"><span data-stu-id="b8ced-138">**Bookmark:**  Bookmarks are similar to promoted results in SharePoint and help promote the best possible results for your user's queries to the top of the search results and make it easy for your users to find important internal sites.</span></span> 
- <span data-ttu-id="b8ced-139">**Preguntas y respuestas:** las preguntas y respuestas son similares a las preguntas frecuentes; se suelen presentar en un formato de pregunta y respuesta.</span><span class="sxs-lookup"><span data-stu-id="b8ced-139">**Questions & Answers:** Q&A are similar to frequently asked questions and these are usually in a question and answer format.</span></span> <span data-ttu-id="b8ced-140">Las preguntas y respuestas proporcionan la mejor respuesta posible para las preguntas de los usuarios en relación con el trabajo.</span><span class="sxs-lookup"><span data-stu-id="b8ced-140">It provides the best possible answer(s) to your user's work-related questions.</span></span>
- <span data-ttu-id="b8ced-141">**Ubicación:** las ubicaciones son direcciones que ayudan a los usuarios a localizar edificios, oficinas, campus, etc., de su organización.</span><span class="sxs-lookup"><span data-stu-id="b8ced-141">**Location:** Location are addresses that help users locate your organization's buildings, offices, campuses.</span></span> 

<span data-ttu-id="b8ced-142">Cuantos más marcadores, preguntas y respuestas, y ubicaciones publique, mayores serán el valor y los beneficios para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b8ced-142">The more Bookmarks, Q&A, and Locations you have, the more value and benefit you add for users.</span></span> <span data-ttu-id="b8ced-143">Sin embargo, muchos de ellos pueden añadir una sobrecarga sustancial a la gestión, puesto que deben ser revisados y actualizados periódicamente para que los resultados sigan siendo relevantes y actualizados.</span><span class="sxs-lookup"><span data-stu-id="b8ced-143">However, too many of them can add a substantial management overhead as they must be reviewed and updated periodically to keep the results relevant and up to date.</span></span>

<span data-ttu-id="b8ced-144">Estos son algunos ejemplos de contenido que debería considerar como marcadores para los usuarios:</span><span class="sxs-lookup"><span data-stu-id="b8ced-144">Here are some examples of content that you should consider bookmarking for your users:</span></span>
- <span data-ttu-id="b8ced-145">Información de producto, servicio u organización.</span><span class="sxs-lookup"><span data-stu-id="b8ced-145">Organization or product or service information.</span></span>
- <span data-ttu-id="b8ced-146">Contenido informativo que está disponible para todos los usuarios; Por ejemplo, información de la compañía, ayuda para las aplicaciones de Office y Windows, etc.</span><span class="sxs-lookup"><span data-stu-id="b8ced-146">Informational content that is available for everyone; for example, information about the company, help for Windows and Office apps, etc.</span></span> 
- <span data-ttu-id="b8ced-147">Contenido que las personas de la organización buscan generalmente en su trabajo cotidiano.</span><span class="sxs-lookup"><span data-stu-id="b8ced-147">Content that people in the organization generally search for in their day-to-day work.</span></span> <span data-ttu-id="b8ced-148">Las búsquedas comunes relacionadas con el trabajo incluyen prestaciones, informes de horas y gastos, envíos de pedidos de compra y cómo obtener ayuda del departamento de TI.</span><span class="sxs-lookup"><span data-stu-id="b8ced-148">Common work-related searches include employee benefits, time and expense reporting, submitting purchase orders, and getting help from IT services.</span></span> 

<span data-ttu-id="b8ced-149">Para crear y administrar el contenido de la búsqueda, consulte [Hacer que el contenido sea fácil de encontrar](make-content-easy-to-find.md).</span><span class="sxs-lookup"><span data-stu-id="b8ced-149">For creating and managing search content, see [Making content easy to find](make-content-easy-to-find.md).</span></span>

### <a name="step-4-test-single-sign-on"></a><span data-ttu-id="b8ced-150">Paso 4: Prueba de inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="b8ced-150">Step 4: Test single sign-on</span></span>
<span data-ttu-id="b8ced-151">**Búsqueda de Microsoft** usa Azure Active Directory (AAD) para autenticar y autorizar el acceso a datos de su organización.</span><span class="sxs-lookup"><span data-stu-id="b8ced-151">**Microsoft Search** uses Azure Active Directory (AAD) to authenticate and authorize access to your organization’s data.</span></span>  <span data-ttu-id="b8ced-152">Esto significa que sus usuarios inician sesión automáticamente en su cuenta profesional o educativa cuando usted ha iniciado sesión en una aplicación de Office 365 o en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b8ced-152">This means your users are automatically signed in with your work or school account when you've signed into an Office 365 app or Windows 10.</span></span>

<span data-ttu-id="b8ced-153">Se recomienda que los usuarios de **Búsqueda de Microsoft** usen el inicio de sesión único, ya que reduce el número de veces que se pide a los usuarios que inicien sesión.</span><span class="sxs-lookup"><span data-stu-id="b8ced-153">We recommend that **Microsoft Search** users use single sign-on as it reduces the number of times users are prompted to sign in.</span></span> <span data-ttu-id="b8ced-154">Los administradores deben probar el inicio de sesión único con un grupo pequeño de usuarios, lo que les ayudará a identificar cualquier problema de configuración que genere bloqueos.</span><span class="sxs-lookup"><span data-stu-id="b8ced-154">Administrators should test single sign-on with a small group of users to help identify any blocking configuration issues.</span></span> 

<span data-ttu-id="b8ced-155">Para los usuarios de Chrome en Windows 10, el inicio de sesión único solo funcionará si la extensión de inicio de sesión de Windows 10 y AAD para Chrome están instalados.</span><span class="sxs-lookup"><span data-stu-id="b8ced-155">For Chrome users on Windows 10, single sign-in works only when the Windows 10 and AAD sign-in extension for Chrome is installed.</span></span> <span data-ttu-id="b8ced-156">Una vez instalados, use la extensión de Chrome para autenticar fácilmente con AAD al iniciar sesión en sitios compatibles, incluidos Office 365 y Bing.</span><span class="sxs-lookup"><span data-stu-id="b8ced-156">Once installed, you can use the Chrome extension to easily authenticate with AAD when signing in to supported sites, including Office 365 and Bing.</span></span> <span data-ttu-id="b8ced-157">Esta función está disponible solo para usuarios autorizados.</span><span class="sxs-lookup"><span data-stu-id="b8ced-157">This functionality is available for authorized users only.</span></span> 

<span data-ttu-id="b8ced-158">Para descargar e instalar Windows 10 y la extensión de inicio de sesión de AAD para Chrome, vaya a la [Chrome Web Store](https://go.microsoft.com/fwlink/?linkid=2090961).</span><span class="sxs-lookup"><span data-stu-id="b8ced-158">To download and install Windows 10 and AAD sign-in extension for Chrome, go to [Chrome Web Store](https://go.microsoft.com/fwlink/?linkid=2090961).</span></span>

### <a name="step-5-training-and-communication"></a><span data-ttu-id="b8ced-159">Paso 5: Formación y comunicación</span><span class="sxs-lookup"><span data-stu-id="b8ced-159">Step 5: Training and communication</span></span>
<span data-ttu-id="b8ced-160">Establezca recursos de autoservicio a los que los empleados puedan acceder fácilmente por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="b8ced-160">Establish self-service resources that employees can easily access on their own.</span></span> <span data-ttu-id="b8ced-161">Esto le ayudará a reducir la carga general sobre usted y sobre su equipo distribuyendo constantemente comunicaciones y asistiendo a la autoformación de los empleados.</span><span class="sxs-lookup"><span data-stu-id="b8ced-161">This will help reduce the overall burden on you and your team to constantly push communications and assist in self-training and educating employees.</span></span> <span data-ttu-id="b8ced-162">Proporcione a sus usuarios comunicaciones, preguntas frecuentes, vídeos y formación en vídeo o seminarios web.</span><span class="sxs-lookup"><span data-stu-id="b8ced-162">Provide your users communications, FAQs, videos, and recorded training or webinars.</span></span> <span data-ttu-id="b8ced-163">Estos son algunos vínculos útiles para empezar:</span><span class="sxs-lookup"><span data-stu-id="b8ced-163">Here are some helpful links to start with:</span></span>
- [<span data-ttu-id="b8ced-164">Encuentre lo que necesita con Búsqueda de Microsoft en Office</span><span class="sxs-lookup"><span data-stu-id="b8ced-164">Find what you need with Microsoft Search in Office</span></span>](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446?ui=en-US&rs=en-US&ad=US)
- [<span data-ttu-id="b8ced-165">Centro de aprendizaje de Office 365</span><span class="sxs-lookup"><span data-stu-id="b8ced-165">Office 365 Training Center</span></span>](https://support.office.com/office-training-center)
- <span data-ttu-id="b8ced-166">
  [Búsqueda de Microsoft Center](https://support.office.com/en-us/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc?ui=en-US&rs=en-US&ad=US)</span><span class="sxs-lookup"><span data-stu-id="b8ced-166">[Microsoft Search Center](https://support.office.com/en-us/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc?ui=en-US&rs=en-US&ad=US)</span></span>

### <a name="trying-out-microsoft-search-in-bing"></a><span data-ttu-id="b8ced-167">Probar **Búsqueda de Microsoft** en Bing</span><span class="sxs-lookup"><span data-stu-id="b8ced-167">Trying out **Microsoft Search** in Bing</span></span> 
<span data-ttu-id="b8ced-168">El administrador de **Búsqueda de Microsoft** puede desactivar **Búsqueda de Microsoft** en Bing.</span><span class="sxs-lookup"><span data-stu-id="b8ced-168">**Microsoft Search** administrator can turn **Microsoft Search** off in Bing.</span></span> <span data-ttu-id="b8ced-169">Si lo desactiva, los usuarios no verán el contenido de la organización en las búsquedas de Bing.</span><span class="sxs-lookup"><span data-stu-id="b8ced-169">If turned off, users will not see organization content in Bing search.</span></span> <span data-ttu-id="b8ced-170">De forma predeterminada, **Búsqueda de Microsoft** está activado en Bing.</span><span class="sxs-lookup"><span data-stu-id="b8ced-170">By default, **Microsoft Search** is turned on in Bing.</span></span> <span data-ttu-id="b8ced-171">Le recomendamos que mantenga **Búsqueda de Microsoft** activado en Bing para una mejor experiencia de usuario.</span><span class="sxs-lookup"><span data-stu-id="b8ced-171">We recommend that you keep **Microsoft Search** turned on in Bing for a better user experience.</span></span> 

<span data-ttu-id="b8ced-172">Si desea probar **Búsqueda de Microsoft** en un inquilino de prueba o si desea probar la experiencia de búsqueda antes de que esté disponible para todos los usuarios, puede desactivar **Búsqueda de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="b8ced-172">If you want to tryout **Microsoft Search** on a test tenant or you want to test the search experience before making it available to all users, you can turn off **Microsoft Search**.</span></span>
<span data-ttu-id="b8ced-173">Para activar/desactivar **Búsqueda de Microsoft** en Bing, vaya a **Servicios y complementos** en el **centro de administración de Microsoft 365** y active/desactive **Búsqueda de Microsoft en Bing**.</span><span class="sxs-lookup"><span data-stu-id="b8ced-173">To turn **Microsoft Search** on/off in Bing, go to **Services & add-ins** in **Microsoft 365 admin center** and turn **Microsoft Search in Bing** on/off.</span></span>