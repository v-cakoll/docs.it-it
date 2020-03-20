---
title: Elemento <listeners> per <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: 0eee325e01b41a15a19e4f40f479596f9d70f73b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153412"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="32050-102">\<elementi di> \<dei listener per i> di origine</span><span class="sxs-lookup"><span data-stu-id="32050-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="32050-103">Aggiunge o rimuove i <xref:System.Diagnostics.TraceSource.Listeners%2A> listener <xref:System.Diagnostics.TraceSource>nella raccolta per un oggetto .</span><span class="sxs-lookup"><span data-stu-id="32050-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="32050-104">Un listener indirizza l'output di traccia a una destinazione appropriata, ad esempio un log, una finestra o un file di testo.</span><span class="sxs-lookup"><span data-stu-id="32050-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
[<span data-ttu-id="32050-105">**\<>di configurazione**</span><span class="sxs-lookup"><span data-stu-id="32050-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="32050-106">&nbsp;&nbsp;[**\<>system.diagnostics**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="32050-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="32050-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<fonti>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="32050-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="32050-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="32050-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="32050-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>di ascoltatori**</span><span class="sxs-lookup"><span data-stu-id="32050-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32050-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="32050-110">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32050-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="32050-111">Attributes and Elements</span></span>  
 <span data-ttu-id="32050-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="32050-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32050-113">Attributes</span><span class="sxs-lookup"><span data-stu-id="32050-113">Attributes</span></span>  
 <span data-ttu-id="32050-114">No.</span><span class="sxs-lookup"><span data-stu-id="32050-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="32050-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="32050-115">Child Elements</span></span>  
  
|<span data-ttu-id="32050-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="32050-116">Element</span></span>|<span data-ttu-id="32050-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="32050-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32050-118">\<aggiungere></span><span class="sxs-lookup"><span data-stu-id="32050-118">\<add></span></span>](add-element-for-listeners-for-source.md)|<span data-ttu-id="32050-119">Aggiunge un listener alla raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="32050-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="32050-120">\<rimuovere></span><span class="sxs-lookup"><span data-stu-id="32050-120">\<remove></span></span>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="32050-121">Rimuove un listener `Listeners` dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="32050-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="32050-122">\<>chiari</span><span class="sxs-lookup"><span data-stu-id="32050-122">\<clear></span></span>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="32050-123">Cancella la raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="32050-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="32050-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="32050-124">Parent Elements</span></span>  
  
|<span data-ttu-id="32050-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="32050-125">Element</span></span>|<span data-ttu-id="32050-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="32050-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="32050-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="32050-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="32050-128">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="32050-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="32050-129">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="32050-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="32050-130">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="32050-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32050-131">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="32050-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="32050-132">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="32050-132">Configuration File</span></span>  
 <span data-ttu-id="32050-133">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine.config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="32050-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32050-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="32050-134">Example</span></span>  
 <span data-ttu-id="32050-135">Nell'esempio seguente viene `<listeners>` illustrato come utilizzare l'elemento `mySource` per aggiungere un listener di traccia della console all'origine e rimuovere il listener di traccia predefinito.</span><span class="sxs-lookup"><span data-stu-id="32050-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="32050-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32050-136">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="32050-137">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="32050-137">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="32050-138">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="32050-138">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
