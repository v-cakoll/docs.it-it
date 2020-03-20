---
title: <trace> Elemento
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
ms.openlocfilehash: 7d8a989219d84e8604e767456c84c0092bc73b22
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153166"
---
# <a name="trace-element"></a><span data-ttu-id="7f446-102">\<elemento> di traccia</span><span class="sxs-lookup"><span data-stu-id="7f446-102">\<trace> Element</span></span>
<span data-ttu-id="7f446-103">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="7f446-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
[<span data-ttu-id="7f446-104">**\<>di configurazione**</span><span class="sxs-lookup"><span data-stu-id="7f446-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="7f446-105">&nbsp;&nbsp;[**\<>system.diagnostics**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="7f446-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="7f446-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<>traccia**</span><span class="sxs-lookup"><span data-stu-id="7f446-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<trace>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f446-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f446-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f446-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7f446-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7f446-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7f446-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f446-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="7f446-110">Attributes</span></span>  
  
|<span data-ttu-id="7f446-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="7f446-111">Attribute</span></span>|<span data-ttu-id="7f446-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f446-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="7f446-113">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7f446-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="7f446-114">Specifica se i listener di traccia scaricano automaticamente il buffer di output dopo ogni operazione di scrittura.</span><span class="sxs-lookup"><span data-stu-id="7f446-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="7f446-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7f446-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="7f446-116">Specifica il numero di spazi per il rientro.</span><span class="sxs-lookup"><span data-stu-id="7f446-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="7f446-117">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7f446-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="7f446-118">Indica se deve essere utilizzato il blocco globale.</span><span class="sxs-lookup"><span data-stu-id="7f446-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="7f446-119">Attributo autoflush</span><span class="sxs-lookup"><span data-stu-id="7f446-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="7f446-120">valore</span><span class="sxs-lookup"><span data-stu-id="7f446-120">Value</span></span>|<span data-ttu-id="7f446-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f446-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="7f446-122">Non scarica automaticamente il buffer di output.</span><span class="sxs-lookup"><span data-stu-id="7f446-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="7f446-123">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="7f446-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="7f446-124">Scarica automaticamente il buffer di output.</span><span class="sxs-lookup"><span data-stu-id="7f446-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="7f446-125">UseGlobalLock Attributo</span><span class="sxs-lookup"><span data-stu-id="7f446-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="7f446-126">valore</span><span class="sxs-lookup"><span data-stu-id="7f446-126">Value</span></span>|<span data-ttu-id="7f446-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f446-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="7f446-128">Non utilizza il blocco globale se il listener è thread-safe; in caso contrario, utilizza il blocco globale.</span><span class="sxs-lookup"><span data-stu-id="7f446-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="7f446-129">Utilizza il blocco globale indipendentemente dal fatto che il listener sia thread-safe.</span><span class="sxs-lookup"><span data-stu-id="7f446-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="7f446-130">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="7f446-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f446-131">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7f446-131">Child Elements</span></span>  
  
|<span data-ttu-id="7f446-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f446-132">Element</span></span>|<span data-ttu-id="7f446-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f446-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f446-134">\<>di ascoltatori</span><span class="sxs-lookup"><span data-stu-id="7f446-134">\<listeners></span></span>](listeners-element-for-trace.md)|<span data-ttu-id="7f446-135">Specifica un listener che raccoglie, archivia e instrada i messaggi.</span><span class="sxs-lookup"><span data-stu-id="7f446-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7f446-136">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7f446-136">Parent Elements</span></span>  
  
|<span data-ttu-id="7f446-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f446-137">Element</span></span>|<span data-ttu-id="7f446-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f446-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7f446-139">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7f446-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="7f446-140">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="7f446-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7f446-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f446-141">Example</span></span>  
 <span data-ttu-id="7f446-142">Nell'esempio seguente viene `<trace>` illustrato come utilizzare `MyListener` l'elemento per aggiungere il listener alla `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="7f446-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="7f446-143">`MyListener`crea un file `MyListener.log` denominato e scrive l'output nel file.</span><span class="sxs-lookup"><span data-stu-id="7f446-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="7f446-144">L'attributo `useGlobalLock` `false`è impostato su , che determina la non utilizzo del blocco globale se il listener di traccia è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="7f446-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="7f446-145">L'attributo `autoflush` `true`è impostato su , che fa sì che <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> il listener di traccia scriva nel file indipendentemente dal fatto che il metodo venga chiamato o meno.</span><span class="sxs-lookup"><span data-stu-id="7f446-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="7f446-146">L'attributo `indentsize` è impostato su 0 (zero), che fa <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> sì che il listener indenta zero spazi quando viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="7f446-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7f446-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f446-147">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="7f446-148">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="7f446-148">Trace and Debug Settings Schema</span></span>](index.md)
