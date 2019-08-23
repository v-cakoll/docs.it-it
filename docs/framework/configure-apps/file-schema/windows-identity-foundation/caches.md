---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 5ad75ae18772d6e7c724f2cbf40c1e3083d5c345
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941971"
---
# <a name="caches"></a><span data-ttu-id="65a1b-101">\<memorizza nella cache ></span><span class="sxs-lookup"><span data-stu-id="65a1b-101">\<caches></span></span>
<span data-ttu-id="65a1b-102">Registra le cache utilizzate per i token di sessione e il rilevamento della riproduzione dei token.</span><span class="sxs-lookup"><span data-stu-id="65a1b-102">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="65a1b-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="65a1b-103">\<system.identityModel></span></span>  
<span data-ttu-id="65a1b-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="65a1b-104">\<identityConfiguration></span></span>  
<span data-ttu-id="65a1b-105">\<memorizza nella cache ></span><span class="sxs-lookup"><span data-stu-id="65a1b-105">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65a1b-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="65a1b-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65a1b-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="65a1b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="65a1b-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="65a1b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65a1b-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="65a1b-109">Attributes</span></span>  
 <span data-ttu-id="65a1b-110">Nessuna</span><span class="sxs-lookup"><span data-stu-id="65a1b-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="65a1b-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="65a1b-111">Child Elements</span></span>  
  
|<span data-ttu-id="65a1b-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="65a1b-112">Element</span></span>|<span data-ttu-id="65a1b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="65a1b-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65a1b-114">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="65a1b-114">\<sessionSecurityTokenCache></span></span>](sessionsecuritytokencache.md)|<span data-ttu-id="65a1b-115">Registra una cache per i token di sessione con un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="65a1b-115">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="65a1b-116">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="65a1b-116">\<tokenReplayCache></span></span>](tokenreplaycache.md)|<span data-ttu-id="65a1b-117">Registra una cache di riproduzione dei token con un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="65a1b-117">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="65a1b-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="65a1b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="65a1b-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="65a1b-119">Element</span></span>|<span data-ttu-id="65a1b-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="65a1b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65a1b-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="65a1b-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="65a1b-122">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="65a1b-122">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="65a1b-123">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="65a1b-123">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="65a1b-124">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="65a1b-124">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65a1b-125">Note</span><span class="sxs-lookup"><span data-stu-id="65a1b-125">Remarks</span></span>  
 <span data-ttu-id="65a1b-126">Un `<caches>` elemento può essere specificato a livello di servizio `<identityConfiguration>` nell'elemento o nel livello di raccolta del gestore del token di sicurezza `<securityTokenHandlerConfiguration>` sotto l'elemento.</span><span class="sxs-lookup"><span data-stu-id="65a1b-126">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="65a1b-127">Le impostazioni in una raccolta di gestori di token eseguono l'override di quelle specificate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="65a1b-127">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="65a1b-128">L' `<caches>` elemento è rappresentato <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="65a1b-128">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="65a1b-129">Le cache configurate sono rappresentate <xref:System.IdentityModel.Configuration.IdentityModelCaches> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="65a1b-129">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65a1b-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="65a1b-130">Example</span></span>  
 <span data-ttu-id="65a1b-131">Nel codice XML seguente viene illustrata la configurazione di una cache personalizzata per i token di<xref:System.IdentityModel.Tokens.SessionSecurityToken>sicurezza della sessione ().</span><span class="sxs-lookup"><span data-stu-id="65a1b-131">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="65a1b-132">La configurazione è ricavata `ClaimsAwareWebFarm` dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="65a1b-132">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
