---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 9be3bf980c3756678d26d8652271113d4daaba43
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943704"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="17a69-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="17a69-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="17a69-102">Registra una cache per i token di sessione con un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="17a69-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="17a69-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="17a69-103">\<system.identityModel></span></span>  
<span data-ttu-id="17a69-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="17a69-104">\<identityConfiguration></span></span>  
<span data-ttu-id="17a69-105">\<memorizza nella cache ></span><span class="sxs-lookup"><span data-stu-id="17a69-105">\<caches></span></span>  
<span data-ttu-id="17a69-106">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="17a69-106">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17a69-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17a69-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17a69-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="17a69-108">Attributes and Elements</span></span>  
 <span data-ttu-id="17a69-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="17a69-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17a69-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="17a69-110">Attributes</span></span>  
  
|<span data-ttu-id="17a69-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="17a69-111">Attribute</span></span>|<span data-ttu-id="17a69-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="17a69-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="17a69-113">type</span><span class="sxs-lookup"><span data-stu-id="17a69-113">type</span></span>|<span data-ttu-id="17a69-114">Tipo che deriva dalla <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> classe.</span><span class="sxs-lookup"><span data-stu-id="17a69-114">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="17a69-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="17a69-115">Child Elements</span></span>  
 <span data-ttu-id="17a69-116">Nessuna</span><span class="sxs-lookup"><span data-stu-id="17a69-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="17a69-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="17a69-117">Parent Elements</span></span>  
  
|<span data-ttu-id="17a69-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="17a69-118">Element</span></span>|<span data-ttu-id="17a69-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="17a69-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17a69-120">\<caches></span><span class="sxs-lookup"><span data-stu-id="17a69-120">\<caches></span></span>](caches.md)|<span data-ttu-id="17a69-121">Registra le cache utilizzate da un servizio o da una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="17a69-121">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="17a69-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="17a69-122">Example</span></span>  
 <span data-ttu-id="17a69-123">Nel codice XML seguente viene illustrata la configurazione di una cache personalizzata per i token di<xref:System.IdentityModel.Tokens.SessionSecurityToken>sicurezza della sessione ().</span><span class="sxs-lookup"><span data-stu-id="17a69-123">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="17a69-124">La configurazione è ricavata `ClaimsAwareWebFarm` dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="17a69-124">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="17a69-125">Per ulteriori informazioni su questo esempio, vedere [indice di esempio di codice WIF](../../../security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="17a69-125">For more information about this sample, see [WIF Code Sample Index](../../../security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="17a69-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17a69-126">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
