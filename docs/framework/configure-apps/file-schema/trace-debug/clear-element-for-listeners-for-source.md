---
title: '&lt;deselezionare&gt; (elemento) per &lt;listener&gt; per &lt;origine&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 362e1d7a4ac4c39309aa86561683df1d239f2ab1
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083866"
---
# <a name="ltcleargt-element-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="0ee6c-102">&lt;deselezionare&gt; (elemento) per &lt;listener&gt; per &lt;origine&gt;</span><span class="sxs-lookup"><span data-stu-id="0ee6c-102">&lt;clear&gt; Element for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="0ee6c-103">Cancella la raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="0ee6c-103">Clears the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="0ee6c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0ee6c-104">\<configuration></span></span>  
<span data-ttu-id="0ee6c-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="0ee6c-105">\<system.diagnostics></span></span>  
<span data-ttu-id="0ee6c-106">\<sources></span><span class="sxs-lookup"><span data-stu-id="0ee6c-106">\<sources></span></span>  
<span data-ttu-id="0ee6c-107">\<origine ></span><span class="sxs-lookup"><span data-stu-id="0ee6c-107">\<source></span></span>  
<span data-ttu-id="0ee6c-108">\<listeners></span><span class="sxs-lookup"><span data-stu-id="0ee6c-108">\<listeners></span></span>  
<span data-ttu-id="0ee6c-109">\<clear></span><span class="sxs-lookup"><span data-stu-id="0ee6c-109">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ee6c-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ee6c-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ee6c-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0ee6c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0ee6c-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0ee6c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ee6c-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="0ee6c-113">Attributes</span></span>  
 <span data-ttu-id="0ee6c-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0ee6c-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0ee6c-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0ee6c-115">Child Elements</span></span>  
 <span data-ttu-id="0ee6c-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0ee6c-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0ee6c-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0ee6c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0ee6c-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="0ee6c-118">Element</span></span>|<span data-ttu-id="0ee6c-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ee6c-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0ee6c-120">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0ee6c-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="0ee6c-121">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="0ee6c-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="0ee6c-122">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="0ee6c-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="0ee6c-123">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="0ee6c-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="0ee6c-124">Specifica i listener di raccolgono, archiviano e indirizzano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="0ee6c-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ee6c-125">Note</span><span class="sxs-lookup"><span data-stu-id="0ee6c-125">Remarks</span></span>  
 <span data-ttu-id="0ee6c-126">Il `<clear>` elemento rimuove tutti i listener dal `Listeners` insieme per un'origine di traccia, tra cui la <xref:System.Diagnostics.DefaultTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="0ee6c-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="0ee6c-127">È possibile usare la `<clear>` elemento prima di usare il `<add>` elemento per essere certi che non sono presenti altri listener attivi nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="0ee6c-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="0ee6c-128">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="0ee6c-128">Configuration File</span></span>  
 <span data-ttu-id="0ee6c-129">Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0ee6c-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ee6c-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ee6c-130">Example</span></span>  
 <span data-ttu-id="0ee6c-131">Nell'esempio seguente viene illustrato come utilizzare il `<clear>` elemento prima di usare il `<add>` elementi da aggiungere i listener `console` e `textListener` per il `Listeners` raccolta per l'origine di traccia `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="0ee6c-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0ee6c-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ee6c-132">See also</span></span>
- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="0ee6c-133">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="0ee6c-133">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="0ee6c-134">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="0ee6c-134">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
