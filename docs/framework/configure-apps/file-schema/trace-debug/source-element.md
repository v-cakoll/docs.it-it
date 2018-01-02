---
title: '&lt;origine&gt; elemento'
ms.date: 09/29/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d6c5c65be8a540fdbba64d5a604c0963f9797e0a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltsourcegt-element"></a><span data-ttu-id="6a9e8-102">&lt;origine&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="6a9e8-102">&lt;source&gt; Element</span></span>
<span data-ttu-id="6a9e8-103">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="6a9e8-103">Specifies a trace source that initiates tracing messages.</span></span>  
  
 <span data-ttu-id="6a9e8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6a9e8-104">\<configuration></span></span>  
<span data-ttu-id="6a9e8-105">\<System. Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="6a9e8-105">\<system.diagnostics></span></span>  
<span data-ttu-id="6a9e8-106">\<origini ></span><span class="sxs-lookup"><span data-stu-id="6a9e8-106">\<sources></span></span>  
<span data-ttu-id="6a9e8-107">\<origine ></span><span class="sxs-lookup"><span data-stu-id="6a9e8-107">\<source></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a9e8-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6a9e8-108">Syntax</span></span>  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a9e8-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6a9e8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6a9e8-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6a9e8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a9e8-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="6a9e8-111">Attributes</span></span>  
  
|<span data-ttu-id="6a9e8-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="6a9e8-112">Attribute</span></span>|<span data-ttu-id="6a9e8-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a9e8-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="6a9e8-114">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6a9e8-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="6a9e8-115">Specifica il nome dell'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="6a9e8-115">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="6a9e8-116">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6a9e8-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="6a9e8-117">Specifica il nome di un'istanza di commutatore di traccia nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6a9e8-117">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="6a9e8-118">Se l'opzione non viene identificata un `<switches>` elemento, il valore specifica il livello per il commutatore.</span><span class="sxs-lookup"><span data-stu-id="6a9e8-118">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="6a9e8-119">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6a9e8-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="6a9e8-120">Specifica il tipo di opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="6a9e8-120">Specifies the type of the trace switch.</span></span> <span data-ttu-id="6a9e8-121">Se presente, il tipo deve essere un nome di classe valido e non può essere una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="6a9e8-121">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="6a9e8-122">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6a9e8-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="6a9e8-123">Specifica il valore per un attributo specifico di origine di traccia identificato dal <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> metodo per l'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="6a9e8-123">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6a9e8-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6a9e8-124">Child Elements</span></span>  
  
|<span data-ttu-id="6a9e8-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="6a9e8-125">Element</span></span>|<span data-ttu-id="6a9e8-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a9e8-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a9e8-127">\<listeners></span><span class="sxs-lookup"><span data-stu-id="6a9e8-127">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|<span data-ttu-id="6a9e8-128">Contiene i listener di raccolgano, archiviano e indirizzare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="6a9e8-128">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6a9e8-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6a9e8-129">Parent Elements</span></span>  
  
|<span data-ttu-id="6a9e8-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="6a9e8-130">Element</span></span>|<span data-ttu-id="6a9e8-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a9e8-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6a9e8-132">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6a9e8-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="6a9e8-133">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="6a9e8-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="6a9e8-134">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="6a9e8-134">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a9e8-135">Note</span><span class="sxs-lookup"><span data-stu-id="6a9e8-135">Remarks</span></span>  
 <span data-ttu-id="6a9e8-136">Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6a9e8-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a9e8-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="6a9e8-137">Example</span></span>  
 <span data-ttu-id="6a9e8-138">Nell'esempio seguente viene illustrato come utilizzare il `<source>` elemento a cui aggiungere l'origine di traccia `mySource` e impostare il livello per l'opzione di origine denominata `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="6a9e8-138">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="6a9e8-139">Viene aggiunto un listener di traccia di console che scrive le informazioni di traccia nella console.</span><span class="sxs-lookup"><span data-stu-id="6a9e8-139">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
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
  
## <a name="see-also"></a><span data-ttu-id="6a9e8-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a9e8-140">See Also</span></span>  
 [<span data-ttu-id="6a9e8-141">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="6a9e8-141">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="6a9e8-142">Opzioni di traccia</span><span class="sxs-lookup"><span data-stu-id="6a9e8-142">Trace Switches</span></span>](../../../../../docs/framework/debug-trace-profile/trace-switches.md)
