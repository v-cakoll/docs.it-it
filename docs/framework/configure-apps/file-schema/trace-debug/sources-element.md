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
ms.openlocfilehash: 0ca35d9be5e1eaf36a2c9cae99efc2736ef3403d
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699202"
---
# <a name="sources-element"></a><span data-ttu-id="91381-102">Elemento > \<sources</span><span class="sxs-lookup"><span data-stu-id="91381-102">\<sources> Element</span></span>
<span data-ttu-id="91381-103">Specifica le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="91381-103">Specifies trace sources that initiate tracing messages.</span></span>  
  
[<span data-ttu-id="91381-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="91381-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="91381-105">&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="91381-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="91381-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<sources >**</span><span class="sxs-lookup"><span data-stu-id="91381-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91381-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91381-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91381-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="91381-108">Attributes and Elements</span></span>  
 <span data-ttu-id="91381-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="91381-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91381-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="91381-110">Attributes</span></span>  
 <span data-ttu-id="91381-111">No.</span><span class="sxs-lookup"><span data-stu-id="91381-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="91381-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="91381-112">Child Elements</span></span>  
  
|<span data-ttu-id="91381-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="91381-113">Element</span></span>|<span data-ttu-id="91381-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91381-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91381-115">\<source></span><span class="sxs-lookup"><span data-stu-id="91381-115">\<source></span></span>](source-element.md)|<span data-ttu-id="91381-116">Elemento obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="91381-116">Required element.</span></span><br /><br /> <span data-ttu-id="91381-117">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="91381-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="91381-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="91381-118">Parent Elements</span></span>  
  
|<span data-ttu-id="91381-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="91381-119">Element</span></span>|<span data-ttu-id="91381-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91381-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="91381-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="91381-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="91381-122">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="91381-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91381-123">Note</span><span class="sxs-lookup"><span data-stu-id="91381-123">Remarks</span></span>  
 <span data-ttu-id="91381-124">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="91381-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91381-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="91381-125">Example</span></span>  
 <span data-ttu-id="91381-126">Nell'esempio seguente viene illustrato come utilizzare l'elemento `<sources>` per aggiungere l'origine di traccia `mySource` e per impostare il livello per l'opzione di origine denominata `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="91381-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="91381-127">Viene aggiunto un listener di traccia della console che scrive le informazioni di traccia nella console.</span><span class="sxs-lookup"><span data-stu-id="91381-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="91381-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91381-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="91381-129">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="91381-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="91381-130">\<source></span><span class="sxs-lookup"><span data-stu-id="91381-130">\<source></span></span>](source-element.md)
