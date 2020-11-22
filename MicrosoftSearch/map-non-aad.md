---
title: Asignación de identidades que no son de AAD
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Pasos sobre cómo asignar identidades que no sean AAD
ms.openlocfilehash: cd7d0eb17678d69ec1966e4472b38c1f18c30809
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367662"
---
# <a name="map-your-non-azure-ad-identities"></a><span data-ttu-id="493f1-103">Asignar las identidades que no son de Azure AD</span><span class="sxs-lookup"><span data-stu-id="493f1-103">Map your non-Azure AD Identities</span></span>  

<span data-ttu-id="493f1-104">Este artículo le guiará por los pasos necesarios para asignar sus identidades que no son de Azure AD a sus identidades de Azure AD, de modo que los usuarios de la lista de control de acceso (ACL) con identidades que no son de Azure AD puedan ver los resultados de la búsqueda del conector en su ámbito.</span><span class="sxs-lookup"><span data-stu-id="493f1-104">This article walks you through the steps of mapping your non-Azure AD identities to your Azure AD identities so that people in your Access Control List (ACL) with non-Azure AD identities can see connector search results scoped to them.</span></span>

<span data-ttu-id="493f1-105">Estos pasos solo son relevantes para los administradores de búsqueda que configuran los conectores de [ServiceNow](servicenow-connector.md) o [Salesforce](salesforce-connector.md) por Microsoft con los permisos de búsqueda de "solo personas con acceso a este origen de datos" y el tipo de identidad "no es AAD".</span><span class="sxs-lookup"><span data-stu-id="493f1-105">These steps are only relevant to search administrators who are setting up a [ServiceNow](servicenow-connector.md) or [Salesforce](salesforce-connector.md) connectors by Microsoft with search permissions for "Only people with access to this data source" and identity type "Non-AAD."</span></span>

>[!NOTE]
><span data-ttu-id="493f1-106">Si está configurando un conector de Salesforce y **solo selecciona personas con acceso a este origen de datos y el** tipo de identidad **AAD** en la pantalla de permisos de búsqueda, consulte el artículo [map Your Identities de Azure ad](map-aad.md) para conocer los pasos sobre cómo asignar identidades de Azure ad.</span><span class="sxs-lookup"><span data-stu-id="493f1-106">If you are setting up a Salesforce connector and select **Only people with access to this data source** and identity type **AAD** on the search permissions screen, refer to the [Map your Azure AD Identities](map-aad.md) article for steps on how to map Azure AD identities.</span></span>  

## <a name="steps-for-mapping-your-non-azure-ad-properties"></a><span data-ttu-id="493f1-107">Pasos para asignar las propiedades que no son de Azure AD</span><span class="sxs-lookup"><span data-stu-id="493f1-107">Steps for mapping your non-Azure AD properties</span></span>

### <a name="1-select-an-azure-ad-user-property"></a><span data-ttu-id="493f1-108">1. seleccionar una propiedad de usuario de Azure AD</span><span class="sxs-lookup"><span data-stu-id="493f1-108">1. Select an Azure AD user property</span></span>  

<span data-ttu-id="493f1-109">Puede seleccionar la propiedad de usuario de Azure AD para la que está creando la asignación.</span><span class="sxs-lookup"><span data-stu-id="493f1-109">You can select the Azure AD user property you are creating the mapping for.</span></span> <span data-ttu-id="493f1-110">Esta es la propiedad de destino de la que pretende asignar las identidades que no son de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="493f1-110">This is the target property you are aiming to map your non-Azure AD identities to.</span></span>  

<span data-ttu-id="493f1-111">Puede seleccionar una de las siguientes propiedades de Azure AD:</span><span class="sxs-lookup"><span data-stu-id="493f1-111">You can select one of the following Azure AD properties:</span></span>

| <span data-ttu-id="493f1-112">Propiedad de Azure AD</span><span class="sxs-lookup"><span data-stu-id="493f1-112">Azure AD property</span></span>    | <span data-ttu-id="493f1-113">Definición</span><span class="sxs-lookup"><span data-stu-id="493f1-113">Definition</span></span>           | <span data-ttu-id="493f1-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="493f1-114">Example</span></span>         |
| :------------------- | :------------------- |:--------------- |
| <span data-ttu-id="493f1-115">Nombre principal de usuario (UPN)</span><span class="sxs-lookup"><span data-stu-id="493f1-115">User Principal Name (UPN)</span></span>  | <span data-ttu-id="493f1-116">Un UPN consta de un prefijo UPN (el nombre de la cuenta de usuario) y un sufijo UPN (un nombre de dominio DNS).</span><span class="sxs-lookup"><span data-stu-id="493f1-116">A UPN consists of a UPN prefix (the user account name) and a UPN suffix (a DNS domain name).</span></span> <span data-ttu-id="493f1-117">El prefijo se une con el sufijo mediante el símbolo "@".</span><span class="sxs-lookup"><span data-stu-id="493f1-117">The prefix is joined with the suffix using the "@" symbol.</span></span> | <span data-ttu-id="493f1-118">us1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="493f1-118">us1@contoso.onmicrosoft.com</span></span> |
| <span data-ttu-id="493f1-119">IDENTIFICADOR de Azure AD</span><span class="sxs-lookup"><span data-stu-id="493f1-119">Azure AD ID</span></span>                 | <span data-ttu-id="493f1-120">Un identificador de Azure AD para un usuario determinado es el único GUID del usuario.</span><span class="sxs-lookup"><span data-stu-id="493f1-120">An Azure AD ID for a given user is the unique GUID of the user.</span></span>                 | <span data-ttu-id="493f1-121">58006c96-9e6e-45ea-8c88-4a56851eefad</span><span class="sxs-lookup"><span data-stu-id="493f1-121">58006c96-9e6e-45ea-8c88-4a56851eefad</span></span>            |
| <span data-ttu-id="493f1-122">IDENTIFICADOR de seguridad (SID) de Active Directory</span><span class="sxs-lookup"><span data-stu-id="493f1-122">Active Directory Security ID (SID)</span></span>                  | <span data-ttu-id="493f1-123">El SID (identificador de seguridad) es un identificador único que Active Directory usa para identificar objetos como entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="493f1-123">SID (Security Identifier) is a unique identifier that Active Directory uses to identify objects as security principal.</span></span>                  | <span data-ttu-id="493f1-124">S-1-5-21-453406510-812318184-4183662089</span><span class="sxs-lookup"><span data-stu-id="493f1-124">S-1-5-21-453406510-812318184-4183662089</span></span>             |

### <a name="2-select-non-azure-ad-user-properties-to-map"></a><span data-ttu-id="493f1-125">2. Seleccione las propiedades de usuario que no son de Azure AD para asignar</span><span class="sxs-lookup"><span data-stu-id="493f1-125">2. Select non-Azure AD user properties to map</span></span>

<span data-ttu-id="493f1-126">Puede seleccionar las propiedades que no son de Azure AD extraídas del origen de datos para aplicar expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="493f1-126">You can select non-Azure AD properties pulled from your data source to apply regular expressions on.</span></span> <span data-ttu-id="493f1-127">Para obtener más información sobre dónde encontrar estas propiedades en su origen de datos, consulte las páginas de [ServiceNow](servicenow-connector.md) y [Salesforce](salesforce-connector.md) .</span><span class="sxs-lookup"><span data-stu-id="493f1-127">To learn more about where to find these properties in your data source, see the [ServiceNow](servicenow-connector.md) and [Salesforce](salesforce-connector.md) pages.</span></span>  

<span data-ttu-id="493f1-128">Puede seleccionar una propiedad de usuario que no sea de Azure AD en la lista desplegable y proporcionar una expresión regular que se aplicará a esos valores de propiedad de usuario.</span><span class="sxs-lookup"><span data-stu-id="493f1-128">You can select a non-Azure AD user property from the dropdown and provide a regular expression to be applied on those user property values.</span></span> <span data-ttu-id="493f1-129">Para obtener más información acerca de las expresiones regulares, consulte [referencia de expresiones regulares]( https://docs.microsoft.com/dotnet/standard/base-types/regular-expression-language-quick-reference).</span><span class="sxs-lookup"><span data-stu-id="493f1-129">To learn more about regular expressions, see [regular expression reference]( https://docs.microsoft.com/dotnet/standard/base-types/regular-expression-language-quick-reference).</span></span>  

<span data-ttu-id="493f1-130">A continuación se muestran algunos ejemplos de expresiones regulares y sus salidas que se aplican a una cadena de muestra:</span><span class="sxs-lookup"><span data-stu-id="493f1-130">Below are some examples of regular expressions and their outputs applied to a sample string:</span></span> 

| <span data-ttu-id="493f1-131">Cadena de muestra</span><span class="sxs-lookup"><span data-stu-id="493f1-131">Sample String</span></span>                  | <span data-ttu-id="493f1-132">Expresión regular</span><span class="sxs-lookup"><span data-stu-id="493f1-132">Regular expression</span></span>                 | <span data-ttu-id="493f1-133">Resultado de la expresión regular de la cadena de muestra</span><span class="sxs-lookup"><span data-stu-id="493f1-133">Output of regular expression on sample string</span></span>           |
| :------------------- | :------------------- |:---------------|
| <span data-ttu-id="493f1-134">Alexis Vasquez</span><span class="sxs-lookup"><span data-stu-id="493f1-134">Alexis Vasquez</span></span>  | <span data-ttu-id="493f1-135">.\*</span><span class="sxs-lookup"><span data-stu-id="493f1-135">.\*</span></span> | <span data-ttu-id="493f1-136">Alexis Vasquez</span><span class="sxs-lookup"><span data-stu-id="493f1-136">Alexis Vasquez</span></span> |
| <span data-ttu-id="493f1-137">Alexis Vasquez</span><span class="sxs-lookup"><span data-stu-id="493f1-137">Alexis Vasquez</span></span>                 | <span data-ttu-id="493f1-138">..$</span><span class="sxs-lookup"><span data-stu-id="493f1-138">..$</span></span>                 | <span data-ttu-id="493f1-139">Easy</span><span class="sxs-lookup"><span data-stu-id="493f1-139">ez</span></span>            |
| <span data-ttu-id="493f1-140">Alexis Vasquez</span><span class="sxs-lookup"><span data-stu-id="493f1-140">Alexis Vasquez</span></span>                  | <span data-ttu-id="493f1-141">(\w +) $</span><span class="sxs-lookup"><span data-stu-id="493f1-141">(\w+)$</span></span>                  | <span data-ttu-id="493f1-142">Vasquez</span><span class="sxs-lookup"><span data-stu-id="493f1-142">Vasquez</span></span>             |

<span data-ttu-id="493f1-143">Puede Agregar tantas propiedades de usuario que no sean de Azure AD como quiera que sean expresiones.</span><span class="sxs-lookup"><span data-stu-id="493f1-143">You can add as many non-Azure AD user properties as you would like expressions for.</span></span> <span data-ttu-id="493f1-144">Puede aplicar diferentes expresiones regulares a la misma propiedad de usuario si la fórmula final garantiza que.</span><span class="sxs-lookup"><span data-stu-id="493f1-144">You can apply different regular expressions to the same user property if your final formula warrants that.</span></span>  

### <a name="3-create-formula-to-complete-mapping"></a><span data-ttu-id="493f1-145">3. crear una fórmula para completar la asignación</span><span class="sxs-lookup"><span data-stu-id="493f1-145">3. Create formula to complete mapping</span></span>

<span data-ttu-id="493f1-146">Puede combinar los resultados de las expresiones regulares aplicadas a cada una de las propiedades de usuario que no sean de Azure AD para formar la propiedad de Azure AD seleccionada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="493f1-146">You can combine the outputs of the regular expressions applied to each of your non-Azure AD user properties to form the Azure AD property selected in step 1.</span></span>

<span data-ttu-id="493f1-147">En el cuadro de fórmula, " {0} " corresponde a la salida de la expresión regular aplicada a la *primera* propiedad que no es de Azure ad que seleccionó.</span><span class="sxs-lookup"><span data-stu-id="493f1-147">In the formula box, "{0}" corresponds to the output of the regular expression applied to the *first* non-Azure AD property you selected.</span></span> <span data-ttu-id="493f1-148">" {1} " corresponde a la salida de la expresión regular aplicada a la *segunda* propiedad que no es de Azure ad que haya seleccionado.</span><span class="sxs-lookup"><span data-stu-id="493f1-148">"{1}" corresponds to the output of the regular expression applied to the *second* non-Azure AD property you selected.</span></span> <span data-ttu-id="493f1-149">" {2} " corresponde a la salida de la expresión regular aplicada a la *tercera* propiedad que no es de Azure ad, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="493f1-149">"{2}" corresponds to the output of the regular expression applied to the *third* non-Azure AD property, and so on.</span></span>  

<span data-ttu-id="493f1-150">A continuación se muestran algunos ejemplos de fórmulas con salidas de expresión regular de ejemplo y resultados de fórmulas:</span><span class="sxs-lookup"><span data-stu-id="493f1-150">Below are some examples of formulas with sample regular expression outputs and formula outputs:</span></span> 

| <span data-ttu-id="493f1-151">Fórmula de ejemplo</span><span class="sxs-lookup"><span data-stu-id="493f1-151">Sample formula</span></span>                  | <span data-ttu-id="493f1-152">Valor de {0} en usuario de ejemplo</span><span class="sxs-lookup"><span data-stu-id="493f1-152">Value of {0} on sample user</span></span>                 | <span data-ttu-id="493f1-153">Valor de {1} en usuario de ejemplo</span><span class="sxs-lookup"><span data-stu-id="493f1-153">Value of {1} on sample user</span></span>           | <span data-ttu-id="493f1-154">Resultado de la fórmula</span><span class="sxs-lookup"><span data-stu-id="493f1-154">Output of formula</span></span>                  |
| :------------------- | :------------------- |:---------------|:---------------|
| <span data-ttu-id="493f1-155">{0}.{1} @contoso. com</span><span class="sxs-lookup"><span data-stu-id="493f1-155">{0}.{1}@contoso.com</span></span>  | <span data-ttu-id="493f1-156">Name</span><span class="sxs-lookup"><span data-stu-id="493f1-156">firstname</span></span> | <span data-ttu-id="493f1-157">Apellido</span><span class="sxs-lookup"><span data-stu-id="493f1-157">lastname</span></span> |<span data-ttu-id="493f1-158">firstname.lastname@contoso.com</span><span class="sxs-lookup"><span data-stu-id="493f1-158">firstname.lastname@contoso.com</span></span>
| <span data-ttu-id="493f1-159">{0}@domain. com</span><span class="sxs-lookup"><span data-stu-id="493f1-159">{0}@domain.com</span></span>                 | <span data-ttu-id="493f1-160">identificado</span><span class="sxs-lookup"><span data-stu-id="493f1-160">userid</span></span>                 |             |<span data-ttu-id="493f1-161">userid@domain.com</span><span class="sxs-lookup"><span data-stu-id="493f1-161">userid@domain.com</span></span>

<span data-ttu-id="493f1-162">Después de proporcionar la fórmula, puede hacer clic opcionalmente en **vista previa** para ver una vista previa de 5 usuarios aleatorios del origen de datos con sus correspondientes asignaciones de usuario aplicadas.</span><span class="sxs-lookup"><span data-stu-id="493f1-162">After you provide your formula, you can optionally click **Preview** to see a preview of 5 random users from your data source with their respective user mappings applied.</span></span> <span data-ttu-id="493f1-163">El resultado de la vista previa incluye el valor de las propiedades de usuario que no son de Azure AD seleccionadas en el paso 2 para esos usuarios y el resultado de la fórmula final que se proporciona en el paso 3 para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="493f1-163">The output of the preview includes the value of the non-Azure AD user properties selected in step 2 for those users and the output of the final formula provided in step 3 for that user.</span></span> <span data-ttu-id="493f1-164">También indica si los resultados de la fórmula podrían resolverse en un usuario de Azure AD del espacio empresarial a través de un icono de "éxito" o "error".</span><span class="sxs-lookup"><span data-stu-id="493f1-164">It also indicates whether the output of the formula could be resolved to an Azure AD user in your tenant via a "Success" or "Failed" icon.</span></span>  

>[!NOTE]
><span data-ttu-id="493f1-165">Todavía puede continuar con la creación de la conexión si una o más asignaciones de usuario tienen el estado "error" después de hacer clic en **vista previa**.</span><span class="sxs-lookup"><span data-stu-id="493f1-165">You can still proceed with creating your connection if one or more user mappings have a "Failed" status after you click **Preview**.</span></span> <span data-ttu-id="493f1-166">La vista previa muestra 5 usuarios aleatorios y sus asignaciones desde el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="493f1-166">The preview shows 5 random users and their mappings from your data source.</span></span> <span data-ttu-id="493f1-167">Si la asignación que proporciona no asigna todos los usuarios, es posible que experimente este caso.</span><span class="sxs-lookup"><span data-stu-id="493f1-167">If the mapping you provide does not map all users, you may experience this case.</span></span>

## <a name="sample-non-azure-ad-mapping"></a><span data-ttu-id="493f1-168">Ejemplo de asignación que no es de Azure AD</span><span class="sxs-lookup"><span data-stu-id="493f1-168">Sample non-Azure AD mapping</span></span>

<span data-ttu-id="493f1-169">Vea la siguiente instantánea para obtener una muestra de asignación que no es de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="493f1-169">See the snapshot below for a sample non-Azure AD mapping.</span></span>

![Instantánea de ejemplo de cómo rellenar la página de asignación que no es de Azure AD](media/non-aad-mapping.png)

## <a name="limitations"></a><span data-ttu-id="493f1-171">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="493f1-171">Limitations</span></span>  

- <span data-ttu-id="493f1-172">Solo se admite una asignación para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="493f1-172">Only one mapping is supported for all users.</span></span> <span data-ttu-id="493f1-173">No se admiten las asignaciones condicionales.</span><span class="sxs-lookup"><span data-stu-id="493f1-173">Conditional mappings are not supported.</span></span>  

- <span data-ttu-id="493f1-174">No puede cambiar la asignación una vez publicada la conexión.</span><span class="sxs-lookup"><span data-stu-id="493f1-174">You cannot change your mapping once the connection is published.</span></span>  

- <span data-ttu-id="493f1-175">Actualmente solo se admiten expresiones de Regex basadas en las propiedades de usuario no AAD para la transformación.</span><span class="sxs-lookup"><span data-stu-id="493f1-175">Only regex-based expressions against the non-AAD user properties are currently supported for the transformation.</span></span>

- <span data-ttu-id="493f1-176">Solo hay 3 identidades de Azure AD a las que puede elegir asignar (UPN, identificador de Azure AD y SID de AD).</span><span class="sxs-lookup"><span data-stu-id="493f1-176">There are only 3 Azure AD identities you can choose to map to (UPN, Azure AD ID, and AD SID).</span></span>