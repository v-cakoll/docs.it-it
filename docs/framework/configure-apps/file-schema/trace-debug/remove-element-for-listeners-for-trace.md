---
title: <remove>Elemento per <listeners> per<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: f06973ec30d5061e4a200d6bf7e68adcf6302018
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088840"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="f5920-102">\<remove>Elemento per \<listeners> per\<trace></span><span class="sxs-lookup"><span data-stu-id="f5920-102">\<remove> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="f5920-103">Rimuove un listener dalla raccolta **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="f5920-103">Removes a listener from the **Listeners** collection.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="f5920-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f5920-104">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5920-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f5920-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f5920-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f5920-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5920-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="f5920-107">Attributes</span></span>  
  
|<span data-ttu-id="f5920-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="f5920-108">Attribute</span></span>|<span data-ttu-id="f5920-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5920-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5920-110">**nome**</span><span class="sxs-lookup"><span data-stu-id="f5920-110">**name**</span></span>|<span data-ttu-id="f5920-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f5920-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="f5920-112">Nome del listener da rimuovere dalla raccolta **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="f5920-112">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5920-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f5920-113">Child Elements</span></span>  
 <span data-ttu-id="f5920-114">No.</span><span class="sxs-lookup"><span data-stu-id="f5920-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f5920-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f5920-115">Parent Elements</span></span>  
  
|<span data-ttu-id="f5920-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="f5920-116">Element</span></span>|<span data-ttu-id="f5920-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5920-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f5920-118">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f5920-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="f5920-119">Specifica un listener che raccoglie, archivia e instrada i messaggi.</span><span class="sxs-lookup"><span data-stu-id="f5920-119">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="f5920-120">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="f5920-120">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="f5920-121">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="f5920-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="f5920-122">Configura il servizio di traccia di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="f5920-122">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5920-123">Commenti</span><span class="sxs-lookup"><span data-stu-id="f5920-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f5920-124">La rimozione <xref:System.Diagnostics.DefaultTraceListener> di dalla `Listeners` raccolta modifica il comportamento dei <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> metodi,, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> e <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f5920-124">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="f5920-125">La chiamata `Assert` `Fail` di un metodo o determina in genere la visualizzazione di una finestra di messaggio, ma la finestra di messaggio non viene visualizzata se l'oggetto <xref:System.Diagnostics.DefaultTraceListener> non è presente nella `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="f5920-125">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5920-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="f5920-126">Example</span></span>  
 <span data-ttu-id="f5920-127">Nell'esempio seguente viene illustrato come rimuovere il listener di traccia predefinito dalla raccolta di **listener** di traccia.</span><span class="sxs-lookup"><span data-stu-id="f5920-127">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f5920-128">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f5920-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="f5920-129">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="f5920-129">Trace and Debug Settings Schema</span></span>](index.md)
