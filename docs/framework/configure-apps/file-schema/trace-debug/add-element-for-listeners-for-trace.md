---
title: <add>Elemento per <listeners> per<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: d4ff919991ab1505b2845a225706d32cc1e57d0a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920576"
---
# <a name="add-element-for-listeners-for-trace"></a><span data-ttu-id="4ceb6-102">\<aggiungere > elemento per \<i listener > per \<la traccia ></span><span class="sxs-lookup"><span data-stu-id="4ceb6-102">\<add> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="4ceb6-103">Aggiunge un listener alla raccolta **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="4ceb6-103">Adds a listener to the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="4ceb6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4ceb6-104">\<configuration></span></span>  
<span data-ttu-id="4ceb6-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="4ceb6-105">\<system.diagnostics></span></span>  
<span data-ttu-id="4ceb6-106">\<traccia ></span><span class="sxs-lookup"><span data-stu-id="4ceb6-106">\<trace></span></span>  
<span data-ttu-id="4ceb6-107">\<listener ></span><span class="sxs-lookup"><span data-stu-id="4ceb6-107">\<listeners></span></span>  
<span data-ttu-id="4ceb6-108">\<add></span><span class="sxs-lookup"><span data-stu-id="4ceb6-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ceb6-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4ceb6-109">Syntax</span></span>  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ceb6-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4ceb6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4ceb6-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ceb6-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="4ceb6-112">Attributes</span></span>  
  
|<span data-ttu-id="4ceb6-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="4ceb6-113">Attribute</span></span>|<span data-ttu-id="4ceb6-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="4ceb6-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4ceb6-115">**type**</span><span class="sxs-lookup"><span data-stu-id="4ceb6-115">**type**</span></span>|<span data-ttu-id="4ceb6-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="4ceb6-117">Specifica il tipo di listener.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-117">Specifies the type of the listener.</span></span> <span data-ttu-id="4ceb6-118">È necessario usare una stringa che soddisfi i requisiti specificati per [specificare nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="4ceb6-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="4ceb6-119">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="4ceb6-119">**initializeData**</span></span>|<span data-ttu-id="4ceb6-120">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4ceb6-121">Stringa passata al costruttore per la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-121">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="4ceb6-122">**name**</span><span class="sxs-lookup"><span data-stu-id="4ceb6-122">**name**</span></span>|<span data-ttu-id="4ceb6-123">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4ceb6-124">Specifica il nome del listener.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ceb6-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4ceb6-125">Child Elements</span></span>  
  
|<span data-ttu-id="4ceb6-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="4ceb6-126">Element</span></span>|<span data-ttu-id="4ceb6-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ceb6-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ceb6-128">\<filter></span><span class="sxs-lookup"><span data-stu-id="4ceb6-128">\<filter></span></span>](filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="4ceb6-129">Aggiunge un filtro a un listener nella `Listeners` raccolta per una traccia.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4ceb6-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4ceb6-130">Parent Elements</span></span>  
  
|<span data-ttu-id="4ceb6-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="4ceb6-131">Element</span></span>|<span data-ttu-id="4ceb6-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ceb6-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4ceb6-133">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="4ceb6-134">Specifica un listener che raccoglie, archivia e instrada i messaggi.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="4ceb6-135">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="4ceb6-136">Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="4ceb6-137">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ceb6-138">Note</span><span class="sxs-lookup"><span data-stu-id="4ceb6-138">Remarks</span></span>  
 <span data-ttu-id="4ceb6-139">Le <xref:System.Diagnostics.Debug> classi <xref:System.Diagnostics.Trace> e condividono la stessa raccolta Listeners.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="4ceb6-140">Se si aggiunge un oggetto listener alla raccolta in una di queste classi, l'altra classe utilizzerà lo stesso listener.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="4ceb6-141">Le classi del listener derivano <xref:System.Diagnostics.TraceListener>da.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="4ceb6-142">Se non si specifica l' `name` attributo del listener di traccia, il <xref:System.Diagnostics.TraceListener.Name%2A> valore predefinito di per il listener di traccia è una stringa vuota ("").</span><span class="sxs-lookup"><span data-stu-id="4ceb6-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="4ceb6-143">Se l'applicazione dispone di un solo listener, è possibile aggiungerlo senza specificare un nome e rimuoverlo specificando una stringa vuota per il nome.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="4ceb6-144">Tuttavia, se l'applicazione ha più di un listener, è necessario specificare nomi univoci per ogni listener di traccia, che consente di identificare e gestire i singoli listener di traccia <xref:System.Diagnostics.Debug.Listeners%2A> all' <xref:System.Diagnostics.Trace.Listeners%2A> interno delle raccolte e.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4ceb6-145">L'aggiunta di più listener di traccia dello stesso tipo e con lo stesso nome comporta l'aggiunta di un solo listener di traccia del tipo e del nome alla `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="4ceb6-146">Tuttavia, è possibile aggiungere a livello di codice più listener identici `Listeners` alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="4ceb6-147">Il valore dell'attributo **initializeData** dipende dal tipo di listener creato.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="4ceb6-148">Non tutti i listener di traccia richiedono che venga specificato **initializeData**.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4ceb6-149">Quando si usa l' `initializeData` attributo, è possibile che venga visualizzato l'avviso del compilatore "l'attributo ' initializeData ' non è dichiarato".</span><span class="sxs-lookup"><span data-stu-id="4ceb6-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="4ceb6-150">Questo avviso si verifica perché le impostazioni di configurazione vengono convalidate rispetto alla <xref:System.Diagnostics.TraceListener>classe di base astratta, che `initializeData` non riconosce l'attributo.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="4ceb6-151">In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispongono di un costruttore che accetta un parametro.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="4ceb6-152">Nella tabella seguente vengono illustrati i listener di traccia inclusi nel .NET Framework e viene descritto il valore degli attributi **initializeData** .</span><span class="sxs-lookup"><span data-stu-id="4ceb6-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="4ceb6-153">Classe listener di traccia</span><span class="sxs-lookup"><span data-stu-id="4ceb6-153">Trace listener class</span></span>|<span data-ttu-id="4ceb6-154">valore dell'attributo initializeData</span><span class="sxs-lookup"><span data-stu-id="4ceb6-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="4ceb6-155">Valore per il <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>costruttore. `useErrorStream`</span><span class="sxs-lookup"><span data-stu-id="4ceb6-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="4ceb6-156">Impostare l' `initializeData` attributo su "`true`" per scrivere l'output di traccia ed <xref:System.Console.Error%2A?displayProperty=nameWithType>eseguire il debug in; "`false`" in cui <xref:System.Console.Out%2A?displayProperty=nameWithType>scrivere.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="4ceb6-157">Nome del file <xref:System.Diagnostics.DelimitedListTraceListener> in cui scrive.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="4ceb6-158">Nome del nome di un'origine del log eventi esistente.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="4ceb6-159">Nome del file in cui <xref:System.Diagnostics.EventSchemaTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="4ceb6-160">Nome del file in cui <xref:System.Diagnostics.TextWriterTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="4ceb6-161">Nome del file in cui <xref:System.Diagnostics.XmlWriterTraceListener> scrive.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4ceb6-162">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ceb6-162">Example</span></span>  
 <span data-ttu-id="4ceb6-163">Nell'esempio seguente viene illustrato come utilizzare `MyListener` `MyEventListener`  **\<gli elementi add >** per aggiungere i listener e alla raccolta Listeners.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="4ceb6-164">`MyListener`Crea un file denominato `MyListener.log` e scrive l'output nel file.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-164">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="4ceb6-165">`MyEventListener`Crea una voce nel log eventi.</span><span class="sxs-lookup"><span data-stu-id="4ceb6-165">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4ceb6-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ceb6-166">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [<span data-ttu-id="4ceb6-167">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="4ceb6-167">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4ceb6-168">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="4ceb6-168">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
