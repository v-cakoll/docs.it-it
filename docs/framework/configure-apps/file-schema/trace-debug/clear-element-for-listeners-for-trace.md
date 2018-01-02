---
title: '&lt;deselezionare&gt; elemento per &lt;listener&gt; per &lt;traccia&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: b2739cc5eaa6a1e43c06849e1b00f7ac8bd531e7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltcleargt-element-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="c8057-102">&lt;deselezionare&gt; elemento per &lt;listener&gt; per &lt;traccia&gt;</span><span class="sxs-lookup"><span data-stu-id="c8057-102">&lt;clear&gt; Element for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="c8057-103">Cancella la raccolta `Listeners` per una traccia.</span><span class="sxs-lookup"><span data-stu-id="c8057-103">Clears the `Listeners` collection for trace.</span></span>  
  
 <span data-ttu-id="c8057-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c8057-104">\<configuration></span></span>  
<span data-ttu-id="c8057-105">\<System. Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="c8057-105">\<system.diagnostics></span></span>  
<span data-ttu-id="c8057-106">\<traccia ></span><span class="sxs-lookup"><span data-stu-id="c8057-106">\<trace></span></span>  
<span data-ttu-id="c8057-107">\<listener ></span><span class="sxs-lookup"><span data-stu-id="c8057-107">\<listeners></span></span>  
<span data-ttu-id="c8057-108">\<Deselezionare ></span><span class="sxs-lookup"><span data-stu-id="c8057-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8057-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8057-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8057-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c8057-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c8057-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c8057-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8057-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="c8057-112">Attributes</span></span>  
 <span data-ttu-id="c8057-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c8057-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c8057-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c8057-114">Child Elements</span></span>  
 <span data-ttu-id="c8057-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c8057-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c8057-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c8057-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c8057-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="c8057-117">Element</span></span>|<span data-ttu-id="c8057-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8057-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c8057-119">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c8057-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="c8057-120">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="c8057-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="c8057-121">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="c8057-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="c8057-122">Contiene i listener di raccolgano, archiviano e indirizzare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="c8057-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="c8057-123">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="c8057-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8057-124">Note</span><span class="sxs-lookup"><span data-stu-id="c8057-124">Remarks</span></span>  
 <span data-ttu-id="c8057-125">Il `<clear>` elemento rimuove tutti i listener dal `Listeners` insieme per la traccia.</span><span class="sxs-lookup"><span data-stu-id="c8057-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="c8057-126">È possibile utilizzare il `<clear>` elemento prima di utilizzare il `<add>` elemento per essere certi che non sono presenti altri listener attivi nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="c8057-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="c8057-127">È possibile cancellare il `Listeners` insieme a livello di codice chiamando il <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> metodo il <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> proprietà (`System.Diagnostics.Trace.Listeners.Clear()`).</span><span class="sxs-lookup"><span data-stu-id="c8057-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="c8057-128">Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c8057-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8057-129">Il `<clear>` elemento rimuove il <xref:System.Diagnostics.DefaultTraceListener> dal `Listeners` insieme, modifica del comportamento del <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, e <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> metodi.</span><span class="sxs-lookup"><span data-stu-id="c8057-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="c8057-130">La chiamata a un `Assert` o `Fail` metodo in genere comporta la visualizzazione di una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="c8057-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="c8057-131">Tuttavia, la finestra di messaggio non viene visualizzata se il <xref:System.Diagnostics.DefaultTraceListener> non si trova nel `Listeners` insieme.</span><span class="sxs-lookup"><span data-stu-id="c8057-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8057-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="c8057-132">Example</span></span>  
 <span data-ttu-id="c8057-133">Nell'esempio seguente viene illustrato come utilizzare il `<clear>` elemento prima di utilizzare il `<add>` elemento per aggiungere il listener `console` per il `Listeners` insieme per la traccia.</span><span class="sxs-lookup"><span data-stu-id="c8057-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="c8057-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8057-134">See Also</span></span>  
 <xref:System.Diagnostics.Trace.Listeners%2A>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 <xref:System.Diagnostics.TraceSource>  
 [<span data-ttu-id="c8057-135">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="c8057-135">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="c8057-136">\<remove></span><span class="sxs-lookup"><span data-stu-id="c8057-136">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)  
 [<span data-ttu-id="c8057-137">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="c8057-137">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
