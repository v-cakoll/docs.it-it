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
# <a name="listeners-element-for-source"></a><span data-ttu-id="a91c4-102">Elemento > \<listeners per \<SOURCE ></span><span class="sxs-lookup"><span data-stu-id="a91c4-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="a91c4-103">Aggiunge o rimuove i listener nella raccolta <xref:System.Diagnostics.TraceSource.Listeners%2A> per un <xref:System.Diagnostics.TraceSource>.</span><span class="sxs-lookup"><span data-stu-id="a91c4-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="a91c4-104">Un listener indirizza l'output di traccia a una destinazione appropriata, ad esempio un log, una finestra o un file di testo.</span><span class="sxs-lookup"><span data-stu-id="a91c4-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
[<span data-ttu-id="a91c4-105"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="a91c4-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="a91c4-106">&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="a91c4-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="a91c4-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="a91c4-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="a91c4-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<source >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="a91c4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="a91c4-109">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<listeners >**</span><span class="sxs-lookup"><span data-stu-id="a91c4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a91c4-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a91c4-110">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a91c4-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a91c4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a91c4-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a91c4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a91c4-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="a91c4-113">Attributes</span></span>  
 <span data-ttu-id="a91c4-114">No.</span><span class="sxs-lookup"><span data-stu-id="a91c4-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a91c4-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a91c4-115">Child Elements</span></span>  
  
|<span data-ttu-id="a91c4-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="a91c4-116">Element</span></span>|<span data-ttu-id="a91c4-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a91c4-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a91c4-118">\<add></span><span class="sxs-lookup"><span data-stu-id="a91c4-118">\<add></span></span>](add-element-for-listeners-for-source.md)|<span data-ttu-id="a91c4-119">Aggiunge un listener alla raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="a91c4-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="a91c4-120">\<remove></span><span class="sxs-lookup"><span data-stu-id="a91c4-120">\<remove></span></span>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="a91c4-121">Rimuove un listener dalla raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="a91c4-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="a91c4-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="a91c4-122">\<clear></span></span>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="a91c4-123">Cancella la raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="a91c4-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a91c4-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a91c4-124">Parent Elements</span></span>  
  
|<span data-ttu-id="a91c4-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="a91c4-125">Element</span></span>|<span data-ttu-id="a91c4-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a91c4-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a91c4-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a91c4-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a91c4-128">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="a91c4-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="a91c4-129">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="a91c4-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="a91c4-130">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="a91c4-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a91c4-131">Note</span><span class="sxs-lookup"><span data-stu-id="a91c4-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="a91c4-132">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="a91c4-132">Configuration File</span></span>  
 <span data-ttu-id="a91c4-133">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a91c4-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a91c4-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="a91c4-134">Example</span></span>  
 <span data-ttu-id="a91c4-135">Nell'esempio seguente viene illustrato come utilizzare l'elemento `<listeners>` per aggiungere un listener di traccia della console all'origine `mySource` e rimuovere il listener di traccia predefinito.</span><span class="sxs-lookup"><span data-stu-id="a91c4-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a91c4-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a91c4-136">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="a91c4-137">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="a91c4-137">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a91c4-138">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="a91c4-138">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
