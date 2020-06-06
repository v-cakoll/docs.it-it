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
ms.openlocfilehash: d510c445c585a36005ed415b14188efc4be03984
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089110"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="c022d-102">Elemento \<settings> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="c022d-102">\<settings> Element (Network Settings)</span></span>
<span data-ttu-id="c022d-103">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c022d-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<settings>**

## <a name="syntax"></a><span data-ttu-id="c022d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c022d-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c022d-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c022d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c022d-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c022d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c022d-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="c022d-107">Attributes</span></span>  
 <span data-ttu-id="c022d-108">No.</span><span class="sxs-lookup"><span data-stu-id="c022d-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c022d-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c022d-109">Child Elements</span></span>  
  
|<span data-ttu-id="c022d-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="c022d-110">Element</span></span>|<span data-ttu-id="c022d-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c022d-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c022d-112">httpListener</span><span class="sxs-lookup"><span data-stu-id="c022d-112">httpListener</span></span>](httplistener-element-network-settings.md)|<span data-ttu-id="c022d-113">Personalizza i parametri utilizzati dalla <xref:System.Net.HttpListener> classe.</span><span class="sxs-lookup"><span data-stu-id="c022d-113">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="c022d-114">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="c022d-114">httpWebRequest</span></span>](httpwebrequest-element-network-settings.md)|<span data-ttu-id="c022d-115">Personalizza i parametri della richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="c022d-115">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="c022d-116">IPv6</span><span class="sxs-lookup"><span data-stu-id="c022d-116">ipv6</span></span>](ipv6-element-network-settings.md)|<span data-ttu-id="c022d-117">Abilita il supporto protocollo Internet versione 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="c022d-117">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="c022d-118">\<performanceCounter>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="c022d-118">\<performanceCounter> Element (Network Settings)</span></span>](performancecounter-element-network-settings.md)|<span data-ttu-id="c022d-119">Abilita i contatori delle prestazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="c022d-119">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="c022d-120">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="c022d-120">servicePointManager</span></span>](servicepointmanager-element-network-settings.md)|<span data-ttu-id="c022d-121">Configura le connessioni alle risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="c022d-121">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="c022d-122">presa</span><span class="sxs-lookup"><span data-stu-id="c022d-122">socket</span></span>](socket-element-network-settings.md)|<span data-ttu-id="c022d-123">Specifica se le operazioni socket utilizzano le porte di completamento.</span><span class="sxs-lookup"><span data-stu-id="c022d-123">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="c022d-124">\<webProxyScript>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="c022d-124">\<webProxyScript> Element (Network Settings)</span></span>](webproxyscript-element-network-settings.md)|<span data-ttu-id="c022d-125">Configura le caratteristiche dello script utilizzato per individuare i proxy Web.</span><span class="sxs-lookup"><span data-stu-id="c022d-125">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c022d-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c022d-126">Parent Elements</span></span>  
  
|<span data-ttu-id="c022d-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="c022d-127">Element</span></span>|<span data-ttu-id="c022d-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c022d-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c022d-129">system.net</span><span class="sxs-lookup"><span data-stu-id="c022d-129">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="c022d-130">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c022d-130">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c022d-131">Commenti</span><span class="sxs-lookup"><span data-stu-id="c022d-131">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c022d-132">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="c022d-132">Configuration Files</span></span>  
 <span data-ttu-id="c022d-133">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="c022d-133">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c022d-134">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="c022d-134">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="c022d-135">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="c022d-135">Network Settings Schema</span></span>](index.md)
