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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "71697149"
---
# <a name="performancecounters-element"></a><span data-ttu-id="e7022-102">\<performanceCounters> Elemento</span><span class="sxs-lookup"><span data-stu-id="e7022-102">\<performanceCounters> Element</span></span>

<span data-ttu-id="e7022-103">Specifica le dimensioni della memoria globale condivisa dai contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e7022-103">Specifies the size of the global memory shared by performance counters.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**  

## <a name="syntax"></a><span data-ttu-id="e7022-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7022-104">Syntax</span></span>

```xml
<performanceCounters filemappingsize="524288" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e7022-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e7022-105">Attributes and Elements</span></span>

<span data-ttu-id="e7022-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e7022-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e7022-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="e7022-107">Attributes</span></span>

|<span data-ttu-id="e7022-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="e7022-108">Attribute</span></span>|<span data-ttu-id="e7022-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7022-109">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="e7022-110">FileMappingSize</span><span class="sxs-lookup"><span data-stu-id="e7022-110">filemappingsize</span></span>|<span data-ttu-id="e7022-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e7022-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="e7022-112">Specifica la dimensione, in byte, della memoria globale condivisa dai contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e7022-112">Specifies the size, in bytes, of the global memory shared by performance counters.</span></span> <span data-ttu-id="e7022-113">Il valore predefinito è 524288.</span><span class="sxs-lookup"><span data-stu-id="e7022-113">The default is 524288.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="e7022-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e7022-114">Child Elements</span></span>

<span data-ttu-id="e7022-115">No.</span><span class="sxs-lookup"><span data-stu-id="e7022-115">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e7022-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e7022-116">Parent Elements</span></span>

|<span data-ttu-id="e7022-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="e7022-117">Element</span></span>|<span data-ttu-id="e7022-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7022-118">Description</span></span>|
|-------------|-----------------|
|`Configuration`|<span data-ttu-id="e7022-119">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e7022-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`system.diagnostics`|<span data-ttu-id="e7022-120">Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e7022-120">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e7022-121">Commenti</span><span class="sxs-lookup"><span data-stu-id="e7022-121">Remarks</span></span>

<span data-ttu-id="e7022-122">I contatori delle prestazioni utilizzano un file mappato alla memoria o una memoria condivisa per pubblicare i dati sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e7022-122">Performance counters use a memory mapped file, or shared memory, to publish performance data.</span></span>  <span data-ttu-id="e7022-123">Le dimensioni della memoria condivisa determinano il numero di istanze che possono essere usate contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="e7022-123">The size of the shared memory determines how many instances can be used at once.</span></span>  <span data-ttu-id="e7022-124">Esistono due tipi di memoria condivisa: memoria condivisa globale e memoria condivisa separata.</span><span class="sxs-lookup"><span data-stu-id="e7022-124">There are two types of shared memory: global shared memory and separate shared memory.</span></span>  <span data-ttu-id="e7022-125">La memoria condivisa globale viene utilizzata da tutte le categorie di contatori delle prestazioni installate con le versioni .NET Framework 1,0 o 1,1.</span><span class="sxs-lookup"><span data-stu-id="e7022-125">The global shared memory is used by all performance counter categories installed with the .NET Framework versions 1.0 or 1.1.</span></span>  <span data-ttu-id="e7022-126">Le categorie di contatori delle prestazioni installate con la versione di .NET Framework 2,0 usano una memoria condivisa separata, con ogni categoria di contatori delle prestazioni con memoria propria.</span><span class="sxs-lookup"><span data-stu-id="e7022-126">Performance counter categories installed with the .NET Framework version 2.0 use separate shared memory, with each performance counter category having its own memory.</span></span>

<span data-ttu-id="e7022-127">Le dimensioni della memoria condivisa globale possono essere impostate solo con un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e7022-127">The size of global shared memory can be set only with a configuration file.</span></span>  <span data-ttu-id="e7022-128">Le dimensioni predefinite sono pari a 524.288 addii, le cui dimensioni massime sono di 33.554.432 byte e la dimensione minima è 32.768 byte.</span><span class="sxs-lookup"><span data-stu-id="e7022-128">The default size is 524,288 byes, the maximum size is 33,554,432 bytes, and the minimum size is 32,768 bytes.</span></span>  <span data-ttu-id="e7022-129">Poiché la memoria condivisa globale è condivisa da tutti i processi e le categorie, il primo autore specifica le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e7022-129">Since the global shared memory is shared by all processes and categories, the first creator specifies the size.</span></span>  <span data-ttu-id="e7022-130">Se si definiscono le dimensioni nel file di configurazione dell'applicazione, tale dimensione viene utilizzata solo se l'applicazione è la prima applicazione che provoca l'esecuzione dei contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e7022-130">If you define the size in your application configuration file, that size is only used if your application is the first application that causes the performance counters to execute.</span></span>  <span data-ttu-id="e7022-131">Il percorso corretto per specificare il `filemappingsize` valore è quindi il file Machine. config.</span><span class="sxs-lookup"><span data-stu-id="e7022-131">Therefore the correct location to specify the `filemappingsize` value is the Machine.config file.</span></span>  <span data-ttu-id="e7022-132">La memoria nella memoria condivisa globale non può essere rilasciata dai singoli contatori delle prestazioni, quindi la memoria condivisa globale viene esaurita se viene creato un numero elevato di istanze del contatore delle prestazioni con nomi diversi.</span><span class="sxs-lookup"><span data-stu-id="e7022-132">Memory in the global shared memory cannot be released by individual performance counters, so eventually global shared memory is exhausted if a large number of performance counter instances with different names are created.</span></span>

<span data-ttu-id="e7022-133">Per la dimensione della memoria condivisa separata, viene fatto riferimento prima del valore DWORD FileMappingSize nella chiave del registro di sistema HKEY_LOCAL_MACHINE \SYSTEM\CurrentControlSet\Services \\ *\<category name>* \Performance, seguito dal valore specificato per la memoria condivisa globale nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e7022-133">For the size of separate shared memory, the DWORD FileMappingSize value in the registry key HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<category name>* \Performance is referenced first, followed by the value specified for the global shared memory in the configuration file.</span></span> <span data-ttu-id="e7022-134">Se il valore FileMappingSize non esiste, le dimensioni separate della memoria condivisa vengono impostate su un quarto (1/4) nell'impostazione globale nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e7022-134">If the FileMappingSize value does not exist, then the separate shared memory size is set to one fourth (1/4) the global setting in the configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7022-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7022-135">See also</span></span>

- <xref:System.Diagnostics.PerformanceCounter>
- <xref:System.Diagnostics.PerformanceCounterCategory>
- <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>
- <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
