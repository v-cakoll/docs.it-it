---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: b1d04280ef993297102d446ba5a7db54e8404dd8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750787"
---
# <a name="caches"></a><span data-ttu-id="c7c20-101">\<caches></span><span class="sxs-lookup"><span data-stu-id="c7c20-101">\<caches></span></span>
<span data-ttu-id="c7c20-102">Registra le cache usate per il rilevamento riproduzione token e i token di sessione.</span><span class="sxs-lookup"><span data-stu-id="c7c20-102">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="c7c20-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="c7c20-103">\<system.identityModel></span></span>  
<span data-ttu-id="c7c20-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="c7c20-104">\<identityConfiguration></span></span>  
<span data-ttu-id="c7c20-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="c7c20-105">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7c20-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c7c20-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7c20-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c7c20-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c7c20-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c7c20-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7c20-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="c7c20-109">Attributes</span></span>  
 <span data-ttu-id="c7c20-110">nessuno</span><span class="sxs-lookup"><span data-stu-id="c7c20-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c7c20-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c7c20-111">Child Elements</span></span>  
  
|<span data-ttu-id="c7c20-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="c7c20-112">Element</span></span>|<span data-ttu-id="c7c20-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7c20-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c7c20-114">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="c7c20-114">\<sessionSecurityTokenCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|<span data-ttu-id="c7c20-115">Registra una cache per i token di sessione con un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c7c20-115">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="c7c20-116">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="c7c20-116">\<tokenReplayCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|<span data-ttu-id="c7c20-117">Registra una cache di riproduzione dei token con un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c7c20-117">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c7c20-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c7c20-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c7c20-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="c7c20-119">Element</span></span>|<span data-ttu-id="c7c20-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7c20-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c7c20-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="c7c20-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="c7c20-122">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="c7c20-122">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="c7c20-123">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="c7c20-123">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="c7c20-124">Fornisce la configurazione per una raccolta di sicurezza i gestori di token.</span><span class="sxs-lookup"><span data-stu-id="c7c20-124">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7c20-125">Note</span><span class="sxs-lookup"><span data-stu-id="c7c20-125">Remarks</span></span>  
 <span data-ttu-id="c7c20-126">Oggetto `<caches>` elemento può essere specificato a livello di servizio con il `<identityConfiguration>` elemento o a livello di raccolta gestori di token di sicurezza nel `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="c7c20-126">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="c7c20-127">Le impostazioni in una raccolta di gestori di token sostituiscono quelle specificate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="c7c20-127">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="c7c20-128">Il `<caches>` elemento è rappresentato dal <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> classe.</span><span class="sxs-lookup"><span data-stu-id="c7c20-128">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="c7c20-129">Le cache configurate sono rappresentate dal <xref:System.IdentityModel.Configuration.IdentityModelCaches> classe.</span><span class="sxs-lookup"><span data-stu-id="c7c20-129">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7c20-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="c7c20-130">Example</span></span>  
 <span data-ttu-id="c7c20-131">Il codice XML seguente viene illustrata la configurazione di una cache personalizzata per contenere i token di sicurezza della sessione (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="c7c20-131">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="c7c20-132">La configurazione è tratto dalla `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="c7c20-132">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
