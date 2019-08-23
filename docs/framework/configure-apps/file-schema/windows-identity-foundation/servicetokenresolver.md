---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 69d34cb54c2236f178ac4291ed24a3f5b45db48e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923102"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="39430-101">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="39430-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="39430-102">Registra il resolver del token di servizio utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="39430-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="39430-103">Il resolver del token del servizio viene usato per risolvere il token di crittografia sui token e i messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="39430-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="39430-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="39430-104">\<system.identityModel></span></span>  
<span data-ttu-id="39430-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="39430-105">\<identityConfiguration></span></span>  
<span data-ttu-id="39430-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="39430-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="39430-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="39430-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="39430-108">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="39430-108">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39430-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39430-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39430-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="39430-110">Attributes and Elements</span></span>  
 <span data-ttu-id="39430-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="39430-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39430-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="39430-112">Attributes</span></span>  
  
|<span data-ttu-id="39430-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="39430-113">Attribute</span></span>|<span data-ttu-id="39430-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="39430-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="39430-115">type</span><span class="sxs-lookup"><span data-stu-id="39430-115">type</span></span>|<span data-ttu-id="39430-116">Specifica il tipo del resolver del token del servizio.</span><span class="sxs-lookup"><span data-stu-id="39430-116">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="39430-117">Tipo o un tipo che deriva <xref:System.IdentityModel.Selectors.SecurityTokenResolver> dalla classe. <xref:System.IdentityModel.Selectors.SecurityTokenResolver></span><span class="sxs-lookup"><span data-stu-id="39430-117">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="39430-118">Per ulteriori informazioni su come specificare l'attributo `type` , vedere [riferimenti ai tipi personalizzati].</span><span class="sxs-lookup"><span data-stu-id="39430-118">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="39430-119">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="39430-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="39430-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="39430-120">Child Elements</span></span>  
 <span data-ttu-id="39430-121">Nessuna</span><span class="sxs-lookup"><span data-stu-id="39430-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="39430-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="39430-122">Parent Elements</span></span>  
  
|<span data-ttu-id="39430-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="39430-123">Element</span></span>|<span data-ttu-id="39430-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39430-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39430-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="39430-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="39430-126">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="39430-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39430-127">Note</span><span class="sxs-lookup"><span data-stu-id="39430-127">Remarks</span></span>  
 <span data-ttu-id="39430-128">Il resolver del token del servizio può essere usato per risolvere il token di crittografia sui token e i messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="39430-128">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="39430-129">Viene usato per recuperare la chiave che deve essere usata per decrittografare i token in ingresso.</span><span class="sxs-lookup"><span data-stu-id="39430-129">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="39430-130">È necessario specificare l' `type` attributo.</span><span class="sxs-lookup"><span data-stu-id="39430-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="39430-131">Il tipo specificato può essere <xref:System.IdentityModel.Selectors.SecurityTokenResolver> o un tipo personalizzato che deriva <xref:System.IdentityModel.Selectors.SecurityTokenResolver> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="39430-131">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="39430-132">Alcuni gestori di token consentono di specificare le impostazioni del resolver del token del servizio nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="39430-132">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="39430-133">Le impostazioni sui singoli gestori di token eseguono l'override di quelle specificate nella raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="39430-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="39430-134">Specificare l' `<serviceTokenResolver>` elemento come elemento figlio [ \<dell'elemento > IdentityConfiguration](identityconfiguration.md) è stato deprecato, ma è ancora supportato per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="39430-134">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="39430-135">Le impostazioni sull' `<securityTokenHandlerConfiguration>` elemento eseguono l'override `<identityConfiguration>` di quelle nell'elemento.</span><span class="sxs-lookup"><span data-stu-id="39430-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39430-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="39430-136">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
