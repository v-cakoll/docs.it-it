---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: 003221ed4dc7f4ccf72d2e0d3a91265e13172813
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941950"
---
# <a name="audienceuris"></a><span data-ttu-id="3a5f5-101">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="3a5f5-101">\<audienceUris></span></span>
<span data-ttu-id="3a5f5-102">Specifica il set di URI che sono identificatori accettabili del relying party (RP).</span><span class="sxs-lookup"><span data-stu-id="3a5f5-102">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="3a5f5-103">I token non verranno accettati a meno che non siano limitati a uno degli URI del gruppo di destinatari consentiti.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-103">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
 <span data-ttu-id="3a5f5-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="3a5f5-104">\<system.identityModel></span></span>  
<span data-ttu-id="3a5f5-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="3a5f5-105">\<identityConfiguration></span></span>  
<span data-ttu-id="3a5f5-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="3a5f5-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="3a5f5-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="3a5f5-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="3a5f5-108">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="3a5f5-108">\<audienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a5f5-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3a5f5-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a5f5-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3a5f5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3a5f5-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a5f5-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="3a5f5-112">Attributes</span></span>  
  
|<span data-ttu-id="3a5f5-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="3a5f5-113">Attribute</span></span>|<span data-ttu-id="3a5f5-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="3a5f5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3a5f5-115">modalità</span><span class="sxs-lookup"><span data-stu-id="3a5f5-115">mode</span></span>|<span data-ttu-id="3a5f5-116"><xref:System.IdentityModel.Selectors.AudienceUriMode> Valore che specifica se la restrizione dei destinatari deve essere applicata a un token in ingresso.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-116">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="3a5f5-117">I valori possibili sono "Always", "Never" e "BearerKeyOnly".</span><span class="sxs-lookup"><span data-stu-id="3a5f5-117">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="3a5f5-118">Il valore predefinito è "Always".</span><span class="sxs-lookup"><span data-stu-id="3a5f5-118">The default is "Always".</span></span> <span data-ttu-id="3a5f5-119">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a5f5-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3a5f5-120">Child Elements</span></span>  
  
|<span data-ttu-id="3a5f5-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a5f5-121">Element</span></span>|<span data-ttu-id="3a5f5-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a5f5-122">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="3a5f5-123">Aggiunge l'URI specificato dall' `value` attributo alla raccolta audienceUris.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-123">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="3a5f5-124">L'attributo `value` è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-124">The `value` attribute is required.</span></span> <span data-ttu-id="3a5f5-125">L'URI fa distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-125">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="3a5f5-126">Cancella la raccolta audienceUris.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-126">Clears the audienceUris collection.</span></span> <span data-ttu-id="3a5f5-127">Tutti gli identificatori vengono rimossi dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-127">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="3a5f5-128">Rimuove l'URI specificato dall' `value` attributo dalla raccolta audienceUris.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-128">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="3a5f5-129">L'attributo `value` è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-129">The `value` attribute is required.</span></span> <span data-ttu-id="3a5f5-130">L'URI fa distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-130">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3a5f5-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3a5f5-131">Parent Elements</span></span>  
  
|<span data-ttu-id="3a5f5-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a5f5-132">Element</span></span>|<span data-ttu-id="3a5f5-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a5f5-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a5f5-134">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="3a5f5-134">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="3a5f5-135">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-135">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a5f5-136">Note</span><span class="sxs-lookup"><span data-stu-id="3a5f5-136">Remarks</span></span>  
 <span data-ttu-id="3a5f5-137">Per impostazione predefinita, la raccolta è vuota; utilizzare `<add>`gli `<clear>`elementi, `<remove>` e per modificare la raccolta.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-137">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="3a5f5-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>gli <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> oggetti e usano i valori nella raccolta di URI dei destinatari per configurare eventuali restrizioni degli URI <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> dei destinatari consentiti negli oggetti.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="3a5f5-139">L' `<audienceUris>` elemento è rappresentato <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-139">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="3a5f5-140">Un singolo URI aggiunto alla raccolta è rappresentato dalla <xref:System.IdentityModel.Configuration.AudienceUriElement> classe.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-140">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3a5f5-141">L'uso dell'elemento `<audienceUris>` come elemento figlio [ \<dell'elemento > IdentityConfiguration](identityconfiguration.md) è stato deprecato, ma è ancora supportato per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-141">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="3a5f5-142">Le impostazioni sull' `<securityTokenHandlerConfiguration>` elemento eseguono l'override `<identityConfiguration>` di quelle nell'elemento.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a5f5-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="3a5f5-143">Example</span></span>  
 <span data-ttu-id="3a5f5-144">Nel codice XML seguente viene illustrato come configurare gli URI di audience accettabili per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-144">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="3a5f5-145">Questo esempio Mostra come configurare un singolo URI.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-145">This example configures a single URI.</span></span> <span data-ttu-id="3a5f5-146">I token con ambito per questo URI verranno accettati, tutti gli altri verranno rifiutati.</span><span class="sxs-lookup"><span data-stu-id="3a5f5-146">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
