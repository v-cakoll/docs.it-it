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
ms.openlocfilehash: 0c7665898f8c625c2d07b67ea6c7fe25113fddd8
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699481"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="e94dd-102">Elemento > \<add per \<sharedListeners ></span><span class="sxs-lookup"><span data-stu-id="e94dd-102">\<add> Element for \<sharedListeners></span></span>
<span data-ttu-id="e94dd-103">Aggiunge un listener alla raccolta `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="e94dd-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="e94dd-104">`sharedListeners` è una raccolta di listener a cui può fare riferimento qualsiasi [\<source >](source-element.md) o [\<trace >](trace-element.md) .</span><span class="sxs-lookup"><span data-stu-id="e94dd-104">`sharedListeners` is a collection of listeners that any [\<source>](source-element.md) or [\<trace>](trace-element.md) can reference.</span></span>  <span data-ttu-id="e94dd-105">Per impostazione predefinita, i listener nella raccolta `sharedListeners` non vengono inseriti in una raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="e94dd-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="e94dd-106">Devono essere aggiunti per nome al [> \<SOURCE](source-element.md) o [\<trace >](trace-element.md).</span><span class="sxs-lookup"><span data-stu-id="e94dd-106">They must be added by name to the [\<source>](source-element.md) or [\<trace>](trace-element.md).</span></span> <span data-ttu-id="e94dd-107">Non è possibile ottenere i listener nella raccolta `sharedListeners` nel codice in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e94dd-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  
  
[<span data-ttu-id="e94dd-108"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="e94dd-108">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="e94dd-109">&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="e94dd-109">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="e94dd-110">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<sharedListeners >** ](sharedlisteners-element.md)</span><span class="sxs-lookup"><span data-stu-id="e94dd-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)</span></span>  
<span data-ttu-id="e94dd-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="e94dd-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e94dd-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e94dd-112">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e94dd-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e94dd-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e94dd-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e94dd-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e94dd-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="e94dd-115">Attributes</span></span>  
  
|<span data-ttu-id="e94dd-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="e94dd-116">Attribute</span></span>|<span data-ttu-id="e94dd-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e94dd-117">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="e94dd-118">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e94dd-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="e94dd-119">Specifica il nome del listener utilizzato per aggiungere il listener condiviso a una raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="e94dd-119">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="e94dd-120">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e94dd-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="e94dd-121">Specifica il tipo di listener.</span><span class="sxs-lookup"><span data-stu-id="e94dd-121">Specifies the type of the listener.</span></span> <span data-ttu-id="e94dd-122">È necessario usare una stringa che soddisfi i requisiti specificati per [specificare nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="e94dd-122">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="e94dd-123">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e94dd-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e94dd-124">Stringa passata al costruttore per la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="e94dd-124">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="e94dd-125">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e94dd-125">Optional attribute.</span></span><br/><br/><span data-ttu-id="e94dd-126">Rappresentazione di stringa di uno o più membri dell'enumerazione <xref:System.Diagnostics.TraceOptions> che indica i dati da scrivere nell'output di traccia.</span><span class="sxs-lookup"><span data-stu-id="e94dd-126">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="e94dd-127">Più elementi sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="e94dd-127">Multiple items are separated by commas.</span></span> <span data-ttu-id="e94dd-128">Il valore predefinito è "None".</span><span class="sxs-lookup"><span data-stu-id="e94dd-128">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="e94dd-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e94dd-129">Child Elements</span></span>  
  
|<span data-ttu-id="e94dd-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="e94dd-130">Element</span></span>|<span data-ttu-id="e94dd-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e94dd-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e94dd-132">\<filter></span><span class="sxs-lookup"><span data-stu-id="e94dd-132">\<filter></span></span>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="e94dd-133">Aggiunge un filtro a un listener nella raccolta `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="e94dd-133">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e94dd-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e94dd-134">Parent Elements</span></span>  
  
|<span data-ttu-id="e94dd-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="e94dd-135">Element</span></span>|<span data-ttu-id="e94dd-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e94dd-136">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e94dd-137">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e94dd-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="e94dd-138">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="e94dd-138">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="e94dd-139">Raccolta di listener a cui qualsiasi origine o elemento Trace può fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="e94dd-139">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e94dd-140">Note</span><span class="sxs-lookup"><span data-stu-id="e94dd-140">Remarks</span></span>  
 <span data-ttu-id="e94dd-141">Le classi del listener fornite con la .NET Framework derivano dalla classe <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="e94dd-141">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="e94dd-142">Il valore per l'attributo `name` viene utilizzato per aggiungere il listener condiviso a una raccolta `Listeners` per una traccia o un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="e94dd-142">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="e94dd-143">Il valore dell'attributo `initializeData` dipende dal tipo di listener creato.</span><span class="sxs-lookup"><span data-stu-id="e94dd-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="e94dd-144">Non tutti i listener di traccia richiedono di specificare `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="e94dd-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e94dd-145">Quando si usa l'attributo `initializeData`, è possibile che venga visualizzato l'avviso del compilatore "l'attributo ' initializeData ' non è dichiarato".</span><span class="sxs-lookup"><span data-stu-id="e94dd-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="e94dd-146">Questo avviso si verifica perché le impostazioni di configurazione vengono convalidate rispetto alla classe di base astratta <xref:System.Diagnostics.TraceListener>, che non riconosce l'attributo `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="e94dd-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="e94dd-147">In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispongono di un costruttore che accetta un parametro.</span><span class="sxs-lookup"><span data-stu-id="e94dd-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="e94dd-148">Nella tabella seguente vengono illustrati i listener di traccia inclusi nel .NET Framework e viene descritto il valore degli attributi `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="e94dd-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="e94dd-149">Classe listener di traccia</span><span class="sxs-lookup"><span data-stu-id="e94dd-149">Trace listener class</span></span>|<span data-ttu-id="e94dd-150">valore dell'attributo initializeData</span><span class="sxs-lookup"><span data-stu-id="e94dd-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="e94dd-151">Valore `useErrorStream` per il costruttore <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.</span><span class="sxs-lookup"><span data-stu-id="e94dd-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="e94dd-152">Impostare l'attributo `initializeData` su "`true`" per scrivere l'output di traccia e di debug nel flusso di errore standard. impostarla su "`false`" per scrivere nel flusso di output standard.</span><span class="sxs-lookup"><span data-stu-id="e94dd-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="e94dd-153">Nome del file in cui viene scritto <xref:System.Diagnostics.DelimitedListTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="e94dd-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="e94dd-154">Nome di un'origine del log eventi esistente.</span><span class="sxs-lookup"><span data-stu-id="e94dd-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="e94dd-155">Nome del file in cui viene scritto il <xref:System.Diagnostics.EventSchemaTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="e94dd-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="e94dd-156">Nome del file in cui viene scritto il <xref:System.Diagnostics.TextWriterTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="e94dd-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="e94dd-157">Nome del file in cui viene scritto il <xref:System.Diagnostics.XmlWriterTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="e94dd-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="e94dd-158">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="e94dd-158">Configuration File</span></span>  
 <span data-ttu-id="e94dd-159">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e94dd-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e94dd-160">Esempio</span><span class="sxs-lookup"><span data-stu-id="e94dd-160">Example</span></span>  
 <span data-ttu-id="e94dd-161">Nell'esempio seguente viene illustrato come utilizzare gli elementi `<add>` per aggiungere la <xref:System.Diagnostics.TextWriterTraceListener> @ no__t-2 alla raccolta `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="e94dd-161">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="e94dd-162">`textListener` viene aggiunto per nome alla raccolta `Listeners` per l'origine di traccia `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="e94dd-162">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="e94dd-163">Il listener `textListener` scrive l'output di traccia nel file listener. log.</span><span class="sxs-lookup"><span data-stu-id="e94dd-163">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e94dd-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e94dd-164">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="e94dd-165">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="e94dd-165">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e94dd-166">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="e94dd-166">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
