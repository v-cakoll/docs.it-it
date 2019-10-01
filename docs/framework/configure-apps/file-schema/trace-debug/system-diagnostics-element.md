---
title: Elemento < System. Diagnostics >
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: dc05c46cb1ba74baceaaeadc2959a6889faf19c9
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699190"
---
# <a name="systemdiagnostics-element"></a><span data-ttu-id="7d95f-102">Elemento \<system. Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="7d95f-102">\<system.diagnostics> Element</span></span>
<span data-ttu-id="7d95f-103">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="7d95f-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
[<span data-ttu-id="7d95f-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="7d95f-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="7d95f-105">&nbsp; @ no__t-1 **\<System. diagnostics >**</span><span class="sxs-lookup"><span data-stu-id="7d95f-105">&nbsp;&nbsp;**\<system.diagnostics>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d95f-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d95f-106">Syntax</span></span>  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d95f-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7d95f-107">Attributes and Elements</span></span>  
 <span data-ttu-id="7d95f-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7d95f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d95f-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="7d95f-109">Attributes</span></span>  
 <span data-ttu-id="7d95f-110">No.</span><span class="sxs-lookup"><span data-stu-id="7d95f-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7d95f-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7d95f-111">Child Elements</span></span>  
  
|<span data-ttu-id="7d95f-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="7d95f-112">Element</span></span>|<span data-ttu-id="7d95f-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d95f-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d95f-114">\<assert></span><span class="sxs-lookup"><span data-stu-id="7d95f-114">\<assert></span></span>](assert-element.md)|<span data-ttu-id="7d95f-115">Specifica se visualizzare una finestra di messaggio quando si chiama il metodo <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Specifica anche il nome del file in cui scrivere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="7d95f-115">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="7d95f-116">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="7d95f-116">\<performanceCounters></span></span>](performancecounters-element.md)|<span data-ttu-id="7d95f-117">Specifica le dimensioni della memoria globale condivisa dai contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="7d95f-117">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="7d95f-118">\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="7d95f-118">\<sharedListeners></span></span>](sharedlisteners-element.md)|<span data-ttu-id="7d95f-119">Contiene i listener a cui può fare riferimento qualsiasi origine o elemento di traccia.</span><span class="sxs-lookup"><span data-stu-id="7d95f-119">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="7d95f-120">I listener identificati come listener condivisi possono essere aggiunti alle origini o alle tracce in base al nome.</span><span class="sxs-lookup"><span data-stu-id="7d95f-120">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[<span data-ttu-id="7d95f-121">\<sources></span><span class="sxs-lookup"><span data-stu-id="7d95f-121">\<sources></span></span>](sources-element.md)|<span data-ttu-id="7d95f-122">Specifica le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="7d95f-122">Specifies trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="7d95f-123">\<switches></span><span class="sxs-lookup"><span data-stu-id="7d95f-123">\<switches></span></span>](switches-element.md)|<span data-ttu-id="7d95f-124">Contiene le opzioni di traccia e i livelli in cui sono impostate le opzioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="7d95f-124">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[<span data-ttu-id="7d95f-125">\<trace></span><span class="sxs-lookup"><span data-stu-id="7d95f-125">\<trace></span></span>](trace-element.md)|<span data-ttu-id="7d95f-126">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="7d95f-126">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7d95f-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7d95f-127">Parent Elements</span></span>  
  
|<span data-ttu-id="7d95f-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="7d95f-128">Element</span></span>|<span data-ttu-id="7d95f-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d95f-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7d95f-130">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7d95f-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7d95f-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d95f-131">Example</span></span>  
 <span data-ttu-id="7d95f-132">Nell'esempio seguente viene illustrato come incorporare un'opzione di traccia e un listener di traccia nell'elemento **\<system. diagnostics >** .</span><span class="sxs-lookup"><span data-stu-id="7d95f-132">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="7d95f-133">L'opzione di traccia `General` è impostata sul livello <xref:System.Diagnostics.TraceLevel>.</span><span class="sxs-lookup"><span data-stu-id="7d95f-133">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="7d95f-134">Il listener di traccia `myListener` crea un file denominato `MyListener.log` e scrive l'output nel file.</span><span class="sxs-lookup"><span data-stu-id="7d95f-134">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7d95f-135">In .NET Framework versione 2.0 è possibile usare testo per specificare il valore di un'opzione,</span><span class="sxs-lookup"><span data-stu-id="7d95f-135">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="7d95f-136">Ad esempio, è possibile specificare `true` per un <xref:System.Diagnostics.BooleanSwitch> o usare il testo che rappresenta un valore di enumerazione come `Error` per un <xref:System.Diagnostics.TraceSwitch>.</span><span class="sxs-lookup"><span data-stu-id="7d95f-136">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="7d95f-137">La riga `<add name="myTraceSwitch" value="Error" />` equivale a `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="7d95f-137">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7d95f-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d95f-138">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="7d95f-139">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="7d95f-139">Trace and Debug Settings Schema</span></span>](index.md)
