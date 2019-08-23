---
title: <source> Elemento
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 55120e292ac2a2c822c5510563d1aa167ca921e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920459"
---
# <a name="source-element"></a><span data-ttu-id="7dd69-102">\<Elemento > di origine</span><span class="sxs-lookup"><span data-stu-id="7dd69-102">\<source> Element</span></span>
<span data-ttu-id="7dd69-103">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="7dd69-103">Specifies a trace source that initiates tracing messages.</span></span>  
  
 <span data-ttu-id="7dd69-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7dd69-104">\<configuration></span></span>  
<span data-ttu-id="7dd69-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="7dd69-105">\<system.diagnostics></span></span>  
<span data-ttu-id="7dd69-106">\<origini ></span><span class="sxs-lookup"><span data-stu-id="7dd69-106">\<sources></span></span>  
<span data-ttu-id="7dd69-107">\<> di origine</span><span class="sxs-lookup"><span data-stu-id="7dd69-107">\<source></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dd69-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7dd69-108">Syntax</span></span>  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7dd69-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7dd69-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7dd69-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7dd69-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7dd69-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="7dd69-111">Attributes</span></span>  
  
|<span data-ttu-id="7dd69-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="7dd69-112">Attribute</span></span>|<span data-ttu-id="7dd69-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7dd69-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="7dd69-114">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7dd69-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="7dd69-115">Specifica il nome dell'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="7dd69-115">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="7dd69-116">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7dd69-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="7dd69-117">Specifica il nome di un'istanza dell'opzione di traccia nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7dd69-117">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="7dd69-118">Se l'opzione non è identificata in `<switches>` un elemento, il valore specifica il livello per l'opzione.</span><span class="sxs-lookup"><span data-stu-id="7dd69-118">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="7dd69-119">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7dd69-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="7dd69-120">Specifica il tipo di opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="7dd69-120">Specifies the type of the trace switch.</span></span> <span data-ttu-id="7dd69-121">Se presente, il tipo deve essere un nome di classe valido e non può essere una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="7dd69-121">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="7dd69-122">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7dd69-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="7dd69-123">Specifica il valore per un attributo specifico dell'origine di traccia identificato dal <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> metodo per l'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="7dd69-123">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7dd69-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7dd69-124">Child Elements</span></span>  
  
|<span data-ttu-id="7dd69-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="7dd69-125">Element</span></span>|<span data-ttu-id="7dd69-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7dd69-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7dd69-127">\<listeners></span><span class="sxs-lookup"><span data-stu-id="7dd69-127">\<listeners></span></span>](listeners-element-for-source.md)|<span data-ttu-id="7dd69-128">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="7dd69-128">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7dd69-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7dd69-129">Parent Elements</span></span>  
  
|<span data-ttu-id="7dd69-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="7dd69-130">Element</span></span>|<span data-ttu-id="7dd69-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7dd69-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7dd69-132">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7dd69-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="7dd69-133">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="7dd69-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="7dd69-134">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="7dd69-134">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7dd69-135">Note</span><span class="sxs-lookup"><span data-stu-id="7dd69-135">Remarks</span></span>  
 <span data-ttu-id="7dd69-136">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7dd69-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dd69-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="7dd69-137">Example</span></span>  
 <span data-ttu-id="7dd69-138">Nell'esempio seguente viene illustrato come utilizzare l' `<source>` elemento per aggiungere l'origine `mySource` di traccia e impostare il livello per l'opzione di origine `sourceSwitch`denominata.</span><span class="sxs-lookup"><span data-stu-id="7dd69-138">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="7dd69-139">Viene aggiunto un listener di traccia della console che scrive le informazioni di traccia nella console.</span><span class="sxs-lookup"><span data-stu-id="7dd69-139">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7dd69-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7dd69-140">See also</span></span>

- [<span data-ttu-id="7dd69-141">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="7dd69-141">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7dd69-142">Opzioni di traccia</span><span class="sxs-lookup"><span data-stu-id="7dd69-142">Trace Switches</span></span>](../../../debug-trace-profile/trace-switches.md)
