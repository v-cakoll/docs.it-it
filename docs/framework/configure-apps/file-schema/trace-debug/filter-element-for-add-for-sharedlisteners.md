---
title: Elemento <filter> per <add> per <sharedListeners>
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
ms.openlocfilehash: e04ecd773bd6aa7791858711edbd72128dc391ea
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088874"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a><span data-ttu-id="8150f-102">\<elemento > Filter per \<Aggiungi > per \<sharedListeners ></span><span class="sxs-lookup"><span data-stu-id="8150f-102">\<filter> Element for \<add> for \<sharedListeners></span></span>
<span data-ttu-id="8150f-103">Aggiunge un filtro a un listener nella raccolta `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="8150f-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  

<span data-ttu-id="8150f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8150f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8150f-105">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="8150f-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="8150f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sharedListeners**](sharedlisteners-element.md) ></span><span class="sxs-lookup"><span data-stu-id="8150f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)</span></span>\
<span data-ttu-id="8150f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**aggiungi >** ](add-element-for-sharedlisteners.md)</span><span class="sxs-lookup"><span data-stu-id="8150f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-sharedlisteners.md)</span></span>\
<span data-ttu-id="8150f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**filtro** ></span><span class="sxs-lookup"><span data-stu-id="8150f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8150f-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8150f-109">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8150f-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8150f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8150f-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8150f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8150f-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="8150f-112">Attributes</span></span>  
  
|<span data-ttu-id="8150f-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="8150f-113">Attribute</span></span>|<span data-ttu-id="8150f-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8150f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8150f-115">**type**</span><span class="sxs-lookup"><span data-stu-id="8150f-115">**type**</span></span>|<span data-ttu-id="8150f-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8150f-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="8150f-117">Specifica il tipo di filtro.</span><span class="sxs-lookup"><span data-stu-id="8150f-117">Specifies the type of the filter.</span></span> <span data-ttu-id="8150f-118">È possibile utilizzare solo il nome completo del tipo (nel formato della proprietà <xref:System.Type.FullName%2A?displayProperty=nameWithType>) oppure è possibile utilizzare il nome completo del tipo, incluse le informazioni sull'assembly, nel formato della proprietà <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8150f-118">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="8150f-119">Per informazioni sulla creazione di un nome di tipo completo, vedere [specifica di nomi di tipo](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)completi.</span><span class="sxs-lookup"><span data-stu-id="8150f-119">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="8150f-120">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="8150f-120">**initializeData**</span></span>|<span data-ttu-id="8150f-121">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8150f-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="8150f-122">Stringa passata al costruttore per la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="8150f-122">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8150f-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8150f-123">Child Elements</span></span>  
 <span data-ttu-id="8150f-124">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="8150f-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8150f-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8150f-125">Parent Elements</span></span>  
  
|<span data-ttu-id="8150f-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="8150f-126">Element</span></span>|<span data-ttu-id="8150f-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8150f-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8150f-128">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8150f-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="8150f-129">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="8150f-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="8150f-130">Raccolta di listener a cui qualsiasi origine o elemento Trace può fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="8150f-130">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="8150f-131">Aggiunge un listener alla raccolta **sharedListeners** .</span><span class="sxs-lookup"><span data-stu-id="8150f-131">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8150f-132">Note</span><span class="sxs-lookup"><span data-stu-id="8150f-132">Remarks</span></span>  
 <span data-ttu-id="8150f-133">Se un listener viene definito in un elemento `<add>` dell'elemento `<sharedListeners>`, il filtro per il listener deve essere definito in un elemento `<filter>` figlio dell'elemento `<add>`.</span><span class="sxs-lookup"><span data-stu-id="8150f-133">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="8150f-134">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8150f-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8150f-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="8150f-135">Example</span></span>  
 <span data-ttu-id="8150f-136">Nell'esempio seguente viene illustrato come utilizzare l'elemento `<filter>` per aggiungere un filtro al listener di traccia `console` nella raccolta `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="8150f-136">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8150f-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8150f-137">See also</span></span>

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="8150f-138">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="8150f-138">Trace and Debug Settings Schema</span></span>](index.md)
