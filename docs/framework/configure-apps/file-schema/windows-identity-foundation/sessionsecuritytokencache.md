---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 5c68fe618f965f364a3716c3bc65de5e165b12ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793796"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="d7ef3-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="d7ef3-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="d7ef3-102">Registra una cache per i token di sessione con un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d7ef3-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="d7ef3-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d7ef3-103">\<system.identityModel></span></span>  
<span data-ttu-id="d7ef3-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d7ef3-104">\<identityConfiguration></span></span>  
<span data-ttu-id="d7ef3-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="d7ef3-105">\<caches></span></span>  
<span data-ttu-id="d7ef3-106">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="d7ef3-106">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7ef3-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d7ef3-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7ef3-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d7ef3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d7ef3-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d7ef3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7ef3-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="d7ef3-110">Attributes</span></span>  
  
|<span data-ttu-id="d7ef3-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="d7ef3-111">Attribute</span></span>|<span data-ttu-id="d7ef3-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7ef3-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d7ef3-113">tipo</span><span class="sxs-lookup"><span data-stu-id="d7ef3-113">type</span></span>|<span data-ttu-id="d7ef3-114">Un tipo da cui deriva il <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> classe.</span><span class="sxs-lookup"><span data-stu-id="d7ef3-114">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d7ef3-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d7ef3-115">Child Elements</span></span>  
 <span data-ttu-id="d7ef3-116">nessuno</span><span class="sxs-lookup"><span data-stu-id="d7ef3-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d7ef3-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d7ef3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d7ef3-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="d7ef3-118">Element</span></span>|<span data-ttu-id="d7ef3-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7ef3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7ef3-120">\<caches></span><span class="sxs-lookup"><span data-stu-id="d7ef3-120">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="d7ef3-121">Registra le cache utilizzate da un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d7ef3-121">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d7ef3-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="d7ef3-122">Example</span></span>  
 <span data-ttu-id="d7ef3-123">Il codice XML seguente viene illustrata la configurazione di una cache personalizzata per contenere i token di sicurezza della sessione (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="d7ef3-123">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="d7ef3-124">La configurazione è tratto dalla `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="d7ef3-124">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="d7ef3-125">Per altre informazioni su questo esempio, vedere [indice degli esempi di codice di WIF](../../../../../docs/framework/security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="d7ef3-125">For more information about this sample, see [WIF Code Sample Index](../../../../../docs/framework/security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7ef3-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7ef3-126">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
