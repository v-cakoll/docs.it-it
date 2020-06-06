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
ms.openlocfilehash: afee69eb894518b1c88483e34a1d64d452019244
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74802123"
---
# <a name="requestcaching-element-network-settings"></a><span data-ttu-id="937a9-102">Elemento \<requestCaching> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="937a9-102">\<requestCaching> Element (Network Settings)</span></span>
<span data-ttu-id="937a9-103">Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="937a9-103">Controls the caching mechanism for network requests.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<requestCaching>**  
  
## <a name="syntax"></a><span data-ttu-id="937a9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="937a9-104">Syntax</span></span>  
  
```xml  
<requestCaching  
  isPrivateCache ="true|false"  
  disableAllCaching="true|false"  
  defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
  unspecifiedMaximumAge= "d.hh:mm:ss">  
    <defaultHttpCachePolicy>...</defaultHttpCachePolicy>  
    <defaultFtpCachePolicy>...</defaultFtpCachePolicy>  
</requestCaching>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="937a9-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="937a9-105">Attributes and Elements</span></span>  
 <span data-ttu-id="937a9-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="937a9-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="937a9-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="937a9-107">Attributes</span></span>  
  
|<span data-ttu-id="937a9-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="937a9-108">Attribute</span></span>|<span data-ttu-id="937a9-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="937a9-109">Description</span></span>|  
|---------------|-----------------|  
|`isPrivateCache`|<span data-ttu-id="937a9-110">Specifica se la cache fornisce l'isolamento tra le informazioni di utenti diversi.</span><span class="sxs-lookup"><span data-stu-id="937a9-110">Specifies whether the cache provides isolation between the information of different users.</span></span> <span data-ttu-id="937a9-111">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="937a9-111">The default value is `true`.</span></span> <span data-ttu-id="937a9-112">Questo valore deve essere `false` per le applicazioni di livello intermedio.</span><span class="sxs-lookup"><span data-stu-id="937a9-112">This value should be `false` for middle tier applications.</span></span>|  
|`disableAllCaching`|<span data-ttu-id="937a9-113">Specifica che la memorizzazione nella cache è disabilitata per tutte le risposte Web e non può essere sottoposta a override a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="937a9-113">Specifies that caching is disabled for all Web responses, and cannot be overridden programmatically.</span></span>|  
|`defaultPolicyLevel`|<span data-ttu-id="937a9-114">Uno dei valori dell'enumerazione <xref:System.Net.Cache.RequestCacheLevel>.</span><span class="sxs-lookup"><span data-stu-id="937a9-114">One of the values in the <xref:System.Net.Cache.RequestCacheLevel> enumeration.</span></span> <span data-ttu-id="937a9-115">Il valore predefinito è `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="937a9-115">The default value is `BypassCache`.</span></span>|  
|`unspecifiedMaximumAge`|<span data-ttu-id="937a9-116">Specifica l'ora predefinita dopo la quale il contenuto è contrassegnato come scaduto.</span><span class="sxs-lookup"><span data-stu-id="937a9-116">Specifies the default time after which content is marked as expired.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="937a9-117">policyLevel (attributo)</span><span class="sxs-lookup"><span data-stu-id="937a9-117">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="937a9-118">Valore</span><span class="sxs-lookup"><span data-stu-id="937a9-118">Value</span></span>|<span data-ttu-id="937a9-119">Description</span><span class="sxs-lookup"><span data-stu-id="937a9-119">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="937a9-120">Restituisce la risorsa memorizzata nella cache se la risorsa è aggiornata, la lunghezza del contenuto è precisa e sono presenti gli attributi relativi alla scadenza, alla modifica e alla lunghezza del contenuto.</span><span class="sxs-lookup"><span data-stu-id="937a9-120">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="937a9-121">Restituisce la risorsa dal server.</span><span class="sxs-lookup"><span data-stu-id="937a9-121">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="937a9-122">Restituisce la risorsa memorizzata nella cache se la lunghezza del contenuto è presente e corrisponde alla dimensione della voce.</span><span class="sxs-lookup"><span data-stu-id="937a9-122">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="937a9-123">Restituisce la risorsa memorizzata nella cache se viene fornita la lunghezza del contenuto e corrisponde alla dimensione della voce. in caso contrario, la risorsa viene scaricata dal server e viene restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="937a9-123">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="937a9-124">Restituisce la risorsa memorizzata nella cache se il timestamp della risorsa memorizzata nella cache corrisponde al timestamp della risorsa nel server. in caso contrario, la risorsa viene scaricata dal server, archiviata nella cache e viene restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="937a9-124">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and is returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="937a9-125">Scarica la risorsa dal server, la archivia nella cache e restituisce la risorsa al chiamante.</span><span class="sxs-lookup"><span data-stu-id="937a9-125">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="937a9-126">Se una risorsa memorizzata nella cache esiste, viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="937a9-126">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="937a9-127">La risorsa viene scaricata dal server e viene restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="937a9-127">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="937a9-128">Soddisfa una richiesta utilizzando la copia memorizzata nella cache della risorsa se il timestamp corrisponde al timestamp della risorsa nel server. in caso contrario, la risorsa viene scaricata dal server, presentata al chiamante e memorizzata nella cache.</span><span class="sxs-lookup"><span data-stu-id="937a9-128">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and is stored in the cache,</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="937a9-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="937a9-129">Child Elements</span></span>  
  
|<span data-ttu-id="937a9-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="937a9-130">Element</span></span>|<span data-ttu-id="937a9-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="937a9-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="937a9-132">defaultHttpCachePolicy</span><span class="sxs-lookup"><span data-stu-id="937a9-132">defaultHttpCachePolicy</span></span>](defaulthttpcachepolicy-element-network-settings.md)|<span data-ttu-id="937a9-133">Elemento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="937a9-133">Optional element.</span></span><br /><br /> <span data-ttu-id="937a9-134">Descrive se la memorizzazione nella cache HTTP è attiva e descrive i criteri di memorizzazione nella cache predefiniti.</span><span class="sxs-lookup"><span data-stu-id="937a9-134">Describes whether HTTP caching is active and describes the default caching policy.</span></span>|  
|[<span data-ttu-id="937a9-135">\<defaultFtpCachePolicy>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="937a9-135">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>](defaultftpcachepolicy-element-network-settings.md)|<span data-ttu-id="937a9-136">Elemento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="937a9-136">Optional element.</span></span><br /><br /> <span data-ttu-id="937a9-137">Descrive se la memorizzazione nella cache FTP è attiva e descrive i criteri di memorizzazione nella cache predefiniti.</span><span class="sxs-lookup"><span data-stu-id="937a9-137">Describes whether FTP caching is active and describes the default caching policy.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="937a9-138">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="937a9-138">Parent Elements</span></span>  
  
|<span data-ttu-id="937a9-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="937a9-139">Element</span></span>|<span data-ttu-id="937a9-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="937a9-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="937a9-141">system.net</span><span class="sxs-lookup"><span data-stu-id="937a9-141">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="937a9-142">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="937a9-142">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="937a9-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="937a9-143">Example</span></span>  
 <span data-ttu-id="937a9-144">Nell'esempio seguente viene illustrato come disabilitare tutti i Caching.</span><span class="sxs-lookup"><span data-stu-id="937a9-144">The following example shows how to disable all caching.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="937a9-145">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="937a9-145">See also</span></span>

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [<span data-ttu-id="937a9-146">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="937a9-146">Network Settings Schema</span></span>](index.md)
