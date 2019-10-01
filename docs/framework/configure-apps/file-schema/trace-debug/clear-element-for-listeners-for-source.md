---
title: Elemento <clear> per <listeners> per <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 05c20040ef59f4dee6b15bbe0b0369281b532754
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697198"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="af2d2-102">Elemento > \<clear per \<listeners > per \<source ></span><span class="sxs-lookup"><span data-stu-id="af2d2-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="af2d2-103">Cancella la raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="af2d2-103">Clears the `Listeners` collection for a trace source.</span></span>  
  
[<span data-ttu-id="af2d2-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="af2d2-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="af2d2-105">&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="af2d2-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="af2d2-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="af2d2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="af2d2-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<source >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="af2d2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="af2d2-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0listeners >** ](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="af2d2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>  
<span data-ttu-id="af2d2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**</span><span class="sxs-lookup"><span data-stu-id="af2d2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af2d2-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af2d2-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af2d2-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="af2d2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="af2d2-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="af2d2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af2d2-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="af2d2-113">Attributes</span></span>  
 <span data-ttu-id="af2d2-114">No.</span><span class="sxs-lookup"><span data-stu-id="af2d2-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="af2d2-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="af2d2-115">Child Elements</span></span>  
 <span data-ttu-id="af2d2-116">No.</span><span class="sxs-lookup"><span data-stu-id="af2d2-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af2d2-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="af2d2-117">Parent Elements</span></span>  
  
|<span data-ttu-id="af2d2-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="af2d2-118">Element</span></span>|<span data-ttu-id="af2d2-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="af2d2-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="af2d2-120">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="af2d2-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="af2d2-121">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="af2d2-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="af2d2-122">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="af2d2-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="af2d2-123">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="af2d2-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="af2d2-124">Specifica i listener che raccolgono, archiviano e indirizzano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="af2d2-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af2d2-125">Note</span><span class="sxs-lookup"><span data-stu-id="af2d2-125">Remarks</span></span>  
 <span data-ttu-id="af2d2-126">L'elemento `<clear>` rimuove tutti i listener dalla raccolta `Listeners` per un'origine di traccia, incluso il <xref:System.Diagnostics.DefaultTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="af2d2-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="af2d2-127">È possibile utilizzare l'elemento `<clear>` prima di utilizzare l'elemento `<add>` per assicurarsi che non siano presenti altri listener attivi nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="af2d2-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="af2d2-128">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="af2d2-128">Configuration File</span></span>  
 <span data-ttu-id="af2d2-129">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="af2d2-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af2d2-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="af2d2-130">Example</span></span>  
 <span data-ttu-id="af2d2-131">Nell'esempio seguente viene illustrato come utilizzare l'elemento `<clear>` prima di utilizzare gli elementi `<add>` per aggiungere i listener `console` e `textListener` alla raccolta `Listeners` per l'origine di traccia `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="af2d2-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="af2d2-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af2d2-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="af2d2-133">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="af2d2-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="af2d2-134">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="af2d2-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
