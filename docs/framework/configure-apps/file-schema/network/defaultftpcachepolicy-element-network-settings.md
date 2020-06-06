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
ms.openlocfilehash: 9261a430642cb4d5ac4507835bd0fd3561bd8c02
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088434"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="24dff-102">Elemento \<defaultFtpCachePolicy> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="24dff-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="24dff-103">Descrive se la memorizzazione nella cache FTP è attiva e descrive i criteri di memorizzazione nella cache predefiniti.</span><span class="sxs-lookup"><span data-stu-id="24dff-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultFtpCachePolicy>**

## <a name="syntax"></a><span data-ttu-id="24dff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="24dff-104">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24dff-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="24dff-105">Attributes and Elements</span></span>  
 <span data-ttu-id="24dff-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="24dff-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24dff-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="24dff-107">Attributes</span></span>  
  
|<span data-ttu-id="24dff-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="24dff-108">Attribute</span></span>|<span data-ttu-id="24dff-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24dff-109">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="24dff-110">Specifica i criteri di memorizzazione nella cache FTP.</span><span class="sxs-lookup"><span data-stu-id="24dff-110">Specifies the FTP caching policy.</span></span> <span data-ttu-id="24dff-111">Il valore predefinito è `Default`.</span><span class="sxs-lookup"><span data-stu-id="24dff-111">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="24dff-112">policyLevel (attributo)</span><span class="sxs-lookup"><span data-stu-id="24dff-112">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="24dff-113">Valore</span><span class="sxs-lookup"><span data-stu-id="24dff-113">Value</span></span>|<span data-ttu-id="24dff-114">Description</span><span class="sxs-lookup"><span data-stu-id="24dff-114">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="24dff-115">Restituisce la risorsa memorizzata nella cache se la risorsa è aggiornata, la lunghezza del contenuto è precisa e sono presenti gli attributi relativi alla scadenza, alla modifica e alla lunghezza del contenuto.</span><span class="sxs-lookup"><span data-stu-id="24dff-115">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="24dff-116">Restituisce la risorsa dal server.</span><span class="sxs-lookup"><span data-stu-id="24dff-116">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="24dff-117">Restituisce la risorsa memorizzata nella cache se la lunghezza del contenuto è presente e corrisponde alla dimensione della voce.</span><span class="sxs-lookup"><span data-stu-id="24dff-117">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="24dff-118">Restituisce la risorsa memorizzata nella cache se viene fornita la lunghezza del contenuto e corrisponde alla dimensione della voce. in caso contrario, la risorsa viene scaricata dal server e viene restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="24dff-118">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="24dff-119">Restituisce la risorsa memorizzata nella cache se il timestamp della risorsa memorizzata nella cache corrisponde al timestamp della risorsa nel server. in caso contrario, la risorsa viene scaricata dal server, archiviata nella cache e restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="24dff-119">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="24dff-120">Scarica la risorsa dal server, la archivia nella cache e restituisce la risorsa al chiamante.</span><span class="sxs-lookup"><span data-stu-id="24dff-120">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="24dff-121">Se una risorsa memorizzata nella cache esiste, viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="24dff-121">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="24dff-122">La risorsa viene scaricata dal server e viene restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="24dff-122">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="24dff-123">Soddisfa una richiesta utilizzando la copia memorizzata nella cache della risorsa se il timestamp è identico a quello della risorsa sul server. In caso contrario, la risorsa viene scaricata dal server, presentata al chiamante e memorizzata nella cache.</span><span class="sxs-lookup"><span data-stu-id="24dff-123">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="24dff-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="24dff-124">Child Elements</span></span>  
 <span data-ttu-id="24dff-125">No.</span><span class="sxs-lookup"><span data-stu-id="24dff-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="24dff-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="24dff-126">Parent Elements</span></span>  
  
|<span data-ttu-id="24dff-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="24dff-127">Element</span></span>|<span data-ttu-id="24dff-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24dff-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24dff-129">requestCaching</span><span class="sxs-lookup"><span data-stu-id="24dff-129">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="24dff-130">Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="24dff-130">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24dff-131">Commenti</span><span class="sxs-lookup"><span data-stu-id="24dff-131">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="24dff-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="24dff-132">Example</span></span>  
 <span data-ttu-id="24dff-133">Nell'esempio seguente viene illustrato come specificare un criterio di memorizzazione nella cache FTP di `NoCacheNoStore` .</span><span class="sxs-lookup"><span data-stu-id="24dff-133">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="24dff-134">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="24dff-134">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="24dff-135">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="24dff-135">Network Settings Schema</span></span>](index.md)
