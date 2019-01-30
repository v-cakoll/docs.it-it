---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: 556c444d5e48e27036c4b49338f6e70de7ef5c5d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267274"
---
# <a name="audienceuris"></a><span data-ttu-id="3a19f-101">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="3a19f-101">\<audienceUris></span></span>
<span data-ttu-id="3a19f-102">Specifica il set di URI accettabili identificatori della relying party (RP).</span><span class="sxs-lookup"><span data-stu-id="3a19f-102">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="3a19f-103">I token non verranno accettati, a meno che hanno come ambito per uno dei gruppi di destinatari consentiti gli URI.</span><span class="sxs-lookup"><span data-stu-id="3a19f-103">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
 <span data-ttu-id="3a19f-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="3a19f-104">\<system.identityModel></span></span>  
<span data-ttu-id="3a19f-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="3a19f-105">\<identityConfiguration></span></span>  
<span data-ttu-id="3a19f-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="3a19f-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="3a19f-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="3a19f-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="3a19f-108">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="3a19f-108">\<audienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a19f-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3a19f-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a19f-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3a19f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3a19f-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3a19f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a19f-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="3a19f-112">Attributes</span></span>  
  
|<span data-ttu-id="3a19f-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="3a19f-113">Attribute</span></span>|<span data-ttu-id="3a19f-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a19f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3a19f-115">modalità</span><span class="sxs-lookup"><span data-stu-id="3a19f-115">mode</span></span>|<span data-ttu-id="3a19f-116">Un <xref:System.IdentityModel.Selectors.AudienceUriMode> valore che specifica se la restrizione di gruppo di destinatari deve essere applicata a un token in ingresso.</span><span class="sxs-lookup"><span data-stu-id="3a19f-116">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="3a19f-117">I valori possibili sono "Sempre", "Mai" e "BearerKeyOnly".</span><span class="sxs-lookup"><span data-stu-id="3a19f-117">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="3a19f-118">Il valore predefinito è "Sempre".</span><span class="sxs-lookup"><span data-stu-id="3a19f-118">The default is "Always".</span></span> <span data-ttu-id="3a19f-119">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3a19f-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a19f-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3a19f-120">Child Elements</span></span>  
  
|<span data-ttu-id="3a19f-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a19f-121">Element</span></span>|<span data-ttu-id="3a19f-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a19f-122">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="3a19f-123">Aggiunge l'URI specificato da di `value` attributo alla raccolta di audienceUris.</span><span class="sxs-lookup"><span data-stu-id="3a19f-123">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="3a19f-124">L'attributo `value` è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3a19f-124">The `value` attribute is required.</span></span> <span data-ttu-id="3a19f-125">L'URI è tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="3a19f-125">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="3a19f-126">Cancella la raccolta di audienceUris.</span><span class="sxs-lookup"><span data-stu-id="3a19f-126">Clears the audienceUris collection.</span></span> <span data-ttu-id="3a19f-127">Tutti gli identificatori vengono rimossi dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="3a19f-127">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="3a19f-128">Rimuove l'URI specificato da di `value` attributo dalla raccolta di audienceUris.</span><span class="sxs-lookup"><span data-stu-id="3a19f-128">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="3a19f-129">L'attributo `value` è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3a19f-129">The `value` attribute is required.</span></span> <span data-ttu-id="3a19f-130">L'URI è tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="3a19f-130">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3a19f-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3a19f-131">Parent Elements</span></span>  
  
|<span data-ttu-id="3a19f-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a19f-132">Element</span></span>|<span data-ttu-id="3a19f-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a19f-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a19f-134">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="3a19f-134">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="3a19f-135">Fornisce la configurazione per una raccolta di sicurezza i gestori di token.</span><span class="sxs-lookup"><span data-stu-id="3a19f-135">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a19f-136">Note</span><span class="sxs-lookup"><span data-stu-id="3a19f-136">Remarks</span></span>  
 <span data-ttu-id="3a19f-137">Per impostazione predefinita, la raccolta è vuota. usare `<add>`, `<clear>`, e `<remove>` elementi per modificare la raccolta.</span><span class="sxs-lookup"><span data-stu-id="3a19f-137">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="3a19f-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> e <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> agli oggetti usano i valori nel gruppo di destinatari raccolta di URI per configurare qualsiasi consentito audience le restrizioni di URI in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> oggetti.</span><span class="sxs-lookup"><span data-stu-id="3a19f-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="3a19f-139">Il `<audienceUris>` elemento è rappresentato dal <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> classe.</span><span class="sxs-lookup"><span data-stu-id="3a19f-139">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="3a19f-140">Un singolo URI aggiunto alla raccolta è rappresentato dal <xref:System.IdentityModel.Configuration.AudienceUriElement> classe.</span><span class="sxs-lookup"><span data-stu-id="3a19f-140">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a19f-141">L'utilizzo dei `<audienceUris>` come elemento figlio dell'elemento di [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento è stato deprecato, ma è ancora supportata per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="3a19f-141">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="3a19f-142">Le impostazioni nel `<securityTokenHandlerConfiguration>` elemento sostituiscono quelle di `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="3a19f-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a19f-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="3a19f-143">Example</span></span>  
 <span data-ttu-id="3a19f-144">Il codice XML seguente viene illustrato come configurare il "audience" accettabili gli URI per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3a19f-144">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="3a19f-145">Questo esempio mostra come configurare un singolo URI.</span><span class="sxs-lookup"><span data-stu-id="3a19f-145">This example configures a single URI.</span></span> <span data-ttu-id="3a19f-146">I token con ambiti per questo URI verranno accettati, tutte le altre verranno rifiutate.</span><span class="sxs-lookup"><span data-stu-id="3a19f-146">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
