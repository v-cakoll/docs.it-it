---
title: '&lt;filtro&gt; (elemento) per &lt;aggiungere&gt; per &lt;listener&gt; per &lt;origine&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 044d446b97f0899b9575085a15c3faa399ce776e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624613"
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="4aa8f-102">&lt;filtro&gt; (elemento) per &lt;aggiungere&gt; per &lt;listener&gt; per &lt;origine&gt;</span><span class="sxs-lookup"><span data-stu-id="4aa8f-102">&lt;filter&gt; Element for &lt;add&gt; for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="4aa8f-103">Aggiunge un filtro a un listener nella raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="4aa8f-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="4aa8f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4aa8f-104">\<configuration></span></span>  
<span data-ttu-id="4aa8f-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="4aa8f-105">\<system.diagnostics></span></span>  
<span data-ttu-id="4aa8f-106">\<sources></span><span class="sxs-lookup"><span data-stu-id="4aa8f-106">\<sources></span></span>  
<span data-ttu-id="4aa8f-107">\<origine ></span><span class="sxs-lookup"><span data-stu-id="4aa8f-107">\<source></span></span>  
<span data-ttu-id="4aa8f-108">\<listeners></span><span class="sxs-lookup"><span data-stu-id="4aa8f-108">\<listeners></span></span>  
<span data-ttu-id="4aa8f-109">\<add></span><span class="sxs-lookup"><span data-stu-id="4aa8f-109">\<add></span></span>  
<span data-ttu-id="4aa8f-110">\<filter></span><span class="sxs-lookup"><span data-stu-id="4aa8f-110">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4aa8f-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4aa8f-111">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4aa8f-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4aa8f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4aa8f-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4aa8f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4aa8f-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="4aa8f-114">Attributes</span></span>  
  
|<span data-ttu-id="4aa8f-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="4aa8f-115">Attribute</span></span>|<span data-ttu-id="4aa8f-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4aa8f-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="4aa8f-117">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4aa8f-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="4aa8f-118">Specifica il tipo di filtro, che deve ereditare il <xref:System.Diagnostics.TraceFilter> classe.</span><span class="sxs-lookup"><span data-stu-id="4aa8f-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="4aa8f-119">È possibile usare il nome completo dello spazio dei nomi del tipo, che corrisponde al tipo <xref:System.Type.FullName%2A> proprietà, oppure è possibile usare il nome completo del tipo tra cui le informazioni sull'assembly, che corrisponde alla <xref:System.Type.AssemblyQualifiedName%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="4aa8f-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="4aa8f-120">Per informazioni sui nomi di tipo completo, vedere [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="4aa8f-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="4aa8f-121">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4aa8f-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4aa8f-122">La stringa passata al costruttore della classe di filtro specificato.</span><span class="sxs-lookup"><span data-stu-id="4aa8f-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4aa8f-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4aa8f-123">Child Elements</span></span>  
 <span data-ttu-id="4aa8f-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4aa8f-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4aa8f-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4aa8f-125">Parent Elements</span></span>  
  
|<span data-ttu-id="4aa8f-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="4aa8f-126">Element</span></span>|<span data-ttu-id="4aa8f-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4aa8f-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4aa8f-128">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4aa8f-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="4aa8f-129">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="4aa8f-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="4aa8f-130">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="4aa8f-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="4aa8f-131">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="4aa8f-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="4aa8f-132">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="4aa8f-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="4aa8f-133">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="4aa8f-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="4aa8f-134">Aggiunge un listener alla raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="4aa8f-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4aa8f-135">Note</span><span class="sxs-lookup"><span data-stu-id="4aa8f-135">Remarks</span></span>  
 <span data-ttu-id="4aa8f-136">Il `<filter>` elemento deve essere contenuto in un `<add>` (elemento) per un listener di origine di traccia che specifica il tipo del listener, non solo il nome di un listener definiti in un [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="4aa8f-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span></span> <span data-ttu-id="4aa8f-137">Se il listener è definito in un [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), il filtro per il listener deve essere definito in tale elemento.</span><span class="sxs-lookup"><span data-stu-id="4aa8f-137">If the listener is defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="4aa8f-138">Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4aa8f-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4aa8f-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="4aa8f-139">Example</span></span>  
 <span data-ttu-id="4aa8f-140">Nell'esempio seguente viene illustrato come utilizzare il `<filter>` elemento per aggiungere un filtro per il listener `console` nel `Listeners` insieme per l'origine di traccia `myTraceSource`, che specifica il livello di evento di filtro come `Error`.</span><span class="sxs-lookup"><span data-stu-id="4aa8f-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" switchName="SourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="SourceSwitch" value="Warning" />  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4aa8f-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4aa8f-141">See also</span></span>
- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="4aa8f-142">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="4aa8f-142">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
