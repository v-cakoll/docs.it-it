---
title: 'Procedura: creare ed eseguire una query PLINQ semplice'
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
- PLINQ queries, how to create
ms.assetid: 983b4213-bddd-4a44-9262-cbe59186df4c
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 20b1be451e53a81dd0631a89310a5b884aa83166
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-create-and-execute-a-simple-plinq-query"></a><span data-ttu-id="dc97b-102">Procedura: creare ed eseguire una query PLINQ semplice</span><span class="sxs-lookup"><span data-stu-id="dc97b-102">How to: Create and Execute a Simple PLINQ Query</span></span>
<span data-ttu-id="dc97b-103">L'esempio seguente mostra come creare una semplice query Parallel LINQ usando il metodo di estensione <xref:System.Linq.ParallelEnumerable.AsParallel%2A> sulla sequenza di origine ed eseguendo la query tramite il metodo <xref:System.Linq.ParallelEnumerable.ForAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="dc97b-103">The following example shows how to create a simple Parallel LINQ query by using the <xref:System.Linq.ParallelEnumerable.AsParallel%2A> extension method on the source sequence, and executing the query by using the <xref:System.Linq.ParallelEnumerable.ForAll%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc97b-104">Le espressioni lambda sono usate nella documentazione per definire i delegati in PLINQ.</span><span class="sxs-lookup"><span data-stu-id="dc97b-104">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="dc97b-105">Se non si ha familiarità con le espressioni lambda in C# o Visual Basic, vedere [Espressioni lambda in PLINQ e TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="dc97b-105">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc97b-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="dc97b-106">Example</span></span>  
 [!code-csharp[PLINQ#11](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/create1.cs#11)]
 [!code-vb[PLINQ#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/create1.vb#11)]  
  
 <span data-ttu-id="dc97b-107">Questo esempio illustra il modello di base per la creazione e l'esecuzione di qualsiasi query Parallel LINQ nei casi in cui l'ordine della sequenza di risultati non è importante. Le query non ordinate sono in genere più veloci delle query ordinate.</span><span class="sxs-lookup"><span data-stu-id="dc97b-107">This example demonstrates the basic pattern for creating and executing any Parallel LINQ query when the ordering of the result sequence is not important; unordered queries are generally faster than ordered queries.</span></span> <span data-ttu-id="dc97b-108">La query partiziona l'origine in attività eseguita in modo asincrono su più thread.</span><span class="sxs-lookup"><span data-stu-id="dc97b-108">The query partitions the source into tasks that are executed asynchronously on multiple threads.</span></span> <span data-ttu-id="dc97b-109">L'ordine di completamento di ogni attività dipende non solo dalla quantità di lavoro necessario per l'elaborazione degli elementi nella partizione, ma anche da fattori esterni, ad esempio il modo in cui il sistema operativo pianifica ogni thread.</span><span class="sxs-lookup"><span data-stu-id="dc97b-109">The order in which each task completes depends not only on the amount of work involved to process the elements in the partition, but also on external factors such as how the operating system schedules each thread.</span></span> <span data-ttu-id="dc97b-110">Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente.</span><span class="sxs-lookup"><span data-stu-id="dc97b-110">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="dc97b-111">Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="dc97b-111">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span> <span data-ttu-id="dc97b-112">Per altre informazioni su come mantenere l'ordinamento degli elementi in una query, vedere [Procedura: Controllare l'ordinamento in una query PLINQ](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md).</span><span class="sxs-lookup"><span data-stu-id="dc97b-112">For more information about how to preserve the ordering of elements in a query, see [How to: Control Ordering in a PLINQ Query](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc97b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc97b-113">See Also</span></span>  
 [<span data-ttu-id="dc97b-114">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="dc97b-114">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
