---
title: Oggetti e funzionalità del threading
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d689aeb91ad79b776c3b93c1809ec46947ea60b
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874787"
---
# <a name="threading-objects-and-features"></a><span data-ttu-id="f56cb-102">Oggetti e funzionalità del threading</span><span class="sxs-lookup"><span data-stu-id="f56cb-102">Threading Objects and Features</span></span>
<span data-ttu-id="f56cb-103">.NET Framework fornisce numerosi oggetti che consentono di creare e gestire applicazioni multithread.</span><span class="sxs-lookup"><span data-stu-id="f56cb-103">The .NET Framework provides a number of objects that help you create and manage multithreaded applications.</span></span> <span data-ttu-id="f56cb-104">I thread gestiti sono rappresentati dalla classe <xref:System.Threading.Thread>.</span><span class="sxs-lookup"><span data-stu-id="f56cb-104">Managed threads are represented by the <xref:System.Threading.Thread> class.</span></span> <span data-ttu-id="f56cb-105">La classe <xref:System.Threading.ThreadPool> consente di creare e gestire facilmente attività multithreading in background.</span><span class="sxs-lookup"><span data-stu-id="f56cb-105">The <xref:System.Threading.ThreadPool> class provides easy creation and management of multithreaded background tasks.</span></span> <span data-ttu-id="f56cb-106">La classe <xref:System.ComponentModel.BackgroundWorker> ha la stessa funzione per le attività che interagiscono con l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="f56cb-106">The <xref:System.ComponentModel.BackgroundWorker> class does the same for tasks that interact with the user interface.</span></span> <span data-ttu-id="f56cb-107">La classe <xref:System.Threading.Timer> esegue attività in background a intervalli fissi.</span><span class="sxs-lookup"><span data-stu-id="f56cb-107">The <xref:System.Threading.Timer> class executes background tasks at timed intervals.</span></span>  
  
 <span data-ttu-id="f56cb-108">Esistono anche numerose classi che sincronizzano le attività dei thread, tra cui le classi <xref:System.Threading.Semaphore> e <xref:System.Threading.EventWaitHandle> introdotte in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="f56cb-108">In addition, there are a number of classes that synchronize activities of threads, including the <xref:System.Threading.Semaphore> and <xref:System.Threading.EventWaitHandle> classes introduced in the .NET Framework version 2.0.</span></span> <span data-ttu-id="f56cb-109">Le funzionalità di queste classi sono messe a confronto nella [panoramica sulle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="f56cb-109">The features of these classes are compared in [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f56cb-110">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="f56cb-110">In This Section</span></span>  
 [<span data-ttu-id="f56cb-111">Pool di thread gestiti</span><span class="sxs-lookup"><span data-stu-id="f56cb-111">The Managed Thread Pool</span></span>](../../../docs/standard/threading/the-managed-thread-pool.md)  
 <span data-ttu-id="f56cb-112">Illustra la classe **ThreadPool**, che consente di richiedere un thread per eseguire un'attività senza dover gestire manualmente il thread.</span><span class="sxs-lookup"><span data-stu-id="f56cb-112">Explains the **ThreadPool** class, which enables you to request a thread to execute a task without having to do any thread management yourself.</span></span>  
  
 [<span data-ttu-id="f56cb-113">Timer</span><span class="sxs-lookup"><span data-stu-id="f56cb-113">Timers</span></span>](../../../docs/standard/threading/timers.md)  
 <span data-ttu-id="f56cb-114">Descrive i timer che possono essere usati in un ambiente multithreading.</span><span class="sxs-lookup"><span data-stu-id="f56cb-114">Describes timers that can be used in a multithreaded environment.</span></span>  
  
 [<span data-ttu-id="f56cb-115">Monitoraggi</span><span class="sxs-lookup"><span data-stu-id="f56cb-115">Monitors</span></span>](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)  
 <span data-ttu-id="f56cb-116">Illustra come usare la classe **Monitor** per sincronizzare l'accesso a un membro o per creare i propri tipi di gestione dei thread.</span><span class="sxs-lookup"><span data-stu-id="f56cb-116">Explains how to use the **Monitor** class to synchronize access to a member or to build your own thread management types.</span></span>  
  
 [<span data-ttu-id="f56cb-117">Handle di attesa</span><span class="sxs-lookup"><span data-stu-id="f56cb-117">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 <span data-ttu-id="f56cb-118">Descrive la classe <xref:System.Threading.WaitHandle>, la classe base astratta per gli handle di attesa eventi, i mutex e i semafori, che consente di attendere più eventi di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="f56cb-118">Describes the <xref:System.Threading.WaitHandle> class, the abstract base class for event wait handles, mutexes, and semaphores, which enables waiting for multiple synchronization events.</span></span>  
  
 [<span data-ttu-id="f56cb-119">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="f56cb-119">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 <span data-ttu-id="f56cb-120">Descrive gli handle di attesa eventi gestiti, usati per sincronizzare le attività dei thread effettuando segnalazioni e attendendo segnali.</span><span class="sxs-lookup"><span data-stu-id="f56cb-120">Describes managed event wait handles, which are used to synchronize thread activities by signaling and waiting for signals.</span></span>  
  
 [<span data-ttu-id="f56cb-121">Mutex</span><span class="sxs-lookup"><span data-stu-id="f56cb-121">Mutexes</span></span>](../../../docs/standard/threading/mutexes.md)  
 <span data-ttu-id="f56cb-122">Illustra come usare un <xref:System.Threading.Mutex> per sincronizzare l'accesso a un oggetto o creare i propri meccanismi di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="f56cb-122">Explains how to use a <xref:System.Threading.Mutex> to synchronize access to an object or to build your own synchronization mechanisms.</span></span>  
  
 [<span data-ttu-id="f56cb-123">Operazioni interlocked</span><span class="sxs-lookup"><span data-stu-id="f56cb-123">Interlocked Operations</span></span>](../../../docs/standard/threading/interlocked-operations.md)  
 <span data-ttu-id="f56cb-124">Illustra come usare la classe <xref:System.Threading.Interlocked> per incrementare o decrementare un valore e archiviarlo in una sola operazione atomica.</span><span class="sxs-lookup"><span data-stu-id="f56cb-124">Explains how to use the <xref:System.Threading.Interlocked> class to increment or decrement a value and store the value in a single atomic operation.</span></span>  
  
 [<span data-ttu-id="f56cb-125">Blocchi in lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="f56cb-125">Reader-Writer Locks</span></span>](../../../docs/standard/threading/reader-writer-locks.md)  
 <span data-ttu-id="f56cb-126">Definisce un blocco che implementa la semantica writer singolo/visualizzatori multipli.</span><span class="sxs-lookup"><span data-stu-id="f56cb-126">Defines a lock that implements single-writer/multiple-reader semantics.</span></span>  
  
 [<span data-ttu-id="f56cb-127">Semaphore e SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="f56cb-127">Semaphore and SemaphoreSlim</span></span>](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)  
 <span data-ttu-id="f56cb-128">Descrive gli oggetti <xref:System.Threading.Semaphore> e illustra come usarli per controllare l'accesso alle risorse limitate.</span><span class="sxs-lookup"><span data-stu-id="f56cb-128">Describes <xref:System.Threading.Semaphore> objects and explains how to use them to control access to limited resources.</span></span>  
  
 [<span data-ttu-id="f56cb-129">Panoramica sulle primitive di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="f56cb-129">Overview of Synchronization Primitives</span></span>](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 <span data-ttu-id="f56cb-130">Confronta le funzionalità delle classi di .NET Framework fornite per bloccare e sincronizzare i thread gestiti.</span><span class="sxs-lookup"><span data-stu-id="f56cb-130">Compares the features of the .NET Framework classes provided for locking and synchronizing managed threads.</span></span>  
  
 [<span data-ttu-id="f56cb-131">Barrier</span><span class="sxs-lookup"><span data-stu-id="f56cb-131">Barrier</span></span>](../../../docs/standard/threading/barrier.md)  
 <span data-ttu-id="f56cb-132">Descrive gli oggetti <xref:System.Threading.Barrier> che implementano lo schema della barriera per il coordinamento dei thread nelle operazioni in più fasi.</span><span class="sxs-lookup"><span data-stu-id="f56cb-132">Describes <xref:System.Threading.Barrier> objects that implement the barrier pattern for coordination of threads in phased operations.</span></span>  
  
 [<span data-ttu-id="f56cb-133">SpinLock</span><span class="sxs-lookup"><span data-stu-id="f56cb-133">SpinLock</span></span>](../../../docs/standard/threading/spinlock.md)  
 <span data-ttu-id="f56cb-134">Descrive <xref:System.Threading.SpinLock>, una semplice alternativa alla classe Monitor per alcuni scenari di basso livello.</span><span class="sxs-lookup"><span data-stu-id="f56cb-134">Describes <xref:System.Threading.SpinLock>, a lightweight alternative to the Monitor class for certain low-level scenarios.</span></span>  
  
 [<span data-ttu-id="f56cb-135">SpinWait</span><span class="sxs-lookup"><span data-stu-id="f56cb-135">SpinWait</span></span>](../../../docs/standard/threading/spinwait.md)  
 <span data-ttu-id="f56cb-136">Descrive <xref:System.Threading.SpinWait>, una primitiva di sincronizzazione di basso livello che esegue la rotazione con stato occupato prima di iniziare un'attesa basata sul kernel.</span><span class="sxs-lookup"><span data-stu-id="f56cb-136">Describes <xref:System.Threading.SpinWait>, a low level synchronization primitive that performs busy spinning prior to initiating a kernel-based wait.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f56cb-137">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="f56cb-137">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="f56cb-138">Rende disponibile la documentazione di riferimento per la classe **Thread**, che rappresenta un thread gestito, indipendentemente dal fatto che derivi da codice non gestito o sia stato creato in un'applicazione gestita.</span><span class="sxs-lookup"><span data-stu-id="f56cb-138">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="f56cb-139">Consente le attività in background che interagiscono con l'interfaccia utente, comunicando tramite gli eventi generati nel thread di interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="f56cb-139">Enables background tasks that interact with the user interface, communicating via events raised on the user-interface thread.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f56cb-140">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="f56cb-140">Related Sections</span></span>  
 [<span data-ttu-id="f56cb-141">I/O di file asincrono</span><span class="sxs-lookup"><span data-stu-id="f56cb-141">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 <span data-ttu-id="f56cb-142">Descrive come le porte di completamento asincrono di I/O usano il pool di thread per richiedere l'elaborazione solo quando un'operazione di input/output viene completata.</span><span class="sxs-lookup"><span data-stu-id="f56cb-142">Describes how I/O asynchronous completion ports use the thread pool to require processing only when an input/output operation completes.</span></span>  
  
 [<span data-ttu-id="f56cb-143">Task Parallel Library (TPL)</span><span class="sxs-lookup"><span data-stu-id="f56cb-143">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="f56cb-144">Descrive l'approccio consigliato per la programmazione multithreading in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="f56cb-144">Describes the recommended approach for multithreaded programming in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] and later.</span></span>
