---
title: <filter>Elemento per <add> <listeners> per per<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: afde5381a7dd7dfe6a1a9d238a2029511bd9bae2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927141"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="219e0-102">\<Filtra > elemento per \<Aggiungi > per \<i listener > per \<la traccia ></span><span class="sxs-lookup"><span data-stu-id="219e0-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="219e0-103">Aggiunge un filtro a un listener nella `Listeners` raccolta per una traccia.</span><span class="sxs-lookup"><span data-stu-id="219e0-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  
  
 <span data-ttu-id="219e0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="219e0-104">\<configuration></span></span>  
<span data-ttu-id="219e0-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="219e0-105">\<system.diagnostics></span></span>  
<span data-ttu-id="219e0-106">\<traccia ></span><span class="sxs-lookup"><span data-stu-id="219e0-106">\<trace></span></span>  
<span data-ttu-id="219e0-107">\<listener ></span><span class="sxs-lookup"><span data-stu-id="219e0-107">\<listeners></span></span>  
<span data-ttu-id="219e0-108">\<add></span><span class="sxs-lookup"><span data-stu-id="219e0-108">\<add></span></span>  
<span data-ttu-id="219e0-109">\<Filtra ></span><span class="sxs-lookup"><span data-stu-id="219e0-109">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="219e0-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="219e0-110">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="219e0-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="219e0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="219e0-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="219e0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="219e0-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="219e0-113">Attributes</span></span>  
  
|<span data-ttu-id="219e0-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="219e0-114">Attribute</span></span>|<span data-ttu-id="219e0-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="219e0-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="219e0-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="219e0-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="219e0-117">Specifica il tipo di filtro che deve ereditare dalla <xref:System.Diagnostics.TraceFilter> classe.</span><span class="sxs-lookup"><span data-stu-id="219e0-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="219e0-118">È possibile utilizzare il nome completo dello spazio dei nomi del tipo, che corrisponde alla <xref:System.Type.FullName%2A> proprietà del tipo, oppure è possibile utilizzare il nome completo del tipo, incluse le informazioni sull'assembly, che corrisponde <xref:System.Type.AssemblyQualifiedName%2A> alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="219e0-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="219e0-119">Per informazioni sui nomi di tipo completi, vedere [specifica di nomi di tipo](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)completi.</span><span class="sxs-lookup"><span data-stu-id="219e0-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="219e0-120">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="219e0-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="219e0-121">Stringa passata al costruttore per la classe di filtro specificata.</span><span class="sxs-lookup"><span data-stu-id="219e0-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="219e0-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="219e0-122">Child Elements</span></span>  
 <span data-ttu-id="219e0-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="219e0-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="219e0-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="219e0-124">Parent Elements</span></span>  
  
|<span data-ttu-id="219e0-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="219e0-125">Element</span></span>|<span data-ttu-id="219e0-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="219e0-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="219e0-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="219e0-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="219e0-128">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="219e0-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="219e0-129">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="219e0-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="219e0-130">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="219e0-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="219e0-131">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="219e0-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="219e0-132">Aggiunge un listener alla raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="219e0-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="219e0-133">Note</span><span class="sxs-lookup"><span data-stu-id="219e0-133">Remarks</span></span>  
 <span data-ttu-id="219e0-134">L' `<filter>` elemento deve essere contenuto in un `<add>` elemento per un listener di traccia che specifica il tipo del listener, non solo il nome di un listener definito in un [ \<> sharedListeners](sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="219e0-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="219e0-135">Se il listener è definito in una [ \<> sharedListeners](sharedlisteners-element.md), il filtro per il listener deve essere definito in tale elemento.</span><span class="sxs-lookup"><span data-stu-id="219e0-135">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="219e0-136">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="219e0-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="219e0-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="219e0-137">Example</span></span>  
 <span data-ttu-id="219e0-138">Nell'esempio seguente viene illustrato come utilizzare l' `<filter>` elemento per aggiungere un filtro al listener `console` nella `Listeners` raccolta per la traccia, specificando il livello dell'evento Filter `Error`come.</span><span class="sxs-lookup"><span data-stu-id="219e0-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="219e0-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="219e0-139">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="219e0-140">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="219e0-140">Trace and Debug Settings Schema</span></span>](index.md)
