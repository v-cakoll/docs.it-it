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
ms.openlocfilehash: 4d2a96619fd1c48c79b5590efdb52c307d29710c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291006"
---
# <a name="managed-threading-basics"></a><span data-ttu-id="3b642-102">Nozioni di base sul threading gestito</span><span class="sxs-lookup"><span data-stu-id="3b642-102">Managed threading basics</span></span>

<span data-ttu-id="3b642-103">I primi cinque argomenti di questa sezione contengono informazioni utili per determinare quando usare il threading gestito e descrivono alcune funzionalità di base.</span><span class="sxs-lookup"><span data-stu-id="3b642-103">The first five topics of this section are designed to help you determine when to use managed threading and to explain some basic features.</span></span> <span data-ttu-id="3b642-104">Per informazioni sulle classi che forniscono funzionalità aggiuntive, vedere [Oggetti e funzionalità del threading](threading-objects-and-features.md) e [Cenni preliminari sulle primitive di sincronizzazione](overview-of-synchronization-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="3b642-104">For information on classes that provide additional features, see [Threading Objects and Features](threading-objects-and-features.md) and [Overview of Synchronization Primitives](overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="3b642-105">Gli altri argomenti di questa sezione illustrano funzionalità avanzate, tra cui l'interazione del threading gestito con il sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="3b642-105">The rest of the topics in this section cover advanced topics, including the interaction of managed threading with the Windows operating system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3b642-106">In .NET Framework 4, Task Parallel Library e PLINQ forniscono le API per il parallelismo di attività e dati nei programmi multithread.</span><span class="sxs-lookup"><span data-stu-id="3b642-106">In the .NET Framework 4, the Task Parallel Library and PLINQ provide APIs for task and data parallelism in multi-threaded programs.</span></span> <span data-ttu-id="3b642-107">Per ulteriori informazioni, vedere [programmazione parallela](../parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="3b642-107">For more information, see [Parallel Programming](../parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3b642-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3b642-108">In this section</span></span>

 [<span data-ttu-id="3b642-109">Thread e Threading</span><span class="sxs-lookup"><span data-stu-id="3b642-109">Threads and Threading</span></span>](threads-and-threading.md)  
 <span data-ttu-id="3b642-110">Illustra i vantaggi e gli svantaggi di più thread e descrive gli scenari in cui è possibile creare thread o usare thread di pool di thread.</span><span class="sxs-lookup"><span data-stu-id="3b642-110">Discusses the advantages and drawbacks of multiple threads, and outlines the scenarios in which you might create threads or use thread pool threads.</span></span>  
  
 [<span data-ttu-id="3b642-111">Eccezioni in thread gestiti</span><span class="sxs-lookup"><span data-stu-id="3b642-111">Exceptions in Managed Threads</span></span>](exceptions-in-managed-threads.md)  
 <span data-ttu-id="3b642-112">Illustra il comportamento delle eccezioni non gestite nei thread per versioni diverse di .NET Framework, in particolare le situazioni in cui causano la terminazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3b642-112">Describes the behavior of unhandled exceptions in threads for different versions of the .NET Framework, in particular the situations in which they result in termination of the application.</span></span>  
  
 [<span data-ttu-id="3b642-113">Sincronizzazione dei dati per il multithreading</span><span class="sxs-lookup"><span data-stu-id="3b642-113">Synchronizing Data for Multithreading</span></span>](synchronizing-data-for-multithreading.md)  
 <span data-ttu-id="3b642-114">Illustra le strategie per la sincronizzazione dei dati nelle classi, che verranno usati con più thread.</span><span class="sxs-lookup"><span data-stu-id="3b642-114">Describes strategies for synchronizing data in classes that will be used with multiple threads.</span></span>  
  
 [<span data-ttu-id="3b642-115">Thread in primo piano e in background</span><span class="sxs-lookup"><span data-stu-id="3b642-115">Foreground and Background Threads</span></span>](foreground-and-background-threads.md)  
 <span data-ttu-id="3b642-116">Illustra le differenze tra i thread in primo piano e in background.</span><span class="sxs-lookup"><span data-stu-id="3b642-116">Explains the differences between foreground and background threads.</span></span>  
  
 [<span data-ttu-id="3b642-117">Threading gestito e non gestito in Windows</span><span class="sxs-lookup"><span data-stu-id="3b642-117">Managed and Unmanaged Threading in Windows</span></span>](managed-and-unmanaged-threading-in-windows.md)  
 <span data-ttu-id="3b642-118">Illustra la relazione tra il threading gestito e non gestito, elenca gli equivalenti gestiti delle API di threading Windows e illustra l'interazione degli apartment COM e dei thread gestiti.</span><span class="sxs-lookup"><span data-stu-id="3b642-118">Discusses the relationship between managed and unmanaged threading, lists managed equivalents for Windows threading APIs, and discusses the interaction of COM apartments and managed threads.</span></span>  
  
 [<span data-ttu-id="3b642-119">Archiviazione locale del thread: slot di dati e campi statici relativi ai thread</span><span class="sxs-lookup"><span data-stu-id="3b642-119">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>](thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 <span data-ttu-id="3b642-120">Illustra i meccanismi di archiviazione relativi ai thread.</span><span class="sxs-lookup"><span data-stu-id="3b642-120">Describes thread-relative storage mechanisms.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3b642-121">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="3b642-121">Reference</span></span>

 <xref:System.Threading.Thread>  
 <span data-ttu-id="3b642-122">Rende disponibile la documentazione di riferimento per la classe **Thread**, che rappresenta un thread gestito, indipendentemente dal fatto che derivi da codice non gestito o sia stato creato in un'applicazione gestita.</span><span class="sxs-lookup"><span data-stu-id="3b642-122">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="3b642-123">Consente di implementare in modo sicuro il multithreading insieme agli oggetti dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="3b642-123">Provides a safe way to implement multithreading in conjunction with user-interface objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3b642-124">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="3b642-124">Related sections</span></span>

 [<span data-ttu-id="3b642-125">Panoramica delle primitive di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="3b642-125">Overview of Synchronization Primitives</span></span>](overview-of-synchronization-primitives.md)  
 <span data-ttu-id="3b642-126">Illustra le classi gestite usate per sincronizzare le attività di più thread.</span><span class="sxs-lookup"><span data-stu-id="3b642-126">Describes the managed classes used to synchronize the activities of multiple threads.</span></span>  
  
 [<span data-ttu-id="3b642-127">Procedure consigliate per il threading gestito</span><span class="sxs-lookup"><span data-stu-id="3b642-127">Managed Threading Best Practices</span></span>](managed-threading-best-practices.md)  
 <span data-ttu-id="3b642-128">Illustra i problemi comuni del multithreading e le strategie per evitarli.</span><span class="sxs-lookup"><span data-stu-id="3b642-128">Describes common problems with multithreading and strategies for avoiding problems.</span></span>  
  
 [<span data-ttu-id="3b642-129">Programmazione parallela</span><span class="sxs-lookup"><span data-stu-id="3b642-129">Parallel Programming</span></span>](../parallel-programming/index.md)  
 <span data-ttu-id="3b642-130">Illustra Task Parallel Library e PLINQ, che semplificano notevolmente la creazione di applicazioni .NET Framework asincrone e multithread.</span><span class="sxs-lookup"><span data-stu-id="3b642-130">Describes the Task Parallel Library and PLINQ, which greatly simplify the work of creating asynchronous and multi-threaded .NET Framework applications.</span></span>
