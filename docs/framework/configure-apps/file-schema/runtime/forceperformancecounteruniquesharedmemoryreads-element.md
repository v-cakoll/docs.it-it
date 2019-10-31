---
title: <forcePerformanceCounterUniqueSharedMemoryReads> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: efa6dce1035f7d2cf63b74c6a03d911b5dede722
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116957"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="e8139-102">\<elemento > forcePerformanceCounterUniqueSharedMemoryReads</span><span class="sxs-lookup"><span data-stu-id="e8139-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>
<span data-ttu-id="e8139-103">Specifica se PerfCounter.dll usa l'impostazione del Registro di sistema CategoryOptions in un'applicazione di .NET Framework versione 1.1 per determinare se caricare i dati del contatore delle prestazioni dalla memoria condivisa specifica della categoria o dalla memoria globale.</span><span class="sxs-lookup"><span data-stu-id="e8139-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
<span data-ttu-id="e8139-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e8139-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e8139-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="e8139-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="e8139-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<forcePerformanceCounterUniqueSharedMemoryReads >**</span><span class="sxs-lookup"><span data-stu-id="e8139-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8139-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8139-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8139-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e8139-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e8139-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e8139-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8139-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="e8139-110">Attributes</span></span>  
  
|<span data-ttu-id="e8139-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="e8139-111">Attribute</span></span>|<span data-ttu-id="e8139-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8139-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="e8139-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e8139-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="e8139-114">Indica se PerfCounter. dll usa l'impostazione del registro di sistema CategoryOptions per determinare se caricare i dati dei contatori delle prestazioni dalla memoria condivisa specifica della categoria o dalla memoria globale.</span><span class="sxs-lookup"><span data-stu-id="e8139-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="e8139-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="e8139-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="e8139-116">Value</span><span class="sxs-lookup"><span data-stu-id="e8139-116">Value</span></span>|<span data-ttu-id="e8139-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8139-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="e8139-118">PerfCounter. dll non usa l'impostazione predefinita del registro di sistema CategoryOptions.</span><span class="sxs-lookup"><span data-stu-id="e8139-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="e8139-119">PerfCounter. dll usa l'impostazione del registro di sistema CategoryOptions.</span><span class="sxs-lookup"><span data-stu-id="e8139-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8139-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e8139-120">Child Elements</span></span>  
 <span data-ttu-id="e8139-121">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="e8139-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8139-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e8139-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e8139-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8139-123">Element</span></span>|<span data-ttu-id="e8139-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8139-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e8139-125">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e8139-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e8139-126">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="e8139-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8139-127">Note</span><span class="sxs-lookup"><span data-stu-id="e8139-127">Remarks</span></span>  
 <span data-ttu-id="e8139-128">Nelle versioni del .NET Framework prima del .NET Framework 4, la versione di PerfCounter. dll che è stata caricata corrisponde al runtime caricato nel processo.</span><span class="sxs-lookup"><span data-stu-id="e8139-128">In versions of the .NET Framework before the .NET Framework 4, the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="e8139-129">Se un computer ha installato sia la versione di .NET Framework 1,1 che la .NET Framework 2,0, un'applicazione .NET Framework 1,1 caricherà la versione .NET Framework 1,1 di PerfCounter. dll.</span><span class="sxs-lookup"><span data-stu-id="e8139-129">If a computer had both the .NET Framework version 1.1 and the .NET Framework 2.0 installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="e8139-130">A partire da .NET Framework 4, viene caricata la versione installata più recente di PerfCounter. dll.</span><span class="sxs-lookup"><span data-stu-id="e8139-130">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="e8139-131">Ciò significa che un'applicazione .NET Framework 1,1 caricherà la versione .NET Framework 4 di PerfCounter. dll se il .NET Framework 4 è installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="e8139-131">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="e8139-132">A partire da .NET Framework 4, quando si utilizzano i contatori delle prestazioni, PerfCounter. dll controlla la voce del registro di sistema CategoryOptions per ogni provider per determinare se deve essere letta dalla memoria condivisa specifica della categoria o dalla memoria condivisa globale.</span><span class="sxs-lookup"><span data-stu-id="e8139-132">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="e8139-133">Il .NET Framework 1,1 PerfCounter. dll non legge la voce del registro di sistema perché non è in grado di riconoscere la memoria condivisa specifica della categoria; viene sempre letta dalla memoria condivisa globale.</span><span class="sxs-lookup"><span data-stu-id="e8139-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="e8139-134">Per compatibilità con le versioni precedenti, il .NET Framework 4 PerfCounter. dll non controlla la voce del registro di sistema CategoryOptions durante l'esecuzione in un'applicazione .NET Framework 1,1.</span><span class="sxs-lookup"><span data-stu-id="e8139-134">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="e8139-135">Usa semplicemente la memoria condivisa globale, proprio come la .NET Framework 1,1 PerfCounter. dll.</span><span class="sxs-lookup"><span data-stu-id="e8139-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="e8139-136">Tuttavia, è possibile indicare al .NET Framework 4 PerfCounter. dll di controllare l'impostazione del registro di sistema abilitando l'elemento `<forcePerformanceCounterUniqueSharedMemoryReads>`.</span><span class="sxs-lookup"><span data-stu-id="e8139-136">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e8139-137">L'abilitazione dell'elemento `<forcePerformanceCounterUniqueSharedMemoryReads>` non garantisce che venga utilizzata la memoria condivisa specifica della categoria.</span><span class="sxs-lookup"><span data-stu-id="e8139-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="e8139-138">Se si imposta Enabled su `true`, PerfCounter. dll fa riferimento solo all'impostazione del registro di sistema CategoryOptions.</span><span class="sxs-lookup"><span data-stu-id="e8139-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="e8139-139">L'impostazione predefinita per CategoryOptions consiste nell'usare la memoria condivisa specifica della categoria; Tuttavia, è possibile modificare CategoryOptions per indicare che deve essere utilizzata la memoria condivisa globale.</span><span class="sxs-lookup"><span data-stu-id="e8139-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="e8139-140">La chiave del registro di sistema che contiene l'impostazione CategoryOptions è HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< CategoryName\>\Performance.</span><span class="sxs-lookup"><span data-stu-id="e8139-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="e8139-141">Per impostazione predefinita, CategoryOptions è impostato su 3, che indica a PerfCounter. dll di usare la memoria condivisa specifica della categoria.</span><span class="sxs-lookup"><span data-stu-id="e8139-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="e8139-142">Se CategoryOptions è impostato su 0, PerfCounter. dll utilizza la memoria condivisa globale.</span><span class="sxs-lookup"><span data-stu-id="e8139-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="e8139-143">I dati dell'istanza verranno riutilizzati solo se il nome dell'istanza da creare è identico all'istanza in fase di riutilizzo.</span><span class="sxs-lookup"><span data-stu-id="e8139-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="e8139-144">Tutte le versioni saranno in grado di scrivere nella categoria.</span><span class="sxs-lookup"><span data-stu-id="e8139-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="e8139-145">Se CategoryOptions è impostato su 1, viene utilizzata la memoria condivisa globale, ma i dati dell'istanza possono essere riutilizzati se il nome della categoria ha la stessa lunghezza della categoria riutilizzata.</span><span class="sxs-lookup"><span data-stu-id="e8139-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="e8139-146">Le impostazioni 0 e 1 possono causare perdite di memoria e la compilazione della memoria del contatore delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e8139-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8139-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8139-147">Example</span></span>  
 <span data-ttu-id="e8139-148">Nell'esempio seguente viene illustrato come specificare che PerfCounter. dll deve fare riferimento alla voce del registro di sistema CategoryOptions per determinare se deve utilizzare la memoria condivisa specifica della categoria.</span><span class="sxs-lookup"><span data-stu-id="e8139-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e8139-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8139-149">See also</span></span>

- [<span data-ttu-id="e8139-150">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="e8139-150">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e8139-151">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="e8139-151">Configuration File Schema</span></span>](../index.md)
