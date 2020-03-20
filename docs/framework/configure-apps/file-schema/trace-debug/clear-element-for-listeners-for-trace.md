---
title: <clear>Elemento <listeners> per<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 905dad8274fede80f4809ff3c7a014049f9df450
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153542"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="97894-102">\<Clear> \<Element per \<i> di listener per i> di traccia</span><span class="sxs-lookup"><span data-stu-id="97894-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="97894-103">Cancella la raccolta `Listeners` per una traccia.</span><span class="sxs-lookup"><span data-stu-id="97894-103">Clears the `Listeners` collection for trace.</span></span>  

<span data-ttu-id="97894-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="97894-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="97894-105">&nbsp;&nbsp;[**\<>system.diagnostics**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="97894-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="97894-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>traccia**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="97894-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="97894-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di ascoltatori**](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="97894-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="97894-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>chiari**</span><span class="sxs-lookup"><span data-stu-id="97894-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="97894-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97894-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97894-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="97894-110">Attributes and Elements</span></span>  
 <span data-ttu-id="97894-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="97894-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97894-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="97894-112">Attributes</span></span>  
 <span data-ttu-id="97894-113">No.</span><span class="sxs-lookup"><span data-stu-id="97894-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="97894-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="97894-114">Child Elements</span></span>  
 <span data-ttu-id="97894-115">No.</span><span class="sxs-lookup"><span data-stu-id="97894-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="97894-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="97894-116">Parent Elements</span></span>  
  
|<span data-ttu-id="97894-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="97894-117">Element</span></span>|<span data-ttu-id="97894-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97894-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="97894-119">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="97894-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="97894-120">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="97894-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="97894-121">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="97894-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="97894-122">Contiene i listener che raccolgono, archiviano e instradano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="97894-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="97894-123">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="97894-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97894-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="97894-124">Remarks</span></span>  
 <span data-ttu-id="97894-125">L'elemento `<clear>` rimuove tutti `Listeners` i listener dalla raccolta per la traccia.</span><span class="sxs-lookup"><span data-stu-id="97894-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="97894-126">È possibile `<clear>` utilizzare l'elemento prima di utilizzare l'elemento `<add>` per essere certi che non siano presenti altri listener attivi nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="97894-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="97894-127">È possibile `Listeners` cancellare l'insieme <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> a <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> livello`System.Diagnostics.Trace.Listeners.Clear()`di codice chiamando il metodo sulla proprietà ( ).</span><span class="sxs-lookup"><span data-stu-id="97894-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="97894-128">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine.config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="97894-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="97894-129">L'elemento `<clear>` <xref:System.Diagnostics.DefaultTraceListener> rimuove `Listeners` l'oggetto dall'insieme, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>alterando il comportamento dei metodi , , <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>e <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="97894-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="97894-130">La `Assert` chiamata `Fail` a un metodo o comporta in genere la visualizzazione di una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="97894-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="97894-131">Tuttavia, la finestra di messaggio <xref:System.Diagnostics.DefaultTraceListener> non viene `Listeners` visualizzata se l'oggetto non è presente nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="97894-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97894-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="97894-132">Example</span></span>  
 <span data-ttu-id="97894-133">Nell'esempio seguente viene `<clear>` illustrato come `<add>` utilizzare l'elemento `console` prima `Listeners` di utilizzare l'elemento per aggiungere il listener alla raccolta per la traccia.</span><span class="sxs-lookup"><span data-stu-id="97894-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="97894-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97894-134">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="97894-135">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="97894-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="97894-136">\<rimuovere></span><span class="sxs-lookup"><span data-stu-id="97894-136">\<remove></span></span>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="97894-137">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="97894-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
