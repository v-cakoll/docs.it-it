---
title: <filter>Elemento per <add> per per <listeners><trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: b6c2c2bf7fe953a75f9d8129039ef33b4d8a3f56
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153466"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="022c5-102">\<filter>Elemento per \<add> per per \<listeners>\<trace></span><span class="sxs-lookup"><span data-stu-id="022c5-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="022c5-103">Aggiunge un filtro a un listener nella `Listeners` raccolta per una traccia.</span><span class="sxs-lookup"><span data-stu-id="022c5-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a><span data-ttu-id="022c5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="022c5-104">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="022c5-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="022c5-105">Attributes and Elements</span></span>  
 <span data-ttu-id="022c5-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="022c5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="022c5-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="022c5-107">Attributes</span></span>  
  
|<span data-ttu-id="022c5-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="022c5-108">Attribute</span></span>|<span data-ttu-id="022c5-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="022c5-109">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="022c5-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="022c5-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="022c5-111">Specifica il tipo di filtro che deve ereditare dalla <xref:System.Diagnostics.TraceFilter> classe.</span><span class="sxs-lookup"><span data-stu-id="022c5-111">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="022c5-112">È possibile utilizzare il nome completo dello spazio dei nomi del tipo, che corrisponde alla proprietà del tipo <xref:System.Type.FullName%2A> , oppure è possibile utilizzare il nome completo del tipo, incluse le informazioni sull'assembly, che corrisponde alla <xref:System.Type.AssemblyQualifiedName%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="022c5-112">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="022c5-113">Per informazioni sui nomi di tipo completi, vedere [specifica di nomi di tipo](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)completi.</span><span class="sxs-lookup"><span data-stu-id="022c5-113">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="022c5-114">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="022c5-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="022c5-115">Stringa passata al costruttore per la classe di filtro specificata.</span><span class="sxs-lookup"><span data-stu-id="022c5-115">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="022c5-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="022c5-116">Child Elements</span></span>  
 <span data-ttu-id="022c5-117">No.</span><span class="sxs-lookup"><span data-stu-id="022c5-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="022c5-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="022c5-118">Parent Elements</span></span>  
  
|<span data-ttu-id="022c5-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="022c5-119">Element</span></span>|<span data-ttu-id="022c5-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="022c5-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="022c5-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="022c5-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="022c5-122">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="022c5-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="022c5-123">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="022c5-123">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="022c5-124">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="022c5-124">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="022c5-125">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="022c5-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="022c5-126">Aggiunge un listener alla raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="022c5-126">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="022c5-127">Commenti</span><span class="sxs-lookup"><span data-stu-id="022c5-127">Remarks</span></span>  
 <span data-ttu-id="022c5-128">L' `<filter>` elemento deve essere contenuto in un `<add>` elemento per un listener di traccia che specifica il tipo del listener, non solo il nome di un listener definito in un oggetto [\<sharedListeners>](sharedlisteners-element.md) .</span><span class="sxs-lookup"><span data-stu-id="022c5-128">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="022c5-129">Se il listener è definito in un oggetto [\<sharedListeners>](sharedlisteners-element.md) , il filtro per il listener deve essere definito in tale elemento.</span><span class="sxs-lookup"><span data-stu-id="022c5-129">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="022c5-130">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="022c5-130">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="022c5-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="022c5-131">Example</span></span>  
 <span data-ttu-id="022c5-132">Nell'esempio seguente viene illustrato come utilizzare l' `<filter>` elemento per aggiungere un filtro al listener `console` nella `Listeners` raccolta per la traccia, specificando il livello dell'evento Filter come `Error` .</span><span class="sxs-lookup"><span data-stu-id="022c5-132">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="022c5-133">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="022c5-133">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="022c5-134">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="022c5-134">Trace and Debug Settings Schema</span></span>](index.md)
