---
title: <add> Elemento per <listeners> per <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: ba0ffc4f95b9af7fcd319068501ce0bb9714c2ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089582"
---
# <a name="add-element-for-listeners-for-trace"></a><span data-ttu-id="cab2a-102">\<aggiungere > (elemento) per \<listeners > per \<traccia ></span><span class="sxs-lookup"><span data-stu-id="cab2a-102">\<add> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="cab2a-103">Aggiunge un listener per il **listener** raccolta.</span><span class="sxs-lookup"><span data-stu-id="cab2a-103">Adds a listener to the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="cab2a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cab2a-104">\<configuration></span></span>  
<span data-ttu-id="cab2a-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="cab2a-105">\<system.diagnostics></span></span>  
<span data-ttu-id="cab2a-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="cab2a-106">\<trace></span></span>  
<span data-ttu-id="cab2a-107">\<listeners></span><span class="sxs-lookup"><span data-stu-id="cab2a-107">\<listeners></span></span>  
<span data-ttu-id="cab2a-108">\<add></span><span class="sxs-lookup"><span data-stu-id="cab2a-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cab2a-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cab2a-109">Syntax</span></span>  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cab2a-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cab2a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cab2a-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cab2a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cab2a-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="cab2a-112">Attributes</span></span>  
  
|<span data-ttu-id="cab2a-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="cab2a-113">Attribute</span></span>|<span data-ttu-id="cab2a-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cab2a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cab2a-115">**type**</span><span class="sxs-lookup"><span data-stu-id="cab2a-115">**type**</span></span>|<span data-ttu-id="cab2a-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="cab2a-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="cab2a-117">Specifica il tipo del listener.</span><span class="sxs-lookup"><span data-stu-id="cab2a-117">Specifies the type of the listener.</span></span> <span data-ttu-id="cab2a-118">È necessario usare una stringa che soddisfi i requisiti specificati nelle [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="cab2a-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="cab2a-119">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="cab2a-119">**initializeData**</span></span>|<span data-ttu-id="cab2a-120">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cab2a-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="cab2a-121">La stringa passata al costruttore per la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="cab2a-121">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="cab2a-122">**name**</span><span class="sxs-lookup"><span data-stu-id="cab2a-122">**name**</span></span>|<span data-ttu-id="cab2a-123">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cab2a-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="cab2a-124">Specifica il nome del listener.</span><span class="sxs-lookup"><span data-stu-id="cab2a-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cab2a-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cab2a-125">Child Elements</span></span>  
  
|<span data-ttu-id="cab2a-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="cab2a-126">Element</span></span>|<span data-ttu-id="cab2a-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cab2a-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cab2a-128">\<filter></span><span class="sxs-lookup"><span data-stu-id="cab2a-128">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="cab2a-129">Aggiunge un filtro a un listener di `Listeners` raccolta per una traccia.</span><span class="sxs-lookup"><span data-stu-id="cab2a-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cab2a-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cab2a-130">Parent Elements</span></span>  
  
|<span data-ttu-id="cab2a-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="cab2a-131">Element</span></span>|<span data-ttu-id="cab2a-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cab2a-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cab2a-133">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cab2a-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="cab2a-134">Specifica un listener che raccoglie, archivia e indirizza i messaggi.</span><span class="sxs-lookup"><span data-stu-id="cab2a-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="cab2a-135">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="cab2a-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="cab2a-136">Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cab2a-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="cab2a-137">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="cab2a-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cab2a-138">Note</span><span class="sxs-lookup"><span data-stu-id="cab2a-138">Remarks</span></span>  
 <span data-ttu-id="cab2a-139">Il <xref:System.Diagnostics.Debug> e <xref:System.Diagnostics.Trace> condividono lo stesso **listener** raccolta.</span><span class="sxs-lookup"><span data-stu-id="cab2a-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="cab2a-140">Se si aggiunge un oggetto listener alla raccolta in una di queste classi, l'altra classe utilizza lo stesso listener.</span><span class="sxs-lookup"><span data-stu-id="cab2a-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="cab2a-141">Le classi di listener derivano dal <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="cab2a-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="cab2a-142">Se non si specifica la `name` attributo del listener di traccia, il <xref:System.Diagnostics.TraceListener.Name%2A> delle impostazioni predefinite del listener di traccia in una stringa vuota ("").</span><span class="sxs-lookup"><span data-stu-id="cab2a-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="cab2a-143">Se l'applicazione presenta un solo listener, è possibile aggiungerlo senza specificare un nome e rimuoverlo specificando una stringa vuota per il nome.</span><span class="sxs-lookup"><span data-stu-id="cab2a-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="cab2a-144">Tuttavia, se l'applicazione presenta più di un listener, è necessario specificare nomi univoci per ogni listener di traccia, che consente di identificare e gestire i listener di traccia singoli all'interno di <xref:System.Diagnostics.Debug.Listeners%2A> e <xref:System.Diagnostics.Trace.Listeners%2A> raccolte.</span><span class="sxs-lookup"><span data-stu-id="cab2a-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cab2a-145">Aggiunta più di un listener di traccia, dello stesso tipo e con lo stesso nome dei risultati in un solo listener di traccia di quel tipo e assegnare un nome viene aggiunto al `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="cab2a-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="cab2a-146">Tuttavia, è possibile aggiungere a livello di programmazione più listener identici per il `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="cab2a-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="cab2a-147">Il valore per il **initializeData** attributo dipende dal tipo di listener creato.</span><span class="sxs-lookup"><span data-stu-id="cab2a-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="cab2a-148">Non tutti i listener di traccia è necessario specificare **initializeData**.</span><span class="sxs-lookup"><span data-stu-id="cab2a-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cab2a-149">Quando si usa il `initializeData` attributo, è possibile che venga visualizzato l'avviso "non è dichiarato l'attributo 'attributo initializeData'." del compilatore</span><span class="sxs-lookup"><span data-stu-id="cab2a-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="cab2a-150">Questo avviso viene generato perché le impostazioni di configurazione vengono convalidate in base alla classe base astratta <xref:System.Diagnostics.TraceListener>, che non riconosce il `initializeData` attributo.</span><span class="sxs-lookup"><span data-stu-id="cab2a-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="cab2a-151">In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispone di un costruttore che accetta un parametro.</span><span class="sxs-lookup"><span data-stu-id="cab2a-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="cab2a-152">Nella tabella seguente mostra i listener di traccia incluse in .NET Framework e descrive il valore della loro **initializeData** attributi.</span><span class="sxs-lookup"><span data-stu-id="cab2a-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="cab2a-153">Classe di listener di traccia</span><span class="sxs-lookup"><span data-stu-id="cab2a-153">Trace listener class</span></span>|<span data-ttu-id="cab2a-154">valore dell'attributo initializeData</span><span class="sxs-lookup"><span data-stu-id="cab2a-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="cab2a-155">Il `useErrorStream` valore per il <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="cab2a-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="cab2a-156">Impostare il `initializeData` dell'attributo "`true`" per scrivere analisi e debug di output per <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" in cui scrivere <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cab2a-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="cab2a-157">Il nome del file di <xref:System.Diagnostics.DelimitedListTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="cab2a-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="cab2a-158">Il nome del nome di un'origine di log eventi esistente.</span><span class="sxs-lookup"><span data-stu-id="cab2a-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="cab2a-159">Il nome del file che il <xref:System.Diagnostics.EventSchemaTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="cab2a-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="cab2a-160">Il nome del file che il <xref:System.Diagnostics.TextWriterTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="cab2a-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="cab2a-161">Il nome del file che il <xref:System.Diagnostics.XmlWriterTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="cab2a-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cab2a-162">Esempio</span><span class="sxs-lookup"><span data-stu-id="cab2a-162">Example</span></span>  
 <span data-ttu-id="cab2a-163">Nell'esempio seguente viene illustrato come utilizzare  **\<Aggiungi >** elementi da aggiungere i listener `MyListener` e `MyEventListener` per il **listener** raccolta.</span><span class="sxs-lookup"><span data-stu-id="cab2a-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="cab2a-164">`MyListener` Crea un file denominato `MyListener.log` e scrive l'output del file.</span><span class="sxs-lookup"><span data-stu-id="cab2a-164">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="cab2a-165">`MyEventListener` Crea una voce nel registro eventi.</span><span class="sxs-lookup"><span data-stu-id="cab2a-165">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cab2a-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cab2a-166">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [<span data-ttu-id="cab2a-167">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="cab2a-167">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="cab2a-168">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="cab2a-168">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
