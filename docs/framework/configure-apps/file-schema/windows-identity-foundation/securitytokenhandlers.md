---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: 678e5c705181c55257b1ddb853690ada60ecd17a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942465"
---
# <a name="securitytokenhandlers"></a><span data-ttu-id="dca11-101">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="dca11-101">\<securityTokenHandlers></span></span>
<span data-ttu-id="dca11-102">Specifica una raccolta di gestori di token di sicurezza registrati con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="dca11-102">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
 <span data-ttu-id="dca11-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="dca11-103">\<system.identityModel></span></span>  
<span data-ttu-id="dca11-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="dca11-104">\<identityConfiguration></span></span>  
<span data-ttu-id="dca11-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="dca11-105">\<securityTokenHandlers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dca11-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dca11-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dca11-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dca11-107">Attributes and Elements</span></span>  
 <span data-ttu-id="dca11-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dca11-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dca11-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="dca11-109">Attributes</span></span>  
  
|<span data-ttu-id="dca11-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="dca11-110">Attribute</span></span>|<span data-ttu-id="dca11-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dca11-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dca11-112">name</span><span class="sxs-lookup"><span data-stu-id="dca11-112">name</span></span>|<span data-ttu-id="dca11-113">Specifica il nome di una raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="dca11-113">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="dca11-114">Gli unici valori riconosciuti dal Framework sono "ActAs" e "OnBehalfOf".</span><span class="sxs-lookup"><span data-stu-id="dca11-114">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="dca11-115">Se le raccolte di gestori di token vengono specificate con uno di questi nomi, l'insieme verrà usato per l'elaborazione rispettivamente dei token ActAs o OnBehalfOf.</span><span class="sxs-lookup"><span data-stu-id="dca11-115">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dca11-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dca11-116">Child Elements</span></span>  
  
|<span data-ttu-id="dca11-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="dca11-117">Element</span></span>|<span data-ttu-id="dca11-118">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="dca11-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dca11-119">\<add></span><span class="sxs-lookup"><span data-stu-id="dca11-119">\<add></span></span>](add.md)|<span data-ttu-id="dca11-120">Aggiunge un gestore del token di sicurezza alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="dca11-120">Adds a security token handler to the token handler collection.</span></span>|  
|[<span data-ttu-id="dca11-121">\<clear></span><span class="sxs-lookup"><span data-stu-id="dca11-121">\<clear></span></span>](clear.md)|<span data-ttu-id="dca11-122">Cancella tutti i gestori dei token di sicurezza dalla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="dca11-122">Clears all security token handlers from the token handler collection.</span></span>|  
|[<span data-ttu-id="dca11-123">\<remove></span><span class="sxs-lookup"><span data-stu-id="dca11-123">\<remove></span></span>](remove.md)|<span data-ttu-id="dca11-124">Rimuove un gestore del token di sicurezza dalla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="dca11-124">Removes a security token handler from the token handler collection.</span></span>|  
|[<span data-ttu-id="dca11-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="dca11-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="dca11-126">Fornisce la configurazione per la raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="dca11-126">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dca11-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dca11-127">Parent Elements</span></span>  
  
|<span data-ttu-id="dca11-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="dca11-128">Element</span></span>|<span data-ttu-id="dca11-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dca11-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dca11-130">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="dca11-130">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="dca11-131">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="dca11-131">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dca11-132">Note</span><span class="sxs-lookup"><span data-stu-id="dca11-132">Remarks</span></span>  
 <span data-ttu-id="dca11-133">È possibile specificare una o più raccolte denominate di gestori di token di sicurezza in una configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="dca11-133">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="dca11-134">È possibile specificare un nome per una raccolta usando l' `name` attributo.</span><span class="sxs-lookup"><span data-stu-id="dca11-134">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="dca11-135">Gli unici nomi gestiti dal Framework sono "ActAs" e "OnBehalfOf".</span><span class="sxs-lookup"><span data-stu-id="dca11-135">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="dca11-136">Se i gestori sono presenti in queste raccolte, vengono utilizzati da un servizio token di sicurezza (STS) invece dei gestori predefiniti durante l'elaborazione `ActAs` e `OnBehalfOf` i token.</span><span class="sxs-lookup"><span data-stu-id="dca11-136">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="dca11-137">Per impostazione predefinita, la raccolta viene popolata con i tipi di <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>gestore <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>seguenti <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>: <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>,, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>,, <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler> <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, e.</span><span class="sxs-lookup"><span data-stu-id="dca11-137">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="dca11-138">È possibile modificare la raccolta usando gli `<add>`elementi, `<remove>`e. `<clear>`</span><span class="sxs-lookup"><span data-stu-id="dca11-138">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="dca11-139">È necessario assicurarsi che nella raccolta sia presente solo un singolo gestore di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="dca11-139">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="dca11-140">Se, ad esempio, si deriva un gestore dalla <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe, il gestore o l'oggetto può essere configurato in una singola raccolta, ma non in entrambi i <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> casi.</span><span class="sxs-lookup"><span data-stu-id="dca11-140">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="dca11-141">Utilizzare l' `<securityTokenHandlerConfiguration>` elemento per specificare le impostazioni di configurazione per i gestori nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="dca11-141">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="dca11-142">Le impostazioni specificate tramite questo elemento eseguono l'override di quelle specificate nel servizio tramite l' [ \<elemento IdentityConfiguration >](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="dca11-142">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="dca11-143">Alcuni gestori (inclusi diversi tipi di gestori incorporati) possono supportare una configurazione aggiuntiva tramite un elemento figlio dell' `<add>` elemento.</span><span class="sxs-lookup"><span data-stu-id="dca11-143">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="dca11-144">Le impostazioni specificate in un gestore eseguono l'override delle impostazioni equivalenti specificate nella raccolta o nel servizio.</span><span class="sxs-lookup"><span data-stu-id="dca11-144">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
