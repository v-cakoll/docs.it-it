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
ms.openlocfilehash: c64673908dc9afe67d97c08f93e5b9d9533bd34d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153672"
---
# <a name="add-element-for-listeners-for-trace"></a><span data-ttu-id="373f5-102">\<add>Elemento per \<listeners> per\<trace></span><span class="sxs-lookup"><span data-stu-id="373f5-102">\<add> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="373f5-103">Aggiunge un listener alla raccolta **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="373f5-103">Adds a listener to the **Listeners** collection.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="373f5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="373f5-104">Syntax</span></span>  
  
```xml  
<add name="name"
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="373f5-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="373f5-105">Attributes and Elements</span></span>  
 <span data-ttu-id="373f5-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="373f5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="373f5-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="373f5-107">Attributes</span></span>  
  
|<span data-ttu-id="373f5-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="373f5-108">Attribute</span></span>|<span data-ttu-id="373f5-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="373f5-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="373f5-110">**type**</span><span class="sxs-lookup"><span data-stu-id="373f5-110">**type**</span></span>|<span data-ttu-id="373f5-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="373f5-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="373f5-112">Specifica il tipo di listener.</span><span class="sxs-lookup"><span data-stu-id="373f5-112">Specifies the type of the listener.</span></span> <span data-ttu-id="373f5-113">È necessario usare una stringa che soddisfi i requisiti specificati per [specificare nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="373f5-113">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="373f5-114">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="373f5-114">**initializeData**</span></span>|<span data-ttu-id="373f5-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="373f5-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="373f5-116">Stringa passata al costruttore per la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="373f5-116">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="373f5-117">**nome**</span><span class="sxs-lookup"><span data-stu-id="373f5-117">**name**</span></span>|<span data-ttu-id="373f5-118">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="373f5-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="373f5-119">Specifica il nome del listener.</span><span class="sxs-lookup"><span data-stu-id="373f5-119">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="373f5-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="373f5-120">Child Elements</span></span>  
  
|<span data-ttu-id="373f5-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="373f5-121">Element</span></span>|<span data-ttu-id="373f5-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="373f5-122">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="373f5-123">Aggiunge un filtro a un listener nella `Listeners` raccolta per una traccia.</span><span class="sxs-lookup"><span data-stu-id="373f5-123">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="373f5-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="373f5-124">Parent Elements</span></span>  
  
|<span data-ttu-id="373f5-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="373f5-125">Element</span></span>|<span data-ttu-id="373f5-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="373f5-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="373f5-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="373f5-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="373f5-128">Specifica un listener che raccoglie, archivia e instrada i messaggi.</span><span class="sxs-lookup"><span data-stu-id="373f5-128">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="373f5-129">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="373f5-129">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="373f5-130">Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="373f5-130">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="373f5-131">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="373f5-131">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="373f5-132">Commenti</span><span class="sxs-lookup"><span data-stu-id="373f5-132">Remarks</span></span>  
 <span data-ttu-id="373f5-133">Le <xref:System.Diagnostics.Debug> <xref:System.Diagnostics.Trace> classi e condividono la stessa raccolta **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="373f5-133">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="373f5-134">Se si aggiunge un oggetto listener alla raccolta in una di queste classi, l'altra classe utilizzerà lo stesso listener.</span><span class="sxs-lookup"><span data-stu-id="373f5-134">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="373f5-135">Le classi del listener derivano da <xref:System.Diagnostics.TraceListener> .</span><span class="sxs-lookup"><span data-stu-id="373f5-135">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="373f5-136">Se non si specifica l' `name` attributo del listener di traccia, il <xref:System.Diagnostics.TraceListener.Name%2A> valore predefinito di per il listener di traccia è una stringa vuota ("").</span><span class="sxs-lookup"><span data-stu-id="373f5-136">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="373f5-137">Se l'applicazione dispone di un solo listener, è possibile aggiungerlo senza specificare un nome e rimuoverlo specificando una stringa vuota per il nome.</span><span class="sxs-lookup"><span data-stu-id="373f5-137">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="373f5-138">Tuttavia, se l'applicazione ha più di un listener, è necessario specificare nomi univoci per ogni listener di traccia, che consente di identificare e gestire i singoli listener di traccia all'interno delle <xref:System.Diagnostics.Debug.Listeners%2A> <xref:System.Diagnostics.Trace.Listeners%2A> raccolte e.</span><span class="sxs-lookup"><span data-stu-id="373f5-138">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="373f5-139">L'aggiunta di più listener di traccia dello stesso tipo e con lo stesso nome comporta l'aggiunta di un solo listener di traccia del tipo e del nome alla `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="373f5-139">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="373f5-140">Tuttavia, è possibile aggiungere a livello di codice più listener identici alla `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="373f5-140">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="373f5-141">Il valore dell'attributo **initializeData** dipende dal tipo di listener creato.</span><span class="sxs-lookup"><span data-stu-id="373f5-141">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="373f5-142">Non tutti i listener di traccia richiedono che venga specificato **initializeData**.</span><span class="sxs-lookup"><span data-stu-id="373f5-142">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="373f5-143">Quando si usa l' `initializeData` attributo, è possibile che venga visualizzato l'avviso del compilatore "l'attributo ' initializeData ' non è dichiarato".</span><span class="sxs-lookup"><span data-stu-id="373f5-143">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="373f5-144">Questo avviso si verifica perché le impostazioni di configurazione vengono convalidate rispetto alla classe di base astratta <xref:System.Diagnostics.TraceListener> , che non riconosce l' `initializeData` attributo.</span><span class="sxs-lookup"><span data-stu-id="373f5-144">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="373f5-145">In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispongono di un costruttore che accetta un parametro.</span><span class="sxs-lookup"><span data-stu-id="373f5-145">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="373f5-146">Nella tabella seguente vengono illustrati i listener di traccia inclusi nel .NET Framework e viene descritto il valore degli attributi **initializeData** .</span><span class="sxs-lookup"><span data-stu-id="373f5-146">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="373f5-147">Classe listener di traccia</span><span class="sxs-lookup"><span data-stu-id="373f5-147">Trace listener class</span></span>|<span data-ttu-id="373f5-148">valore dell'attributo initializeData</span><span class="sxs-lookup"><span data-stu-id="373f5-148">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="373f5-149">`useErrorStream`Valore per il <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="373f5-149">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="373f5-150">Impostare l' `initializeData` attributo su " `true` " per scrivere l'output di traccia ed eseguire il debug in <xref:System.Console.Error%2A?displayProperty=nameWithType> ; " `false` " in cui scrivere <xref:System.Console.Out%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="373f5-150">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="373f5-151">Nome del file in cui scrive <xref:System.Diagnostics.DelimitedListTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="373f5-151">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="373f5-152">Nome del nome di un'origine del log eventi esistente.</span><span class="sxs-lookup"><span data-stu-id="373f5-152">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="373f5-153">Nome del file <xref:System.Diagnostics.EventSchemaTraceListener> in cui scrive.</span><span class="sxs-lookup"><span data-stu-id="373f5-153">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="373f5-154">Nome del file <xref:System.Diagnostics.TextWriterTraceListener> in cui scrive.</span><span class="sxs-lookup"><span data-stu-id="373f5-154">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="373f5-155">Nome del file <xref:System.Diagnostics.XmlWriterTraceListener> in cui scrive.</span><span class="sxs-lookup"><span data-stu-id="373f5-155">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="373f5-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="373f5-156">Example</span></span>  
 <span data-ttu-id="373f5-157">Nell'esempio seguente viene illustrato come utilizzare **\<add>** gli elementi per aggiungere i listener `MyListener` e `MyEventListener` alla raccolta **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="373f5-157">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="373f5-158">`MyListener`Crea un file denominato `MyListener.log` e scrive l'output nel file.</span><span class="sxs-lookup"><span data-stu-id="373f5-158">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="373f5-159">`MyEventListener`Crea una voce nel log eventi.</span><span class="sxs-lookup"><span data-stu-id="373f5-159">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="373f5-160">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="373f5-160">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [<span data-ttu-id="373f5-161">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="373f5-161">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="373f5-162">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="373f5-162">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
