---
title: <source> Elemento
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 417722ce2f3865350158413307495e3ab435d386
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153295"
---
# <a name="source-element"></a><span data-ttu-id="b0db8-102">\<source> Elemento</span><span class="sxs-lookup"><span data-stu-id="b0db8-102">\<source> Element</span></span>
<span data-ttu-id="b0db8-103">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="b0db8-103">Specifies a trace source that initiates tracing messages.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<source>**

## <a name="syntax"></a><span data-ttu-id="b0db8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0db8-104">Syntax</span></span>  
  
```xml  
<source>
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0db8-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b0db8-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b0db8-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b0db8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0db8-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="b0db8-107">Attributes</span></span>  
  
|<span data-ttu-id="b0db8-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="b0db8-108">Attribute</span></span>|<span data-ttu-id="b0db8-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0db8-109">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="b0db8-110">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b0db8-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b0db8-111">Specifica il nome dell'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="b0db8-111">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="b0db8-112">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b0db8-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b0db8-113">Specifica il nome di un'istanza dell'opzione di traccia nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b0db8-113">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="b0db8-114">Se l'opzione non è identificata in un `<switches>` elemento, il valore specifica il livello per l'opzione.</span><span class="sxs-lookup"><span data-stu-id="b0db8-114">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="b0db8-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b0db8-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b0db8-116">Specifica il tipo di opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="b0db8-116">Specifies the type of the trace switch.</span></span> <span data-ttu-id="b0db8-117">Se presente, il tipo deve essere un nome di classe valido e non può essere una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="b0db8-117">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="b0db8-118">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b0db8-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b0db8-119">Specifica il valore per un attributo specifico dell'origine di traccia identificato dal <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> metodo per l'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="b0db8-119">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0db8-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b0db8-120">Child Elements</span></span>  
  
|<span data-ttu-id="b0db8-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0db8-121">Element</span></span>|<span data-ttu-id="b0db8-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0db8-122">Description</span></span>|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-source.md)|<span data-ttu-id="b0db8-123">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi.</span><span class="sxs-lookup"><span data-stu-id="b0db8-123">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b0db8-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b0db8-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b0db8-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0db8-125">Element</span></span>|<span data-ttu-id="b0db8-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0db8-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b0db8-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b0db8-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b0db8-128">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="b0db8-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="b0db8-129">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="b0db8-129">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0db8-130">Commenti</span><span class="sxs-lookup"><span data-stu-id="b0db8-130">Remarks</span></span>  
 <span data-ttu-id="b0db8-131">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b0db8-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0db8-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="b0db8-132">Example</span></span>  
 <span data-ttu-id="b0db8-133">Nell'esempio seguente viene illustrato come utilizzare l' `<source>` elemento per aggiungere l'origine di traccia `mySource` e impostare il livello per l'opzione di origine denominata `sourceSwitch` .</span><span class="sxs-lookup"><span data-stu-id="b0db8-133">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="b0db8-134">Viene aggiunto un listener di traccia della console che scrive le informazioni di traccia nella console.</span><span class="sxs-lookup"><span data-stu-id="b0db8-134">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b0db8-135">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="b0db8-135">See also</span></span>

- [<span data-ttu-id="b0db8-136">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="b0db8-136">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b0db8-137">Opzioni di traccia</span><span class="sxs-lookup"><span data-stu-id="b0db8-137">Trace Switches</span></span>](../../../debug-trace-profile/trace-switches.md)
