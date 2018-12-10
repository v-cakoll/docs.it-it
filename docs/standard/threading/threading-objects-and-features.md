---
title: Oggetti e funzionalità del threading
ms.date: 10/01/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a355c2e996ddb00dad804dfeb22987923d91aa6
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144520"
---
# <a name="threading-objects-and-features"></a><span data-ttu-id="16cd1-102">Oggetti e funzionalità del threading</span><span class="sxs-lookup"><span data-stu-id="16cd1-102">Threading objects and features</span></span>

<span data-ttu-id="16cd1-103">Oltre alla classe <xref:System.Threading.Thread?displayProperty=nameWithType>, .NET offre diverse classi utili per lo sviluppo di applicazioni multithreading.</span><span class="sxs-lookup"><span data-stu-id="16cd1-103">Along with the <xref:System.Threading.Thread?displayProperty=nameWithType> class, .NET provides a number of classes that help you develop multithreaded applications.</span></span> <span data-ttu-id="16cd1-104">Gli articoli seguenti offrono una panoramica di queste classi:</span><span class="sxs-lookup"><span data-stu-id="16cd1-104">The following articles provide overview of those classes:</span></span>

|<span data-ttu-id="16cd1-105">Titolo</span><span class="sxs-lookup"><span data-stu-id="16cd1-105">Title</span></span>|<span data-ttu-id="16cd1-106">Description</span><span class="sxs-lookup"><span data-stu-id="16cd1-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="16cd1-107">Pool di thread gestiti</span><span class="sxs-lookup"><span data-stu-id="16cd1-107">The managed thread pool</span></span>](the-managed-thread-pool.md)|<span data-ttu-id="16cd1-108">Descrive la classe <xref:System.Threading.ThreadPool?displayProperty=nameWithType> che offre un pool di thread di lavoro gestiti da .NET.</span><span class="sxs-lookup"><span data-stu-id="16cd1-108">Describes the <xref:System.Threading.ThreadPool?displayProperty=nameWithType> class, which provides a pool of worker threads that are managed by .NET.</span></span>|  
|[<span data-ttu-id="16cd1-109">Timer</span><span class="sxs-lookup"><span data-stu-id="16cd1-109">Timers</span></span>](timers.md)|<span data-ttu-id="16cd1-110">Descrive i timer .NET che possono essere usati in un ambiente con multithreading.</span><span class="sxs-lookup"><span data-stu-id="16cd1-110">Describes .NET timers that can be used in a multithreaded environment.</span></span>|
|[<span data-ttu-id="16cd1-111">Cenni preliminari sulle primitive di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="16cd1-111">Overview of synchronization primitives</span></span>](overview-of-synchronization-primitives.md)|<span data-ttu-id="16cd1-112">Descrive i tipi che possono essere usati per sincronizzare l'accesso a una risorsa condivisa o controllare l'interazione tra thread.</span><span class="sxs-lookup"><span data-stu-id="16cd1-112">Describes types that can be used to synchronize access to a shared resource or control thread interaction.</span></span>|
|[<span data-ttu-id="16cd1-113">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="16cd1-113">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)|<span data-ttu-id="16cd1-114">Descrive gli handle di attesa eventi gestiti, usati per sincronizzare le attività dei thread effettuando segnalazioni e attendendo segnali.</span><span class="sxs-lookup"><span data-stu-id="16cd1-114">Describes managed event wait handles, which are used to synchronize thread activities by signaling and waiting for signals.</span></span>|
|[<span data-ttu-id="16cd1-115">Mutex</span><span class="sxs-lookup"><span data-stu-id="16cd1-115">Mutexes</span></span>](mutexes.md)|<span data-ttu-id="16cd1-116">Descrive <xref:System.Threading.Mutex?displayProperty=nameWithType>, che concede l'accesso esclusivo a una risorsa condivisa.</span><span class="sxs-lookup"><span data-stu-id="16cd1-116">Describes <xref:System.Threading.Mutex?displayProperty=nameWithType>, which grants exclusive access to a shared resource.</span></span>|
|[<span data-ttu-id="16cd1-117">Semaphore e SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="16cd1-117">Semaphore and SemaphoreSlim</span></span>](semaphore-and-semaphoreslim.md)|<span data-ttu-id="16cd1-118">Descrive la classe <xref:System.Threading.Semaphore?displayProperty=nameWithType>, che limita il numero di thread che possono accedere simultaneamente a una risorsa condivisa o a un pool di risorse.</span><span class="sxs-lookup"><span data-stu-id="16cd1-118">Describes the <xref:System.Threading.Semaphore?displayProperty=nameWithType> class, which limits number of threads that can access a shared resource or a pool of resources concurrently.</span></span>|
|[<span data-ttu-id="16cd1-119">Barrier</span><span class="sxs-lookup"><span data-stu-id="16cd1-119">Barrier</span></span>](barrier.md)|<span data-ttu-id="16cd1-120">Descrive la classe <xref:System.Threading.Barrier?displayProperty=nameWithType> che implementa lo schema della barriera per il coordinamento dei thread nelle operazioni in più fasi.</span><span class="sxs-lookup"><span data-stu-id="16cd1-120">Describes the <xref:System.Threading.Barrier?displayProperty=nameWithType> class that implements the barrier pattern for coordination of threads in phased operations.</span></span>|
|[<span data-ttu-id="16cd1-121">SpinLock</span><span class="sxs-lookup"><span data-stu-id="16cd1-121">SpinLock</span></span>](spinlock.md)|<span data-ttu-id="16cd1-122">Descrive la struttura <xref:System.Threading.SpinLock?displayProperty=nameWithType>, che rappresenta un'alternativa leggera alla classe <xref:System.Threading.Monitor?displayProperty=nameWithType> per alcuni scenari di blocco di basso livello.</span><span class="sxs-lookup"><span data-stu-id="16cd1-122">Describes the <xref:System.Threading.SpinLock?displayProperty=nameWithType> structure, which is a lightweight alternative to the <xref:System.Threading.Monitor?displayProperty=nameWithType> class for certain low-level locking scenarios.</span></span>|
|[<span data-ttu-id="16cd1-123">SpinWait</span><span class="sxs-lookup"><span data-stu-id="16cd1-123">SpinWait</span></span>](spinwait.md)|<span data-ttu-id="16cd1-124">Descrive la struttura <xref:System.Threading.SpinWait?displayProperty=nameWithType>, che fornisce supporto per l'attesa basata su rotazione.</span><span class="sxs-lookup"><span data-stu-id="16cd1-124">Describes the <xref:System.Threading.SpinWait?displayProperty=nameWithType> structure, which provides support for spin-based waiting.</span></span>|

## <a name="see-also"></a><span data-ttu-id="16cd1-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16cd1-125">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- [<span data-ttu-id="16cd1-126">Utilizzo di thread e threading</span><span class="sxs-lookup"><span data-stu-id="16cd1-126">Using threads and threading</span></span>](using-threads-and-threading.md)
- [<span data-ttu-id="16cd1-127">Asynchronous File I/O</span><span class="sxs-lookup"><span data-stu-id="16cd1-127">Asynchronous File I/O</span></span>](../io/asynchronous-file-i-o.md)
- [<span data-ttu-id="16cd1-128">Programmazione parallela</span><span class="sxs-lookup"><span data-stu-id="16cd1-128">Parallel Programming</span></span>](../parallel-programming/index.md)
- [<span data-ttu-id="16cd1-129">Task Parallel Library (TPL)</span><span class="sxs-lookup"><span data-stu-id="16cd1-129">Task Parallel Library (TPL)</span></span>](../parallel-programming/task-parallel-library-tpl.md)
