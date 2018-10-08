---
title: '&lt;certificateValidator&gt;'
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 65b8aa6fa4422579ce0d1c5e33d3418ea051612a
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2018
ms.locfileid: "48849698"
---
# <a name="ltcertificatevalidatorgt"></a><span data-ttu-id="2af71-102">&lt;certificateValidator&gt;</span><span class="sxs-lookup"><span data-stu-id="2af71-102">&lt;certificateValidator&gt;</span></span>
<span data-ttu-id="2af71-103">Specifica un tipo personalizzato per la convalida del certificato.</span><span class="sxs-lookup"><span data-stu-id="2af71-103">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="2af71-104">Questo tipo viene usato solo se il `certificateValidationMode` attributo del [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) elemento è impostato su "Custom".</span><span class="sxs-lookup"><span data-stu-id="2af71-104">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="2af71-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="2af71-105">\<system.identityModel></span></span>  
<span data-ttu-id="2af71-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="2af71-106">\<identityConfiguration></span></span>  
<span data-ttu-id="2af71-107">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="2af71-107">\<certificateValidation></span></span>  
<span data-ttu-id="2af71-108">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="2af71-108">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2af71-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2af71-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2af71-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2af71-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2af71-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2af71-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2af71-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="2af71-112">Attributes</span></span>  
  
|<span data-ttu-id="2af71-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="2af71-113">Attribute</span></span>|<span data-ttu-id="2af71-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2af71-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2af71-115">tipo</span><span class="sxs-lookup"><span data-stu-id="2af71-115">type</span></span>|<span data-ttu-id="2af71-116">Specifica un tipo personalizzato che deriva dal <xref:System.IdentityModel.Selectors.X509CertificateValidator> classe.</span><span class="sxs-lookup"><span data-stu-id="2af71-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="2af71-117">Impostare il `certificateValidationMode` attributo del [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) su "Custom" per usare questo tipo di elemento.</span><span class="sxs-lookup"><span data-stu-id="2af71-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="2af71-118">Per altre informazioni su come specificare il `type` dell'attributo, vedere [riferimenti a tipi personalizzati](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="2af71-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="2af71-119">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2af71-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2af71-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2af71-120">Child Elements</span></span>  
 <span data-ttu-id="2af71-121">nessuno</span><span class="sxs-lookup"><span data-stu-id="2af71-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2af71-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2af71-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2af71-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="2af71-123">Element</span></span>|<span data-ttu-id="2af71-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2af71-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2af71-125">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="2af71-125">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="2af71-126">Controllare le impostazioni che utilizzano i gestori di token per convalidare i certificati.</span><span class="sxs-lookup"><span data-stu-id="2af71-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2af71-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="2af71-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
