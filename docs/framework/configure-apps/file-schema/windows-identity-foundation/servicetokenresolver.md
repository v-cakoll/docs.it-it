---
title: '&lt;serviceTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: c25ea1fc32c93e7eb57ef8ed06d6f786ae0a670e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltservicetokenresolvergt"></a><span data-ttu-id="fbbd0-102">&lt;serviceTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="fbbd0-102">&lt;serviceTokenResolver&gt;</span></span>
<span data-ttu-id="fbbd0-103">Registra il resolver dei token di servizio che viene utilizzata dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="fbbd0-103">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="fbbd0-104">Il resolver dei token di servizio viene utilizzato per risolvere il token di crittografia di token in arrivo e messaggi.</span><span class="sxs-lookup"><span data-stu-id="fbbd0-104">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="fbbd0-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="fbbd0-105">\<system.identityModel></span></span>  
<span data-ttu-id="fbbd0-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="fbbd0-106">\<identityConfiguration></span></span>  
<span data-ttu-id="fbbd0-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="fbbd0-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="fbbd0-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="fbbd0-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="fbbd0-109">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="fbbd0-109">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbbd0-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fbbd0-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fbbd0-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fbbd0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fbbd0-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fbbd0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fbbd0-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="fbbd0-113">Attributes</span></span>  
  
|<span data-ttu-id="fbbd0-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="fbbd0-114">Attribute</span></span>|<span data-ttu-id="fbbd0-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbbd0-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fbbd0-116">tipo</span><span class="sxs-lookup"><span data-stu-id="fbbd0-116">type</span></span>|<span data-ttu-id="fbbd0-117">Specifica il tipo di resolver del token di servizio.</span><span class="sxs-lookup"><span data-stu-id="fbbd0-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="fbbd0-118">Entrambi i <xref:System.IdentityModel.Selectors.SecurityTokenResolver> tipo o un tipo che deriva dalla <xref:System.IdentityModel.Selectors.SecurityTokenResolver> classe.</span><span class="sxs-lookup"><span data-stu-id="fbbd0-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="fbbd0-119">Per ulteriori informazioni su come specificare il `type` attributo, vedere [riferimenti al tipo personalizzato].</span><span class="sxs-lookup"><span data-stu-id="fbbd0-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="fbbd0-120">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fbbd0-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fbbd0-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fbbd0-121">Child Elements</span></span>  
 <span data-ttu-id="fbbd0-122">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fbbd0-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fbbd0-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fbbd0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fbbd0-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="fbbd0-124">Element</span></span>|<span data-ttu-id="fbbd0-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbbd0-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fbbd0-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="fbbd0-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="fbbd0-127">Fornisce la configurazione per una raccolta di sicurezza gestori di token.</span><span class="sxs-lookup"><span data-stu-id="fbbd0-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbbd0-128">Note</span><span class="sxs-lookup"><span data-stu-id="fbbd0-128">Remarks</span></span>  
 <span data-ttu-id="fbbd0-129">Per risolvere il token di crittografia di token in arrivo e messaggi, è possibile utilizzare il resolver dei token di servizio.</span><span class="sxs-lookup"><span data-stu-id="fbbd0-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="fbbd0-130">Consente di recuperare la chiave che deve essere utilizzata per decrittografare i token in ingresso.</span><span class="sxs-lookup"><span data-stu-id="fbbd0-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="fbbd0-131">È necessario specificare il `type` attributo.</span><span class="sxs-lookup"><span data-stu-id="fbbd0-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="fbbd0-132">Il tipo specificato può essere <xref:System.IdentityModel.Selectors.SecurityTokenResolver> o un tipo personalizzato da cui deriva il <xref:System.IdentityModel.Selectors.SecurityTokenResolver> classe.</span><span class="sxs-lookup"><span data-stu-id="fbbd0-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="fbbd0-133">Alcuni gestori di token consentono di specificare le impostazioni di resolver del token del servizio nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="fbbd0-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="fbbd0-134">Le impostazioni ai gestori di token singoli sostituiscono quelle specificate nella raccolta di gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="fbbd0-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fbbd0-135">Specifica il `<serviceTokenResolver>` come un elemento figlio dell'elemento di [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento è stato deprecato, ma è ancora supportato per compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="fbbd0-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="fbbd0-136">Impostazioni di `<securityTokenHandlerConfiguration>` elemento prevalgono su quelle nel `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="fbbd0-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbbd0-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="fbbd0-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
