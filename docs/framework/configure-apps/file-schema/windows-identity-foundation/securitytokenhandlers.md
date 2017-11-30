---
title: '&lt;securityTokenHandlers&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 3151ec3511bca598e5aaabc72b821bdd3aed0b7b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltsecuritytokenhandlersgt"></a><span data-ttu-id="e5e7f-102">&lt;securityTokenHandlers&gt;</span><span class="sxs-lookup"><span data-stu-id="e5e7f-102">&lt;securityTokenHandlers&gt;</span></span>
<span data-ttu-id="e5e7f-103">Specifica una raccolta di gestori di token di sicurezza che sono registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="e5e7f-103">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
 <span data-ttu-id="e5e7f-104">\<System. IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="e5e7f-104">\<system.identityModel></span></span>  
<span data-ttu-id="e5e7f-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="e5e7f-105">\<identityConfiguration></span></span>  
<span data-ttu-id="e5e7f-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="e5e7f-106">\<securityTokenHandlers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5e7f-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5e7f-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5e7f-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e5e7f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e5e7f-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e5e7f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5e7f-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="e5e7f-110">Attributes</span></span>  
  
|<span data-ttu-id="e5e7f-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="e5e7f-111">Attribute</span></span>|<span data-ttu-id="e5e7f-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e5e7f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5e7f-113">name</span><span class="sxs-lookup"><span data-stu-id="e5e7f-113">name</span></span>|<span data-ttu-id="e5e7f-114">Specifica il nome di una raccolta di gestore del token.</span><span class="sxs-lookup"><span data-stu-id="e5e7f-114">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="e5e7f-115">Gli unici valori riconosciuti dal framework sono "ActAs" e "OnBehalfOf".</span><span class="sxs-lookup"><span data-stu-id="e5e7f-115">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="e5e7f-116">Se le raccolte di gestore del token vengono specificate con uno di questi nomi, la raccolta verrà utilizzata durante l'elaborazione di ActAs o OnBehalfOf token rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="e5e7f-116">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5e7f-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e5e7f-117">Child Elements</span></span>  
  
|<span data-ttu-id="e5e7f-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="e5e7f-118">Element</span></span>|<span data-ttu-id="e5e7f-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e5e7f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5e7f-120">\<add></span><span class="sxs-lookup"><span data-stu-id="e5e7f-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="e5e7f-121">Aggiunge un gestore di token di sicurezza alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="e5e7f-121">Adds a security token handler to the token handler collection.</span></span>|  
|[<span data-ttu-id="e5e7f-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="e5e7f-122">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)|<span data-ttu-id="e5e7f-123">Cancella tutti i gestori di token di sicurezza dalla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="e5e7f-123">Clears all security token handlers from the token handler collection.</span></span>|  
|[<span data-ttu-id="e5e7f-124">\<remove></span><span class="sxs-lookup"><span data-stu-id="e5e7f-124">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)|<span data-ttu-id="e5e7f-125">Rimuove un gestore di token di sicurezza dalla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="e5e7f-125">Removes a security token handler from the token handler collection.</span></span>|  
|[<span data-ttu-id="e5e7f-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="e5e7f-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="e5e7f-127">Fornisce la configurazione per la raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="e5e7f-127">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e5e7f-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e5e7f-128">Parent Elements</span></span>  
  
|<span data-ttu-id="e5e7f-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="e5e7f-129">Element</span></span>|<span data-ttu-id="e5e7f-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e5e7f-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5e7f-131">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="e5e7f-131">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="e5e7f-132">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="e5e7f-132">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5e7f-133">Note</span><span class="sxs-lookup"><span data-stu-id="e5e7f-133">Remarks</span></span>  
 <span data-ttu-id="e5e7f-134">È possibile specificare uno o più insiemi di gestori di token di sicurezza in una configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="e5e7f-134">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="e5e7f-135">È possibile specificare un nome per una raccolta tramite il `name` attributo.</span><span class="sxs-lookup"><span data-stu-id="e5e7f-135">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="e5e7f-136">Gli unici nomi che gestisce il framework sono "ActAs" e "OnBehalfOf".</span><span class="sxs-lookup"><span data-stu-id="e5e7f-136">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="e5e7f-137">Se esistono gestori eventi in tali raccolte, vengono usati da un servizio token di sicurezza (STS) anziché i gestori predefiniti durante l'elaborazione `ActAs` e `OnBehalfOf` token.</span><span class="sxs-lookup"><span data-stu-id="e5e7f-137">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="e5e7f-138">Per impostazione predefinita, la raccolta viene popolata con i seguenti tipi di gestore: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, e <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="e5e7f-138">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="e5e7f-139">È possibile modificare la raccolta tramite il `<add>`, `<remove>`, e `<clear>` elementi.</span><span class="sxs-lookup"><span data-stu-id="e5e7f-139">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="e5e7f-140">È necessario assicurarsi che solo un singolo gestore di qualsiasi tipo specifico è presente nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="e5e7f-140">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="e5e7f-141">Ad esempio, se si deriva un gestore di <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe, il gestore o <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> può essere configurato in una singola raccolta, ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="e5e7f-141">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="e5e7f-142">Utilizzare il `<securityTokenHandlerConfiguration>` elemento per specificare le impostazioni di configurazione per i gestori nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="e5e7f-142">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="e5e7f-143">Le impostazioni specificate tramite questo elemento sostituiscono quelle specificate nel servizio tramite il [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="e5e7f-143">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="e5e7f-144">Alcuni gestori (compresi alcuni dei tipi di gestore predefinito) possono supportare una configurazione aggiuntiva tramite un elemento figlio del `<add>` elemento.</span><span class="sxs-lookup"><span data-stu-id="e5e7f-144">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="e5e7f-145">Le impostazioni specificate in un gestore sostituiscono impostazioni equivalenti specificate nella raccolta o il servizio.</span><span class="sxs-lookup"><span data-stu-id="e5e7f-145">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
