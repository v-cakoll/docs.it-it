---
title: Elemento <System. Diagnostics>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: 4f831592d7d178276b1625e1ef7d8512085342af
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153207"
---
# <a name="systemdiagnostics-element"></a><span data-ttu-id="6e89e-102">\<system.diagnostics> Elemento</span><span class="sxs-lookup"><span data-stu-id="6e89e-102">\<system.diagnostics> Element</span></span>
<span data-ttu-id="6e89e-103">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="6e89e-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.diagnostics>**  
  
## <a name="syntax"></a><span data-ttu-id="6e89e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6e89e-104">Syntax</span></span>  
  
```xml  
<system.diagnostics>
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e89e-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6e89e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="6e89e-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6e89e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e89e-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="6e89e-107">Attributes</span></span>  
 <span data-ttu-id="6e89e-108">No.</span><span class="sxs-lookup"><span data-stu-id="6e89e-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6e89e-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6e89e-109">Child Elements</span></span>  
  
|<span data-ttu-id="6e89e-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="6e89e-110">Element</span></span>|<span data-ttu-id="6e89e-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6e89e-111">Description</span></span>|  
|-------------|-----------------|  
|[\<assert>](assert-element.md)|<span data-ttu-id="6e89e-112">Specifica se visualizzare una finestra di messaggio quando si chiama il metodo <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Specifica anche il nome del file in cui scrivere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="6e89e-112">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[\<performanceCounters>](performancecounters-element.md)|<span data-ttu-id="6e89e-113">Specifica le dimensioni della memoria globale condivisa dai contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="6e89e-113">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[\<sharedListeners>](sharedlisteners-element.md)|<span data-ttu-id="6e89e-114">Contiene i listener a cui può fare riferimento qualsiasi origine o elemento di traccia.</span><span class="sxs-lookup"><span data-stu-id="6e89e-114">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="6e89e-115">I listener identificati come listener condivisi possono essere aggiunti alle origini o alle tracce in base al nome.</span><span class="sxs-lookup"><span data-stu-id="6e89e-115">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[\<sources>](sources-element.md)|<span data-ttu-id="6e89e-116">Specifica le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="6e89e-116">Specifies trace sources that initiate tracing messages.</span></span>|  
|[\<switches>](switches-element.md)|<span data-ttu-id="6e89e-117">Contiene le opzioni di traccia e i livelli in cui sono impostate le opzioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="6e89e-117">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[\<trace>](trace-element.md)|<span data-ttu-id="6e89e-118">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="6e89e-118">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6e89e-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6e89e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6e89e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="6e89e-120">Element</span></span>|<span data-ttu-id="6e89e-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6e89e-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6e89e-122">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6e89e-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6e89e-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="6e89e-123">Example</span></span>  
 <span data-ttu-id="6e89e-124">Nell'esempio seguente viene illustrato come incorporare un'opzione di traccia e un listener di traccia all'interno dell' **\<system.diagnostics>** elemento.</span><span class="sxs-lookup"><span data-stu-id="6e89e-124">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="6e89e-125">L' `General` opzione Trace è impostata sul <xref:System.Diagnostics.TraceLevel> livello.</span><span class="sxs-lookup"><span data-stu-id="6e89e-125">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="6e89e-126">Il listener `myListener` di traccia crea un file denominato `MyListener.log` e scrive l'output nel file.</span><span class="sxs-lookup"><span data-stu-id="6e89e-126">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6e89e-127">In .NET Framework versione 2.0 è possibile usare testo per specificare il valore di un'opzione,</span><span class="sxs-lookup"><span data-stu-id="6e89e-127">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="6e89e-128">Ad esempio, è possibile specificare `true` per <xref:System.Diagnostics.BooleanSwitch> o usare il testo che rappresenta un valore di enumerazione come `Error` per un oggetto <xref:System.Diagnostics.TraceSwitch> .</span><span class="sxs-lookup"><span data-stu-id="6e89e-128">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="6e89e-129">La riga `<add name="myTraceSwitch" value="Error" />` equivale a `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="6e89e-129">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6e89e-130">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="6e89e-130">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="6e89e-131">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="6e89e-131">Trace and Debug Settings Schema</span></span>](index.md)
