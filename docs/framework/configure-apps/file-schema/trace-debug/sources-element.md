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
ms.openlocfilehash: a9c5c5529e349eca2ba089ed6fb71da4bd48430a
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48033246"
---
# <a name="ltsourcesgt-element"></a><span data-ttu-id="75646-102">&lt;origini&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="75646-102">&lt;sources&gt; Element</span></span>
<span data-ttu-id="75646-103">Specifica le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="75646-103">Specifies trace sources that initiate tracing messages.</span></span>  
  
 <span data-ttu-id="75646-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="75646-104">\<configuration></span></span>  
<span data-ttu-id="75646-105">\<System. Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="75646-105">\<system.diagnostics></span></span>  
<span data-ttu-id="75646-106">\<origini ></span><span class="sxs-lookup"><span data-stu-id="75646-106">\<sources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75646-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75646-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75646-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="75646-108">Attributes and Elements</span></span>  
 <span data-ttu-id="75646-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="75646-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75646-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="75646-110">Attributes</span></span>  
 <span data-ttu-id="75646-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="75646-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="75646-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="75646-112">Child Elements</span></span>  
  
|<span data-ttu-id="75646-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="75646-113">Element</span></span>|<span data-ttu-id="75646-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75646-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75646-115">\<source></span><span class="sxs-lookup"><span data-stu-id="75646-115">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|<span data-ttu-id="75646-116">Elemento obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="75646-116">Required element.</span></span><br /><br /> <span data-ttu-id="75646-117">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="75646-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="75646-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="75646-118">Parent Elements</span></span>  
  
|<span data-ttu-id="75646-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="75646-119">Element</span></span>|<span data-ttu-id="75646-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75646-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="75646-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="75646-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="75646-122">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="75646-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75646-123">Note</span><span class="sxs-lookup"><span data-stu-id="75646-123">Remarks</span></span>  
 <span data-ttu-id="75646-124">Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="75646-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75646-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="75646-125">Example</span></span>  
 <span data-ttu-id="75646-126">Nell'esempio seguente viene illustrato come utilizzare il `<sources>` elemento a cui aggiungere l'origine di traccia `mySource` e impostare il livello per l'opzione di origine denominata `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="75646-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="75646-127">Viene aggiunto un listener di traccia della console che scrive le informazioni di traccia nella console.</span><span class="sxs-lookup"><span data-stu-id="75646-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="75646-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75646-128">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.XmlWriterTraceListener>  
 [<span data-ttu-id="75646-129">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="75646-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="75646-130">\<source></span><span class="sxs-lookup"><span data-stu-id="75646-130">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)
