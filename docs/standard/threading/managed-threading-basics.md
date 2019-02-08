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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e053a04ba0587a4eca166fa710bc465094feca80
ms.sourcegitcommit: dcc8feeff4718664087747529638ec9b47e65234
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2019
ms.locfileid: "55479568"
---
# <a name="managed-threading-basics"></a><span data-ttu-id="b2c50-102">Nozioni di base sul threading gestito</span><span class="sxs-lookup"><span data-stu-id="b2c50-102">Managed threading basics</span></span>

<span data-ttu-id="b2c50-103">I primi cinque argomenti di questa sezione contengono informazioni utili per determinare quando usare il threading gestito e descrivono alcune funzionalità di base.</span><span class="sxs-lookup"><span data-stu-id="b2c50-103">The first five topics of this section are designed to help you determine when to use managed threading and to explain some basic features.</span></span> <span data-ttu-id="b2c50-104">Per informazioni sulle classi che forniscono funzionalità aggiuntive, vedere [Oggetti e funzionalità del threading](../../../docs/standard/threading/threading-objects-and-features.md) e [Cenni preliminari sulle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="b2c50-104">For information on classes that provide additional features, see [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) and [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="b2c50-105">Gli altri argomenti di questa sezione illustrano funzionalità avanzate, tra cui l'interazione del threading gestito con il sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="b2c50-105">The rest of the topics in this section cover advanced topics, including the interaction of managed threading with the Windows operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2c50-106">In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] Task Parallel Library e PLINQ forniscono le API per il parallelismo di attività e dati nei programmi multithread.</span><span class="sxs-lookup"><span data-stu-id="b2c50-106">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the Task Parallel Library and PLINQ provide APIs for task and data parallelism in multi-threaded programs.</span></span> <span data-ttu-id="b2c50-107">Per altre informazioni, vedere [Programmazione parallela](../../../docs/standard/parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="b2c50-107">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b2c50-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="b2c50-108">In this section</span></span>

 <span data-ttu-id="b2c50-109">[Threads and Threading](../../../docs/standard/threading/threads-and-threading.md) (Thread e threading)</span><span class="sxs-lookup"><span data-stu-id="b2c50-109">[Threads and Threading](../../../docs/standard/threading/threads-and-threading.md)</span></span>  
 <span data-ttu-id="b2c50-110">Illustra i vantaggi e gli svantaggi di più thread e descrive gli scenari in cui è possibile creare thread o usare thread di pool di thread.</span><span class="sxs-lookup"><span data-stu-id="b2c50-110">Discusses the advantages and drawbacks of multiple threads, and outlines the scenarios in which you might create threads or use thread pool threads.</span></span>  
  
 [<span data-ttu-id="b2c50-111">Eccezioni in thread gestiti</span><span class="sxs-lookup"><span data-stu-id="b2c50-111">Exceptions in Managed Threads</span></span>](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 <span data-ttu-id="b2c50-112">Illustra il comportamento delle eccezioni non gestite nei thread per versioni diverse di .NET Framework, in particolare le situazioni in cui causano la terminazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b2c50-112">Describes the behavior of unhandled exceptions in threads for different versions of the .NET Framework, in particular the situations in which they result in termination of the application.</span></span>  
  
 [<span data-ttu-id="b2c50-113">Sincronizzazione dei dati per il multithreading</span><span class="sxs-lookup"><span data-stu-id="b2c50-113">Synchronizing Data for Multithreading</span></span>](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 <span data-ttu-id="b2c50-114">Illustra le strategie per la sincronizzazione dei dati nelle classi, che verranno usati con più thread.</span><span class="sxs-lookup"><span data-stu-id="b2c50-114">Describes strategies for synchronizing data in classes that will be used with multiple threads.</span></span>  
  
 [<span data-ttu-id="b2c50-115">Thread in primo piano e in background</span><span class="sxs-lookup"><span data-stu-id="b2c50-115">Foreground and Background Threads</span></span>](../../../docs/standard/threading/foreground-and-background-threads.md)  
 <span data-ttu-id="b2c50-116">Illustra le differenze tra i thread in primo piano e in background.</span><span class="sxs-lookup"><span data-stu-id="b2c50-116">Explains the differences between foreground and background threads.</span></span>  
  
 [<span data-ttu-id="b2c50-117">Threading gestito e non gestito in Windows</span><span class="sxs-lookup"><span data-stu-id="b2c50-117">Managed and Unmanaged Threading in Windows</span></span>](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 <span data-ttu-id="b2c50-118">Illustra la relazione tra il threading gestito e non gestito, elenca gli equivalenti gestiti delle API di threading Windows e illustra l'interazione degli apartment COM e dei thread gestiti.</span><span class="sxs-lookup"><span data-stu-id="b2c50-118">Discusses the relationship between managed and unmanaged threading, lists managed equivalents for Windows threading APIs, and discusses the interaction of COM apartments and managed threads.</span></span>  
  
 [<span data-ttu-id="b2c50-119">Thread.Suspend, operazioni di Garbage Collection e punti sicuri</span><span class="sxs-lookup"><span data-stu-id="b2c50-119">Thread.Suspend, Garbage Collection, and Safe Points</span></span>](../../../docs/standard/threading/thread-suspend-garbage-collection-and-safe-points.md)  
 <span data-ttu-id="b2c50-120">Illustra la sospensione dei thread e la Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b2c50-120">Describes thread suspension and garbage collection.</span></span>  
  
 [<span data-ttu-id="b2c50-121">Archiviazione locale del thread: slot di dati e campi statici relativi ai thread</span><span class="sxs-lookup"><span data-stu-id="b2c50-121">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 <span data-ttu-id="b2c50-122">Illustra i meccanismi di archiviazione relativi ai thread.</span><span class="sxs-lookup"><span data-stu-id="b2c50-122">Describes thread-relative storage mechanisms.</span></span>  
  
 [<span data-ttu-id="b2c50-123">Annullamento in thread gestiti</span><span class="sxs-lookup"><span data-stu-id="b2c50-123">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 <span data-ttu-id="b2c50-124">Illustra come è possibile annullare le operazioni asincrone o sincrone con esecuzione prolungata usando un token di annullamento.</span><span class="sxs-lookup"><span data-stu-id="b2c50-124">Describes how asynchronous or long-running synchronous operations can be canceled by using a cancellation token.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b2c50-125">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="b2c50-125">Reference</span></span>

 <xref:System.Threading.Thread>  
 <span data-ttu-id="b2c50-126">Rende disponibile la documentazione di riferimento per la classe **Thread**, che rappresenta un thread gestito, indipendentemente dal fatto che derivi da codice non gestito o sia stato creato in un'applicazione gestita.</span><span class="sxs-lookup"><span data-stu-id="b2c50-126">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="b2c50-127">Consente di implementare in modo sicuro il multithreading insieme agli oggetti dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="b2c50-127">Provides a safe way to implement multithreading in conjunction with user-interface objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b2c50-128">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="b2c50-128">Related sections</span></span>

 [<span data-ttu-id="b2c50-129">Panoramica sulle primitive di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="b2c50-129">Overview of Synchronization Primitives</span></span>](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 <span data-ttu-id="b2c50-130">Illustra le classi gestite usate per sincronizzare le attività di più thread.</span><span class="sxs-lookup"><span data-stu-id="b2c50-130">Describes the managed classes used to synchronize the activities of multiple threads.</span></span>  
  
 [<span data-ttu-id="b2c50-131">Suggerimenti per l'utilizzo del threading gestito</span><span class="sxs-lookup"><span data-stu-id="b2c50-131">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 <span data-ttu-id="b2c50-132">Illustra i problemi comuni del multithreading e le strategie per evitarli.</span><span class="sxs-lookup"><span data-stu-id="b2c50-132">Describes common problems with multithreading and strategies for avoiding problems.</span></span>  
  
 [<span data-ttu-id="b2c50-133">Programmazione parallela</span><span class="sxs-lookup"><span data-stu-id="b2c50-133">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 <span data-ttu-id="b2c50-134">Illustra Task Parallel Library e PLINQ, che semplificano notevolmente la creazione di applicazioni .NET Framework asincrone e multithread.</span><span class="sxs-lookup"><span data-stu-id="b2c50-134">Describes the Task Parallel Library and PLINQ, which greatly simplify the work of creating asynchronous and multi-threaded .NET Framework applications.</span></span>
