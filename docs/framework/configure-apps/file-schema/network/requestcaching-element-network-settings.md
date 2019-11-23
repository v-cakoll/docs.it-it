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
ms.openlocfilehash: f0979d2e0caeb0b22b90572aef0ad53235020f1d
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697832"
---
# <a name="requestcaching-element-network-settings"></a><span data-ttu-id="d1340-102">Elemento \<requestCaching> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="d1340-102">\<requestCaching> Element (Network Settings)</span></span>
<span data-ttu-id="d1340-103">Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="d1340-103">Controls the caching mechanism for network requests.</span></span>  
  
[<span data-ttu-id="d1340-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="d1340-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="d1340-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d1340-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="d1340-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<requestCaching >**</span><span class="sxs-lookup"><span data-stu-id="d1340-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<requestCaching>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1340-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d1340-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1340-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d1340-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d1340-109">Le sezioni seguenti descrivono gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d1340-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1340-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="d1340-110">Attributes</span></span>  
  
|<span data-ttu-id="d1340-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="d1340-111">Attribute</span></span>|<span data-ttu-id="d1340-112">description</span><span class="sxs-lookup"><span data-stu-id="d1340-112">Description</span></span>|  
|---------------|-----------------|  
|`isPrivateCache`|<span data-ttu-id="d1340-113">Specifica se la cache fornisce l'isolamento tra le informazioni di utenti diversi.</span><span class="sxs-lookup"><span data-stu-id="d1340-113">Specifies whether the cache provides isolation between the information of different users.</span></span> <span data-ttu-id="d1340-114">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="d1340-114">The default value is `true`.</span></span> <span data-ttu-id="d1340-115">Questo valore deve essere `false` per le applicazioni di livello intermedio.</span><span class="sxs-lookup"><span data-stu-id="d1340-115">This value should be `false` for middle tier applications.</span></span>|  
|`disableAllCaching`|<span data-ttu-id="d1340-116">Specifica che la memorizzazione nella cache è disabilitata per tutte le risposte Web e non può essere sottoposta a override a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="d1340-116">Specifies that caching is disabled for all Web responses, and cannot be overridden programmatically.</span></span>|  
|`defaultPolicyLevel`|<span data-ttu-id="d1340-117">Uno dei valori dell'enumerazione <xref:System.Net.Cache.RequestCacheLevel>.</span><span class="sxs-lookup"><span data-stu-id="d1340-117">One of the values in the <xref:System.Net.Cache.RequestCacheLevel> enumeration.</span></span> <span data-ttu-id="d1340-118">Il valore predefinito è `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="d1340-118">The default value is `BypassCache`.</span></span>|  
|`unspecifiedMaximumAge`|<span data-ttu-id="d1340-119">Specifica l'ora predefinita dopo la quale il contenuto è contrassegnato come scaduto.</span><span class="sxs-lookup"><span data-stu-id="d1340-119">Specifies the default time after which content is marked as expired.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="d1340-120">policyLevel (attributo)</span><span class="sxs-lookup"><span data-stu-id="d1340-120">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="d1340-121">Valore</span><span class="sxs-lookup"><span data-stu-id="d1340-121">Value</span></span>|<span data-ttu-id="d1340-122">description</span><span class="sxs-lookup"><span data-stu-id="d1340-122">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="d1340-123">Restituisce la risorsa memorizzata nella cache se la risorsa è aggiornata, la lunghezza del contenuto è precisa e sono presenti gli attributi relativi alla scadenza, alla modifica e alla lunghezza del contenuto.</span><span class="sxs-lookup"><span data-stu-id="d1340-123">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="d1340-124">Restituisce la risorsa dal server.</span><span class="sxs-lookup"><span data-stu-id="d1340-124">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="d1340-125">Restituisce la risorsa memorizzata nella cache se la lunghezza del contenuto è presente e corrisponde alla dimensione della voce.</span><span class="sxs-lookup"><span data-stu-id="d1340-125">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="d1340-126">Restituisce la risorsa memorizzata nella cache se viene fornita la lunghezza del contenuto e corrisponde alla dimensione della voce. in caso contrario, la risorsa viene scaricata dal server e viene restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="d1340-126">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="d1340-127">Restituisce la risorsa memorizzata nella cache se il timestamp della risorsa memorizzata nella cache corrisponde al timestamp della risorsa nel server. in caso contrario, la risorsa viene scaricata dal server, archiviata nella cache e viene restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="d1340-127">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and is returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="d1340-128">Scarica la risorsa dal server, la archivia nella cache e restituisce la risorsa al chiamante.</span><span class="sxs-lookup"><span data-stu-id="d1340-128">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="d1340-129">Se una risorsa memorizzata nella cache esiste, viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="d1340-129">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="d1340-130">La risorsa viene scaricata dal server e viene restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="d1340-130">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="d1340-131">Soddisfa una richiesta utilizzando la copia memorizzata nella cache della risorsa se il timestamp corrisponde al timestamp della risorsa nel server. in caso contrario, la risorsa viene scaricata dal server, presentata al chiamante e memorizzata nella cache.</span><span class="sxs-lookup"><span data-stu-id="d1340-131">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and is stored in the cache,</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1340-132">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d1340-132">Child Elements</span></span>  
  
|<span data-ttu-id="d1340-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="d1340-133">Element</span></span>|<span data-ttu-id="d1340-134">description</span><span class="sxs-lookup"><span data-stu-id="d1340-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1340-135">defaultHttpCachePolicy</span><span class="sxs-lookup"><span data-stu-id="d1340-135">defaultHttpCachePolicy</span></span>](defaulthttpcachepolicy-element-network-settings.md)|<span data-ttu-id="d1340-136">Elemento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d1340-136">Optional element.</span></span><br /><br /> <span data-ttu-id="d1340-137">Descrive se la memorizzazione nella cache HTTP è attiva e descrive i criteri di memorizzazione nella cache predefiniti.</span><span class="sxs-lookup"><span data-stu-id="d1340-137">Describes whether HTTP caching is active and describes the default caching policy.</span></span>|  
|[<span data-ttu-id="d1340-138">\<elemento > defaultFtpCachePolicy (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="d1340-138">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>](defaultftpcachepolicy-element-network-settings.md)|<span data-ttu-id="d1340-139">Elemento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d1340-139">Optional element.</span></span><br /><br /> <span data-ttu-id="d1340-140">Descrive se la memorizzazione nella cache FTP è attiva e descrive i criteri di memorizzazione nella cache predefiniti.</span><span class="sxs-lookup"><span data-stu-id="d1340-140">Describes whether FTP caching is active and describes the default caching policy.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d1340-141">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d1340-141">Parent Elements</span></span>  
  
|<span data-ttu-id="d1340-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="d1340-142">Element</span></span>|<span data-ttu-id="d1340-143">description</span><span class="sxs-lookup"><span data-stu-id="d1340-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1340-144">system.net</span><span class="sxs-lookup"><span data-stu-id="d1340-144">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="d1340-145">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d1340-145">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d1340-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="d1340-146">Example</span></span>  
 <span data-ttu-id="d1340-147">Nell'esempio seguente viene illustrato come disabilitare tutti i Caching.</span><span class="sxs-lookup"><span data-stu-id="d1340-147">The following example shows how to disable all caching.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d1340-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1340-148">See also</span></span>

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [<span data-ttu-id="d1340-149">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="d1340-149">Network Settings Schema</span></span>](index.md)
