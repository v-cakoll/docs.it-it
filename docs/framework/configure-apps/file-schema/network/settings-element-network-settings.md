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
ms.openlocfilehash: ba08f630dc602c950da309bf29482d85b41af7ef
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697686"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="ea96c-102">Elemento > \<settings (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="ea96c-102">\<settings> Element (Network Settings)</span></span>
<span data-ttu-id="ea96c-103">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ea96c-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  
  
[<span data-ttu-id="ea96c-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="ea96c-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="ea96c-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="ea96c-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="ea96c-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<settings >**</span><span class="sxs-lookup"><span data-stu-id="ea96c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<settings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea96c-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea96c-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea96c-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ea96c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ea96c-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ea96c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea96c-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="ea96c-110">Attributes</span></span>  
 <span data-ttu-id="ea96c-111">No.</span><span class="sxs-lookup"><span data-stu-id="ea96c-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ea96c-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ea96c-112">Child Elements</span></span>  
  
|<span data-ttu-id="ea96c-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea96c-113">Element</span></span>|<span data-ttu-id="ea96c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea96c-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea96c-115">httpListener</span><span class="sxs-lookup"><span data-stu-id="ea96c-115">httpListener</span></span>](httplistener-element-network-settings.md)|<span data-ttu-id="ea96c-116">Personalizza i parametri utilizzati dalla classe <xref:System.Net.HttpListener>.</span><span class="sxs-lookup"><span data-stu-id="ea96c-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="ea96c-117">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="ea96c-117">httpWebRequest</span></span>](httpwebrequest-element-network-settings.md)|<span data-ttu-id="ea96c-118">Personalizza i parametri della richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="ea96c-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="ea96c-119">ipv6</span><span class="sxs-lookup"><span data-stu-id="ea96c-119">ipv6</span></span>](ipv6-element-network-settings.md)|<span data-ttu-id="ea96c-120">Abilita il supporto protocollo Internet versione 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="ea96c-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="ea96c-121">Elemento > \<performanceCounter (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="ea96c-121">\<performanceCounter> Element (Network Settings)</span></span>](performancecounter-element-network-settings.md)|<span data-ttu-id="ea96c-122">Abilita i contatori delle prestazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="ea96c-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="ea96c-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="ea96c-123">servicePointManager</span></span>](servicepointmanager-element-network-settings.md)|<span data-ttu-id="ea96c-124">Configura le connessioni alle risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="ea96c-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="ea96c-125">socket</span><span class="sxs-lookup"><span data-stu-id="ea96c-125">socket</span></span>](socket-element-network-settings.md)|<span data-ttu-id="ea96c-126">Specifica se le operazioni socket utilizzano le porte di completamento.</span><span class="sxs-lookup"><span data-stu-id="ea96c-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="ea96c-127">Elemento > \<webProxyScript (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="ea96c-127">\<webProxyScript> Element (Network Settings)</span></span>](webproxyscript-element-network-settings.md)|<span data-ttu-id="ea96c-128">Configura le caratteristiche dello script utilizzato per individuare i proxy Web.</span><span class="sxs-lookup"><span data-stu-id="ea96c-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ea96c-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ea96c-129">Parent Elements</span></span>  
  
|<span data-ttu-id="ea96c-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea96c-130">Element</span></span>|<span data-ttu-id="ea96c-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea96c-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea96c-132">system.net</span><span class="sxs-lookup"><span data-stu-id="ea96c-132">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="ea96c-133">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ea96c-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea96c-134">Note</span><span class="sxs-lookup"><span data-stu-id="ea96c-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ea96c-135">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="ea96c-135">Configuration Files</span></span>  
 <span data-ttu-id="ea96c-136">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ea96c-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea96c-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea96c-137">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="ea96c-138">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="ea96c-138">Network Settings Schema</span></span>](index.md)
