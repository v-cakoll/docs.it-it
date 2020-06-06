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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153607"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="88b6a-102">Elemento \<add> per \<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="88b6a-102">\<add> Element for \<sharedListeners></span></span>
<span data-ttu-id="88b6a-103">Aggiunge un listener alla raccolta `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="88b6a-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="88b6a-104">`sharedListeners`è una raccolta di listener a cui è [\<source>](source-element.md) [\<trace>](trace-element.md) possibile fare riferimento o.</span><span class="sxs-lookup"><span data-stu-id="88b6a-104">`sharedListeners` is a collection of listeners that any [\<source>](source-element.md) or [\<trace>](trace-element.md) can reference.</span></span>  <span data-ttu-id="88b6a-105">Per impostazione predefinita, i listener nella `sharedListeners` raccolta non vengono inseriti in una `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="88b6a-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="88b6a-106">Devono essere aggiunti per nome a [\<source>](source-element.md) o [\<trace>](trace-element.md) .</span><span class="sxs-lookup"><span data-stu-id="88b6a-106">They must be added by name to the [\<source>](source-element.md) or [\<trace>](trace-element.md).</span></span> <span data-ttu-id="88b6a-107">Non è possibile ottenere i listener nella `sharedListeners` raccolta nel codice in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="88b6a-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="88b6a-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="88b6a-108">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88b6a-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="88b6a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="88b6a-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="88b6a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88b6a-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="88b6a-111">Attributes</span></span>  
  
|<span data-ttu-id="88b6a-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="88b6a-112">Attribute</span></span>|<span data-ttu-id="88b6a-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="88b6a-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="88b6a-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="88b6a-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="88b6a-115">Specifica il nome del listener utilizzato per aggiungere il listener condiviso a una `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="88b6a-115">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="88b6a-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="88b6a-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="88b6a-117">Specifica il tipo di listener.</span><span class="sxs-lookup"><span data-stu-id="88b6a-117">Specifies the type of the listener.</span></span> <span data-ttu-id="88b6a-118">È necessario usare una stringa che soddisfi i requisiti specificati per [specificare nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="88b6a-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="88b6a-119">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="88b6a-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="88b6a-120">Stringa passata al costruttore per la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="88b6a-120">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="88b6a-121">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="88b6a-121">Optional attribute.</span></span><br/><br/><span data-ttu-id="88b6a-122">Rappresentazione di stringa di uno o più <xref:System.Diagnostics.TraceOptions> membri dell'enumerazione che indica i dati da scrivere nell'output di traccia.</span><span class="sxs-lookup"><span data-stu-id="88b6a-122">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="88b6a-123">Più elementi sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="88b6a-123">Multiple items are separated by commas.</span></span> <span data-ttu-id="88b6a-124">Il valore predefinito è "None".</span><span class="sxs-lookup"><span data-stu-id="88b6a-124">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="88b6a-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="88b6a-125">Child Elements</span></span>  
  
|<span data-ttu-id="88b6a-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="88b6a-126">Element</span></span>|<span data-ttu-id="88b6a-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="88b6a-127">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="88b6a-128">Aggiunge un filtro a un listener nella raccolta `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="88b6a-128">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="88b6a-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="88b6a-129">Parent Elements</span></span>  
  
|<span data-ttu-id="88b6a-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="88b6a-130">Element</span></span>|<span data-ttu-id="88b6a-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="88b6a-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="88b6a-132">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="88b6a-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="88b6a-133">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="88b6a-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="88b6a-134">Raccolta di listener a cui qualsiasi origine o elemento Trace può fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="88b6a-134">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88b6a-135">Commenti</span><span class="sxs-lookup"><span data-stu-id="88b6a-135">Remarks</span></span>  
 <span data-ttu-id="88b6a-136">Le classi del listener fornite con la .NET Framework derivano dalla <xref:System.Diagnostics.TraceListener> classe.</span><span class="sxs-lookup"><span data-stu-id="88b6a-136">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="88b6a-137">Il valore per l' `name` attributo viene utilizzato per aggiungere il listener condiviso a una `Listeners` raccolta per una traccia o un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="88b6a-137">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="88b6a-138">Il valore dell' `initializeData` attributo dipende dal tipo di listener creato.</span><span class="sxs-lookup"><span data-stu-id="88b6a-138">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="88b6a-139">Non tutti i listener di traccia richiedono che venga specificato `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="88b6a-139">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="88b6a-140">Quando si usa l' `initializeData` attributo, è possibile che venga visualizzato l'avviso del compilatore "l'attributo ' initializeData ' non è dichiarato".</span><span class="sxs-lookup"><span data-stu-id="88b6a-140">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="88b6a-141">Questo avviso si verifica perché le impostazioni di configurazione vengono convalidate rispetto alla classe di base astratta <xref:System.Diagnostics.TraceListener> , che non riconosce l' `initializeData` attributo.</span><span class="sxs-lookup"><span data-stu-id="88b6a-141">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="88b6a-142">In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispongono di un costruttore che accetta un parametro.</span><span class="sxs-lookup"><span data-stu-id="88b6a-142">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="88b6a-143">Nella tabella seguente vengono illustrati i listener di traccia inclusi nel .NET Framework e viene descritto il valore dei rispettivi `initializeData` attributi.</span><span class="sxs-lookup"><span data-stu-id="88b6a-143">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="88b6a-144">Classe listener di traccia</span><span class="sxs-lookup"><span data-stu-id="88b6a-144">Trace listener class</span></span>|<span data-ttu-id="88b6a-145">valore dell'attributo initializeData</span><span class="sxs-lookup"><span data-stu-id="88b6a-145">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="88b6a-146">`useErrorStream`Valore per il <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="88b6a-146">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="88b6a-147">Impostare l' `initializeData` attributo su " `true` " per scrivere l'output di traccia e di debug nel flusso di errore standard. impostarlo su " `false` " per scrivere nel flusso di output standard.</span><span class="sxs-lookup"><span data-stu-id="88b6a-147">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="88b6a-148">Nome del file in cui scrive <xref:System.Diagnostics.DelimitedListTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="88b6a-148">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="88b6a-149">Nome di un'origine del log eventi esistente.</span><span class="sxs-lookup"><span data-stu-id="88b6a-149">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="88b6a-150">Nome del file <xref:System.Diagnostics.EventSchemaTraceListener> in cui scrive.</span><span class="sxs-lookup"><span data-stu-id="88b6a-150">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="88b6a-151">Nome del file <xref:System.Diagnostics.TextWriterTraceListener> in cui scrive.</span><span class="sxs-lookup"><span data-stu-id="88b6a-151">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="88b6a-152">Nome del file <xref:System.Diagnostics.XmlWriterTraceListener> in cui scrive.</span><span class="sxs-lookup"><span data-stu-id="88b6a-152">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="88b6a-153">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="88b6a-153">Configuration File</span></span>  
 <span data-ttu-id="88b6a-154">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="88b6a-154">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88b6a-155">Esempio</span><span class="sxs-lookup"><span data-stu-id="88b6a-155">Example</span></span>  
 <span data-ttu-id="88b6a-156">Nell'esempio seguente viene illustrato come utilizzare `<add>` gli elementi per aggiungere l'oggetto <xref:System.Diagnostics.TextWriterTraceListener> `textListener` alla `sharedListeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="88b6a-156">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="88b6a-157">`textListener`viene aggiunto per nome alla `Listeners` raccolta per l'origine di traccia `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="88b6a-157">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="88b6a-158">Il `textListener` listener scrive l'output di traccia nel file listener. log.</span><span class="sxs-lookup"><span data-stu-id="88b6a-158">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="88b6a-159">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="88b6a-159">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="88b6a-160">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="88b6a-160">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="88b6a-161">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="88b6a-161">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
