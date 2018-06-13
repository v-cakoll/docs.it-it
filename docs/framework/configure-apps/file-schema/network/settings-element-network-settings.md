---
title: '&lt;impostazioni&gt; elemento (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3f717705a6cd4cc29fe333f5012c7fec466d350b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752478"
---
# <a name="ltsettingsgt-element-network-settings"></a><span data-ttu-id="3e258-102">&lt;impostazioni&gt; elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="3e258-102">&lt;settings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="3e258-103">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3e258-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="3e258-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3e258-104">\<configuration></span></span>  
<span data-ttu-id="3e258-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="3e258-105">\<system.net></span></span>  
<span data-ttu-id="3e258-106">\<Impostazioni ></span><span class="sxs-lookup"><span data-stu-id="3e258-106">\<settings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e258-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e258-107">Syntax</span></span>  
  
```xml  
<settings>  
  <httpListener> … </httpListener>  
  <httpWebRequest> … </httpWebRequest>  
  <ipv6> … </ipv6>  
  <performanceCounters> … </performanceCounters>  
  <servicePointManager> … </servicePointManager>  
  <socket> … </socket>  
  <webProxyScript> … </webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e258-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3e258-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3e258-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3e258-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e258-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="3e258-110">Attributes</span></span>  
 <span data-ttu-id="3e258-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3e258-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3e258-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3e258-112">Child Elements</span></span>  
  
|<span data-ttu-id="3e258-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="3e258-113">Element</span></span>|<span data-ttu-id="3e258-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e258-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3e258-115">HttpListener</span><span class="sxs-lookup"><span data-stu-id="3e258-115">httpListener</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|<span data-ttu-id="3e258-116">Consente di personalizzare i parametri utilizzati per la <xref:System.Net.HttpListener> classe.</span><span class="sxs-lookup"><span data-stu-id="3e258-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="3e258-117">HttpWebRequest</span><span class="sxs-lookup"><span data-stu-id="3e258-117">httpWebRequest</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|<span data-ttu-id="3e258-118">Consente di personalizzare i parametri della richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="3e258-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="3e258-119">IPv6</span><span class="sxs-lookup"><span data-stu-id="3e258-119">ipv6</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|<span data-ttu-id="3e258-120">Protocollo Internet versione 6 (IPv6) consente il supporto.</span><span class="sxs-lookup"><span data-stu-id="3e258-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="3e258-121">\<performanceCounter > elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="3e258-121">\<performanceCounter> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|<span data-ttu-id="3e258-122">Abilita i contatori delle prestazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="3e258-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="3e258-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="3e258-123">servicePointManager</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|<span data-ttu-id="3e258-124">Configura le connessioni alle risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="3e258-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="3e258-125">Socket</span><span class="sxs-lookup"><span data-stu-id="3e258-125">socket</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|<span data-ttu-id="3e258-126">Specifica se le operazioni socket utilizzano le porte di completamento.</span><span class="sxs-lookup"><span data-stu-id="3e258-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="3e258-127">\<webProxyScript > elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="3e258-127">\<webProxyScript> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|<span data-ttu-id="3e258-128">Consente di configurare le caratteristiche dello script utilizzato per individuare il proxy Web.</span><span class="sxs-lookup"><span data-stu-id="3e258-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3e258-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3e258-129">Parent Elements</span></span>  
  
|<span data-ttu-id="3e258-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="3e258-130">Element</span></span>|<span data-ttu-id="3e258-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e258-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3e258-132">System.NET</span><span class="sxs-lookup"><span data-stu-id="3e258-132">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="3e258-133">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3e258-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e258-134">Note</span><span class="sxs-lookup"><span data-stu-id="3e258-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3e258-135">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="3e258-135">Configuration Files</span></span>  
 <span data-ttu-id="3e258-136">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="3e258-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e258-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e258-137">See Also</span></span>  
 <xref:System.Net?displayProperty=nameWithType>  
 [<span data-ttu-id="3e258-138">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="3e258-138">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
