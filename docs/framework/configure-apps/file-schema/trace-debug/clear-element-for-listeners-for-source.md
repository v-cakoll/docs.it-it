---
title: Elemento <clear> per <listeners> per <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 4567f236397435e89371ca4c80730ff964fddd21
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088926"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="66843-102">\<elemento clear > per \<listeners > per \<origine ></span><span class="sxs-lookup"><span data-stu-id="66843-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="66843-103">Cancella la raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="66843-103">Clears the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="66843-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="66843-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="66843-105">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="66843-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="66843-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**origini**](sources-element.md) ></span><span class="sxs-lookup"><span data-stu-id="66843-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="66843-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**origine**](source-element.md) ></span><span class="sxs-lookup"><span data-stu-id="66843-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="66843-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**listener**](listeners-element-for-source.md) ></span><span class="sxs-lookup"><span data-stu-id="66843-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="66843-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**clear >**</span><span class="sxs-lookup"><span data-stu-id="66843-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="66843-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="66843-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66843-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="66843-111">Attributes and Elements</span></span>  
 <span data-ttu-id="66843-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="66843-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66843-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="66843-113">Attributes</span></span>  
 <span data-ttu-id="66843-114">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="66843-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="66843-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="66843-115">Child Elements</span></span>  
 <span data-ttu-id="66843-116">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="66843-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="66843-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="66843-117">Parent Elements</span></span>  
  
|<span data-ttu-id="66843-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="66843-118">Element</span></span>|<span data-ttu-id="66843-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66843-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="66843-120">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="66843-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="66843-121">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="66843-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="66843-122">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="66843-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="66843-123">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="66843-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="66843-124">Specifica i listener che raccolgono, archiviano e indirizzano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="66843-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66843-125">Note</span><span class="sxs-lookup"><span data-stu-id="66843-125">Remarks</span></span>  
 <span data-ttu-id="66843-126">L'elemento `<clear>` rimuove tutti i listener dalla raccolta `Listeners` per un'origine di traccia, incluso il <xref:System.Diagnostics.DefaultTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="66843-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="66843-127">È possibile utilizzare l'elemento `<clear>` prima di utilizzare l'elemento `<add>` per verificare che non siano presenti altri listener attivi nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="66843-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="66843-128">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="66843-128">Configuration File</span></span>  
 <span data-ttu-id="66843-129">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="66843-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66843-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="66843-130">Example</span></span>  
 <span data-ttu-id="66843-131">Nell'esempio seguente viene illustrato come utilizzare l'elemento `<clear>` prima di utilizzare gli elementi `<add>` per aggiungere i listener `console` e `textListener` alla raccolta di `Listeners` per l'origine di traccia `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="66843-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="66843-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66843-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="66843-133">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="66843-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="66843-134">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="66843-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
