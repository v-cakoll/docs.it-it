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
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088413"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a><span data-ttu-id="9c797-102">\<elemento > defaultHttpCachePolicy (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="9c797-102">\<defaultHttpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="9c797-103">Descrive se la memorizzazione nella cache HTTP è attiva e descrive i criteri di memorizzazione nella cache predefiniti.</span><span class="sxs-lookup"><span data-stu-id="9c797-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  

<span data-ttu-id="9c797-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9c797-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9c797-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9c797-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="9c797-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<RequestCaching**](requestcaching-element-network-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="9c797-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)</span></span>\
<span data-ttu-id="9c797-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<DefaultHttpCachePolicy** ></span><span class="sxs-lookup"><span data-stu-id="9c797-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultHttpCachePolicy>**</span></span>

## <a name="syntax"></a><span data-ttu-id="9c797-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c797-108">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c797-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9c797-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9c797-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9c797-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c797-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="9c797-111">Attributes</span></span>  
  
|<span data-ttu-id="9c797-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="9c797-112">Attribute</span></span>|<span data-ttu-id="9c797-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c797-113">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="9c797-114">Specifica l'intervallo di tempo massimo prima che un oggetto memorizzato nella cache venga contrassegnato come scaduto.</span><span class="sxs-lookup"><span data-stu-id="9c797-114">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="9c797-115">Specifica il tempo massimo trascorso il tempo di aggiornamento calcolato prima che un oggetto memorizzato nella cache venga contrassegnato come scaduto.</span><span class="sxs-lookup"><span data-stu-id="9c797-115">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="9c797-116">Specifica il tempo minimo per considerare aggiornato un oggetto memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="9c797-116">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="9c797-117">Specifica se i criteri di memorizzazione nella cache sono automatici o se la cache è stata ignorata.</span><span class="sxs-lookup"><span data-stu-id="9c797-117">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="9c797-118">Il valore predefinito è `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="9c797-118">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9c797-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9c797-119">Child Elements</span></span>  
 <span data-ttu-id="9c797-120">Nessuno</span><span class="sxs-lookup"><span data-stu-id="9c797-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9c797-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9c797-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9c797-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c797-122">Element</span></span>|<span data-ttu-id="9c797-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c797-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c797-124">requestCaching</span><span class="sxs-lookup"><span data-stu-id="9c797-124">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="9c797-125">Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="9c797-125">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c797-126">Note</span><span class="sxs-lookup"><span data-stu-id="9c797-126">Remarks</span></span>  
 <span data-ttu-id="9c797-127">Il valore per l'attributo `policyLevel` è `BypassCache` o `Default`.</span><span class="sxs-lookup"><span data-stu-id="9c797-127">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="9c797-128">I valori per gli elementi `maximumAge`, `maximumStale`e `minimumFresh` sono un intervallo di tempo esplicito con formato *d*. *HH*:*mm*:*SS* (giorni, ore, minuti e secondi) o costanti `minValue` o `maxValue`, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="9c797-128">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9c797-129">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="9c797-129">Configuration Files</span></span>  
 <span data-ttu-id="9c797-130">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="9c797-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c797-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="9c797-131">Example</span></span>  
 <span data-ttu-id="9c797-132">Nell'esempio seguente viene illustrato come specificare un periodo di tempo minimo di sei ore, una durata massima di due giorni e un tempo di esecuzione massimo di quattro ore.</span><span class="sxs-lookup"><span data-stu-id="9c797-132">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9c797-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c797-133">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="9c797-134">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="9c797-134">Network Settings Schema</span></span>](index.md)
