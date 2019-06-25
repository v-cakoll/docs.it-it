---
title: <forcePerformanceCounterUniqueSharedMemoryReads> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 00af9cf60d0bd2bac60950617b1315579d1a5a4d
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "67347343"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="6dbee-102">\<forcePerformanceCounterUniqueSharedMemoryReads > elemento</span><span class="sxs-lookup"><span data-stu-id="6dbee-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>
<span data-ttu-id="6dbee-103">Specifica se PerfCounter.dll usa l'impostazione del Registro di sistema CategoryOptions in un'applicazione di .NET Framework versione 1.1 per determinare se caricare i dati del contatore delle prestazioni dalla memoria condivisa specifica della categoria o dalla memoria globale.</span><span class="sxs-lookup"><span data-stu-id="6dbee-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
 <span data-ttu-id="6dbee-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6dbee-104">\<configuration></span></span>  
<span data-ttu-id="6dbee-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="6dbee-105">\<runtime></span></span>  
<span data-ttu-id="6dbee-106">\<forcePerformanceCounterUniqueSharedMemoryReads></span><span class="sxs-lookup"><span data-stu-id="6dbee-106">\<forcePerformanceCounterUniqueSharedMemoryReads></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dbee-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6dbee-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6dbee-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6dbee-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6dbee-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6dbee-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6dbee-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="6dbee-110">Attributes</span></span>  
  
|<span data-ttu-id="6dbee-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="6dbee-111">Attribute</span></span>|<span data-ttu-id="6dbee-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6dbee-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="6dbee-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6dbee-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="6dbee-114">Indica se PerfCounter. dll Usa l'impostazione del Registro di sistema CategoryOptions per determinare se caricare i dati dei contatori delle prestazioni di memoria condivisa specifica della categoria o della memoria globale.</span><span class="sxs-lookup"><span data-stu-id="6dbee-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="6dbee-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="6dbee-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="6dbee-116">Valore</span><span class="sxs-lookup"><span data-stu-id="6dbee-116">Value</span></span>|<span data-ttu-id="6dbee-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6dbee-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="6dbee-118">PerfCounter non usa il CategoryOptions questa impostazione del registro è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="6dbee-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="6dbee-119">PerfCounter usare l'impostazione del Registro di sistema CategoryOptions.</span><span class="sxs-lookup"><span data-stu-id="6dbee-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6dbee-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6dbee-120">Child Elements</span></span>  
 <span data-ttu-id="6dbee-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6dbee-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6dbee-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6dbee-122">Parent Elements</span></span>  
  
|<span data-ttu-id="6dbee-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="6dbee-123">Element</span></span>|<span data-ttu-id="6dbee-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6dbee-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6dbee-125">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6dbee-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6dbee-126">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="6dbee-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6dbee-127">Note</span><span class="sxs-lookup"><span data-stu-id="6dbee-127">Remarks</span></span>  
 <span data-ttu-id="6dbee-128">Nelle versioni di .NET Framework precedenti a .NET Framework 4, la versione di PerfCounter. dll è stato caricato corrispondeva al runtime che è stato caricato nel processo.</span><span class="sxs-lookup"><span data-stu-id="6dbee-128">In versions of the .NET Framework before the .NET Framework 4, the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="6dbee-129">Se un computer dispone di .NET Framework versione 1.1 sia installato .NET Framework 2.0, un'applicazione .NET Framework 1.1 carica la versione di .NET Framework 1.1 di PerfCounter. dll.</span><span class="sxs-lookup"><span data-stu-id="6dbee-129">If a computer had both the .NET Framework version 1.1 and the .NET Framework 2.0 installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="6dbee-130">A partire da .NET Framework 4, la versione installata più recente di PerfCounter. dll viene caricata.</span><span class="sxs-lookup"><span data-stu-id="6dbee-130">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="6dbee-131">Ciò significa che un'applicazione .NET Framework 1.1 caricherà la versione di .NET Framework 4 di PerfCounter se .NET Framework 4 è installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="6dbee-131">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="6dbee-132">A partire da .NET Framework 4, quando si utilizzano contatori delle prestazioni, PerfCounter controlla la voce del Registro di sistema CategoryOptions per ogni provider determinare se è necessario leggere dalla memoria condivisa specifica della categoria o la memoria condivisa globale.</span><span class="sxs-lookup"><span data-stu-id="6dbee-132">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="6dbee-133">Il .NET Framework 1.1 PerfCounter. dll non legge tale voce del Registro di sistema, perché non è conoscenza di memoria condivisa specifiche della categoria. legge sempre dalla memoria condivisa globale.</span><span class="sxs-lookup"><span data-stu-id="6dbee-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="6dbee-134">Per motivi di compatibilità di .NET Framework 4 PerfCounter. dll non verifica la voce del Registro di sistema CategoryOptions durante l'esecuzione in un'applicazione .NET Framework 1.1.</span><span class="sxs-lookup"><span data-stu-id="6dbee-134">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="6dbee-135">Utilizza semplicemente memoria condivisa globale, esattamente come il .NET Framework 1.1 PerfCounter. dll.</span><span class="sxs-lookup"><span data-stu-id="6dbee-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="6dbee-136">Si può però istruire il PerfCounter 4 di .NET Framework per verificare l'impostazione del Registro di sistema, consentendo la `<forcePerformanceCounterUniqueSharedMemoryReads>` elemento.</span><span class="sxs-lookup"><span data-stu-id="6dbee-136">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6dbee-137">L'abilitazione di `<forcePerformanceCounterUniqueSharedMemoryReads>` elemento non garantisce che verrà utilizzata la memoria condivisa specifiche della categoria.</span><span class="sxs-lookup"><span data-stu-id="6dbee-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="6dbee-138">Impostazione abilitata a `true` fa sì che solo fare riferimento l'impostazione del Registro di sistema CategoryOptions PerfCounter. dll.</span><span class="sxs-lookup"><span data-stu-id="6dbee-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="6dbee-139">L'impostazione predefinita per CategoryOptions consiste nell'usare specifiche della categoria memoria condivisa. Tuttavia, è possibile modificare CategoryOptions per indicare che la memoria condivisa globale deve essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="6dbee-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="6dbee-140">La chiave del Registro di sistema che contiene l'impostazione CategoryOptions è HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< categoryName\>\Performance.</span><span class="sxs-lookup"><span data-stu-id="6dbee-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="6dbee-141">Per impostazione predefinita, CategoryOptions è impostato su 3, che indica di PerfCounter. dll da utilizzare memoria condivisa specifica della categoria.</span><span class="sxs-lookup"><span data-stu-id="6dbee-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="6dbee-142">Se CategoryOptions è impostato su 0, PerfCounter utilizza memoria condivisa globale.</span><span class="sxs-lookup"><span data-stu-id="6dbee-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="6dbee-143">I dati dell'istanza verranno riutilizzati solo se il nome dell'istanza da creare è identico all'istanza vengono riutilizzato.</span><span class="sxs-lookup"><span data-stu-id="6dbee-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="6dbee-144">Tutte le versioni sarà in grado di scrivere in tale categoria.</span><span class="sxs-lookup"><span data-stu-id="6dbee-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="6dbee-145">Se CategoryOptions è impostato su 1, viene utilizzata la memoria condivisa globale, ma i dati dell'istanza possono essere riutilizzati se il nome della categoria è uguale alla lunghezza della categoria verrà riutilizzata.</span><span class="sxs-lookup"><span data-stu-id="6dbee-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="6dbee-146">Le impostazioni di 0 e 1 possono causare perdite di memoria e il riempimento del memoria dei contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="6dbee-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6dbee-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="6dbee-147">Example</span></span>  
 <span data-ttu-id="6dbee-148">Nell'esempio seguente viene illustrato come specificare che PerfCounter devono fare riferimento la voce del Registro di sistema CategoryOptions per determinare se deve utilizzare memoria condivisa specifica della categoria.</span><span class="sxs-lookup"><span data-stu-id="6dbee-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6dbee-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6dbee-149">See also</span></span>

- [<span data-ttu-id="6dbee-150">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="6dbee-150">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="6dbee-151">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="6dbee-151">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
