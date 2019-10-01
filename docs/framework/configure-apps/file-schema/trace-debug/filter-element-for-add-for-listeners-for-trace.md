---
title: Elemento <filter> per <add> per <listeners> per <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: f6b1ec99c5aab8e85df7f1920aca32f49a5be066
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699369"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="1c945-102">Elemento > \<filter per \<ADD > per @no__t > 2listeners per \<trace ></span><span class="sxs-lookup"><span data-stu-id="1c945-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="1c945-103">Aggiunge un filtro a un listener nella raccolta `Listeners` per una traccia.</span><span class="sxs-lookup"><span data-stu-id="1c945-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  
  
[<span data-ttu-id="1c945-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="1c945-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="1c945-105">&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="1c945-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="1c945-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<trace >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="1c945-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>  
<span data-ttu-id="1c945-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<listeners >** ](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="1c945-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>  
<span data-ttu-id="1c945-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0Add >** ](add-element-for-listeners-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="1c945-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-trace.md)</span></span>  
<span data-ttu-id="1c945-109">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 @ no__t-8 @ no__t-9 **&nbsp;1filter >**</span><span class="sxs-lookup"><span data-stu-id="1c945-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c945-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c945-110">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c945-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1c945-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1c945-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1c945-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c945-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="1c945-113">Attributes</span></span>  
  
|<span data-ttu-id="1c945-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="1c945-114">Attribute</span></span>|<span data-ttu-id="1c945-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c945-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="1c945-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1c945-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="1c945-117">Specifica il tipo di filtro che deve ereditare dalla classe <xref:System.Diagnostics.TraceFilter>.</span><span class="sxs-lookup"><span data-stu-id="1c945-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="1c945-118">È possibile utilizzare il nome completo dello spazio dei nomi del tipo, che corrisponde alla proprietà <xref:System.Type.FullName%2A> del tipo, oppure è possibile utilizzare il nome completo del tipo, incluse le informazioni sull'assembly, che corrisponde alla proprietà <xref:System.Type.AssemblyQualifiedName%2A>.</span><span class="sxs-lookup"><span data-stu-id="1c945-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="1c945-119">Per informazioni sui nomi di tipo completi, vedere [specifica di nomi di tipo](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)completi.</span><span class="sxs-lookup"><span data-stu-id="1c945-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="1c945-120">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1c945-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="1c945-121">Stringa passata al costruttore per la classe di filtro specificata.</span><span class="sxs-lookup"><span data-stu-id="1c945-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c945-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1c945-122">Child Elements</span></span>  
 <span data-ttu-id="1c945-123">No.</span><span class="sxs-lookup"><span data-stu-id="1c945-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1c945-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1c945-124">Parent Elements</span></span>  
  
|<span data-ttu-id="1c945-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="1c945-125">Element</span></span>|<span data-ttu-id="1c945-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c945-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1c945-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1c945-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="1c945-128">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="1c945-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="1c945-129">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="1c945-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="1c945-130">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="1c945-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="1c945-131">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="1c945-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="1c945-132">Aggiunge un listener alla raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="1c945-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c945-133">Note</span><span class="sxs-lookup"><span data-stu-id="1c945-133">Remarks</span></span>  
 <span data-ttu-id="1c945-134">L'elemento `<filter>` deve essere contenuto in un elemento `<add>` per un listener di traccia che specifica il tipo del listener, non solo il nome di un listener definito in una [> \<sharedListeners](sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="1c945-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="1c945-135">Se il listener è definito in una [> \<sharedListeners](sharedlisteners-element.md), il filtro per il listener deve essere definito in tale elemento.</span><span class="sxs-lookup"><span data-stu-id="1c945-135">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="1c945-136">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1c945-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c945-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="1c945-137">Example</span></span>  
 <span data-ttu-id="1c945-138">Nell'esempio seguente viene illustrato come utilizzare l'elemento `<filter>` per aggiungere un filtro al listener `console` nella raccolta `Listeners` per Trace, specificando il livello di evento Filter come `Error`.</span><span class="sxs-lookup"><span data-stu-id="1c945-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
        <remove name="Default" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1c945-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c945-139">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="1c945-140">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="1c945-140">Trace and Debug Settings Schema</span></span>](index.md)
