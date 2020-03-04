---
title: Garbage Collection
ms.date: 03/30/2017
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
ms.openlocfilehash: 846df5ecb1e681e8d0440e627586a681bf071efa
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160144"
---
# <a name="garbage-collection"></a><span data-ttu-id="8fe10-102">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="8fe10-102">Garbage Collection</span></span>
<span data-ttu-id="8fe10-103">Il Garbage Collector di .NET gestisce l'allocazione e il rilascio di memoria per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8fe10-103">.NET's garbage collector manages the allocation and release of memory for your application.</span></span> <span data-ttu-id="8fe10-104">Ogni volta che si crea un nuovo oggetto, Common Language Runtime alloca memoria per l'oggetto dall'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="8fe10-104">Each time you create a new object, the common language runtime allocates memory for the object from the managed heap.</span></span> <span data-ttu-id="8fe10-105">Lo spazio per i nuovi oggetti verrà allocato in questo modo dal runtime fino all'esaurimento dello spazio degli indirizzi nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="8fe10-105">As long as address space is available in the managed heap, the runtime continues to allocate space for new objects.</span></span> <span data-ttu-id="8fe10-106">La memoria, tuttavia, non è infinita.</span><span class="sxs-lookup"><span data-stu-id="8fe10-106">However, memory is not infinite.</span></span> <span data-ttu-id="8fe10-107">Alla fine il Garbage Collector deve eseguire una raccolta per liberare memoria.</span><span class="sxs-lookup"><span data-stu-id="8fe10-107">Eventually the garbage collector must perform a collection in order to free some memory.</span></span> <span data-ttu-id="8fe10-108">Il modulo di ottimizzazione del Garbage Collector consente di determinare il momento migliore per l'esecuzione di una raccolta sulla base delle allocazioni in corso.</span><span class="sxs-lookup"><span data-stu-id="8fe10-108">The garbage collector's optimizing engine determines the best time to perform a collection, based upon the allocations being made.</span></span> <span data-ttu-id="8fe10-109">Durante l'esecuzione di una raccolta, il Garbage Collector verifica la presenza di oggetti non più usati dall'applicazione nell'heap gestito ed esegue le operazioni necessarie per reclamare la relativa memoria.</span><span class="sxs-lookup"><span data-stu-id="8fe10-109">When the garbage collector performs a collection, it checks for objects in the managed heap that are no longer being used by the application and performs the necessary operations to reclaim their memory.</span></span>  
  
<a name="related_topics"></a>
## <a name="related-topics"></a><span data-ttu-id="8fe10-110">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8fe10-110">Related Topics</span></span>  
  
|<span data-ttu-id="8fe10-111">Titolo</span><span class="sxs-lookup"><span data-stu-id="8fe10-111">Title</span></span>|<span data-ttu-id="8fe10-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8fe10-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="8fe10-113">Nozioni fondamentali di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="8fe10-113">Fundamentals of Garbage Collection</span></span>](../../../docs/standard/garbage-collection/fundamentals.md)|<span data-ttu-id="8fe10-114">Descrive il funzionamento di Garbage Collection, la modalità di allocazione degli oggetti nell'heap gestito e altri concetti di base.</span><span class="sxs-lookup"><span data-stu-id="8fe10-114">Describes how garbage collection works, how objects are allocated on the managed heap, and other core concepts.</span></span>|  
|[<span data-ttu-id="8fe10-115">Garbage Collection e prestazioni</span><span class="sxs-lookup"><span data-stu-id="8fe10-115">Garbage Collection and Performance</span></span>](../../../docs/standard/garbage-collection/performance.md)|<span data-ttu-id="8fe10-116">Descrive i controlli delle prestazioni è possibile usare per diagnosticare i problemi di Garbage Collection e di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="8fe10-116">Describes the performance checks you can use to diagnose garbage collection and performance issues.</span></span>|  
|[<span data-ttu-id="8fe10-117">Raccolte indotte</span><span class="sxs-lookup"><span data-stu-id="8fe10-117">Induced Collections</span></span>](../../../docs/standard/garbage-collection/induced.md)|<span data-ttu-id="8fe10-118">Descrive come eseguire un'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="8fe10-118">Describes how to make a garbage collection occur.</span></span>|  
|[<span data-ttu-id="8fe10-119">Modalità di latenza</span><span class="sxs-lookup"><span data-stu-id="8fe10-119">Latency Modes</span></span>](../../../docs/standard/garbage-collection/latency.md)|<span data-ttu-id="8fe10-120">Descrive i modi per determinare l'ingerenza di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="8fe10-120">Describes the modes that determine the intrusiveness of garbage collection.</span></span>|  
|[<span data-ttu-id="8fe10-121">Ottimizzazione per l'hosting Web condiviso</span><span class="sxs-lookup"><span data-stu-id="8fe10-121">Optimization for Shared Web Hosting</span></span>](../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)|<span data-ttu-id="8fe10-122">Descrive come ottimizzare l'operazione di Garbage Collection nei server condivisi da più siti Web di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="8fe10-122">Describes how to optimize garbage collection on servers shared by several small Web sites.</span></span>|  
|[<span data-ttu-id="8fe10-123">Notifiche di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="8fe10-123">Garbage Collection Notifications</span></span>](../../../docs/standard/garbage-collection/notifications.md)|<span data-ttu-id="8fe10-124">Descrive come determinare quando è imminente una Garbage Collection completa e quando è stata completata.</span><span class="sxs-lookup"><span data-stu-id="8fe10-124">Describes how to determine when a full garbage collection is approaching and when it has completed.</span></span>|  
|[<span data-ttu-id="8fe10-125">Monitoraggio delle risorse del dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="8fe10-125">Application Domain Resource Monitoring</span></span>](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)|<span data-ttu-id="8fe10-126">Descrive come monitorare l'utilizzo della CPU e della memoria da un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8fe10-126">Describes how to monitor CPU and memory usage by an application domain.</span></span>|  
|[<span data-ttu-id="8fe10-127">Riferimenti deboli</span><span class="sxs-lookup"><span data-stu-id="8fe10-127">Weak References</span></span>](../../../docs/standard/garbage-collection/weak-references.md)|<span data-ttu-id="8fe10-128">Descrive i riferimenti che consentono al Garbage Collector di raccogliere un oggetto, pur senza impedire all'applicazione di accedervi.</span><span class="sxs-lookup"><span data-stu-id="8fe10-128">Describes features that permit the garbage collector to collect an object while still allowing the application to access that object.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="8fe10-129">Riferimento</span><span class="sxs-lookup"><span data-stu-id="8fe10-129">Reference</span></span>  
 <xref:System.GC?displayProperty=nameWithType>  
  
 <xref:System.GCCollectionMode?displayProperty=nameWithType>  
  
 <xref:System.GCNotificationStatus?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCSettings?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>  
  
 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
  
 <xref:System.IDisposable?displayProperty=nameWithType>  
  
## <a name="see-also"></a><span data-ttu-id="8fe10-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fe10-130">See also</span></span>

- [<span data-ttu-id="8fe10-131">Pulizia delle risorse non gestite</span><span class="sxs-lookup"><span data-stu-id="8fe10-131">Cleaning Up Unmanaged Resources</span></span>](../../../docs/standard/garbage-collection/unmanaged.md)
