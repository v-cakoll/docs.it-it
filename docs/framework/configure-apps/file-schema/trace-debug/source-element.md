---
title: <source> Elemento
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 8860f5d3ed7ee0c04d1e8afd7614f3f73b470808
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673706"
---
# <a name="source-element"></a><span data-ttu-id="64647-102">\<origine > elemento</span><span class="sxs-lookup"><span data-stu-id="64647-102">\<source> Element</span></span>
<span data-ttu-id="64647-103">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="64647-103">Specifies a trace source that initiates tracing messages.</span></span>  
  
 <span data-ttu-id="64647-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="64647-104">\<configuration></span></span>  
<span data-ttu-id="64647-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="64647-105">\<system.diagnostics></span></span>  
<span data-ttu-id="64647-106">\<sources></span><span class="sxs-lookup"><span data-stu-id="64647-106">\<sources></span></span>  
<span data-ttu-id="64647-107">\<origine ></span><span class="sxs-lookup"><span data-stu-id="64647-107">\<source></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64647-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64647-108">Syntax</span></span>  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64647-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="64647-109">Attributes and Elements</span></span>  
 <span data-ttu-id="64647-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="64647-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64647-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="64647-111">Attributes</span></span>  
  
|<span data-ttu-id="64647-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="64647-112">Attribute</span></span>|<span data-ttu-id="64647-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64647-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="64647-114">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="64647-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="64647-115">Specifica il nome dell'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="64647-115">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="64647-116">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="64647-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="64647-117">Specifica il nome di un'istanza del commutatore traccia nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="64647-117">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="64647-118">Se l'opzione non viene identificata una `<switches>` elemento, il valore specifica il livello per il commutatore.</span><span class="sxs-lookup"><span data-stu-id="64647-118">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="64647-119">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="64647-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="64647-120">Specifica il tipo di opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="64647-120">Specifies the type of the trace switch.</span></span> <span data-ttu-id="64647-121">Se presente, il tipo deve essere un nome di classe valido e non può essere una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="64647-121">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="64647-122">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="64647-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="64647-123">Specifica il valore per un attributo specifico dell'origine di traccia identificato dalla <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> metodo per l'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="64647-123">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64647-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="64647-124">Child Elements</span></span>  
  
|<span data-ttu-id="64647-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="64647-125">Element</span></span>|<span data-ttu-id="64647-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64647-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64647-127">\<listeners></span><span class="sxs-lookup"><span data-stu-id="64647-127">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|<span data-ttu-id="64647-128">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="64647-128">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="64647-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="64647-129">Parent Elements</span></span>  
  
|<span data-ttu-id="64647-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="64647-130">Element</span></span>|<span data-ttu-id="64647-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64647-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="64647-132">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="64647-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="64647-133">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="64647-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="64647-134">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="64647-134">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64647-135">Note</span><span class="sxs-lookup"><span data-stu-id="64647-135">Remarks</span></span>  
 <span data-ttu-id="64647-136">Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="64647-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64647-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="64647-137">Example</span></span>  
 <span data-ttu-id="64647-138">Nell'esempio seguente viene illustrato come utilizzare il `<source>` elemento a cui aggiungere l'origine di traccia `mySource` e impostare il livello per l'opzione di origine denominata `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="64647-138">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="64647-139">Viene aggiunto un listener di traccia della console che scrive le informazioni di traccia nella console.</span><span class="sxs-lookup"><span data-stu-id="64647-139">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="64647-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64647-140">See also</span></span>

- [<span data-ttu-id="64647-141">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="64647-141">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="64647-142">Opzioni di traccia</span><span class="sxs-lookup"><span data-stu-id="64647-142">Trace Switches</span></span>](../../../../../docs/framework/debug-trace-profile/trace-switches.md)
