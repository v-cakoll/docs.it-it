---
title: '&lt;i listener&gt; (elemento) per &lt;traccia&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
author: mcleblanc
ms.author: markl
ms.openlocfilehash: bfcf96c553f85aeb0a40dfd6ea36667d504e8eee
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48028001"
---
# <a name="ltlistenersgt-element-for-lttracegt"></a><span data-ttu-id="41b15-102">&lt;i listener&gt; (elemento) per &lt;traccia&gt;</span><span class="sxs-lookup"><span data-stu-id="41b15-102">&lt;listeners&gt; Element for &lt;trace&gt;</span></span>
<span data-ttu-id="41b15-103">Specifica un listener che raccoglie, archivia e indirizza i messaggi.</span><span class="sxs-lookup"><span data-stu-id="41b15-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="41b15-104">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="41b15-104">Listeners direct the tracing output to an appropriate target.</span></span>  
  
 <span data-ttu-id="41b15-105">\<configurazione > elemento</span><span class="sxs-lookup"><span data-stu-id="41b15-105">\<configuration> Element</span></span>  
<span data-ttu-id="41b15-106">\<System. Diagnostics > elemento</span><span class="sxs-lookup"><span data-stu-id="41b15-106">\<system.diagnostics> Element</span></span>  
<span data-ttu-id="41b15-107">\<traccia > elemento</span><span class="sxs-lookup"><span data-stu-id="41b15-107">\<trace> Element</span></span>  
<span data-ttu-id="41b15-108">\<i listener > (elemento) per \<traccia ></span><span class="sxs-lookup"><span data-stu-id="41b15-108">\<listeners> Element for \<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41b15-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="41b15-109">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41b15-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="41b15-110">Attributes and Elements</span></span>  
 <span data-ttu-id="41b15-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="41b15-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41b15-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="41b15-112">Attributes</span></span>  
 <span data-ttu-id="41b15-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="41b15-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="41b15-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="41b15-114">Child Elements</span></span>  
  
|<span data-ttu-id="41b15-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="41b15-115">Element</span></span>|<span data-ttu-id="41b15-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41b15-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41b15-117">\<add></span><span class="sxs-lookup"><span data-stu-id="41b15-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|<span data-ttu-id="41b15-118">Aggiunge un listener alla raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="41b15-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="41b15-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="41b15-119">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|<span data-ttu-id="41b15-120">Cancella la raccolta `Listeners` per una traccia.</span><span class="sxs-lookup"><span data-stu-id="41b15-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="41b15-121">\<remove></span><span class="sxs-lookup"><span data-stu-id="41b15-121">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|<span data-ttu-id="41b15-122">Rimuove un listener dal `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="41b15-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="41b15-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="41b15-123">Parent Elements</span></span>  
  
|<span data-ttu-id="41b15-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="41b15-124">Element</span></span>|<span data-ttu-id="41b15-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41b15-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="41b15-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="41b15-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="41b15-127">Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="41b15-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="41b15-128">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="41b15-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41b15-129">Note</span><span class="sxs-lookup"><span data-stu-id="41b15-129">Remarks</span></span>  
 <span data-ttu-id="41b15-130">Il <xref:System.Diagnostics.Debug> e <xref:System.Diagnostics.Trace> condividono lo stesso **listener** raccolta.</span><span class="sxs-lookup"><span data-stu-id="41b15-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="41b15-131">Se si aggiunge un oggetto listener alla raccolta in una di queste classi, l'altra classe utilizza lo stesso listener.</span><span class="sxs-lookup"><span data-stu-id="41b15-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="41b15-132">Le classi di listener fornite con .NET Framework derivano dal <xref:System.Diagnostics.TraceListener> classe.</span><span class="sxs-lookup"><span data-stu-id="41b15-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="41b15-133">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="41b15-133">Configuration File</span></span>  
 <span data-ttu-id="41b15-134">Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="41b15-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41b15-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="41b15-135">Example</span></span>  
 <span data-ttu-id="41b15-136">Nell'esempio seguente viene illustrato come utilizzare il  **\<listener >** elemento a cui aggiungere i listener `MyListener` e `MyEventListener` per i **listener** raccolta.</span><span class="sxs-lookup"><span data-stu-id="41b15-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="41b15-137">`MyListener` Crea un file denominato `MyListener.log` e scrive l'output del file.</span><span class="sxs-lookup"><span data-stu-id="41b15-137">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="41b15-138">`MyEventListener` Crea una voce nel registro eventi.</span><span class="sxs-lookup"><span data-stu-id="41b15-138">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"   
          type="System.Diagnostics.TextWriterTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"   
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="41b15-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41b15-139">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="41b15-140">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="41b15-140">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
