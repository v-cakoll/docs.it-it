---
title: '&lt;impostazioni&gt; (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
ms.openlocfilehash: 87a944eca6ea4158f15c9911c6b13fd4d3c0921d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151200"
---
# <a name="ltsettingsgt-element-network-settings"></a><span data-ttu-id="9a807-102">&lt;impostazioni&gt; (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="9a807-102">&lt;settings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="9a807-103">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9a807-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="9a807-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9a807-104">\<configuration></span></span>  
<span data-ttu-id="9a807-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="9a807-105">\<system.net></span></span>  
<span data-ttu-id="9a807-106">\<Impostazioni ></span><span class="sxs-lookup"><span data-stu-id="9a807-106">\<settings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a807-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a807-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a807-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9a807-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9a807-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9a807-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a807-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="9a807-110">Attributes</span></span>  
 <span data-ttu-id="9a807-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9a807-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9a807-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9a807-112">Child Elements</span></span>  
  
|<span data-ttu-id="9a807-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a807-113">Element</span></span>|<span data-ttu-id="9a807-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a807-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a807-115">httpListener</span><span class="sxs-lookup"><span data-stu-id="9a807-115">httpListener</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|<span data-ttu-id="9a807-116">Consente di personalizzare i parametri usati dal <xref:System.Net.HttpListener> classe.</span><span class="sxs-lookup"><span data-stu-id="9a807-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="9a807-117">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="9a807-117">httpWebRequest</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|<span data-ttu-id="9a807-118">Consente di personalizzare i parametri della richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="9a807-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="9a807-119">IPv6</span><span class="sxs-lookup"><span data-stu-id="9a807-119">ipv6</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|<span data-ttu-id="9a807-120">Abilita protocollo Internet versione 6 (IPv6) supportano.</span><span class="sxs-lookup"><span data-stu-id="9a807-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="9a807-121">\<performanceCounter > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="9a807-121">\<performanceCounter> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|<span data-ttu-id="9a807-122">I contatori delle prestazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="9a807-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="9a807-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="9a807-123">servicePointManager</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|<span data-ttu-id="9a807-124">Consente di configurare le connessioni alle risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="9a807-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="9a807-125">socket</span><span class="sxs-lookup"><span data-stu-id="9a807-125">socket</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|<span data-ttu-id="9a807-126">Specifica se le operazioni socket usano le porte di completamento.</span><span class="sxs-lookup"><span data-stu-id="9a807-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="9a807-127">\<webProxyScript > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="9a807-127">\<webProxyScript> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|<span data-ttu-id="9a807-128">Consente di configurare le caratteristiche dello script utilizzato per individuare i proxy Web.</span><span class="sxs-lookup"><span data-stu-id="9a807-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9a807-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9a807-129">Parent Elements</span></span>  
  
|<span data-ttu-id="9a807-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a807-130">Element</span></span>|<span data-ttu-id="9a807-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a807-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a807-132">System.NET</span><span class="sxs-lookup"><span data-stu-id="9a807-132">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="9a807-133">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9a807-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a807-134">Note</span><span class="sxs-lookup"><span data-stu-id="9a807-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9a807-135">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="9a807-135">Configuration Files</span></span>  
 <span data-ttu-id="9a807-136">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="9a807-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a807-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a807-137">See Also</span></span>  
- <xref:System.Net?displayProperty=nameWithType>  
- [<span data-ttu-id="9a807-138">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="9a807-138">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
