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
ms.openlocfilehash: 12797e2f06d03aacd81700eae57d5776c1a6f354
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663991"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="b3300-102">\<Elemento > Impostazioni (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="b3300-102">\<settings> Element (Network Settings)</span></span>
<span data-ttu-id="b3300-103">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b3300-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="b3300-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b3300-104">\<configuration></span></span>  
<span data-ttu-id="b3300-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b3300-105">\<system.net></span></span>  
<span data-ttu-id="b3300-106">\<Impostazioni ></span><span class="sxs-lookup"><span data-stu-id="b3300-106">\<settings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3300-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3300-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3300-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b3300-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b3300-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b3300-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3300-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="b3300-110">Attributes</span></span>  
 <span data-ttu-id="b3300-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b3300-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b3300-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b3300-112">Child Elements</span></span>  
  
|<span data-ttu-id="b3300-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="b3300-113">Element</span></span>|<span data-ttu-id="b3300-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3300-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3300-115">httpListener</span><span class="sxs-lookup"><span data-stu-id="b3300-115">httpListener</span></span>](httplistener-element-network-settings.md)|<span data-ttu-id="b3300-116">Personalizza i <xref:System.Net.HttpListener> parametri utilizzati dalla classe.</span><span class="sxs-lookup"><span data-stu-id="b3300-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="b3300-117">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="b3300-117">httpWebRequest</span></span>](httpwebrequest-element-network-settings.md)|<span data-ttu-id="b3300-118">Personalizza i parametri della richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="b3300-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="b3300-119">ipv6</span><span class="sxs-lookup"><span data-stu-id="b3300-119">ipv6</span></span>](ipv6-element-network-settings.md)|<span data-ttu-id="b3300-120">Abilita il supporto protocollo Internet versione 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="b3300-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="b3300-121">\<Elemento > performanceCounter (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="b3300-121">\<performanceCounter> Element (Network Settings)</span></span>](performancecounter-element-network-settings.md)|<span data-ttu-id="b3300-122">Abilita i contatori delle prestazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="b3300-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="b3300-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="b3300-123">servicePointManager</span></span>](servicepointmanager-element-network-settings.md)|<span data-ttu-id="b3300-124">Configura le connessioni alle risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="b3300-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="b3300-125">socket</span><span class="sxs-lookup"><span data-stu-id="b3300-125">socket</span></span>](socket-element-network-settings.md)|<span data-ttu-id="b3300-126">Specifica se le operazioni socket utilizzano le porte di completamento.</span><span class="sxs-lookup"><span data-stu-id="b3300-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="b3300-127">\<Elemento > webProxyScript (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="b3300-127">\<webProxyScript> Element (Network Settings)</span></span>](webproxyscript-element-network-settings.md)|<span data-ttu-id="b3300-128">Configura le caratteristiche dello script utilizzato per individuare i proxy Web.</span><span class="sxs-lookup"><span data-stu-id="b3300-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b3300-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b3300-129">Parent Elements</span></span>  
  
|<span data-ttu-id="b3300-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="b3300-130">Element</span></span>|<span data-ttu-id="b3300-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3300-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3300-132">system.net</span><span class="sxs-lookup"><span data-stu-id="b3300-132">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="b3300-133">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b3300-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3300-134">Note</span><span class="sxs-lookup"><span data-stu-id="b3300-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b3300-135">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="b3300-135">Configuration Files</span></span>  
 <span data-ttu-id="b3300-136">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="b3300-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3300-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3300-137">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="b3300-138">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="b3300-138">Network Settings Schema</span></span>](index.md)
