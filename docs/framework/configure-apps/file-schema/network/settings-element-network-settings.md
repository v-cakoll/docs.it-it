---
title: Elemento <settings> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
ms.openlocfilehash: a1733803d1f5a5bf64aeb69d0360cef3de3b3a69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674415"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="d77d4-102">\<Impostazioni > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="d77d4-102">\<settings> Element (Network Settings)</span></span>
<span data-ttu-id="d77d4-103">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d77d4-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="d77d4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d77d4-104">\<configuration></span></span>  
<span data-ttu-id="d77d4-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="d77d4-105">\<system.net></span></span>  
<span data-ttu-id="d77d4-106">\<Impostazioni ></span><span class="sxs-lookup"><span data-stu-id="d77d4-106">\<settings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d77d4-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d77d4-107">Syntax</span></span>  
  
```xml  
<settings>  
  <httpListener>...</httpListener>  
  <httpWebRequest>...</httpWebRequest>  
  <ipv6>...</ipv6>  
  <performanceCounters>...</performanceCounters>  
  <servicePointManager>...</servicePointManager>  
  <socket>...</socket>  
  <webProxyScript>...</webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d77d4-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d77d4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d77d4-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d77d4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d77d4-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="d77d4-110">Attributes</span></span>  
 <span data-ttu-id="d77d4-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d77d4-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d77d4-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d77d4-112">Child Elements</span></span>  
  
|<span data-ttu-id="d77d4-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="d77d4-113">Element</span></span>|<span data-ttu-id="d77d4-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d77d4-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d77d4-115">httpListener</span><span class="sxs-lookup"><span data-stu-id="d77d4-115">httpListener</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|<span data-ttu-id="d77d4-116">Consente di personalizzare i parametri usati dal <xref:System.Net.HttpListener> classe.</span><span class="sxs-lookup"><span data-stu-id="d77d4-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="d77d4-117">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="d77d4-117">httpWebRequest</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|<span data-ttu-id="d77d4-118">Consente di personalizzare i parametri della richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="d77d4-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="d77d4-119">ipv6</span><span class="sxs-lookup"><span data-stu-id="d77d4-119">ipv6</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|<span data-ttu-id="d77d4-120">Abilita protocollo Internet versione 6 (IPv6) supportano.</span><span class="sxs-lookup"><span data-stu-id="d77d4-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="d77d4-121">\<performanceCounter > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="d77d4-121">\<performanceCounter> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|<span data-ttu-id="d77d4-122">I contatori delle prestazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="d77d4-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="d77d4-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="d77d4-123">servicePointManager</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|<span data-ttu-id="d77d4-124">Consente di configurare le connessioni alle risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="d77d4-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="d77d4-125">socket</span><span class="sxs-lookup"><span data-stu-id="d77d4-125">socket</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|<span data-ttu-id="d77d4-126">Specifica se le operazioni socket usano le porte di completamento.</span><span class="sxs-lookup"><span data-stu-id="d77d4-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="d77d4-127">\<webProxyScript > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="d77d4-127">\<webProxyScript> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|<span data-ttu-id="d77d4-128">Consente di configurare le caratteristiche dello script utilizzato per individuare i proxy Web.</span><span class="sxs-lookup"><span data-stu-id="d77d4-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d77d4-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d77d4-129">Parent Elements</span></span>  
  
|<span data-ttu-id="d77d4-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="d77d4-130">Element</span></span>|<span data-ttu-id="d77d4-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d77d4-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d77d4-132">system.net</span><span class="sxs-lookup"><span data-stu-id="d77d4-132">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="d77d4-133">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d77d4-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d77d4-134">Note</span><span class="sxs-lookup"><span data-stu-id="d77d4-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d77d4-135">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="d77d4-135">Configuration Files</span></span>  
 <span data-ttu-id="d77d4-136">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="d77d4-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d77d4-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d77d4-137">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="d77d4-138">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="d77d4-138">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
