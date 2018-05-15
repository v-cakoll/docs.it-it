---
title: '&lt;aggiungere&gt; elemento per &lt;listener&gt; per &lt;origine&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ba8ff652003a9167ec370643797ac9300b83889a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="a4b4a-102">&lt;aggiungere&gt; elemento per &lt;listener&gt; per &lt;origine&gt;</span><span class="sxs-lookup"><span data-stu-id="a4b4a-102">&lt;add&gt; Element for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="a4b4a-103">Aggiunge un listener alla raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="a4b4a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a4b4a-104">\<configuration></span></span>  
<span data-ttu-id="a4b4a-105">\<System. Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="a4b4a-105">\<system.diagnostics></span></span>  
<span data-ttu-id="a4b4a-106">\<origini ></span><span class="sxs-lookup"><span data-stu-id="a4b4a-106">\<sources></span></span>  
<span data-ttu-id="a4b4a-107">\<origine ></span><span class="sxs-lookup"><span data-stu-id="a4b4a-107">\<source></span></span>  
<span data-ttu-id="a4b4a-108">\<listener ></span><span class="sxs-lookup"><span data-stu-id="a4b4a-108">\<listeners></span></span>  
<span data-ttu-id="a4b4a-109">\<add></span><span class="sxs-lookup"><span data-stu-id="a4b4a-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4b4a-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4b4a-110">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4b4a-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a4b4a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a4b4a-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4b4a-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="a4b4a-113">Attributes</span></span>  
  
|<span data-ttu-id="a4b4a-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="a4b4a-114">Attribute</span></span>|<span data-ttu-id="a4b4a-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a4b4a-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="a4b4a-116">Attributo, obbligatorio, a meno che non viene fatto riferimento a un listener di `sharedListeners` insieme, in cui caso è sufficiente farvi riferimento in base al nome (vedere il [esempio](#example)).</span><span class="sxs-lookup"><span data-stu-id="a4b4a-116">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="a4b4a-117">Specifica il tipo del listener.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-117">Specifies the type of the listener.</span></span> <span data-ttu-id="a4b4a-118">È necessario utilizzare una stringa che soddisfi i requisiti indicati in [specifica di nomi di tipo completi](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="a4b4a-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="a4b4a-119">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a4b4a-120">La stringa passata al costruttore per la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-120">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="a4b4a-121">Oggetto <xref:System.Configuration.ConfigurationException> viene generata se la classe non ha un costruttore che accetta una stringa.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-121">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="a4b4a-122">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a4b4a-123">Specifica il nome del listener.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-123">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="a4b4a-124">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-124">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a4b4a-125">Specifica il <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> valore della proprietà per il listener di traccia.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-125">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="a4b4a-126">[attributi]</span><span class="sxs-lookup"><span data-stu-id="a4b4a-126">[custom attributes]</span></span>|<span data-ttu-id="a4b4a-127">Attributi facoltativi.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-127">Optional attributes.</span></span><br /><br /> <span data-ttu-id="a4b4a-128">Specifica il valore di attributi specifico del listener identificati per il <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> metodo per il listener.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-128">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="a4b4a-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> è univoco per un esempio di attributo aggiuntivo il <xref:System.Diagnostics.DelimitedListTraceListener> classe.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4b4a-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a4b4a-130">Child Elements</span></span>  
  
|<span data-ttu-id="a4b4a-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="a4b4a-131">Element</span></span>|<span data-ttu-id="a4b4a-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a4b4a-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4b4a-133">\<filter></span><span class="sxs-lookup"><span data-stu-id="a4b4a-133">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="a4b4a-134">Aggiunge un filtro a un listener nella raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-134">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a4b4a-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a4b4a-135">Parent Elements</span></span>  
  
|<span data-ttu-id="a4b4a-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="a4b4a-136">Element</span></span>|<span data-ttu-id="a4b4a-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a4b4a-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a4b4a-138">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a4b4a-139">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-139">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="a4b4a-140">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-140">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="a4b4a-141">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-141">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="a4b4a-142">Specifica i listener di raccolgano, archiviano e indirizzare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-142">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4b4a-143">Note</span><span class="sxs-lookup"><span data-stu-id="a4b4a-143">Remarks</span></span>  
 <span data-ttu-id="a4b4a-144">Le classi di listener fornite con .NET Framework derivano dalla <xref:System.Diagnostics.TraceListener> classe.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-144">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="a4b4a-145">Se non si specifica il `name` attributo del listener di traccia, il <xref:System.Diagnostics.TraceListener.Name%2A> valore predefinito di proprietà del listener di traccia in una stringa vuota ("").</span><span class="sxs-lookup"><span data-stu-id="a4b4a-145">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="a4b4a-146">Se l'applicazione presenta un solo listener, è possibile aggiungerlo senza specificare un nome ed è possibile rimuoverlo specificando una stringa vuota per il nome.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-146">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="a4b4a-147">Tuttavia, se l'applicazione presenta più di un listener, specificare un nome univoco per ogni listener di traccia, che consente di identificare e gestire singoli traccia nei listener di <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> insieme.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-147">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4b4a-148">Aggiunta di più di un listener di traccia, dello stesso tipo e con lo stesso nome risultati in un solo listener di traccia di quel tipo e nome viene aggiunto al `Listeners` insieme.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-148">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="a4b4a-149">Tuttavia, è possibile aggiungere a livello di codice più listener identici per il `Listeners` insieme.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-149">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="a4b4a-150">Il valore per il `initializeData` attributo dipende dal tipo di listener creato.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-150">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="a4b4a-151">Non tutti i listener di traccia è necessario specificare `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-151">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4b4a-152">Quando si utilizza il `initializeData` attributo, è possibile che venga visualizzato l'avviso "l'attributo 'initializeData' non dichiarato." del compilatore</span><span class="sxs-lookup"><span data-stu-id="a4b4a-152">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="a4b4a-153">Questo avviso viene generato perché le impostazioni di configurazione vengono convalidate in base alla classe base astratta <xref:System.Diagnostics.TraceListener>, che non riconosce il `initializeData` attributo.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-153">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="a4b4a-154">In genere, è possibile ignorare questo avviso per le implementazioni di listener di traccia che dispone di un costruttore che accetta un parametro.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-154">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="a4b4a-155">Nella tabella seguente mostra i listener di traccia inclusi in .NET Framework e descrive il valore della loro `initializeData` attributi.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-155">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="a4b4a-156">Classe di listener di traccia</span><span class="sxs-lookup"><span data-stu-id="a4b4a-156">Trace listener class</span></span>|<span data-ttu-id="a4b4a-157">valore dell'attributo initializeData</span><span class="sxs-lookup"><span data-stu-id="a4b4a-157">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="a4b4a-158">Il `useErrorStream` valore per il <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-158">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="a4b4a-159">Impostare il `initializeData` attributo "`true`"per scrivere output di traccia e debug nel flusso di errore standard; impostarla su"`false`" per scrivere nel flusso di output standard.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-159">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="a4b4a-160">Il nome del file di <xref:System.Diagnostics.DelimitedListTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-160">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="a4b4a-161">Il nome di un'origine di log eventi esistente.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-161">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="a4b4a-162">Il nome del file che il <xref:System.Diagnostics.EventSchemaTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-162">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="a4b4a-163">Il nome del file che il <xref:System.Diagnostics.TextWriterTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-163">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="a4b4a-164">Il nome del file che il <xref:System.Diagnostics.XmlWriterTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-164">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="a4b4a-165">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="a4b4a-165">Configuration File</span></span>  
 <span data-ttu-id="a4b4a-166">Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-166">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4b4a-167">Esempio</span><span class="sxs-lookup"><span data-stu-id="a4b4a-167">Example</span></span>  
 <span data-ttu-id="a4b4a-168">Nell'esempio seguente viene illustrato come utilizzare `<add>` elementi per aggiungere i listener `console` e `textListener` per il `Listeners` raccolta per l'origine di traccia `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-168">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="a4b4a-169">Il `textListener` listener scrive output di traccia nel file myListener.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-169">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a4b4a-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4b4a-170">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="a4b4a-171">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="a4b4a-171">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="a4b4a-172">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="a4b4a-172">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
