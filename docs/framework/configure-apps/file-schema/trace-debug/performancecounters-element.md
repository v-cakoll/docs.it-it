---
title: '&lt;performanceCounters&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <perfomanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
ms.openlocfilehash: 5afa38a98aa6ea0901849b01d6b1030d079f218e
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083977"
---
# <a name="ltperformancecountersgt-element"></a><span data-ttu-id="d9aa2-102">&lt;performanceCounters&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="d9aa2-102">&lt;performanceCounters&gt; Element</span></span>
<span data-ttu-id="d9aa2-103">Specifica le dimensioni della memoria globale condivisa dai contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="d9aa2-103">Specifies the size of the global memory shared by performance counters.</span></span>  
  
 <span data-ttu-id="d9aa2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d9aa2-104">\<configuration></span></span>  
<span data-ttu-id="d9aa2-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="d9aa2-105">\<system.diagnostics></span></span>  
<span data-ttu-id="d9aa2-106">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="d9aa2-106">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9aa2-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9aa2-107">Syntax</span></span>  
  
```xml  
<performanceCounters filemappingsize="524288" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9aa2-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d9aa2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d9aa2-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d9aa2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9aa2-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="d9aa2-110">Attributes</span></span>  
  
|<span data-ttu-id="d9aa2-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="d9aa2-111">Attribute</span></span>|<span data-ttu-id="d9aa2-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d9aa2-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d9aa2-113">filemappingsize</span><span class="sxs-lookup"><span data-stu-id="d9aa2-113">filemappingsize</span></span>|<span data-ttu-id="d9aa2-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d9aa2-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="d9aa2-115">Specifica le dimensioni, in byte, della memoria globale condivisa dai contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="d9aa2-115">Specifies the size, in bytes, of the global memory shared by performance counters.</span></span> <span data-ttu-id="d9aa2-116">Il valore predefinito è 524288.</span><span class="sxs-lookup"><span data-stu-id="d9aa2-116">The default is 524288.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d9aa2-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d9aa2-117">Child Elements</span></span>  
 <span data-ttu-id="d9aa2-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d9aa2-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d9aa2-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d9aa2-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d9aa2-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="d9aa2-120">Element</span></span>|<span data-ttu-id="d9aa2-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d9aa2-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="d9aa2-122">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d9aa2-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="d9aa2-123">Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d9aa2-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9aa2-124">Note</span><span class="sxs-lookup"><span data-stu-id="d9aa2-124">Remarks</span></span>  
 <span data-ttu-id="d9aa2-125">I contatori delle prestazioni utilizzano un file mappato alla memoria o della memoria condivisa, per pubblicare i dati sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="d9aa2-125">Performance counters use a memory mapped file, or shared memory, to publish performance data.</span></span>  <span data-ttu-id="d9aa2-126">Le dimensioni della memoria condivisa determinano il numero di istanze può essere utilizzato in una sola volta.</span><span class="sxs-lookup"><span data-stu-id="d9aa2-126">The size of the shared memory determines how many instances can be used at once.</span></span>  <span data-ttu-id="d9aa2-127">Esistono due tipi di memoria condivisa: memoria condivisa globale e della memoria condivisa separata.</span><span class="sxs-lookup"><span data-stu-id="d9aa2-127">There are two types of shared memory: global shared memory and separate shared memory.</span></span>  <span data-ttu-id="d9aa2-128">La memoria condivisa globale viene usata da tutte le categorie di contatori delle prestazioni installate con le versioni di .NET Framework 1.0 o 1.1.</span><span class="sxs-lookup"><span data-stu-id="d9aa2-128">The global shared memory is used by all performance counter categories installed with the .NET Framework versions 1.0 or 1.1.</span></span>  <span data-ttu-id="d9aa2-129">Categorie di contatori delle prestazioni installate con .NET Framework versione 2.0 usano memoria condivisa separata, con ogni categoria di contatori delle prestazioni disponga della propria memoria.</span><span class="sxs-lookup"><span data-stu-id="d9aa2-129">Performance counter categories installed with the .NET Framework version 2.0 use separate shared memory, with each performance counter category having its own memory.</span></span>  
  
 <span data-ttu-id="d9aa2-130">Le dimensioni della memoria condivisa globale possono essere impostate solo con un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d9aa2-130">The size of global shared memory can be set only with a configuration file.</span></span>  <span data-ttu-id="d9aa2-131">Il valore predefinito è 524.288, la dimensione massima è 33.554.432 byte e la dimensione minima è 32.768 byte.</span><span class="sxs-lookup"><span data-stu-id="d9aa2-131">The default size is 524,288 byes, the maximum size is 33,554,432 bytes, and the minimum size is 32,768 bytes.</span></span>  <span data-ttu-id="d9aa2-132">Poiché la memoria condivisa globale è condiviso da tutti i processi e le categorie, l'autore prima specifica le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d9aa2-132">Since the global shared memory is shared by all processes and categories, the first creator specifies the size.</span></span>  <span data-ttu-id="d9aa2-133">Se si definiscono le dimensioni nel file di configurazione dell'applicazione, che la dimensione viene usata solo se l'applicazione è la prima applicazione che fa sì che i contatori delle prestazioni per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d9aa2-133">If you define the size in your application configuration file, that size is only used if your application is the first application that causes the performance counters to execute.</span></span>  <span data-ttu-id="d9aa2-134">Pertanto la posizione corretta per specificare il `filemappingsize` valore è il file Machine. config.</span><span class="sxs-lookup"><span data-stu-id="d9aa2-134">Therefore the correct location to specify the `filemappingsize` value is the Machine.config file.</span></span>  <span data-ttu-id="d9aa2-135">Impossibile rilasciare memoria nella memoria globale condivisa dai contatori delle prestazioni singoli, pertanto, alla fine viene esaurita la memoria globale condivisa se viene creato un numero elevato di istanze del contatore delle prestazioni con nomi diversi.</span><span class="sxs-lookup"><span data-stu-id="d9aa2-135">Memory in the global shared memory cannot be released by individual performance counters, so eventually global shared memory is exhausted if a large number of performance counter instances with different names are created.</span></span>  
  
 <span data-ttu-id="d9aa2-136">Per le dimensioni della memoria condivisa separata, il valore della chiave DWORD FileMappingSize nel Registro di sistema chiave HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<il nome di categoria >* \Performance viene fatto riferimento in primo luogo, seguito dal valore specificato per la memoria condivisa globale nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d9aa2-136">For the size of separate shared memory, the DWORD FileMappingSize value in the registry key HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<category name>* \Performance is referenced first, followed by the value specified for the global shared memory in the configuration file.</span></span> <span data-ttu-id="d9aa2-137">Se il valore FileMappingSize non esiste, quindi le dimensioni di memoria condivisa separata sono impostata su un quarto (1 e 4) l'impostazione globale nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d9aa2-137">If the FileMappingSize value does not exist, then the separate shared memory size is set to one fourth (1/4) the global setting in the configuration file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9aa2-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9aa2-138">See also</span></span>
- <xref:System.Diagnostics.PerformanceCounter>
- <xref:System.Diagnostics.PerformanceCounterCategory>
- <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>
- <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
