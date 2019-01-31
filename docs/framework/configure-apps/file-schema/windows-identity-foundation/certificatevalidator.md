---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: df52212305e0865b8c03fdd49068cb7c7da4fa38
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277452"
---
# <a name="certificatevalidator"></a><span data-ttu-id="42059-101">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="42059-101">\<certificateValidator></span></span>
<span data-ttu-id="42059-102">Specifica un tipo personalizzato per la convalida del certificato.</span><span class="sxs-lookup"><span data-stu-id="42059-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="42059-103">Questo tipo viene usato solo se il `certificateValidationMode` attributo del [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) elemento è impostato su "Custom".</span><span class="sxs-lookup"><span data-stu-id="42059-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="42059-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="42059-104">\<system.identityModel></span></span>  
<span data-ttu-id="42059-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="42059-105">\<identityConfiguration></span></span>  
<span data-ttu-id="42059-106">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="42059-106">\<certificateValidation></span></span>  
<span data-ttu-id="42059-107">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="42059-107">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42059-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42059-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42059-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="42059-109">Attributes and Elements</span></span>  
 <span data-ttu-id="42059-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="42059-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42059-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="42059-111">Attributes</span></span>  
  
|<span data-ttu-id="42059-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="42059-112">Attribute</span></span>|<span data-ttu-id="42059-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42059-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42059-114">tipo</span><span class="sxs-lookup"><span data-stu-id="42059-114">type</span></span>|<span data-ttu-id="42059-115">Specifica un tipo personalizzato che deriva dal <xref:System.IdentityModel.Selectors.X509CertificateValidator> classe.</span><span class="sxs-lookup"><span data-stu-id="42059-115">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="42059-116">Impostare il `certificateValidationMode` attributo del [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) su "Custom" per usare questo tipo di elemento.</span><span class="sxs-lookup"><span data-stu-id="42059-116">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="42059-117">Per altre informazioni su come specificare il `type` dell'attributo, vedere [riferimenti a tipi personalizzati](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="42059-117">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="42059-118">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="42059-118">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42059-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="42059-119">Child Elements</span></span>  
 <span data-ttu-id="42059-120">nessuno</span><span class="sxs-lookup"><span data-stu-id="42059-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="42059-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="42059-121">Parent Elements</span></span>  
  
|<span data-ttu-id="42059-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="42059-122">Element</span></span>|<span data-ttu-id="42059-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42059-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42059-124">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="42059-124">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="42059-125">Controllare le impostazioni che utilizzano i gestori di token per convalidare i certificati.</span><span class="sxs-lookup"><span data-stu-id="42059-125">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="42059-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="42059-126">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
