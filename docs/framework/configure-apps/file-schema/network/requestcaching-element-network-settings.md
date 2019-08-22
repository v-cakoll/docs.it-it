---
title: Elemento <requestCaching> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
ms.openlocfilehash: 2a3d0b182acad2351ed095934ca97c6194d344fc
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659129"
---
# <a name="requestcaching-element-network-settings"></a><span data-ttu-id="d6c60-102">Elemento \<requestCaching> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="d6c60-102">\<requestCaching> Element (Network Settings)</span></span>
<span data-ttu-id="d6c60-103">Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="d6c60-103">Controls the caching mechanism for network requests.</span></span>  
  
 <span data-ttu-id="d6c60-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d6c60-104">\<configuration></span></span>  
<span data-ttu-id="d6c60-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="d6c60-105">\<system.net></span></span>  
<span data-ttu-id="d6c60-106">\<requestCaching></span><span class="sxs-lookup"><span data-stu-id="d6c60-106">\<requestCaching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6c60-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6c60-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6c60-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d6c60-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d6c60-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d6c60-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6c60-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="d6c60-110">Attributes</span></span>  
  
|<span data-ttu-id="d6c60-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="d6c60-111">Attribute</span></span>|<span data-ttu-id="d6c60-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d6c60-112">Description</span></span>|  
|---------------|-----------------|  
|`isPrivateCache`|<span data-ttu-id="d6c60-113">Specifica se la cache fornisce l'isolamento tra le informazioni di utenti diversi.</span><span class="sxs-lookup"><span data-stu-id="d6c60-113">Specifies whether the cache provides isolation between the information of different users.</span></span> <span data-ttu-id="d6c60-114">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="d6c60-114">The default value is `true`.</span></span> <span data-ttu-id="d6c60-115">Questo valore deve essere `false` per le applicazioni di livello intermedio.</span><span class="sxs-lookup"><span data-stu-id="d6c60-115">This value should be `false` for middle tier applications.</span></span>|  
|`disableAllCaching`|<span data-ttu-id="d6c60-116">Specifica che la memorizzazione nella cache è disabilitata per tutte le risposte Web e non può essere sottoposta a override a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="d6c60-116">Specifies that caching is disabled for all Web responses, and cannot be overridden programmatically.</span></span>|  
|`defaultPolicyLevel`|<span data-ttu-id="d6c60-117">Uno dei valori dell'enumerazione <xref:System.Net.Cache.RequestCacheLevel>.</span><span class="sxs-lookup"><span data-stu-id="d6c60-117">One of the values in the <xref:System.Net.Cache.RequestCacheLevel> enumeration.</span></span> <span data-ttu-id="d6c60-118">Il valore predefinito è `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="d6c60-118">The default value is `BypassCache`.</span></span>|  
|`unspecifiedMaximumAge`|<span data-ttu-id="d6c60-119">Specifica l'ora predefinita dopo la quale il contenuto è contrassegnato come scaduto.</span><span class="sxs-lookup"><span data-stu-id="d6c60-119">Specifies the default time after which content is marked as expired.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="d6c60-120">policyLevel (attributo)</span><span class="sxs-lookup"><span data-stu-id="d6c60-120">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="d6c60-121">Value</span><span class="sxs-lookup"><span data-stu-id="d6c60-121">Value</span></span>|<span data-ttu-id="d6c60-122">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d6c60-122">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="d6c60-123">Restituisce la risorsa memorizzata nella cache se la risorsa è aggiornata, la lunghezza del contenuto è precisa e sono presenti gli attributi relativi alla scadenza, alla modifica e alla lunghezza del contenuto.</span><span class="sxs-lookup"><span data-stu-id="d6c60-123">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="d6c60-124">Restituisce la risorsa dal server.</span><span class="sxs-lookup"><span data-stu-id="d6c60-124">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="d6c60-125">Restituisce la risorsa memorizzata nella cache se la lunghezza del contenuto è presente e corrisponde alla dimensione della voce.</span><span class="sxs-lookup"><span data-stu-id="d6c60-125">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="d6c60-126">Restituisce la risorsa memorizzata nella cache se viene fornita la lunghezza del contenuto e corrisponde alla dimensione della voce. in caso contrario, la risorsa viene scaricata dal server e viene restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="d6c60-126">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="d6c60-127">Restituisce la risorsa memorizzata nella cache se il timestamp della risorsa memorizzata nella cache corrisponde al timestamp della risorsa nel server. in caso contrario, la risorsa viene scaricata dal server, archiviata nella cache e viene restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="d6c60-127">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and is returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="d6c60-128">Scarica la risorsa dal server, la archivia nella cache e restituisce la risorsa al chiamante.</span><span class="sxs-lookup"><span data-stu-id="d6c60-128">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="d6c60-129">Se una risorsa memorizzata nella cache esiste, viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="d6c60-129">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="d6c60-130">La risorsa viene scaricata dal server e viene restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="d6c60-130">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="d6c60-131">Soddisfa una richiesta utilizzando la copia memorizzata nella cache della risorsa se il timestamp corrisponde al timestamp della risorsa nel server. in caso contrario, la risorsa viene scaricata dal server, presentata al chiamante e memorizzata nella cache.</span><span class="sxs-lookup"><span data-stu-id="d6c60-131">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and is stored in the cache,</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6c60-132">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d6c60-132">Child Elements</span></span>  
  
|<span data-ttu-id="d6c60-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="d6c60-133">Element</span></span>|<span data-ttu-id="d6c60-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6c60-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6c60-135">defaultHttpCachePolicy</span><span class="sxs-lookup"><span data-stu-id="d6c60-135">defaultHttpCachePolicy</span></span>](defaulthttpcachepolicy-element-network-settings.md)|<span data-ttu-id="d6c60-136">Elemento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d6c60-136">Optional element.</span></span><br /><br /> <span data-ttu-id="d6c60-137">Descrive se la memorizzazione nella cache HTTP è attiva e descrive i criteri di memorizzazione nella cache predefiniti.</span><span class="sxs-lookup"><span data-stu-id="d6c60-137">Describes whether HTTP caching is active and describes the default caching policy.</span></span>|  
|[<span data-ttu-id="d6c60-138">\<Elemento > defaultFtpCachePolicy (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="d6c60-138">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>](defaultftpcachepolicy-element-network-settings.md)|<span data-ttu-id="d6c60-139">Elemento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d6c60-139">Optional element.</span></span><br /><br /> <span data-ttu-id="d6c60-140">Descrive se la memorizzazione nella cache FTP è attiva e descrive i criteri di memorizzazione nella cache predefiniti.</span><span class="sxs-lookup"><span data-stu-id="d6c60-140">Describes whether FTP caching is active and describes the default caching policy.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d6c60-141">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d6c60-141">Parent Elements</span></span>  
  
|<span data-ttu-id="d6c60-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="d6c60-142">Element</span></span>|<span data-ttu-id="d6c60-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6c60-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6c60-144">system.net</span><span class="sxs-lookup"><span data-stu-id="d6c60-144">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="d6c60-145">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d6c60-145">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d6c60-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="d6c60-146">Example</span></span>  
 <span data-ttu-id="d6c60-147">Nell'esempio seguente viene illustrato come disabilitare tutti i Caching.</span><span class="sxs-lookup"><span data-stu-id="d6c60-147">The following example shows how to disable all caching.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6c60-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6c60-148">See also</span></span>

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [<span data-ttu-id="d6c60-149">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="d6c60-149">Network Settings Schema</span></span>](index.md)
