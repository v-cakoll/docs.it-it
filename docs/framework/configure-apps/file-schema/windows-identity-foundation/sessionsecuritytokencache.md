---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: a0db10ceb75a470dbf799d717b2059355dd104bb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "81646071"
---
# \<sessionSecurityTokenCache>
<span data-ttu-id="61f99-101">Registra una cache per i token di sessione con un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="61f99-101">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**  
  
## <a name="syntax"></a><span data-ttu-id="61f99-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61f99-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61f99-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="61f99-103">Attributes and Elements</span></span>  
 <span data-ttu-id="61f99-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="61f99-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61f99-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="61f99-105">Attributes</span></span>  
  
|<span data-ttu-id="61f99-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="61f99-106">Attribute</span></span>|<span data-ttu-id="61f99-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61f99-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="61f99-108">type</span><span class="sxs-lookup"><span data-stu-id="61f99-108">type</span></span>|<span data-ttu-id="61f99-109">Tipo che deriva dalla <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> classe.</span><span class="sxs-lookup"><span data-stu-id="61f99-109">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61f99-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="61f99-110">Child Elements</span></span>  
 <span data-ttu-id="61f99-111">nessuno</span><span class="sxs-lookup"><span data-stu-id="61f99-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="61f99-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="61f99-112">Parent Elements</span></span>  
  
|<span data-ttu-id="61f99-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="61f99-113">Element</span></span>|<span data-ttu-id="61f99-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61f99-114">Description</span></span>|  
|-------------|-----------------|  
|[\<caches>](caches.md)|<span data-ttu-id="61f99-115">Registra le cache utilizzate da un servizio o da una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="61f99-115">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="61f99-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="61f99-116">Example</span></span>  
 <span data-ttu-id="61f99-117">Nel codice XML seguente viene illustrata la configurazione di una cache personalizzata per i token di sicurezza della sessione ( <xref:System.IdentityModel.Tokens.SessionSecurityToken> ).</span><span class="sxs-lookup"><span data-stu-id="61f99-117">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="61f99-118">La configurazione è ricavata dall' `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="61f99-118">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="61f99-119">Per ulteriori informazioni su questo esempio, vedere [indice di esempio di codice WIF](https://docs.microsoft.com/previous-versions/dotnet/framework/security/wif-code-sample-index).</span><span class="sxs-lookup"><span data-stu-id="61f99-119">For more information about this sample, see [WIF Code Sample Index](https://docs.microsoft.com/previous-versions/dotnet/framework/security/wif-code-sample-index).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="61f99-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61f99-120">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
