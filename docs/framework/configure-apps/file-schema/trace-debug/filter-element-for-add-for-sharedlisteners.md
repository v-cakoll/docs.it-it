---
title: '&lt;filtro&gt; (elemento) per &lt;aggiungere&gt; per &lt;sharedListeners&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 5172a2be163e178b9c7115825fa5dba4ff073a96
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47115139"
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltsharedlistenersgt"></a><span data-ttu-id="fdc73-102">&lt;filtro&gt; (elemento) per &lt;aggiungere&gt; per &lt;sharedListeners&gt;</span><span class="sxs-lookup"><span data-stu-id="fdc73-102">&lt;filter&gt; Element for &lt;add&gt; for &lt;sharedListeners&gt;</span></span>
<span data-ttu-id="fdc73-103">Aggiunge un filtro a un listener nella raccolta `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="fdc73-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  
  
 <span data-ttu-id="fdc73-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fdc73-104">\<configuration></span></span>  
<span data-ttu-id="fdc73-105">\<System. Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="fdc73-105">\<system.diagnostics></span></span>  
<span data-ttu-id="fdc73-106">\<sharedListeners > elemento</span><span class="sxs-lookup"><span data-stu-id="fdc73-106">\<sharedListeners> Element</span></span>  
<span data-ttu-id="fdc73-107">\<add></span><span class="sxs-lookup"><span data-stu-id="fdc73-107">\<add></span></span>  
<span data-ttu-id="fdc73-108">\<Filtro ></span><span class="sxs-lookup"><span data-stu-id="fdc73-108">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdc73-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fdc73-109">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fdc73-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fdc73-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fdc73-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fdc73-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fdc73-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="fdc73-112">Attributes</span></span>  
  
|<span data-ttu-id="fdc73-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="fdc73-113">Attribute</span></span>|<span data-ttu-id="fdc73-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fdc73-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fdc73-115">**type**</span><span class="sxs-lookup"><span data-stu-id="fdc73-115">**type**</span></span>|<span data-ttu-id="fdc73-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fdc73-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="fdc73-117">Specifica il tipo del filtro.</span><span class="sxs-lookup"><span data-stu-id="fdc73-117">Specifies the type of the filter.</span></span> <span data-ttu-id="fdc73-118">È possibile usare solo il nome completo del tipo (nel formato il <xref:System.Type.FullName%2A?displayProperty=nameWithType> proprietà), oppure è possibile usare il nome completo del tipo tra cui le informazioni sull'assembly (nel formato di <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> proprietà).</span><span class="sxs-lookup"><span data-stu-id="fdc73-118">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="fdc73-119">Per informazioni sulla creazione di un nome completo del tipo, vedere [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="fdc73-119">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="fdc73-120">**attributo initializeData**</span><span class="sxs-lookup"><span data-stu-id="fdc73-120">**initializeData**</span></span>|<span data-ttu-id="fdc73-121">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fdc73-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="fdc73-122">La stringa passata al costruttore per la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="fdc73-122">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fdc73-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fdc73-123">Child Elements</span></span>  
 <span data-ttu-id="fdc73-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="fdc73-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fdc73-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fdc73-125">Parent Elements</span></span>  
  
|<span data-ttu-id="fdc73-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="fdc73-126">Element</span></span>|<span data-ttu-id="fdc73-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fdc73-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fdc73-128">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fdc73-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="fdc73-129">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="fdc73-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="fdc73-130">Raccolta di listener che possono fare riferimento qualsiasi origine o un elemento di traccia.</span><span class="sxs-lookup"><span data-stu-id="fdc73-130">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="fdc73-131">Aggiunge un listener per il **sharedListeners** raccolta.</span><span class="sxs-lookup"><span data-stu-id="fdc73-131">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdc73-132">Note</span><span class="sxs-lookup"><span data-stu-id="fdc73-132">Remarks</span></span>  
 <span data-ttu-id="fdc73-133">Se viene definito un listener in un `<add>` elemento del `<sharedListeners>` elemento, il filtro per il listener deve essere definito un `<filter>` elemento figlio del `<add>` elemento.</span><span class="sxs-lookup"><span data-stu-id="fdc73-133">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="fdc73-134">Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fdc73-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdc73-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="fdc73-135">Example</span></span>  
 <span data-ttu-id="fdc73-136">Nell'esempio seguente viene illustrato come utilizzare il `<filter>` elemento per aggiungere un filtro per il listener di traccia `console` nel `sharedListeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="fdc73-136">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"   
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"   
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fdc73-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fdc73-137">See Also</span></span>  
 <xref:System.Diagnostics.TraceFilter>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.TraceSource>  
 [<span data-ttu-id="fdc73-138">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="fdc73-138">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
