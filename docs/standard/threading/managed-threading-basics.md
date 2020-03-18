---
title: Nozioni di base sul threading gestito
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
ms.openlocfilehash: bec769043ab630b37609bed12302ceff5b90474a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139238"
---
# <a name="managed-threading-basics"></a><span data-ttu-id="568d3-102">Nozioni di base sul threading gestito</span><span class="sxs-lookup"><span data-stu-id="568d3-102">Managed threading basics</span></span>

<span data-ttu-id="568d3-103">I primi cinque argomenti di questa sezione contengono informazioni utili per determinare quando usare il threading gestito e descrivono alcune funzionalità di base.</span><span class="sxs-lookup"><span data-stu-id="568d3-103">The first five topics of this section are designed to help you determine when to use managed threading and to explain some basic features.</span></span> <span data-ttu-id="568d3-104">Per informazioni sulle classi che forniscono funzionalità aggiuntive, vedere [Oggetti e funzionalità del threading](../../../docs/standard/threading/threading-objects-and-features.md) e [Cenni preliminari sulle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="568d3-104">For information on classes that provide additional features, see [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) and [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="568d3-105">Gli altri argomenti di questa sezione illustrano funzionalità avanzate, tra cui l'interazione del threading gestito con il sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="568d3-105">The rest of the topics in this section cover advanced topics, including the interaction of managed threading with the Windows operating system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="568d3-106">In .NET Framework 4, Task Parallel Library e PLINQ forniscono le API per il parallelismo di attività e dati nei programmi multithread.</span><span class="sxs-lookup"><span data-stu-id="568d3-106">In the .NET Framework 4, the Task Parallel Library and PLINQ provide APIs for task and data parallelism in multi-threaded programs.</span></span> <span data-ttu-id="568d3-107">Per ulteriori informazioni, vedere [Programmazione parallela](../../../docs/standard/parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="568d3-107">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="568d3-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="568d3-108">In this section</span></span>

 [<span data-ttu-id="568d3-109">Thread e threading</span><span class="sxs-lookup"><span data-stu-id="568d3-109">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)  
 <span data-ttu-id="568d3-110">Illustra i vantaggi e gli svantaggi di più thread e descrive gli scenari in cui è possibile creare thread o usare thread di pool di thread.</span><span class="sxs-lookup"><span data-stu-id="568d3-110">Discusses the advantages and drawbacks of multiple threads, and outlines the scenarios in which you might create threads or use thread pool threads.</span></span>  
  
 [<span data-ttu-id="568d3-111">Eccezioni in thread gestiti</span><span class="sxs-lookup"><span data-stu-id="568d3-111">Exceptions in Managed Threads</span></span>](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 <span data-ttu-id="568d3-112">Illustra il comportamento delle eccezioni non gestite nei thread per versioni diverse di .NET Framework, in particolare le situazioni in cui causano la terminazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="568d3-112">Describes the behavior of unhandled exceptions in threads for different versions of the .NET Framework, in particular the situations in which they result in termination of the application.</span></span>  
  
 [<span data-ttu-id="568d3-113">Sincronizzazione dei dati per il multithreading</span><span class="sxs-lookup"><span data-stu-id="568d3-113">Synchronizing Data for Multithreading</span></span>](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 <span data-ttu-id="568d3-114">Illustra le strategie per la sincronizzazione dei dati nelle classi, che verranno usati con più thread.</span><span class="sxs-lookup"><span data-stu-id="568d3-114">Describes strategies for synchronizing data in classes that will be used with multiple threads.</span></span>  
  
 [<span data-ttu-id="568d3-115">Thread in primo piano e in background</span><span class="sxs-lookup"><span data-stu-id="568d3-115">Foreground and Background Threads</span></span>](../../../docs/standard/threading/foreground-and-background-threads.md)  
 <span data-ttu-id="568d3-116">Illustra le differenze tra i thread in primo piano e in background.</span><span class="sxs-lookup"><span data-stu-id="568d3-116">Explains the differences between foreground and background threads.</span></span>  
  
 [<span data-ttu-id="568d3-117">Threading gestito e non gestito in Windows</span><span class="sxs-lookup"><span data-stu-id="568d3-117">Managed and Unmanaged Threading in Windows</span></span>](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 <span data-ttu-id="568d3-118">Illustra la relazione tra il threading gestito e non gestito, elenca gli equivalenti gestiti delle API di threading Windows e illustra l'interazione degli apartment COM e dei thread gestiti.</span><span class="sxs-lookup"><span data-stu-id="568d3-118">Discusses the relationship between managed and unmanaged threading, lists managed equivalents for Windows threading APIs, and discusses the interaction of COM apartments and managed threads.</span></span>  
  
 [<span data-ttu-id="568d3-119">Archiviazione locale del thread: slot di dati e campi statici relativi ai thread</span><span class="sxs-lookup"><span data-stu-id="568d3-119">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 <span data-ttu-id="568d3-120">Illustra i meccanismi di archiviazione relativi ai thread.</span><span class="sxs-lookup"><span data-stu-id="568d3-120">Describes thread-relative storage mechanisms.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="568d3-121">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="568d3-121">Reference</span></span>

 <xref:System.Threading.Thread>  
 <span data-ttu-id="568d3-122">Rende disponibile la documentazione di riferimento per la classe **Thread**, che rappresenta un thread gestito, indipendentemente dal fatto che derivi da codice non gestito o sia stato creato in un'applicazione gestita.</span><span class="sxs-lookup"><span data-stu-id="568d3-122">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="568d3-123">Consente di implementare in modo sicuro il multithreading insieme agli oggetti dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="568d3-123">Provides a safe way to implement multithreading in conjunction with user-interface objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="568d3-124">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="568d3-124">Related sections</span></span>

 [<span data-ttu-id="568d3-125">Panoramica delle primitive di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="568d3-125">Overview of Synchronization Primitives</span></span>](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 <span data-ttu-id="568d3-126">Illustra le classi gestite usate per sincronizzare le attività di più thread.</span><span class="sxs-lookup"><span data-stu-id="568d3-126">Describes the managed classes used to synchronize the activities of multiple threads.</span></span>  
  
 [<span data-ttu-id="568d3-127">Procedure consigliate per il threading gestitoManaged Threading Best Practices</span><span class="sxs-lookup"><span data-stu-id="568d3-127">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 <span data-ttu-id="568d3-128">Illustra i problemi comuni del multithreading e le strategie per evitarli.</span><span class="sxs-lookup"><span data-stu-id="568d3-128">Describes common problems with multithreading and strategies for avoiding problems.</span></span>  
  
 [<span data-ttu-id="568d3-129">Programmazione parallela</span><span class="sxs-lookup"><span data-stu-id="568d3-129">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 <span data-ttu-id="568d3-130">Illustra Task Parallel Library e PLINQ, che semplificano notevolmente la creazione di applicazioni .NET Framework asincrone e multithread.</span><span class="sxs-lookup"><span data-stu-id="568d3-130">Describes the Task Parallel Library and PLINQ, which greatly simplify the work of creating asynchronous and multi-threaded .NET Framework applications.</span></span>
