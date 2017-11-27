---
title: '&lt;defaultFtpCachePolicy&gt; elemento (impostazioni di rete)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 6b9a5fb2f62c27d278570ad789deab30917bc432
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltdefaultftpcachepolicygt-element-network-settings"></a><span data-ttu-id="89975-102">&lt;defaultFtpCachePolicy&gt; elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="89975-102">&lt;defaultFtpCachePolicy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="89975-103">Indica se la memorizzazione nella cache FTP è attivo e descrive il valore predefinito di criteri di memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="89975-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="89975-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="89975-104">\<configuration></span></span>  
<span data-ttu-id="89975-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="89975-105">\<system.net></span></span>  
<span data-ttu-id="89975-106">\<requestCaching ></span><span class="sxs-lookup"><span data-stu-id="89975-106">\<requestCaching></span></span>  
<span data-ttu-id="89975-107">\<defaultFtpCachePolicy ></span><span class="sxs-lookup"><span data-stu-id="89975-107">\<defaultFtpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89975-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89975-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89975-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="89975-109">Attributes and Elements</span></span>  
 <span data-ttu-id="89975-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="89975-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89975-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="89975-111">Attributes</span></span>  
  
|<span data-ttu-id="89975-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="89975-112">Attribute</span></span>|<span data-ttu-id="89975-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89975-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="89975-114">Specifica il protocollo FTP criteri di memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="89975-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="89975-115">Il valore predefinito è `Default`.</span><span class="sxs-lookup"><span data-stu-id="89975-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="89975-116">Attributo policyLevel</span><span class="sxs-lookup"><span data-stu-id="89975-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="89975-117">Valore</span><span class="sxs-lookup"><span data-stu-id="89975-117">Value</span></span>|<span data-ttu-id="89975-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89975-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="89975-119">Restituisce la risorsa memorizzata nella cache se la risorsa viene aggiornata, la lunghezza del contenuto è precisa e la scadenza, modifica e gli attributi di lunghezza del contenuto sono presenti.</span><span class="sxs-lookup"><span data-stu-id="89975-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="89975-120">Restituisce la risorsa dal server.</span><span class="sxs-lookup"><span data-stu-id="89975-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="89975-121">Restituisce la risorsa memorizzata nella cache se la lunghezza del contenuto è presente e corrisponde alla dimensione dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="89975-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="89975-122">Restituisce la risorsa memorizzata nella cache se la lunghezza del contenuto viene fornita e corrisponde alla dimensione dell'elemento; in caso contrario, la risorsa viene scaricata dal server e viene restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="89975-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="89975-123">Restituisce la risorsa memorizzata nella cache, se il timestamp della risorsa nella cache è identico a quello della risorsa del server. in caso contrario, la risorsa viene scaricata dal server di, memorizzata nella cache e restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="89975-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="89975-124">Scarica la risorsa dal server, viene memorizzato nella cache e la restituisce al chiamante.</span><span class="sxs-lookup"><span data-stu-id="89975-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="89975-125">Se esiste una risorsa memorizzati nella cache, viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="89975-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="89975-126">La risorsa viene scaricata dal server e viene restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="89975-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="89975-127">Soddisfa una richiesta tramite la copia memorizzata nella cache della risorsa, se il timestamp è identico a quello della risorsa del server. in caso contrario, la risorsa viene scaricata dal server di, presentata al chiamante e memorizzata nella cache.</span><span class="sxs-lookup"><span data-stu-id="89975-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89975-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="89975-128">Child Elements</span></span>  
 <span data-ttu-id="89975-129">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="89975-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="89975-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="89975-130">Parent Elements</span></span>  
  
|<span data-ttu-id="89975-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="89975-131">Element</span></span>|<span data-ttu-id="89975-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89975-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89975-133">requestCaching</span><span class="sxs-lookup"><span data-stu-id="89975-133">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="89975-134">Controlla il meccanismo di memorizzazione nella cache delle richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="89975-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89975-135">Note</span><span class="sxs-lookup"><span data-stu-id="89975-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="89975-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="89975-136">Example</span></span>  
 <span data-ttu-id="89975-137">Nell'esempio seguente viene illustrato come specificare un FTP la memorizzazione nella cache dei criteri di `NoCacheNoStore`.</span><span class="sxs-lookup"><span data-stu-id="89975-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="89975-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89975-138">See Also</span></span>  
 <xref:System.Net.Cache>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.Cache.RequestCacheLevel>  
 [<span data-ttu-id="89975-139">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="89975-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
