---
title: Elemento <defaultHttpCachePolicy> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
ms.openlocfilehash: c5029a7d1e53c28d0abb232efdc3e0bd2c9658d4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088413"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a><span data-ttu-id="7818c-102">Elemento \<defaultHttpCachePolicy> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="7818c-102">\<defaultHttpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="7818c-103">Descrive se la memorizzazione nella cache HTTP è attiva e descrive i criteri di memorizzazione nella cache predefiniti.</span><span class="sxs-lookup"><span data-stu-id="7818c-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultHttpCachePolicy>**

## <a name="syntax"></a><span data-ttu-id="7818c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7818c-104">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7818c-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7818c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7818c-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7818c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7818c-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="7818c-107">Attributes</span></span>  
  
|<span data-ttu-id="7818c-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="7818c-108">Attribute</span></span>|<span data-ttu-id="7818c-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7818c-109">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="7818c-110">Specifica l'intervallo di tempo massimo prima che un oggetto memorizzato nella cache venga contrassegnato come scaduto.</span><span class="sxs-lookup"><span data-stu-id="7818c-110">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="7818c-111">Specifica il tempo massimo trascorso il tempo di aggiornamento calcolato prima che un oggetto memorizzato nella cache venga contrassegnato come scaduto.</span><span class="sxs-lookup"><span data-stu-id="7818c-111">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="7818c-112">Specifica il tempo minimo per considerare aggiornato un oggetto memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="7818c-112">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="7818c-113">Specifica se i criteri di memorizzazione nella cache sono automatici o se la cache è stata ignorata.</span><span class="sxs-lookup"><span data-stu-id="7818c-113">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="7818c-114">Il valore predefinito è `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="7818c-114">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7818c-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7818c-115">Child Elements</span></span>  
 <span data-ttu-id="7818c-116">nessuno</span><span class="sxs-lookup"><span data-stu-id="7818c-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7818c-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7818c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="7818c-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="7818c-118">Element</span></span>|<span data-ttu-id="7818c-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7818c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7818c-120">requestCaching</span><span class="sxs-lookup"><span data-stu-id="7818c-120">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="7818c-121">Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="7818c-121">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7818c-122">Commenti</span><span class="sxs-lookup"><span data-stu-id="7818c-122">Remarks</span></span>  
 <span data-ttu-id="7818c-123">Il valore dell' `policyLevel` attributo è `BypassCache` o `Default` .</span><span class="sxs-lookup"><span data-stu-id="7818c-123">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="7818c-124">I valori per `maximumAge` gli `maximumStale` elementi, e `minimumFresh` sono un intervallo di tempo esplicito con un formato *d*.\* HH*:*mm*:*SS\* (giorni, ore, minuti e secondi) o costanti `minValue` o `maxValue` , a seconda dei casi.</span><span class="sxs-lookup"><span data-stu-id="7818c-124">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="7818c-125">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="7818c-125">Configuration Files</span></span>  
 <span data-ttu-id="7818c-126">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="7818c-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7818c-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="7818c-127">Example</span></span>  
 <span data-ttu-id="7818c-128">Nell'esempio seguente viene illustrato come specificare un periodo di tempo minimo di sei ore, una durata massima di due giorni e un tempo di esecuzione massimo di quattro ore.</span><span class="sxs-lookup"><span data-stu-id="7818c-128">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy  
        minimumFresh="0.06:00:00"  
        maximumAge="2.00:00:00"  
        maximumStale="0.04:00:00"
      />  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7818c-129">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="7818c-129">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="7818c-130">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="7818c-130">Network Settings Schema</span></span>](index.md)
