---
title: '&lt;performanceCounters&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <perfomanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 64afd62c6eeca7bce14e331fdc65fccfa3d02bce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltperformancecountersgt-element"></a><span data-ttu-id="73a4e-102">&lt;performanceCounters&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="73a4e-102">&lt;performanceCounters&gt; Element</span></span>
<span data-ttu-id="73a4e-103">Specifica le dimensioni della memoria globale condivisa dai contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="73a4e-103">Specifies the size of the global memory shared by performance counters.</span></span>  
  
 <span data-ttu-id="73a4e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="73a4e-104">\<configuration></span></span>  
<span data-ttu-id="73a4e-105">\<System. Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="73a4e-105">\<system.diagnostics></span></span>  
<span data-ttu-id="73a4e-106">\<performanceCounters ></span><span class="sxs-lookup"><span data-stu-id="73a4e-106">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73a4e-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="73a4e-107">Syntax</span></span>  
  
```xml  
<performanceCounters filemappingsize="524288" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73a4e-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="73a4e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="73a4e-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="73a4e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73a4e-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="73a4e-110">Attributes</span></span>  
  
|<span data-ttu-id="73a4e-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="73a4e-111">Attribute</span></span>|<span data-ttu-id="73a4e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73a4e-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="73a4e-113">FileMappingSize</span><span class="sxs-lookup"><span data-stu-id="73a4e-113">filemappingsize</span></span>|<span data-ttu-id="73a4e-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="73a4e-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="73a4e-115">Specifica le dimensioni, in byte, della memoria globale condivisa dai contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="73a4e-115">Specifies the size, in bytes, of the global memory shared by performance counters.</span></span> <span data-ttu-id="73a4e-116">Il valore predefinito è 524288.</span><span class="sxs-lookup"><span data-stu-id="73a4e-116">The default is 524288.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73a4e-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="73a4e-117">Child Elements</span></span>  
 <span data-ttu-id="73a4e-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="73a4e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73a4e-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="73a4e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="73a4e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="73a4e-120">Element</span></span>|<span data-ttu-id="73a4e-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73a4e-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="73a4e-122">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="73a4e-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="73a4e-123">Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="73a4e-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73a4e-124">Note</span><span class="sxs-lookup"><span data-stu-id="73a4e-124">Remarks</span></span>  
 <span data-ttu-id="73a4e-125">I contatori delle prestazioni di usare un file mappato alla memoria o memoria condivisa, per pubblicare i dati sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="73a4e-125">Performance counters use a memory mapped file, or shared memory, to publish performance data.</span></span>  <span data-ttu-id="73a4e-126">La dimensione della memoria condivisa determina il numero di istanze può essere utilizzato in una sola volta.</span><span class="sxs-lookup"><span data-stu-id="73a4e-126">The size of the shared memory determines how many instances can be used at once.</span></span>  <span data-ttu-id="73a4e-127">Esistono due tipi di memoria condivisa: memoria condivisa globale e della memoria condivisa separata.</span><span class="sxs-lookup"><span data-stu-id="73a4e-127">There are two types of shared memory: global shared memory and separate shared memory.</span></span>  <span data-ttu-id="73a4e-128">La memoria condivisa globale viene utilizzata da tutte le categorie di contatori delle prestazioni installate con le versioni di .NET Framework 1.0 o 1.1.</span><span class="sxs-lookup"><span data-stu-id="73a4e-128">The global shared memory is used by all performance counter categories installed with the .NET Framework versions 1.0 or 1.1.</span></span>  <span data-ttu-id="73a4e-129">Categorie di contatori delle prestazioni installate con .NET Framework versione 2.0 utilizzano memoria condivisa separata, con ogni categoria di contatori delle prestazioni disponga della propria memoria.</span><span class="sxs-lookup"><span data-stu-id="73a4e-129">Performance counter categories installed with the .NET Framework version 2.0 use separate shared memory, with each performance counter category having its own memory.</span></span>  
  
 <span data-ttu-id="73a4e-130">La dimensione della memoria condivisa globale può essere impostata solo con un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="73a4e-130">The size of global shared memory can be set only with a configuration file.</span></span>  <span data-ttu-id="73a4e-131">La dimensione predefinita è 524.288, la dimensione massima è 33.554.432 byte e la dimensione minima è corrispondono a 32.768 byte.</span><span class="sxs-lookup"><span data-stu-id="73a4e-131">The default size is 524,288 byes, the maximum size is 33,554,432 bytes, and the minimum size is 32,768 bytes.</span></span>  <span data-ttu-id="73a4e-132">Poiché la memoria condivisa globale è condiviso da tutti i processi e le categorie, l'autore del primo specifica le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="73a4e-132">Since the global shared memory is shared by all processes and categories, the first creator specifies the size.</span></span>  <span data-ttu-id="73a4e-133">Se si definiscono le dimensioni nel file di configurazione dell'applicazione, tale dimensione viene utilizzata solo se l'applicazione è la prima applicazione che fa sì che i contatori delle prestazioni per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="73a4e-133">If you define the size in your application configuration file, that size is only used if your application is the first application that causes the performance counters to execute.</span></span>  <span data-ttu-id="73a4e-134">Pertanto la posizione corretta per specificare il `filemappingsize` valore rappresenta il file Machine. config.</span><span class="sxs-lookup"><span data-stu-id="73a4e-134">Therefore the correct location to specify the `filemappingsize` value is the Machine.config file.</span></span>  <span data-ttu-id="73a4e-135">Impossibile rilasciare memoria nella memoria globale condivisa da singoli contatori delle prestazioni, dopo un certo periodo esaurimento di memoria condivisa globale se viene creato un numero elevato di istanze di contatore delle prestazioni con nomi diversi.</span><span class="sxs-lookup"><span data-stu-id="73a4e-135">Memory in the global shared memory cannot be released by individual performance counters, so eventually global shared memory is exhausted if a large number of performance counter instances with different names are created.</span></span>  
  
 <span data-ttu-id="73a4e-136">Per le dimensioni della memoria condivisa separata, il valore di DWORD FileMappingSize nel Registro di sistema chiave HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<nome categoria >*\Performance viene fatto riferimento in primo luogo, seguito dal valore specificato per la memoria condivisa globale nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="73a4e-136">For the size of separate shared memory, the DWORD FileMappingSize value in the registry key HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<category name>*\Performance is referenced first, followed by the value specified for the global shared memory in the configuration file.</span></span> <span data-ttu-id="73a4e-137">Se il valore di FileMappingSize non esiste, quindi le dimensioni di memoria condivisa separata sono impostata su un quarto (1/4) dell'impostazione globale nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="73a4e-137">If the FileMappingSize value does not exist, then the separate shared memory size is set to one fourth (1/4) the global setting in the configuration file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73a4e-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73a4e-138">See Also</span></span>  
 <xref:System.Diagnostics.PerformanceCounter>  
 <xref:System.Diagnostics.PerformanceCounterCategory>  
 <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>  
 <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
