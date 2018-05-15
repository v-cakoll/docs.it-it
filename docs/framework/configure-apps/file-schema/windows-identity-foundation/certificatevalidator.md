---
title: '&lt;certificateValidator&gt;'
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: a4663b0c3a2a6965a977a1d551c47de7e13d144b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltcertificatevalidatorgt"></a><span data-ttu-id="1a96c-102">&lt;certificateValidator&gt;</span><span class="sxs-lookup"><span data-stu-id="1a96c-102">&lt;certificateValidator&gt;</span></span>
<span data-ttu-id="1a96c-103">Specifica un tipo personalizzato per la convalida del certificato.</span><span class="sxs-lookup"><span data-stu-id="1a96c-103">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="1a96c-104">Questo tipo viene utilizzato solo se il `certificateValidationMode` attributo del [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) viene impostato su "Custom".</span><span class="sxs-lookup"><span data-stu-id="1a96c-104">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="1a96c-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="1a96c-105">\<system.identityModel></span></span>  
<span data-ttu-id="1a96c-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="1a96c-106">\<identityConfiguration></span></span>  
<span data-ttu-id="1a96c-107">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="1a96c-107">\<certificateValidation></span></span>  
<span data-ttu-id="1a96c-108">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="1a96c-108">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a96c-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a96c-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation>  
      <certificateValidator type=xs:string>  
      </certificateValidator>  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a96c-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1a96c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1a96c-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1a96c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a96c-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="1a96c-112">Attributes</span></span>  
  
|<span data-ttu-id="1a96c-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="1a96c-113">Attribute</span></span>|<span data-ttu-id="1a96c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1a96c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1a96c-115">tipo</span><span class="sxs-lookup"><span data-stu-id="1a96c-115">type</span></span>|<span data-ttu-id="1a96c-116">Specifica un tipo personalizzato da cui deriva il <xref:System.IdentityModel.Selectors.X509CertificateValidator> classe.</span><span class="sxs-lookup"><span data-stu-id="1a96c-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="1a96c-117">Impostare il `certificateValidationMode` attributo del [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) elemento su "Custom" per utilizzare questo tipo.</span><span class="sxs-lookup"><span data-stu-id="1a96c-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="1a96c-118">Per ulteriori informazioni su come specificare il `type` attributo, vedere [riferimenti al tipo personalizzato](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="1a96c-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="1a96c-119">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1a96c-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a96c-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1a96c-120">Child Elements</span></span>  
 <span data-ttu-id="1a96c-121">Nessuno</span><span class="sxs-lookup"><span data-stu-id="1a96c-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1a96c-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1a96c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="1a96c-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="1a96c-123">Element</span></span>|<span data-ttu-id="1a96c-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1a96c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a96c-125">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="1a96c-125">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="1a96c-126">Controlla le impostazioni che utilizzano gestori di token per convalidare i certificati.</span><span class="sxs-lookup"><span data-stu-id="1a96c-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1a96c-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="1a96c-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
