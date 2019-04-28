---
title: Elemento <performanceCounter> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
ms.openlocfilehash: 30c5cd07c92a8fc3c340cab0ff9ae74e940c0c12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705239"
---
# <a name="performancecounter-element-network-settings"></a><span data-ttu-id="4363b-102">\<performanceCounter > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="4363b-102">\<performanceCounter> Element (Network Settings)</span></span>
<span data-ttu-id="4363b-103">Abilita o disabilita i contatori delle prestazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="4363b-103">Enables or disables networking performance counters.</span></span>  
  
 <span data-ttu-id="4363b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4363b-104">\<configuration></span></span>  
<span data-ttu-id="4363b-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="4363b-105">\<system.net></span></span>  
<span data-ttu-id="4363b-106">\<Impostazioni ></span><span class="sxs-lookup"><span data-stu-id="4363b-106">\<settings></span></span>  
<span data-ttu-id="4363b-107">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="4363b-107">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4363b-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4363b-108">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4363b-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4363b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4363b-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4363b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4363b-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="4363b-111">Attributes</span></span>  
  
|<span data-ttu-id="4363b-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="4363b-112">Attribute</span></span>|<span data-ttu-id="4363b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4363b-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="4363b-114">Specifica se sono abilitati i contatori delle prestazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="4363b-114">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="4363b-115">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="4363b-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4363b-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4363b-116">Child Elements</span></span>  
 <span data-ttu-id="4363b-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4363b-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4363b-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4363b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4363b-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="4363b-119">Element</span></span>|<span data-ttu-id="4363b-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4363b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4363b-121">settings</span><span class="sxs-lookup"><span data-stu-id="4363b-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="4363b-122">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="4363b-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4363b-123">Note</span><span class="sxs-lookup"><span data-stu-id="4363b-123">Remarks</span></span>  
 <span data-ttu-id="4363b-124">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4363b-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="4363b-125">I contatori delle prestazioni della rete devono essere abilitati nel file di configurazione da usare.</span><span class="sxs-lookup"><span data-stu-id="4363b-125">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="4363b-126">Tutti i contatori delle prestazioni della rete vengono abilitati o disabilitati con una singola impostazione nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4363b-126">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="4363b-127">Non è possibile abilitare o disabilitare singoli contatori delle prestazioni della rete.</span><span class="sxs-lookup"><span data-stu-id="4363b-127">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="4363b-128">Per altre informazioni sui contatori di prestazioni di rete specifico, vedere [contatori delle prestazioni della rete](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking).</span><span class="sxs-lookup"><span data-stu-id="4363b-128">For more information on the specific networking performance counters, see [Networking Performance Counters](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking).</span></span>  
  
 <span data-ttu-id="4363b-129">Il valore predefinito è che le prestazioni di rete i contatori sono disabilitati.</span><span class="sxs-lookup"><span data-stu-id="4363b-129">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="4363b-130">Il <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> proprietà può essere utilizzata per ottenere il valore corrente del **abilitata** attributo dal file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="4363b-130">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4363b-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="4363b-131">Example</span></span>  
 <span data-ttu-id="4363b-132">Nell'esempio seguente viene illustrato come configurare il <xref:System.Net> e relativi spazi dei nomi per abilitare i contatori delle prestazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="4363b-132">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4363b-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4363b-133">See also</span></span>

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4363b-134">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="4363b-134">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="4363b-135">I contatori delle prestazioni di rete</span><span class="sxs-lookup"><span data-stu-id="4363b-135">Networking Performance Counters</span></span>](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking)
