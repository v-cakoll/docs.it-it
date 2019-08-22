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
ms.openlocfilehash: 05aac6c1ed3c04bce263a45cafdb9bec906bd75b
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664054"
---
# <a name="performancecounter-element-network-settings"></a><span data-ttu-id="eefa4-102">\<Elemento > performanceCounter (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="eefa4-102">\<performanceCounter> Element (Network Settings)</span></span>
<span data-ttu-id="eefa4-103">Abilita o Disabilita i contatori delle prestazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="eefa4-103">Enables or disables networking performance counters.</span></span>  
  
 <span data-ttu-id="eefa4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="eefa4-104">\<configuration></span></span>  
<span data-ttu-id="eefa4-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="eefa4-105">\<system.net></span></span>  
<span data-ttu-id="eefa4-106">\<Impostazioni ></span><span class="sxs-lookup"><span data-stu-id="eefa4-106">\<settings></span></span>  
<span data-ttu-id="eefa4-107">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="eefa4-107">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eefa4-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eefa4-108">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eefa4-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="eefa4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="eefa4-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="eefa4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eefa4-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="eefa4-111">Attributes</span></span>  
  
|<span data-ttu-id="eefa4-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="eefa4-112">Attribute</span></span>|<span data-ttu-id="eefa4-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="eefa4-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="eefa4-114">Specifica se i contatori delle prestazioni di rete sono abilitati.</span><span class="sxs-lookup"><span data-stu-id="eefa4-114">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="eefa4-115">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="eefa4-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eefa4-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="eefa4-116">Child Elements</span></span>  
 <span data-ttu-id="eefa4-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="eefa4-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eefa4-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="eefa4-118">Parent Elements</span></span>  
  
|<span data-ttu-id="eefa4-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="eefa4-119">Element</span></span>|<span data-ttu-id="eefa4-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eefa4-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eefa4-121">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="eefa4-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="eefa4-122">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="eefa4-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eefa4-123">Note</span><span class="sxs-lookup"><span data-stu-id="eefa4-123">Remarks</span></span>  
 <span data-ttu-id="eefa4-124">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="eefa4-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="eefa4-125">I contatori delle prestazioni della rete devono essere abilitati nel file di configurazione da usare.</span><span class="sxs-lookup"><span data-stu-id="eefa4-125">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="eefa4-126">Tutti i contatori delle prestazioni della rete vengono abilitati o disabilitati con una singola impostazione nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="eefa4-126">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="eefa4-127">Non è possibile abilitare o disabilitare singoli contatori delle prestazioni della rete.</span><span class="sxs-lookup"><span data-stu-id="eefa4-127">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="eefa4-128">Per ulteriori informazioni sui contatori delle prestazioni di rete specifici, vedere [contatori delle prestazioni di rete](../../../debug-trace-profile/performance-counters.md#networking).</span><span class="sxs-lookup"><span data-stu-id="eefa4-128">For more information on the specific networking performance counters, see [Networking Performance Counters](../../../debug-trace-profile/performance-counters.md#networking).</span></span>  
  
 <span data-ttu-id="eefa4-129">Il valore predefinito è che i contatori delle prestazioni di rete sono disabilitati.</span><span class="sxs-lookup"><span data-stu-id="eefa4-129">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="eefa4-130">È <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> possibile utilizzare la proprietà per ottenere il valore corrente dell'attributo **Enabled** dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="eefa4-130">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eefa4-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="eefa4-131">Example</span></span>  
 <span data-ttu-id="eefa4-132">Nell'esempio seguente viene illustrato come configurare gli <xref:System.Net> spazi dei nomi e correlati per abilitare i contatori delle prestazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="eefa4-132">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eefa4-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eefa4-133">See also</span></span>

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="eefa4-134">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="eefa4-134">Network Settings Schema</span></span>](index.md)
- [<span data-ttu-id="eefa4-135">Contatori delle prestazioni di rete</span><span class="sxs-lookup"><span data-stu-id="eefa4-135">Networking Performance Counters</span></span>](../../../debug-trace-profile/performance-counters.md#networking)
