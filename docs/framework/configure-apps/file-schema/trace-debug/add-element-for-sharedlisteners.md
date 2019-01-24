---
title: '&lt;aggiungere&gt; (elemento) per &lt;sharedListeners&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
author: mcleblanc
ms.author: markl
ms.openlocfilehash: b8de4fd8a130f93b2ed3e14701c442a65c9ffcd8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712470"
---
# <a name="ltaddgt-element-for-ltsharedlistenersgt"></a><span data-ttu-id="ee2bf-102">&lt;aggiungere&gt; (elemento) per &lt;sharedListeners&gt;</span><span class="sxs-lookup"><span data-stu-id="ee2bf-102">&lt;add&gt; Element for &lt;sharedListeners&gt;</span></span>
<span data-ttu-id="ee2bf-103">Aggiunge un listener alla raccolta `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="ee2bf-104">`sharedListeners` è una raccolta di listener che eventuali [ \<origine >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) oppure [ \<traccia >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) può fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-104">`sharedListeners` is a collection of listeners that any [\<source>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) or [\<trace>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) can reference.</span></span>  <span data-ttu-id="ee2bf-105">Per impostazione predefinita, nei listener di traccia le `sharedListeners` raccolta non vengono inserite in un `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="ee2bf-106">Devono essere aggiunti in base al nome per il [ \<origine >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) oppure [ \<traccia >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md).</span><span class="sxs-lookup"><span data-stu-id="ee2bf-106">They must be added by name to the [\<source>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) or [\<trace>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md).</span></span> <span data-ttu-id="ee2bf-107">Non è possibile ottenere il listener `sharedListeners` insieme nel codice in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  
  
 <span data-ttu-id="ee2bf-108">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ee2bf-108">\<configuration></span></span>  
<span data-ttu-id="ee2bf-109">&nbsp;&nbsp;\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="ee2bf-109">&nbsp;&nbsp;\<system.diagnostics></span></span>  
<span data-ttu-id="ee2bf-110">&nbsp;&nbsp;&nbsp;&nbsp;\<sharedListeners > elemento</span><span class="sxs-lookup"><span data-stu-id="ee2bf-110">&nbsp;&nbsp;&nbsp;&nbsp;\<sharedListeners> Element</span></span>  
<span data-ttu-id="ee2bf-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<add></span><span class="sxs-lookup"><span data-stu-id="ee2bf-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee2bf-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee2bf-112">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee2bf-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ee2bf-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ee2bf-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee2bf-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="ee2bf-115">Attributes</span></span>  
  
|<span data-ttu-id="ee2bf-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="ee2bf-116">Attribute</span></span>|<span data-ttu-id="ee2bf-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee2bf-117">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="ee2bf-118">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="ee2bf-119">Specifica il nome del listener che consente di aggiungere il listener condiviso a un `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-119">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="ee2bf-120">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="ee2bf-121">Specifica il tipo del listener.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-121">Specifies the type of the listener.</span></span> <span data-ttu-id="ee2bf-122">È necessario usare una stringa che soddisfi i requisiti specificati nelle [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="ee2bf-122">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="ee2bf-123">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ee2bf-124">La stringa passata al costruttore per la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-124">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="ee2bf-125">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-125">Optional attribute.</span></span><br/><br/><span data-ttu-id="ee2bf-126">La rappresentazione di stringa di uno o più <xref:System.Diagnostics.TraceOptions> membri di enumerazione che indica i dati da scrivere nell'output di traccia.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-126">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="ee2bf-127">Più elementi sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-127">Multiple items are separated by commas.</span></span> <span data-ttu-id="ee2bf-128">Il valore predefinito è "None".</span><span class="sxs-lookup"><span data-stu-id="ee2bf-128">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ee2bf-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ee2bf-129">Child Elements</span></span>  
  
|<span data-ttu-id="ee2bf-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="ee2bf-130">Element</span></span>|<span data-ttu-id="ee2bf-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee2bf-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee2bf-132">\<filter></span><span class="sxs-lookup"><span data-stu-id="ee2bf-132">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="ee2bf-133">Aggiunge un filtro a un listener nella raccolta `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-133">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ee2bf-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ee2bf-134">Parent Elements</span></span>  
  
|<span data-ttu-id="ee2bf-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="ee2bf-135">Element</span></span>|<span data-ttu-id="ee2bf-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee2bf-136">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ee2bf-137">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="ee2bf-138">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-138">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="ee2bf-139">Raccolta di listener che possono fare riferimento qualsiasi origine o un elemento di traccia.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-139">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee2bf-140">Note</span><span class="sxs-lookup"><span data-stu-id="ee2bf-140">Remarks</span></span>  
 <span data-ttu-id="ee2bf-141">Le classi di listener fornite con .NET Framework derivano dal <xref:System.Diagnostics.TraceListener> classe.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-141">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="ee2bf-142">Il valore per il `name` attributo è usato per aggiungere il listener condiviso per un `Listeners` insieme per un'analisi o un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-142">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="ee2bf-143">Il valore per il `initializeData` attributo dipende dal tipo di listener creato.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="ee2bf-144">Non tutti i listener di traccia è necessario specificare `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee2bf-145">Quando si usa il `initializeData` attributo, è possibile che venga visualizzato l'avviso "non è dichiarato l'attributo 'attributo initializeData'." del compilatore</span><span class="sxs-lookup"><span data-stu-id="ee2bf-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="ee2bf-146">Questo avviso viene generato perché le impostazioni di configurazione vengono convalidate in base alla classe base astratta <xref:System.Diagnostics.TraceListener>, che non riconosce il `initializeData` attributo.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="ee2bf-147">In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispone di un costruttore che accetta un parametro.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="ee2bf-148">Nella tabella seguente mostra i listener di traccia incluse in .NET Framework e descrive il valore della loro `initializeData` attributi.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="ee2bf-149">Classe di listener di traccia</span><span class="sxs-lookup"><span data-stu-id="ee2bf-149">Trace listener class</span></span>|<span data-ttu-id="ee2bf-150">valore dell'attributo initializeData</span><span class="sxs-lookup"><span data-stu-id="ee2bf-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="ee2bf-151">Il `useErrorStream` valore per il <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="ee2bf-152">Impostare il `initializeData` dell'attributo "`true`"per scrivere output di traccia e debug nel flusso di errore standard; impostarlo su"`false`" per scrivere nel flusso di output standard.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="ee2bf-153">Il nome del file di <xref:System.Diagnostics.DelimitedListTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="ee2bf-154">Il nome di un'origine di log eventi esistente.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="ee2bf-155">Il nome del file che il <xref:System.Diagnostics.EventSchemaTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="ee2bf-156">Il nome del file che il <xref:System.Diagnostics.TextWriterTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="ee2bf-157">Il nome del file che il <xref:System.Diagnostics.XmlWriterTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="ee2bf-158">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="ee2bf-158">Configuration File</span></span>  
 <span data-ttu-id="ee2bf-159">Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee2bf-160">Esempio</span><span class="sxs-lookup"><span data-stu-id="ee2bf-160">Example</span></span>  
 <span data-ttu-id="ee2bf-161">Nell'esempio seguente viene illustrato come utilizzare `<add>` elementi da aggiungere i <xref:System.Diagnostics.TextWriterTraceListener> `textListener` per il `sharedListeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-161">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="ee2bf-162">`textListener` viene aggiunto in base al nome per il `Listeners` insieme per l'origine di traccia `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-162">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="ee2bf-163">Il `textListener` listener scrive output di traccia nel file myListener.</span><span class="sxs-lookup"><span data-stu-id="ee2bf-163">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ee2bf-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee2bf-164">See also</span></span>
- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="ee2bf-165">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="ee2bf-165">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="ee2bf-166">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="ee2bf-166">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
