---
title: Elemento <defaultFtpCachePolicy> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
ms.openlocfilehash: 7ff44f0251936d51b4e396c37c53322efa110227
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659414"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="b4e45-102">\<Elemento > defaultFtpCachePolicy (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="b4e45-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="b4e45-103">Descrive se la memorizzazione nella cache FTP è attiva e descrive i criteri di memorizzazione nella cache predefiniti.</span><span class="sxs-lookup"><span data-stu-id="b4e45-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="b4e45-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b4e45-104">\<configuration></span></span>  
<span data-ttu-id="b4e45-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b4e45-105">\<system.net></span></span>  
<span data-ttu-id="b4e45-106">\<requestCaching></span><span class="sxs-lookup"><span data-stu-id="b4e45-106">\<requestCaching></span></span>  
<span data-ttu-id="b4e45-107">\<defaultFtpCachePolicy></span><span class="sxs-lookup"><span data-stu-id="b4e45-107">\<defaultFtpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4e45-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b4e45-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4e45-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b4e45-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b4e45-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b4e45-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4e45-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="b4e45-111">Attributes</span></span>  
  
|<span data-ttu-id="b4e45-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="b4e45-112">Attribute</span></span>|<span data-ttu-id="b4e45-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4e45-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="b4e45-114">Specifica i criteri di memorizzazione nella cache FTP.</span><span class="sxs-lookup"><span data-stu-id="b4e45-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="b4e45-115">Il valore predefinito è `Default`.</span><span class="sxs-lookup"><span data-stu-id="b4e45-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="b4e45-116">policyLevel (attributo)</span><span class="sxs-lookup"><span data-stu-id="b4e45-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="b4e45-117">Value</span><span class="sxs-lookup"><span data-stu-id="b4e45-117">Value</span></span>|<span data-ttu-id="b4e45-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4e45-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="b4e45-119">Restituisce la risorsa memorizzata nella cache se la risorsa è aggiornata, la lunghezza del contenuto è precisa e sono presenti gli attributi relativi alla scadenza, alla modifica e alla lunghezza del contenuto.</span><span class="sxs-lookup"><span data-stu-id="b4e45-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="b4e45-120">Restituisce la risorsa dal server.</span><span class="sxs-lookup"><span data-stu-id="b4e45-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="b4e45-121">Restituisce la risorsa memorizzata nella cache se la lunghezza del contenuto è presente e corrisponde alla dimensione della voce.</span><span class="sxs-lookup"><span data-stu-id="b4e45-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="b4e45-122">Restituisce la risorsa memorizzata nella cache se viene fornita la lunghezza del contenuto e corrisponde alla dimensione della voce. in caso contrario, la risorsa viene scaricata dal server e viene restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="b4e45-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="b4e45-123">Restituisce la risorsa memorizzata nella cache se il timestamp della risorsa memorizzata nella cache corrisponde al timestamp della risorsa nel server. in caso contrario, la risorsa viene scaricata dal server, archiviata nella cache e restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="b4e45-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="b4e45-124">Scarica la risorsa dal server, la archivia nella cache e restituisce la risorsa al chiamante.</span><span class="sxs-lookup"><span data-stu-id="b4e45-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="b4e45-125">Se una risorsa memorizzata nella cache esiste, viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="b4e45-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="b4e45-126">La risorsa viene scaricata dal server e viene restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="b4e45-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="b4e45-127">Soddisfa una richiesta utilizzando la copia memorizzata nella cache della risorsa se il timestamp corrisponde al timestamp della risorsa nel server. in caso contrario, la risorsa viene scaricata dal server, presentata al chiamante e archiviata nella cache.</span><span class="sxs-lookup"><span data-stu-id="b4e45-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4e45-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b4e45-128">Child Elements</span></span>  
 <span data-ttu-id="b4e45-129">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b4e45-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b4e45-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b4e45-130">Parent Elements</span></span>  
  
|<span data-ttu-id="b4e45-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="b4e45-131">Element</span></span>|<span data-ttu-id="b4e45-132">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="b4e45-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4e45-133">requestCaching</span><span class="sxs-lookup"><span data-stu-id="b4e45-133">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="b4e45-134">Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="b4e45-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4e45-135">Note</span><span class="sxs-lookup"><span data-stu-id="b4e45-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4e45-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="b4e45-136">Example</span></span>  
 <span data-ttu-id="b4e45-137">Nell'esempio seguente viene illustrato come specificare un criterio di memorizzazione nella cache `NoCacheNoStore`FTP di.</span><span class="sxs-lookup"><span data-stu-id="b4e45-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultFtpCachePolicy  
        policyLevel="NoCacheNoStore">  
      </defaultFtpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b4e45-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4e45-138">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="b4e45-139">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="b4e45-139">Network Settings Schema</span></span>](index.md)
