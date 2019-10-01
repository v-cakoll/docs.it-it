---
title: Elemento <remove> per <listeners> per <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: 56d1e56514aed98d5f3b9f7363e461af6ac68a8c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697224"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="35cb9-102">Elemento > \<remove per \<listeners > per \<trace ></span><span class="sxs-lookup"><span data-stu-id="35cb9-102">\<remove> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="35cb9-103">Rimuove un listener dalla raccolta **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="35cb9-103">Removes a listener from the **Listeners** collection.</span></span>  
  
[<span data-ttu-id="35cb9-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="35cb9-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="35cb9-105">&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="35cb9-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="35cb9-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<trace >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="35cb9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>  
<span data-ttu-id="35cb9-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<listeners >** ](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="35cb9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>  
<span data-ttu-id="35cb9-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="35cb9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35cb9-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35cb9-109">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35cb9-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="35cb9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="35cb9-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="35cb9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35cb9-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="35cb9-112">Attributes</span></span>  
  
|<span data-ttu-id="35cb9-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="35cb9-113">Attribute</span></span>|<span data-ttu-id="35cb9-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="35cb9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="35cb9-115">**name**</span><span class="sxs-lookup"><span data-stu-id="35cb9-115">**name**</span></span>|<span data-ttu-id="35cb9-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="35cb9-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="35cb9-117">Nome del listener da rimuovere dalla raccolta **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="35cb9-117">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35cb9-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="35cb9-118">Child Elements</span></span>  
 <span data-ttu-id="35cb9-119">No.</span><span class="sxs-lookup"><span data-stu-id="35cb9-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35cb9-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="35cb9-120">Parent Elements</span></span>  
  
|<span data-ttu-id="35cb9-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="35cb9-121">Element</span></span>|<span data-ttu-id="35cb9-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="35cb9-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="35cb9-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="35cb9-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="35cb9-124">Specifica un listener che raccoglie, archivia e instrada i messaggi.</span><span class="sxs-lookup"><span data-stu-id="35cb9-124">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="35cb9-125">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="35cb9-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="35cb9-126">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="35cb9-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="35cb9-127">Configura il servizio di traccia ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="35cb9-127">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35cb9-128">Note</span><span class="sxs-lookup"><span data-stu-id="35cb9-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="35cb9-129">La rimozione di <xref:System.Diagnostics.DefaultTraceListener> dalla raccolta `Listeners` modifica il comportamento dei metodi <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> e <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="35cb9-129">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="35cb9-130">La chiamata di un metodo `Assert` o `Fail` comporta in genere la visualizzazione di una finestra di messaggio, ma la finestra di messaggio non viene visualizzata se la <xref:System.Diagnostics.DefaultTraceListener> non è presente nella raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="35cb9-130">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35cb9-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="35cb9-131">Example</span></span>  
 <span data-ttu-id="35cb9-132">Nell'esempio seguente viene illustrato come rimuovere il listener di traccia predefinito dalla raccolta di **listener** di traccia.</span><span class="sxs-lookup"><span data-stu-id="35cb9-132">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="35cb9-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35cb9-133">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="35cb9-134">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="35cb9-134">Trace and Debug Settings Schema</span></span>](index.md)
