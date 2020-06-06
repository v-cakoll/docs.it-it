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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153269"
---
# <a name="sources-element"></a><span data-ttu-id="f7b12-102">\<sources> Elemento</span><span class="sxs-lookup"><span data-stu-id="f7b12-102">\<sources> Element</span></span>
<span data-ttu-id="f7b12-103">Specifica le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="f7b12-103">Specifies trace sources that initiate tracing messages.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<sources>**

## <a name="syntax"></a><span data-ttu-id="f7b12-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7b12-104">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7b12-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f7b12-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f7b12-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f7b12-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7b12-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="f7b12-107">Attributes</span></span>  
 <span data-ttu-id="f7b12-108">No.</span><span class="sxs-lookup"><span data-stu-id="f7b12-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f7b12-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f7b12-109">Child Elements</span></span>  
  
|<span data-ttu-id="f7b12-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="f7b12-110">Element</span></span>|<span data-ttu-id="f7b12-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7b12-111">Description</span></span>|  
|-------------|-----------------|  
|[\<source>](source-element.md)|<span data-ttu-id="f7b12-112">Elemento obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f7b12-112">Required element.</span></span><br /><br /> <span data-ttu-id="f7b12-113">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="f7b12-113">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f7b12-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f7b12-114">Parent Elements</span></span>  
  
|<span data-ttu-id="f7b12-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="f7b12-115">Element</span></span>|<span data-ttu-id="f7b12-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7b12-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f7b12-117">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f7b12-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="f7b12-118">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="f7b12-118">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7b12-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="f7b12-119">Remarks</span></span>  
 <span data-ttu-id="f7b12-120">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f7b12-120">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7b12-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="f7b12-121">Example</span></span>  
 <span data-ttu-id="f7b12-122">Nell'esempio seguente viene illustrato come utilizzare l' `<sources>` elemento per aggiungere l'origine di traccia `mySource` e impostare il livello per l'opzione di origine denominata `sourceSwitch` .</span><span class="sxs-lookup"><span data-stu-id="f7b12-122">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="f7b12-123">Viene aggiunto un listener di traccia della console che scrive le informazioni di traccia nella console.</span><span class="sxs-lookup"><span data-stu-id="f7b12-123">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f7b12-124">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f7b12-124">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="f7b12-125">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="f7b12-125">Trace and Debug Settings Schema</span></span>](index.md)
- [\<source>](source-element.md)
