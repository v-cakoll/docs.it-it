---
title: '&lt;rimuovere&gt; (elemento) per &lt;listener&gt; per &lt;origine&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 8beb3ef041b153535afcb8bd92e1c29787e1f161
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654412"
---
# <a name="ltremovegt-element-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="99241-102">&lt;rimuovere&gt; (elemento) per &lt;listener&gt; per &lt;origine&gt;</span><span class="sxs-lookup"><span data-stu-id="99241-102">&lt;remove&gt; Element for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="99241-103">Rimuove un listener dalla raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="99241-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="99241-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="99241-104">\<configuration></span></span>  
<span data-ttu-id="99241-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="99241-105">\<system.diagnostics></span></span>  
<span data-ttu-id="99241-106">\<sources></span><span class="sxs-lookup"><span data-stu-id="99241-106">\<sources></span></span>  
<span data-ttu-id="99241-107">\<origine ></span><span class="sxs-lookup"><span data-stu-id="99241-107">\<source></span></span>  
<span data-ttu-id="99241-108">\<listeners></span><span class="sxs-lookup"><span data-stu-id="99241-108">\<listeners></span></span>  
<span data-ttu-id="99241-109">\<remove></span><span class="sxs-lookup"><span data-stu-id="99241-109">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99241-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99241-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99241-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="99241-111">Attributes and Elements</span></span>  
 <span data-ttu-id="99241-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="99241-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99241-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="99241-113">Attributes</span></span>  
  
|<span data-ttu-id="99241-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="99241-114">Attribute</span></span>|<span data-ttu-id="99241-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99241-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="99241-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="99241-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="99241-117">Il nome del listener da rimuovere dal `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="99241-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99241-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="99241-118">Child Elements</span></span>  
 <span data-ttu-id="99241-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="99241-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99241-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="99241-120">Parent Elements</span></span>  
  
|<span data-ttu-id="99241-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="99241-121">Element</span></span>|<span data-ttu-id="99241-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99241-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="99241-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="99241-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="99241-124">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="99241-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="99241-125">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="99241-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="99241-126">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="99241-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="99241-127">Specifica i listener di raccolgono, archiviano e indirizzano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="99241-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99241-128">Note</span><span class="sxs-lookup"><span data-stu-id="99241-128">Remarks</span></span>  
 <span data-ttu-id="99241-129">Il `<remove>` elemento rimuove un listener specificato dal `Listeners` insieme per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="99241-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="99241-130">È possibile rimuovere un elemento dal `Listeners` insieme per un'origine di traccia a livello di codice chiamando il <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> metodo sul <xref:System.Diagnostics.TraceSource.Listeners%2A> proprietà del <xref:System.Diagnostics.TraceSource> istanza.</span><span class="sxs-lookup"><span data-stu-id="99241-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="99241-131">Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="99241-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99241-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="99241-132">Example</span></span>  
 <span data-ttu-id="99241-133">Nell'esempio seguente viene illustrato come utilizzare il `<remove>` elemento prima di usare il `<add>` elemento a cui aggiungere il listener `console` per il `Listeners` raccolta per l'origine di traccia `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="99241-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="99241-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99241-134">See also</span></span>
- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="99241-135">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="99241-135">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="99241-136">\<clear></span><span class="sxs-lookup"><span data-stu-id="99241-136">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="99241-137">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="99241-137">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
