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
ms.openlocfilehash: f0c46532cb7716f4dc066f0e96c14534d7fa0b42
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltcachesgt"></a><span data-ttu-id="94b5a-102">&lt;memorizza nella cache&gt;</span><span class="sxs-lookup"><span data-stu-id="94b5a-102">&lt;caches&gt;</span></span>
<span data-ttu-id="94b5a-103">Registra le cache usate per i token di sessione e il rilevamento riproduzione token.</span><span class="sxs-lookup"><span data-stu-id="94b5a-103">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="94b5a-104">\<System. IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="94b5a-104">\<system.identityModel></span></span>  
<span data-ttu-id="94b5a-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="94b5a-105">\<identityConfiguration></span></span>  
<span data-ttu-id="94b5a-106">\<memorizza nella cache ></span><span class="sxs-lookup"><span data-stu-id="94b5a-106">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94b5a-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94b5a-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94b5a-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="94b5a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="94b5a-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="94b5a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94b5a-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="94b5a-110">Attributes</span></span>  
 <span data-ttu-id="94b5a-111">Nessuna</span><span class="sxs-lookup"><span data-stu-id="94b5a-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="94b5a-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="94b5a-112">Child Elements</span></span>  
  
|<span data-ttu-id="94b5a-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="94b5a-113">Element</span></span>|<span data-ttu-id="94b5a-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94b5a-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94b5a-115">\<sessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="94b5a-115">\<sessionSecurityTokenCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|<span data-ttu-id="94b5a-116">Registra una cache per i token di sessione con un servizio o una raccolta di gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="94b5a-116">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="94b5a-117">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="94b5a-117">\<tokenReplayCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|<span data-ttu-id="94b5a-118">Registra una cache di riproduzione token con un servizio o una raccolta di gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="94b5a-118">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="94b5a-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="94b5a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="94b5a-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="94b5a-120">Element</span></span>|<span data-ttu-id="94b5a-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94b5a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94b5a-122">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="94b5a-122">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="94b5a-123">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="94b5a-123">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="94b5a-124">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="94b5a-124">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="94b5a-125">Fornisce la configurazione per una raccolta di sicurezza gestori di token.</span><span class="sxs-lookup"><span data-stu-id="94b5a-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94b5a-126">Note</span><span class="sxs-lookup"><span data-stu-id="94b5a-126">Remarks</span></span>  
 <span data-ttu-id="94b5a-127">A `<caches>` elemento può essere specificato a livello di servizio sotto il `<identityConfiguration>` elemento o a livello di raccolta gestore dei token di sicurezza nel `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="94b5a-127">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="94b5a-128">Le impostazioni in una raccolta di gestore del token sostituiscono quelle specificate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="94b5a-128">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="94b5a-129">Il `<caches>` elemento è rappresentato dalla <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> classe.</span><span class="sxs-lookup"><span data-stu-id="94b5a-129">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="94b5a-130">Le cache configurate sono rappresentate dalla <xref:System.IdentityModel.Configuration.IdentityModelCaches> classe.</span><span class="sxs-lookup"><span data-stu-id="94b5a-130">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94b5a-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="94b5a-131">Example</span></span>  
 <span data-ttu-id="94b5a-132">Il codice XML seguente viene illustrata la configurazione di una cache personalizzata per la sessione come token di sicurezza (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="94b5a-132">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="94b5a-133">Da cui proviene la configurazione di `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="94b5a-133">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
