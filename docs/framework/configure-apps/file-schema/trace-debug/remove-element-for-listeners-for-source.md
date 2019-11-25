---
title: Elemento <remove> per <listeners> per <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 75db45d4e868ce88e030ec6a43c8bdaf788a1102
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088859"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="f2f19-102">\<rimuovere > elemento per \<listener > per \<origine ></span><span class="sxs-lookup"><span data-stu-id="f2f19-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="f2f19-103">Rimuove un listener dalla raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="f2f19-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="f2f19-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f2f19-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f2f19-105">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="f2f19-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="f2f19-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**origini**](sources-element.md) ></span><span class="sxs-lookup"><span data-stu-id="f2f19-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="f2f19-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**origine**](source-element.md) ></span><span class="sxs-lookup"><span data-stu-id="f2f19-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="f2f19-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**listener**](listeners-element-for-source.md) ></span><span class="sxs-lookup"><span data-stu-id="f2f19-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="f2f19-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<rimuovere >**</span><span class="sxs-lookup"><span data-stu-id="f2f19-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f2f19-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f2f19-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2f19-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f2f19-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f2f19-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f2f19-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2f19-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="f2f19-113">Attributes</span></span>  
  
|<span data-ttu-id="f2f19-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="f2f19-114">Attribute</span></span>|<span data-ttu-id="f2f19-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2f19-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="f2f19-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f2f19-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="f2f19-117">Nome del listener da rimuovere dalla raccolta di `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="f2f19-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f2f19-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f2f19-118">Child Elements</span></span>  
 <span data-ttu-id="f2f19-119">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="f2f19-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f2f19-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f2f19-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f2f19-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="f2f19-121">Element</span></span>|<span data-ttu-id="f2f19-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2f19-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f2f19-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f2f19-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="f2f19-124">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="f2f19-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="f2f19-125">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="f2f19-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="f2f19-126">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="f2f19-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="f2f19-127">Specifica i listener che raccolgono, archiviano e indirizzano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="f2f19-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2f19-128">Note</span><span class="sxs-lookup"><span data-stu-id="f2f19-128">Remarks</span></span>  
 <span data-ttu-id="f2f19-129">L'elemento `<remove>` rimuove un listener specificato dalla raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="f2f19-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="f2f19-130">È possibile rimuovere un elemento dalla raccolta `Listeners` per un'origine di traccia a livello di codice chiamando il metodo <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> sulla proprietà <xref:System.Diagnostics.TraceSource.Listeners%2A> dell'istanza di <xref:System.Diagnostics.TraceSource>.</span><span class="sxs-lookup"><span data-stu-id="f2f19-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="f2f19-131">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f2f19-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2f19-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="f2f19-132">Example</span></span>  
 <span data-ttu-id="f2f19-133">Nell'esempio seguente viene illustrato come utilizzare l'elemento `<remove>` prima di utilizzare l'elemento `<add>` per aggiungere il listener `console` alla raccolta `Listeners` per l'origine di traccia `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="f2f19-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"   
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="f2f19-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2f19-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="f2f19-135">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="f2f19-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f2f19-136">\<clear></span><span class="sxs-lookup"><span data-stu-id="f2f19-136">\<clear></span></span>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="f2f19-137">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="f2f19-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
