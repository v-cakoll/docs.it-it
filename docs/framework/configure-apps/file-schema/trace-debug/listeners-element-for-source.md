---
title: Elemento <listeners> per <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: 0eee325e01b41a15a19e4f40f479596f9d70f73b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153412"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="61846-102">Elemento \<listeners> per \<source></span><span class="sxs-lookup"><span data-stu-id="61846-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="61846-103">Aggiunge o rimuove i listener nella <xref:System.Diagnostics.TraceSource.Listeners%2A> raccolta per un oggetto <xref:System.Diagnostics.TraceSource> .</span><span class="sxs-lookup"><span data-stu-id="61846-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="61846-104">Un listener indirizza l'output di traccia a una destinazione appropriata, ad esempio un log, una finestra o un file di testo.</span><span class="sxs-lookup"><span data-stu-id="61846-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**  
  
## <a name="syntax"></a><span data-ttu-id="61846-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61846-105">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61846-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="61846-106">Attributes and Elements</span></span>  
 <span data-ttu-id="61846-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="61846-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61846-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="61846-108">Attributes</span></span>  
 <span data-ttu-id="61846-109">No.</span><span class="sxs-lookup"><span data-stu-id="61846-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="61846-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="61846-110">Child Elements</span></span>  
  
|<span data-ttu-id="61846-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="61846-111">Element</span></span>|<span data-ttu-id="61846-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61846-112">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-source.md)|<span data-ttu-id="61846-113">Aggiunge un listener alla raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="61846-113">Adds a listener to the `Listeners` collection.</span></span>|  
|[\<remove>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="61846-114">Rimuove un listener dalla `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="61846-114">Removes a listener from the `Listeners` collection.</span></span>|  
|[\<clear>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="61846-115">Cancella la raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="61846-115">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="61846-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="61846-116">Parent Elements</span></span>  
  
|<span data-ttu-id="61846-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="61846-117">Element</span></span>|<span data-ttu-id="61846-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61846-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="61846-119">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="61846-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="61846-120">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="61846-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="61846-121">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="61846-121">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="61846-122">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="61846-122">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61846-123">Commenti</span><span class="sxs-lookup"><span data-stu-id="61846-123">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="61846-124">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="61846-124">Configuration File</span></span>  
 <span data-ttu-id="61846-125">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="61846-125">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61846-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="61846-126">Example</span></span>  
 <span data-ttu-id="61846-127">Nell'esempio seguente viene illustrato come utilizzare l' `<listeners>` elemento per aggiungere un listener di traccia della console all' `mySource` origine e per rimuovere il listener di traccia predefinito.</span><span class="sxs-lookup"><span data-stu-id="61846-127">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="61846-128">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="61846-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="61846-129">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="61846-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="61846-130">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="61846-130">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
