---
title: <add>Elemento <listeners> per<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: c64673908dc9afe67d97c08f93e5b9d9533bd34d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153672"
---
# <a name="add-element-for-listeners-for-trace"></a><span data-ttu-id="9ee04-102">\<aggiungere>elemento \<per i \<listener> per i> di tracciaAdd a Element for listeners> for trace></span><span class="sxs-lookup"><span data-stu-id="9ee04-102">\<add> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="9ee04-103">Aggiunge un listener alla raccolta **Listeners.**</span><span class="sxs-lookup"><span data-stu-id="9ee04-103">Adds a listener to the **Listeners** collection.</span></span>  

<span data-ttu-id="9ee04-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9ee04-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9ee04-105">&nbsp;&nbsp;[**\<>system.diagnostics**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="9ee04-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="9ee04-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>traccia**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="9ee04-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="9ee04-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di ascoltatori**](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="9ee04-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="9ee04-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<aggiungere>**</span><span class="sxs-lookup"><span data-stu-id="9ee04-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="9ee04-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9ee04-109">Syntax</span></span>  
  
```xml  
<add name="name"
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ee04-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9ee04-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9ee04-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9ee04-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ee04-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="9ee04-112">Attributes</span></span>  
  
|<span data-ttu-id="9ee04-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="9ee04-113">Attribute</span></span>|<span data-ttu-id="9ee04-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ee04-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9ee04-115">**type**</span><span class="sxs-lookup"><span data-stu-id="9ee04-115">**type**</span></span>|<span data-ttu-id="9ee04-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9ee04-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="9ee04-117">Specifica il tipo di listener.</span><span class="sxs-lookup"><span data-stu-id="9ee04-117">Specifies the type of the listener.</span></span> <span data-ttu-id="9ee04-118">È necessario utilizzare una stringa che soddisfi i requisiti specificati in Specifica di nomi di [tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="9ee04-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="9ee04-119">**Initializedata**</span><span class="sxs-lookup"><span data-stu-id="9ee04-119">**initializeData**</span></span>|<span data-ttu-id="9ee04-120">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="9ee04-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="9ee04-121">Stringa passata al costruttore per la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="9ee04-121">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="9ee04-122">**name**</span><span class="sxs-lookup"><span data-stu-id="9ee04-122">**name**</span></span>|<span data-ttu-id="9ee04-123">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="9ee04-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="9ee04-124">Specifica il nome del listener.</span><span class="sxs-lookup"><span data-stu-id="9ee04-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ee04-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9ee04-125">Child Elements</span></span>  
  
|<span data-ttu-id="9ee04-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ee04-126">Element</span></span>|<span data-ttu-id="9ee04-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ee04-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ee04-128">\<>di filtro</span><span class="sxs-lookup"><span data-stu-id="9ee04-128">\<filter></span></span>](filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="9ee04-129">Aggiunge un filtro a `Listeners` un listener nella raccolta per una traccia.</span><span class="sxs-lookup"><span data-stu-id="9ee04-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9ee04-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9ee04-130">Parent Elements</span></span>  
  
|<span data-ttu-id="9ee04-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ee04-131">Element</span></span>|<span data-ttu-id="9ee04-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ee04-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9ee04-133">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9ee04-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="9ee04-134">Specifica un listener che raccoglie, archivia e instrada i messaggi.</span><span class="sxs-lookup"><span data-stu-id="9ee04-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="9ee04-135">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="9ee04-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="9ee04-136">Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="9ee04-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="9ee04-137">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="9ee04-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ee04-138">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9ee04-138">Remarks</span></span>  
 <span data-ttu-id="9ee04-139">Le <xref:System.Diagnostics.Debug> <xref:System.Diagnostics.Trace> classi e condividono la stessa raccolta **Listeners.**</span><span class="sxs-lookup"><span data-stu-id="9ee04-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="9ee04-140">Se si aggiunge un oggetto listener alla raccolta in una di queste classi, l'altra classe utilizza lo stesso listener.</span><span class="sxs-lookup"><span data-stu-id="9ee04-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="9ee04-141">Le classi listener <xref:System.Diagnostics.TraceListener>derivano da .</span><span class="sxs-lookup"><span data-stu-id="9ee04-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="9ee04-142">Se non si `name` specifica l'attributo <xref:System.Diagnostics.TraceListener.Name%2A> del listener di traccia, il valore predefinito del listener di traccia è una stringa vuota ("").</span><span class="sxs-lookup"><span data-stu-id="9ee04-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="9ee04-143">Se l'applicazione dispone di un solo listener, è possibile aggiungerlo senza specificare un nome e rimuoverlo specificando una stringa vuota per il nome.</span><span class="sxs-lookup"><span data-stu-id="9ee04-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="9ee04-144">Tuttavia, se l'applicazione dispone di più listener, è necessario specificare nomi univoci per ogni <xref:System.Diagnostics.Debug.Listeners%2A> listener <xref:System.Diagnostics.Trace.Listeners%2A> di traccia, che consente di identificare e gestire i singoli listener di traccia all'interno delle raccolte e .</span><span class="sxs-lookup"><span data-stu-id="9ee04-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ee04-145">L'aggiunta di più listener di traccia dello stesso tipo e con lo stesso nome `Listeners` comporta l'aggiunta di un solo listener di traccia di tale tipo e nome alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="9ee04-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="9ee04-146">Tuttavia, è possibile aggiungere a livello `Listeners` di codice più listener identici alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="9ee04-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="9ee04-147">Il valore per l'attributo **initializeData** dipende dal tipo di listener creato.</span><span class="sxs-lookup"><span data-stu-id="9ee04-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="9ee04-148">Non tutti i listener di traccia richiedono l'impostazione di **initializeData**.</span><span class="sxs-lookup"><span data-stu-id="9ee04-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ee04-149">Quando si `initializeData` utilizza l'attributo, è possibile che venga visualizzato l'avviso del compilatore "L'attributo 'initializeData' non è dichiarato".</span><span class="sxs-lookup"><span data-stu-id="9ee04-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="9ee04-150">Questo avviso viene generato perché le impostazioni di <xref:System.Diagnostics.TraceListener>configurazione vengono convalidate rispetto alla classe base astratta , che non riconosce l'attributo `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="9ee04-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="9ee04-151">In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispongono di un costruttore che accetta un parametro.</span><span class="sxs-lookup"><span data-stu-id="9ee04-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="9ee04-152">Nella tabella seguente vengono illustrati i listener di traccia inclusi in .NET Framework e viene descritto il valore dei relativi attributi **initializeData.**</span><span class="sxs-lookup"><span data-stu-id="9ee04-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="9ee04-153">Classe listener di traccia</span><span class="sxs-lookup"><span data-stu-id="9ee04-153">Trace listener class</span></span>|<span data-ttu-id="9ee04-154">valore dell'attributo initializeData</span><span class="sxs-lookup"><span data-stu-id="9ee04-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="9ee04-155">Valore `useErrorStream` per <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> il costruttore.</span><span class="sxs-lookup"><span data-stu-id="9ee04-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="9ee04-156">Impostare `initializeData` l'attributo su "`true`" <xref:System.Console.Error%2A?displayProperty=nameWithType>per scrivere la traccia e l'output di debug in ; "`false`" per <xref:System.Console.Out%2A?displayProperty=nameWithType>scrivere a .</span><span class="sxs-lookup"><span data-stu-id="9ee04-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="9ee04-157">Nome del file in cui scrive <xref:System.Diagnostics.DelimitedListTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="9ee04-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="9ee04-158">Nome del nome di un'origine del log eventi esistente.</span><span class="sxs-lookup"><span data-stu-id="9ee04-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="9ee04-159">Nome del file in <xref:System.Diagnostics.EventSchemaTraceListener> cui viene scritto il file.</span><span class="sxs-lookup"><span data-stu-id="9ee04-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="9ee04-160">Nome del file in <xref:System.Diagnostics.TextWriterTraceListener> cui viene scritto il file.</span><span class="sxs-lookup"><span data-stu-id="9ee04-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="9ee04-161">Nome del file in <xref:System.Diagnostics.XmlWriterTraceListener> cui viene scritto il file.</span><span class="sxs-lookup"><span data-stu-id="9ee04-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9ee04-162">Esempio</span><span class="sxs-lookup"><span data-stu-id="9ee04-162">Example</span></span>  
 <span data-ttu-id="9ee04-163">Nell'esempio seguente viene \*\* \<\*\* illustrato come utilizzare add `MyListener` `MyEventListener`>elementi per aggiungere i listener e per il **Listeners** insieme.</span><span class="sxs-lookup"><span data-stu-id="9ee04-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="9ee04-164">`MyListener`crea un `MyListener.log` file chiamato e scrive l'output nel file.</span><span class="sxs-lookup"><span data-stu-id="9ee04-164">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="9ee04-165">`MyEventListener`crea una voce nel registro eventi.</span><span class="sxs-lookup"><span data-stu-id="9ee04-165">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9ee04-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ee04-166">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [<span data-ttu-id="9ee04-167">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="9ee04-167">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9ee04-168">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="9ee04-168">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
