---
title: '&lt;sessionSecurityTokenCache&gt;'
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 024375cb114bb080c576ea033e5588526350ecdf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54510091"
---
# <a name="ltsessionsecuritytokencachegt"></a><span data-ttu-id="749be-102">&lt;sessionSecurityTokenCache&gt;</span><span class="sxs-lookup"><span data-stu-id="749be-102">&lt;sessionSecurityTokenCache&gt;</span></span>
<span data-ttu-id="749be-103">Registra una cache per i token di sessione con un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="749be-103">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="749be-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="749be-104">\<system.identityModel></span></span>  
<span data-ttu-id="749be-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="749be-105">\<identityConfiguration></span></span>  
<span data-ttu-id="749be-106">\<caches></span><span class="sxs-lookup"><span data-stu-id="749be-106">\<caches></span></span>  
<span data-ttu-id="749be-107">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="749be-107">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="749be-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="749be-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="749be-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="749be-109">Attributes and Elements</span></span>  
 <span data-ttu-id="749be-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="749be-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="749be-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="749be-111">Attributes</span></span>  
  
|<span data-ttu-id="749be-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="749be-112">Attribute</span></span>|<span data-ttu-id="749be-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="749be-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="749be-114">tipo</span><span class="sxs-lookup"><span data-stu-id="749be-114">type</span></span>|<span data-ttu-id="749be-115">Un tipo da cui deriva il <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> classe.</span><span class="sxs-lookup"><span data-stu-id="749be-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="749be-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="749be-116">Child Elements</span></span>  
 <span data-ttu-id="749be-117">nessuno</span><span class="sxs-lookup"><span data-stu-id="749be-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="749be-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="749be-118">Parent Elements</span></span>  
  
|<span data-ttu-id="749be-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="749be-119">Element</span></span>|<span data-ttu-id="749be-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="749be-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="749be-121">\<caches></span><span class="sxs-lookup"><span data-stu-id="749be-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="749be-122">Registra le cache utilizzate da un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="749be-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="749be-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="749be-123">Example</span></span>  
 <span data-ttu-id="749be-124">Il codice XML seguente viene illustrata la configurazione di una cache personalizzata per contenere i token di sicurezza della sessione (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="749be-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="749be-125">La configurazione è tratto dalla `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="749be-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="749be-126">Per altre informazioni su questo esempio, vedere [indice degli esempi di codice di WIF](../../../../../docs/framework/security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="749be-126">For more information about this sample, see [WIF Code Sample Index](../../../../../docs/framework/security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="749be-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="749be-127">See also</span></span>
- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
