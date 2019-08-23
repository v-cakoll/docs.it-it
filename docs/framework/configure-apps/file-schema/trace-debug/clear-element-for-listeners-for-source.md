---
title: <clear>Elemento per <listeners> per<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 768d51a74b4c31d1250d2f5d6517f760f886e0a0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920541"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="01070-102">\<Cancella > elemento per \<i listener > per \<l'origine ></span><span class="sxs-lookup"><span data-stu-id="01070-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="01070-103">Cancella la raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="01070-103">Clears the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="01070-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="01070-104">\<configuration></span></span>  
<span data-ttu-id="01070-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="01070-105">\<system.diagnostics></span></span>  
<span data-ttu-id="01070-106">\<origini ></span><span class="sxs-lookup"><span data-stu-id="01070-106">\<sources></span></span>  
<span data-ttu-id="01070-107">\<> di origine</span><span class="sxs-lookup"><span data-stu-id="01070-107">\<source></span></span>  
<span data-ttu-id="01070-108">\<listener ></span><span class="sxs-lookup"><span data-stu-id="01070-108">\<listeners></span></span>  
<span data-ttu-id="01070-109">\<Cancella ></span><span class="sxs-lookup"><span data-stu-id="01070-109">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01070-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01070-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01070-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="01070-111">Attributes and Elements</span></span>  
 <span data-ttu-id="01070-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="01070-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01070-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="01070-113">Attributes</span></span>  
 <span data-ttu-id="01070-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="01070-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="01070-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="01070-115">Child Elements</span></span>  
 <span data-ttu-id="01070-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="01070-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01070-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="01070-117">Parent Elements</span></span>  
  
|<span data-ttu-id="01070-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="01070-118">Element</span></span>|<span data-ttu-id="01070-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01070-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="01070-120">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="01070-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="01070-121">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="01070-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="01070-122">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="01070-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="01070-123">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="01070-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="01070-124">Specifica i listener che raccolgono, archiviano e indirizzano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="01070-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01070-125">Note</span><span class="sxs-lookup"><span data-stu-id="01070-125">Remarks</span></span>  
 <span data-ttu-id="01070-126">L' `<clear>` elemento rimuove tutti i listener `Listeners` dalla raccolta per un'origine di <xref:System.Diagnostics.DefaultTraceListener>traccia, incluso.</span><span class="sxs-lookup"><span data-stu-id="01070-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="01070-127">È possibile usare l' `<clear>` elemento prima di usare `<add>` l'elemento per assicurarsi che non ci siano altri listener attivi nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="01070-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="01070-128">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="01070-128">Configuration File</span></span>  
 <span data-ttu-id="01070-129">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="01070-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01070-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="01070-130">Example</span></span>  
 <span data-ttu-id="01070-131">Nell'esempio seguente viene illustrato come utilizzare l' `<clear>` elemento prima `console` di `<add>` utilizzare gli elementi per aggiungere i `Listeners` listener e `textListener` alla raccolta per l'origine `TraceSourceApp`di traccia.</span><span class="sxs-lookup"><span data-stu-id="01070-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
       <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <clear/>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
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
  
## <a name="see-also"></a><span data-ttu-id="01070-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01070-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="01070-133">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="01070-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="01070-134">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="01070-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
