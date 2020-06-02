---
title: 'Procedura: Annullare una query PLINQ'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to cancel
- cancellation, PLINQ
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
ms.openlocfilehash: 09405a8a9f5d96d80454bcc98cbf29db54df6725
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288212"
---
# <a name="how-to-cancel-a-plinq-query"></a><span data-ttu-id="32d52-102">Procedura: Annullare una query PLINQ</span><span class="sxs-lookup"><span data-stu-id="32d52-102">How to: Cancel a PLINQ Query</span></span>
<span data-ttu-id="32d52-103">Gli esempi seguenti descrivono due modi per annullare una query PLINQ.</span><span class="sxs-lookup"><span data-stu-id="32d52-103">The following examples show two ways to cancel a PLINQ query.</span></span> <span data-ttu-id="32d52-104">Il primo esempio descrive come annullare una query costituita principalmente da attraversamento di dati.</span><span class="sxs-lookup"><span data-stu-id="32d52-104">The first example shows how to cancel a query that consists mostly of data traversal.</span></span> <span data-ttu-id="32d52-105">Il secondo esempio descrive come annullare una query che contiene una funzione utente onerosa dal punto di vista delle risorse di calcolo.</span><span class="sxs-lookup"><span data-stu-id="32d52-105">The second example shows how to cancel a query that contains a user function that is computationally expensive.</span></span>

> [!NOTE]
> <span data-ttu-id="32d52-106">Quando è abilitato "Just My Code", Visual Studio si interrompe in corrispondenza della riga che genera l'eccezione e visualizza un messaggio di errore che indica che l'eccezione non è stata gestita dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="32d52-106">When "Just My Code" is enabled, Visual Studio will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="32d52-107">Questo errore non è grave.</span><span class="sxs-lookup"><span data-stu-id="32d52-107">This error is benign.</span></span> <span data-ttu-id="32d52-108">È possibile premere F5 per continuare e osservare il comportamento di gestione delle eccezioni illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="32d52-108">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="32d52-109">Per impedire l'interruzione di Visual Studio al primo errore, deselezionare semplicemente la casella di controllo "Just My Code" in **Strumenti, Opzioni, Debug, Generale**.</span><span class="sxs-lookup"><span data-stu-id="32d52-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>
>
> <span data-ttu-id="32d52-110">Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente.</span><span class="sxs-lookup"><span data-stu-id="32d52-110">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="32d52-111">Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="32d52-111">For more information about speedup, see [Understanding Speedup in PLINQ](understanding-speedup-in-plinq.md).</span></span>

## <a name="example"></a><span data-ttu-id="32d52-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="32d52-112">Example</span></span>

[!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
[!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]

<span data-ttu-id="32d52-113">Il framework PLINQ non gestisce un singolo oggetto <xref:System.OperationCanceledException> in un oggetto <xref:System.AggregateException?displayProperty=nameWithType>. L'oggetto <xref:System.OperationCanceledException> deve essere gestito in un blocco catch separato.</span><span class="sxs-lookup"><span data-stu-id="32d52-113">The PLINQ framework does not roll a single <xref:System.OperationCanceledException> into an <xref:System.AggregateException?displayProperty=nameWithType>; the <xref:System.OperationCanceledException> must be handled in a separate catch block.</span></span> <span data-ttu-id="32d52-114">Se uno o più delegati dell'utente generano un oggetto OperationCanceledException (externalCT), usando un oggetto <xref:System.Threading.CancellationToken?displayProperty=nameWithType> esterno, ma senza altre eccezioni e se la query è stata definita come `AsParallel().WithCancellation(externalCT)`, PLINQ genererà un singolo oggetto <xref:System.OperationCanceledException>(externalCT) anziché un oggetto <xref:System.AggregateException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="32d52-114">If one or more user delegates throws an OperationCanceledException(externalCT) (by using an external <xref:System.Threading.CancellationToken?displayProperty=nameWithType>) but no other exception, and the query was defined as `AsParallel().WithCancellation(externalCT)`, then PLINQ will issue a single <xref:System.OperationCanceledException> (externalCT) rather than an <xref:System.AggregateException?displayProperty=nameWithType>.</span></span> <span data-ttu-id="32d52-115">Tuttavia, se un delegato dell'utente genera un oggetto <xref:System.OperationCanceledException> e un altro delegato genera un altro tipo di eccezione, entrambe le eccezioni vengono gestite in un oggetto <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="32d52-115">However, if one user delegate throws an <xref:System.OperationCanceledException>, and another delegate throws another exception type, then both exceptions will be rolled into an <xref:System.AggregateException>.</span></span>

<span data-ttu-id="32d52-116">Le indicazioni generali sull'annullamento sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="32d52-116">The general guidance on cancellation is as follows:</span></span>

1. <span data-ttu-id="32d52-117">Se si esegue l'annullamento delegata dall'utente, è necessario informare PLINQ sull'esterno <xref:System.Threading.CancellationToken> e generare un <xref:System.OperationCanceledException> (externalCT).</span><span class="sxs-lookup"><span data-stu-id="32d52-117">If you perform user-delegate cancellation, you should inform PLINQ about the external <xref:System.Threading.CancellationToken> and throw an <xref:System.OperationCanceledException>(externalCT).</span></span>

2. <span data-ttu-id="32d52-118">Se si verifica l'annullamento e non vengono generate altre eccezioni, gestire un oggetto <xref:System.OperationCanceledException> anziché un oggetto <xref:System.AggregateException> .</span><span class="sxs-lookup"><span data-stu-id="32d52-118">If cancellation occurs and no other exceptions are thrown, then handle an <xref:System.OperationCanceledException> rather than an <xref:System.AggregateException>.</span></span>

## <a name="example"></a><span data-ttu-id="32d52-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="32d52-119">Example</span></span>

<span data-ttu-id="32d52-120">L'esempio seguente mostra come gestire l'annullamento in presenza di una funzione onerosa dal punto di vista delle risorse di calcolo nel codice utente.</span><span class="sxs-lookup"><span data-stu-id="32d52-120">The following example shows how to handle cancellation when you have a computationally expensive function in user code.</span></span>

[!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
[!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]

<span data-ttu-id="32d52-121">Quando si gestisce l'annullamento nel codice utente, non è necessario usare <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> nella definizione di query.</span><span class="sxs-lookup"><span data-stu-id="32d52-121">When you handle the cancellation in user code, you do not have to use <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> in the query definition.</span></span> <span data-ttu-id="32d52-122">Tuttavia, si consiglia di utilizzare <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> , poiché <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> non ha effetto sulle prestazioni delle query e consente di gestire l'annullamento dagli operatori di query e dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="32d52-122">However, we recommended that you do use <xref:System.Linq.ParallelEnumerable.WithCancellation%2A>, because <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> has no effect on query performance and it enables the cancellation to be handled by query operators and your user code.</span></span>

<span data-ttu-id="32d52-123">Per garantire velocità di risposta del sistema, è consigliabile verificare l'annullamento circa una volta al millisecondo, ma è considerato accettabile qualsiasi periodo fino a 10 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="32d52-123">In order to ensure system responsiveness, we recommend that you check for cancellation around once per millisecond; however, any period up to 10 milliseconds is considered acceptable.</span></span> <span data-ttu-id="32d52-124">Questa frequenza non dovrebbe avere impatto negativo sulle prestazioni del codice.</span><span class="sxs-lookup"><span data-stu-id="32d52-124">This frequency should not have a negative impact on your code's performance.</span></span>

<span data-ttu-id="32d52-125">Quando un enumeratore viene eliminato, ad esempio quando il codice si interrompe da un ciclo foreach (for each in Visual Basic) che esegue l'iterazione sui risultati della query, la query viene annullata, ma non viene generata alcuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="32d52-125">When an enumerator is disposed, for example when code breaks out of a foreach (For Each in Visual Basic) loop that is iterating over query results, then the query is canceled, but no exception is thrown.</span></span>

## <a name="see-also"></a><span data-ttu-id="32d52-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32d52-126">See also</span></span>

- <xref:System.Linq.ParallelEnumerable>
- [<span data-ttu-id="32d52-127">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="32d52-127">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
- [<span data-ttu-id="32d52-128">Annullamento in thread gestiti</span><span class="sxs-lookup"><span data-stu-id="32d52-128">Cancellation in Managed Threads</span></span>](../threading/cancellation-in-managed-threads.md)
