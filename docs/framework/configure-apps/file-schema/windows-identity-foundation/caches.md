---
title: '&lt;Cache&gt;'
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: a91a389e53354e4f5b26e1510fc2f025300d65cc
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47192680"
---
# <a name="ltcachesgt"></a><span data-ttu-id="0d005-102">&lt;Cache&gt;</span><span class="sxs-lookup"><span data-stu-id="0d005-102">&lt;caches&gt;</span></span>
<span data-ttu-id="0d005-103">Registra le cache usate per il rilevamento riproduzione token e i token di sessione.</span><span class="sxs-lookup"><span data-stu-id="0d005-103">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="0d005-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="0d005-104">\<system.identityModel></span></span>  
<span data-ttu-id="0d005-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="0d005-105">\<identityConfiguration></span></span>  
<span data-ttu-id="0d005-106">\<memorizza nella cache ></span><span class="sxs-lookup"><span data-stu-id="0d005-106">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d005-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0d005-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d005-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0d005-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0d005-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0d005-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d005-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="0d005-110">Attributes</span></span>  
 <span data-ttu-id="0d005-111">nessuno</span><span class="sxs-lookup"><span data-stu-id="0d005-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0d005-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0d005-112">Child Elements</span></span>  
  
|<span data-ttu-id="0d005-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="0d005-113">Element</span></span>|<span data-ttu-id="0d005-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d005-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d005-115">\<sessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="0d005-115">\<sessionSecurityTokenCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|<span data-ttu-id="0d005-116">Registra una cache per i token di sessione con un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0d005-116">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="0d005-117">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="0d005-117">\<tokenReplayCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|<span data-ttu-id="0d005-118">Registra una cache di riproduzione dei token con un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0d005-118">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0d005-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0d005-119">Parent Elements</span></span>  
  
|<span data-ttu-id="0d005-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="0d005-120">Element</span></span>|<span data-ttu-id="0d005-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d005-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d005-122">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="0d005-122">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="0d005-123">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="0d005-123">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="0d005-124">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="0d005-124">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="0d005-125">Fornisce la configurazione per una raccolta di sicurezza i gestori di token.</span><span class="sxs-lookup"><span data-stu-id="0d005-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d005-126">Note</span><span class="sxs-lookup"><span data-stu-id="0d005-126">Remarks</span></span>  
 <span data-ttu-id="0d005-127">Oggetto `<caches>` elemento può essere specificato a livello di servizio con il `<identityConfiguration>` elemento o a livello di raccolta gestori di token di sicurezza nel `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="0d005-127">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="0d005-128">Le impostazioni in una raccolta di gestori di token sostituiscono quelle specificate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="0d005-128">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="0d005-129">Il `<caches>` elemento è rappresentato dal <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> classe.</span><span class="sxs-lookup"><span data-stu-id="0d005-129">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="0d005-130">Le cache configurate sono rappresentate dal <xref:System.IdentityModel.Configuration.IdentityModelCaches> classe.</span><span class="sxs-lookup"><span data-stu-id="0d005-130">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d005-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="0d005-131">Example</span></span>  
 <span data-ttu-id="0d005-132">Il codice XML seguente viene illustrata la configurazione di una cache personalizzata per contenere i token di sicurezza della sessione (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="0d005-132">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="0d005-133">La configurazione è tratto dalla `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="0d005-133">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
