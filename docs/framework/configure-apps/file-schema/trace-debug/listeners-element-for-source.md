---
title: Elemento <listeners> per <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: d7641611e5d8257b49bc6a6abd0a2fadfde66e91
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697294"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="14ac3-102">\<listener > elemento per \<origine ></span><span class="sxs-lookup"><span data-stu-id="14ac3-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="14ac3-103">Aggiunge o rimuove i listener nella raccolta <xref:System.Diagnostics.TraceSource.Listeners%2A> per un <xref:System.Diagnostics.TraceSource>.</span><span class="sxs-lookup"><span data-stu-id="14ac3-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="14ac3-104">Un listener indirizza l'output di traccia a una destinazione appropriata, ad esempio un log, una finestra o un file di testo.</span><span class="sxs-lookup"><span data-stu-id="14ac3-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
[<span data-ttu-id="14ac3-105"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="14ac3-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="14ac3-106">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="14ac3-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="14ac3-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<origini** >](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="14ac3-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="14ac3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[ **origine** >](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="14ac3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="14ac3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**listener** ></span><span class="sxs-lookup"><span data-stu-id="14ac3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14ac3-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="14ac3-110">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14ac3-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="14ac3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="14ac3-112">Le sezioni seguenti descrivono gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="14ac3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14ac3-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="14ac3-113">Attributes</span></span>  
 <span data-ttu-id="14ac3-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="14ac3-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="14ac3-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="14ac3-115">Child Elements</span></span>  
  
|<span data-ttu-id="14ac3-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="14ac3-116">Element</span></span>|<span data-ttu-id="14ac3-117">description</span><span class="sxs-lookup"><span data-stu-id="14ac3-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14ac3-118">\<add></span><span class="sxs-lookup"><span data-stu-id="14ac3-118">\<add></span></span>](add-element-for-listeners-for-source.md)|<span data-ttu-id="14ac3-119">Aggiunge un listener alla raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="14ac3-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="14ac3-120">\<remove></span><span class="sxs-lookup"><span data-stu-id="14ac3-120">\<remove></span></span>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="14ac3-121">Rimuove un listener dalla raccolta di `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="14ac3-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="14ac3-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="14ac3-122">\<clear></span></span>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="14ac3-123">Cancella la raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="14ac3-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="14ac3-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="14ac3-124">Parent Elements</span></span>  
  
|<span data-ttu-id="14ac3-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="14ac3-125">Element</span></span>|<span data-ttu-id="14ac3-126">description</span><span class="sxs-lookup"><span data-stu-id="14ac3-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="14ac3-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="14ac3-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="14ac3-128">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="14ac3-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="14ac3-129">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="14ac3-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="14ac3-130">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="14ac3-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14ac3-131">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="14ac3-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="14ac3-132">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="14ac3-132">Configuration File</span></span>  
 <span data-ttu-id="14ac3-133">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="14ac3-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14ac3-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="14ac3-134">Example</span></span>  
 <span data-ttu-id="14ac3-135">Nell'esempio seguente viene illustrato come utilizzare l'elemento `<listeners>` per aggiungere un listener di traccia della console all'origine `mySource` e rimuovere il listener di traccia predefinito.</span><span class="sxs-lookup"><span data-stu-id="14ac3-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener">  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error"/>  
          </add>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="14ac3-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14ac3-136">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="14ac3-137">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="14ac3-137">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="14ac3-138">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="14ac3-138">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
