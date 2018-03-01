---
title: Sospensione e ripresa di thread
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resuming threads
- threading [.NET Framework], pausing
- pausing threads
ms.assetid: 9fce4859-a19d-4506-b082-7dd0792688ca
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4b87fbb51dbdcd5226a902e8b7ee5aeb7e126b7e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="pausing-and-resuming-threads"></a><span data-ttu-id="45d73-102">Sospensione e ripresa di thread</span><span class="sxs-lookup"><span data-stu-id="45d73-102">Pausing and Resuming Threads</span></span>
<span data-ttu-id="45d73-103">Le tecniche più comuni per sincronizzare le attività dei thread consistono nel blocco e nel rilascio dei thread oppure nel blocco di oggetti o aree di codice.</span><span class="sxs-lookup"><span data-stu-id="45d73-103">The most common ways to synchronize the activities of threads are to block and release threads, or to lock objects or regions of code.</span></span> <span data-ttu-id="45d73-104">Per altre informazioni su questi meccanismi di blocco, vedere [Panoramica delle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="45d73-104">For more information on these locking and blocking mechanisms, see [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="45d73-105">È anche possibile fare in modo che i thread vengano sospesi automaticamente.</span><span class="sxs-lookup"><span data-stu-id="45d73-105">You can also have threads put themselves to sleep.</span></span> <span data-ttu-id="45d73-106">Quando i thread sono bloccati o sospesi, è possibile usare un'eccezione <xref:System.Threading.ThreadInterruptedException> per interromperne lo stato di attesa.</span><span class="sxs-lookup"><span data-stu-id="45d73-106">When threads are blocked or sleeping, you can use a <xref:System.Threading.ThreadInterruptedException> to break them out of their wait states.</span></span>  
  
## <a name="the-threadsleep-method"></a><span data-ttu-id="45d73-107">Metodo Thread.Sleep</span><span class="sxs-lookup"><span data-stu-id="45d73-107">The Thread.Sleep Method</span></span>  
 <span data-ttu-id="45d73-108">Se si chiama il metodo <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>, il thread corrente viene bloccato immediatamente per il numero di millisecondi o l'intervallo di tempo passato al metodo, cedendo il resto della porzione di tempo a un altro thread.</span><span class="sxs-lookup"><span data-stu-id="45d73-108">Calling the <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> method causes the current thread to immediately block for the number of milliseconds or the time interval you pass to the method, and yields the remainder of its time slice to another thread.</span></span> <span data-ttu-id="45d73-109">Una volta trascorso tale intervallo, il thread inattivo riprende l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="45d73-109">Once that interval elapses, the sleeping thread resumes execution.</span></span>  
  
 <span data-ttu-id="45d73-110">Un thread non può chiamare <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> su un altro thread.</span><span class="sxs-lookup"><span data-stu-id="45d73-110">One thread cannot call <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> on another thread.</span></span>  <span data-ttu-id="45d73-111"><xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> è un metodo statico che determina sempre il thread corrente da sospendere.</span><span class="sxs-lookup"><span data-stu-id="45d73-111"><xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is a static method that always causes the current thread to sleep.</span></span>  
  
 <span data-ttu-id="45d73-112">Se si chiama <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> con un valore di <xref:System.Threading.Timeout.Infinite?displayProperty=nameWithType>, un thread rimarrà sospeso finché non verrà interrotto da un altro thread tramite una chiamata al metodo <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> nel thread sospeso o finché non verrà terminato da una chiamata al relativo metodo <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="45d73-112">Calling <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> with a value of <xref:System.Threading.Timeout.Infinite?displayProperty=nameWithType> causes a thread to sleep until it is interrupted by another thread that calls the  <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> method on the sleeping thread, or until it is terminated by a call to its <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method.</span></span>  <span data-ttu-id="45d73-113">L'esempio seguente illustra entrambi i metodi per interrompere un thread inattivo.</span><span class="sxs-lookup"><span data-stu-id="45d73-113">The following example illustrates both methods of interrupting a sleeping thread.</span></span>  
  
 [!code-csharp[Conceptual.Threading.Resuming#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Threading.Resuming/cs/Sleep1.cs#1)]
 [!code-vb[Conceptual.Threading.Resuming#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Threading.Resuming/vb/Sleep1.vb#1)]  
  
## <a name="interrupting-threads"></a><span data-ttu-id="45d73-114">Interruzione di thread</span><span class="sxs-lookup"><span data-stu-id="45d73-114">Interrupting Threads</span></span>  
 <span data-ttu-id="45d73-115">È possibile interrompere un thread in attesa chiamando il metodo <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> sul thread bloccato per generare un'eccezione <xref:System.Threading.ThreadInterruptedException>, che fa uscire il thread dalla chiamata che lo blocca.</span><span class="sxs-lookup"><span data-stu-id="45d73-115">You can interrupt a waiting thread by calling the <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> method on the blocked thread to throw a <xref:System.Threading.ThreadInterruptedException>, which breaks the thread out of the blocking call.</span></span> <span data-ttu-id="45d73-116">Il thread dovrebbe intercettare l'eccezione <xref:System.Threading.ThreadInterruptedException> ed eseguire le operazioni appropriate per continuare a funzionare.</span><span class="sxs-lookup"><span data-stu-id="45d73-116">The thread should catch the <xref:System.Threading.ThreadInterruptedException> and do whatever is appropriate to continue working.</span></span> <span data-ttu-id="45d73-117">Se il thread ignora l'eccezione, l'ambiente di esecuzione la intercetta e interrompe il thread.</span><span class="sxs-lookup"><span data-stu-id="45d73-117">If the thread ignores the exception, the runtime catches the exception and stops the thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45d73-118">Se il thread di destinazione non è bloccato al momento della chiamata del metodo <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>, il thread non subisce interruzioni finché non viene bloccato.</span><span class="sxs-lookup"><span data-stu-id="45d73-118">If the target thread is not blocked when <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> is called, the thread is not interrupted until it blocks.</span></span> <span data-ttu-id="45d73-119">Se il thread non si blocca, verrà completato senza subire alcuna interruzione.</span><span class="sxs-lookup"><span data-stu-id="45d73-119">If the thread never blocks, it could complete without ever being interrupted.</span></span>  
  
 <span data-ttu-id="45d73-120">Se un'attesa è di tipo gestito, sia <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> che <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> riporteranno immediatamente il thread allo stato di attività.</span><span class="sxs-lookup"><span data-stu-id="45d73-120">If a wait is a managed wait, then <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> and <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> both wake the thread immediately.</span></span> <span data-ttu-id="45d73-121">Nel caso di un'attesa non gestita, ad esempio un platform invoke alla funzione Win32 [WaitForSingleObject](https://msdn.microsoft.com/library/windows/desktop/ms687032\(v=vs.85\).aspx), né <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> né <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> potrà assumere il controllo del thread fino alla restituzione o alla chiamata nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="45d73-121">If a wait is an unmanaged wait (for example, a platform invoke call to the Win32 [WaitForSingleObject](https://msdn.microsoft.com/library/windows/desktop/ms687032\(v=vs.85\).aspx) function), neither <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> nor <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> can take control of the thread until it returns to or calls into managed code.</span></span> <span data-ttu-id="45d73-122">Di seguito è descritto il comportamento nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="45d73-122">In managed code, the behavior is as follows:</span></span>  
  
-   <span data-ttu-id="45d73-123"><xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> fa uscire un thread da qualsiasi attesa e genera un'eccezione <xref:System.Threading.ThreadInterruptedException> nel thread di destinazione.</span><span class="sxs-lookup"><span data-stu-id="45d73-123"><xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> wakes a thread out of any wait it might be in and causes a <xref:System.Threading.ThreadInterruptedException> to be thrown in the destination thread.</span></span>  
  
-   <span data-ttu-id="45d73-124"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> fa uscire un thread da qualsiasi attesa e genera un'eccezione <xref:System.Threading.ThreadAbortException> nel thread.</span><span class="sxs-lookup"><span data-stu-id="45d73-124"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> wakes a thread out of any wait it might be in and causes a <xref:System.Threading.ThreadAbortException> to be thrown on the thread.</span></span> <span data-ttu-id="45d73-125">Per informazioni dettagliate, vedere [Eliminazione definitiva di thread](../../../docs/standard/threading/destroying-threads.md).</span><span class="sxs-lookup"><span data-stu-id="45d73-125">For details, see [Destroying Threads](../../../docs/standard/threading/destroying-threads.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45d73-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45d73-126">See Also</span></span>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadInterruptedException>  
 <xref:System.Threading.ThreadAbortException>  
 [<span data-ttu-id="45d73-127">Threading</span><span class="sxs-lookup"><span data-stu-id="45d73-127">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="45d73-128">Utilizzo di thread e threading</span><span class="sxs-lookup"><span data-stu-id="45d73-128">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)  
 [<span data-ttu-id="45d73-129">Panoramica sulle primitive di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="45d73-129">Overview of Synchronization Primitives</span></span>](../../../docs/standard/threading/overview-of-synchronization-primitives.md)
