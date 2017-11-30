---
title: 'Procedura: utilizzare SpinLock per la sincronizzazione di basso livello'
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
helpviewer_keywords: SpinLock, how to use
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 30ddc7d340b210aaad4a04ea43e89555d2701f20
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-spinlock-for-low-level-synchronization"></a><span data-ttu-id="d1d1d-102">Procedura: utilizzare SpinLock per la sincronizzazione di basso livello</span><span class="sxs-lookup"><span data-stu-id="d1d1d-102">How to: Use SpinLock for Low-Level Synchronization</span></span>
<span data-ttu-id="d1d1d-103">Nell'esempio seguente viene illustrato come utilizzare un <xref:System.Threading.SpinLock>.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-103">The following example demonstrates how to use a <xref:System.Threading.SpinLock>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1d1d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d1d1d-104">Example</span></span>  
 <span data-ttu-id="d1d1d-105">In questo esempio, la sezione critica esegue una quantità minima di lavoro, che rende un ottimo candidato per un <xref:System.Threading.SpinLock>.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-105">In this example, the critical section performs a minimal amount of work, which makes it a good candidate for a <xref:System.Threading.SpinLock>.</span></span> <span data-ttu-id="d1d1d-106">Aumentando il lavoro di una piccola quantità aumenta le prestazioni del <xref:System.Threading.SpinLock> rispetto a un blocco standard.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-106">Increasing the work a small amount increases the performance of the <xref:System.Threading.SpinLock> compared to a standard lock.</span></span> <span data-ttu-id="d1d1d-107">Tuttavia, esiste un punto in cui uno SpinLock diventa più costoso di un blocco standard.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-107">However, there is a point at which a SpinLock becomes more expensive than a standard lock.</span></span> <span data-ttu-id="d1d1d-108">È possibile usare la funzionalità del profilo di concorrenza negli strumenti di profilatura per vedere quale tipo di blocco fornisce prestazioni migliori nel programma.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-108">You can use the concurrency profiling functionality in the profiling tools to see which type of lock provides better performance in your program.</span></span> <span data-ttu-id="d1d1d-109">Per altre informazioni, vedere [Visualizzatore di concorrenza](/visualstudio/profiling/concurrency-visualizer).</span><span class="sxs-lookup"><span data-stu-id="d1d1d-109">For more information, see [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).</span></span>  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 <span data-ttu-id="d1d1d-110"><xref:System.Threading.SpinLock>potrebbe essere utile quando un blocco su una risorsa condivisa non viene mantenuto per molto tempo.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-110"><xref:System.Threading.SpinLock> might be useful when a lock on a shared resource is not going to be held for very long.</span></span> <span data-ttu-id="d1d1d-111">In questi casi, nei computer multicore può essere efficiente per il thread bloccato l'azione di ruotare per alcuni cicli finché il blocco non viene rilasciato.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-111">In such cases, on multi-core computers it can be efficient for the blocked thread to spin for a few cycles until the lock is released.</span></span> <span data-ttu-id="d1d1d-112">Ruotando, il thread non diventa bloccato, che è un processo intensivo della CPU.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-112">By spinning, the thread does not become blocked, which is a CPU-intensive process.</span></span> <span data-ttu-id="d1d1d-113"><xref:System.Threading.SpinLock>interromperà lo spin in determinate condizioni per evitare l'esaurimento dei processori logici o di inversione di priorità nei sistemi con Hyper-Threading.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-113"><xref:System.Threading.SpinLock> will stop spinning under certain conditions to prevent starvation of logical processors or priority inversion on systems with Hyper-Threading.</span></span>  
  
 <span data-ttu-id="d1d1d-114">Questo esempio viene utilizzato il <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> (classe), che richiede la sincronizzazione di utente per l'accesso a thread multipli.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-114">This example uses the <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> class, which requires user synchronization for multi-threaded access.</span></span> <span data-ttu-id="d1d1d-115">Nelle applicazioni destinate a .NET Framework versione 4, un'altra opzione consiste nell'utilizzare il <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, che non richiede alcun blocco dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-115">In applications that target the .NET Framework version 4, another option is to use the <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, which does not require any user locks.</span></span>  
  
 <span data-ttu-id="d1d1d-116">Si noti l'uso di `false` (`False` in Visual Basic) nella chiamata a <xref:System.Threading.SpinLock.Exit%2A>.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-116">Note the use of `false` (`False` in Visual Basic) in the call to <xref:System.Threading.SpinLock.Exit%2A>.</span></span> <span data-ttu-id="d1d1d-117">Questo fornisce prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-117">This provides the best performance.</span></span> <span data-ttu-id="d1d1d-118">Specificare `true` (`True`) nelle architetture IA64 per usare il limite di memoria, che scarica il buffer di scrittura per garantire che il blocco sia ora disponibile per l'uscita di altri thread.</span><span class="sxs-lookup"><span data-stu-id="d1d1d-118">Specify `true` (`True`)on IA64 architectures to use the memory fence, which flushes the write buffers to ensure that the lock is now available for other threads to exit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1d1d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1d1d-119">See Also</span></span>  
 [<span data-ttu-id="d1d1d-120">Oggetti e funzionalità del threading</span><span class="sxs-lookup"><span data-stu-id="d1d1d-120">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
