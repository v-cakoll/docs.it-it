---
title: Elemento <add> per <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
ms.openlocfilehash: c4b83834fb7aaf64a696b85bd2c8da47cfba2397
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927219"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="ecdfb-102">\<aggiungere > elemento per \<sharedListeners ></span><span class="sxs-lookup"><span data-stu-id="ecdfb-102">\<add> Element for \<sharedListeners></span></span>
<span data-ttu-id="ecdfb-103">Aggiunge un listener alla raccolta `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="ecdfb-104">`sharedListeners`è una raccolta di listener a cui può fare riferimento qualsiasi [ \<> di origine](source-element.md) o [ \<> di traccia](trace-element.md) .</span><span class="sxs-lookup"><span data-stu-id="ecdfb-104">`sharedListeners` is a collection of listeners that any [\<source>](source-element.md) or [\<trace>](trace-element.md) can reference.</span></span>  <span data-ttu-id="ecdfb-105">Per impostazione predefinita, i `sharedListeners` listener nella raccolta non vengono inseriti in una `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="ecdfb-106">Devono essere aggiunti per nome al > di [ \<origine](source-element.md) o [ \<> di traccia](trace-element.md).</span><span class="sxs-lookup"><span data-stu-id="ecdfb-106">They must be added by name to the [\<source>](source-element.md) or [\<trace>](trace-element.md).</span></span> <span data-ttu-id="ecdfb-107">Non è possibile ottenere i listener nella `sharedListeners` raccolta nel codice in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  
  
 <span data-ttu-id="ecdfb-108">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ecdfb-108">\<configuration></span></span>  
<span data-ttu-id="ecdfb-109">&nbsp;&nbsp;\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="ecdfb-109">&nbsp;&nbsp;\<system.diagnostics></span></span>  
<span data-ttu-id="ecdfb-110">&nbsp;&nbsp;&nbsp;&nbsp;\<Elemento > sharedListeners</span><span class="sxs-lookup"><span data-stu-id="ecdfb-110">&nbsp;&nbsp;&nbsp;&nbsp;\<sharedListeners> Element</span></span>  
<span data-ttu-id="ecdfb-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<add></span><span class="sxs-lookup"><span data-stu-id="ecdfb-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecdfb-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ecdfb-112">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ecdfb-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ecdfb-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ecdfb-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ecdfb-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="ecdfb-115">Attributes</span></span>  
  
|<span data-ttu-id="ecdfb-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="ecdfb-116">Attribute</span></span>|<span data-ttu-id="ecdfb-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ecdfb-117">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="ecdfb-118">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="ecdfb-119">Specifica il nome del listener utilizzato per aggiungere il listener condiviso a una `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-119">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="ecdfb-120">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="ecdfb-121">Specifica il tipo di listener.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-121">Specifies the type of the listener.</span></span> <span data-ttu-id="ecdfb-122">È necessario usare una stringa che soddisfi i requisiti specificati per [specificare nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="ecdfb-122">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="ecdfb-123">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ecdfb-124">Stringa passata al costruttore per la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-124">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="ecdfb-125">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-125">Optional attribute.</span></span><br/><br/><span data-ttu-id="ecdfb-126">Rappresentazione di stringa di uno o più <xref:System.Diagnostics.TraceOptions> membri dell'enumerazione che indica i dati da scrivere nell'output di traccia.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-126">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="ecdfb-127">Più elementi sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-127">Multiple items are separated by commas.</span></span> <span data-ttu-id="ecdfb-128">Il valore predefinito è "None".</span><span class="sxs-lookup"><span data-stu-id="ecdfb-128">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ecdfb-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ecdfb-129">Child Elements</span></span>  
  
|<span data-ttu-id="ecdfb-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="ecdfb-130">Element</span></span>|<span data-ttu-id="ecdfb-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ecdfb-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ecdfb-132">\<filter></span><span class="sxs-lookup"><span data-stu-id="ecdfb-132">\<filter></span></span>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="ecdfb-133">Aggiunge un filtro a un listener nella raccolta `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-133">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ecdfb-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ecdfb-134">Parent Elements</span></span>  
  
|<span data-ttu-id="ecdfb-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="ecdfb-135">Element</span></span>|<span data-ttu-id="ecdfb-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ecdfb-136">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ecdfb-137">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="ecdfb-138">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-138">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="ecdfb-139">Raccolta di listener a cui qualsiasi origine o elemento Trace può fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-139">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ecdfb-140">Note</span><span class="sxs-lookup"><span data-stu-id="ecdfb-140">Remarks</span></span>  
 <span data-ttu-id="ecdfb-141">Le classi del listener fornite con la .NET Framework derivano <xref:System.Diagnostics.TraceListener> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-141">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="ecdfb-142">Il valore per l' `name` attributo viene utilizzato per aggiungere il listener condiviso a una `Listeners` raccolta per una traccia o un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-142">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="ecdfb-143">Il valore `initializeData` dell'attributo dipende dal tipo di listener creato.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="ecdfb-144">Non tutti i listener di traccia richiedono che venga `initializeData`specificato.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ecdfb-145">Quando si usa l' `initializeData` attributo, è possibile che venga visualizzato l'avviso del compilatore "l'attributo ' initializeData ' non è dichiarato".</span><span class="sxs-lookup"><span data-stu-id="ecdfb-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="ecdfb-146">Questo avviso si verifica perché le impostazioni di configurazione vengono convalidate rispetto alla <xref:System.Diagnostics.TraceListener>classe di base astratta, che `initializeData` non riconosce l'attributo.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="ecdfb-147">In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispongono di un costruttore che accetta un parametro.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="ecdfb-148">Nella tabella seguente vengono illustrati i listener di traccia inclusi nel .NET Framework e viene descritto il valore dei rispettivi `initializeData` attributi.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="ecdfb-149">Classe listener di traccia</span><span class="sxs-lookup"><span data-stu-id="ecdfb-149">Trace listener class</span></span>|<span data-ttu-id="ecdfb-150">valore dell'attributo initializeData</span><span class="sxs-lookup"><span data-stu-id="ecdfb-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="ecdfb-151">Valore per il <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>costruttore. `useErrorStream`</span><span class="sxs-lookup"><span data-stu-id="ecdfb-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="ecdfb-152">Impostare l' `initializeData` attributo su "`true`" per scrivere l'output di traccia e di debug nel flusso di errore standard. impostarlo su "`false`" per scrivere nel flusso di output standard.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="ecdfb-153">Nome del file <xref:System.Diagnostics.DelimitedListTraceListener> in cui scrive.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="ecdfb-154">Nome di un'origine del log eventi esistente.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="ecdfb-155">Nome del file in cui <xref:System.Diagnostics.EventSchemaTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="ecdfb-156">Nome del file in cui <xref:System.Diagnostics.TextWriterTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="ecdfb-157">Nome del file in cui <xref:System.Diagnostics.XmlWriterTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="ecdfb-158">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="ecdfb-158">Configuration File</span></span>  
 <span data-ttu-id="ecdfb-159">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecdfb-160">Esempio</span><span class="sxs-lookup"><span data-stu-id="ecdfb-160">Example</span></span>  
 <span data-ttu-id="ecdfb-161">Nell'esempio seguente viene illustrato come utilizzare `<add>` gli elementi per aggiungere <xref:System.Diagnostics.TextWriterTraceListener> l'oggetto `sharedListeners` `textListener` alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-161">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="ecdfb-162">`textListener`viene aggiunto per nome alla `Listeners` raccolta per l'origine `TraceSourceApp`di traccia.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-162">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="ecdfb-163">Il `textListener` listener scrive l'output di traccia nel file listener. log.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-163">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="ecdfb-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecdfb-164">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="ecdfb-165">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="ecdfb-165">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ecdfb-166">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="ecdfb-166">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
