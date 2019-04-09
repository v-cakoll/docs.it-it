---
title: <requestCaching> (Impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
ms.openlocfilehash: af290e4b9258a08425a15e297ff538502edea916
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164853"
---
# <a name="requestcaching-element-network-settings"></a><span data-ttu-id="f8282-102">\<requestCaching > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="f8282-102">\<requestCaching> Element (Network Settings)</span></span>
<span data-ttu-id="f8282-103">Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="f8282-103">Controls the caching mechanism for network requests.</span></span>  
  
 <span data-ttu-id="f8282-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f8282-104">\<configuration></span></span>  
<span data-ttu-id="f8282-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="f8282-105">\<system.net></span></span>  
<span data-ttu-id="f8282-106">\<requestCaching></span><span class="sxs-lookup"><span data-stu-id="f8282-106">\<requestCaching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8282-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8282-107">Syntax</span></span>  
  
```xml  
<requestCaching  
  isPrivateCache ="true|false"  
  disableAllCaching="true|false"  
  defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
  unspecifiedMaximumAge= "d.hh.mm.ss">  
    <defaultHttpCachePolicy>...</defaultHttpCachePolicy>  
    <defaultFtpCachePolicy>...</defaultFtpCachePolicy>  
</requestCaching>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8282-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f8282-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f8282-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f8282-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8282-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="f8282-110">Attributes</span></span>  
  
|<span data-ttu-id="f8282-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="f8282-111">Attribute</span></span>|<span data-ttu-id="f8282-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8282-112">Description</span></span>|  
|---------------|-----------------|  
|`isPrivateCache`|<span data-ttu-id="f8282-113">Specifica se la cache fornisce l'isolamento tra le informazioni di utenti diversi.</span><span class="sxs-lookup"><span data-stu-id="f8282-113">Specifies whether the cache provides isolation between the information of different users.</span></span> <span data-ttu-id="f8282-114">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="f8282-114">The default value is `true`.</span></span> <span data-ttu-id="f8282-115">Questo valore deve essere `false` per le applicazioni di livello intermedio.</span><span class="sxs-lookup"><span data-stu-id="f8282-115">This value should be `false` for middle tier applications.</span></span>|  
|`disableAllCaching`|<span data-ttu-id="f8282-116">Specifica che la memorizzazione nella cache è disabilitata per tutte le risposte Web e non può essere sottoposto a override a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="f8282-116">Specifies that caching is disabled for all Web responses, and cannot be overridden programmatically.</span></span>|  
|`defaultPolicyLevel`|<span data-ttu-id="f8282-117">Uno dei valori dell'enumerazione <xref:System.Net.Cache.RequestCacheLevel>.</span><span class="sxs-lookup"><span data-stu-id="f8282-117">One of the values in the <xref:System.Net.Cache.RequestCacheLevel> enumeration.</span></span> <span data-ttu-id="f8282-118">Il valore predefinito è `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="f8282-118">The default value is `BypassCache`.</span></span>|  
|`unspecifiedMaximumAge`|<span data-ttu-id="f8282-119">Specifica il tempo predefinito dopo il quale contenuto viene contrassegnato come scaduto.</span><span class="sxs-lookup"><span data-stu-id="f8282-119">Specifies the default time after which content is marked as expired.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="f8282-120">Attributo policyLevel</span><span class="sxs-lookup"><span data-stu-id="f8282-120">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="f8282-121">Value</span><span class="sxs-lookup"><span data-stu-id="f8282-121">Value</span></span>|<span data-ttu-id="f8282-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8282-122">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="f8282-123">Restituisce la risorsa memorizzata nella cache se la risorsa è aggiornata, la lunghezza del contenuto è precisa e la scadenza, modifica e gli attributi di lunghezza del contenuto sono presenti.</span><span class="sxs-lookup"><span data-stu-id="f8282-123">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="f8282-124">Restituisce la risorsa dal server.</span><span class="sxs-lookup"><span data-stu-id="f8282-124">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="f8282-125">Restituisce la risorsa memorizzata nella cache se la lunghezza del contenuto è presente e corrisponde alla dimensione dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="f8282-125">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="f8282-126">Restituisce la risorsa memorizzata nella cache se la lunghezza del contenuto viene fornita e corrisponde alla dimensione dell'elemento; in caso contrario, la risorsa viene scaricata dal server e viene restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="f8282-126">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="f8282-127">Restituisce la risorsa memorizzata nella cache se il timestamp della risorsa memorizzata nella cache è identico a quello della risorsa del server. in caso contrario, la risorsa viene scaricata dal server, memorizzato nella cache e viene restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="f8282-127">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and is returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="f8282-128">Scarica la risorsa dal server, viene memorizzato nella cache e la risorsa viene restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="f8282-128">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="f8282-129">Se esiste una risorsa memorizzata nella cache, viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="f8282-129">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="f8282-130">La risorsa viene scaricata dal server e viene restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="f8282-130">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="f8282-131">Soddisfa una richiesta mediante la copia memorizzata nella cache della risorsa se il timestamp è identico a quello della risorsa del server. in caso contrario, la risorsa viene scaricata dal server, presentato al chiamante e viene memorizzata nella cache,</span><span class="sxs-lookup"><span data-stu-id="f8282-131">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and is stored in the cache,</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f8282-132">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f8282-132">Child Elements</span></span>  
  
|<span data-ttu-id="f8282-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="f8282-133">Element</span></span>|<span data-ttu-id="f8282-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8282-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8282-135">defaultHttpCachePolicy</span><span class="sxs-lookup"><span data-stu-id="f8282-135">defaultHttpCachePolicy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaulthttpcachepolicy-element-network-settings.md)|<span data-ttu-id="f8282-136">Elemento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f8282-136">Optional element.</span></span><br /><br /> <span data-ttu-id="f8282-137">Indica se la memorizzazione nella cache HTTP è attivo e ne descrive l'impostazione predefinita dei criteri di memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="f8282-137">Describes whether HTTP caching is active and describes the default caching policy.</span></span>|  
|[<span data-ttu-id="f8282-138">\<defaultFtpCachePolicy > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="f8282-138">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultftpcachepolicy-element-network-settings.md)|<span data-ttu-id="f8282-139">Elemento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f8282-139">Optional element.</span></span><br /><br /> <span data-ttu-id="f8282-140">Indica se la memorizzazione nella cache FTP è attivo e ne descrive l'impostazione predefinita dei criteri di memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="f8282-140">Describes whether FTP caching is active and describes the default caching policy.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f8282-141">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f8282-141">Parent Elements</span></span>  
  
|<span data-ttu-id="f8282-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="f8282-142">Element</span></span>|<span data-ttu-id="f8282-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8282-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8282-144">system.net</span><span class="sxs-lookup"><span data-stu-id="f8282-144">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="f8282-145">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f8282-145">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f8282-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8282-146">Example</span></span>  
 <span data-ttu-id="f8282-147">Nell'esempio seguente viene illustrato come disattivare la cache.</span><span class="sxs-lookup"><span data-stu-id="f8282-147">The following example shows how to disable all caching.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8282-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8282-148">See also</span></span>

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [<span data-ttu-id="f8282-149">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="f8282-149">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
