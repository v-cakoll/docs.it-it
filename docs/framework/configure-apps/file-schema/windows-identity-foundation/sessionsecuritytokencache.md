---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: e949b16f76f20191b84bbbbb6e8b019d913316f0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251839"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="b1c12-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="b1c12-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="b1c12-102">Registra una cache per i token di sessione con un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b1c12-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
<span data-ttu-id="b1c12-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b1c12-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b1c12-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="b1c12-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="b1c12-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="b1c12-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="b1c12-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memorizza nella cache >** ](caches.md)</span><span class="sxs-lookup"><span data-stu-id="b1c12-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)</span></span>\
<span data-ttu-id="b1c12-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> sessionSecurityTokenCache**</span><span class="sxs-lookup"><span data-stu-id="b1c12-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1c12-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b1c12-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1c12-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b1c12-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b1c12-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b1c12-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1c12-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="b1c12-111">Attributes</span></span>  
  
|<span data-ttu-id="b1c12-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="b1c12-112">Attribute</span></span>|<span data-ttu-id="b1c12-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="b1c12-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b1c12-114">type</span><span class="sxs-lookup"><span data-stu-id="b1c12-114">type</span></span>|<span data-ttu-id="b1c12-115">Tipo che deriva dalla <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> classe.</span><span class="sxs-lookup"><span data-stu-id="b1c12-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b1c12-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b1c12-116">Child Elements</span></span>  
 <span data-ttu-id="b1c12-117">Nessuna</span><span class="sxs-lookup"><span data-stu-id="b1c12-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b1c12-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b1c12-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b1c12-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="b1c12-119">Element</span></span>|<span data-ttu-id="b1c12-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b1c12-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1c12-121">\<caches></span><span class="sxs-lookup"><span data-stu-id="b1c12-121">\<caches></span></span>](caches.md)|<span data-ttu-id="b1c12-122">Registra le cache utilizzate da un servizio o da una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b1c12-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b1c12-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="b1c12-123">Example</span></span>  
 <span data-ttu-id="b1c12-124">Nel codice XML seguente viene illustrata la configurazione di una cache personalizzata per i token di<xref:System.IdentityModel.Tokens.SessionSecurityToken>sicurezza della sessione ().</span><span class="sxs-lookup"><span data-stu-id="b1c12-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="b1c12-125">La configurazione è ricavata `ClaimsAwareWebFarm` dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="b1c12-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="b1c12-126">Per ulteriori informazioni su questo esempio, vedere [indice di esempio di codice WIF](../../../security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="b1c12-126">For more information about this sample, see [WIF Code Sample Index](../../../security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1c12-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1c12-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
