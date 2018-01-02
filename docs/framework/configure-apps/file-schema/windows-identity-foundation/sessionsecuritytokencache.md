---
title: '&lt;sessionSecurityTokenCache&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 9f4b87d6c620a07ee831888086bdab75a689875e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltsessionsecuritytokencachegt"></a><span data-ttu-id="99966-102">&lt;sessionSecurityTokenCache&gt;</span><span class="sxs-lookup"><span data-stu-id="99966-102">&lt;sessionSecurityTokenCache&gt;</span></span>
<span data-ttu-id="99966-103">Registra una cache per i token di sessione con un servizio o una raccolta di gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="99966-103">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="99966-104">\<System. IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="99966-104">\<system.identityModel></span></span>  
<span data-ttu-id="99966-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="99966-105">\<identityConfiguration></span></span>  
<span data-ttu-id="99966-106">\<memorizza nella cache ></span><span class="sxs-lookup"><span data-stu-id="99966-106">\<caches></span></span>  
<span data-ttu-id="99966-107">\<sessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="99966-107">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99966-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99966-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99966-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="99966-109">Attributes and Elements</span></span>  
 <span data-ttu-id="99966-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="99966-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99966-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="99966-111">Attributes</span></span>  
  
|<span data-ttu-id="99966-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="99966-112">Attribute</span></span>|<span data-ttu-id="99966-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99966-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99966-114">tipo</span><span class="sxs-lookup"><span data-stu-id="99966-114">type</span></span>|<span data-ttu-id="99966-115">Un tipo da cui deriva il <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> classe.</span><span class="sxs-lookup"><span data-stu-id="99966-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99966-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="99966-116">Child Elements</span></span>  
 <span data-ttu-id="99966-117">None</span><span class="sxs-lookup"><span data-stu-id="99966-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99966-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="99966-118">Parent Elements</span></span>  
  
|<span data-ttu-id="99966-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="99966-119">Element</span></span>|<span data-ttu-id="99966-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99966-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99966-121">\<memorizza nella cache ></span><span class="sxs-lookup"><span data-stu-id="99966-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="99966-122">Registra la cache utilizzate da un servizio o una raccolta di gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="99966-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="99966-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="99966-123">Example</span></span>  
 <span data-ttu-id="99966-124">Il codice XML seguente viene illustrata la configurazione di una cache personalizzata per la sessione come token di sicurezza (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="99966-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="99966-125">Da cui proviene la configurazione di `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="99966-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="99966-126">Per ulteriori informazioni su questo esempio, vedere [indice degli esempi di codice WIF](../../../../../docs/framework/security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="99966-126">For more information about this sample, see [WIF Code Sample Index](../../../../../docs/framework/security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="99966-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99966-127">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
