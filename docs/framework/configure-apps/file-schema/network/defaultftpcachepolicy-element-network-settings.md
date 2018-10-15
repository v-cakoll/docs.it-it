---
title: '&lt;defaultFtpCachePolicy&gt; (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
author: mcleblanc
ms.author: markl
ms.openlocfilehash: e03fb02bd351058c1fcdedb8367d03318418a12c
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2018
ms.locfileid: "49316441"
---
# <a name="ltdefaultftpcachepolicygt-element-network-settings"></a><span data-ttu-id="db33b-102">&lt;defaultFtpCachePolicy&gt; (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="db33b-102">&lt;defaultFtpCachePolicy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="db33b-103">Indica se la memorizzazione nella cache FTP è attivo e ne descrive l'impostazione predefinita dei criteri di memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="db33b-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="db33b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="db33b-104">\<configuration></span></span>  
<span data-ttu-id="db33b-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="db33b-105">\<system.net></span></span>  
<span data-ttu-id="db33b-106">\<requestCaching ></span><span class="sxs-lookup"><span data-stu-id="db33b-106">\<requestCaching></span></span>  
<span data-ttu-id="db33b-107">\<defaultFtpCachePolicy ></span><span class="sxs-lookup"><span data-stu-id="db33b-107">\<defaultFtpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db33b-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="db33b-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db33b-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="db33b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="db33b-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="db33b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db33b-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="db33b-111">Attributes</span></span>  
  
|<span data-ttu-id="db33b-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="db33b-112">Attribute</span></span>|<span data-ttu-id="db33b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db33b-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="db33b-114">Specifica il protocollo FTP dei criteri di memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="db33b-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="db33b-115">Il valore predefinito è `Default`.</span><span class="sxs-lookup"><span data-stu-id="db33b-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="db33b-116">Attributo policyLevel</span><span class="sxs-lookup"><span data-stu-id="db33b-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="db33b-117">Valore</span><span class="sxs-lookup"><span data-stu-id="db33b-117">Value</span></span>|<span data-ttu-id="db33b-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db33b-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="db33b-119">Restituisce la risorsa memorizzata nella cache se la risorsa è aggiornata, la lunghezza del contenuto è precisa e la scadenza, modifica e gli attributi di lunghezza del contenuto sono presenti.</span><span class="sxs-lookup"><span data-stu-id="db33b-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="db33b-120">Restituisce la risorsa dal server.</span><span class="sxs-lookup"><span data-stu-id="db33b-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="db33b-121">Restituisce la risorsa memorizzata nella cache se la lunghezza del contenuto è presente e corrisponde alla dimensione dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="db33b-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="db33b-122">Restituisce la risorsa memorizzata nella cache se la lunghezza del contenuto viene fornita e corrisponde alla dimensione dell'elemento; in caso contrario, la risorsa viene scaricata dal server e viene restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="db33b-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="db33b-123">Restituisce la risorsa memorizzata nella cache se il timestamp della risorsa memorizzata nella cache è identico a quello della risorsa del server. in caso contrario, la risorsa viene scaricata dal server di, memorizzata nella cache e restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="db33b-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="db33b-124">Scarica la risorsa dal server, viene memorizzato nella cache e la risorsa viene restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="db33b-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="db33b-125">Se esiste una risorsa memorizzata nella cache, viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="db33b-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="db33b-126">La risorsa viene scaricata dal server e viene restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="db33b-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="db33b-127">Soddisfa una richiesta mediante la copia memorizzata nella cache della risorsa se il timestamp è identico a quello della risorsa del server. in caso contrario, la risorsa viene scaricata dal server di, presentata al chiamante e memorizzata nella cache.</span><span class="sxs-lookup"><span data-stu-id="db33b-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db33b-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="db33b-128">Child Elements</span></span>  
 <span data-ttu-id="db33b-129">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="db33b-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="db33b-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="db33b-130">Parent Elements</span></span>  
  
|<span data-ttu-id="db33b-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="db33b-131">Element</span></span>|<span data-ttu-id="db33b-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db33b-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db33b-133">requestCaching</span><span class="sxs-lookup"><span data-stu-id="db33b-133">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="db33b-134">Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="db33b-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db33b-135">Note</span><span class="sxs-lookup"><span data-stu-id="db33b-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="db33b-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="db33b-136">Example</span></span>  
 <span data-ttu-id="db33b-137">Nell'esempio seguente viene illustrato come specificare un criterio della cache FTP `NoCacheNoStore`.</span><span class="sxs-lookup"><span data-stu-id="db33b-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="db33b-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db33b-138">See Also</span></span>  
 <xref:System.Net.Cache>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.Cache.RequestCacheLevel>  
 [<span data-ttu-id="db33b-139">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="db33b-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
