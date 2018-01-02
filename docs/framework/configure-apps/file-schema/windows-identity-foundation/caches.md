---
title: '&lt;memorizza nella cache&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: b9dfa7b2f0952f3f9e224ad51fd4d9c0c263ce04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltcachesgt"></a><span data-ttu-id="79e2b-102">&lt;memorizza nella cache&gt;</span><span class="sxs-lookup"><span data-stu-id="79e2b-102">&lt;caches&gt;</span></span>
<span data-ttu-id="79e2b-103">Registra le cache usate per i token di sessione e il rilevamento riproduzione token.</span><span class="sxs-lookup"><span data-stu-id="79e2b-103">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="79e2b-104">\<System. IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="79e2b-104">\<system.identityModel></span></span>  
<span data-ttu-id="79e2b-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="79e2b-105">\<identityConfiguration></span></span>  
<span data-ttu-id="79e2b-106">\<memorizza nella cache ></span><span class="sxs-lookup"><span data-stu-id="79e2b-106">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79e2b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="79e2b-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79e2b-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="79e2b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="79e2b-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="79e2b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79e2b-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="79e2b-110">Attributes</span></span>  
 <span data-ttu-id="79e2b-111">nessuno</span><span class="sxs-lookup"><span data-stu-id="79e2b-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="79e2b-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="79e2b-112">Child Elements</span></span>  
  
|<span data-ttu-id="79e2b-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="79e2b-113">Element</span></span>|<span data-ttu-id="79e2b-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79e2b-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79e2b-115">\<sessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="79e2b-115">\<sessionSecurityTokenCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|<span data-ttu-id="79e2b-116">Registra una cache per i token di sessione con un servizio o una raccolta di gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="79e2b-116">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="79e2b-117">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="79e2b-117">\<tokenReplayCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|<span data-ttu-id="79e2b-118">Registra una cache di riproduzione token con un servizio o una raccolta di gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="79e2b-118">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="79e2b-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="79e2b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="79e2b-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="79e2b-120">Element</span></span>|<span data-ttu-id="79e2b-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79e2b-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79e2b-122">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="79e2b-122">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="79e2b-123">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="79e2b-123">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="79e2b-124">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="79e2b-124">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="79e2b-125">Fornisce la configurazione per una raccolta di sicurezza gestori di token.</span><span class="sxs-lookup"><span data-stu-id="79e2b-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79e2b-126">Note</span><span class="sxs-lookup"><span data-stu-id="79e2b-126">Remarks</span></span>  
 <span data-ttu-id="79e2b-127">A `<caches>` elemento può essere specificato a livello di servizio sotto il `<identityConfiguration>` elemento o a livello di raccolta gestore dei token di sicurezza nel `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="79e2b-127">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="79e2b-128">Le impostazioni in una raccolta di gestore del token sostituiscono quelle specificate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="79e2b-128">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="79e2b-129">Il `<caches>` elemento è rappresentato dalla <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> classe.</span><span class="sxs-lookup"><span data-stu-id="79e2b-129">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="79e2b-130">Le cache configurate sono rappresentate dalla <xref:System.IdentityModel.Configuration.IdentityModelCaches> classe.</span><span class="sxs-lookup"><span data-stu-id="79e2b-130">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79e2b-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="79e2b-131">Example</span></span>  
 <span data-ttu-id="79e2b-132">Il codice XML seguente viene illustrata la configurazione di una cache personalizzata per la sessione come token di sicurezza (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="79e2b-132">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="79e2b-133">Da cui proviene la configurazione di `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="79e2b-133">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
