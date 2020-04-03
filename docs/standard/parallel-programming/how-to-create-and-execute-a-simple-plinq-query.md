---
title: 'Procedura: creare ed eseguire una query PLINQ semplice'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create
ms.assetid: 983b4213-bddd-4a44-9262-cbe59186df4c
ms.openlocfilehash: c4cd75e55aabb551e5951a902ea6394a5659c9ee
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635848"
---
# <a name="how-to-create-and-execute-a-simple-plinq-query"></a><span data-ttu-id="a7105-102">Procedura: creare ed eseguire una query PLINQ semplice</span><span class="sxs-lookup"><span data-stu-id="a7105-102">How to: Create and Execute a Simple PLINQ Query</span></span>

<span data-ttu-id="a7105-103">Nell'esempio di questo articolo viene illustrato come creare una semplice <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=nameWithType> query LINQ (Parallel Language Integrated Query) <xref:System.Linq.ParallelEnumerable.ForAll%2A?displayProperty=nameWithTyp> utilizzando il metodo di estensione nella sequenza di origine ed eseguendo la query utilizzando il metodo .</span><span class="sxs-lookup"><span data-stu-id="a7105-103">The example in this article shows how to create a simple Parallel Language Integrated Query (LINQ) query by using the <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=nameWithType> extension method on the source sequence and executing the query by using the <xref:System.Linq.ParallelEnumerable.ForAll%2A?displayProperty=nameWithTyp> method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a7105-104">Le espressioni lambda sono usate nella documentazione per definire i delegati in PLINQ.</span><span class="sxs-lookup"><span data-stu-id="a7105-104">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="a7105-105">Se non si ha familiarità con le espressioni lambda in Visual Basic o in Visual Basic, vedere [Espressioni lambda in PLINQ e TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="a7105-105">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7105-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="a7105-106">Example</span></span>  
 [!code-csharp[PLINQ#11](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/create1.cs#11)]
 [!code-vb[PLINQ#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/create1.vb#11)]  
  
 <span data-ttu-id="a7105-107">In questo esempio viene illustrato il modello di base per la creazione e l'esecuzione di qualsiasi query Parallel LINQ quando l'ordine della sequenza di risultati non è importante.</span><span class="sxs-lookup"><span data-stu-id="a7105-107">This example demonstrates the basic pattern for creating and executing any Parallel LINQ query when the ordering of the result sequence is not important.</span></span> <span data-ttu-id="a7105-108">Le query non ordinate sono in genere più veloci delle query ordinate.</span><span class="sxs-lookup"><span data-stu-id="a7105-108">Unordered queries are generally faster than ordered queries.</span></span> <span data-ttu-id="a7105-109">La query partiziona l'origine in attività eseguita in modo asincrono su più thread.</span><span class="sxs-lookup"><span data-stu-id="a7105-109">The query partitions the source into tasks that are executed asynchronously on multiple threads.</span></span> <span data-ttu-id="a7105-110">L'ordine di completamento di ogni attività dipende non solo dalla quantità di lavoro necessario per l'elaborazione degli elementi nella partizione, ma anche da fattori esterni, ad esempio il modo in cui il sistema operativo pianifica ogni thread.</span><span class="sxs-lookup"><span data-stu-id="a7105-110">The order in which each task completes depends not only on the amount of work involved to process the elements in the partition, but also on external factors such as how the operating system schedules each thread.</span></span> <span data-ttu-id="a7105-111">Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente.</span><span class="sxs-lookup"><span data-stu-id="a7105-111">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="a7105-112">Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="a7105-112">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span> <span data-ttu-id="a7105-113">Per altre informazioni su come mantenere l'ordinamento degli elementi in una query, vedere [Procedura: Controllare l'ordinamento in una query PLINQ](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md).</span><span class="sxs-lookup"><span data-stu-id="a7105-113">For more information about how to preserve the ordering of elements in a query, see [How to: Control Ordering in a PLINQ Query](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7105-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7105-114">See also</span></span>

- [<span data-ttu-id="a7105-115">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="a7105-115">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
