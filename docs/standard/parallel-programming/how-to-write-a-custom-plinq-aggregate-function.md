---
title: 'Procedura: scrivere una funzione di aggregazione PLINQ personalizzata'
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
helpviewer_keywords: PLINQ queries, how to create aggregate function
ms.assetid: 5a70dd49-ab2a-4798-b551-196ee7042b1a
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8b098f21e29d0d59cd99ddbb64af6246d9953a3a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-custom-plinq-aggregate-function"></a><span data-ttu-id="39176-102">Procedura: scrivere una funzione di aggregazione PLINQ personalizzata</span><span class="sxs-lookup"><span data-stu-id="39176-102">How to: Write a Custom PLINQ Aggregate Function</span></span>
<span data-ttu-id="39176-103">In questo esempio viene illustrato come utilizzare il <xref:System.Linq.ParallelEnumerable.Aggregate%2A> per applicare una funzione di aggregazione personalizzata a una sequenza di origine.</span><span class="sxs-lookup"><span data-stu-id="39176-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.Aggregate%2A> method to apply a custom aggregation function to a source sequence.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="39176-104">Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente.</span><span class="sxs-lookup"><span data-stu-id="39176-104">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="39176-105">Per ulteriori informazioni sull'aumento di velocità, vedere [comprensione aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="39176-105">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="39176-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="39176-106">Example</span></span>  
 <span data-ttu-id="39176-107">L'esempio seguente calcola la deviazione standard di una sequenza di numeri interi.</span><span class="sxs-lookup"><span data-stu-id="39176-107">The following example calculates the standard deviation of a sequence of integers.</span></span>  
  
 [!code-csharp[PLINQ#31](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#31)]
 [!code-vb[PLINQ#31](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#31)]  
  
 <span data-ttu-id="39176-108">In questo esempio viene usato un overload dell'operatore di query standard di aggregazione che è univoco in PLINQ.</span><span class="sxs-lookup"><span data-stu-id="39176-108">This example uses an overload of the Aggregate standard query operator that is unique to PLINQ.</span></span> <span data-ttu-id="39176-109">Questo overload accetta un ulteriore <xref:System.Func%603?displayProperty=nameWithType> come terzo parametro di input.</span><span class="sxs-lookup"><span data-stu-id="39176-109">This overload takes an extra <xref:System.Func%603?displayProperty=nameWithType> as the third input parameter.</span></span> <span data-ttu-id="39176-110">Questo delegato combina i risultati di tutti i thread, prima di eseguire il calcolo finale i risultati aggregati.</span><span class="sxs-lookup"><span data-stu-id="39176-110">This delegate combines the results from all threads before it performs the final calculation on the aggregated results.</span></span> <span data-ttu-id="39176-111">In questo esempio si sommano le somme da tutti i thread.</span><span class="sxs-lookup"><span data-stu-id="39176-111">In this example we add together the sums from all the threads.</span></span>  
  
 <span data-ttu-id="39176-112">Si noti che quando un corpo di espressione lambda è costituito da un'unica espressione, il valore restituito di <xref:System.Func%602?displayProperty=nameWithType> delegato è il valore dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="39176-112">Note that when a lambda expression body consists of a single expression, the return value of the <xref:System.Func%602?displayProperty=nameWithType> delegate is the value of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39176-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39176-113">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="39176-114">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="39176-114">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
