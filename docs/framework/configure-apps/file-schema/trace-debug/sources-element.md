---
title: '&lt;origini&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 73fe0fb13c191843516a2218c708851abc1851b0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltsourcesgt-element"></a><span data-ttu-id="729ce-102">&lt;origini&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="729ce-102">&lt;sources&gt; Element</span></span>
<span data-ttu-id="729ce-103">Specifica le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="729ce-103">Specifies trace sources that initiate tracing messages.</span></span>  
  
 <span data-ttu-id="729ce-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="729ce-104">\<configuration></span></span>  
<span data-ttu-id="729ce-105">\<System. Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="729ce-105">\<system.diagnostics></span></span>  
<span data-ttu-id="729ce-106">\<origini ></span><span class="sxs-lookup"><span data-stu-id="729ce-106">\<sources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="729ce-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="729ce-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="729ce-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="729ce-108">Attributes and Elements</span></span>  
 <span data-ttu-id="729ce-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="729ce-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="729ce-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="729ce-110">Attributes</span></span>  
 <span data-ttu-id="729ce-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="729ce-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="729ce-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="729ce-112">Child Elements</span></span>  
  
|<span data-ttu-id="729ce-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="729ce-113">Element</span></span>|<span data-ttu-id="729ce-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="729ce-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="729ce-115">\<source></span><span class="sxs-lookup"><span data-stu-id="729ce-115">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|<span data-ttu-id="729ce-116">Elemento obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="729ce-116">Required element.</span></span><br /><br /> <span data-ttu-id="729ce-117">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="729ce-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="729ce-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="729ce-118">Parent Elements</span></span>  
  
|<span data-ttu-id="729ce-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="729ce-119">Element</span></span>|<span data-ttu-id="729ce-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="729ce-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="729ce-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="729ce-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="729ce-122">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="729ce-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="729ce-123">Note</span><span class="sxs-lookup"><span data-stu-id="729ce-123">Remarks</span></span>  
 <span data-ttu-id="729ce-124">Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="729ce-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="729ce-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="729ce-125">Example</span></span>  
 <span data-ttu-id="729ce-126">Nell'esempio seguente viene illustrato come utilizzare il `<sources>` elemento a cui aggiungere l'origine di traccia `mySource` e impostare il livello per l'opzione di origine denominata `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="729ce-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="729ce-127">Viene aggiunto un listener di traccia di console che scrive le informazioni di traccia nella console.</span><span class="sxs-lookup"><span data-stu-id="729ce-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="729ce-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="729ce-128">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.XmlWriterTraceListener>  
 [<span data-ttu-id="729ce-129">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="729ce-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="729ce-130">\<source></span><span class="sxs-lookup"><span data-stu-id="729ce-130">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)
