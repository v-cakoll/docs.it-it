---
title: <filter>Elemento per <add> per per <listeners><source>
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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153516"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="790e6-102">\<filter>Elemento per \<add> per per \<listeners>\<source></span><span class="sxs-lookup"><span data-stu-id="790e6-102">\<filter> Element for \<add> for \<listeners> for \<source></span></span>
<span data-ttu-id="790e6-103">Aggiunge un filtro a un listener nella raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="790e6-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a><span data-ttu-id="790e6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="790e6-104">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="790e6-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="790e6-105">Attributes and Elements</span></span>  
 <span data-ttu-id="790e6-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="790e6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="790e6-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="790e6-107">Attributes</span></span>  
  
|<span data-ttu-id="790e6-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="790e6-108">Attribute</span></span>|<span data-ttu-id="790e6-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="790e6-109">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="790e6-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="790e6-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="790e6-111">Specifica il tipo di filtro che deve ereditare dalla <xref:System.Diagnostics.TraceFilter> classe.</span><span class="sxs-lookup"><span data-stu-id="790e6-111">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="790e6-112">È possibile utilizzare il nome completo dello spazio dei nomi del tipo, che corrisponde alla proprietà del tipo <xref:System.Type.FullName%2A> , oppure è possibile utilizzare il nome completo del tipo, incluse le informazioni sull'assembly, che corrisponde alla <xref:System.Type.AssemblyQualifiedName%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="790e6-112">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="790e6-113">Per informazioni sui nomi di tipo completi, vedere [specifica di nomi di tipo](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)completi.</span><span class="sxs-lookup"><span data-stu-id="790e6-113">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="790e6-114">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="790e6-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="790e6-115">Stringa passata al costruttore per la classe di filtro specificata.</span><span class="sxs-lookup"><span data-stu-id="790e6-115">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="790e6-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="790e6-116">Child Elements</span></span>  
 <span data-ttu-id="790e6-117">No.</span><span class="sxs-lookup"><span data-stu-id="790e6-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="790e6-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="790e6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="790e6-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="790e6-119">Element</span></span>|<span data-ttu-id="790e6-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="790e6-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="790e6-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="790e6-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="790e6-122">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="790e6-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="790e6-123">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="790e6-123">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="790e6-124">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="790e6-124">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="790e6-125">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="790e6-125">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="790e6-126">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="790e6-126">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="790e6-127">Aggiunge un listener alla raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="790e6-127">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="790e6-128">Commenti</span><span class="sxs-lookup"><span data-stu-id="790e6-128">Remarks</span></span>  
 <span data-ttu-id="790e6-129">L' `<filter>` elemento deve essere contenuto in un `<add>` elemento per un listener di origine di traccia che specifica il tipo del listener, non solo il nome di un listener definito in un oggetto [\<sharedListeners>](sharedlisteners-element.md) .</span><span class="sxs-lookup"><span data-stu-id="790e6-129">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="790e6-130">Se il listener è definito in un oggetto [\<sharedListeners>](sharedlisteners-element.md) , il filtro per il listener deve essere definito in tale elemento.</span><span class="sxs-lookup"><span data-stu-id="790e6-130">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="790e6-131">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="790e6-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="790e6-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="790e6-132">Example</span></span>  
 <span data-ttu-id="790e6-133">Nell'esempio seguente viene illustrato come utilizzare l' `<filter>` elemento per aggiungere un filtro al listener `console` nella `Listeners` raccolta per l'origine di traccia `myTraceSource` , specificando il livello di evento Filter come `Error` .</span><span class="sxs-lookup"><span data-stu-id="790e6-133">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="790e6-134">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="790e6-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="790e6-135">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="790e6-135">Trace and Debug Settings Schema</span></span>](index.md)
