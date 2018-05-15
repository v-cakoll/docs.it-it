---
title: '&lt;aggiungere&gt; elemento per &lt;listener&gt; per &lt;traccia&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e27187c05b49b7f73ef19243a3286e8c1de71579
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="94907-102">&lt;aggiungere&gt; elemento per &lt;listener&gt; per &lt;traccia&gt;</span><span class="sxs-lookup"><span data-stu-id="94907-102">&lt;add&gt; Element for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="94907-103">Aggiunge un listener per il **listener** insieme.</span><span class="sxs-lookup"><span data-stu-id="94907-103">Adds a listener to the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="94907-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="94907-104">\<configuration></span></span>  
<span data-ttu-id="94907-105">\<System. Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="94907-105">\<system.diagnostics></span></span>  
<span data-ttu-id="94907-106">\<traccia ></span><span class="sxs-lookup"><span data-stu-id="94907-106">\<trace></span></span>  
<span data-ttu-id="94907-107">\<listener ></span><span class="sxs-lookup"><span data-stu-id="94907-107">\<listeners></span></span>  
<span data-ttu-id="94907-108">\<add></span><span class="sxs-lookup"><span data-stu-id="94907-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94907-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94907-109">Syntax</span></span>  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94907-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="94907-110">Attributes and Elements</span></span>  
 <span data-ttu-id="94907-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="94907-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94907-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="94907-112">Attributes</span></span>  
  
|<span data-ttu-id="94907-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="94907-113">Attribute</span></span>|<span data-ttu-id="94907-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94907-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="94907-115">**type**</span><span class="sxs-lookup"><span data-stu-id="94907-115">**type**</span></span>|<span data-ttu-id="94907-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="94907-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="94907-117">Specifica il tipo del listener.</span><span class="sxs-lookup"><span data-stu-id="94907-117">Specifies the type of the listener.</span></span> <span data-ttu-id="94907-118">È necessario utilizzare una stringa che soddisfi i requisiti indicati in [specifica di nomi di tipo completi](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="94907-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="94907-119">**attributo initializeData**</span><span class="sxs-lookup"><span data-stu-id="94907-119">**initializeData**</span></span>|<span data-ttu-id="94907-120">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="94907-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="94907-121">La stringa passata al costruttore per la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="94907-121">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="94907-122">**name**</span><span class="sxs-lookup"><span data-stu-id="94907-122">**name**</span></span>|<span data-ttu-id="94907-123">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="94907-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="94907-124">Specifica il nome del listener.</span><span class="sxs-lookup"><span data-stu-id="94907-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="94907-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="94907-125">Child Elements</span></span>  
  
|<span data-ttu-id="94907-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="94907-126">Element</span></span>|<span data-ttu-id="94907-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94907-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94907-128">\<filter></span><span class="sxs-lookup"><span data-stu-id="94907-128">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="94907-129">Aggiunge un filtro a un listener di `Listeners` insieme per una traccia.</span><span class="sxs-lookup"><span data-stu-id="94907-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="94907-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="94907-130">Parent Elements</span></span>  
  
|<span data-ttu-id="94907-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="94907-131">Element</span></span>|<span data-ttu-id="94907-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94907-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="94907-133">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="94907-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="94907-134">Specifica un listener per la raccolta, la memorizzazione e indirizza i messaggi.</span><span class="sxs-lookup"><span data-stu-id="94907-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="94907-135">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="94907-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="94907-136">Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="94907-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="94907-137">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="94907-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94907-138">Note</span><span class="sxs-lookup"><span data-stu-id="94907-138">Remarks</span></span>  
 <span data-ttu-id="94907-139">Il <xref:System.Diagnostics.Debug> e <xref:System.Diagnostics.Trace> condividono lo stesso **listener** insieme.</span><span class="sxs-lookup"><span data-stu-id="94907-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="94907-140">Se si aggiunge un oggetto listener alla raccolta in una di queste classi, l'altra classe utilizza lo stesso listener.</span><span class="sxs-lookup"><span data-stu-id="94907-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="94907-141">Derivano le classi di listener di <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="94907-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="94907-142">Se non si specifica il `name` attributo del listener di traccia, il <xref:System.Diagnostics.TraceListener.Name%2A> delle impostazioni predefinite del listener di traccia in una stringa vuota ("").</span><span class="sxs-lookup"><span data-stu-id="94907-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="94907-143">Se l'applicazione presenta un solo listener, è possibile aggiungerlo senza specificare un nome e rimuoverlo specificando una stringa vuota per il nome.</span><span class="sxs-lookup"><span data-stu-id="94907-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="94907-144">Tuttavia, se l'applicazione presenta più di un listener, è necessario specificare nomi univoci per ogni listener di traccia, che consente di identificare e gestire singoli listener di traccia all'interno di <xref:System.Diagnostics.Debug.Listeners%2A> e <xref:System.Diagnostics.Trace.Listeners%2A> raccolte.</span><span class="sxs-lookup"><span data-stu-id="94907-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94907-145">Aggiunta di più di un listener di traccia, dello stesso tipo e con lo stesso nome risultati in un solo listener di traccia di quel tipo e nome viene aggiunto al `Listeners` insieme.</span><span class="sxs-lookup"><span data-stu-id="94907-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="94907-146">Tuttavia, è possibile aggiungere a livello di codice più listener identici per il `Listeners` insieme.</span><span class="sxs-lookup"><span data-stu-id="94907-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="94907-147">Il valore per il **initializeData** attributo dipende dal tipo di listener creato.</span><span class="sxs-lookup"><span data-stu-id="94907-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="94907-148">Non tutti i listener di traccia è necessario specificare **initializeData**.</span><span class="sxs-lookup"><span data-stu-id="94907-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94907-149">Quando si utilizza il `initializeData` attributo, è possibile che venga visualizzato l'avviso "l'attributo 'initializeData' non dichiarato." del compilatore</span><span class="sxs-lookup"><span data-stu-id="94907-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="94907-150">Questo avviso viene generato perché le impostazioni di configurazione vengono convalidate in base alla classe base astratta <xref:System.Diagnostics.TraceListener>, che non riconosce il `initializeData` attributo.</span><span class="sxs-lookup"><span data-stu-id="94907-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="94907-151">In genere, è possibile ignorare questo avviso per le implementazioni di listener di traccia che dispone di un costruttore che accetta un parametro.</span><span class="sxs-lookup"><span data-stu-id="94907-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="94907-152">Nella tabella seguente mostra i listener di traccia inclusi in .NET Framework e descrive il valore della loro **initializeData** attributi.</span><span class="sxs-lookup"><span data-stu-id="94907-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="94907-153">Classe di listener di traccia</span><span class="sxs-lookup"><span data-stu-id="94907-153">Trace listener class</span></span>|<span data-ttu-id="94907-154">valore dell'attributo initializeData</span><span class="sxs-lookup"><span data-stu-id="94907-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="94907-155">Il `useErrorStream` valore per il <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="94907-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="94907-156">Impostare il `initializeData` attributo "`true`" per scrivere una traccia e debug di output per <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" per scrivere <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="94907-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="94907-157">Il nome del file di <xref:System.Diagnostics.DelimitedListTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="94907-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="94907-158">Il nome del nome di un'origine di log eventi esistenti.</span><span class="sxs-lookup"><span data-stu-id="94907-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="94907-159">Il nome del file che il <xref:System.Diagnostics.EventSchemaTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="94907-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="94907-160">Il nome del file che il <xref:System.Diagnostics.TextWriterTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="94907-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="94907-161">Il nome del file che il <xref:System.Diagnostics.XmlWriterTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="94907-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="94907-162">Esempio</span><span class="sxs-lookup"><span data-stu-id="94907-162">Example</span></span>  
 <span data-ttu-id="94907-163">Nell'esempio seguente viene illustrato come utilizzare  **\<aggiungere >** elementi per aggiungere i listener `MyListener` e `MyEventListener` per il **listener** insieme.</span><span class="sxs-lookup"><span data-stu-id="94907-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="94907-164">`MyListener` Crea un file denominato `MyListener.log` e scrive l'output al file.</span><span class="sxs-lookup"><span data-stu-id="94907-164">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="94907-165">`MyEventListener` Crea una voce nel registro eventi.</span><span class="sxs-lookup"><span data-stu-id="94907-165">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
            <add name="MyEventListener"  
                 type="System.Diagnostics.EventLogTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"                 initializeData="MyConfigEventLog"/>  
            <add name="configConsoleListener"  
                 type="System.Diagnostics.ConsoleTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="94907-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94907-166">See Also</span></span>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 [<span data-ttu-id="94907-167">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="94907-167">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="94907-168">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="94907-168">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
