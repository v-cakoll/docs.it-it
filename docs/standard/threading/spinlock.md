---
title: SpinLock
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: synchronization primitives, SpinLock
ms.assetid: f9af93bb-7a0d-4ba5-afe8-74f48b6b6958
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: efe9b3126b3c952ab156f9ca40752ad8d3fddcd1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="spinlock"></a><span data-ttu-id="4d4f0-102">SpinLock</span><span class="sxs-lookup"><span data-stu-id="4d4f0-102">SpinLock</span></span>
<span data-ttu-id="4d4f0-103">Il <xref:System.Threading.SpinLock> struttura è una primitiva di sincronizzazione di basso livello a esclusione reciproca che ruota in attesa di acquisire un blocco.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-103">The <xref:System.Threading.SpinLock> structure is a low-level, mutual-exclusion synchronization primitive that spins while it waits to acquire a lock.</span></span> <span data-ttu-id="4d4f0-104">Nei computer multicore, quando prevede tempi di attesa sono brevi e il conflitto è minimo, <xref:System.Threading.SpinLock> può risultare più efficace rispetto ad altri tipi di blocchi.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-104">On multicore computers, when wait times are expected to be short and when contention is minimal, <xref:System.Threading.SpinLock> can perform better than other kinds of locks.</span></span> <span data-ttu-id="4d4f0-105">Tuttavia, è consigliabile utilizzare <xref:System.Threading.SpinLock> solo quando è determinare il profilo di <xref:System.Threading.Monitor?displayProperty=nameWithType> (metodo) o <xref:System.Threading.Interlocked> metodi rallentano in modo significativo le prestazioni del programma.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-105">However, we recommend that you use <xref:System.Threading.SpinLock> only when you determine by profiling that the <xref:System.Threading.Monitor?displayProperty=nameWithType> method or the <xref:System.Threading.Interlocked> methods are significantly slowing the performance of your program.</span></span>  
  
 <span data-ttu-id="4d4f0-106"><xref:System.Threading.SpinLock>può produrre l'intervallo di tempo del thread, anche se non ha ancora acquisito il blocco.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-106"><xref:System.Threading.SpinLock> may yield the time slice of the thread even if it has not yet acquired the lock.</span></span> <span data-ttu-id="4d4f0-107">Ciò avviene per evitare l'inversione di priorità di thread e per consentire al garbage collector di avanzamento del lavoro.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-107">It does this to avoid thread-priority inversion, and to enable the garbage collector to make progress.</span></span> <span data-ttu-id="4d4f0-108">Quando si utilizza un <xref:System.Threading.SpinLock>, verificare che nessun thread può contenere il blocco per più di un intervallo di tempo molto breve, e che nessun thread può restare bloccata mentre mantiene il blocco.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-108">When you use a <xref:System.Threading.SpinLock>, ensure that no thread can hold the lock for more than a very brief time span, and that no thread can block while it holds the lock.</span></span>  
  
 <span data-ttu-id="4d4f0-109">Poiché SpinLock è un tipo valore, è necessario passarlo in modo esplicito per riferimento se si prevede due copie per fare riferimento allo stesso blocco.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-109">Because SpinLock is a value type, you must explicitly pass it by reference if you intend the two copies to refer to the same lock.</span></span>  
  
 <span data-ttu-id="4d4f0-110">Per ulteriori informazioni sull'utilizzo di questo tipo, vedere <xref:System.Threading.SpinLock?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-110">For more information about how to use this type, see <xref:System.Threading.SpinLock?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4d4f0-111">Per un esempio, vedere [procedura: utilizzare SpinLock per la sincronizzazione di basso livello](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="4d4f0-111">For an example, see [How to: Use SpinLock for Low-Level Synchronization](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).</span></span>  
  
 <span data-ttu-id="4d4f0-112"><xref:System.Threading.SpinLock>supporta un *thread*-*rilevamento* modalità da utilizzare durante la fase di sviluppo per rilevare il thread che contiene il blocco in un momento specifico.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-112"><xref:System.Threading.SpinLock> supports a *thread*-*tracking* mode that you can use during the development phase to help track the thread that is holding the lock at a specific time.</span></span> <span data-ttu-id="4d4f0-113">Modalità di rilevamento thread è molto utile per il debug, ma si consiglia di disattivare nella versione di rilascio del programma in quanto può ridurre le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-113">Thread-tracking mode is very useful for debugging, but we recommend that you turn it off in the release version of your program because it may slow performance.</span></span> <span data-ttu-id="4d4f0-114">Per ulteriori informazioni, vedere [come: la modalità di rilevamento abilitare Thread in SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).</span><span class="sxs-lookup"><span data-stu-id="4d4f0-114">For more information, see [How to: Enable Thread-Tracking Mode in SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d4f0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d4f0-115">See Also</span></span>  
 [<span data-ttu-id="4d4f0-116">Oggetti e funzionalità del threading</span><span class="sxs-lookup"><span data-stu-id="4d4f0-116">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
