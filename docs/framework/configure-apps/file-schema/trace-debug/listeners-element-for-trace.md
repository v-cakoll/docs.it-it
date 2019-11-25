---
title: Elemento <listeners> per <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: 10530cfadf2e182f912c699e50294af4b57f47b5
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088868"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="44e0b-102">\<listeners > elemento per \<Trace ></span><span class="sxs-lookup"><span data-stu-id="44e0b-102">\<listeners> Element for \<trace></span></span>
<span data-ttu-id="44e0b-103">Specifica un listener che raccoglie, archivia e instrada i messaggi.</span><span class="sxs-lookup"><span data-stu-id="44e0b-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="44e0b-104">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="44e0b-104">Listeners direct the tracing output to an appropriate target.</span></span>  

<span data-ttu-id="44e0b-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="44e0b-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="44e0b-106">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="44e0b-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="44e0b-107">&nbsp;&nbsp;&nbsp;&nbsp;\<[**Trace**](trace-element.md) ></span><span class="sxs-lookup"><span data-stu-id="44e0b-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\</span></span>
<span data-ttu-id="44e0b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**listener**\<</span><span class="sxs-lookup"><span data-stu-id="44e0b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>

## <a name="syntax"></a><span data-ttu-id="44e0b-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44e0b-109">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44e0b-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="44e0b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="44e0b-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="44e0b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44e0b-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="44e0b-112">Attributes</span></span>  
 <span data-ttu-id="44e0b-113">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="44e0b-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="44e0b-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="44e0b-114">Child Elements</span></span>  
  
|<span data-ttu-id="44e0b-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="44e0b-115">Element</span></span>|<span data-ttu-id="44e0b-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44e0b-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44e0b-117">\<add></span><span class="sxs-lookup"><span data-stu-id="44e0b-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="44e0b-118">Aggiunge un listener alla raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="44e0b-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="44e0b-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="44e0b-119">\<clear></span></span>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="44e0b-120">Cancella la raccolta `Listeners` per una traccia.</span><span class="sxs-lookup"><span data-stu-id="44e0b-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="44e0b-121">\<remove></span><span class="sxs-lookup"><span data-stu-id="44e0b-121">\<remove></span></span>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="44e0b-122">Rimuove un listener dalla raccolta di `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="44e0b-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="44e0b-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="44e0b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="44e0b-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="44e0b-124">Element</span></span>|<span data-ttu-id="44e0b-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44e0b-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="44e0b-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="44e0b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="44e0b-127">Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="44e0b-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="44e0b-128">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="44e0b-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44e0b-129">Note</span><span class="sxs-lookup"><span data-stu-id="44e0b-129">Remarks</span></span>  
 <span data-ttu-id="44e0b-130">Le classi <xref:System.Diagnostics.Debug> e <xref:System.Diagnostics.Trace> condividono la stessa raccolta **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="44e0b-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="44e0b-131">Se si aggiunge un oggetto listener alla raccolta in una di queste classi, l'altra classe utilizzerà lo stesso listener.</span><span class="sxs-lookup"><span data-stu-id="44e0b-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="44e0b-132">Le classi del listener fornite con la .NET Framework derivano dalla classe <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="44e0b-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="44e0b-133">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="44e0b-133">Configuration File</span></span>  
 <span data-ttu-id="44e0b-134">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="44e0b-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44e0b-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="44e0b-135">Example</span></span>  
 <span data-ttu-id="44e0b-136">Nell'esempio seguente viene illustrato come utilizzare l'elemento **> listener\<** per aggiungere i listener `MyListener` e `MyEventListener` alla raccolta **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="44e0b-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="44e0b-137">`MyListener` crea un file denominato `MyListener.log` e scrive l'output nel file.</span><span class="sxs-lookup"><span data-stu-id="44e0b-137">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="44e0b-138">`MyEventListener` crea una voce nel registro eventi.</span><span class="sxs-lookup"><span data-stu-id="44e0b-138">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="44e0b-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44e0b-139">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="44e0b-140">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="44e0b-140">Trace and Debug Settings Schema</span></span>](index.md)
