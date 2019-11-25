---
title: Elemento <add> per <listeners> per <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: eb3e9cf4a6d138998cfde865cda8ed4146be26d0
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088988"
---
# <a name="add-element-for-listeners-for-trace"></a><span data-ttu-id="58971-102">\<aggiungere > elemento per \<listener > per \<traccia ></span><span class="sxs-lookup"><span data-stu-id="58971-102">\<add> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="58971-103">Aggiunge un listener alla raccolta **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="58971-103">Adds a listener to the **Listeners** collection.</span></span>  

<span data-ttu-id="58971-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="58971-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="58971-105">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="58971-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="58971-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**Trace**](trace-element.md) ></span><span class="sxs-lookup"><span data-stu-id="58971-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\</span></span>
<span data-ttu-id="58971-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**listener**](listeners-element-for-trace.md)\<</span><span class="sxs-lookup"><span data-stu-id="58971-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\</span></span>
<span data-ttu-id="58971-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="58971-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="58971-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58971-109">Syntax</span></span>  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58971-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="58971-110">Attributes and Elements</span></span>  
 <span data-ttu-id="58971-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="58971-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58971-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="58971-112">Attributes</span></span>  
  
|<span data-ttu-id="58971-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="58971-113">Attribute</span></span>|<span data-ttu-id="58971-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58971-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="58971-115">**type**</span><span class="sxs-lookup"><span data-stu-id="58971-115">**type**</span></span>|<span data-ttu-id="58971-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="58971-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="58971-117">Specifica il tipo di listener.</span><span class="sxs-lookup"><span data-stu-id="58971-117">Specifies the type of the listener.</span></span> <span data-ttu-id="58971-118">È necessario usare una stringa che soddisfi i requisiti specificati per [specificare nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="58971-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="58971-119">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="58971-119">**initializeData**</span></span>|<span data-ttu-id="58971-120">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="58971-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="58971-121">Stringa passata al costruttore per la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="58971-121">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="58971-122">**name**</span><span class="sxs-lookup"><span data-stu-id="58971-122">**name**</span></span>|<span data-ttu-id="58971-123">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="58971-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="58971-124">Specifica il nome del listener.</span><span class="sxs-lookup"><span data-stu-id="58971-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58971-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="58971-125">Child Elements</span></span>  
  
|<span data-ttu-id="58971-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="58971-126">Element</span></span>|<span data-ttu-id="58971-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58971-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58971-128">\<filter></span><span class="sxs-lookup"><span data-stu-id="58971-128">\<filter></span></span>](filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="58971-129">Aggiunge un filtro a un listener nella raccolta `Listeners` per una traccia.</span><span class="sxs-lookup"><span data-stu-id="58971-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="58971-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="58971-130">Parent Elements</span></span>  
  
|<span data-ttu-id="58971-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="58971-131">Element</span></span>|<span data-ttu-id="58971-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58971-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="58971-133">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="58971-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="58971-134">Specifica un listener che raccoglie, archivia e instrada i messaggi.</span><span class="sxs-lookup"><span data-stu-id="58971-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="58971-135">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="58971-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="58971-136">Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="58971-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="58971-137">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="58971-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58971-138">Note</span><span class="sxs-lookup"><span data-stu-id="58971-138">Remarks</span></span>  
 <span data-ttu-id="58971-139">Le classi <xref:System.Diagnostics.Debug> e <xref:System.Diagnostics.Trace> condividono la stessa raccolta **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="58971-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="58971-140">Se si aggiunge un oggetto listener alla raccolta in una di queste classi, l'altra classe utilizzerà lo stesso listener.</span><span class="sxs-lookup"><span data-stu-id="58971-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="58971-141">Le classi listener derivano dalla <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="58971-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="58971-142">Se non si specifica l'attributo `name` del listener di traccia, il <xref:System.Diagnostics.TraceListener.Name%2A> del listener di traccia viene impostato come valore predefinito su una stringa vuota ("").</span><span class="sxs-lookup"><span data-stu-id="58971-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="58971-143">Se l'applicazione dispone di un solo listener, è possibile aggiungerlo senza specificare un nome e rimuoverlo specificando una stringa vuota per il nome.</span><span class="sxs-lookup"><span data-stu-id="58971-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="58971-144">Tuttavia, se l'applicazione ha più di un listener, è necessario specificare nomi univoci per ogni listener di traccia, che consente di identificare e gestire i singoli listener di traccia all'interno delle raccolte <xref:System.Diagnostics.Debug.Listeners%2A> e <xref:System.Diagnostics.Trace.Listeners%2A>.</span><span class="sxs-lookup"><span data-stu-id="58971-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="58971-145">L'aggiunta di più listener di traccia dello stesso tipo e con lo stesso nome comporta l'aggiunta di un solo listener di traccia di quel tipo e del nome alla raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="58971-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="58971-146">Tuttavia, è possibile aggiungere a livello di codice più listener identici alla raccolta di `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="58971-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="58971-147">Il valore dell'attributo **initializeData** dipende dal tipo di listener creato.</span><span class="sxs-lookup"><span data-stu-id="58971-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="58971-148">Non tutti i listener di traccia richiedono che venga specificato **initializeData**.</span><span class="sxs-lookup"><span data-stu-id="58971-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="58971-149">Quando si usa l'attributo `initializeData`, è possibile che venga visualizzato l'avviso del compilatore "l'attributo ' initializeData ' non è dichiarato".</span><span class="sxs-lookup"><span data-stu-id="58971-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="58971-150">Questo avviso si verifica perché le impostazioni di configurazione vengono convalidate rispetto alla classe di base astratta <xref:System.Diagnostics.TraceListener>, che non riconosce l'attributo `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="58971-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="58971-151">In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispongono di un costruttore che accetta un parametro.</span><span class="sxs-lookup"><span data-stu-id="58971-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="58971-152">Nella tabella seguente vengono illustrati i listener di traccia inclusi nel .NET Framework e viene descritto il valore degli attributi **initializeData** .</span><span class="sxs-lookup"><span data-stu-id="58971-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="58971-153">Classe listener di traccia</span><span class="sxs-lookup"><span data-stu-id="58971-153">Trace listener class</span></span>|<span data-ttu-id="58971-154">valore dell'attributo initializeData</span><span class="sxs-lookup"><span data-stu-id="58971-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="58971-155">Valore `useErrorStream` per il costruttore di <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.</span><span class="sxs-lookup"><span data-stu-id="58971-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="58971-156">Impostare l'attributo `initializeData` su "`true`" per scrivere l'output di traccia e di debug in <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" per scrivere <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="58971-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="58971-157">Nome del file in cui viene scritto il <xref:System.Diagnostics.DelimitedListTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="58971-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="58971-158">Nome del nome di un'origine del log eventi esistente.</span><span class="sxs-lookup"><span data-stu-id="58971-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="58971-159">Nome del file in cui viene scritto il <xref:System.Diagnostics.EventSchemaTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="58971-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="58971-160">Nome del file in cui viene scritto il <xref:System.Diagnostics.TextWriterTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="58971-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="58971-161">Nome del file in cui viene scritto il <xref:System.Diagnostics.XmlWriterTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="58971-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="58971-162">Esempio</span><span class="sxs-lookup"><span data-stu-id="58971-162">Example</span></span>  
 <span data-ttu-id="58971-163">Nell'esempio seguente viene illustrato come utilizzare **\<aggiungere >** elementi per aggiungere i listener `MyListener` e `MyEventListener` alla raccolta **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="58971-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="58971-164">`MyListener` crea un file denominato `MyListener.log` e scrive l'output nel file.</span><span class="sxs-lookup"><span data-stu-id="58971-164">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="58971-165">`MyEventListener` crea una voce nel registro eventi.</span><span class="sxs-lookup"><span data-stu-id="58971-165">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="58971-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58971-166">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [<span data-ttu-id="58971-167">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="58971-167">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="58971-168">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="58971-168">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
