---
title: Nozioni di base sul threading gestito
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62c207f6074e33813887c6903f5285ee72d14e85
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="managed-threading-basics"></a><span data-ttu-id="43bab-102">Nozioni di base sul threading gestito</span><span class="sxs-lookup"><span data-stu-id="43bab-102">Managed Threading Basics</span></span>
<span data-ttu-id="43bab-103">I primi cinque argomenti di questa sezione sono progettati per determinare quando usare threading gestito e vengono descritte alcune funzionalità di base.</span><span class="sxs-lookup"><span data-stu-id="43bab-103">The first five topics of this section are designed to help you determine when to use managed threading, and to explain some basic features.</span></span> <span data-ttu-id="43bab-104">Per informazioni sulle classi che forniscono funzionalità aggiuntive, vedere [Threading oggetti e funzionalità](../../../docs/standard/threading/threading-objects-and-features.md) e [panoramica delle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="43bab-104">For information on classes that provide additional features, see [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) and [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="43bab-105">Il resto degli argomenti in questa sezione illustrano avanzata, tra cui l'interazione del threading gestito con il sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="43bab-105">The rest of the topics in this section cover advanced topics, including the interaction of managed threading with the Windows operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43bab-106">Nel [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], la libreria Task Parallel Library e PLINQ forniscono le API per parallelismo delle attività e i dati nei programmi multithread.</span><span class="sxs-lookup"><span data-stu-id="43bab-106">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the Task Parallel Library and PLINQ provide APIs for task and data parallelism in multi-threaded programs.</span></span> <span data-ttu-id="43bab-107">Per altre informazioni, vedere [Programmazione parallela](../../../docs/standard/parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="43bab-107">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43bab-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="43bab-108">In This Section</span></span>  
 [<span data-ttu-id="43bab-109">Thread e Threading</span><span class="sxs-lookup"><span data-stu-id="43bab-109">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)  
 <span data-ttu-id="43bab-110">Illustra i vantaggi e svantaggi di più thread e vengono descritti gli scenari in cui è possibile creare thread o usano i pool thread.</span><span class="sxs-lookup"><span data-stu-id="43bab-110">Discusses the advantages and drawbacks of multiple threads, and outlines the scenarios in which you might create threads or use thread pool threads.</span></span>  
  
 [<span data-ttu-id="43bab-111">Eccezioni in thread gestiti</span><span class="sxs-lookup"><span data-stu-id="43bab-111">Exceptions in Managed Threads</span></span>](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 <span data-ttu-id="43bab-112">Viene descritto il comportamento di eccezioni non gestite nei thread per versioni diverse di .NET Framework, in particolare nelle situazioni in cui risultano chiusura dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="43bab-112">Describes the behavior of unhandled exceptions in threads for different versions of the .NET Framework, in particular the situations in which they result in termination of the application.</span></span>  
  
 [<span data-ttu-id="43bab-113">Sincronizzazione dei dati per il multithreading</span><span class="sxs-lookup"><span data-stu-id="43bab-113">Synchronizing Data for Multithreading</span></span>](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 <span data-ttu-id="43bab-114">Descrive le strategie per la sincronizzazione dei dati nelle classi che verranno utilizzate con più thread.</span><span class="sxs-lookup"><span data-stu-id="43bab-114">Describes strategies for synchronizing data in classes that will be used with multiple threads.</span></span>  
  
 [<span data-ttu-id="43bab-115">Stati dei thread gestiti</span><span class="sxs-lookup"><span data-stu-id="43bab-115">Managed Thread States</span></span>](../../../docs/standard/threading/managed-thread-states.md)  
 <span data-ttu-id="43bab-116">Vengono descritti gli stati di base di thread e viene illustrato come rilevare se un thread è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="43bab-116">Describes the basic thread states, and explains how to detect whether a thread is running.</span></span>  
  
 [<span data-ttu-id="43bab-117">Thread in primo piano e in background</span><span class="sxs-lookup"><span data-stu-id="43bab-117">Foreground and Background Threads</span></span>](../../../docs/standard/threading/foreground-and-background-threads.md)  
 <span data-ttu-id="43bab-118">Vengono illustrate le differenze tra i thread in primo piano e sfondo.</span><span class="sxs-lookup"><span data-stu-id="43bab-118">Explains the differences between foreground and background threads.</span></span>  
  
 [<span data-ttu-id="43bab-119">Threading gestito e non gestito in Windows</span><span class="sxs-lookup"><span data-stu-id="43bab-119">Managed and Unmanaged Threading in Windows</span></span>](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 <span data-ttu-id="43bab-120">Viene illustrata la relazione tra threading gestito e non gestito, elenca equivalenti gestiti threading API di Windows e viene descritta l'interazione di thread gestiti e apartment COM.</span><span class="sxs-lookup"><span data-stu-id="43bab-120">Discusses the relationship between managed and unmanaged threading, lists managed equivalents for Windows threading APIs, and discusses the interaction of COM apartments and managed threads.</span></span>  
  
 [<span data-ttu-id="43bab-121">Thread.Suspend, operazioni di Garbage Collection e punti sicuri</span><span class="sxs-lookup"><span data-stu-id="43bab-121">Thread.Suspend, Garbage Collection, and Safe Points</span></span>](../../../docs/standard/threading/thread-suspend-garbage-collection-and-safe-points.md)  
 <span data-ttu-id="43bab-122">Descrive i thread sospensione e garbage collection.</span><span class="sxs-lookup"><span data-stu-id="43bab-122">Describes thread suspension and garbage collection.</span></span>  
  
 [<span data-ttu-id="43bab-123">Archiviazione locale del thread: slot di dati e campi statici relativi ai thread</span><span class="sxs-lookup"><span data-stu-id="43bab-123">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 <span data-ttu-id="43bab-124">Vengono descritti i meccanismi di archiviazione relativi ai thread.</span><span class="sxs-lookup"><span data-stu-id="43bab-124">Describes thread-relative storage mechanisms.</span></span>  
  
 [<span data-ttu-id="43bab-125">Annullamento in thread gestiti</span><span class="sxs-lookup"><span data-stu-id="43bab-125">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 <span data-ttu-id="43bab-126">Descrive le operazioni sincrone asincrone o con esecuzione prolungata può essere annullata utilizzando un token di annullamento.</span><span class="sxs-lookup"><span data-stu-id="43bab-126">Describes how asynchronous or long-running synchronous operations can be canceled by using a cancellation token.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="43bab-127">Riferimento</span><span class="sxs-lookup"><span data-stu-id="43bab-127">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="43bab-128">Rende disponibile la documentazione di riferimento per la classe **Thread**, che rappresenta un thread gestito, indipendentemente dal fatto che derivi da codice non gestito o sia stato creato in un'applicazione gestita.</span><span class="sxs-lookup"><span data-stu-id="43bab-128">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="43bab-129">Fornisce un metodo sicuro per implementare il multithreading insieme a oggetti dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="43bab-129">Provides a safe way to implement multithreading in conjunction with user-interface objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="43bab-130">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="43bab-130">Related Sections</span></span>  
 [<span data-ttu-id="43bab-131">Cenni preliminari sulle primitive di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="43bab-131">Overview of Synchronization Primitives</span></span>](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 <span data-ttu-id="43bab-132">Descrive le classi gestite utilizzate per sincronizzare le attività di più thread.</span><span class="sxs-lookup"><span data-stu-id="43bab-132">Describes the managed classes used to synchronize the activities of multiple threads.</span></span>  
  
 [<span data-ttu-id="43bab-133">Suggerimenti per l'utilizzo del threading gestito</span><span class="sxs-lookup"><span data-stu-id="43bab-133">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 <span data-ttu-id="43bab-134">Vengono descritti problemi comuni con multithreading e le strategie per evitarli.</span><span class="sxs-lookup"><span data-stu-id="43bab-134">Describes common problems with multithreading and strategies for avoiding problems.</span></span>  
  
 [<span data-ttu-id="43bab-135">Programmazione parallela</span><span class="sxs-lookup"><span data-stu-id="43bab-135">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 <span data-ttu-id="43bab-136">Descrive la Task Parallel Library e PLINQ, che semplificano notevolmente la creazione di applicazioni .NET Framework asincrone e multithreading.</span><span class="sxs-lookup"><span data-stu-id="43bab-136">Describes the Task Parallel Library and PLINQ, which greatly simplify the work of creating asynchronous and multi-threaded .NET Framework applications.</span></span>
