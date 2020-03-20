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
ms.openlocfilehash: 5588892ec75a791eda1eb043936c0af95e79354e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153607"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="eaead-102">\<Aggiungere elemento \<> per la> sharedListenersAdd a Element for sharedListeners></span><span class="sxs-lookup"><span data-stu-id="eaead-102">\<add> Element for \<sharedListeners></span></span>
<span data-ttu-id="eaead-103">Aggiunge un listener alla raccolta `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="eaead-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="eaead-104">`sharedListeners`è una raccolta di [ \<](source-element.md) listener a cui possono fare riferimento qualsiasi>di origine o [ \<>](trace-element.md) di traccia.</span><span class="sxs-lookup"><span data-stu-id="eaead-104">`sharedListeners` is a collection of listeners that any [\<source>](source-element.md) or [\<trace>](trace-element.md) can reference.</span></span>  <span data-ttu-id="eaead-105">Per impostazione predefinita, `sharedListeners` i listener nella `Listeners` raccolta non vengono inseriti in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="eaead-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="eaead-106">Devono essere aggiunti in [ \<](source-element.md) base al nome al>di origine o [ \< ](trace-element.md)>di traccia .</span><span class="sxs-lookup"><span data-stu-id="eaead-106">They must be added by name to the [\<source>](source-element.md) or [\<trace>](trace-element.md).</span></span> <span data-ttu-id="eaead-107">Non è possibile ottenere i listener `sharedListeners` nella raccolta nel codice in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="eaead-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  

<span data-ttu-id="eaead-108">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="eaead-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="eaead-109">&nbsp;&nbsp;[**\<>system.diagnostics**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="eaead-109">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="eaead-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>sharedListeners**](sharedlisteners-element.md)</span><span class="sxs-lookup"><span data-stu-id="eaead-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)</span></span>\
<span data-ttu-id="eaead-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<aggiungere>**</span><span class="sxs-lookup"><span data-stu-id="eaead-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="eaead-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eaead-112">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eaead-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="eaead-113">Attributes and Elements</span></span>  
 <span data-ttu-id="eaead-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="eaead-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eaead-115">Attributes</span><span class="sxs-lookup"><span data-stu-id="eaead-115">Attributes</span></span>  
  
|<span data-ttu-id="eaead-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="eaead-116">Attribute</span></span>|<span data-ttu-id="eaead-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eaead-117">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="eaead-118">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="eaead-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="eaead-119">Specifica il nome del listener utilizzato per aggiungere il `Listeners` listener condiviso a una raccolta.</span><span class="sxs-lookup"><span data-stu-id="eaead-119">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="eaead-120">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="eaead-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="eaead-121">Specifica il tipo di listener.</span><span class="sxs-lookup"><span data-stu-id="eaead-121">Specifies the type of the listener.</span></span> <span data-ttu-id="eaead-122">È necessario utilizzare una stringa che soddisfi i requisiti specificati in Specifica di nomi di [tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="eaead-122">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="eaead-123">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="eaead-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="eaead-124">Stringa passata al costruttore per la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="eaead-124">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="eaead-125">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="eaead-125">Optional attribute.</span></span><br/><br/><span data-ttu-id="eaead-126">Rappresentazione di stringa <xref:System.Diagnostics.TraceOptions> di uno o più membri di enumerazione che indicano i dati da scrivere nell'output di traccia.</span><span class="sxs-lookup"><span data-stu-id="eaead-126">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="eaead-127">Più elementi sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="eaead-127">Multiple items are separated by commas.</span></span> <span data-ttu-id="eaead-128">Il valore predefinito è "None".</span><span class="sxs-lookup"><span data-stu-id="eaead-128">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="eaead-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="eaead-129">Child Elements</span></span>  
  
|<span data-ttu-id="eaead-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="eaead-130">Element</span></span>|<span data-ttu-id="eaead-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eaead-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eaead-132">\<>di filtro</span><span class="sxs-lookup"><span data-stu-id="eaead-132">\<filter></span></span>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="eaead-133">Aggiunge un filtro a un listener nella raccolta `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="eaead-133">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eaead-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="eaead-134">Parent Elements</span></span>  
  
|<span data-ttu-id="eaead-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="eaead-135">Element</span></span>|<span data-ttu-id="eaead-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eaead-136">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="eaead-137">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eaead-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="eaead-138">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="eaead-138">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="eaead-139">Raccolta di listener a cui può fare riferimento qualsiasi elemento di origine o di traccia.</span><span class="sxs-lookup"><span data-stu-id="eaead-139">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eaead-140">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="eaead-140">Remarks</span></span>  
 <span data-ttu-id="eaead-141">Le classi listener fornite con .NET <xref:System.Diagnostics.TraceListener> Framework derivano dalla classe .</span><span class="sxs-lookup"><span data-stu-id="eaead-141">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="eaead-142">Il valore `name` dell'attributo viene utilizzato per `Listeners` aggiungere il listener condiviso a una raccolta per una traccia o un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="eaead-142">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="eaead-143">Il valore `initializeData` dell'attributo dipende dal tipo di listener creato.</span><span class="sxs-lookup"><span data-stu-id="eaead-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="eaead-144">Non tutti i listener di `initializeData`traccia richiedono l'impostazione di .</span><span class="sxs-lookup"><span data-stu-id="eaead-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eaead-145">Quando si `initializeData` utilizza l'attributo, è possibile che venga visualizzato l'avviso del compilatore "L'attributo 'initializeData' non è dichiarato".</span><span class="sxs-lookup"><span data-stu-id="eaead-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="eaead-146">Questo avviso viene generato perché le impostazioni di <xref:System.Diagnostics.TraceListener>configurazione vengono convalidate rispetto alla classe base astratta , che non riconosce l'attributo `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="eaead-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="eaead-147">In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispongono di un costruttore che accetta un parametro.</span><span class="sxs-lookup"><span data-stu-id="eaead-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="eaead-148">Nella tabella seguente vengono illustrati i listener di traccia inclusi in .NET Framework e viene descritto il valore dei relativi `initializeData` attributi.</span><span class="sxs-lookup"><span data-stu-id="eaead-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="eaead-149">Classe listener di traccia</span><span class="sxs-lookup"><span data-stu-id="eaead-149">Trace listener class</span></span>|<span data-ttu-id="eaead-150">valore dell'attributo initializeData</span><span class="sxs-lookup"><span data-stu-id="eaead-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="eaead-151">Valore `useErrorStream` per <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> il costruttore.</span><span class="sxs-lookup"><span data-stu-id="eaead-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="eaead-152">Impostare `initializeData` l'attributo su "`true`" per scrivere la traccia e l'output di debug nel flusso di errore standard; impostarlo su`false`" " per scrivere nel flusso di output standard.</span><span class="sxs-lookup"><span data-stu-id="eaead-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="eaead-153">Nome del file in cui scrive <xref:System.Diagnostics.DelimitedListTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="eaead-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="eaead-154">Nome di un'origine del log eventi esistente.</span><span class="sxs-lookup"><span data-stu-id="eaead-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="eaead-155">Nome del file in <xref:System.Diagnostics.EventSchemaTraceListener> cui viene scritto il file.</span><span class="sxs-lookup"><span data-stu-id="eaead-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="eaead-156">Nome del file in <xref:System.Diagnostics.TextWriterTraceListener> cui viene scritto il file.</span><span class="sxs-lookup"><span data-stu-id="eaead-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="eaead-157">Nome del file in <xref:System.Diagnostics.XmlWriterTraceListener> cui viene scritto il file.</span><span class="sxs-lookup"><span data-stu-id="eaead-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="eaead-158">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="eaead-158">Configuration File</span></span>  
 <span data-ttu-id="eaead-159">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine.config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eaead-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eaead-160">Esempio</span><span class="sxs-lookup"><span data-stu-id="eaead-160">Example</span></span>  
 <span data-ttu-id="eaead-161">Nell'esempio seguente viene `<add>` illustrato come <xref:System.Diagnostics.TextWriterTraceListener> `textListener` utilizzare `sharedListeners` gli elementi per aggiungere l'oggetto alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="eaead-161">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="eaead-162">`textListener`viene aggiunto in `Listeners` base al nome `TraceSourceApp`all'insieme per l'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="eaead-162">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="eaead-163">Il `textListener` listener scrive l'output di traccia nel file myListener.log.</span><span class="sxs-lookup"><span data-stu-id="eaead-163">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eaead-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eaead-164">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="eaead-165">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="eaead-165">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="eaead-166">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="eaead-166">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
