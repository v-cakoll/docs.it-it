---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: bd04e4ebdf5c58adaeea0ff0ca5993d7d9ce38f1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252174"
---
# <a name="audienceuris"></a><span data-ttu-id="30727-101">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="30727-101">\<audienceUris></span></span>
<span data-ttu-id="30727-102">Specifica il set di URI che sono identificatori accettabili del relying party (RP).</span><span class="sxs-lookup"><span data-stu-id="30727-102">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="30727-103">I token non verranno accettati a meno che non siano limitati a uno degli URI del gruppo di destinatari consentiti.</span><span class="sxs-lookup"><span data-stu-id="30727-103">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
<span data-ttu-id="30727-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="30727-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="30727-105">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="30727-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="30727-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="30727-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="30727-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="30727-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="30727-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlerConfiguration**](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="30727-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="30727-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> audienceUris**</span><span class="sxs-lookup"><span data-stu-id="30727-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<audienceUris>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30727-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30727-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30727-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="30727-111">Attributes and Elements</span></span>  
 <span data-ttu-id="30727-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="30727-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30727-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="30727-113">Attributes</span></span>  
  
|<span data-ttu-id="30727-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="30727-114">Attribute</span></span>|<span data-ttu-id="30727-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="30727-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="30727-116">modalità</span><span class="sxs-lookup"><span data-stu-id="30727-116">mode</span></span>|<span data-ttu-id="30727-117"><xref:System.IdentityModel.Selectors.AudienceUriMode> Valore che specifica se la restrizione dei destinatari deve essere applicata a un token in ingresso.</span><span class="sxs-lookup"><span data-stu-id="30727-117">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="30727-118">I valori possibili sono "Always", "Never" e "BearerKeyOnly".</span><span class="sxs-lookup"><span data-stu-id="30727-118">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="30727-119">Il valore predefinito è "Always".</span><span class="sxs-lookup"><span data-stu-id="30727-119">The default is "Always".</span></span> <span data-ttu-id="30727-120">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="30727-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30727-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="30727-121">Child Elements</span></span>  
  
|<span data-ttu-id="30727-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="30727-122">Element</span></span>|<span data-ttu-id="30727-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30727-123">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="30727-124">Aggiunge l'URI specificato dall' `value` attributo alla raccolta audienceUris.</span><span class="sxs-lookup"><span data-stu-id="30727-124">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="30727-125">L'attributo `value` è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="30727-125">The `value` attribute is required.</span></span> <span data-ttu-id="30727-126">L'URI fa distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="30727-126">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="30727-127">Cancella la raccolta audienceUris.</span><span class="sxs-lookup"><span data-stu-id="30727-127">Clears the audienceUris collection.</span></span> <span data-ttu-id="30727-128">Tutti gli identificatori vengono rimossi dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="30727-128">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="30727-129">Rimuove l'URI specificato dall' `value` attributo dalla raccolta audienceUris.</span><span class="sxs-lookup"><span data-stu-id="30727-129">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="30727-130">L'attributo `value` è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="30727-130">The `value` attribute is required.</span></span> <span data-ttu-id="30727-131">L'URI fa distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="30727-131">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="30727-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="30727-132">Parent Elements</span></span>  
  
|<span data-ttu-id="30727-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="30727-133">Element</span></span>|<span data-ttu-id="30727-134">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="30727-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30727-135">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="30727-135">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="30727-136">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="30727-136">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30727-137">Note</span><span class="sxs-lookup"><span data-stu-id="30727-137">Remarks</span></span>  
 <span data-ttu-id="30727-138">Per impostazione predefinita, la raccolta è vuota; utilizzare `<add>`gli `<clear>`elementi, `<remove>` e per modificare la raccolta.</span><span class="sxs-lookup"><span data-stu-id="30727-138">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="30727-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>gli <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> oggetti e usano i valori nella raccolta di URI dei destinatari per configurare eventuali restrizioni degli URI <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> dei destinatari consentiti negli oggetti.</span><span class="sxs-lookup"><span data-stu-id="30727-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="30727-140">L' `<audienceUris>` elemento è rappresentato <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="30727-140">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="30727-141">Un singolo URI aggiunto alla raccolta è rappresentato dalla <xref:System.IdentityModel.Configuration.AudienceUriElement> classe.</span><span class="sxs-lookup"><span data-stu-id="30727-141">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="30727-142">L'uso dell'elemento `<audienceUris>` come elemento figlio [ \<dell'elemento > IdentityConfiguration](identityconfiguration.md) è stato deprecato, ma è ancora supportato per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="30727-142">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="30727-143">Le impostazioni sull' `<securityTokenHandlerConfiguration>` elemento eseguono l'override `<identityConfiguration>` di quelle nell'elemento.</span><span class="sxs-lookup"><span data-stu-id="30727-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30727-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="30727-144">Example</span></span>  
 <span data-ttu-id="30727-145">Nel codice XML seguente viene illustrato come configurare gli URI di audience accettabili per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="30727-145">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="30727-146">Questo esempio Mostra come configurare un singolo URI.</span><span class="sxs-lookup"><span data-stu-id="30727-146">This example configures a single URI.</span></span> <span data-ttu-id="30727-147">I token con ambito per questo URI verranno accettati, tutti gli altri verranno rifiutati.</span><span class="sxs-lookup"><span data-stu-id="30727-147">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
