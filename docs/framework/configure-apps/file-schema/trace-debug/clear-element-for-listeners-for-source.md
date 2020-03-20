---
title: <clear>Elemento <listeners> per<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 7f9ddd93d27c3619119702c82c9e8752dab1af7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153581"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="9d9ef-102">\<Clear> \<Element per \<i listener> per i> di origine</span><span class="sxs-lookup"><span data-stu-id="9d9ef-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="9d9ef-103">Cancella la raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="9d9ef-103">Clears the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="9d9ef-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9d9ef-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9d9ef-105">&nbsp;&nbsp;[**\<>system.diagnostics**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="9d9ef-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="9d9ef-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<fonti>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="9d9ef-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="9d9ef-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="9d9ef-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="9d9ef-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di ascoltatori**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="9d9ef-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="9d9ef-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>chiari**</span><span class="sxs-lookup"><span data-stu-id="9d9ef-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="9d9ef-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9d9ef-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d9ef-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9d9ef-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9d9ef-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9d9ef-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d9ef-113">Attributes</span><span class="sxs-lookup"><span data-stu-id="9d9ef-113">Attributes</span></span>  
 <span data-ttu-id="9d9ef-114">No.</span><span class="sxs-lookup"><span data-stu-id="9d9ef-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9d9ef-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9d9ef-115">Child Elements</span></span>  
 <span data-ttu-id="9d9ef-116">No.</span><span class="sxs-lookup"><span data-stu-id="9d9ef-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9d9ef-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9d9ef-117">Parent Elements</span></span>  
  
|<span data-ttu-id="9d9ef-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="9d9ef-118">Element</span></span>|<span data-ttu-id="9d9ef-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d9ef-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9d9ef-120">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9d9ef-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="9d9ef-121">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="9d9ef-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="9d9ef-122">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="9d9ef-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="9d9ef-123">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="9d9ef-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="9d9ef-124">Specifica i listener che raccolgono, archiviano e instradano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="9d9ef-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d9ef-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9d9ef-125">Remarks</span></span>  
 <span data-ttu-id="9d9ef-126">L'elemento `<clear>` rimuove tutti `Listeners` i listener dalla raccolta <xref:System.Diagnostics.DefaultTraceListener>per un'origine di traccia, incluso l'oggetto .</span><span class="sxs-lookup"><span data-stu-id="9d9ef-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="9d9ef-127">È possibile `<clear>` utilizzare l'elemento prima di utilizzare l'elemento `<add>` per essere certi che non siano presenti altri listener attivi nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="9d9ef-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="9d9ef-128">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="9d9ef-128">Configuration File</span></span>  
 <span data-ttu-id="9d9ef-129">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine.config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9d9ef-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d9ef-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="9d9ef-130">Example</span></span>  
 <span data-ttu-id="9d9ef-131">Nell'esempio riportato di `<clear>` seguito viene `<add>` illustrato come utilizzare `console` `textListener` l'elemento prima di utilizzare gli elementi per aggiungere i listener e all'insieme `Listeners` per l'origine `TraceSourceApp`di traccia.</span><span class="sxs-lookup"><span data-stu-id="9d9ef-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9d9ef-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d9ef-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="9d9ef-133">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="9d9ef-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9d9ef-134">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="9d9ef-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
