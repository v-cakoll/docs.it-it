---
title: '&lt;traccia&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
ms.openlocfilehash: 668e69b534617dbe05bbefde6e85b905601961fc
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083522"
---
# <a name="lttracegt-element"></a><span data-ttu-id="2f021-102">&lt;traccia&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="2f021-102">&lt;trace&gt; Element</span></span>
<span data-ttu-id="2f021-103">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="2f021-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
 <span data-ttu-id="2f021-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2f021-104">\<configuration></span></span>  
<span data-ttu-id="2f021-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="2f021-105">\<system.diagnostics></span></span>  
<span data-ttu-id="2f021-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="2f021-106">\<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f021-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f021-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f021-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2f021-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2f021-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2f021-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f021-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="2f021-110">Attributes</span></span>  
  
|<span data-ttu-id="2f021-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="2f021-111">Attribute</span></span>|<span data-ttu-id="2f021-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f021-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="2f021-113">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2f021-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2f021-114">Specifica se i listener di traccia automaticamente svuotano del buffer di output dopo ogni operazione di scrittura.</span><span class="sxs-lookup"><span data-stu-id="2f021-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="2f021-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2f021-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2f021-116">Specifica il numero di spazi del rientro.</span><span class="sxs-lookup"><span data-stu-id="2f021-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="2f021-117">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2f021-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2f021-118">Indica se il blocco globale deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="2f021-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="2f021-119">Attributo AutoFlush</span><span class="sxs-lookup"><span data-stu-id="2f021-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="2f021-120">Value</span><span class="sxs-lookup"><span data-stu-id="2f021-120">Value</span></span>|<span data-ttu-id="2f021-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f021-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="2f021-122">Non consente automaticamente di scaricare il buffer di output.</span><span class="sxs-lookup"><span data-stu-id="2f021-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="2f021-123">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2f021-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="2f021-124">Scarica automaticamente il buffer di output.</span><span class="sxs-lookup"><span data-stu-id="2f021-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="2f021-125">Attributo useGlobalLock</span><span class="sxs-lookup"><span data-stu-id="2f021-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="2f021-126">Value</span><span class="sxs-lookup"><span data-stu-id="2f021-126">Value</span></span>|<span data-ttu-id="2f021-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f021-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="2f021-128">Non utilizzare il blocco globale se il listener è thread-safe. in caso contrario, viene utilizzato il blocco globale.</span><span class="sxs-lookup"><span data-stu-id="2f021-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="2f021-129">Usa il blocco globale indipendentemente dal fatto che il listener è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="2f021-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="2f021-130">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2f021-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f021-131">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2f021-131">Child Elements</span></span>  
  
|<span data-ttu-id="2f021-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f021-132">Element</span></span>|<span data-ttu-id="2f021-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f021-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f021-134">\<listeners></span><span class="sxs-lookup"><span data-stu-id="2f021-134">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|<span data-ttu-id="2f021-135">Specifica un listener che raccoglie, archivia e indirizza i messaggi.</span><span class="sxs-lookup"><span data-stu-id="2f021-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2f021-136">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2f021-136">Parent Elements</span></span>  
  
|<span data-ttu-id="2f021-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f021-137">Element</span></span>|<span data-ttu-id="2f021-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f021-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2f021-139">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2f021-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="2f021-140">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="2f021-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2f021-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="2f021-141">Example</span></span>  
 <span data-ttu-id="2f021-142">Nell'esempio seguente viene illustrato come utilizzare il `<trace>` elemento a cui aggiungere il listener `MyListener` per il `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="2f021-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="2f021-143">`MyListener` Crea un file denominato `MyListener.log` e scrive l'output del file.</span><span class="sxs-lookup"><span data-stu-id="2f021-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="2f021-144">Il `useGlobalLock` attributo è impostato su `false`, in modo che il blocco globale non può essere utilizzato se il listener di traccia è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="2f021-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="2f021-145">Il `autoflush` attributo è impostato su `true`, in modo che il listener di traccia da scrivere nel file indipendentemente dal fatto che il <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="2f021-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="2f021-146">Il `indentsize` attributo è impostato su 0 (zero), che fa sì che il listener per il rientro quando la <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="2f021-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f021-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f021-147">See also</span></span>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="2f021-148">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="2f021-148">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
