---
title: <filter>Elemento per <add> per<sharedListeners>
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
ms.openlocfilehash: 571a3add232f3e4f9747040dc104b85e8cc3085e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920505"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a><span data-ttu-id="281d2-102">\<Filtra > elemento per \<Aggiungi > per \<sharedListeners ></span><span class="sxs-lookup"><span data-stu-id="281d2-102">\<filter> Element for \<add> for \<sharedListeners></span></span>
<span data-ttu-id="281d2-103">Aggiunge un filtro a un listener nella raccolta `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="281d2-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  
  
 <span data-ttu-id="281d2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="281d2-104">\<configuration></span></span>  
<span data-ttu-id="281d2-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="281d2-105">\<system.diagnostics></span></span>  
<span data-ttu-id="281d2-106">\<Elemento > sharedListeners</span><span class="sxs-lookup"><span data-stu-id="281d2-106">\<sharedListeners> Element</span></span>  
<span data-ttu-id="281d2-107">\<add></span><span class="sxs-lookup"><span data-stu-id="281d2-107">\<add></span></span>  
<span data-ttu-id="281d2-108">\<Filtra ></span><span class="sxs-lookup"><span data-stu-id="281d2-108">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="281d2-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="281d2-109">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="281d2-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="281d2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="281d2-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="281d2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="281d2-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="281d2-112">Attributes</span></span>  
  
|<span data-ttu-id="281d2-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="281d2-113">Attribute</span></span>|<span data-ttu-id="281d2-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="281d2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="281d2-115">**type**</span><span class="sxs-lookup"><span data-stu-id="281d2-115">**type**</span></span>|<span data-ttu-id="281d2-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="281d2-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="281d2-117">Specifica il tipo di filtro.</span><span class="sxs-lookup"><span data-stu-id="281d2-117">Specifies the type of the filter.</span></span> <span data-ttu-id="281d2-118">È possibile utilizzare solo il nome completo del tipo (nel formato della <xref:System.Type.FullName%2A?displayProperty=nameWithType> proprietà) oppure è possibile utilizzare il nome completo del tipo, incluse le informazioni sull'assembly (nel formato <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> della proprietà).</span><span class="sxs-lookup"><span data-stu-id="281d2-118">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="281d2-119">Per informazioni sulla creazione di un nome di tipo completo, vedere [specifica di nomi di tipo](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)completi.</span><span class="sxs-lookup"><span data-stu-id="281d2-119">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="281d2-120">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="281d2-120">**initializeData**</span></span>|<span data-ttu-id="281d2-121">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="281d2-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="281d2-122">Stringa passata al costruttore per la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="281d2-122">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="281d2-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="281d2-123">Child Elements</span></span>  
 <span data-ttu-id="281d2-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="281d2-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="281d2-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="281d2-125">Parent Elements</span></span>  
  
|<span data-ttu-id="281d2-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="281d2-126">Element</span></span>|<span data-ttu-id="281d2-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="281d2-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="281d2-128">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="281d2-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="281d2-129">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="281d2-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="281d2-130">Raccolta di listener a cui qualsiasi origine o elemento Trace può fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="281d2-130">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="281d2-131">Aggiunge un listener alla raccolta **sharedListeners** .</span><span class="sxs-lookup"><span data-stu-id="281d2-131">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="281d2-132">Note</span><span class="sxs-lookup"><span data-stu-id="281d2-132">Remarks</span></span>  
 <span data-ttu-id="281d2-133">Se un listener viene definito in un `<add>` elemento `<sharedListeners>` dell'elemento, il filtro per il listener deve essere definito in un `<filter>` elemento figlio dell' `<add>` elemento.</span><span class="sxs-lookup"><span data-stu-id="281d2-133">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="281d2-134">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="281d2-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="281d2-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="281d2-135">Example</span></span>  
 <span data-ttu-id="281d2-136">Nell'esempio seguente viene illustrato come utilizzare l' `<filter>` elemento per aggiungere un filtro al listener `console` di traccia nella `sharedListeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="281d2-136">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="281d2-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="281d2-137">See also</span></span>

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="281d2-138">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="281d2-138">Trace and Debug Settings Schema</span></span>](index.md)
