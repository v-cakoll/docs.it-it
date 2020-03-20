---
title: <add>Elemento <listeners> per<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 883eef32172c5a7f900197995b4c57c3d5a84e19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153685"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="0f97d-102">\<aggiungere>elemento \<per i \<listener> per i> di origineAdd a Element for listeners> for source></span><span class="sxs-lookup"><span data-stu-id="0f97d-102">\<add> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="0f97d-103">Aggiunge un listener alla raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="0f97d-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="0f97d-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0f97d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0f97d-105">&nbsp;&nbsp;[**\<>system.diagnostics**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="0f97d-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="0f97d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<fonti>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="0f97d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="0f97d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="0f97d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="0f97d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di ascoltatori**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="0f97d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="0f97d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<aggiungere>**</span><span class="sxs-lookup"><span data-stu-id="0f97d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0f97d-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f97d-110">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f97d-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0f97d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0f97d-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0f97d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f97d-113">Attributes</span><span class="sxs-lookup"><span data-stu-id="0f97d-113">Attributes</span></span>  
  
|<span data-ttu-id="0f97d-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="0f97d-114">Attribute</span></span>|<span data-ttu-id="0f97d-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f97d-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="0f97d-116">Attributo obbligatorio, a meno che non `sharedListeners` si faccia riferimento a un listener nell'insieme, nel qual caso è sufficiente farvi riferimento in base al nome (vedere l'esempio ). [Example](#example)</span><span class="sxs-lookup"><span data-stu-id="0f97d-116">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="0f97d-117">Specifica il tipo di listener.</span><span class="sxs-lookup"><span data-stu-id="0f97d-117">Specifies the type of the listener.</span></span> <span data-ttu-id="0f97d-118">È necessario utilizzare una stringa che soddisfi i requisiti specificati in Specifica di nomi di [tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="0f97d-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="0f97d-119">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0f97d-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="0f97d-120">Stringa passata al costruttore per la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="0f97d-120">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="0f97d-121">Viene <xref:System.Configuration.ConfigurationException> generata un'eccezione se la classe non dispone di un costruttore che accetta una stringa.</span><span class="sxs-lookup"><span data-stu-id="0f97d-121">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="0f97d-122">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0f97d-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="0f97d-123">Specifica il nome del listener.</span><span class="sxs-lookup"><span data-stu-id="0f97d-123">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="0f97d-124">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0f97d-124">Optional attribute.</span></span><br /><br /> <span data-ttu-id="0f97d-125">Specifica il <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> valore della proprietà per il listener di traccia.</span><span class="sxs-lookup"><span data-stu-id="0f97d-125">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="0f97d-126">[attributi personalizzati]</span><span class="sxs-lookup"><span data-stu-id="0f97d-126">[custom attributes]</span></span>|<span data-ttu-id="0f97d-127">Attributi facoltativi.</span><span class="sxs-lookup"><span data-stu-id="0f97d-127">Optional attributes.</span></span><br /><br /> <span data-ttu-id="0f97d-128">Specifica il valore per gli attributi <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> specifici del listener identificati dal metodo per tale listener.</span><span class="sxs-lookup"><span data-stu-id="0f97d-128">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="0f97d-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>è un esempio di un <xref:System.Diagnostics.DelimitedListTraceListener> attributo aggiuntivo univoco per la classe.</span><span class="sxs-lookup"><span data-stu-id="0f97d-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0f97d-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0f97d-130">Child Elements</span></span>  
  
|<span data-ttu-id="0f97d-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="0f97d-131">Element</span></span>|<span data-ttu-id="0f97d-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f97d-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f97d-133">\<>di filtro</span><span class="sxs-lookup"><span data-stu-id="0f97d-133">\<filter></span></span>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="0f97d-134">Aggiunge un filtro a un listener nella raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="0f97d-134">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0f97d-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0f97d-135">Parent Elements</span></span>  
  
|<span data-ttu-id="0f97d-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="0f97d-136">Element</span></span>|<span data-ttu-id="0f97d-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f97d-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0f97d-138">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0f97d-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="0f97d-139">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="0f97d-139">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="0f97d-140">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="0f97d-140">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="0f97d-141">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="0f97d-141">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="0f97d-142">Specifica i listener che raccolgono, archiviano e instradano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="0f97d-142">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f97d-143">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0f97d-143">Remarks</span></span>  
 <span data-ttu-id="0f97d-144">Le classi listener fornite con .NET <xref:System.Diagnostics.TraceListener> Framework derivano dalla classe .</span><span class="sxs-lookup"><span data-stu-id="0f97d-144">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="0f97d-145">Se non si `name` specifica l'attributo <xref:System.Diagnostics.TraceListener.Name%2A> del listener di traccia, il valore predefinito della proprietà del listener di traccia è una stringa vuota ("").</span><span class="sxs-lookup"><span data-stu-id="0f97d-145">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="0f97d-146">Se l'applicazione dispone di un solo listener, è possibile aggiungerlo senza specificare un nome ed è possibile rimuoverlo specificando una stringa vuota per il nome.</span><span class="sxs-lookup"><span data-stu-id="0f97d-146">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="0f97d-147">Tuttavia, se l'applicazione dispone di più listener, è necessario specificare un nome univoco per ogni <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> listener di traccia, che consente di identificare e gestire i singoli listener di traccia nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="0f97d-147">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f97d-148">L'aggiunta di più listener di traccia dello stesso tipo e con lo stesso nome `Listeners` comporta l'aggiunta di un solo listener di traccia di tale tipo e nome alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="0f97d-148">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="0f97d-149">Tuttavia, è possibile aggiungere a livello `Listeners` di codice più listener identici alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="0f97d-149">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="0f97d-150">Il valore `initializeData` dell'attributo dipende dal tipo di listener creato.</span><span class="sxs-lookup"><span data-stu-id="0f97d-150">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="0f97d-151">Non tutti i listener di `initializeData`traccia richiedono l'impostazione di .</span><span class="sxs-lookup"><span data-stu-id="0f97d-151">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f97d-152">Quando si `initializeData` utilizza l'attributo, è possibile che venga visualizzato l'avviso del compilatore "L'attributo 'initializeData' non è dichiarato".</span><span class="sxs-lookup"><span data-stu-id="0f97d-152">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="0f97d-153">Questo avviso viene generato perché le impostazioni di <xref:System.Diagnostics.TraceListener>configurazione vengono convalidate rispetto alla classe base astratta , che non riconosce l'attributo `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="0f97d-153">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="0f97d-154">In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispongono di un costruttore che accetta un parametro.</span><span class="sxs-lookup"><span data-stu-id="0f97d-154">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="0f97d-155">Nella tabella seguente vengono illustrati i listener di traccia inclusi in .NET Framework e viene descritto il valore dei relativi `initializeData` attributi.</span><span class="sxs-lookup"><span data-stu-id="0f97d-155">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="0f97d-156">Classe listener di traccia</span><span class="sxs-lookup"><span data-stu-id="0f97d-156">Trace listener class</span></span>|<span data-ttu-id="0f97d-157">valore dell'attributo initializeData</span><span class="sxs-lookup"><span data-stu-id="0f97d-157">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="0f97d-158">Valore `useErrorStream` per <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> il costruttore.</span><span class="sxs-lookup"><span data-stu-id="0f97d-158">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="0f97d-159">Impostare `initializeData` l'attributo su "`true`" per scrivere la traccia e l'output di debug nel flusso di errore standard; impostarlo su`false`" " per scrivere nel flusso di output standard.</span><span class="sxs-lookup"><span data-stu-id="0f97d-159">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="0f97d-160">Nome del file in cui scrive <xref:System.Diagnostics.DelimitedListTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="0f97d-160">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="0f97d-161">Nome di un'origine del log eventi esistente.</span><span class="sxs-lookup"><span data-stu-id="0f97d-161">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="0f97d-162">Nome del file in <xref:System.Diagnostics.EventSchemaTraceListener> cui viene scritto il file.</span><span class="sxs-lookup"><span data-stu-id="0f97d-162">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="0f97d-163">Nome del file in <xref:System.Diagnostics.TextWriterTraceListener> cui viene scritto il file.</span><span class="sxs-lookup"><span data-stu-id="0f97d-163">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="0f97d-164">Nome del file in <xref:System.Diagnostics.XmlWriterTraceListener> cui viene scritto il file.</span><span class="sxs-lookup"><span data-stu-id="0f97d-164">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="0f97d-165">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="0f97d-165">Configuration File</span></span>  
 <span data-ttu-id="0f97d-166">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine.config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0f97d-166">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f97d-167">Esempio</span><span class="sxs-lookup"><span data-stu-id="0f97d-167">Example</span></span>  
 <span data-ttu-id="0f97d-168">Nell'esempio riportato `<add>` di seguito viene `console` illustrato `textListener` come `Listeners` utilizzare gli `TraceSourceApp`elementi per aggiungere i listener e all'insieme per l'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="0f97d-168">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="0f97d-169">Il `textListener` listener scrive l'output di traccia nel file myListener.log.</span><span class="sxs-lookup"><span data-stu-id="0f97d-169">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0f97d-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f97d-170">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="0f97d-171">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="0f97d-171">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0f97d-172">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="0f97d-172">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
