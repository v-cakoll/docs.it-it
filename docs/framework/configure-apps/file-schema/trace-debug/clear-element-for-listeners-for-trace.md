---
title: <clear> Elemento per <listeners> per <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 97b18f9d6baa618b0f535955b232e2119c758b11
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701320"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="cef9c-102">\<Cancella > (elemento) per \<listeners > per \<traccia ></span><span class="sxs-lookup"><span data-stu-id="cef9c-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="cef9c-103">Cancella la raccolta `Listeners` per una traccia.</span><span class="sxs-lookup"><span data-stu-id="cef9c-103">Clears the `Listeners` collection for trace.</span></span>  
  
 <span data-ttu-id="cef9c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cef9c-104">\<configuration></span></span>  
<span data-ttu-id="cef9c-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="cef9c-105">\<system.diagnostics></span></span>  
<span data-ttu-id="cef9c-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="cef9c-106">\<trace></span></span>  
<span data-ttu-id="cef9c-107">\<listeners></span><span class="sxs-lookup"><span data-stu-id="cef9c-107">\<listeners></span></span>  
<span data-ttu-id="cef9c-108">\<clear></span><span class="sxs-lookup"><span data-stu-id="cef9c-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cef9c-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cef9c-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cef9c-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cef9c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cef9c-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cef9c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cef9c-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="cef9c-112">Attributes</span></span>  
 <span data-ttu-id="cef9c-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cef9c-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cef9c-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cef9c-114">Child Elements</span></span>  
 <span data-ttu-id="cef9c-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cef9c-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cef9c-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cef9c-116">Parent Elements</span></span>  
  
|<span data-ttu-id="cef9c-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="cef9c-117">Element</span></span>|<span data-ttu-id="cef9c-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cef9c-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cef9c-119">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cef9c-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="cef9c-120">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="cef9c-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="cef9c-121">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="cef9c-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="cef9c-122">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="cef9c-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="cef9c-123">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="cef9c-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cef9c-124">Note</span><span class="sxs-lookup"><span data-stu-id="cef9c-124">Remarks</span></span>  
 <span data-ttu-id="cef9c-125">Il `<clear>` elemento rimuove tutti i listener dal `Listeners` insieme per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="cef9c-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="cef9c-126">È possibile usare la `<clear>` elemento prima di usare il `<add>` elemento per essere certi che non sono presenti altri listener attivi nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="cef9c-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="cef9c-127">È possibile cancellare il `Listeners` insieme a livello di codice chiamando il <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> metodo sul <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> proprietà (`System.Diagnostics.Trace.Listeners.Clear()`).</span><span class="sxs-lookup"><span data-stu-id="cef9c-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="cef9c-128">Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cef9c-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cef9c-129">Il `<clear>` elemento consente di rimuovere il <xref:System.Diagnostics.DefaultTraceListener> dalle `Listeners` insieme, modifica del comportamento del <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, e <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> metodi.</span><span class="sxs-lookup"><span data-stu-id="cef9c-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="cef9c-130">La chiamata a un `Assert` o `Fail` metodo in genere comporta la visualizzazione di una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="cef9c-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="cef9c-131">Tuttavia, la finestra di messaggio non viene visualizzata se il <xref:System.Diagnostics.DefaultTraceListener> non si trova nel `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="cef9c-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cef9c-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="cef9c-132">Example</span></span>  
 <span data-ttu-id="cef9c-133">Nell'esempio seguente viene illustrato come utilizzare il `<clear>` elemento prima di usare il `<add>` elemento a cui aggiungere il listener `console` per il `Listeners` insieme per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="cef9c-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cef9c-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cef9c-134">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="cef9c-135">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="cef9c-135">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="cef9c-136">\<remove></span><span class="sxs-lookup"><span data-stu-id="cef9c-136">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="cef9c-137">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="cef9c-137">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
