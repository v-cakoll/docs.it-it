---
title: '&lt;sessionSecurityTokenCache&gt;'
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 0b0d3c01a81f110f79f64d75aa2ab2ff2873fedd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltsessionsecuritytokencachegt"></a><span data-ttu-id="813e2-102">&lt;sessionSecurityTokenCache&gt;</span><span class="sxs-lookup"><span data-stu-id="813e2-102">&lt;sessionSecurityTokenCache&gt;</span></span>
<span data-ttu-id="813e2-103">Registra una cache per i token di sessione con un servizio o una raccolta di gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="813e2-103">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="813e2-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="813e2-104">\<system.identityModel></span></span>  
<span data-ttu-id="813e2-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="813e2-105">\<identityConfiguration></span></span>  
<span data-ttu-id="813e2-106">\<memorizza nella cache ></span><span class="sxs-lookup"><span data-stu-id="813e2-106">\<caches></span></span>  
<span data-ttu-id="813e2-107">\<sessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="813e2-107">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="813e2-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="813e2-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <sessionSecurityTokenCache type=xs:string>  
      </sessionSecurityTokenCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="813e2-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="813e2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="813e2-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="813e2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="813e2-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="813e2-111">Attributes</span></span>  
  
|<span data-ttu-id="813e2-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="813e2-112">Attribute</span></span>|<span data-ttu-id="813e2-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="813e2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="813e2-114">tipo</span><span class="sxs-lookup"><span data-stu-id="813e2-114">type</span></span>|<span data-ttu-id="813e2-115">Un tipo da cui deriva il <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> classe.</span><span class="sxs-lookup"><span data-stu-id="813e2-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="813e2-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="813e2-116">Child Elements</span></span>  
 <span data-ttu-id="813e2-117">Nessuno</span><span class="sxs-lookup"><span data-stu-id="813e2-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="813e2-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="813e2-118">Parent Elements</span></span>  
  
|<span data-ttu-id="813e2-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="813e2-119">Element</span></span>|<span data-ttu-id="813e2-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="813e2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="813e2-121">\<memorizza nella cache ></span><span class="sxs-lookup"><span data-stu-id="813e2-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="813e2-122">Registra la cache utilizzate da un servizio o una raccolta di gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="813e2-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="813e2-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="813e2-123">Example</span></span>  
 <span data-ttu-id="813e2-124">Il codice XML seguente viene illustrata la configurazione di una cache personalizzata per la sessione come token di sicurezza (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="813e2-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="813e2-125">Da cui proviene la configurazione di `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="813e2-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="813e2-126">Per ulteriori informazioni su questo esempio, vedere [indice degli esempi di codice WIF](../../../../../docs/framework/security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="813e2-126">For more information about this sample, see [WIF Code Sample Index](../../../../../docs/framework/security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="813e2-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="813e2-127">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
