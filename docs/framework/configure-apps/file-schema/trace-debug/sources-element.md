---
title: <sources> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
ms.openlocfilehash: 2a76816ee73f516b3c7544877a77531acaa8e09c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153269"
---
# <a name="sources-element"></a><span data-ttu-id="ef693-102">\<origini>elemento</span><span class="sxs-lookup"><span data-stu-id="ef693-102">\<sources> Element</span></span>
<span data-ttu-id="ef693-103">Specifica le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="ef693-103">Specifies trace sources that initiate tracing messages.</span></span>  

<span data-ttu-id="ef693-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ef693-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ef693-105">&nbsp;&nbsp;[**\<>system.diagnostics**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="ef693-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="ef693-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<fonti>**</span><span class="sxs-lookup"><span data-stu-id="ef693-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sources>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ef693-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef693-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef693-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ef693-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ef693-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ef693-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef693-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="ef693-110">Attributes</span></span>  
 <span data-ttu-id="ef693-111">No.</span><span class="sxs-lookup"><span data-stu-id="ef693-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ef693-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ef693-112">Child Elements</span></span>  
  
|<span data-ttu-id="ef693-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef693-113">Element</span></span>|<span data-ttu-id="ef693-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef693-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef693-115">\<></span><span class="sxs-lookup"><span data-stu-id="ef693-115">\<source></span></span>](source-element.md)|<span data-ttu-id="ef693-116">Elemento obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ef693-116">Required element.</span></span><br /><br /> <span data-ttu-id="ef693-117">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="ef693-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ef693-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ef693-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ef693-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef693-119">Element</span></span>|<span data-ttu-id="ef693-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef693-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ef693-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ef693-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="ef693-122">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="ef693-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef693-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ef693-123">Remarks</span></span>  
 <span data-ttu-id="ef693-124">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine.config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ef693-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef693-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="ef693-125">Example</span></span>  
 <span data-ttu-id="ef693-126">Nell'esempio riportato di `<sources>` seguito viene illustrato `mySource` come utilizzare l'elemento per `sourceSwitch`aggiungere l'origine di traccia e impostare il livello per l'opzione di origine denominata .</span><span class="sxs-lookup"><span data-stu-id="ef693-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="ef693-127">Viene aggiunto un listener di traccia della console che scrive le informazioni di traccia nella console.</span><span class="sxs-lookup"><span data-stu-id="ef693-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <sources>  
         <source name="mySource" switchName="sourceSwitch"
            switchType="System.Diagnostics.SourceSwitch"  >  
            <listeners>  
               <add name="console"
                  type="System.Diagnostics.ConsoleTraceListener" >  
                  <filter type="System.Diagnostics.EventTypeFilter"
                     initializeData="Error" />  
               </add>  
               <remove name="Default" />  
            </listeners>  
         </source>  
      </sources>  
      <switches>  
         <add name="sourceSwitch" value="Warning" />  
      </switches>
   </system.diagnostics>
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef693-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef693-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="ef693-129">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="ef693-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ef693-130">\<></span><span class="sxs-lookup"><span data-stu-id="ef693-130">\<source></span></span>](source-element.md)
