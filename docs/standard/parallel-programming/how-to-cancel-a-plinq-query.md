---
title: 'Procedura: annullare una query PLINQ'
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
- PLINQ queries, how to cancel
- cancellation, PLINQ
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d8031758462df45c030b8b75a3507f1bfb44bfd0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-plinq-query"></a><span data-ttu-id="7125a-102">Procedura: annullare una query PLINQ</span><span class="sxs-lookup"><span data-stu-id="7125a-102">How to: Cancel a PLINQ Query</span></span>
<span data-ttu-id="7125a-103">Gli esempi seguenti mostrano due modi per annullare una query PLINQ.</span><span class="sxs-lookup"><span data-stu-id="7125a-103">The following examples show two ways to cancel a PLINQ query.</span></span> <span data-ttu-id="7125a-104">Nel primo esempio viene illustrato come annullare una query che è costituito principalmente da attraversamento di dati.</span><span class="sxs-lookup"><span data-stu-id="7125a-104">The first example shows how to cancel a query that consists mostly of data traversal.</span></span> <span data-ttu-id="7125a-105">Nel secondo esempio viene illustrato come annullare una query che contiene una funzione utente che è dispendiosa.</span><span class="sxs-lookup"><span data-stu-id="7125a-105">The second example shows how to cancel a query that contains a user function that is computationally expensive.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7125a-106">Quando "Just My Code" è abilitato, Visual interruzione sulla riga che genera l'eccezione e verrà visualizzato un messaggio di errore simile a "eccezione non gestita dal codice utente".</span><span class="sxs-lookup"><span data-stu-id="7125a-106">When "Just My Code" is enabled, Visual Studio will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="7125a-107">Questo errore non è grave.</span><span class="sxs-lookup"><span data-stu-id="7125a-107">This error is benign.</span></span> <span data-ttu-id="7125a-108">È possibile premere F5 per continuare e osservare il comportamento di gestione delle eccezioni illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="7125a-108">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="7125a-109">Per impedire l'interruzione per il primo errore di Visual Studio, deselezionare semplicemente la casella di controllo "Just My Code" **strumenti, opzioni, debug, generale**.</span><span class="sxs-lookup"><span data-stu-id="7125a-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
>   
>  <span data-ttu-id="7125a-110">Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente.</span><span class="sxs-lookup"><span data-stu-id="7125a-110">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="7125a-111">Per ulteriori informazioni sull'aumento di velocità, vedere [comprensione aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="7125a-111">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7125a-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="7125a-112">Example</span></span>  
 [!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
 [!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]  
  
 <span data-ttu-id="7125a-113">Il framework PLINQ non esegue il rollback di una singola <xref:System.OperationCanceledException> in un <xref:System.AggregateException?displayProperty=nameWithType>; <xref:System.OperationCanceledException> devono essere gestiti in un blocco catch separato.</span><span class="sxs-lookup"><span data-stu-id="7125a-113">The PLINQ framework does not roll a single <xref:System.OperationCanceledException> into an <xref:System.AggregateException?displayProperty=nameWithType>; the <xref:System.OperationCanceledException> must be handled in a separate catch block.</span></span> <span data-ttu-id="7125a-114">Se uno o più utente genera un oggetto OperationCanceledException (utilizzando un riferimento esterno <xref:System.Threading.CancellationToken?displayProperty=nameWithType>) ma non altre eccezioni e la query è stata definita come `AsParallel().WithCancellation(externalCT)`, PLINQ genererà un singolo <xref:System.OperationCanceledException> (externalCT) anziché un oggetto <xref:System.AggregateException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7125a-114">If one or more user delegates throws an OperationCanceledException(externalCT) (by using an external <xref:System.Threading.CancellationToken?displayProperty=nameWithType>) but no other exception, and the query was defined as `AsParallel().WithCancellation(externalCT)`, then PLINQ will issue a single <xref:System.OperationCanceledException> (externalCT) rather than an <xref:System.AggregateException?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7125a-115">Tuttavia, se un utente delegato genera un <xref:System.OperationCanceledException>e un altro delegato genera un altro tipo di eccezione, quindi entrambe le eccezioni verranno incluse in un <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="7125a-115">However, if one user delegate throws an <xref:System.OperationCanceledException>, and another delegate throws another exception type, then both exceptions will be rolled into an <xref:System.AggregateException>.</span></span>  
  
 <span data-ttu-id="7125a-116">Le indicazioni generali al momento dell'annullamento sono come segue:</span><span class="sxs-lookup"><span data-stu-id="7125a-116">The general guidance on cancellation is as follows:</span></span>  
  
1.  <span data-ttu-id="7125a-117">Se si esegue l'annullamento di delegato dell'utente è necessario informare PLINQ esterno <xref:System.Threading.CancellationToken> e generare un <xref:System.OperationCanceledException>(externalCT).</span><span class="sxs-lookup"><span data-stu-id="7125a-117">If you perform user-delegate cancellation you should inform PLINQ about the external <xref:System.Threading.CancellationToken> and throw an <xref:System.OperationCanceledException>(externalCT).</span></span>  
  
2.  <span data-ttu-id="7125a-118">Se si verifica l'annullamento e non altri vengono generate eccezioni, è necessario gestire un <xref:System.OperationCanceledException> anziché un oggetto <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="7125a-118">If cancellation occurs and no other exceptions are thrown, then you should handle an <xref:System.OperationCanceledException> rather than an <xref:System.AggregateException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7125a-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="7125a-119">Example</span></span>  
 <span data-ttu-id="7125a-120">Nell'esempio seguente viene illustrato come gestire l'annullamento quando si dispone di una funzione dispendiosa a livello di codice utente.</span><span class="sxs-lookup"><span data-stu-id="7125a-120">The following example shows how to handle cancellation when you have a computationally expensive function in user code.</span></span>  
  
 [!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
 [!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]  
  
 <span data-ttu-id="7125a-121">Quando si gestisce l'annullamento nel codice utente, non è necessario utilizzare <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> nella definizione della query.</span><span class="sxs-lookup"><span data-stu-id="7125a-121">When you handle the cancellation in user code, you do not have to use <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> in the query definition.</span></span> <span data-ttu-id="7125a-122">Tuttavia, è consigliabile farlo perché <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> non ha alcun effetto sulle prestazioni delle query e consente l'annullamento deve essere gestito da operatori di query e il codice utente.</span><span class="sxs-lookup"><span data-stu-id="7125a-122">However, we recommended that you do this because <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> has no effect on query performance and it enables the cancellation to be handled by query operators and your user code.</span></span>  
  
 <span data-ttu-id="7125a-123">Per garantire velocità di risposta del sistema, si consiglia di verificare la disponibilità di annullamento circa una volta al millisecondo. Tuttavia, qualsiasi periodo fino a 10 millisecondi viene considerata accettabile.</span><span class="sxs-lookup"><span data-stu-id="7125a-123">In order to ensure system responsiveness, we recommend that you check for cancellation around once per millisecond; however, any period up to 10 milliseconds is considered acceptable.</span></span> <span data-ttu-id="7125a-124">Questa frequenza senza un impatto negativo sulle prestazioni del codice.</span><span class="sxs-lookup"><span data-stu-id="7125a-124">This frequency should not have a negative impact on your code's performance.</span></span>  
  
 <span data-ttu-id="7125a-125">Quando viene eliminato un enumeratore, ad esempio quando il codice esce da un ciclo foreach (For Each in Visual Basic) che esegue l'iterazione sui risultati di query, quindi la query è stata annullata, ma viene generata alcuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="7125a-125">When an enumerator is disposed, for example when code breaks out of a foreach (For Each in Visual Basic) loop that is iterating over query results, then the query is cancelled, but no exception is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7125a-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7125a-126">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="7125a-127">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="7125a-127">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [<span data-ttu-id="7125a-128">Annullamento in thread gestiti</span><span class="sxs-lookup"><span data-stu-id="7125a-128">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
