---
title: '&lt;System. Diagnostics&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d336a0f733451cb28d8fe57af20585515b71ca4b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltsystemdiagnosticsgt-element"></a><span data-ttu-id="660c3-102">&lt;System. Diagnostics&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="660c3-102">&lt;system.diagnostics&gt; Element</span></span>
<span data-ttu-id="660c3-103">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="660c3-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="660c3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="660c3-104">\<configuration></span></span>  
<span data-ttu-id="660c3-105">\<System. Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="660c3-105">\<system.diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="660c3-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="660c3-106">Syntax</span></span>  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="660c3-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="660c3-107">Attributes and Elements</span></span>  
 <span data-ttu-id="660c3-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="660c3-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="660c3-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="660c3-109">Attributes</span></span>  
 <span data-ttu-id="660c3-110">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="660c3-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="660c3-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="660c3-111">Child Elements</span></span>  
  
|<span data-ttu-id="660c3-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="660c3-112">Element</span></span>|<span data-ttu-id="660c3-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="660c3-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="660c3-114">\<assert></span><span class="sxs-lookup"><span data-stu-id="660c3-114">\<assert></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|<span data-ttu-id="660c3-115">Specifica se visualizzare una finestra di messaggio quando si chiama il metodo <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Specifica anche il nome del file in cui scrivere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="660c3-115">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="660c3-116">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="660c3-116">\<performanceCounters></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|<span data-ttu-id="660c3-117">Specifica le dimensioni della memoria globale condivisa dai contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="660c3-117">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="660c3-118">\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="660c3-118">\<sharedListeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|<span data-ttu-id="660c3-119">Contiene i listener a cui può fare riferimento qualsiasi origine o elemento di traccia.</span><span class="sxs-lookup"><span data-stu-id="660c3-119">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="660c3-120">I listener identificati come condivisi possono essere aggiunti alle origini o le tracce in base al nome.</span><span class="sxs-lookup"><span data-stu-id="660c3-120">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[<span data-ttu-id="660c3-121">\<sources></span><span class="sxs-lookup"><span data-stu-id="660c3-121">\<sources></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|<span data-ttu-id="660c3-122">Specifica le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="660c3-122">Specifies trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="660c3-123">\<switches></span><span class="sxs-lookup"><span data-stu-id="660c3-123">\<switches></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|<span data-ttu-id="660c3-124">Contiene le opzioni di traccia e i livelli in cui vengono impostate le opzioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="660c3-124">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[<span data-ttu-id="660c3-125">\<trace></span><span class="sxs-lookup"><span data-stu-id="660c3-125">\<trace></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|<span data-ttu-id="660c3-126">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="660c3-126">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="660c3-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="660c3-127">Parent Elements</span></span>  
  
|<span data-ttu-id="660c3-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="660c3-128">Element</span></span>|<span data-ttu-id="660c3-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="660c3-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="660c3-130">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="660c3-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="660c3-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="660c3-131">Example</span></span>  
 <span data-ttu-id="660c3-132">Nell'esempio seguente viene illustrato come incorporare un'opzione di traccia e un listener di traccia all'interno di  **\<System. Diagnostics >** elemento.</span><span class="sxs-lookup"><span data-stu-id="660c3-132">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="660c3-133">Il `General` è impostata l'opzione di traccia di <xref:System.Diagnostics.TraceLevel> livello.</span><span class="sxs-lookup"><span data-stu-id="660c3-133">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="660c3-134">Il listener di traccia `myListener` crea un file denominato `MyListener.log` e scrive l'output del file.</span><span class="sxs-lookup"><span data-stu-id="660c3-134">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="660c3-135">In .NET Framework versione 2.0 è possibile usare testo per specificare il valore di un'opzione,</span><span class="sxs-lookup"><span data-stu-id="660c3-135">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="660c3-136">Ad esempio, è possibile specificare `true` per un <xref:System.Diagnostics.BooleanSwitch> o il testo che rappresenta un valore di enumerazione, ad esempio `Error` per un <xref:System.Diagnostics.TraceSwitch>.</span><span class="sxs-lookup"><span data-stu-id="660c3-136">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="660c3-137">La riga `<add name="myTraceSwitch" value="Error" />` equivale a `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="660c3-137">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="660c3-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="660c3-138">See Also</span></span>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 [<span data-ttu-id="660c3-139">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="660c3-139">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
