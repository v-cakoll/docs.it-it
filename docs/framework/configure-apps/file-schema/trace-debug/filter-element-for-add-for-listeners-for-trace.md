---
title: <filter>Elemento <add> per <listeners> for<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: b6c2c2bf7fe953a75f9d8129039ef33b4d8a3f56
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153466"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="81775-102">\<filter> \<Element for \<add>s for listeners> for \<trace></span><span class="sxs-lookup"><span data-stu-id="81775-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="81775-103">Aggiunge un filtro a `Listeners` un listener nella raccolta per una traccia.</span><span class="sxs-lookup"><span data-stu-id="81775-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  

<span data-ttu-id="81775-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="81775-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="81775-105">&nbsp;&nbsp;[**\<>system.diagnostics**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="81775-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="81775-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>traccia**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="81775-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="81775-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di ascoltatori**](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="81775-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="81775-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<aggiungere>**](add-element-for-listeners-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="81775-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-trace.md)</span></span>\
<span data-ttu-id="81775-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>di filtro**</span><span class="sxs-lookup"><span data-stu-id="81775-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="81775-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="81775-110">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81775-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="81775-111">Attributes and Elements</span></span>  
 <span data-ttu-id="81775-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="81775-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81775-113">Attributes</span><span class="sxs-lookup"><span data-stu-id="81775-113">Attributes</span></span>  
  
|<span data-ttu-id="81775-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="81775-114">Attribute</span></span>|<span data-ttu-id="81775-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81775-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="81775-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="81775-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="81775-117">Specifica il tipo di filtro, che <xref:System.Diagnostics.TraceFilter> deve ereditare dalla classe .</span><span class="sxs-lookup"><span data-stu-id="81775-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="81775-118">È possibile utilizzare il nome completo dello spazio dei nomi <xref:System.Type.FullName%2A> del tipo, che corrisponde alla proprietà del tipo, oppure è possibile utilizzare il nome completo del tipo, incluse le informazioni sull'assembly, che corrisponde alla <xref:System.Type.AssemblyQualifiedName%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="81775-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="81775-119">Per informazioni sui nomi di tipo completi, vedere [Specifica dei nomi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)di tipo completi .</span><span class="sxs-lookup"><span data-stu-id="81775-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="81775-120">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="81775-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="81775-121">Stringa passata al costruttore per la classe di filtro specificata.</span><span class="sxs-lookup"><span data-stu-id="81775-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81775-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="81775-122">Child Elements</span></span>  
 <span data-ttu-id="81775-123">No.</span><span class="sxs-lookup"><span data-stu-id="81775-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="81775-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="81775-124">Parent Elements</span></span>  
  
|<span data-ttu-id="81775-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="81775-125">Element</span></span>|<span data-ttu-id="81775-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81775-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="81775-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="81775-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="81775-128">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="81775-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="81775-129">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="81775-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="81775-130">Contiene i listener che raccolgono, archiviano e instradano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="81775-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="81775-131">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="81775-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="81775-132">Aggiunge un listener alla raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="81775-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81775-133">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="81775-133">Remarks</span></span>  
 <span data-ttu-id="81775-134">L'elemento `<filter>` deve essere `<add>` contenuto in un elemento per un listener di traccia che specifica il tipo del listener, non solo il nome di un listener definito in un [ \<oggetto sharedListeners>](sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="81775-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="81775-135">Se il listener è definito in un [ \<oggetto sharedListeners>](sharedlisteners-element.md), il filtro per tale listener deve essere definito in tale elemento.</span><span class="sxs-lookup"><span data-stu-id="81775-135">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="81775-136">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine.config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="81775-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81775-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="81775-137">Example</span></span>  
 <span data-ttu-id="81775-138">Nell'esempio riportato di `<filter>` seguito viene illustrato come `console` utilizzare `Listeners` l'elemento per aggiungere un `Error`filtro al listener nell'insieme per la traccia, specificando il livello di evento del filtro come .</span><span class="sxs-lookup"><span data-stu-id="81775-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="81775-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81775-139">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="81775-140">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="81775-140">Trace and Debug Settings Schema</span></span>](index.md)
