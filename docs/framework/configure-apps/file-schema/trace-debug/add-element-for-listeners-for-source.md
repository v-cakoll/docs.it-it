---
title: <add>Elemento per <listeners> per<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 883eef32172c5a7f900197995b4c57c3d5a84e19
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153685"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="1e069-102">\<add>Elemento per \<listeners> per\<source></span><span class="sxs-lookup"><span data-stu-id="1e069-102">\<add> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="1e069-103">Aggiunge un listener alla raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="1e069-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="1e069-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e069-104">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e069-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1e069-105">Attributes and Elements</span></span>  
 <span data-ttu-id="1e069-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1e069-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e069-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="1e069-107">Attributes</span></span>  
  
|<span data-ttu-id="1e069-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="1e069-108">Attribute</span></span>|<span data-ttu-id="1e069-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e069-109">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="1e069-110">Attributo obbligatorio, a meno che non si faccia riferimento a un listener nella `sharedListeners` raccolta. in tal caso, è necessario fare riferimento solo al nome (vedere l' [esempio](#example)).</span><span class="sxs-lookup"><span data-stu-id="1e069-110">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="1e069-111">Specifica il tipo di listener.</span><span class="sxs-lookup"><span data-stu-id="1e069-111">Specifies the type of the listener.</span></span> <span data-ttu-id="1e069-112">È necessario usare una stringa che soddisfi i requisiti specificati per [specificare nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="1e069-112">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="1e069-113">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1e069-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="1e069-114">Stringa passata al costruttore per la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="1e069-114">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="1e069-115"><xref:System.Configuration.ConfigurationException>Viene generata un'eccezione se la classe non dispone di un costruttore che accetta una stringa.</span><span class="sxs-lookup"><span data-stu-id="1e069-115">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="1e069-116">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1e069-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="1e069-117">Specifica il nome del listener.</span><span class="sxs-lookup"><span data-stu-id="1e069-117">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="1e069-118">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1e069-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="1e069-119">Specifica il <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> valore della proprietà per il listener di traccia.</span><span class="sxs-lookup"><span data-stu-id="1e069-119">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="1e069-120">[attributi personalizzati]</span><span class="sxs-lookup"><span data-stu-id="1e069-120">[custom attributes]</span></span>|<span data-ttu-id="1e069-121">Attributi facoltativi.</span><span class="sxs-lookup"><span data-stu-id="1e069-121">Optional attributes.</span></span><br /><br /> <span data-ttu-id="1e069-122">Specifica il valore per gli attributi specifici del listener identificati dal <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> metodo per il listener.</span><span class="sxs-lookup"><span data-stu-id="1e069-122">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="1e069-123"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>è un esempio di attributo aggiuntivo univoco per la <xref:System.Diagnostics.DelimitedListTraceListener> classe.</span><span class="sxs-lookup"><span data-stu-id="1e069-123"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e069-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1e069-124">Child Elements</span></span>  
  
|<span data-ttu-id="1e069-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="1e069-125">Element</span></span>|<span data-ttu-id="1e069-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e069-126">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="1e069-127">Aggiunge un filtro a un listener nella raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="1e069-127">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1e069-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1e069-128">Parent Elements</span></span>  
  
|<span data-ttu-id="1e069-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="1e069-129">Element</span></span>|<span data-ttu-id="1e069-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e069-130">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1e069-131">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1e069-131">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="1e069-132">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="1e069-132">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="1e069-133">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="1e069-133">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="1e069-134">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="1e069-134">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="1e069-135">Specifica i listener che raccolgono, archiviano e indirizzano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="1e069-135">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e069-136">Commenti</span><span class="sxs-lookup"><span data-stu-id="1e069-136">Remarks</span></span>  
 <span data-ttu-id="1e069-137">Le classi del listener fornite con la .NET Framework derivano dalla <xref:System.Diagnostics.TraceListener> classe.</span><span class="sxs-lookup"><span data-stu-id="1e069-137">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="1e069-138">Se non si specifica l' `name` attributo del listener di traccia, <xref:System.Diagnostics.TraceListener.Name%2A> per impostazione predefinita la proprietà del listener di traccia è una stringa vuota ("").</span><span class="sxs-lookup"><span data-stu-id="1e069-138">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="1e069-139">Se l'applicazione dispone di un solo listener, è possibile aggiungerla senza specificare un nome ed è possibile rimuoverla specificando una stringa vuota per il nome.</span><span class="sxs-lookup"><span data-stu-id="1e069-139">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="1e069-140">Tuttavia, se l'applicazione ha più di un listener, è necessario specificare un nome univoco per ogni listener di traccia, che consente di identificare e gestire i singoli listener di traccia nella <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> raccolta.</span><span class="sxs-lookup"><span data-stu-id="1e069-140">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1e069-141">L'aggiunta di più listener di traccia dello stesso tipo e con lo stesso nome comporta l'aggiunta di un solo listener di traccia del tipo e del nome alla `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="1e069-141">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="1e069-142">Tuttavia, è possibile aggiungere a livello di codice più listener identici alla `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="1e069-142">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="1e069-143">Il valore dell' `initializeData` attributo dipende dal tipo di listener creato.</span><span class="sxs-lookup"><span data-stu-id="1e069-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="1e069-144">Non tutti i listener di traccia richiedono che venga specificato `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="1e069-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1e069-145">Quando si usa l' `initializeData` attributo, è possibile che venga visualizzato l'avviso del compilatore "l'attributo ' initializeData ' non è dichiarato".</span><span class="sxs-lookup"><span data-stu-id="1e069-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="1e069-146">Questo avviso si verifica perché le impostazioni di configurazione vengono convalidate rispetto alla classe di base astratta <xref:System.Diagnostics.TraceListener> , che non riconosce l' `initializeData` attributo.</span><span class="sxs-lookup"><span data-stu-id="1e069-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="1e069-147">In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispongono di un costruttore che accetta un parametro.</span><span class="sxs-lookup"><span data-stu-id="1e069-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="1e069-148">Nella tabella seguente vengono illustrati i listener di traccia inclusi nel .NET Framework e viene descritto il valore dei rispettivi `initializeData` attributi.</span><span class="sxs-lookup"><span data-stu-id="1e069-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="1e069-149">Classe listener di traccia</span><span class="sxs-lookup"><span data-stu-id="1e069-149">Trace listener class</span></span>|<span data-ttu-id="1e069-150">valore dell'attributo initializeData</span><span class="sxs-lookup"><span data-stu-id="1e069-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="1e069-151">`useErrorStream`Valore per il <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="1e069-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="1e069-152">Impostare l' `initializeData` attributo su " `true` " per scrivere l'output di traccia e di debug nel flusso di errore standard. impostarlo su " `false` " per scrivere nel flusso di output standard.</span><span class="sxs-lookup"><span data-stu-id="1e069-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="1e069-153">Nome del file in cui scrive <xref:System.Diagnostics.DelimitedListTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="1e069-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="1e069-154">Nome di un'origine del log eventi esistente.</span><span class="sxs-lookup"><span data-stu-id="1e069-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="1e069-155">Nome del file <xref:System.Diagnostics.EventSchemaTraceListener> in cui scrive.</span><span class="sxs-lookup"><span data-stu-id="1e069-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="1e069-156">Nome del file <xref:System.Diagnostics.TextWriterTraceListener> in cui scrive.</span><span class="sxs-lookup"><span data-stu-id="1e069-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="1e069-157">Nome del file <xref:System.Diagnostics.XmlWriterTraceListener> in cui scrive.</span><span class="sxs-lookup"><span data-stu-id="1e069-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="1e069-158">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="1e069-158">Configuration File</span></span>  
 <span data-ttu-id="1e069-159">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1e069-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e069-160">Esempio</span><span class="sxs-lookup"><span data-stu-id="1e069-160">Example</span></span>  
 <span data-ttu-id="1e069-161">Nell'esempio seguente viene illustrato come utilizzare `<add>` gli elementi per aggiungere i listener `console` e `textListener` alla `Listeners` raccolta per l'origine di traccia `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="1e069-161">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="1e069-162">Il `textListener` listener scrive l'output di traccia nel file listener. log.</span><span class="sxs-lookup"><span data-stu-id="1e069-162">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1e069-163">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="1e069-163">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="1e069-164">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="1e069-164">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="1e069-165">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="1e069-165">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
