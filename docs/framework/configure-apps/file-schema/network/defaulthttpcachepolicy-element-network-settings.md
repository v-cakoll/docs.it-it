---
title: '&lt;defaultHttpCachePolicy&gt; elemento (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 0425711687a2f8b40f2c645e1c478d52b56ad979
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32741841"
---
# <a name="ltdefaulthttpcachepolicygt-element-network-settings"></a><span data-ttu-id="8a68d-102">&lt;defaultHttpCachePolicy&gt; elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="8a68d-102">&lt;defaultHttpCachePolicy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="8a68d-103">Indica se la memorizzazione nella cache HTTP è attivo e viene descritto il valore predefinito di criteri di memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="8a68d-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="8a68d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8a68d-104">\<configuration></span></span>  
<span data-ttu-id="8a68d-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="8a68d-105">\<system.net></span></span>  
<span data-ttu-id="8a68d-106">\<requestCaching ></span><span class="sxs-lookup"><span data-stu-id="8a68d-106">\<requestCaching></span></span>  
<span data-ttu-id="8a68d-107">\<defaultHttpCachePolicy ></span><span class="sxs-lookup"><span data-stu-id="8a68d-107">\<defaultHttpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a68d-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a68d-108">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a68d-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8a68d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8a68d-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8a68d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a68d-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="8a68d-111">Attributes</span></span>  
  
|<span data-ttu-id="8a68d-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="8a68d-112">Attribute</span></span>|<span data-ttu-id="8a68d-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a68d-113">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="8a68d-114">Specifica l'intervallo di tempo massimo prima che un oggetto memorizzato nella cache viene contrassegnato come scaduto.</span><span class="sxs-lookup"><span data-stu-id="8a68d-114">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="8a68d-115">Specifica il tempo massimo oltre il tempo di validità calcolato prima che un oggetto memorizzato nella cache viene contrassegnato come scaduto.</span><span class="sxs-lookup"><span data-stu-id="8a68d-115">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="8a68d-116">Specifica il tempo minimo per un oggetto memorizzato nella cache essere considerato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="8a68d-116">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="8a68d-117">Specifica se i criteri di memorizzazione nella cache sono automatico o se la cache viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="8a68d-117">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="8a68d-118">Il valore predefinito è `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="8a68d-118">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a68d-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8a68d-119">Child Elements</span></span>  
 <span data-ttu-id="8a68d-120">Nessuno</span><span class="sxs-lookup"><span data-stu-id="8a68d-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8a68d-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8a68d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8a68d-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="8a68d-122">Element</span></span>|<span data-ttu-id="8a68d-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a68d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a68d-124">requestCaching</span><span class="sxs-lookup"><span data-stu-id="8a68d-124">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="8a68d-125">Controlla il meccanismo di memorizzazione nella cache delle richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="8a68d-125">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a68d-126">Note</span><span class="sxs-lookup"><span data-stu-id="8a68d-126">Remarks</span></span>  
 <span data-ttu-id="8a68d-127">Il valore per il `policyLevel` attributo sia `BypassCache` o `Default`.</span><span class="sxs-lookup"><span data-stu-id="8a68d-127">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="8a68d-128">I valori per il `maximumAge`, `maximumStale`, e `minimumFresh` gli elementi sono di un intervallo di tempo esplicito con un formato di *d*. *hh*:*mm*:*ss* (giorni, ore, minuti e secondi), le costanti o `minValue` o `maxValue`, a seconda dei casi.</span><span class="sxs-lookup"><span data-stu-id="8a68d-128">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8a68d-129">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="8a68d-129">Configuration Files</span></span>  
 <span data-ttu-id="8a68d-130">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="8a68d-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a68d-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a68d-131">Example</span></span>  
 <span data-ttu-id="8a68d-132">Nell'esempio seguente viene illustrato come specificare un'ora aggiornata minima di sei ore, un intervallo di durata massima di due giorni e un intervallo di obsolescenza massima pari a quattro ore.</span><span class="sxs-lookup"><span data-stu-id="8a68d-132">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8a68d-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a68d-133">See Also</span></span>  
 <xref:System.Net.Cache>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.Cache.RequestCacheLevel>  
 [<span data-ttu-id="8a68d-134">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="8a68d-134">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
