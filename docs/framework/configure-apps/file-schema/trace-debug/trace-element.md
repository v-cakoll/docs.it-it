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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153166"
---
# <a name="trace-element"></a><span data-ttu-id="90a56-102">\<trace> Elemento</span><span class="sxs-lookup"><span data-stu-id="90a56-102">\<trace> Element</span></span>
<span data-ttu-id="90a56-103">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="90a56-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<trace>**  
  
## <a name="syntax"></a><span data-ttu-id="90a56-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90a56-104">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90a56-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="90a56-105">Attributes and Elements</span></span>  
 <span data-ttu-id="90a56-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="90a56-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90a56-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="90a56-107">Attributes</span></span>  
  
|<span data-ttu-id="90a56-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="90a56-108">Attribute</span></span>|<span data-ttu-id="90a56-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90a56-109">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="90a56-110">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="90a56-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="90a56-111">Specifica se i listener di traccia scaricano automaticamente il buffer di output dopo ogni operazione di scrittura.</span><span class="sxs-lookup"><span data-stu-id="90a56-111">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="90a56-112">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="90a56-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="90a56-113">Specifica il numero di spazi da rientrare.</span><span class="sxs-lookup"><span data-stu-id="90a56-113">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="90a56-114">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="90a56-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="90a56-115">Indica se deve essere utilizzato il blocco globale.</span><span class="sxs-lookup"><span data-stu-id="90a56-115">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="90a56-116">AutoFlush (attributo)</span><span class="sxs-lookup"><span data-stu-id="90a56-116">autoflush Attribute</span></span>  
  
|<span data-ttu-id="90a56-117">Valore</span><span class="sxs-lookup"><span data-stu-id="90a56-117">Value</span></span>|<span data-ttu-id="90a56-118">Description</span><span class="sxs-lookup"><span data-stu-id="90a56-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="90a56-119">Non Scarica automaticamente il buffer di output.</span><span class="sxs-lookup"><span data-stu-id="90a56-119">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="90a56-120">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="90a56-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="90a56-121">Scarica automaticamente il buffer di output.</span><span class="sxs-lookup"><span data-stu-id="90a56-121">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="90a56-122">Attributo useGlobalLock</span><span class="sxs-lookup"><span data-stu-id="90a56-122">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="90a56-123">Valore</span><span class="sxs-lookup"><span data-stu-id="90a56-123">Value</span></span>|<span data-ttu-id="90a56-124">Description</span><span class="sxs-lookup"><span data-stu-id="90a56-124">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="90a56-125">Non utilizza il blocco globale se il listener è thread-safe. in caso contrario, utilizza il blocco globale.</span><span class="sxs-lookup"><span data-stu-id="90a56-125">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="90a56-126">Usa il blocco globale indipendentemente dal fatto che il listener sia thread-safe.</span><span class="sxs-lookup"><span data-stu-id="90a56-126">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="90a56-127">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="90a56-127">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="90a56-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="90a56-128">Child Elements</span></span>  
  
|<span data-ttu-id="90a56-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="90a56-129">Element</span></span>|<span data-ttu-id="90a56-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90a56-130">Description</span></span>|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-trace.md)|<span data-ttu-id="90a56-131">Specifica un listener che raccoglie, archivia e instrada i messaggi.</span><span class="sxs-lookup"><span data-stu-id="90a56-131">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="90a56-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="90a56-132">Parent Elements</span></span>  
  
|<span data-ttu-id="90a56-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="90a56-133">Element</span></span>|<span data-ttu-id="90a56-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90a56-134">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="90a56-135">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="90a56-135">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="90a56-136">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="90a56-136">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="90a56-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="90a56-137">Example</span></span>  
 <span data-ttu-id="90a56-138">Nell'esempio seguente viene illustrato come utilizzare l' `<trace>` elemento per aggiungere il listener `MyListener` alla `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="90a56-138">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="90a56-139">`MyListener`Crea un file denominato `MyListener.log` e scrive l'output nel file.</span><span class="sxs-lookup"><span data-stu-id="90a56-139">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="90a56-140">L' `useGlobalLock` attributo è impostato su `false` , che impedisce l'utilizzo del blocco globale se il listener di traccia è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="90a56-140">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="90a56-141">L' `autoflush` attributo è impostato su `true` , che fa sì che il listener di traccia scriva nel file, indipendentemente dal fatto che il <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> metodo venga chiamato.</span><span class="sxs-lookup"><span data-stu-id="90a56-141">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="90a56-142">L' `indentsize` attributo è impostato su 0 (zero), che fa sì che il listener rientri zero spazi quando <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="90a56-142">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="90a56-143">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="90a56-143">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="90a56-144">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="90a56-144">Trace and Debug Settings Schema</span></span>](index.md)
