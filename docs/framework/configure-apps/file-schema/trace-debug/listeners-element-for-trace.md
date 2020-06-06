---
title: Elemento <listeners> per <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: fd12be1b775d7611ef3f16d23147470313bf9866
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153373"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="348c6-102">Elemento \<listeners> per \<trace></span><span class="sxs-lookup"><span data-stu-id="348c6-102">\<listeners> Element for \<trace></span></span>
<span data-ttu-id="348c6-103">Specifica un listener che raccoglie, archivia e instrada i messaggi.</span><span class="sxs-lookup"><span data-stu-id="348c6-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="348c6-104">I listener indirizzano l'output di traccia a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="348c6-104">Listeners direct the tracing output to an appropriate target.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**

## <a name="syntax"></a><span data-ttu-id="348c6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="348c6-105">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="348c6-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="348c6-106">Attributes and Elements</span></span>  
 <span data-ttu-id="348c6-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="348c6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="348c6-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="348c6-108">Attributes</span></span>  
 <span data-ttu-id="348c6-109">No.</span><span class="sxs-lookup"><span data-stu-id="348c6-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="348c6-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="348c6-110">Child Elements</span></span>  
  
|<span data-ttu-id="348c6-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="348c6-111">Element</span></span>|<span data-ttu-id="348c6-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="348c6-112">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="348c6-113">Aggiunge un listener alla raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="348c6-113">Adds a listener to the `Listeners` collection.</span></span>|  
|[\<clear>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="348c6-114">Cancella la raccolta `Listeners` per una traccia.</span><span class="sxs-lookup"><span data-stu-id="348c6-114">Clears the `Listeners` collection for trace.</span></span>|  
|[\<remove>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="348c6-115">Rimuove un listener dalla `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="348c6-115">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="348c6-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="348c6-116">Parent Elements</span></span>  
  
|<span data-ttu-id="348c6-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="348c6-117">Element</span></span>|<span data-ttu-id="348c6-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="348c6-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="348c6-119">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="348c6-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="348c6-120">Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="348c6-120">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="348c6-121">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="348c6-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="348c6-122">Commenti</span><span class="sxs-lookup"><span data-stu-id="348c6-122">Remarks</span></span>  
 <span data-ttu-id="348c6-123">Le <xref:System.Diagnostics.Debug> <xref:System.Diagnostics.Trace> classi e condividono la stessa raccolta **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="348c6-123">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="348c6-124">Se si aggiunge un oggetto listener alla raccolta in una di queste classi, l'altra classe utilizzerà lo stesso listener.</span><span class="sxs-lookup"><span data-stu-id="348c6-124">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="348c6-125">Le classi del listener fornite con la .NET Framework derivano dalla <xref:System.Diagnostics.TraceListener> classe.</span><span class="sxs-lookup"><span data-stu-id="348c6-125">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="348c6-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="348c6-126">Configuration File</span></span>  
 <span data-ttu-id="348c6-127">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="348c6-127">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="348c6-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="348c6-128">Example</span></span>  
 <span data-ttu-id="348c6-129">Nell'esempio seguente viene illustrato come utilizzare l' **\<listeners>** elemento per aggiungere i listener `MyListener` e `MyEventListener` alla raccolta **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="348c6-129">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="348c6-130">`MyListener`Crea un file denominato `MyListener.log` e scrive l'output nel file.</span><span class="sxs-lookup"><span data-stu-id="348c6-130">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="348c6-131">`MyEventListener`Crea una voce nel log eventi.</span><span class="sxs-lookup"><span data-stu-id="348c6-131">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"
          type="System.Diagnostics.TextWriterTraceListener,
            system, version=1.0.3300.0, Culture=neutral,
            PublicKeyToken=b77a5c561934e089"
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,
            system, version=1.0.3300.0, Culture=neutral,
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="348c6-132">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="348c6-132">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="348c6-133">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="348c6-133">Trace and Debug Settings Schema</span></span>](index.md)
