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
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b146987d2491f044e1f5794eba17d02d8f5e478c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="pausing-and-resuming-threads"></a><span data-ttu-id="3fc42-102">Sospensione e ripresa di thread</span><span class="sxs-lookup"><span data-stu-id="3fc42-102">Pausing and Resuming Threads</span></span>
<span data-ttu-id="3fc42-103">Le tecniche più comuni per sincronizzare le attività dei thread consistono nel blocco e nel rilascio dei thread oppure nel blocco di oggetti o aree di codice.</span><span class="sxs-lookup"><span data-stu-id="3fc42-103">The most common ways to synchronize the activities of threads are to block and release threads, or to lock objects or regions of code.</span></span> <span data-ttu-id="3fc42-104">Per altre informazioni su questi meccanismi di blocco, vedere [Panoramica delle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="3fc42-104">For more information on these locking and blocking mechanisms, see [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="3fc42-105">È anche possibile fare in modo che i thread vengano sospesi automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3fc42-105">You can also have threads put themselves to sleep.</span></span> <span data-ttu-id="3fc42-106">Quando i thread sono bloccati o sospesi, è possibile usare un'eccezione <xref:System.Threading.ThreadInterruptedException> per interromperne lo stato di attesa.</span><span class="sxs-lookup"><span data-stu-id="3fc42-106">When threads are blocked or sleeping, you can use a <xref:System.Threading.ThreadInterruptedException> to break them out of their wait states.</span></span>  
  
## <a name="the-threadsleep-method"></a><span data-ttu-id="3fc42-107">Metodo Thread.Sleep</span><span class="sxs-lookup"><span data-stu-id="3fc42-107">The Thread.Sleep Method</span></span>  
 <span data-ttu-id="3fc42-108">La chiamata di <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> (metodo), il thread corrente viene bloccato immediatamente per il numero di millisecondi o l'intervallo di tempo passare al metodo e restituisce il resto della porzione di tempo a un altro thread.</span><span class="sxs-lookup"><span data-stu-id="3fc42-108">Calling the <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> method causes the current thread to immediately block for the number of milliseconds or the time interval you pass to the method, and yields the remainder of its time slice to another thread.</span></span> <span data-ttu-id="3fc42-109">Una volta trascorso tale intervallo, il thread inattivo riprende l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3fc42-109">Once that interval elapses, the sleeping thread resumes execution.</span></span>  
  
 <span data-ttu-id="3fc42-110">Un thread non può chiamare <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> su un altro thread.</span><span class="sxs-lookup"><span data-stu-id="3fc42-110">One thread cannot call <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> on another thread.</span></span>  <span data-ttu-id="3fc42-111"><xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>è un metodo statico che determinano sempre il thread corrente allo stato di sospensione.</span><span class="sxs-lookup"><span data-stu-id="3fc42-111"><xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is a static method that always causes the current thread to sleep.</span></span>  
  
 <span data-ttu-id="3fc42-112">La chiamata <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> con un valore di <xref:System.Threading.Timeout.Infinite?displayProperty=nameWithType> fa sì che un thread rimarrà sospeso finché verrà interrotto da un altro thread che chiama il <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> metodo sul thread inattivo o fino a quando non viene terminata da una chiamata al relativo <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="3fc42-112">Calling <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> with a value of <xref:System.Threading.Timeout.Infinite?displayProperty=nameWithType> causes a thread to sleep until it is interrupted by another thread that calls the  <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> method on the sleeping thread, or until it is terminated by a call to its <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method.</span></span>  <span data-ttu-id="3fc42-113">L'esempio seguente illustra entrambi i metodi per interrompere un thread inattivo.</span><span class="sxs-lookup"><span data-stu-id="3fc42-113">The following example illustrates both methods of interrupting a sleeping thread.</span></span>  
  
 [!code-csharp[Conceptual.Threading.Resuming#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Threading.Resuming/cs/Sleep1.cs#1)]
 [!code-vb[Conceptual.Threading.Resuming#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Threading.Resuming/vb/Sleep1.vb#1)]  
  
## <a name="interrupting-threads"></a><span data-ttu-id="3fc42-114">Interruzione di thread</span><span class="sxs-lookup"><span data-stu-id="3fc42-114">Interrupting Threads</span></span>  
 <span data-ttu-id="3fc42-115">È possibile interrompere un thread in attesa chiamando il <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> metodo sul thread bloccato per generare un <xref:System.Threading.ThreadInterruptedException>, che interrompe il thread di chiamata di blocco.</span><span class="sxs-lookup"><span data-stu-id="3fc42-115">You can interrupt a waiting thread by calling the <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> method on the blocked thread to throw a <xref:System.Threading.ThreadInterruptedException>, which breaks the thread out of the blocking call.</span></span> <span data-ttu-id="3fc42-116">Il thread dovrebbe intercettare l'eccezione <xref:System.Threading.ThreadInterruptedException> ed eseguire le operazioni appropriate per continuare a funzionare.</span><span class="sxs-lookup"><span data-stu-id="3fc42-116">The thread should catch the <xref:System.Threading.ThreadInterruptedException> and do whatever is appropriate to continue working.</span></span> <span data-ttu-id="3fc42-117">Se il thread ignora l'eccezione, l'ambiente di esecuzione la intercetta e interrompe il thread.</span><span class="sxs-lookup"><span data-stu-id="3fc42-117">If the thread ignores the exception, the runtime catches the exception and stops the thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fc42-118">Se il thread di destinazione non è bloccato al momento della chiamata del metodo <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>, il thread non subisce interruzioni finché non viene bloccato.</span><span class="sxs-lookup"><span data-stu-id="3fc42-118">If the target thread is not blocked when <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> is called, the thread is not interrupted until it blocks.</span></span> <span data-ttu-id="3fc42-119">Se il thread non si blocca, verrà completato senza subire alcuna interruzione.</span><span class="sxs-lookup"><span data-stu-id="3fc42-119">If the thread never blocks, it could complete without ever being interrupted.</span></span>  
  
 <span data-ttu-id="3fc42-120">Se un'attesa è di tipo gestito, sia <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> che <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> riporteranno immediatamente il thread allo stato di attività.</span><span class="sxs-lookup"><span data-stu-id="3fc42-120">If a wait is a managed wait, then <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> and <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> both wake the thread immediately.</span></span> <span data-ttu-id="3fc42-121">Caso di un'attesa non gestita (ad esempio, una chiamata PInvoke per Win32 [WaitForSingleObject](https://msdn.microsoft.com/library/windows/desktop/ms687032\(v=vs.85\).aspx) funzione), né <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> né <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> può assumere il controllo del thread fino alla restituzione o alla chiamata nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="3fc42-121">If a wait is an unmanaged wait (for example, a platform invoke call to the Win32 [WaitForSingleObject](https://msdn.microsoft.com/library/windows/desktop/ms687032\(v=vs.85\).aspx) function), neither <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> nor <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> can take control of the thread until it returns to or calls into managed code.</span></span> <span data-ttu-id="3fc42-122">Di seguito è descritto il comportamento nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="3fc42-122">In managed code, the behavior is as follows:</span></span>  
  
-   <span data-ttu-id="3fc42-123"><xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> fa uscire un thread da qualsiasi attesa e genera un'eccezione <xref:System.Threading.ThreadInterruptedException> nel thread di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3fc42-123"><xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> wakes a thread out of any wait it might be in and causes a <xref:System.Threading.ThreadInterruptedException> to be thrown in the destination thread.</span></span>  
  
-   <span data-ttu-id="3fc42-124"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>riattivazione di un thread qualsiasi attesa e provoca un <xref:System.Threading.ThreadAbortException> generata sul thread.</span><span class="sxs-lookup"><span data-stu-id="3fc42-124"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> wakes a thread out of any wait it might be in and causes a <xref:System.Threading.ThreadAbortException> to be thrown on the thread.</span></span> <span data-ttu-id="3fc42-125">Per informazioni dettagliate, vedere [Eliminazione definitiva di thread](../../../docs/standard/threading/destroying-threads.md).</span><span class="sxs-lookup"><span data-stu-id="3fc42-125">For details, see [Destroying Threads](../../../docs/standard/threading/destroying-threads.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fc42-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fc42-126">See Also</span></span>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadInterruptedException>  
 <xref:System.Threading.ThreadAbortException>  
 [<span data-ttu-id="3fc42-127">Threading</span><span class="sxs-lookup"><span data-stu-id="3fc42-127">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="3fc42-128">Utilizzo di thread e threading</span><span class="sxs-lookup"><span data-stu-id="3fc42-128">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)  
 [<span data-ttu-id="3fc42-129">Cenni preliminari sulle primitive di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="3fc42-129">Overview of Synchronization Primitives</span></span>](../../../docs/standard/threading/overview-of-synchronization-primitives.md)
