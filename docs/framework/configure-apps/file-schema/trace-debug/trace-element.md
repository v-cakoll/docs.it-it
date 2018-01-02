---
title: '&lt;traccia&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d7ddcbdbdbbc2924d4f725d2fd401f873a4cfb0b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="lttracegt-element"></a><span data-ttu-id="51466-102">&lt;traccia&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="51466-102">&lt;trace&gt; Element</span></span>
<span data-ttu-id="51466-103">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="51466-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
 <span data-ttu-id="51466-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="51466-104">\<configuration></span></span>  
<span data-ttu-id="51466-105">\<System. Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="51466-105">\<system.diagnostics></span></span>  
<span data-ttu-id="51466-106">\<traccia ></span><span class="sxs-lookup"><span data-stu-id="51466-106">\<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51466-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51466-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51466-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="51466-108">Attributes and Elements</span></span>  
 <span data-ttu-id="51466-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="51466-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51466-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="51466-110">Attributes</span></span>  
  
|<span data-ttu-id="51466-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="51466-111">Attribute</span></span>|<span data-ttu-id="51466-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51466-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="51466-113">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="51466-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="51466-114">Indica se la traccia automaticamente svuotano il buffer di output dopo ogni operazione di scrittura.</span><span class="sxs-lookup"><span data-stu-id="51466-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="51466-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="51466-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="51466-116">Specifica il numero di spazi per il rientro.</span><span class="sxs-lookup"><span data-stu-id="51466-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="51466-117">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="51466-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="51466-118">Indica se il blocco globale deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="51466-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="51466-119">Attributo AutoFlush</span><span class="sxs-lookup"><span data-stu-id="51466-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="51466-120">Valore</span><span class="sxs-lookup"><span data-stu-id="51466-120">Value</span></span>|<span data-ttu-id="51466-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51466-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="51466-122">Non scaricare automaticamente il buffer di output.</span><span class="sxs-lookup"><span data-stu-id="51466-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="51466-123">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="51466-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="51466-124">Scarica automaticamente il buffer di output.</span><span class="sxs-lookup"><span data-stu-id="51466-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="51466-125">Attributo useGlobalLock</span><span class="sxs-lookup"><span data-stu-id="51466-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="51466-126">Valore</span><span class="sxs-lookup"><span data-stu-id="51466-126">Value</span></span>|<span data-ttu-id="51466-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51466-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="51466-128">Non utilizzare il blocco globale se il listener è thread-safe. in caso contrario, viene utilizzato il blocco globale.</span><span class="sxs-lookup"><span data-stu-id="51466-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="51466-129">Utilizza il blocco globale indipendentemente dal fatto che il listener sia thread-safe.</span><span class="sxs-lookup"><span data-stu-id="51466-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="51466-130">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="51466-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="51466-131">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="51466-131">Child Elements</span></span>  
  
|<span data-ttu-id="51466-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="51466-132">Element</span></span>|<span data-ttu-id="51466-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51466-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51466-134">\<listeners></span><span class="sxs-lookup"><span data-stu-id="51466-134">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|<span data-ttu-id="51466-135">Specifica un listener per la raccolta, la memorizzazione e indirizza i messaggi.</span><span class="sxs-lookup"><span data-stu-id="51466-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="51466-136">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="51466-136">Parent Elements</span></span>  
  
|<span data-ttu-id="51466-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="51466-137">Element</span></span>|<span data-ttu-id="51466-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51466-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="51466-139">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="51466-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="51466-140">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="51466-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="51466-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="51466-141">Example</span></span>  
 <span data-ttu-id="51466-142">Nell'esempio seguente viene illustrato come utilizzare il `<trace>` elemento per aggiungere il listener `MyListener` per il `Listeners` insieme.</span><span class="sxs-lookup"><span data-stu-id="51466-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="51466-143">`MyListener`Crea un file denominato `MyListener.log` e scrive l'output del file.</span><span class="sxs-lookup"><span data-stu-id="51466-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="51466-144">Il `useGlobalLock` attributo è impostato su `false`, che comporta il blocco globale non deve essere utilizzata se il listener di traccia è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="51466-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="51466-145">Il `autoflush` attributo è impostato su `true`, causando il listener di traccia da scrivere nel file indipendentemente dal fatto che il <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> metodo viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="51466-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="51466-146">Il `indentsize` attributo è impostato su 0 (zero), che fa sì che il listener per il rientro quando il <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> metodo viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="51466-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="51466-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51466-147">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 [<span data-ttu-id="51466-148">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="51466-148">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
