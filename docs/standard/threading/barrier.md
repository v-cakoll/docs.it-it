---
title: Barriera (.NET Framework)
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, Barrier
ms.assetid: 613a8bc7-6a28-4795-bd6c-1abd9050478f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 385e370f205851630f809b285a93c2609220efeb
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44274768"
---
# <a name="barrier-net-framework"></a><span data-ttu-id="3fc65-102">Barriera (.NET Framework)</span><span class="sxs-lookup"><span data-stu-id="3fc65-102">Barrier (.NET Framework)</span></span>
<span data-ttu-id="3fc65-103">Una *barriera* è una primitiva di sincronizzazione definita dall'utente che permette a più thread (noti come *partecipanti*) di lavorare contemporaneamente su un algoritmo in fasi diverse.</span><span class="sxs-lookup"><span data-stu-id="3fc65-103">A *barrier* is a user-defined synchronization primitive that enables multiple threads (known as *participants*) to work concurrently on an algorithm in phases.</span></span> <span data-ttu-id="3fc65-104">Ogni partecipante viene eseguito fino al raggiungimento del punto barriera nel codice.</span><span class="sxs-lookup"><span data-stu-id="3fc65-104">Each participant executes until it reaches the barrier point in the code.</span></span> <span data-ttu-id="3fc65-105">La barriera rappresenta la fine di una fase di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3fc65-105">The barrier represents the end of one phase of work.</span></span> <span data-ttu-id="3fc65-106">Quando un partecipante raggiunge la barriera, si blocca fino al raggiungimento della stessa barriera da parte di tutti i partecipanti.</span><span class="sxs-lookup"><span data-stu-id="3fc65-106">When a participant reaches the barrier, it blocks until all participants have reached the same barrier.</span></span> <span data-ttu-id="3fc65-107">Dopo che tutti i partecipanti hanno raggiunto la barriera, è possibile richiamare facoltativamente un'azione post- fase.</span><span class="sxs-lookup"><span data-stu-id="3fc65-107">After all participants have reached the barrier, you can optionally invoke a post-phase action.</span></span> <span data-ttu-id="3fc65-108">Questa azione post- fase può essere usata per eseguire azioni da parte di un singolo thread mentre tutti gli altri thread rimangono bloccati.</span><span class="sxs-lookup"><span data-stu-id="3fc65-108">This post-phase action can be used to perform actions by a single thread while all other threads are still blocked.</span></span> <span data-ttu-id="3fc65-109">Dopo l'esecuzione dell'azione, tutti i partecipanti verranno sbloccati.</span><span class="sxs-lookup"><span data-stu-id="3fc65-109">After the action has been executed, the participants are all unblocked.</span></span>  
  
 <span data-ttu-id="3fc65-110">Il frammento di codice seguente mostra un modello di barriera di base.</span><span class="sxs-lookup"><span data-stu-id="3fc65-110">The following code snippet shows a basic barrier pattern.</span></span>  
  
 [!code-csharp[CDS_Barrier#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#02)]
 [!code-vb[CDS_Barrier#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#02)]  
  
 <span data-ttu-id="3fc65-111">Per un esempio completo, vedere [Procedura: Sincronizzare operazioni simultanee con una barriera](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md).</span><span class="sxs-lookup"><span data-stu-id="3fc65-111">For a complete example, see [How to: Synchronize Concurrent Operations with a Barrier](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md).</span></span>  
  
## <a name="adding-and-removing-participants"></a><span data-ttu-id="3fc65-112">Aggiunta e rimozione di partecipanti</span><span class="sxs-lookup"><span data-stu-id="3fc65-112">Adding and Removing Participants</span></span>  
 <span data-ttu-id="3fc65-113">Quando si crea un oggetto <xref:System.Threading.Barrier>, specificare il numero di partecipanti.</span><span class="sxs-lookup"><span data-stu-id="3fc65-113">When you create a <xref:System.Threading.Barrier>, specify the number of participants.</span></span> <span data-ttu-id="3fc65-114">È anche possibile aggiungere o rimuovere dinamicamente i partecipanti in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="3fc65-114">You can also add or remove participants dynamically at any time.</span></span> <span data-ttu-id="3fc65-115">Se ad esempio un partecipante risolve la propria parte di problema, sarà possibile archiviare il risultato, arrestare l'esecuzione in quel thread e chiamare <xref:System.Threading.Barrier.RemoveParticipant%2A> per ridurre il numero di partecipanti nella barriera.</span><span class="sxs-lookup"><span data-stu-id="3fc65-115">For example, if one participant solves its part of the problem, you can store the result, stop execution on that thread, and call <xref:System.Threading.Barrier.RemoveParticipant%2A> to decrement the number of participants in the barrier.</span></span> <span data-ttu-id="3fc65-116">Quando si aggiunge un partecipante chiamando <xref:System.Threading.Barrier.AddParticipant%2A>, il valore restituito specifica il numero di fase attuale, che potrebbe essere utile per inizializzare il lavoro del nuovo partecipante.</span><span class="sxs-lookup"><span data-stu-id="3fc65-116">When you add a participant by calling <xref:System.Threading.Barrier.AddParticipant%2A>, the return value specifies the current phase number, which may be useful in order to initialize the work of the new participant.</span></span>  
  
## <a name="broken-barriers"></a><span data-ttu-id="3fc65-117">Barriere interrotte</span><span class="sxs-lookup"><span data-stu-id="3fc65-117">Broken Barriers</span></span>  
 <span data-ttu-id="3fc65-118">Se un partecipante non riesce a raggiungere la barriera, possono verificarsi deadlock.</span><span class="sxs-lookup"><span data-stu-id="3fc65-118">Deadlocks can occur if one participant fails to reach the barrier.</span></span> <span data-ttu-id="3fc65-119">Per evitare questi deadlock, usare gli overload del metodo <xref:System.Threading.Barrier.SignalAndWait%2A> per specificare un periodo di timeout e un token di annullamento.</span><span class="sxs-lookup"><span data-stu-id="3fc65-119">To avoid these deadlocks, use the overloads of the <xref:System.Threading.Barrier.SignalAndWait%2A> method to specify a time-out period and a cancellation token.</span></span> <span data-ttu-id="3fc65-120">Questi overload restituiscono un valore booleano che ogni partecipante può controllare prima di passare alla fase successiva.</span><span class="sxs-lookup"><span data-stu-id="3fc65-120">These overloads return a Boolean value that every participant can check before it continues to the next phase.</span></span>  
  
## <a name="post-phase-exceptions"></a><span data-ttu-id="3fc65-121">Eccezioni di post-fase</span><span class="sxs-lookup"><span data-stu-id="3fc65-121">Post-Phase Exceptions</span></span>  
 <span data-ttu-id="3fc65-122">Se il delegato post-fase genera un'eccezione, ne verrà eseguito il wrapping in un oggetto <xref:System.Threading.BarrierPostPhaseException>, che viene quindi propagato a tutti i partecipanti.</span><span class="sxs-lookup"><span data-stu-id="3fc65-122">If the post-phase delegate throws an exception, it is wrapped in a <xref:System.Threading.BarrierPostPhaseException> object which is then propagated to all participants.</span></span>  
  
## <a name="barrier-versus-continuewhenall"></a><span data-ttu-id="3fc65-123">Confronto tra barriera e ContinueWhenAll</span><span class="sxs-lookup"><span data-stu-id="3fc65-123">Barrier Versus ContinueWhenAll</span></span>  
 <span data-ttu-id="3fc65-124">Le barriere risultano particolarmente utili quando i thread eseguono più fasi nei cicli.</span><span class="sxs-lookup"><span data-stu-id="3fc65-124">Barriers are especially useful when the threads are performing multiple phases in loops.</span></span> <span data-ttu-id="3fc65-125">Se il codice richiede solo una o due fasi di lavoro, prendere in considerazione l'uso di oggetti <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> con qualsiasi tipo di join implicito, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3fc65-125">If your code requires only one or two phases of work, consider whether to use <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects with any kind of implicit join, including:</span></span>  
  
-   <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.Invoke%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.ForEach%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.For%2A>  
  
 <span data-ttu-id="3fc65-126">Per altre informazioni, vedere [Concatenamento di attività tramite attività di continuazione](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="3fc65-126">For more information, see [Chaining Tasks by Using Continuation Tasks](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fc65-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fc65-127">See also</span></span>

- <span data-ttu-id="3fc65-128">[Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) (Oggetti e funzionalità del threading)</span><span class="sxs-lookup"><span data-stu-id="3fc65-128">[Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)</span></span>  
- [<span data-ttu-id="3fc65-129">Procedura: Sincronizzare operazioni simultanee con una barriera</span><span class="sxs-lookup"><span data-stu-id="3fc65-129">How to: Synchronize Concurrent Operations with a Barrier</span></span>](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md)
