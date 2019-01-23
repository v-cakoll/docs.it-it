---
title: '&lt;filtro&gt; (elemento) per &lt;aggiungere&gt; per &lt;listener&gt; per &lt;traccia&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 85d81beead84be48730ba3a4469e8efdff1bbb0b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523691"
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="2a6bd-102">&lt;filtro&gt; (elemento) per &lt;aggiungere&gt; per &lt;listener&gt; per &lt;traccia&gt;</span><span class="sxs-lookup"><span data-stu-id="2a6bd-102">&lt;filter&gt; Element for &lt;add&gt; for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="2a6bd-103">Aggiunge un filtro a un listener di `Listeners` raccolta per una traccia.</span><span class="sxs-lookup"><span data-stu-id="2a6bd-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  
  
 <span data-ttu-id="2a6bd-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2a6bd-104">\<configuration></span></span>  
<span data-ttu-id="2a6bd-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="2a6bd-105">\<system.diagnostics></span></span>  
<span data-ttu-id="2a6bd-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="2a6bd-106">\<trace></span></span>  
<span data-ttu-id="2a6bd-107">\<listeners></span><span class="sxs-lookup"><span data-stu-id="2a6bd-107">\<listeners></span></span>  
<span data-ttu-id="2a6bd-108">\<add></span><span class="sxs-lookup"><span data-stu-id="2a6bd-108">\<add></span></span>  
<span data-ttu-id="2a6bd-109">\<filter></span><span class="sxs-lookup"><span data-stu-id="2a6bd-109">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a6bd-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2a6bd-110">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a6bd-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2a6bd-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2a6bd-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2a6bd-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a6bd-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="2a6bd-113">Attributes</span></span>  
  
|<span data-ttu-id="2a6bd-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="2a6bd-114">Attribute</span></span>|<span data-ttu-id="2a6bd-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a6bd-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="2a6bd-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2a6bd-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="2a6bd-117">Specifica il tipo di filtro, che deve ereditare il <xref:System.Diagnostics.TraceFilter> classe.</span><span class="sxs-lookup"><span data-stu-id="2a6bd-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="2a6bd-118">È possibile usare il nome completo dello spazio dei nomi del tipo, che corrisponde al tipo <xref:System.Type.FullName%2A> proprietà, oppure è possibile usare il nome completo del tipo tra cui le informazioni sull'assembly, che corrisponde alla <xref:System.Type.AssemblyQualifiedName%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="2a6bd-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="2a6bd-119">Per informazioni sui nomi di tipo completo, vedere [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="2a6bd-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="2a6bd-120">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2a6bd-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2a6bd-121">La stringa passata al costruttore della classe di filtro specificato.</span><span class="sxs-lookup"><span data-stu-id="2a6bd-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a6bd-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2a6bd-122">Child Elements</span></span>  
 <span data-ttu-id="2a6bd-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2a6bd-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2a6bd-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2a6bd-124">Parent Elements</span></span>  
  
|<span data-ttu-id="2a6bd-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="2a6bd-125">Element</span></span>|<span data-ttu-id="2a6bd-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a6bd-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2a6bd-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2a6bd-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="2a6bd-128">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="2a6bd-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="2a6bd-129">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="2a6bd-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="2a6bd-130">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="2a6bd-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="2a6bd-131">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="2a6bd-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="2a6bd-132">Aggiunge un listener alla raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="2a6bd-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a6bd-133">Note</span><span class="sxs-lookup"><span data-stu-id="2a6bd-133">Remarks</span></span>  
 <span data-ttu-id="2a6bd-134">Il `<filter>` elemento deve essere contenuto in un `<add>` (elemento) per un listener di traccia che specifica il tipo del listener, non solo il nome di un listener definiti in un [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="2a6bd-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span></span> <span data-ttu-id="2a6bd-135">Se il listener è definito in un [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), il filtro per il listener deve essere definito in tale elemento.</span><span class="sxs-lookup"><span data-stu-id="2a6bd-135">If the listener is defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="2a6bd-136">Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2a6bd-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a6bd-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="2a6bd-137">Example</span></span>  
 <span data-ttu-id="2a6bd-138">Nell'esempio seguente viene illustrato come utilizzare il `<filter>` elemento per aggiungere un filtro per il listener `console` nel `Listeners` insieme per l'analisi, che specifica il livello di evento di filtro come `Error`.</span><span class="sxs-lookup"><span data-stu-id="2a6bd-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2a6bd-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a6bd-139">See also</span></span>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="2a6bd-140">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="2a6bd-140">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
