---
title: 'Procedura: scrivere una funzione di aggregazione PLINQ personalizzata'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create aggregate function
ms.assetid: 5a70dd49-ab2a-4798-b551-196ee7042b1a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7aa2a8e5d9695c08d1c98e05cdd1eaa4d9a5318
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33580910"
---
# <a name="how-to-write-a-custom-plinq-aggregate-function"></a><span data-ttu-id="8ac66-102">Procedura: scrivere una funzione di aggregazione PLINQ personalizzata</span><span class="sxs-lookup"><span data-stu-id="8ac66-102">How to: Write a Custom PLINQ Aggregate Function</span></span>
<span data-ttu-id="8ac66-103">Questo esempio mostra come usare il metodo <xref:System.Linq.ParallelEnumerable.Aggregate%2A> per applicare una funzione di aggregazione personalizzata a una sequenza di origine.</span><span class="sxs-lookup"><span data-stu-id="8ac66-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.Aggregate%2A> method to apply a custom aggregation function to a source sequence.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="8ac66-104">Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente.</span><span class="sxs-lookup"><span data-stu-id="8ac66-104">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="8ac66-105">Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="8ac66-105">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ac66-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="8ac66-106">Example</span></span>  
 <span data-ttu-id="8ac66-107">L'esempio seguente calcola la deviazione standard di una sequenza di numeri interi.</span><span class="sxs-lookup"><span data-stu-id="8ac66-107">The following example calculates the standard deviation of a sequence of integers.</span></span>  
  
 [!code-csharp[PLINQ#31](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#31)]
 [!code-vb[PLINQ#31](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#31)]  
  
 <span data-ttu-id="8ac66-108">L'esempio usa un overload dell'operatore query standard Aggregate specifico di PLINQ.</span><span class="sxs-lookup"><span data-stu-id="8ac66-108">This example uses an overload of the Aggregate standard query operator that is unique to PLINQ.</span></span> <span data-ttu-id="8ac66-109">Questo overload accetta un oggetto <xref:System.Func%603?displayProperty=nameWithType> aggiuntivo come terzo parametro di input.</span><span class="sxs-lookup"><span data-stu-id="8ac66-109">This overload takes an extra <xref:System.Func%603?displayProperty=nameWithType> as the third input parameter.</span></span> <span data-ttu-id="8ac66-110">Questo delegato combina i risultati di tutti i thread prima di eseguire il calcolo finale sui risultati aggregati.</span><span class="sxs-lookup"><span data-stu-id="8ac66-110">This delegate combines the results from all threads before it performs the final calculation on the aggregated results.</span></span> <span data-ttu-id="8ac66-111">In questo esempio si sommano i totali di tutti i thread.</span><span class="sxs-lookup"><span data-stu-id="8ac66-111">In this example we add together the sums from all the threads.</span></span>  
  
 <span data-ttu-id="8ac66-112">Si noti che quando il corpo di un'espressione lambda è costituito da una singola espressione, il valore restituito dal delegato <xref:System.Func%602?displayProperty=nameWithType> è il valore dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="8ac66-112">Note that when a lambda expression body consists of a single expression, the return value of the <xref:System.Func%602?displayProperty=nameWithType> delegate is the value of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ac66-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ac66-113">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="8ac66-114">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="8ac66-114">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
