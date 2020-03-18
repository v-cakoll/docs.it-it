---
title: Barriera
ms.date: 09/14/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, Barrier
ms.assetid: 613a8bc7-6a28-4795-bd6c-1abd9050478f
ms.openlocfilehash: 5aa34f7f39f4b9b626bea29372cf984f3cefb361
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138155"
---
# <a name="barrier"></a><span data-ttu-id="1b9b8-102">Barriera</span><span class="sxs-lookup"><span data-stu-id="1b9b8-102">Barrier</span></span>

<span data-ttu-id="1b9b8-103">Una classe <xref:System.Threading.Barrier?displayProperty=nameWithType> è una primitiva di sincronizzazione definita dall'utente che permette a più thread (noti come *partecipanti*) di lavorare contemporaneamente su un algoritmo in fasi diverse.</span><span class="sxs-lookup"><span data-stu-id="1b9b8-103">A <xref:System.Threading.Barrier?displayProperty=nameWithType> is a synchronization primitive that enables multiple threads (known as *participants*) to work concurrently on an algorithm in phases.</span></span> <span data-ttu-id="1b9b8-104">Ogni partecipante viene eseguito fino al raggiungimento del punto barriera nel codice.</span><span class="sxs-lookup"><span data-stu-id="1b9b8-104">Each participant executes until it reaches the barrier point in the code.</span></span> <span data-ttu-id="1b9b8-105">La barriera rappresenta la fine di una fase di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1b9b8-105">The barrier represents the end of one phase of work.</span></span> <span data-ttu-id="1b9b8-106">Quando un partecipante raggiunge la barriera, si blocca fino al raggiungimento della stessa barriera da parte di tutti i partecipanti.</span><span class="sxs-lookup"><span data-stu-id="1b9b8-106">When a participant reaches the barrier, it blocks until all participants have reached the same barrier.</span></span> <span data-ttu-id="1b9b8-107">Dopo che tutti i partecipanti hanno raggiunto la barriera, è possibile richiamare facoltativamente un'azione post- fase.</span><span class="sxs-lookup"><span data-stu-id="1b9b8-107">After all participants have reached the barrier, you can optionally invoke a post-phase action.</span></span> <span data-ttu-id="1b9b8-108">Questa azione post- fase può essere usata per eseguire azioni da parte di un singolo thread mentre tutti gli altri thread rimangono bloccati.</span><span class="sxs-lookup"><span data-stu-id="1b9b8-108">This post-phase action can be used to perform actions by a single thread while all other threads are still blocked.</span></span> <span data-ttu-id="1b9b8-109">Dopo l'esecuzione dell'azione, tutti i partecipanti verranno sbloccati.</span><span class="sxs-lookup"><span data-stu-id="1b9b8-109">After the action has been executed, the participants are all unblocked.</span></span>  
  
 <span data-ttu-id="1b9b8-110">Il frammento di codice seguente mostra un modello di barriera di base.</span><span class="sxs-lookup"><span data-stu-id="1b9b8-110">The following code snippet shows a basic barrier pattern.</span></span>  
  
 [!code-csharp[CDS_Barrier#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#02)]
 [!code-vb[CDS_Barrier#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#02)]  
  
 <span data-ttu-id="1b9b8-111">Per un esempio completo, vedere [Procedura: Sincronizzare operazioni simultanee con una barriera](how-to-synchronize-concurrent-operations-with-a-barrier.md).</span><span class="sxs-lookup"><span data-stu-id="1b9b8-111">For a complete example, see [How to: synchronize concurrent operations with a Barrier](how-to-synchronize-concurrent-operations-with-a-barrier.md).</span></span>  
  
## <a name="adding-and-removing-participants"></a><span data-ttu-id="1b9b8-112">Aggiunta e rimozione di partecipanti</span><span class="sxs-lookup"><span data-stu-id="1b9b8-112">Adding and removing participants</span></span>

 <span data-ttu-id="1b9b8-113">Quando si crea un'istanza di <xref:System.Threading.Barrier>, specificare il numero di partecipanti.</span><span class="sxs-lookup"><span data-stu-id="1b9b8-113">When you create a <xref:System.Threading.Barrier> instance, specify the number of participants.</span></span> <span data-ttu-id="1b9b8-114">È anche possibile aggiungere o rimuovere dinamicamente i partecipanti in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="1b9b8-114">You can also add or remove participants dynamically at any time.</span></span> <span data-ttu-id="1b9b8-115">Se ad esempio un partecipante risolve la propria parte di problema, sarà possibile archiviare il risultato, arrestare l'esecuzione in quel thread e chiamare <xref:System.Threading.Barrier.RemoveParticipant%2A?displayProperty=nameWithType> per ridurre il numero di partecipanti nella barriera.</span><span class="sxs-lookup"><span data-stu-id="1b9b8-115">For example, if one participant solves its part of the problem, you can store the result, stop execution on that thread, and call <xref:System.Threading.Barrier.RemoveParticipant%2A?displayProperty=nameWithType> to decrement the number of participants in the barrier.</span></span> <span data-ttu-id="1b9b8-116">Quando si aggiunge un partecipante chiamando <xref:System.Threading.Barrier.AddParticipant%2A?displayProperty=nameWithType>, il valore restituito specifica il numero di fase attuale, che potrebbe essere utile per inizializzare il lavoro del nuovo partecipante.</span><span class="sxs-lookup"><span data-stu-id="1b9b8-116">When you add a participant by calling <xref:System.Threading.Barrier.AddParticipant%2A?displayProperty=nameWithType>, the return value specifies the current phase number, which may be useful in order to initialize the work of the new participant.</span></span>  
  
## <a name="broken-barriers"></a><span data-ttu-id="1b9b8-117">Barriere interrotte</span><span class="sxs-lookup"><span data-stu-id="1b9b8-117">Broken barriers</span></span>

 <span data-ttu-id="1b9b8-118">Se un partecipante non riesce a raggiungere la barriera, possono verificarsi deadlock.</span><span class="sxs-lookup"><span data-stu-id="1b9b8-118">Deadlocks can occur if one participant fails to reach the barrier.</span></span> <span data-ttu-id="1b9b8-119">Per evitare questi deadlock, usare gli overload del metodo <xref:System.Threading.Barrier.SignalAndWait%2A?displayProperty=nameWithType> per specificare un periodo di timeout e un token di annullamento.</span><span class="sxs-lookup"><span data-stu-id="1b9b8-119">To avoid these deadlocks, use the overloads of the <xref:System.Threading.Barrier.SignalAndWait%2A?displayProperty=nameWithType> method to specify a time-out period and a cancellation token.</span></span> <span data-ttu-id="1b9b8-120">Questi overload restituiscono un valore booleano che ogni partecipante può controllare prima di passare alla fase successiva.</span><span class="sxs-lookup"><span data-stu-id="1b9b8-120">These overloads return a Boolean value that every participant can check before it continues to the next phase.</span></span>  
  
## <a name="post-phase-exceptions"></a><span data-ttu-id="1b9b8-121">Eccezioni di post-fase</span><span class="sxs-lookup"><span data-stu-id="1b9b8-121">Post-phase exceptions</span></span>

 <span data-ttu-id="1b9b8-122">Se il delegato post-fase genera un'eccezione, ne verrà eseguito il wrapping in un oggetto <xref:System.Threading.BarrierPostPhaseException>, che viene quindi propagato a tutti i partecipanti.</span><span class="sxs-lookup"><span data-stu-id="1b9b8-122">If the post-phase delegate throws an exception, it is wrapped in a <xref:System.Threading.BarrierPostPhaseException> object which is then propagated to all participants.</span></span>  
  
## <a name="barrier-versus-continuewhenall"></a><span data-ttu-id="1b9b8-123">Confronto tra barriera e ContinueWhenAll</span><span class="sxs-lookup"><span data-stu-id="1b9b8-123">Barrier versus ContinueWhenAll</span></span>

 <span data-ttu-id="1b9b8-124">Le barriere risultano particolarmente utili quando i thread eseguono più fasi nei cicli.</span><span class="sxs-lookup"><span data-stu-id="1b9b8-124">Barriers are especially useful when the threads are performing multiple phases in loops.</span></span> <span data-ttu-id="1b9b8-125">Se il codice richiede solo una o due fasi di lavoro, prendere in considerazione l'uso di oggetti <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> con qualsiasi tipo di join implicito, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="1b9b8-125">If your code requires only one or two phases of work, consider whether to use <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects with any kind of implicit join, including:</span></span>  
  
- <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="1b9b8-126">Per altre informazioni, vedere [Concatenamento di attività tramite attività di continuazione](../parallel-programming/chaining-tasks-by-using-continuation-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="1b9b8-126">For more information, see [Chaining Tasks by Using Continuation Tasks](../parallel-programming/chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b9b8-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b9b8-127">See also</span></span>

- [<span data-ttu-id="1b9b8-128">Oggetti e funzionalità del threading</span><span class="sxs-lookup"><span data-stu-id="1b9b8-128">Threading objects and features</span></span>](threading-objects-and-features.md)
- [<span data-ttu-id="1b9b8-129">Procedura: Sincronizzare operazioni simultanee con una barriera</span><span class="sxs-lookup"><span data-stu-id="1b9b8-129">How to: synchronize concurrent operations with a Barrier</span></span>](how-to-synchronize-concurrent-operations-with-a-barrier.md)
