---
title: Elemento <add> per <listeners> per <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: c32205310f9fc451a5a55a943f925ee52f65c8a8
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088994"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="62fd2-102">\<aggiungere > elemento per \<listener > per \<origine ></span><span class="sxs-lookup"><span data-stu-id="62fd2-102">\<add> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="62fd2-103">Aggiunge un listener alla raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="62fd2-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="62fd2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="62fd2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="62fd2-105">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="62fd2-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="62fd2-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**origini**](sources-element.md) ></span><span class="sxs-lookup"><span data-stu-id="62fd2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="62fd2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**origine**](source-element.md) ></span><span class="sxs-lookup"><span data-stu-id="62fd2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="62fd2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**listener**](listeners-element-for-source.md) ></span><span class="sxs-lookup"><span data-stu-id="62fd2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="62fd2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="62fd2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="62fd2-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62fd2-110">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62fd2-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="62fd2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="62fd2-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="62fd2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62fd2-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="62fd2-113">Attributes</span></span>  
  
|<span data-ttu-id="62fd2-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="62fd2-114">Attribute</span></span>|<span data-ttu-id="62fd2-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62fd2-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="62fd2-116">Attributo obbligatorio, a meno che non si faccia riferimento a un listener nella raccolta di `sharedListeners`, nel qual caso è necessario fare riferimento solo al nome (vedere l' [esempio](#example)).</span><span class="sxs-lookup"><span data-stu-id="62fd2-116">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="62fd2-117">Specifica il tipo di listener.</span><span class="sxs-lookup"><span data-stu-id="62fd2-117">Specifies the type of the listener.</span></span> <span data-ttu-id="62fd2-118">È necessario usare una stringa che soddisfi i requisiti specificati per [specificare nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="62fd2-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="62fd2-119">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="62fd2-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="62fd2-120">Stringa passata al costruttore per la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="62fd2-120">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="62fd2-121">Viene generata un'<xref:System.Configuration.ConfigurationException> se la classe non dispone di un costruttore che accetta una stringa.</span><span class="sxs-lookup"><span data-stu-id="62fd2-121">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="62fd2-122">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="62fd2-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="62fd2-123">Specifica il nome del listener.</span><span class="sxs-lookup"><span data-stu-id="62fd2-123">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="62fd2-124">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="62fd2-124">Optional attribute.</span></span><br /><br /> <span data-ttu-id="62fd2-125">Specifica il valore della proprietà <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> per il listener di traccia.</span><span class="sxs-lookup"><span data-stu-id="62fd2-125">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="62fd2-126">[attributi personalizzati]</span><span class="sxs-lookup"><span data-stu-id="62fd2-126">[custom attributes]</span></span>|<span data-ttu-id="62fd2-127">Attributi facoltativi.</span><span class="sxs-lookup"><span data-stu-id="62fd2-127">Optional attributes.</span></span><br /><br /> <span data-ttu-id="62fd2-128">Specifica il valore per gli attributi specifici del listener identificati dal metodo <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> per il listener.</span><span class="sxs-lookup"><span data-stu-id="62fd2-128">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="62fd2-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> è un esempio di attributo aggiuntivo univoco per la classe <xref:System.Diagnostics.DelimitedListTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="62fd2-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62fd2-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="62fd2-130">Child Elements</span></span>  
  
|<span data-ttu-id="62fd2-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="62fd2-131">Element</span></span>|<span data-ttu-id="62fd2-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62fd2-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62fd2-133">\<filter></span><span class="sxs-lookup"><span data-stu-id="62fd2-133">\<filter></span></span>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="62fd2-134">Aggiunge un filtro a un listener nella raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="62fd2-134">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="62fd2-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="62fd2-135">Parent Elements</span></span>  
  
|<span data-ttu-id="62fd2-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="62fd2-136">Element</span></span>|<span data-ttu-id="62fd2-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62fd2-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="62fd2-138">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="62fd2-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="62fd2-139">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="62fd2-139">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="62fd2-140">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="62fd2-140">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="62fd2-141">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="62fd2-141">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="62fd2-142">Specifica i listener che raccolgono, archiviano e indirizzano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="62fd2-142">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62fd2-143">Note</span><span class="sxs-lookup"><span data-stu-id="62fd2-143">Remarks</span></span>  
 <span data-ttu-id="62fd2-144">Le classi del listener fornite con la .NET Framework derivano dalla classe <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="62fd2-144">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="62fd2-145">Se non si specifica l'attributo `name` del listener di traccia, la proprietà <xref:System.Diagnostics.TraceListener.Name%2A> del listener di traccia viene impostata in modo predefinito su una stringa vuota ("").</span><span class="sxs-lookup"><span data-stu-id="62fd2-145">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="62fd2-146">Se l'applicazione dispone di un solo listener, è possibile aggiungerla senza specificare un nome ed è possibile rimuoverla specificando una stringa vuota per il nome.</span><span class="sxs-lookup"><span data-stu-id="62fd2-146">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="62fd2-147">Tuttavia, se l'applicazione ha più di un listener, è necessario specificare un nome univoco per ogni listener di traccia, che consente di identificare e gestire i singoli listener di traccia nella raccolta di <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="62fd2-147">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="62fd2-148">L'aggiunta di più listener di traccia dello stesso tipo e con lo stesso nome comporta l'aggiunta di un solo listener di traccia di quel tipo e del nome alla raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="62fd2-148">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="62fd2-149">Tuttavia, è possibile aggiungere a livello di codice più listener identici alla raccolta di `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="62fd2-149">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="62fd2-150">Il valore per l'attributo `initializeData` dipende dal tipo di listener creato.</span><span class="sxs-lookup"><span data-stu-id="62fd2-150">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="62fd2-151">Non tutti i listener di traccia richiedono di specificare `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="62fd2-151">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="62fd2-152">Quando si usa l'attributo `initializeData`, è possibile che venga visualizzato l'avviso del compilatore "l'attributo ' initializeData ' non è dichiarato".</span><span class="sxs-lookup"><span data-stu-id="62fd2-152">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="62fd2-153">Questo avviso si verifica perché le impostazioni di configurazione vengono convalidate rispetto alla classe di base astratta <xref:System.Diagnostics.TraceListener>, che non riconosce l'attributo `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="62fd2-153">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="62fd2-154">In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispongono di un costruttore che accetta un parametro.</span><span class="sxs-lookup"><span data-stu-id="62fd2-154">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="62fd2-155">Nella tabella seguente vengono illustrati i listener di traccia inclusi nel .NET Framework e viene descritto il valore degli attributi di `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="62fd2-155">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="62fd2-156">Classe listener di traccia</span><span class="sxs-lookup"><span data-stu-id="62fd2-156">Trace listener class</span></span>|<span data-ttu-id="62fd2-157">valore dell'attributo initializeData</span><span class="sxs-lookup"><span data-stu-id="62fd2-157">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="62fd2-158">Valore `useErrorStream` per il costruttore di <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.</span><span class="sxs-lookup"><span data-stu-id="62fd2-158">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="62fd2-159">Impostare l'attributo `initializeData` su "`true`" per scrivere l'output di traccia e di debug nel flusso di errore standard. impostarla su "`false`" per scrivere nel flusso di output standard.</span><span class="sxs-lookup"><span data-stu-id="62fd2-159">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="62fd2-160">Nome del file in cui viene scritto il <xref:System.Diagnostics.DelimitedListTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="62fd2-160">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="62fd2-161">Nome di un'origine del log eventi esistente.</span><span class="sxs-lookup"><span data-stu-id="62fd2-161">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="62fd2-162">Nome del file in cui viene scritto il <xref:System.Diagnostics.EventSchemaTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="62fd2-162">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="62fd2-163">Nome del file in cui viene scritto il <xref:System.Diagnostics.TextWriterTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="62fd2-163">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="62fd2-164">Nome del file in cui viene scritto il <xref:System.Diagnostics.XmlWriterTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="62fd2-164">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="62fd2-165">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="62fd2-165">Configuration File</span></span>  
 <span data-ttu-id="62fd2-166">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="62fd2-166">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62fd2-167">Esempio</span><span class="sxs-lookup"><span data-stu-id="62fd2-167">Example</span></span>  
 <span data-ttu-id="62fd2-168">Nell'esempio seguente viene illustrato come utilizzare gli elementi `<add>` per aggiungere i listener `console` e `textListener` alla raccolta `Listeners` per l'origine di traccia `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="62fd2-168">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="62fd2-169">Il listener `textListener` scrive l'output di traccia nel file listener. log.</span><span class="sxs-lookup"><span data-stu-id="62fd2-169">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="62fd2-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62fd2-170">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="62fd2-171">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="62fd2-171">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="62fd2-172">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="62fd2-172">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
