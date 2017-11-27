---
title: '&lt;serviceTokenResolver&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 06e871ee31880a219d9105ff4ce667618bfb78f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltservicetokenresolvergt"></a><span data-ttu-id="a9d99-102">&lt;serviceTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="a9d99-102">&lt;serviceTokenResolver&gt;</span></span>
<span data-ttu-id="a9d99-103">Registra il resolver dei token di servizio che viene utilizzata dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="a9d99-103">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="a9d99-104">Il resolver dei token di servizio viene utilizzato per risolvere il token di crittografia di token in arrivo e messaggi.</span><span class="sxs-lookup"><span data-stu-id="a9d99-104">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="a9d99-105">\<System. IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="a9d99-105">\<system.identityModel></span></span>  
<span data-ttu-id="a9d99-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a9d99-106">\<identityConfiguration></span></span>  
<span data-ttu-id="a9d99-107">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="a9d99-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="a9d99-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a9d99-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="a9d99-109">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="a9d99-109">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9d99-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a9d99-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9d99-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a9d99-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a9d99-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a9d99-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9d99-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="a9d99-113">Attributes</span></span>  
  
|<span data-ttu-id="a9d99-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="a9d99-114">Attribute</span></span>|<span data-ttu-id="a9d99-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a9d99-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a9d99-116">type</span><span class="sxs-lookup"><span data-stu-id="a9d99-116">type</span></span>|<span data-ttu-id="a9d99-117">Specifica il tipo di resolver del token di servizio.</span><span class="sxs-lookup"><span data-stu-id="a9d99-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="a9d99-118">Entrambi i <xref:System.IdentityModel.Selectors.SecurityTokenResolver> tipo o un tipo che deriva dalla <xref:System.IdentityModel.Selectors.SecurityTokenResolver> classe.</span><span class="sxs-lookup"><span data-stu-id="a9d99-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="a9d99-119">Per ulteriori informazioni su come specificare il `type` attributo, vedere [riferimenti al tipo personalizzato].</span><span class="sxs-lookup"><span data-stu-id="a9d99-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="a9d99-120">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a9d99-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a9d99-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a9d99-121">Child Elements</span></span>  
 <span data-ttu-id="a9d99-122">None</span><span class="sxs-lookup"><span data-stu-id="a9d99-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a9d99-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a9d99-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a9d99-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="a9d99-124">Element</span></span>|<span data-ttu-id="a9d99-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a9d99-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9d99-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a9d99-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="a9d99-127">Fornisce la configurazione per una raccolta di sicurezza gestori di token.</span><span class="sxs-lookup"><span data-stu-id="a9d99-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9d99-128">Note</span><span class="sxs-lookup"><span data-stu-id="a9d99-128">Remarks</span></span>  
 <span data-ttu-id="a9d99-129">Per risolvere il token di crittografia di token in arrivo e messaggi, è possibile utilizzare il resolver dei token di servizio.</span><span class="sxs-lookup"><span data-stu-id="a9d99-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="a9d99-130">Consente di recuperare la chiave che deve essere utilizzata per decrittografare i token in ingresso.</span><span class="sxs-lookup"><span data-stu-id="a9d99-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="a9d99-131">È necessario specificare il `type` attributo.</span><span class="sxs-lookup"><span data-stu-id="a9d99-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="a9d99-132">Il tipo specificato può essere <xref:System.IdentityModel.Selectors.SecurityTokenResolver> o un tipo personalizzato da cui deriva il <xref:System.IdentityModel.Selectors.SecurityTokenResolver> classe.</span><span class="sxs-lookup"><span data-stu-id="a9d99-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="a9d99-133">Alcuni gestori di token consentono di specificare le impostazioni di resolver del token del servizio nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="a9d99-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="a9d99-134">Le impostazioni ai gestori di token singoli sostituiscono quelle specificate nella raccolta di gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a9d99-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a9d99-135">Specifica il `<serviceTokenResolver>` come un elemento figlio dell'elemento di [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento è stato deprecato, ma è ancora supportato per compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="a9d99-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="a9d99-136">Impostazioni di `<securityTokenHandlerConfiguration>` elemento prevalgono su quelle nel `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="a9d99-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9d99-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="a9d99-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
