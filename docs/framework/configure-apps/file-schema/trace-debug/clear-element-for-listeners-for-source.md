---
title: <clear>Elemento per <listeners> per<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 7f9ddd93d27c3619119702c82c9e8752dab1af7b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153581"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="12a37-102">\<clear>Elemento per \<listeners> per\<source></span><span class="sxs-lookup"><span data-stu-id="12a37-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="12a37-103">Cancella la raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="12a37-103">Clears the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="12a37-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="12a37-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12a37-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="12a37-105">Attributes and Elements</span></span>  
 <span data-ttu-id="12a37-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="12a37-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12a37-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="12a37-107">Attributes</span></span>  
 <span data-ttu-id="12a37-108">No.</span><span class="sxs-lookup"><span data-stu-id="12a37-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="12a37-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="12a37-109">Child Elements</span></span>  
 <span data-ttu-id="12a37-110">No.</span><span class="sxs-lookup"><span data-stu-id="12a37-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="12a37-111">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="12a37-111">Parent Elements</span></span>  
  
|<span data-ttu-id="12a37-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="12a37-112">Element</span></span>|<span data-ttu-id="12a37-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12a37-113">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="12a37-114">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="12a37-114">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="12a37-115">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="12a37-115">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="12a37-116">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="12a37-116">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="12a37-117">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="12a37-117">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="12a37-118">Specifica i listener che raccolgono, archiviano e indirizzano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="12a37-118">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12a37-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="12a37-119">Remarks</span></span>  
 <span data-ttu-id="12a37-120">L' `<clear>` elemento rimuove tutti i listener dalla `Listeners` raccolta per un'origine di traccia, incluso <xref:System.Diagnostics.DefaultTraceListener> .</span><span class="sxs-lookup"><span data-stu-id="12a37-120">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="12a37-121">È possibile usare l' `<clear>` elemento prima di usare l' `<add>` elemento per assicurarsi che non ci siano altri listener attivi nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="12a37-121">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="12a37-122">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="12a37-122">Configuration File</span></span>  
 <span data-ttu-id="12a37-123">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="12a37-123">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12a37-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="12a37-124">Example</span></span>  
 <span data-ttu-id="12a37-125">Nell'esempio seguente viene illustrato come utilizzare l' `<clear>` elemento prima di utilizzare gli `<add>` elementi per aggiungere i listener `console` e `textListener` alla `Listeners` raccolta per l'origine di traccia `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="12a37-125">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="12a37-126">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="12a37-126">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="12a37-127">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="12a37-127">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="12a37-128">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="12a37-128">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
