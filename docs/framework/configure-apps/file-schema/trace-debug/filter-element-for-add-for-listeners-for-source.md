---
title: <filter>Elemento <add> per <listeners> for<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 0cb668782de263d5f784691f46cb8b74541d942b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153516"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="e2c36-102">\<filter> \<Element per \<aggiungere> \<per i listener> per l'origine></span><span class="sxs-lookup"><span data-stu-id="e2c36-102">\<filter> Element for \<add> for \<listeners> for \<source></span></span>
<span data-ttu-id="e2c36-103">Aggiunge un filtro a un listener nella raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="e2c36-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="e2c36-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e2c36-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e2c36-105">&nbsp;&nbsp;[**\<>system.diagnostics**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="e2c36-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="e2c36-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<fonti>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="e2c36-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="e2c36-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="e2c36-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="e2c36-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di ascoltatori**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="e2c36-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="e2c36-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<aggiungere>**](add-element-for-listeners-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="e2c36-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-source.md)</span></span>\
<span data-ttu-id="e2c36-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>di filtro**</span><span class="sxs-lookup"><span data-stu-id="e2c36-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e2c36-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2c36-111">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2c36-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e2c36-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e2c36-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e2c36-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2c36-114">Attributes</span><span class="sxs-lookup"><span data-stu-id="e2c36-114">Attributes</span></span>  
  
|<span data-ttu-id="e2c36-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="e2c36-115">Attribute</span></span>|<span data-ttu-id="e2c36-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2c36-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="e2c36-117">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e2c36-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="e2c36-118">Specifica il tipo di filtro, che <xref:System.Diagnostics.TraceFilter> deve ereditare dalla classe .</span><span class="sxs-lookup"><span data-stu-id="e2c36-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="e2c36-119">È possibile utilizzare il nome completo dello spazio dei nomi <xref:System.Type.FullName%2A> del tipo, che corrisponde alla proprietà del tipo, oppure è possibile utilizzare il nome completo del tipo, incluse le informazioni sull'assembly, che corrisponde alla <xref:System.Type.AssemblyQualifiedName%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="e2c36-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="e2c36-120">Per informazioni sui nomi di tipo completi, vedere [Specifica dei nomi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)di tipo completi .</span><span class="sxs-lookup"><span data-stu-id="e2c36-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="e2c36-121">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e2c36-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e2c36-122">Stringa passata al costruttore per la classe di filtro specificata.</span><span class="sxs-lookup"><span data-stu-id="e2c36-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2c36-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e2c36-123">Child Elements</span></span>  
 <span data-ttu-id="e2c36-124">No.</span><span class="sxs-lookup"><span data-stu-id="e2c36-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2c36-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e2c36-125">Parent Elements</span></span>  
  
|<span data-ttu-id="e2c36-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="e2c36-126">Element</span></span>|<span data-ttu-id="e2c36-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2c36-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e2c36-128">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e2c36-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="e2c36-129">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="e2c36-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="e2c36-130">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="e2c36-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="e2c36-131">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="e2c36-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="e2c36-132">Contiene i listener che raccolgono, archiviano e instradano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="e2c36-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="e2c36-133">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="e2c36-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="e2c36-134">Aggiunge un listener alla raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="e2c36-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2c36-135">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e2c36-135">Remarks</span></span>  
 <span data-ttu-id="e2c36-136">L'elemento `<filter>` deve essere `<add>` contenuto in un elemento per un listener dell'origine di traccia che specifica il tipo del listener, non solo il nome di un listener definito in un [ \<oggetto sharedListeners>](sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="e2c36-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="e2c36-137">Se il listener è definito in un [ \<oggetto sharedListeners>](sharedlisteners-element.md), il filtro per tale listener deve essere definito in tale elemento.</span><span class="sxs-lookup"><span data-stu-id="e2c36-137">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="e2c36-138">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine.config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2c36-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2c36-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="e2c36-139">Example</span></span>  
 <span data-ttu-id="e2c36-140">Nell'esempio riportato di `<filter>` seguito viene illustrato come `console` utilizzare `Listeners` l'elemento `myTraceSource`per aggiungere un filtro `Error`al listener nell'insieme per l'origine di traccia , specificando il livello di evento del filtro come .</span><span class="sxs-lookup"><span data-stu-id="e2c36-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e2c36-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2c36-141">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="e2c36-142">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="e2c36-142">Trace and Debug Settings Schema</span></span>](index.md)
