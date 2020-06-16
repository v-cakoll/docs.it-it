---
title: Nozioni di base sul threading gestito
description: Vedere i collegamenti ad altri articoli relativi al threading gestito, ad esempio le eccezioni, la sincronizzazione dei dati, il primo piano & thread in background, l'archiviazione locale e altro ancora.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
ms.openlocfilehash: d4a4ceabf29bd0f6f537e59ba477f9da686b1ef5
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769093"
---
# <a name="managed-threading-basics"></a><span data-ttu-id="bfa51-103">Nozioni di base sul threading gestito</span><span class="sxs-lookup"><span data-stu-id="bfa51-103">Managed threading basics</span></span>

<span data-ttu-id="bfa51-104">I primi cinque argomenti di questa sezione contengono informazioni utili per determinare quando usare il threading gestito e descrivono alcune funzionalità di base.</span><span class="sxs-lookup"><span data-stu-id="bfa51-104">The first five topics of this section are designed to help you determine when to use managed threading and to explain some basic features.</span></span> <span data-ttu-id="bfa51-105">Per informazioni sulle classi che forniscono funzionalità aggiuntive, vedere [Oggetti e funzionalità del threading](threading-objects-and-features.md) e [Cenni preliminari sulle primitive di sincronizzazione](overview-of-synchronization-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="bfa51-105">For information on classes that provide additional features, see [Threading Objects and Features](threading-objects-and-features.md) and [Overview of Synchronization Primitives](overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="bfa51-106">Gli altri argomenti di questa sezione illustrano funzionalità avanzate, tra cui l'interazione del threading gestito con il sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="bfa51-106">The rest of the topics in this section cover advanced topics, including the interaction of managed threading with the Windows operating system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bfa51-107">In .NET Framework 4, Task Parallel Library e PLINQ forniscono le API per il parallelismo di attività e dati nei programmi multithread.</span><span class="sxs-lookup"><span data-stu-id="bfa51-107">In the .NET Framework 4, the Task Parallel Library and PLINQ provide APIs for task and data parallelism in multi-threaded programs.</span></span> <span data-ttu-id="bfa51-108">Per ulteriori informazioni, vedere [programmazione parallela](../parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="bfa51-108">For more information, see [Parallel Programming](../parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bfa51-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="bfa51-109">In this section</span></span>

 [<span data-ttu-id="bfa51-110">Thread e Threading</span><span class="sxs-lookup"><span data-stu-id="bfa51-110">Threads and Threading</span></span>](threads-and-threading.md)  
 <span data-ttu-id="bfa51-111">Illustra i vantaggi e gli svantaggi di più thread e descrive gli scenari in cui è possibile creare thread o usare thread di pool di thread.</span><span class="sxs-lookup"><span data-stu-id="bfa51-111">Discusses the advantages and drawbacks of multiple threads, and outlines the scenarios in which you might create threads or use thread pool threads.</span></span>  
  
 [<span data-ttu-id="bfa51-112">Eccezioni in thread gestiti</span><span class="sxs-lookup"><span data-stu-id="bfa51-112">Exceptions in Managed Threads</span></span>](exceptions-in-managed-threads.md)  
 <span data-ttu-id="bfa51-113">Illustra il comportamento delle eccezioni non gestite nei thread per versioni diverse di .NET Framework, in particolare le situazioni in cui causano la terminazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bfa51-113">Describes the behavior of unhandled exceptions in threads for different versions of the .NET Framework, in particular the situations in which they result in termination of the application.</span></span>  
  
 [<span data-ttu-id="bfa51-114">Sincronizzazione dei dati per il multithreading</span><span class="sxs-lookup"><span data-stu-id="bfa51-114">Synchronizing Data for Multithreading</span></span>](synchronizing-data-for-multithreading.md)  
 <span data-ttu-id="bfa51-115">Illustra le strategie per la sincronizzazione dei dati nelle classi, che verranno usati con più thread.</span><span class="sxs-lookup"><span data-stu-id="bfa51-115">Describes strategies for synchronizing data in classes that will be used with multiple threads.</span></span>  
  
 [<span data-ttu-id="bfa51-116">Thread in primo piano e in background</span><span class="sxs-lookup"><span data-stu-id="bfa51-116">Foreground and Background Threads</span></span>](foreground-and-background-threads.md)  
 <span data-ttu-id="bfa51-117">Illustra le differenze tra i thread in primo piano e in background.</span><span class="sxs-lookup"><span data-stu-id="bfa51-117">Explains the differences between foreground and background threads.</span></span>  
  
 [<span data-ttu-id="bfa51-118">Threading gestito e non gestito in Windows</span><span class="sxs-lookup"><span data-stu-id="bfa51-118">Managed and Unmanaged Threading in Windows</span></span>](managed-and-unmanaged-threading-in-windows.md)  
 <span data-ttu-id="bfa51-119">Illustra la relazione tra il threading gestito e non gestito, elenca gli equivalenti gestiti delle API di threading Windows e illustra l'interazione degli apartment COM e dei thread gestiti.</span><span class="sxs-lookup"><span data-stu-id="bfa51-119">Discusses the relationship between managed and unmanaged threading, lists managed equivalents for Windows threading APIs, and discusses the interaction of COM apartments and managed threads.</span></span>  
  
 [<span data-ttu-id="bfa51-120">Archiviazione locale del thread: slot di dati e campi statici relativi ai thread</span><span class="sxs-lookup"><span data-stu-id="bfa51-120">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>](thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 <span data-ttu-id="bfa51-121">Illustra i meccanismi di archiviazione relativi ai thread.</span><span class="sxs-lookup"><span data-stu-id="bfa51-121">Describes thread-relative storage mechanisms.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="bfa51-122">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="bfa51-122">Reference</span></span>

 <xref:System.Threading.Thread>  
 <span data-ttu-id="bfa51-123">Rende disponibile la documentazione di riferimento per la classe **Thread**, che rappresenta un thread gestito, indipendentemente dal fatto che derivi da codice non gestito o sia stato creato in un'applicazione gestita.</span><span class="sxs-lookup"><span data-stu-id="bfa51-123">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="bfa51-124">Consente di implementare in modo sicuro il multithreading insieme agli oggetti dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="bfa51-124">Provides a safe way to implement multithreading in conjunction with user-interface objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bfa51-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="bfa51-125">Related sections</span></span>

 [<span data-ttu-id="bfa51-126">Panoramica delle primitive di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="bfa51-126">Overview of Synchronization Primitives</span></span>](overview-of-synchronization-primitives.md)  
 <span data-ttu-id="bfa51-127">Illustra le classi gestite usate per sincronizzare le attività di più thread.</span><span class="sxs-lookup"><span data-stu-id="bfa51-127">Describes the managed classes used to synchronize the activities of multiple threads.</span></span>  
  
 [<span data-ttu-id="bfa51-128">Procedure consigliate per il threading gestito</span><span class="sxs-lookup"><span data-stu-id="bfa51-128">Managed Threading Best Practices</span></span>](managed-threading-best-practices.md)  
 <span data-ttu-id="bfa51-129">Illustra i problemi comuni del multithreading e le strategie per evitarli.</span><span class="sxs-lookup"><span data-stu-id="bfa51-129">Describes common problems with multithreading and strategies for avoiding problems.</span></span>  
  
 [<span data-ttu-id="bfa51-130">Programmazione parallela</span><span class="sxs-lookup"><span data-stu-id="bfa51-130">Parallel Programming</span></span>](../parallel-programming/index.md)  
 <span data-ttu-id="bfa51-131">Illustra Task Parallel Library e PLINQ, che semplificano notevolmente la creazione di applicazioni .NET Framework asincrone e multithread.</span><span class="sxs-lookup"><span data-stu-id="bfa51-131">Describes the Task Parallel Library and PLINQ, which greatly simplify the work of creating asynchronous and multi-threaded .NET Framework applications.</span></span>
