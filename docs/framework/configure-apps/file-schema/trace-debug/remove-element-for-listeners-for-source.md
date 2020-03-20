---
title: <remove>Elemento <listeners> per<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 657e6db2af9b99b3bbf03afc6aab02c58a830f2d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153335"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="6bbf3-102">\<remove> \<Element per \<i listener> per i> di origine</span><span class="sxs-lookup"><span data-stu-id="6bbf3-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="6bbf3-103">Rimuove un listener dalla raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="6bbf3-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="6bbf3-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6bbf3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6bbf3-105">&nbsp;&nbsp;[**\<>system.diagnostics**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="6bbf3-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="6bbf3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<fonti>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="6bbf3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="6bbf3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="6bbf3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="6bbf3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di ascoltatori**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="6bbf3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="6bbf3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<rimuovere>**</span><span class="sxs-lookup"><span data-stu-id="6bbf3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6bbf3-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6bbf3-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6bbf3-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6bbf3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6bbf3-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6bbf3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6bbf3-113">Attributes</span><span class="sxs-lookup"><span data-stu-id="6bbf3-113">Attributes</span></span>  
  
|<span data-ttu-id="6bbf3-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="6bbf3-114">Attribute</span></span>|<span data-ttu-id="6bbf3-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6bbf3-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="6bbf3-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6bbf3-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="6bbf3-117">Nome del listener da rimuovere `Listeners` dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="6bbf3-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6bbf3-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6bbf3-118">Child Elements</span></span>  
 <span data-ttu-id="6bbf3-119">No.</span><span class="sxs-lookup"><span data-stu-id="6bbf3-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6bbf3-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6bbf3-120">Parent Elements</span></span>  
  
|<span data-ttu-id="6bbf3-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="6bbf3-121">Element</span></span>|<span data-ttu-id="6bbf3-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6bbf3-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6bbf3-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6bbf3-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="6bbf3-124">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="6bbf3-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="6bbf3-125">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="6bbf3-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="6bbf3-126">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="6bbf3-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="6bbf3-127">Specifica i listener che raccolgono, archiviano e instradano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="6bbf3-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6bbf3-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6bbf3-128">Remarks</span></span>  
 <span data-ttu-id="6bbf3-129">L'elemento `<remove>` rimuove un `Listeners` listener specificato dalla raccolta per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="6bbf3-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="6bbf3-130">È possibile rimuovere un `Listeners` elemento dalla raccolta per un'origine di traccia a livello di codice chiamando il <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> metodo sulla <xref:System.Diagnostics.TraceSource.Listeners%2A> proprietà dell'istanza. <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="6bbf3-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="6bbf3-131">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine.config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6bbf3-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6bbf3-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="6bbf3-132">Example</span></span>  
 <span data-ttu-id="6bbf3-133">Nell'esempio riportato di `<remove>` seguito viene `<add>` illustrato come `console` utilizzare `Listeners` l'elemento prima `TraceSourceApp`di utilizzare l'elemento per aggiungere il listener all'insieme per l'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="6bbf3-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6bbf3-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bbf3-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="6bbf3-135">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="6bbf3-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6bbf3-136">\<>chiari</span><span class="sxs-lookup"><span data-stu-id="6bbf3-136">\<clear></span></span>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="6bbf3-137">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="6bbf3-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
