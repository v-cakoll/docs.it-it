---
title: '&lt;performanceCounter&gt; (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 549f3dcfd7225937fd04ad2116e2be311687861b
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47074940"
---
# <a name="ltperformancecountergt-element-network-settings"></a><span data-ttu-id="0fa31-102">&lt;performanceCounter&gt; (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="0fa31-102">&lt;performanceCounter&gt; Element (Network Settings)</span></span>
<span data-ttu-id="0fa31-103">Abilita o disabilita i contatori delle prestazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="0fa31-103">Enables or disables networking performance counters.</span></span>  
  
 <span data-ttu-id="0fa31-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0fa31-104">\<configuration></span></span>  
<span data-ttu-id="0fa31-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="0fa31-105">\<system.net></span></span>  
<span data-ttu-id="0fa31-106">\<Impostazioni ></span><span class="sxs-lookup"><span data-stu-id="0fa31-106">\<settings></span></span>  
<span data-ttu-id="0fa31-107">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="0fa31-107">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fa31-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0fa31-108">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0fa31-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0fa31-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0fa31-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0fa31-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0fa31-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="0fa31-111">Attributes</span></span>  
  
|<span data-ttu-id="0fa31-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="0fa31-112">Attribute</span></span>|<span data-ttu-id="0fa31-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0fa31-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="0fa31-114">Specifica se sono abilitati i contatori delle prestazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="0fa31-114">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="0fa31-115">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="0fa31-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0fa31-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0fa31-116">Child Elements</span></span>  
 <span data-ttu-id="0fa31-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0fa31-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0fa31-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0fa31-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0fa31-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="0fa31-119">Element</span></span>|<span data-ttu-id="0fa31-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0fa31-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0fa31-121">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="0fa31-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="0fa31-122">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="0fa31-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0fa31-123">Note</span><span class="sxs-lookup"><span data-stu-id="0fa31-123">Remarks</span></span>  
 <span data-ttu-id="0fa31-124">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="0fa31-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="0fa31-125">I contatori delle prestazioni della rete devono essere abilitati nel file di configurazione da usare.</span><span class="sxs-lookup"><span data-stu-id="0fa31-125">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="0fa31-126">Tutti i contatori delle prestazioni della rete vengono abilitati o disabilitati con una singola impostazione nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="0fa31-126">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="0fa31-127">Non è possibile abilitare o disabilitare singoli contatori delle prestazioni della rete.</span><span class="sxs-lookup"><span data-stu-id="0fa31-127">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="0fa31-128">Per altre informazioni sui contatori di prestazioni di rete specifico, vedere [contatori delle prestazioni della rete](https://msdn.microsoft.com/library/d1860235-f643-46ae-846c-ff0ed8b0e3cd).</span><span class="sxs-lookup"><span data-stu-id="0fa31-128">For more information on the specific networking performance counters, see [Networking Performance Counters](https://msdn.microsoft.com/library/d1860235-f643-46ae-846c-ff0ed8b0e3cd).</span></span>  
  
 <span data-ttu-id="0fa31-129">Il valore predefinito è che le prestazioni di rete i contatori sono disabilitati.</span><span class="sxs-lookup"><span data-stu-id="0fa31-129">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="0fa31-130">Il <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> proprietà può essere utilizzata per ottenere il valore corrente del **abilitata** attributo dal file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="0fa31-130">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fa31-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="0fa31-131">Example</span></span>  
 <span data-ttu-id="0fa31-132">Nell'esempio seguente viene illustrato come configurare il <xref:System.Net> e relativi spazi dei nomi per abilitare i contatori delle prestazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="0fa31-132">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <performanceCounters  
        enabled="true"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0fa31-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0fa31-133">See Also</span></span>  
 <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="0fa31-134">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="0fa31-134">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)  
 [<span data-ttu-id="0fa31-135">I contatori delle prestazioni di rete</span><span class="sxs-lookup"><span data-stu-id="0fa31-135">Networking Performance Counters</span></span>](https://msdn.microsoft.com/library/d1860235-f643-46ae-846c-ff0ed8b0e3cd)
