---
title: 'Procedura: utilizzare SpinLock per la sincronizzazione di basso livello'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinLock, how to use
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 216480e893f6dbebbb204cbf2bfebae8dc139ec4
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2018
ms.locfileid: "45593856"
---
# <a name="how-to-use-spinlock-for-low-level-synchronization"></a><span data-ttu-id="6b949-102">Procedura: utilizzare SpinLock per la sincronizzazione di basso livello</span><span class="sxs-lookup"><span data-stu-id="6b949-102">How to: Use SpinLock for Low-Level Synchronization</span></span>
<span data-ttu-id="6b949-103">L'esempio seguente illustra come usare un oggetto <xref:System.Threading.SpinLock>.</span><span class="sxs-lookup"><span data-stu-id="6b949-103">The following example demonstrates how to use a <xref:System.Threading.SpinLock>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b949-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="6b949-104">Example</span></span>  
 <span data-ttu-id="6b949-105">In questo esempio la sezione critica esegue una quantità minima di lavoro, quindi è ideale per l'uso di <xref:System.Threading.SpinLock>.</span><span class="sxs-lookup"><span data-stu-id="6b949-105">In this example, the critical section performs a minimal amount of work, which makes it a good candidate for a <xref:System.Threading.SpinLock>.</span></span> <span data-ttu-id="6b949-106">Aumentando leggermente il lavoro, aumentano le prestazioni di <xref:System.Threading.SpinLock> rispetto a un blocco standard.</span><span class="sxs-lookup"><span data-stu-id="6b949-106">Increasing the work a small amount increases the performance of the <xref:System.Threading.SpinLock> compared to a standard lock.</span></span> <span data-ttu-id="6b949-107">Tuttavia, esiste un punto in cui uno SpinLock diventa più costoso di un blocco standard.</span><span class="sxs-lookup"><span data-stu-id="6b949-107">However, there is a point at which a SpinLock becomes more expensive than a standard lock.</span></span> <span data-ttu-id="6b949-108">È possibile usare la funzionalità del profilo di concorrenza negli strumenti di profilatura per vedere quale tipo di blocco fornisce prestazioni migliori nel programma.</span><span class="sxs-lookup"><span data-stu-id="6b949-108">You can use the concurrency profiling functionality in the profiling tools to see which type of lock provides better performance in your program.</span></span> <span data-ttu-id="6b949-109">Per altre informazioni, vedere [Visualizzatore di concorrenza](/visualstudio/profiling/concurrency-visualizer).</span><span class="sxs-lookup"><span data-stu-id="6b949-109">For more information, see [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).</span></span>  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 <span data-ttu-id="6b949-110">È possibile usare <xref:System.Threading.SpinLock> quando un blocco su una risorsa condivisa non verrà mantenuto per molto tempo.</span><span class="sxs-lookup"><span data-stu-id="6b949-110"><xref:System.Threading.SpinLock> might be useful when a lock on a shared resource is not going to be held for very long.</span></span> <span data-ttu-id="6b949-111">In questi casi, nei computer multicore può essere efficiente per il thread bloccato l'azione di ruotare per alcuni cicli finché il blocco non viene rilasciato.</span><span class="sxs-lookup"><span data-stu-id="6b949-111">In such cases, on multi-core computers it can be efficient for the blocked thread to spin for a few cycles until the lock is released.</span></span> <span data-ttu-id="6b949-112">Ruotando, il thread non diventa bloccato, che è un processo intensivo della CPU.</span><span class="sxs-lookup"><span data-stu-id="6b949-112">By spinning, the thread does not become blocked, which is a CPU-intensive process.</span></span> <span data-ttu-id="6b949-113"><xref:System.Threading.SpinLock> interrompe la rotazione in determinate condizioni per evitare l'esaurimento dei processori logici o l'inversione di priorità nei sistemi con hyperthreading.</span><span class="sxs-lookup"><span data-stu-id="6b949-113"><xref:System.Threading.SpinLock> will stop spinning under certain conditions to prevent starvation of logical processors or priority inversion on systems with Hyper-Threading.</span></span>  
  
 <span data-ttu-id="6b949-114">Questo esempio usa la classe <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>, che richiede la sincronizzazione utente per l'accesso a thread multipli.</span><span class="sxs-lookup"><span data-stu-id="6b949-114">This example uses the <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> class, which requires user synchronization for multi-threaded access.</span></span> <span data-ttu-id="6b949-115">Nelle applicazioni destinate a .NET Framework versione 4, è anche possibile usare <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, che non richiede alcun blocco dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6b949-115">In applications that target the .NET Framework version 4, another option is to use the <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, which does not require any user locks.</span></span>  
  
 <span data-ttu-id="6b949-116">Si noti l'uso di `false` (`False` in Visual Basic) nella chiamata a <xref:System.Threading.SpinLock.Exit%2A>.</span><span class="sxs-lookup"><span data-stu-id="6b949-116">Note the use of `false` (`False` in Visual Basic) in the call to <xref:System.Threading.SpinLock.Exit%2A>.</span></span> <span data-ttu-id="6b949-117">Questo fornisce prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="6b949-117">This provides the best performance.</span></span> <span data-ttu-id="6b949-118">Specificare `true` (`True`) nelle architetture IA64 per usare il limite di memoria, che scarica il buffer di scrittura per garantire che il blocco sia ora disponibile per l'uscita di altri thread.</span><span class="sxs-lookup"><span data-stu-id="6b949-118">Specify `true` (`True`)on IA64 architectures to use the memory fence, which flushes the write buffers to ensure that the lock is now available for other threads to exit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b949-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b949-119">See also</span></span>

- <span data-ttu-id="6b949-120">[Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) (Oggetti e funzionalità del threading)</span><span class="sxs-lookup"><span data-stu-id="6b949-120">[Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)</span></span>
