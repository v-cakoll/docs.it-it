---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: bd04e4ebdf5c58adaeea0ff0ca5993d7d9ce38f1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252174"
---
# \<audienceUris>
<span data-ttu-id="23714-101">Specifica il set di URI che sono identificatori accettabili del relying party (RP).</span><span class="sxs-lookup"><span data-stu-id="23714-101">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="23714-102">I token non verranno accettati se non hanno come ambito uno degli URI dei gruppi di destinatari consentiti.</span><span class="sxs-lookup"><span data-stu-id="23714-102">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<audienceUris>**  
  
## <a name="syntax"></a><span data-ttu-id="23714-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23714-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23714-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="23714-104">Attributes and Elements</span></span>  
 <span data-ttu-id="23714-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="23714-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23714-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="23714-106">Attributes</span></span>  
  
|<span data-ttu-id="23714-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="23714-107">Attribute</span></span>|<span data-ttu-id="23714-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23714-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="23714-109">mode</span><span class="sxs-lookup"><span data-stu-id="23714-109">mode</span></span>|<span data-ttu-id="23714-110"><xref:System.IdentityModel.Selectors.AudienceUriMode>Valore che specifica se la restrizione dei destinatari deve essere applicata a un token in ingresso.</span><span class="sxs-lookup"><span data-stu-id="23714-110">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="23714-111">I valori possibili sono "Always", "Never" e "BearerKeyOnly".</span><span class="sxs-lookup"><span data-stu-id="23714-111">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="23714-112">Il valore predefinito è "Always".</span><span class="sxs-lookup"><span data-stu-id="23714-112">The default is "Always".</span></span> <span data-ttu-id="23714-113">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="23714-113">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="23714-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="23714-114">Child Elements</span></span>  
  
|<span data-ttu-id="23714-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="23714-115">Element</span></span>|<span data-ttu-id="23714-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23714-116">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="23714-117">Aggiunge l'URI specificato dall' `value` attributo alla raccolta audienceUris.</span><span class="sxs-lookup"><span data-stu-id="23714-117">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="23714-118">L'attributo `value` è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="23714-118">The `value` attribute is required.</span></span> <span data-ttu-id="23714-119">L'URI fa distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="23714-119">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="23714-120">Cancella la raccolta audienceUris.</span><span class="sxs-lookup"><span data-stu-id="23714-120">Clears the audienceUris collection.</span></span> <span data-ttu-id="23714-121">Tutti gli identificatori vengono rimossi dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="23714-121">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="23714-122">Rimuove l'URI specificato dall' `value` attributo dalla raccolta audienceUris.</span><span class="sxs-lookup"><span data-stu-id="23714-122">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="23714-123">L'attributo `value` è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="23714-123">The `value` attribute is required.</span></span> <span data-ttu-id="23714-124">L'URI fa distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="23714-124">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="23714-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="23714-125">Parent Elements</span></span>  
  
|<span data-ttu-id="23714-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="23714-126">Element</span></span>|<span data-ttu-id="23714-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23714-127">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="23714-128">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="23714-128">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23714-129">Commenti</span><span class="sxs-lookup"><span data-stu-id="23714-129">Remarks</span></span>  
 <span data-ttu-id="23714-130">Per impostazione predefinita, la raccolta è vuota; utilizzare `<add>` `<clear>` `<remove>` gli elementi, e per modificare la raccolta.</span><span class="sxs-lookup"><span data-stu-id="23714-130">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="23714-131"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler><xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>gli oggetti e usano i valori nella raccolta di URI dei destinatari per configurare eventuali restrizioni degli URI dei destinatari consentiti negli <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> oggetti.</span><span class="sxs-lookup"><span data-stu-id="23714-131"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="23714-132">L' `<audienceUris>` elemento è rappresentato dalla <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> classe.</span><span class="sxs-lookup"><span data-stu-id="23714-132">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="23714-133">Un singolo URI aggiunto alla raccolta è rappresentato dalla <xref:System.IdentityModel.Configuration.AudienceUriElement> classe.</span><span class="sxs-lookup"><span data-stu-id="23714-133">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="23714-134">L'uso dell' `<audienceUris>` elemento come elemento figlio dell' [\<identityConfiguration>](identityconfiguration.md) elemento è stato deprecato, ma è ancora supportato per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="23714-134">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="23714-135">Le impostazioni sull' `<securityTokenHandlerConfiguration>` elemento eseguono l'override di quelle nell' `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="23714-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23714-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="23714-136">Example</span></span>  
 <span data-ttu-id="23714-137">Nel codice XML seguente viene illustrato come configurare gli URI di audience accettabili per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="23714-137">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="23714-138">Questo esempio Mostra come configurare un singolo URI.</span><span class="sxs-lookup"><span data-stu-id="23714-138">This example configures a single URI.</span></span> <span data-ttu-id="23714-139">I token con ambito per questo URI verranno accettati, tutti gli altri verranno rifiutati.</span><span class="sxs-lookup"><span data-stu-id="23714-139">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
