---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: a0db10ceb75a470dbf799d717b2059355dd104bb
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646071"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="4e729-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="4e729-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="4e729-102">Registra una cache per i token di sessione con un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4e729-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
<span data-ttu-id="4e729-103">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4e729-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4e729-104">&nbsp;&nbsp;[**\<>system.identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="4e729-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="4e729-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di identitàConfigurazione**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="4e729-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="4e729-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>nella cache**](caches.md)</span><span class="sxs-lookup"><span data-stu-id="4e729-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)</span></span>\
<span data-ttu-id="4e729-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>sessionSecurityTokenCache**</span><span class="sxs-lookup"><span data-stu-id="4e729-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e729-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e729-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e729-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4e729-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4e729-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4e729-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e729-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="4e729-111">Attributes</span></span>  
  
|<span data-ttu-id="4e729-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="4e729-112">Attribute</span></span>|<span data-ttu-id="4e729-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4e729-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4e729-114">type</span><span class="sxs-lookup"><span data-stu-id="4e729-114">type</span></span>|<span data-ttu-id="4e729-115">Tipo che deriva dalla <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> classe.</span><span class="sxs-lookup"><span data-stu-id="4e729-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e729-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4e729-116">Child Elements</span></span>  
 <span data-ttu-id="4e729-117">nessuno</span><span class="sxs-lookup"><span data-stu-id="4e729-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e729-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4e729-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4e729-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="4e729-119">Element</span></span>|<span data-ttu-id="4e729-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4e729-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e729-121">\<>nella cache</span><span class="sxs-lookup"><span data-stu-id="4e729-121">\<caches></span></span>](caches.md)|<span data-ttu-id="4e729-122">Registra le cache usate da un servizio o da una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4e729-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4e729-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="4e729-123">Example</span></span>  
 <span data-ttu-id="4e729-124">Nel codice XML seguente viene illustrata la configurazione<xref:System.IdentityModel.Tokens.SessionSecurityToken>di una cache personalizzata per il contenimento dei token di sicurezza della sessione ( ).</span><span class="sxs-lookup"><span data-stu-id="4e729-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="4e729-125">La configurazione viene `ClaimsAwareWebFarm` ricavata dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="4e729-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="4e729-126">Per ulteriori informazioni su questo esempio, vedere [Indice dell'esempio](https://docs.microsoft.com/previous-versions/dotnet/framework/security/wif-code-sample-index)di codice WIF .</span><span class="sxs-lookup"><span data-stu-id="4e729-126">For more information about this sample, see [WIF Code Sample Index](https://docs.microsoft.com/previous-versions/dotnet/framework/security/wif-code-sample-index).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4e729-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e729-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
