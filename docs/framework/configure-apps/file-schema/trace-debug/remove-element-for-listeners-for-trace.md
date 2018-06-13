---
title: '&lt;rimuovere&gt; elemento per &lt;listener&gt; per &lt;traccia&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 11f4b648ac1ffc614f18a3686eb2b6508a272980
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746553"
---
# <a name="ltremovegt-element-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="7ad86-102">&lt;rimuovere&gt; elemento per &lt;listener&gt; per &lt;traccia&gt;</span><span class="sxs-lookup"><span data-stu-id="7ad86-102">&lt;remove&gt; Element for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="7ad86-103">Rimuove un listener di **listener** insieme.</span><span class="sxs-lookup"><span data-stu-id="7ad86-103">Removes a listener from the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="7ad86-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7ad86-104">\<configuration></span></span>  
<span data-ttu-id="7ad86-105">\<System. Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="7ad86-105">\<system.diagnostics></span></span>  
<span data-ttu-id="7ad86-106">\<traccia ></span><span class="sxs-lookup"><span data-stu-id="7ad86-106">\<trace></span></span>  
<span data-ttu-id="7ad86-107">\<listener ></span><span class="sxs-lookup"><span data-stu-id="7ad86-107">\<listeners></span></span>  
<span data-ttu-id="7ad86-108">\<rimuovere ></span><span class="sxs-lookup"><span data-stu-id="7ad86-108">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ad86-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ad86-109">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ad86-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7ad86-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7ad86-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7ad86-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ad86-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="7ad86-112">Attributes</span></span>  
  
|<span data-ttu-id="7ad86-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="7ad86-113">Attribute</span></span>|<span data-ttu-id="7ad86-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ad86-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7ad86-115">**name**</span><span class="sxs-lookup"><span data-stu-id="7ad86-115">**name**</span></span>|<span data-ttu-id="7ad86-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7ad86-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="7ad86-117">Il nome del listener da rimuovere il **listener** insieme.</span><span class="sxs-lookup"><span data-stu-id="7ad86-117">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7ad86-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7ad86-118">Child Elements</span></span>  
 <span data-ttu-id="7ad86-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7ad86-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7ad86-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7ad86-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7ad86-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="7ad86-121">Element</span></span>|<span data-ttu-id="7ad86-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ad86-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7ad86-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7ad86-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="7ad86-124">Specifica un listener per la raccolta, la memorizzazione e indirizza i messaggi.</span><span class="sxs-lookup"><span data-stu-id="7ad86-124">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="7ad86-125">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="7ad86-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="7ad86-126">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="7ad86-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="7ad86-127">Configura il servizio traccia ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="7ad86-127">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ad86-128">Note</span><span class="sxs-lookup"><span data-stu-id="7ad86-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ad86-129">Rimozione di <xref:System.Diagnostics.DefaultTraceListener> dal `Listeners` raccolta modifica il comportamento del <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, e <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> metodi.</span><span class="sxs-lookup"><span data-stu-id="7ad86-129">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="7ad86-130">La chiamata a un `Assert` o `Fail` metodo normalmente comporta la visualizzazione di una finestra di messaggio, ma la finestra di messaggio non viene visualizzata se il <xref:System.Diagnostics.DefaultTraceListener> non si trova nel `Listeners` insieme.</span><span class="sxs-lookup"><span data-stu-id="7ad86-130">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ad86-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="7ad86-131">Example</span></span>  
 <span data-ttu-id="7ad86-132">Nell'esempio seguente viene illustrato come rimuovere il listener di traccia predefinito dalla traccia **listener** insieme.</span><span class="sxs-lookup"><span data-stu-id="7ad86-132">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ad86-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ad86-133">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 [<span data-ttu-id="7ad86-134">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="7ad86-134">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
