---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 1143717882652fc8a03947327b5f1ea89dde7373
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793809"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="6bbae-101">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="6bbae-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="6bbae-102">Registra il resolver dei token di servizio che viene usato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="6bbae-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="6bbae-103">Il resolver dei token di servizio viene usato per risolvere il token di crittografia token in arrivo e messaggi.</span><span class="sxs-lookup"><span data-stu-id="6bbae-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="6bbae-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="6bbae-104">\<system.identityModel></span></span>  
<span data-ttu-id="6bbae-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="6bbae-105">\<identityConfiguration></span></span>  
<span data-ttu-id="6bbae-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="6bbae-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="6bbae-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="6bbae-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="6bbae-108">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="6bbae-108">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bbae-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6bbae-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6bbae-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6bbae-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6bbae-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6bbae-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6bbae-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="6bbae-112">Attributes</span></span>  
  
|<span data-ttu-id="6bbae-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="6bbae-113">Attribute</span></span>|<span data-ttu-id="6bbae-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6bbae-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6bbae-115">tipo</span><span class="sxs-lookup"><span data-stu-id="6bbae-115">type</span></span>|<span data-ttu-id="6bbae-116">Specifica il tipo di resolver di token del servizio.</span><span class="sxs-lookup"><span data-stu-id="6bbae-116">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="6bbae-117">Entrambi i <xref:System.IdentityModel.Selectors.SecurityTokenResolver> tipo o un tipo che deriva dal <xref:System.IdentityModel.Selectors.SecurityTokenResolver> classe.</span><span class="sxs-lookup"><span data-stu-id="6bbae-117">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="6bbae-118">Per altre informazioni su come specificare il `type` attributo, vedere [riferimenti a tipi personalizzati].</span><span class="sxs-lookup"><span data-stu-id="6bbae-118">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="6bbae-119">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6bbae-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6bbae-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6bbae-120">Child Elements</span></span>  
 <span data-ttu-id="6bbae-121">nessuno</span><span class="sxs-lookup"><span data-stu-id="6bbae-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6bbae-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6bbae-122">Parent Elements</span></span>  
  
|<span data-ttu-id="6bbae-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="6bbae-123">Element</span></span>|<span data-ttu-id="6bbae-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6bbae-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6bbae-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="6bbae-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="6bbae-126">Fornisce la configurazione per una raccolta di sicurezza i gestori di token.</span><span class="sxs-lookup"><span data-stu-id="6bbae-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6bbae-127">Note</span><span class="sxs-lookup"><span data-stu-id="6bbae-127">Remarks</span></span>  
 <span data-ttu-id="6bbae-128">Il resolver dei token di servizio è utilizzabile per risolvere il token di crittografia token in arrivo e messaggi.</span><span class="sxs-lookup"><span data-stu-id="6bbae-128">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="6bbae-129">Utilizzato per recuperare la chiave da usare per decrittografare i token in ingresso.</span><span class="sxs-lookup"><span data-stu-id="6bbae-129">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="6bbae-130">È necessario specificare il `type` attributo.</span><span class="sxs-lookup"><span data-stu-id="6bbae-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="6bbae-131">Il tipo specificato può essere <xref:System.IdentityModel.Selectors.SecurityTokenResolver> o un tipo personalizzato che deriva dal <xref:System.IdentityModel.Selectors.SecurityTokenResolver> classe.</span><span class="sxs-lookup"><span data-stu-id="6bbae-131">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="6bbae-132">Alcuni gestori di token consentono di specificare le impostazioni di resolver dei token del servizio nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="6bbae-132">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="6bbae-133">Le impostazioni ai singoli gestori di token sostituiscono quelle specificate nella raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6bbae-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6bbae-134">Specifica la `<serviceTokenResolver>` come elemento figlio dell'elemento di [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento è stato deprecato, ma è ancora supportata per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="6bbae-134">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="6bbae-135">Le impostazioni nel `<securityTokenHandlerConfiguration>` elemento sostituiscono quelle di `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="6bbae-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6bbae-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="6bbae-136">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
