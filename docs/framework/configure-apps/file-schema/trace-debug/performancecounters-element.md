---
title: <performanceCounters> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <performanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
ms.openlocfilehash: f52fdb2d5b0b7911de63f96663e70735d2f2496c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697149"
---
# <a name="performancecounters-element"></a><span data-ttu-id="a046c-102">Elemento > \<performanceCounters</span><span class="sxs-lookup"><span data-stu-id="a046c-102">\<performanceCounters> Element</span></span>

<span data-ttu-id="a046c-103">Specifica le dimensioni della memoria globale condivisa dai contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="a046c-103">Specifies the size of the global memory shared by performance counters.</span></span>

[<span data-ttu-id="a046c-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="a046c-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="a046c-105">&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="a046c-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="a046c-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<performanceCounters >**</span><span class="sxs-lookup"><span data-stu-id="a046c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="a046c-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a046c-107">Syntax</span></span>

```xml
<performanceCounters filemappingsize="524288" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a046c-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a046c-108">Attributes and Elements</span></span>

<span data-ttu-id="a046c-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a046c-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a046c-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="a046c-110">Attributes</span></span>

|<span data-ttu-id="a046c-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="a046c-111">Attribute</span></span>|<span data-ttu-id="a046c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a046c-112">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="a046c-113">FileMappingSize</span><span class="sxs-lookup"><span data-stu-id="a046c-113">filemappingsize</span></span>|<span data-ttu-id="a046c-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a046c-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="a046c-115">Specifica la dimensione, in byte, della memoria globale condivisa dai contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="a046c-115">Specifies the size, in bytes, of the global memory shared by performance counters.</span></span> <span data-ttu-id="a046c-116">Il valore predefinito è 524288.</span><span class="sxs-lookup"><span data-stu-id="a046c-116">The default is 524288.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a046c-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a046c-117">Child Elements</span></span>

<span data-ttu-id="a046c-118">No.</span><span class="sxs-lookup"><span data-stu-id="a046c-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a046c-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a046c-119">Parent Elements</span></span>

|<span data-ttu-id="a046c-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="a046c-120">Element</span></span>|<span data-ttu-id="a046c-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a046c-121">Description</span></span>|
|-------------|-----------------|
|`Configuration`|<span data-ttu-id="a046c-122">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a046c-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`system.diagnostics`|<span data-ttu-id="a046c-123">Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a046c-123">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a046c-124">Note</span><span class="sxs-lookup"><span data-stu-id="a046c-124">Remarks</span></span>

<span data-ttu-id="a046c-125">I contatori delle prestazioni utilizzano un file mappato alla memoria o una memoria condivisa per pubblicare i dati sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="a046c-125">Performance counters use a memory mapped file, or shared memory, to publish performance data.</span></span>  <span data-ttu-id="a046c-126">Le dimensioni della memoria condivisa determinano il numero di istanze che possono essere usate contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="a046c-126">The size of the shared memory determines how many instances can be used at once.</span></span>  <span data-ttu-id="a046c-127">Esistono due tipi di memoria condivisa: memoria condivisa globale e memoria condivisa separata.</span><span class="sxs-lookup"><span data-stu-id="a046c-127">There are two types of shared memory: global shared memory and separate shared memory.</span></span>  <span data-ttu-id="a046c-128">La memoria condivisa globale viene utilizzata da tutte le categorie di contatori delle prestazioni installate con le versioni .NET Framework 1,0 o 1,1.</span><span class="sxs-lookup"><span data-stu-id="a046c-128">The global shared memory is used by all performance counter categories installed with the .NET Framework versions 1.0 or 1.1.</span></span>  <span data-ttu-id="a046c-129">Le categorie di contatori delle prestazioni installate con la versione di .NET Framework 2,0 usano una memoria condivisa separata, con ogni categoria di contatori delle prestazioni con memoria propria.</span><span class="sxs-lookup"><span data-stu-id="a046c-129">Performance counter categories installed with the .NET Framework version 2.0 use separate shared memory, with each performance counter category having its own memory.</span></span>

<span data-ttu-id="a046c-130">Le dimensioni della memoria condivisa globale possono essere impostate solo con un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a046c-130">The size of global shared memory can be set only with a configuration file.</span></span>  <span data-ttu-id="a046c-131">Le dimensioni predefinite sono pari a 524.288 addii, le cui dimensioni massime sono di 33.554.432 byte e la dimensione minima è 32.768 byte.</span><span class="sxs-lookup"><span data-stu-id="a046c-131">The default size is 524,288 byes, the maximum size is 33,554,432 bytes, and the minimum size is 32,768 bytes.</span></span>  <span data-ttu-id="a046c-132">Poiché la memoria condivisa globale è condivisa da tutti i processi e le categorie, il primo autore specifica le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="a046c-132">Since the global shared memory is shared by all processes and categories, the first creator specifies the size.</span></span>  <span data-ttu-id="a046c-133">Se si definiscono le dimensioni nel file di configurazione dell'applicazione, tale dimensione viene utilizzata solo se l'applicazione è la prima applicazione che provoca l'esecuzione dei contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="a046c-133">If you define the size in your application configuration file, that size is only used if your application is the first application that causes the performance counters to execute.</span></span>  <span data-ttu-id="a046c-134">Il percorso corretto per specificare il valore `filemappingsize` è quindi il file Machine. config.</span><span class="sxs-lookup"><span data-stu-id="a046c-134">Therefore the correct location to specify the `filemappingsize` value is the Machine.config file.</span></span>  <span data-ttu-id="a046c-135">La memoria nella memoria condivisa globale non può essere rilasciata dai singoli contatori delle prestazioni, quindi la memoria condivisa globale viene esaurita se viene creato un numero elevato di istanze del contatore delle prestazioni con nomi diversi.</span><span class="sxs-lookup"><span data-stu-id="a046c-135">Memory in the global shared memory cannot be released by individual performance counters, so eventually global shared memory is exhausted if a large number of performance counter instances with different names are created.</span></span>

<span data-ttu-id="a046c-136">Per la dimensione della memoria condivisa separata, viene fatto riferimento prima del valore DWORD FileMappingSize nella chiave del registro di sistema HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services @ no__t-0 *\<category nome >* \Performance, seguito dal valore specificata per la memoria condivisa globale nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a046c-136">For the size of separate shared memory, the DWORD FileMappingSize value in the registry key HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<category name>* \Performance is referenced first, followed by the value specified for the global shared memory in the configuration file.</span></span> <span data-ttu-id="a046c-137">Se il valore FileMappingSize non esiste, le dimensioni separate della memoria condivisa vengono impostate su un quarto (1/4) nell'impostazione globale nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a046c-137">If the FileMappingSize value does not exist, then the separate shared memory size is set to one fourth (1/4) the global setting in the configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="a046c-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a046c-138">See also</span></span>

- <xref:System.Diagnostics.PerformanceCounter>
- <xref:System.Diagnostics.PerformanceCounterCategory>
- <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>
- <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
