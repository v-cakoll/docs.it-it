---
title: '&lt;audienceUris&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 3ce884c19d205df4727dcce96ffdf34144ff1dd6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltaudienceurisgt"></a><span data-ttu-id="43b85-102">&lt;audienceUris&gt;</span><span class="sxs-lookup"><span data-stu-id="43b85-102">&lt;audienceUris&gt;</span></span>
<span data-ttu-id="43b85-103">Specifica il set di URI accettabili identificatori delle relying party (RP).</span><span class="sxs-lookup"><span data-stu-id="43b85-103">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="43b85-104">Token non verranno accettati, a meno che hanno come ambito per uno dei gruppi di destinatari consentiti gli URI.</span><span class="sxs-lookup"><span data-stu-id="43b85-104">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
 <span data-ttu-id="43b85-105">\<System. IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="43b85-105">\<system.identityModel></span></span>  
<span data-ttu-id="43b85-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="43b85-106">\<identityConfiguration></span></span>  
<span data-ttu-id="43b85-107">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="43b85-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="43b85-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="43b85-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="43b85-109">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="43b85-109">\<audienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43b85-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="43b85-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <audienceUris mode=xs:string>  
          <add value=xs:string />  
          <clear />  
          <remove value=xs:string />  
        </audienceUris>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43b85-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="43b85-111">Attributes and Elements</span></span>  
 <span data-ttu-id="43b85-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="43b85-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43b85-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="43b85-113">Attributes</span></span>  
  
|<span data-ttu-id="43b85-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="43b85-114">Attribute</span></span>|<span data-ttu-id="43b85-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="43b85-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="43b85-116">modalità</span><span class="sxs-lookup"><span data-stu-id="43b85-116">mode</span></span>|<span data-ttu-id="43b85-117">Un <xref:System.IdentityModel.Selectors.AudienceUriMode> valore che specifica se la restrizione di gruppo di destinatari deve essere applicata a un token in ingresso.</span><span class="sxs-lookup"><span data-stu-id="43b85-117">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="43b85-118">I valori possibili sono "Sempre", "Mai" e "BearerKeyOnly".</span><span class="sxs-lookup"><span data-stu-id="43b85-118">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="43b85-119">Il valore predefinito è "Sempre".</span><span class="sxs-lookup"><span data-stu-id="43b85-119">The default is "Always".</span></span> <span data-ttu-id="43b85-120">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="43b85-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="43b85-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="43b85-121">Child Elements</span></span>  
  
|<span data-ttu-id="43b85-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="43b85-122">Element</span></span>|<span data-ttu-id="43b85-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="43b85-123">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="43b85-124">Aggiunge l'URI specificato per il `value` attributo alla raccolta audienceUris.</span><span class="sxs-lookup"><span data-stu-id="43b85-124">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="43b85-125">L'attributo `value` è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="43b85-125">The `value` attribute is required.</span></span> <span data-ttu-id="43b85-126">L'URI è tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="43b85-126">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="43b85-127">Cancella la raccolta di audienceUris.</span><span class="sxs-lookup"><span data-stu-id="43b85-127">Clears the audienceUris collection.</span></span> <span data-ttu-id="43b85-128">Tutti gli identificatori vengono rimossi dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="43b85-128">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="43b85-129">Rimuove l'URI specificato per il `value` attributo dalla raccolta audienceUris.</span><span class="sxs-lookup"><span data-stu-id="43b85-129">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="43b85-130">L'attributo `value` è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="43b85-130">The `value` attribute is required.</span></span> <span data-ttu-id="43b85-131">L'URI è tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="43b85-131">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="43b85-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="43b85-132">Parent Elements</span></span>  
  
|<span data-ttu-id="43b85-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="43b85-133">Element</span></span>|<span data-ttu-id="43b85-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="43b85-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43b85-135">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="43b85-135">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="43b85-136">Fornisce la configurazione per una raccolta di sicurezza gestori di token.</span><span class="sxs-lookup"><span data-stu-id="43b85-136">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43b85-137">Note</span><span class="sxs-lookup"><span data-stu-id="43b85-137">Remarks</span></span>  
 <span data-ttu-id="43b85-138">Per impostazione predefinita, la raccolta è vuota. Utilizzare `<add>`, `<clear>`, e `<remove>` elementi per modificare la raccolta.</span><span class="sxs-lookup"><span data-stu-id="43b85-138">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="43b85-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>e <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> i valori nel gruppo di destinatari insieme di URI per configurare qualsiasi restrizioni URI nel gruppo di destinatari è consentito l'utilizzo di oggetti <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> oggetti.</span><span class="sxs-lookup"><span data-stu-id="43b85-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="43b85-140">Il `<audienceUris>` elemento è rappresentato dalla <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> classe.</span><span class="sxs-lookup"><span data-stu-id="43b85-140">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="43b85-141">Un URI singoli aggiunto alla raccolta è rappresentato dalla <xref:System.IdentityModel.Configuration.AudienceUriElement> classe.</span><span class="sxs-lookup"><span data-stu-id="43b85-141">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43b85-142">L'utilizzo del `<audienceUris>` come un elemento figlio dell'elemento di [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento è stato deprecato, ma è ancora supportato per compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="43b85-142">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="43b85-143">Impostazioni di `<securityTokenHandlerConfiguration>` elemento prevalgono su quelle nel `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="43b85-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43b85-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="43b85-144">Example</span></span>  
 <span data-ttu-id="43b85-145">Il codice XML seguente viene illustrato come configurare il gruppo di destinatari accettabile gli URI per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="43b85-145">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="43b85-146">In questo esempio consente di configurare un unico URI.</span><span class="sxs-lookup"><span data-stu-id="43b85-146">This example configures a single URI.</span></span> <span data-ttu-id="43b85-147">I token nell'ambito per questo URI verranno accettati, tutti gli altri verranno rifiutati.</span><span class="sxs-lookup"><span data-stu-id="43b85-147">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
