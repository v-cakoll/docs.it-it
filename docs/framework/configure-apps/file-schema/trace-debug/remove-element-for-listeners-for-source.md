---
title: <remove>Elemento per <listeners> per<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 657e6db2af9b99b3bbf03afc6aab02c58a830f2d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153335"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="22ac9-102">\<remove>Elemento per \<listeners> per\<source></span><span class="sxs-lookup"><span data-stu-id="22ac9-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="22ac9-103">Rimuove un listener dalla raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="22ac9-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="22ac9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22ac9-104">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22ac9-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="22ac9-105">Attributes and Elements</span></span>  
 <span data-ttu-id="22ac9-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="22ac9-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22ac9-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="22ac9-107">Attributes</span></span>  
  
|<span data-ttu-id="22ac9-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="22ac9-108">Attribute</span></span>|<span data-ttu-id="22ac9-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22ac9-109">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="22ac9-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="22ac9-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="22ac9-111">Nome del listener da rimuovere dalla `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="22ac9-111">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22ac9-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="22ac9-112">Child Elements</span></span>  
 <span data-ttu-id="22ac9-113">No.</span><span class="sxs-lookup"><span data-stu-id="22ac9-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22ac9-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="22ac9-114">Parent Elements</span></span>  
  
|<span data-ttu-id="22ac9-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="22ac9-115">Element</span></span>|<span data-ttu-id="22ac9-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22ac9-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="22ac9-117">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22ac9-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="22ac9-118">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="22ac9-118">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="22ac9-119">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="22ac9-119">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="22ac9-120">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="22ac9-120">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="22ac9-121">Specifica i listener che raccolgono, archiviano e indirizzano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="22ac9-121">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22ac9-122">Commenti</span><span class="sxs-lookup"><span data-stu-id="22ac9-122">Remarks</span></span>  
 <span data-ttu-id="22ac9-123">L' `<remove>` elemento rimuove un listener specificato dalla `Listeners` raccolta per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="22ac9-123">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="22ac9-124">È possibile rimuovere un elemento dalla `Listeners` raccolta per un'origine di traccia a livello di codice chiamando il <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> Metodo sulla <xref:System.Diagnostics.TraceSource.Listeners%2A> proprietà dell' <xref:System.Diagnostics.TraceSource> istanza.</span><span class="sxs-lookup"><span data-stu-id="22ac9-124">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="22ac9-125">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="22ac9-125">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22ac9-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="22ac9-126">Example</span></span>  
 <span data-ttu-id="22ac9-127">Nell'esempio seguente viene illustrato come utilizzare l' `<remove>` elemento prima di utilizzare l' `<add>` elemento per aggiungere il listener `console` alla `Listeners` raccolta per l'origine di traccia `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="22ac9-127">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="22ac9-128">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="22ac9-128">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="22ac9-129">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="22ac9-129">Trace and Debug Settings Schema</span></span>](index.md)
- [\<clear>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="22ac9-130">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="22ac9-130">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
