---
title: Garbage Collection .NET
ms.date: 04/21/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- memory, garbage collection
- garbage collection, automatic memory management
- GC [.NET Framework]
- memory, allocating
- common language runtime, garbage collection
- garbage collector
- cleanup operations
- garbage collection
- memory, releasing
- common language runtime, automatic memory management
- automatic memory management
- runtime, automatic memory management
- runtime, garbage collection
- garbage collection, about
ms.assetid: 22b6cb97-0c80-4eeb-a2cf-5ed7655e37f9
ms.openlocfilehash: ef7e078c6ef2f0b4081c49aa0db09316e79f0702
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286054"
---
# <a name="garbage-collection"></a><span data-ttu-id="8c2db-102">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="8c2db-102">Garbage collection</span></span>

<span data-ttu-id="8c2db-103">Il Garbage Collector di .NET gestisce l'allocazione e il rilascio di memoria per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8c2db-103">.NET's garbage collector manages the allocation and release of memory for your application.</span></span> <span data-ttu-id="8c2db-104">Ogni volta che si crea un nuovo oggetto, Common Language Runtime alloca memoria per l'oggetto dall'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="8c2db-104">Each time you create a new object, the common language runtime allocates memory for the object from the managed heap.</span></span> <span data-ttu-id="8c2db-105">Lo spazio per i nuovi oggetti verrà allocato in questo modo dal runtime fino all'esaurimento dello spazio degli indirizzi nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="8c2db-105">As long as address space is available in the managed heap, the runtime continues to allocate space for new objects.</span></span> <span data-ttu-id="8c2db-106">La memoria, tuttavia, non è infinita.</span><span class="sxs-lookup"><span data-stu-id="8c2db-106">However, memory is not infinite.</span></span> <span data-ttu-id="8c2db-107">Alla fine il Garbage Collector deve eseguire una raccolta per liberare memoria.</span><span class="sxs-lookup"><span data-stu-id="8c2db-107">Eventually the garbage collector must perform a collection in order to free some memory.</span></span> <span data-ttu-id="8c2db-108">Il modulo di ottimizzazione del Garbage Collector consente di determinare il momento migliore per l'esecuzione di una raccolta sulla base delle allocazioni in corso.</span><span class="sxs-lookup"><span data-stu-id="8c2db-108">The garbage collector's optimizing engine determines the best time to perform a collection, based upon the allocations being made.</span></span> <span data-ttu-id="8c2db-109">Durante l'esecuzione di una raccolta, il Garbage Collector verifica la presenza di oggetti non più usati dall'applicazione nell'heap gestito ed esegue le operazioni necessarie per reclamare la relativa memoria.</span><span class="sxs-lookup"><span data-stu-id="8c2db-109">When the garbage collector performs a collection, it checks for objects in the managed heap that are no longer being used by the application and performs the necessary operations to reclaim their memory.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8c2db-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="8c2db-110">In this section</span></span>
  
|<span data-ttu-id="8c2db-111">Titolo</span><span class="sxs-lookup"><span data-stu-id="8c2db-111">Title</span></span>|<span data-ttu-id="8c2db-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c2db-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="8c2db-113">Nozioni fondamentali di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="8c2db-113">Fundamentals of garbage collection</span></span>](fundamentals.md)|<span data-ttu-id="8c2db-114">Descrive il funzionamento di Garbage Collection, la modalità di allocazione degli oggetti nell'heap gestito e altri concetti di base.</span><span class="sxs-lookup"><span data-stu-id="8c2db-114">Describes how garbage collection works, how objects are allocated on the managed heap, and other core concepts.</span></span>|  
|[<span data-ttu-id="8c2db-115">Operazione di Garbage Collection per workstation e server</span><span class="sxs-lookup"><span data-stu-id="8c2db-115">Workstation and server garbage collection</span></span>](workstation-server-gc.md)|<span data-ttu-id="8c2db-116">Descrive le differenze tra Garbage Collection workstation per le app client e Garbage Collection server per le app Server.</span><span class="sxs-lookup"><span data-stu-id="8c2db-116">Describes the differences between workstation garbage collection for client apps and server garbage collection for server apps.</span></span>|
|[<span data-ttu-id="8c2db-117">Garbage Collection in background</span><span class="sxs-lookup"><span data-stu-id="8c2db-117">Background garbage collection</span></span>](background-gc.md)|<span data-ttu-id="8c2db-118">Descrive Garbage Collection in background, ovvero la raccolta di oggetti di generazione 0 e 1 mentre è in corso la raccolta di generazione 2.</span><span class="sxs-lookup"><span data-stu-id="8c2db-118">Describes background garbage collection, which is the collection of generation 0 and 1 objects while generation 2 collection is in progress.</span></span>|
|[<span data-ttu-id="8c2db-119">Heap degli oggetti grandi</span><span class="sxs-lookup"><span data-stu-id="8c2db-119">The large object heap</span></span>](large-object-heap.md)|<span data-ttu-id="8c2db-120">Descrive l'heap degli oggetti grandi (LOH) e la modalità di Garbage Collection degli oggetti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="8c2db-120">Describes the large object heap (LOH) and how large objects are garbage-collected.</span></span>|
|[<span data-ttu-id="8c2db-121">Garbage Collection e prestazioni</span><span class="sxs-lookup"><span data-stu-id="8c2db-121">Garbage collection and performance</span></span>](performance.md)|<span data-ttu-id="8c2db-122">Descrive i controlli delle prestazioni è possibile usare per diagnosticare i problemi di Garbage Collection e di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="8c2db-122">Describes the performance checks you can use to diagnose garbage collection and performance issues.</span></span>|  
|[<span data-ttu-id="8c2db-123">Raccolte indotte</span><span class="sxs-lookup"><span data-stu-id="8c2db-123">Induced collections</span></span>](induced.md)|<span data-ttu-id="8c2db-124">Descrive come eseguire un'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="8c2db-124">Describes how to make a garbage collection occur.</span></span>|  
|[<span data-ttu-id="8c2db-125">Modalità di latenza</span><span class="sxs-lookup"><span data-stu-id="8c2db-125">Latency modes</span></span>](latency.md)|<span data-ttu-id="8c2db-126">Descrive i modi per determinare l'ingerenza di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="8c2db-126">Describes the modes that determine the intrusiveness of garbage collection.</span></span>|  
|[<span data-ttu-id="8c2db-127">Ottimizzazione per l'hosting Web condiviso</span><span class="sxs-lookup"><span data-stu-id="8c2db-127">Optimization for shared web hosting</span></span>](optimization-for-shared-web-hosting.md)|<span data-ttu-id="8c2db-128">Descrive come ottimizzare l'operazione di Garbage Collection nei server condivisi da più siti Web di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="8c2db-128">Describes how to optimize garbage collection on servers shared by several small Web sites.</span></span>|  
|[<span data-ttu-id="8c2db-129">Notifiche di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="8c2db-129">Garbage collection notifications</span></span>](notifications.md)|<span data-ttu-id="8c2db-130">Descrive come determinare quando è imminente una Garbage Collection completa e quando è stata completata.</span><span class="sxs-lookup"><span data-stu-id="8c2db-130">Describes how to determine when a full garbage collection is approaching and when it has completed.</span></span>|  
|[<span data-ttu-id="8c2db-131">Monitoraggio delle risorse del dominio applicazione</span><span class="sxs-lookup"><span data-stu-id="8c2db-131">Application domain resource monitoring</span></span>](app-domain-resource-monitoring.md)|<span data-ttu-id="8c2db-132">Descrive come monitorare l'utilizzo della CPU e della memoria da un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8c2db-132">Describes how to monitor CPU and memory usage by an application domain.</span></span>|  
|[<span data-ttu-id="8c2db-133">Riferimenti deboli</span><span class="sxs-lookup"><span data-stu-id="8c2db-133">Weak references</span></span>](weak-references.md)|<span data-ttu-id="8c2db-134">Descrive i riferimenti che consentono al Garbage Collector di raccogliere un oggetto, pur senza impedire all'applicazione di accedervi.</span><span class="sxs-lookup"><span data-stu-id="8c2db-134">Describes features that permit the garbage collector to collect an object while still allowing the application to access that object.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="8c2db-135">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="8c2db-135">Reference</span></span>

- <xref:System.GC?displayProperty=nameWithType>  
- <xref:System.GCCollectionMode?displayProperty=nameWithType>  
- <xref:System.GCNotificationStatus?displayProperty=nameWithType>  
- <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>  
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
- <xref:System.IDisposable?displayProperty=nameWithType>  
  
## <a name="see-also"></a><span data-ttu-id="8c2db-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c2db-136">See also</span></span>

- [<span data-ttu-id="8c2db-137">Pulizia delle risorse non gestite</span><span class="sxs-lookup"><span data-stu-id="8c2db-137">Clean up unmanaged resources</span></span>](unmanaged.md)
